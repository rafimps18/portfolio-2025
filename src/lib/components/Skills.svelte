<script lang="ts">
	import { skillsDevTools, skillsFrameworks, skillsLang } from '$lib';
</script>

<div class="relative h-[900px] md:h-screen w-screen">
	<div
		class="bg-radial-[at_0%_50%] absolute z-20 h-[900px] md:h-screen w-screen animate-pulse from-purple-700 to-black to-40% bg-fixed opacity-40"
	></div>
	<div
		class="bg-radial-[at_100%_50%] absolute z-20 h-[900px] md:h-screen w-screen animate-pulse from-purple-700 to-black to-40% bg-fixed opacity-40"
	></div>
	<div class="absolute z-30">
		<div id="tools" class="flex h-fit w-screen flex-col items-center justify-start pt-12">
			<div class="border-(--blue-secondary) mb-4 border-b-4">
				<h1 class="exo-700 mt-1 text-3xl text-white">My Tools</h1>
			</div>
			<div class="flex h-full w-full flex-row items-center justify-center gap-4 px-12">
				<div
					class="bg-(--white-primary) border-(--blue-primary) min-h-[50vh] w-full border-l-8 px-8 py-2 lg:w-[60%]"
				>
					<div>
						<h1
							class="exo-700 border-(--red-primary) mb-2 border-b-4 text-center text-3xl text-black"
						>
							Languages
						</h1>
						<div class="flex flex-col items-center justify-center gap-4 md:flex-row md:gap-8">
							<div class="flex flex-row items-center justify-center gap-8 py-2">
								{#each skillsLang.slice(0, skillsLang.length / 2) as skill}
									<div class="flex w-fit flex-col items-center justify-center gap-2">
										<img src={skill.src} class="w-[50px]" alt={skill.altText} />
										<h2 class="exo-500 text-lg text-black">{skill.name}</h2>
									</div>
								{/each}
							</div>
							<div class="flex flex-row items-center justify-center gap-8 py-2">
								{#each skillsLang.slice(skillsLang.length / 2, skillsLang.length) as skill}
									<div class="flex w-fit flex-col items-center justify-center gap-2">
										<img src={skill.src} class="w-[50px]" alt={skill.altText} />
										<h2 class="exo-500 text-lg text-black">{skill.name}</h2>
									</div>
								{/each}
							</div>
						</div>
					</div>
					<div>
						<h1
							class="exo-700 border-(--red-primary) mb-2 border-b-4 text-center text-3xl text-black"
						>
							Frameworks
						</h1>
						<div class="flex flex-col items-center justify-center gap-2 py-2 md:flex-row">
							<div class="flex flex-row items-center justify-center gap-8 py-2">
								{#each skillsFrameworks.slice(0, skillsFrameworks.length / 2) as framework}
									<div class="flex w-fit flex-col items-center justify-center gap-2">
										<img src={framework.src} class="w-[50px]" alt={framework.altText} />
										<h2 class="exo-500 text-lg text-black">{framework.name}</h2>
									</div>
								{/each}
							</div>
							<div class="flex flex-row items-center justify-center gap-8 py-2">
								{#each skillsFrameworks.slice(skillsFrameworks.length / 2, skillsFrameworks.length) as framework}
									<div class="flex w-fit flex-col items-center justify-center gap-2">
										<img src={framework.src} class="w-[50px]" alt={framework.altText} />
										<h2 class="exo-500 text-lg text-black">{framework.name}</h2>
									</div>
								{/each}
							</div>
						</div>
					</div>
					<div>
						<h1
							class="exo-700 border-(--red-primary) mb-2 border-b-4 text-center text-3xl text-black"
						>
							Development Tools
						</h1>
						<div class="flex flex-row items-center justify-center gap-8 py-2">
							{#each skillsDevTools as tool}
								<div class="flex w-fit flex-col items-center justify-center gap-2">
									<img src={tool.src} class="w-[50px]" alt={tool.altText} />
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
