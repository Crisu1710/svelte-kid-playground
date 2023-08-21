<h1 class="text-center uppercase mt-5">My Technical skills</h1>
<div class="container h-full mx-auto flex justify-center items-center">
	<div class="flex flex-col items-center" style="width: 100%;">
	{#each skills as skill}
		<div class="card p-8 mt-4" style="width: 90%;">
			<div class="flex flex-row">
				<div class="text-left" style="width: 100%;">
					<h1 class="text-cyan-400 mb-6">{skill.name}</h1>
					<p>{skill.text}</p>
				</div>
				<p style="display:inline-block; width: 100%;"></p>
				<div class="flex flex-row items-center">
					<a class="btn bg-primary-hover-token border-2 border-cyan-400 text-cyan-400 h-14 mr-4" href="{skill.gitlink}">
						<IconBrandGithub />
						<p class="uppercase">open</p>
					</a>
					<ProgressRadial class="fill-cyan-400" meter="stroke-cyan-400" track="stroke-cyan-400/30" fill font=150 width="w-14" value={skill.level}>{skill.level}%</ProgressRadial>
				</div>
			</div>
		</div>
	{/each}
	</div>
</div>

<script>
	import { IconBrandGithub } from '@tabler/icons-svelte';
	import { ProgressRadial } from "@skeletonlabs/skeleton";
	let skills = [];

	async function get_skills() {
		let res = await fetch('http://127.0.0.1:8000/skills.json');
		skills = await res.json();
		console.log(skills);
	}

	get_skills();
</script>
