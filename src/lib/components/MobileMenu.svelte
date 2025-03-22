<script lang='ts'>
    import { goto } from "$app/navigation";
    import { links } from "$lib";
    let menuOpen = $state(false);

    const openMenu = () => {
        menuOpen=!menuOpen;
    }

    const navigateToSection = (sectionName: string) => {
        menuOpen = false;
        goto(`/${sectionName}`);
    }
</script>

<div class="relative md:hidden">
    <button onclick={openMenu} class="hover:bg-gray-200 p-4 cursor-pointer">
        <img src="/menu.svg" class="w-[30px]" alt="menu icon"/>
    </button>
    {#if menuOpen}
    <div class="absolute top-15 -left-105">
        <div class="w-screen h-fit bg-(--white-primary) flex flex-col">
            {#each links as link}
            <button onclick={() => navigateToSection(link.link)} class="exo-700 text-base py-2 px-4 transition duration-75 active:bg-blue-400 text-center cursor-pointer">
                {link.name}
            </button>
            {/each}
        </div>
    </div>
    {/if}
</div>