<script lang="ts">
	import { onDestroy, onMount } from "svelte";

	let {
		headerText,
		description,
		imageUrl,
        altText,
        index,
	}: { headerText: string; description: string; imageUrl: string; altText: string; index: number; } = $props();

    let img: Element;
    let imgVisible: boolean = $state(false);
    let observer: IntersectionObserver;

    onMount(()=>{
        observer = new IntersectionObserver(
         ([entry]) => { 
                if (!imgVisible) {
                    imgVisible = entry.isIntersecting
                }
            },
            { threshold: 0.3 }
        )
        observer.observe(img);
    })

    onDestroy(()=>{
        if (observer) observer.disconnect(); 
    })
</script>

<div class="{imgVisible ? 'visibleX' : ''} {index%2 ? 'fadeFromLeft' : 'fadeFromRight' } h-fit w-fit bg-(--white-primary) border-l-8 border-(--blue-primary) py-4 px-6 gap-4 flex flex-col justify-center items-center">
	<div>
		<h1 class="exo-700 text-2xl text-center">{headerText}</h1>
	</div>
	<div>
		<img bind:this={img} src={imageUrl} class="w-full lg:w-[50vw]" alt={altText} />
	</div>
    <p class="exo-500 text-xl">{description}</p>
</div>