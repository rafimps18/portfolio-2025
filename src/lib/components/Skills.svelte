<script lang="ts">
	import { skillsDevTools, skillsFrameworks, skillsLang } from "$lib";

	console.log(skillsLang.length);

	const skillListLength = skillsLang.length;
	const skillListFirstHalf = skillsLang.slice(0, skillListLength/2);
	const skillListLastHalf = skillsLang.slice(skillListLength/2, skillListLength);
</script>

<div class="relative h-screen w-screen">
	<div class="absolute z-20 w-screen h-screen animate-pulse bg-radial-[at_0%_50%] from-purple-700 to-40% to-black bg-fixed opacity-40"></div>
	<div class="absolute z-20 w-screen h-screen animate-pulse bg-radial-[at_100%_50%] from-purple-700 to-40% to-black bg-fixed opacity-40"></div>
	<div class="absolute z-30">
		<div id="tools" class="flex h-fit w-screen flex-col items-center justify-start pt-12">
			<div class="mb-4 border-b-4 border-(--blue-secondary)">
				<h1 class="exo-700 text-3xl text-white mt-1">My Tools</h1>
			</div>
			<div class="flex h-full w-full flex-row items-center justify-center gap-4 px-12">
				<div class="min-h-[50vh] w-full lg:w-[60%] bg-(--white-primary) px-8 py-2 border-l-8 border-(--blue-primary)">
					<div>
						<h1 class="exo-700 border-b-4 border-(--red-primary) mb-2 text-center text-3xl text-black">
							Languages
						</h1>
						<div class="flex flex-col gap-4 md:gap-8 md:flex-row justify-center items-center">
							<div class="flex flex-row items-center justify-center gap-8 py-2">
								{#each skillListFirstHalf as skill}
									<div class="flex w-fit flex-col items-center justify-center gap-2">
										<img src={skill.src} class="w-[50px]" alt={skill.altText} />
										<h2 class="exo-500 text-lg text-black">{skill.name}</h2>
									</div>
								{/each}
							</div>
							<div class="flex flex-row items-center justify-center gap-8 py-2">
								{#each skillListLastHalf as skill}
									<div class="flex w-fit flex-col items-center justify-center gap-2">
										<img src={skill.src} class="w-[50px]" alt={skill.altText} />
										<h2 class="exo-500 text-lg text-black">{skill.name}</h2>
									</div>
								{/each}
							</div>
						</div>
					</div>
					<div>
						<h1 class="exo-700 border-b-4 border-(--red-primary) mb-2 text-center text-3xl text-black">
							Frameworks
						</h1>
						<div class="flex flex-row items-center justify-center gap-8 py-2">
							{#each skillsFrameworks as framework}
								<div class="flex w-fit flex-col items-center justify-center gap-2">
									<img src={framework.src} class="w-[50px]" alt={framework.altText} />
									<h2 class="exo-500 text-lg text-black">{framework.name}</h2>
								</div>
							{/each}
						</div>
					</div>
					<div>
						<h1 class="exo-700 border-b-4 border-(--red-primary) mb-2 text-center text-3xl text-black">
							Development Tools
						</h1>
						<div class="flex flex-row items-center justify-center gap-8 py-2">
							{#each skillsDevTools as tool}
								<div class="flex w-fit flex-col items-center justify-center gap-2">
									<img src={tool.src} class="w-[50px]" alt={tool.altText}/>
									<h2 class="exo-500 text-lg text-black">{tool.name}</h2>
								</div>
							{/each}
						</div>
					</div>
				</div>
			</div>
		</div>
	</div>
</div>

