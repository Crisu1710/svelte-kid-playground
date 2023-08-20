<div class="container h-full mx-auto flex justify-center items-center">
	<div class="text-center flex flex-row items-center">
	{#each skills as skill}
		<div class="card p-4 ml-4">{skill.name}</div>
	{/each}
	</div>
</div>

<script>
	let skills = [];

	async function get_skills() {
		let res = await fetch('http://127.0.0.1:8000/skills.json');
		skills = await res.json();
		console.log(skills);
	}

	get_skills();
</script>