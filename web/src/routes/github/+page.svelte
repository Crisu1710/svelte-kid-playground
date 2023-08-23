<div class="container h-full mx-auto flex flex-col justify-center items-center">
	<h1>my github repositories</h1>
	<div class="flex flex-row flex-wrap justify-center">
		{#each repos as repo}
		{#if !repo.fork}
		<div class="card p-4 ml-2 mr-2 mt-4" style="width: 400px;">
			{#if repo.language}
				<p class="text-center uppercase text-cyan-400">{repo.language}</p>
			{:else}
			<br>
			{/if}
			<h3 class="text-center mt-2">{repo.name}</h3>
			<div class="justify-center text-center mt-4 mb-4">
				<a class="btn bg-primary-hover-token border-2 border-cyan-400 text-cyan-400 mr-1" href="{repo.html_url}" target="_blank">
					<IconBrandGithub />
					<p class="uppercase">open</p>
				</a>
				<button use:clipboard="{repo.ssh_url}" class="btn bg-primary-hover-token border-2 border-cyan-400 text-cyan-400 mr-1">
					<IconBrandGit />
					<!-- {copied ? 'Copied 👍' : 'Copy'} -->
					<p class="uppercase">clone</p>
				</button>
				<button class="btn bg-primary-hover-token border-2 border-cyan-400 text-cyan-400">
					<IconStar />
					<p>
						{repo.stargazers_count}
					</p>
				</button>
			</div>
		</div>
		{/if}
		{/each}
	</div>
</div>

<script>
	import { IconBrandGithub, IconBrandGit, IconStar } from '@tabler/icons-svelte';
	import { clipboard } from '@skeletonlabs/skeleton';
	let repos = [];

	async function get_repos() {
		let res = await fetch('https://api.github.com/users/Crisu1710/repos');
		repos = await res.json();
	}

	get_repos();
</script>
