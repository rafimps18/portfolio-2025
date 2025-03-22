<script lang="ts">
	import { onMount } from "svelte";

    let name: any;
    let nameVisible: boolean = $state(false);

    onMount(()=>{
        const observer = new IntersectionObserver(
            ([entry]) => { nameVisible = entry.isIntersecting}
        );

        observer.observe(name);
    });
</script>

<div class="w-full h-screen pt-[8vh] flex flex-col gap-4 justify-center items-center">
    <h1 bind:this={name} class="{nameVisible ? 'visible' : ''} fadeFromBottom exo-700 text-white text-6xl md:text-7xl">Rafael Impas</h1>
    <h1 bind:this={name} class="{nameVisible ? 'visible' : ''} fadeFromBottom exo-500 text-white text-4xl">Developer</h1>
</div>