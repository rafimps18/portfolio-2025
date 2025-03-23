<script lang="ts">
	import { links } from "$lib";
    import { contacts } from "$lib";
</script>

<div class="w-screen h-fit md:h-[30vh] flex flex-col md:flex-row justify-center items-start text-white gap-8 md:gap-0 py-8 md:py-0 md:mt-12 px-4 md:px-12">
    <div class="w-full md:w-[33%] h-fit flex flex-row items-start justify-start gap-2">
        <img src="/logo.png" width="30px" alt="logo" />
        <h1 class="exo-700 text-2xl">Rafael Impas</h1>
    </div>
    <div class="w-[33%] h-fit flex flex-col items-start justify-center md:justify-start gap-2">
        <h1 class="exo-700 text-xl">Navigation</h1>
        {#each links as link}
            <a class="exo-500 hover:text-(--blue-primary) text-base cursor-pointer" href={link.link}>{link.name}</a>
        {/each}
    </div>
    <div class="w-full md:w-[33%] h-fit flex flex-col justify-center items-start gap-2">
        <h1 class="exo-700 text-xl">Contact</h1>
        {#each contacts as link}
            <a class="exo-500 hover:text-(--blue-primary) text-base cursor-pointer" href={link.link}>
                <div class=" flex flex-row justify-center items-center gap-2">
                    <img src={link.icon} class="w-[25px] md:w-[30px]" alt="logo" />
                    {link.name}
                </div>
            </a>
        {/each}
    </div>
</div>