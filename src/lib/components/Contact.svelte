<script lang="ts">
	import { fade, fly } from 'svelte/transition';

	let copied: boolean = $state(false);
	const email: string = 'impasrafael@gmail.com';
	function copyEmail() {
		navigator.clipboard.writeText(email);
		copied = true;
		setTimeout(() => {
			copied = false;
		}, 2000);
	}
</script>

<section id="contact">
	<div class="relative min-h-screen w-screen">
		<div
			class="absolute inset-0 animate-pulse bg-radial-[at_50%_100%] from-white to-black to-60% opacity-60"
		></div>
		<div class="absolute h-full w-screen">
			<div class="flex h-screen flex-col items-center justify-center px-12 py-12">
				<div class="border-b-4 border-(--blue-primary)">
					<h1 class="exo-700 mt-1 text-5xl text-white">Contact Me</h1>
				</div>
				<div class="w-[full] py-8 md:w-[75%] lg:w-[50vw]">
					<p class="exo-500 text-center text-lg text-white">
						Got a project in mind or just want to say hi? Feel free to reach out! Whether it's a
						collaboration, a question, or just a chat about web development, I'm always open to new
						connections.
					</p>
					<div class="flex flex-row items-center justify-center gap-2 pt-2">
						<img src="icons/mail-white.svg" alt="mail icon" class="w-[40px]" />
						<p id="email" class="exo-400 text-xl text-white">
							{email}
						</p>
						<button
							onclick={copyEmail}
							class="ml-2 cursor-pointer rounded-lg bg-(--white-primary) p-1 hover:bg-gray-300 active:bg-gray-400 md:p-3"
						>
							<img src="icons/copy.svg" width="20rem" alt="copy icon" />
						</button>
					</div>
					<div class="min-h-[2rem]">
						{#if copied}
							<p
								in:fly={{ y: -10, duration: 500 }}
								out:fade={{ duration: 500 }}
								class="exo-400 text-center text-xl text-white"
							>
								Copied!
							</p>
						{/if}
					</div>
				</div>
			</div>
		</div>
	</div>
</section>
