<script lang="ts">
	import { onMount } from "svelte";

	let {
		headerText,
		description,
		imageUrl,
        altText,
	}: { headerText: string; description: string; imageUrl: string; altText: string; } = $props();

    let img: any;
    let imgVisible: boolean = $state(false);

    onMount(()=>{
        const observer = new IntersectionObserver(
         ([entry]) => { 
                if (!imgVisible) {
                    imgVisible = entry.isIntersecting
                }
            },
            { threshold: 0.3 }
        )

        observer.observe(img);
    })
</script>

<div class="{imgVisible ? 'visible' : ''} fadeFromTop h-fit w-fit bg-(--white-primary) border-l-8 border-(--blue-primary) py-4 px-6 gap-4 flex flex-col justify-center items-center">
	<div>
		<h1 class="exo-700 text-2xl text-center">{headerText}</h1>
	</div>
	<div>
		<img bind:this={img} src={imageUrl} class="w-full lg:w-[50vw]" alt={altText} />
	</div>
    <p class="exo-500 text-xl">{description}</p>
</div>

<style>
    
</style>