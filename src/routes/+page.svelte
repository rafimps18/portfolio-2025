<script lang="ts">
	import Footer from '$lib/components/Footer.svelte';
	import { onMount } from 'svelte';
	import AboutMe from '../lib/components/AboutMe.svelte';
	import Hero from '../lib/components/Hero.svelte';
	import Projects from '../lib/components/Projects.svelte';
	import Skills from '../lib/components/Skills.svelte';
	import Contact from '$lib/components/Contact.svelte';

	onMount(() => {
		document.title = 'Rafael Impas';
	});
</script>

<div class="relative h-full w-screen">
	<Hero />
	<AboutMe />
	<Skills />
	<Projects />
	<Contact />
	<Footer />
</div>
