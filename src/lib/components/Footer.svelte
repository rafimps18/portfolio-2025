<script lang="ts">
	import { links } from '$lib';
	import { contacts } from '$lib';
</script>

<div class="flex flex-col">
	<div
		class="flex h-fit w-screen flex-col items-start justify-center gap-8 px-4 py-12 text-white md:mt-12 md:h-[30vh] md:flex-row md:gap-0 md:px-12 md:py-0"
	>
		<div
			class="flex h-fit w-full flex-row items-start justify-start gap-2 md:w-[33%] md:justify-center"
		>
			<img src="/logo.png" width="30px" alt="logo" />
			<h1 class="exo-700 text-2xl">Rafael Impas</h1>
		</div>
		<div class="flex h-fit w-[33%] flex-col items-start justify-center gap-2 md:justify-start">
			<h1 class="exo-700 text-xl">Navigation</h1>
			{#each links as link}
				<a class="exo-500 cursor-pointer text-base hover:text-(--blue-primary)" href={link.link}
					>{link.name}</a
				>
			{/each}
		</div>
		<div class="flex h-fit w-full flex-col items-start justify-center gap-2 md:w-[33%]">
			<h1 class="exo-700 text-xl">Contact</h1>
			{#each contacts as link}
				<a
					class="exo-500 cursor-pointer text-base hover:text-(--blue-primary)"
					target="_blank"
					href={link.link}
				>
					<div class=" flex flex-row items-center justify-center gap-2">
						<img src={link.icon} class="w-[25px] md:w-[30px]" alt="logo" />
						{link.name}
					</div>
				</a>
			{/each}
		</div>
	</div>
	<div class="w-[100%] py-4">
		<p class="text-center text-gray-400">Copyright © 2025 Rafael Impas</p>
	</div>
</div>
