<script lang="ts">
	import { onDestroy, onMount } from "svelte";

    let name: Element;
    let nameVisible: boolean = $state(false);
    let observer: IntersectionObserver;

    onMount(()=>{
        observer = new IntersectionObserver(
            ([entry]) => { nameVisible = entry.isIntersecting}
        );

        observer.observe(name);
    });

    onDestroy(()=>{
        if (observer) observer.disconnect();
    })
</script>

<div class="relative w-screen min-h-screen">
    <div class="absolute z-30 inset-0 animate-pulse bg-radial from-sky-700 to-70% to-black bg-fixed opacity-20"></div>
    <div class="absolute z-20 inset-0 animate-pulse bg-radial-[at_80%_40%] from-purple-700 to-40% to-black bg-fixed opacity-40"></div>
    <div class="absolute z-10 inset-0 animate-pulse bg-radial-[at_20%_80%] from-purple-700 to-40% to-black bg-fixed opacity-40"></div>
    <div class="absolute z-40 w-screen">
        <div class="w-full z-40 h-screen pt-[8vh] flex flex-col gap-4 justify-center items-center">
            <h1 bind:this={name} class="{nameVisible ? 'visibleY' : ''} fadeFromBottom exo-700 text-white text-6xl md:text-7xl">Rafael Impas</h1>
            <h1 bind:this={name} class="{nameVisible ? 'visibleY' : ''} fadeFromTop exo-500 text-white text-4xl">Developer</h1>
        </div>
    </div>
</div>
