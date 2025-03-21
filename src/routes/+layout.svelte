<script lang="ts">
	import '../app.css';
	import Navbar from '../lib/components/Navbar.svelte';
	let { children } = $props();
</script>

<div class="h-full w-screen">
	<Navbar />
	{@render children()}
</div>
