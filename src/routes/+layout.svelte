<script lang="ts">
	import '../app.css';
	import Navbar from '../lib/components/Navbar.svelte';
	let { children } = $props();
</script>

<svelte:head>
  <title>Rafael Impas - Developer</title>
  <meta name="description" content="Web developer specializing in modern, responsive websites." />
  <meta name="keywords" content="web development, SvelteKit, JavaScript" />
  <meta property="og:title" content="Rafael Impas - Developer" />
  <meta property="og:url" content="https://rafael-impas.vercel.app/" />
  <meta property="og:image" content="https://rafael-impas.vercel.app/preview-image.png" />
</svelte:head>

<div class="h-full">
	<Navbar />
	{@render children()}
</div>
