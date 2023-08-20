<div class="container h-full mx-auto flex justify-center items-center">
	<div class="text-center flex flex-col items-center">
		<Avatar src="{user.avatar_url}" width="w-40" rounded="rounded-full"/>
		<div>
			<h1 class="mb-3 mt-3">
				{user.name} @{user.login}
			</h1>
			<h1>
			{#each links as link}
			    <a class="btn" href="{link.link}" target="_blank" ><svelte:component this="{allIcons[link.tabler]}" color="{link.color}"/></a>
			{/each}
			</h1>
			<h3 class="subheading font-weight-regular mt-5">
				{user.bio}
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
		//let res = await fetch('https://raw.githubusercontent.com/Crisu1710/crisu-web-2.0/main/data/icons.json');
		let res = await fetch('http://127.0.0.1:8000/icons.json');
		links = await res.json();
		console.log(links);
	}

	get_user();
	get_links();
</script>