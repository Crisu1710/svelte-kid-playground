<script>
	// The ordering of these imports is critical to your app working properly
	import '@skeletonlabs/skeleton/themes/theme-skeleton.css';
	// If you have source.organizeImports set to true in VSCode, then it will auto change this ordering
	import '@skeletonlabs/skeleton/styles/skeleton.css';
	// Most of your app wide CSS should be put in this file
	import '../app.postcss';
	import { AppShell, AppBar, LightSwitch } from '@skeletonlabs/skeleton';
	import { IconHome, IconBrandGithub, IconMicroscope, IconCloudComputing, IconDevicesPc} from '@tabler/icons-svelte';
</script>

<!-- App Shell -->
<AppShell>
	<svelte:fragment slot="header">
		<!-- App Bar -->
		<AppBar padding="p-0">
			<svelte:fragment slot="lead">
				<strong class="text-xl uppercase ml-4">my test 123</strong>
			</svelte:fragment>
			<svelte:fragment slot="trail">
				<div class="mr-4">
					<a class="btn rounded-none bg-primary-hover-token h-16" href="/skills">
						<IconCloudComputing />
						<p class="uppercase">skills</p>
					</a>
					<a class="btn rounded-none bg-primary-hover-token h-16" href="/setup">
						<IconMicroscope/>
						<p class="uppercase">homelab</p>
					</a>
					<a class="btn rounded-none bg-primary-hover-token h-16" href="/setup">
						<IconDevicesPc />
						<p class="uppercase">my settup</p>
					</a>
					<a class="btn rounded-none bg-primary-hover-token h-16" href="/github">
						<IconBrandGithub />
						<p class="uppercase">git repos</p>
					</a>
					<a class="btn rounded-none bg-primary-hover-token h-16" href="/home">
						<IconHome />
						<p class="uppercase">home</p>
					</a>
				</div>
				<!-- <LightSwitch/> -->
			</svelte:fragment>
		</AppBar>
	</svelte:fragment>
	<!-- Page Route Content -->
	<slot />
</AppShell>
