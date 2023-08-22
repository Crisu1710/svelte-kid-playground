<h1 class="text-center uppercase mt-5">my devices</h1>
<div class="h-full mx-auto mt-5">
	<div class="flex flex-row flex-wrap justify-center">
		{#each devices as device}
		<div class="card p-4 ml-2 mr-2 mt-4" style="width: 400px;">
			{#if device.language}
				<p class="text-center text-cyan-400">{device.language}</p>
			{:else}
			<br>
			{/if}
			<h2 class="text-center">{device.name}</h2>
		</div>
		{/each}
	</div>
</div>

<script>
	let devices = [];

	async function get_devices() {
		let res = await fetch('http://127.0.0.1:8000/devices.json');
		devices = await res.json();
		console.log(devices);
	}

	get_devices();
</script>
