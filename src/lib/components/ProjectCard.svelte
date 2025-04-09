<script lang="ts">
	import { onDestroy, onMount } from 'svelte';

	let {
		headerText,
		description,
		imageUrl,
		altText,
		index,
		link
	}: {
		headerText: string;
		description: string;
		imageUrl: string;
		altText: string;
		index: number;
		link: string;
	} = $props();

	let img: Element;
	let imgVisible: boolean = $state(false);
	let observer: IntersectionObserver;

	onMount(() => {
		observer = new IntersectionObserver(
			([entry]) => {
				if (!imgVisible) {
					imgVisible = entry.isIntersecting;
				}
			},
			{ threshold: 0.3 }
		);
		observer.observe(img);
	});

	onDestroy(() => {
		if (observer) observer.disconnect();
	});
</script>

<div
	class="{imgVisible ? 'visibleX' : ''} {index % 2
		? 'fadeFromLeft'
		: 'fadeFromRight'} flex h-fit w-fit flex-col items-center justify-center gap-4 border-l-8 border-(--blue-primary) bg-(--white-primary) px-6 py-4"
>
	<div>
		{#if link.length > 0}
			<a
				class="flex flex-row gap-2 hover:text-sky-600 active:text-sky-700"
				href={link}
				target="_blank"
			>
				<h1 class="exo-700 text-center text-2xl">{headerText}</h1>
				<img src="/open.svg" alt="open icon" />
			</a>
		{:else}
			<h1 class="exo-700 text-center text-2xl">{headerText}</h1>
		{/if}
	</div>
	<div>
		<img bind:this={img} src={imageUrl} class="w-full lg:w-[50vw]" alt={altText} />
	</div>
	<p class="exo-500 text-xl">{description}</p>
</div>
