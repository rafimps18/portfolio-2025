<script lang="ts">
	import { onDestroy, onMount } from 'svelte';

	let {
		headerText,
		description,
		imageUrl,
		altText,
		index,
		link,
		github,
		techStack
	}: {
		headerText: string;
		description: string;
		imageUrl: string;
		altText: string;
		index: number;
		link: string | undefined;
		github: string | undefined;
		techStack: string[];
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
		: 'fadeFromRight'} flex h-fit w-fit flex-col items-center justify-center gap-4 rounded-lg border-l-8 border-(--blue-primary) bg-(--white-primary) px-6 py-4 lg:w-[50vw]"
>
	<div>
		<h1 class="exo-700 text-center text-2xl">{headerText}</h1>
	</div>
	<div>
		<img bind:this={img} src={imageUrl} alt={altText} />
	</div>
	<div class="flex flex-col items-center justify-center gap-2">
		<p class="exo-500 text-center text-xl text-wrap">{description}</p>
		<div class="flex flex-col text-center text-lg md:flex-row">
			<h1 class="mr-1">Tech Stack:</h1>
			<p>{techStack.join(', ')}</p>
		</div>
		{#if link}
			<div class="flex flex-row gap-6">
				<div class="flex gap-2">
					{#if github}
						<a
							href={github}
							target="_blank"
							class="bg-white-primary flex gap-2 rounded-lg px-4 py-2 hover:bg-gray-300 active:bg-gray-400"
						>
							<img src="icons/github-original.svg" alt="github icon" width="25" />
							<p>View Code</p>
						</a>
					{/if}
					<a
						href={link}
						target="_blank"
						class="bg-white-primary flex gap-2 rounded-lg px-4 py-2 hover:bg-gray-300 active:bg-gray-400"
					>
						<img src="icons/link.svg" alt="github icon" width="25" />
						<p>View Live</p>
					</a>
				</div>
			</div>
		{/if}
	</div>
</div>
