<script lang='ts'>
	// The ordering of these imports is critical to your app working properly
	import '@skeletonlabs/skeleton/themes/theme-skeleton.css';
	// If you have source.organizeImports set to true in VSCode, then it will auto change this ordering
	import '@skeletonlabs/skeleton/styles/skeleton.css';
	// Most of your app wide CSS should be put in this file
	import '../app.postcss';
	
	import { AppShell, AppBar, Drawer, drawerStore } from '@skeletonlabs/skeleton';

	import Navigation from '/src/lib/Navigation/Navigation.svelte';

	function drawerOpen(): void {
		drawerStore.open({});
	}

	import { page } from '$app/stores';

	$: classesSidebar = $page.url.pathname === '/' ? 'w-0' : 'w-0 lg:w-64';
</script>

<Drawer>
	<h2 class="p-4">Navigation</h2>
	<hr />
	<Navigation />
</Drawer>

<AppShell slotSidebarLeft="bg-surface-500/5 {classesSidebar}">
	<svelte:fragment slot="pageHeader">
		<AppBar gridColumns="grid-cols-3" slotDefault="place-self-center" slotTrail="place-content-end">
			<svelte:fragment slot="lead">
				<div class="flex items-center">
					<button class="lg:hidden btn btn-sm mr-4" on:click={drawerOpen}>
						<span>
							<svg viewBox="0 0 100 80" class="fill-token w-4 h-4">
								<rect width="100" height="20" />
								<rect y="30" width="100" height="20" />
								<rect y="60" width="100" height="20" />
							</svg>
						</span>
					</button>
					<strong class="text-xl uppercase">matthewyoung.xyz</strong>
				</div>
			</svelte:fragment>
			<svelte:fragment slot="trail"></svelte:fragment>
		</AppBar>
	</svelte:fragment>
	<svelte:fragment slot="sidebarLeft">
		<Navigation />
	</svelte:fragment>

	<slot />

	<svelte:fragment slot="footer">Footer</svelte:fragment>
</AppShell>
