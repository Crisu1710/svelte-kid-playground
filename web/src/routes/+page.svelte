<div class="container h-full mx-auto flex justify-center items-center">
	<div class="text-center flex flex-col items-center">
		<Avatar src="{user.avatar_url}" width="w-40" rounded="rounded-full"/>
		<div>
			<h2 class="mb-3 mt-3">
				{user.name} @{user.login}
			</h2>
			<h1>
			{#each links as link}
			    <a class="btn" href="{link.link}" target="_blank" ><svelte:component this="{allIcons[link.tabler]}" color="{link.color}"/></a>
			{/each}
			</h1>
			<h3 class="subheading font-weight-regular mt-5">
				{user.bio} @{user.company}
			</h3>
		</div>
	</div>
</div>

<script>
	import {Avatar} from '@skeletonlabs/skeleton';
	import * as allIcons from '@tabler/icons-svelte';

	let user = [];
	let links = [];

	async function get_user() {
		let res = await fetch('https://api.github.com/users/Crisu1710');
		user = await res.json();
	}

	async function get_links() {
		let res = await fetch('https://raw.githubusercontent.com/Crisu1710/svelte-kit-playground/main/data/icons.json');
		links = await res.json();
	}

	get_user();
	get_links();
</script>
