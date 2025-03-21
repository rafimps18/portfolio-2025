<script lang="ts">
	import ProjectCard from "./ProjectCard.svelte";
    import { projectsData } from "$lib";
</script>

<div class="relative w-screen h-[2300px]">
	<div class="absolute z-20 w-screen h-[2300px] animate-pulse bg-radial-[at_90%_20%] from-purple-700 to-40% to-black opacity-40"></div>
	<div class="absolute z-20 w-screen h-[2300px] animate-pulse bg-radial-[at_0%_40%] from-blue-700 to-40% to-black opacity-40"></div>
	<div class="absolute z-20 w-screen h-[2300px] animate-pulse bg-radial-[at_100%_80%] from-blue-700 to-40% to-black opacity-40"></div>
    <div class="absolute z-30 w-screen h-full">
        <div id="works" class="w-screen h-fit flex flex-col justify-between items-center py-12 px-12">
            <div class="border-b-4 border-(--blue-secondary) mb-8">
                <h1 class="exo-700 text-white text-3xl">My Projects</h1>
            </div>
            <div class="w-full h-full flex flex-col justify-center items-center gap-8">
                {#each projectsData as project}
                    <ProjectCard headerText={project.name} altText={project.altText} imageUrl={project.imageUrl} description={project.description} />
                {/each}
            </div>
        </div>
    </div>
</div>