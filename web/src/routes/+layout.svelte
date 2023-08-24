<AppShell slotSidebarRight="bg-surface-500/5 w-56 p-4">
	<svelte:fragment slot="header">
		<!-- App Bar -->
		<AppBar padding="p-0">
			<svelte:fragment slot="lead">
				<!-- <div class="flex items-center">
					<button class="lg:hidden btn btn-sm mr-4">
						<span>
							<svg viewBox="0 0 100 80" class="fill-token w-4 h-4">
								<rect width="100" height="20" />
								<rect y="30" width="100" height="20" />
								<rect y="60" width="100" height="20" />
							</svg>
						</span>
					</button> -->
					<a href="/" class="text-xl uppercase ml-4">robins.run</a>
				<!-- </div> -->
			</svelte:fragment>
			<svelte:fragment slot="trail">
				<NavigationBar />
			</svelte:fragment>
		</AppBar>
	</svelte:fragment>
	<!-- <svelte:fragment slot="sidebarRight">
		<Navigation />	
	</svelte:fragment> -->
	<svelte:fragment slot="pageFooter">
		<AppBar padding="p-2" gridColumns="grid-cols-1" slotDefault="place-self-center">
			<a href="/imprint" class="justify-center items-center">imprint</a>
		</AppBar>
	</svelte:fragment>
	<!-- Page Route Content -->
	<slot />
</AppShell>

<script>
	import '@skeletonlabs/skeleton/themes/theme-skeleton.css';
	import '@skeletonlabs/skeleton/styles/skeleton.css';
	import '../app.postcss';
	//import Navigation from '$lib/Navigation/Navigation.svelte';
	import NavigationBar from '$lib/Navigation/NavigationBar.svelte'
	import { AppShell, AppBar } from '@skeletonlabs/skeleton';

	// initializeStores();
	// const drawerStore = getDrawerStore();

	// function drawerOpen(){
	// 	drawerStore.open({});
	// }
</script>
