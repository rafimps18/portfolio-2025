<script lang="ts">
	import ProjectCard from './ProjectCard.svelte';
	import { projectsData } from '$lib';
</script>

<section id="works">
	<div class="relative min-h-screen w-screen">
		<div
			class="absolute inset-0 animate-pulse bg-radial-[at_90%_20%] from-purple-700 to-black to-40% opacity-70"
		></div>
		<div
			class="absolute inset-0 animate-pulse bg-radial-[at_0%_40%] from-blue-700 to-black to-40% opacity-40"
		></div>
		<div
			class="absolute inset-0 animate-pulse bg-radial-[at_100%_80%] from-blue-700 to-black to-40% opacity-40"
		></div>
		<div class="relative z-30 flex min-h-screen w-screen flex-col items-center px-4 py-12 md:px-12">
			<div class="mb-8 border-b-4 border-(--blue-primary)">
				<h1 class="exo-700 pt-2 text-3xl text-white">My Works</h1>
			</div>
			<div class="flex w-full flex-col items-center gap-8">
				{#each projectsData as project, index}
					<ProjectCard
						index={index + 1}
						headerText={project.name}
						altText={project.altText}
						imageUrl={project.imageUrl}
						description={project.description}
						link={project.link}
						github={project.github}
						techStack={project.techStack}
					/>
				{/each}
			</div>
		</div>
	</div>
</section>
