<script lang="ts">
	import { goto } from '$app/navigation';
	import { links } from '$lib';
	let menuOpen = $state(false);

	const openMenu = () => {
		menuOpen = !menuOpen;
	};

	const navigateToSection = (sectionName: string) => {
		menuOpen = false;
		goto(`/${sectionName}`);
	};
</script>

<div class="md:hidden">
	<button onclick={openMenu} class="cursor-pointer p-4 hover:bg-gray-200">
		<img src="icons/menu.svg" class="w-[30px]" alt="menu icon" />
	</button>
	{#if menuOpen}
		<div class="fixed top-[7vh] left-0">
			<div class="flex h-fit w-screen flex-col bg-(--white-primary)">
				{#each links as link}
					<button
						onclick={() => navigateToSection(link.link)}
						class="exo-700 cursor-pointer px-4 py-2 text-center text-base transition duration-75 hover:bg-blue-300 active:bg-blue-400"
					>
						{link.name}
					</button>
				{/each}
			</div>
		</div>
	{/if}
</div>
