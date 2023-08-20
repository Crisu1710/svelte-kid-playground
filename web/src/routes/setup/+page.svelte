<div class="container h-full mx-auto flex justify-center items-center">
	<div class="text-center flex flex-row items-center">
	{#each devices as device}
		<div class="card p-4 ml-4">{device.name}</div>
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