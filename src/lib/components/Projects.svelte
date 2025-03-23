<script lang="ts">
	import ProjectCard from "./ProjectCard.svelte";
	import { projectsData } from "$lib";
</script>

<div id="works" class="relative w-screen min-h-screen">
	<div class="absolute inset-0 animate-pulse bg-radial-[at_90%_20%] from-purple-700 to-40% to-black opacity-70"></div>
	<div class="absolute inset-0 animate-pulse bg-radial-[at_0%_40%] from-blue-700 to-40% to-black opacity-40"></div>
	<div class="absolute inset-0 animate-pulse bg-radial-[at_100%_80%] from-blue-700 to-40% to-black opacity-40"></div>
	<div class="relative z-30 w-screen min-h-screen flex flex-col items-center py-12 px-12">
		<div class="border-b-4 border-(--blue-secondary) mb-8">
			<h1 class="exo-700 text-white text-3xl pt-2">My Works</h1>
		</div>
		<div class="w-full flex flex-col items-center gap-8">
			{#each projectsData as project, index}
				<ProjectCard 
					index={index + 1} 
					headerText={project.name} 
					altText={project.altText} 
					imageUrl={project.imageUrl} 
					description={project.description} 
				/>
			{/each}
		</div>
	</div>
</div>
