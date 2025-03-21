<script lang="ts">
    import { links } from "$lib";
</script>

<header class="z-50 fixed w-screen bg-(--white-primary) flex flex-row justify-between items-center px-6 md:px-8 lg:px-12">
    <a href="/" class="flex flex-row gap-2 justify-start items-center hover:bg-gray-200 active:bg-gray-300 rounded-lg py-1 px-2">
        <img src="/logo.png" class="w-[50px] rounded-2xl" alt="logo"/>
        <h1 class="exo-700 text-black text-xl md:text-2xl lg:text-4xl">Rafael Impas</h1>
    </a>
    <div class="flex flex-row justify-between items-center gap-8">
        {#each links as link}
            <a href={link.link} class="exo-700 text-lg py-2 px-4 transition duration-75 hover:border-b-4 hover:text-(--blue-primary) hover:border-(--blue-primary) text-center">{link.name}</a>
        {/each}
    </div>
    <div class="flex md:hidden justify-center items-center">
        <button>
            <img src="/menu.svg" class="w-[30px]" alt="menu icon"/>
        </button>
    </div>
</header>