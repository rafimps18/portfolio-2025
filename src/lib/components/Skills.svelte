<script lang="ts">
	import { skillsDevTools, skillsFrameworks, skillsLang } from '$lib';
	import { onMount } from 'svelte';
	import { onDestroy } from 'svelte';

	let skillsContainer: Element;
	let skillsContainerVisible: boolean = $state(false);
	let sections = ['Languages', 'Frameworks', 'Development Tools'];

	const skillsLangFirstHalf = skillsLang.slice(0, skillsLang.length / 2);
	const skillsLangSecondHalf = skillsLang.slice(skillsLang.length/2, skillsLang.length);
	const skillsFrameworksFirstHalf = skillsFrameworks.slice(0, skillsFrameworks.length / 2);
	const skillsFrameworksSecondHalf = skillsFrameworks.slice(skillsFrameworks.length/2, skillsFrameworks.length);

	let observer: IntersectionObserver;

	onMount(() => {
		observer = new IntersectionObserver(
			([entry]) => {
				if (!skillsContainerVisible) {
					skillsContainerVisible = entry.isIntersecting;
				}
			},
			{ threshold: 0.3 }
		);

		observer.observe(skillsContainer);
	});

	onDestroy(() => {
		if (observer) observer.disconnect();
	});
</script>

<div class="relative w-screen min-h-screen">
	<div
		class="bg-radial-[at_0%_50%] absolute z-20 inset-0 animate-pulse from-purple-700 to-black to-40% bg-fixed opacity-40 md:h-screen"
	></div>
	<div
		class="bg-radial-[at_100%_50%] absolute z-20 inset-0 animate-pulse from-purple-700 to-black to-40% bg-fixed opacity-40 md:h-screen"
	></div>
	<div class="absolute z-30">
		<div id="tools" class="flex min-h-screen w-screen flex-col items-center justify-center pt-12">
			<div class="border-(--blue-secondary) mb-4 border-b-4">
				<h1 class="exo-700 mt-1 text-3xl text-white">My Tools</h1>
			</div>
			<div class="flex h-full w-full flex-row items-center justify-center gap-4 px-12">
				<div
					bind:this={skillsContainer}
					class="{skillsContainerVisible
						? 'visibleY'
						: ''} fadeFromTop bg-(--white-primary) border-(--blue-primary) min-h-[50vh] w-full border-l-8 px-8 py-2 lg:w-[60%]"
				>
					{#each sections as section, index}
						<h1
							class="exo-700 border-(--red-primary) mb-2 border-b-4 text-center text-3xl text-black"
						>
							{section}
						</h1>
						{#if index===0}
							<div class="flex flex-col items-center justify-center gap-2 md:flex-row md:gap-8">
								<div class="flex flex-row items-center justify-center gap-8 py-2">
									{#each skillsLangFirstHalf as skill}
										<div class="flex w-fit flex-col items-center justify-center gap-2">
											<img src={skill.src} class="w-[50px]" alt={skill.altText} />
											<h2 class="exo-500 text-lg text-black">{skill.name}</h2>
										</div>
									{/each}
								</div>
								<div class="flex flex-row items-center justify-center gap-8 py-2">
									{#each skillsLangSecondHalf as skill}
										<div class="flex w-fit flex-col items-center justify-center gap-2">
											<img src={skill.src} class="w-[50px]" alt={skill.altText} />
											<h2 class="exo-500 text-lg text-black">{skill.name}</h2>
										</div>
									{/each}
								</div>
							</div>
						{:else if index===1}
							<div class="flex flex-col items-center justify-center gap-2 md:flex-row md:gap-8">
								<div class="flex flex-row items-center justify-center gap-8 py-2">
									{#each skillsFrameworksFirstHalf as framework}
										<div class="flex w-fit flex-col items-center justify-center gap-2">
											<img src={framework.src} class="w-[50px]" alt={framework.altText} />
											<h2 class="exo-500 text-lg text-black">{framework.name}</h2>
										</div>
									{/each}
								</div>
								<div class="flex flex-row items-center justify-center gap-8">
									{#each skillsFrameworksSecondHalf as framework}
										<div class="flex w-fit flex-col items-center justify-center gap-2">
											<img src={framework.src} class="w-[50px]" alt={framework.altText} />
											<h2 class="exo-500 text-lg text-black">{framework.name}</h2>
										</div>
									{/each}
								</div>
							</div>
						{:else if index===2}
							<div class="flex flex-row items-center justify-center gap-8 py-2">
								{#each skillsDevTools as tool}
									<div class="flex w-fit flex-col items-center justify-center gap-2">
										<img src={tool.src} class="w-[50px]" alt={tool.altText} />
										<h2 class="exo-500 text-lg text-black">{tool.name}</h2>
									</div>
								{/each}
							</div>
						{/if}
					{/each}
				</div>
			</div>
		</div>
	</div>
</div>
