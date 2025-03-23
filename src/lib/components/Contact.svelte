<script lang="ts">
	import { fade, fly } from "svelte/transition";

    let copied: boolean = $state(false);
    const email: string = "impasrafael@gmail.com";
    function copyEmail() {
        navigator.clipboard.writeText(email);
        copied = true;
        setTimeout(() => {
            copied = false;
        }, 2000)
    }
</script>

<div id="contact" class="relative w-screen min-h-screen">
    <div class="absolute inset-0 bg-radial-[at_50%_100%] from-white to-60% to-black opacity-60 animate-pulse"></div>
    <div class="absolute w-screen h-full">
        <div class="flex flex-col h-screen justify-center items-center py-12 px-12">
            <div class="border-b-4 border-(--blue-secondary)">
                <h1 class="exo-700 text-white text-5xl mt-1">Contact Me</h1>
            </div>
            <div class="w-[full] md:w-[75%] lg:w-[50vw] py-8">
                <p class="exo-500 text-white text-lg text-center">Got a project in mind or just want to say hi? Feel free to reach out! Whether it's a collaboration, a question, or just a chat about web development, I'm always open to new connections.</p>
                <div class="flex flex-row gap-2 justify-center items-center pt-2">
                    <img src="mail-white.svg" alt="mail icon" class="w-[40px]" />
                    <p id="email" class="exo-400 text-xl text-white">
                        {email}
                    </p>
                    <button onclick={copyEmail} class="p-3 bg-(--white-primary) hover:bg-gray-300 active:bg-gray-400 rounded-lg cursor-pointer ml-2">
                        <img src="copy.svg" width="20rem" alt="copy icon"/>
                    </button>
                </div>
                <div class="min-h-[2rem]"> 
                    {#if copied}
                        <p in:fly={{y:-10, duration:500}} out:fade={{duration:500}} class="exo-400 text-xl text-white text-center">
                            Copied!
                        </p>
                    {/if}
                </div>
            </div>
        </div>
    </div>
</div>
