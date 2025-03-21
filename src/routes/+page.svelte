<script lang="ts">
	import Footer from "$lib/components/Footer.svelte";
	import { onMount } from "svelte";
    import AboutMe from "../lib/components/AboutMe.svelte";
    import Hero from "../lib/components/Hero.svelte";
	import Projects from "../lib/components/Projects.svelte";
	import Skills from "../lib/components/Skills.svelte";


    onMount(() => {
        document.title = "Rafael Impas";
    })
</script>

<div class="relative w-screen h-full">
    <div class="absolute z-30 w-screen h-screen animate-pulse bg-radial from-sky-700 to-70% to-black bg-fixed opacity-20"></div>
    <div class="absolute z-20 w-screen h-screen animate-pulse bg-radial-[at_80%_40%] from-purple-700 to-40% to-black bg-fixed opacity-40"></div>
    <div class="absolute z-10 w-screen h-screen animate-pulse bg-radial-[at_20%_80%] from-purple-700 to-40% to-black bg-fixed opacity-40"></div>
    <div class="absolute z-40 overflow-x-hidden">
        <Hero/>
        <AboutMe/>
        <Skills/>
        <Projects />
        <Footer />
    </div>
</div>