<script lang="ts">
	import { links } from "$lib";
    import { contacts } from "$lib";
</script>

<div id="contact" class="w-screen h-[30vh] flex flex-row justify-center items-start text-white mt-12 md:px-12">
    <div class="w-[33%] h-fit flex flex-col md:flex-row items-start justify-center gap-2">
        <img src="/logo.png" width="30px" alt="logo" />
        <h1 class="exo-700 text-2xl">Rafael Impas</h1>
    </div>
    <div class="w-[33%] h-fit flex flex-col items-start justify-start gap-2">
        <h1 class="exo-700 text-xl">Navigation</h1>
        {#each links as link}
            <a class="exo-500 hover:text-(--blue-primary) text-base" href={link.link}>{link.name}</a>
        {/each}
    </div>
    <div class="w-[33%] h-fit flex flex-col justify-center items-start gap-2">
        <h1 class="exo-700 textlg">Contact</h1>
        {#each contacts as link}
            <a class="exo-500 hover:text-(--blue-primary) text-base" href={link.link}>
                <div class=" flex flex-row justify-center items-center gap-2">
                    <img src={link.icon} width="30px" alt="logo" />
                    {link.name}
                </div>
            </a>
        {/each}
    </div>
</div>