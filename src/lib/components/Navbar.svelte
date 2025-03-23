<script lang="ts">
    import { links } from "$lib";
	import MobileMenu from "./MobileMenu.svelte";
</script>

<header class="z-50 fixed w-screen bg-(--white-primary) flex flex-row justify-between items-center px-2 md:px-8">
    <a href="/" class="flex flex-row gap-2 justify-start items-center hover:bg-gray-200 active:bg-gray-300 rounded-lg py-1 px-2">
        <img src="/logo.png" class="w-[50px] rounded-2xl" alt="logo"/>
        <h1 class="exo-700 text-black text-xl md:text-2xl lg:text-4xl">Rafael Impas</h1>
    </a>
    <div class="hidden md:flex flex-row justify-between items-center gap-8">
        {#each links as link}
            <a href={link.link} class="exo-700 md:text-sm lg:text-base py-2 px-4 transition duration-75 hover:border-b-4 hover:text-(--blue-primary) hover:border-(--blue-primary) text-center">{link.name}</a>
        {/each}
    </div>
    <MobileMenu />
</header>