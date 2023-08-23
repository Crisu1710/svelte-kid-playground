<div class="container h-full mx-auto flex flex-col justify-center items-center">
	<h1>my devices</h1>
	<div class="flex flex-row flex-wrap justify-center">
		{#each devices as device}
		<div class="card p-6 ml-2 mr-2 mt-2 mb-2" style="width: 400px;">			
			<h1 class="text-center mb-4 text-cyan-400">{device.name}</h1>
			<div class="grid-rows-1 flex flex-row">
				<IconDisc />
				<p class="ml-2">{device.os}</p>
			</div>
			<div class="grid-rows-1 flex flex-row">
				<IconCpu />
				<p class="ml-2">{device.cpu}</p>
			</div>
			<div class="grid-rows-1 flex flex-row">
				<IconPhoto />
				<p class="ml-2">{device.gpu}</p>
			</div>
			<div class="grid-rows-1 flex flex-row">
				<IconCpu2 />
				<p class="ml-2">{device.ram}</p>
			</div>
			<div class="grid-rows-1 flex flex-row">
				<IconLayoutDashboard />
				<p class="ml-2">{device.mb}</p>
			</div>
			<div class="grid-rows-1 flex flex-row">
				<IconPlug />
				<p class="ml-2">{device.psu}</p>
			</div>
			<div class="grid-rows-1 flex flex-row">
				<IconDeviceFloppy />
				<p class="ml-2">{device.disk}</p>
			</div>
		</div>
		{/each}
	</div>
</div>

<script>
	let devices = [];
	import {IconDisc, IconCpu, IconPhoto, IconDeviceFloppy, IconPlug, IconCpu2, IconLayoutDashboard} from '@tabler/icons-svelte'

	async function get_devices() {
		let res = await fetch('https://raw.githubusercontent.com/Crisu1710/svelte-kit-playground/main/data/devices.json');
		devices = await res.json();
	}

	get_devices();
</script>
