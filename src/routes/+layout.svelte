<script lang='ts'>
	// The ordering of these imports is critical to your app working properly
	import '../theme.postcss';
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
	$: classesSidebar = 'w-0';

</script>

<AppShell slotSidebarRight="bg-surface-500/5 {classesSidebar}">
	<svelte:fragment slot="pageHeader">
		<AppBar gridColumns="grid-cols-3" slotDefault="place-self-center" slotTrail="place-content-end">
			<svelte:fragment slot="lead">
				<div class="flex items-center">
					<!-- Mobile Hamburger Button -->
					<!-- Logo Home Button -->
					<a href="/" class="flex btn text-xl font-semibold tracking-tight">matthewyoung.
						<div class="flex">
							<span style="color: cyan;">x</span>
							<span style="color: yellow;">y</span>
							<span style="color: magenta;">z</span>
						</div>
					</a>
				</div>
			</svelte:fragment>
			<svelte:fragment slot="trail">
				<button class="lg:hidden btn btn-sm mr-4" on:click={drawerOpen}>
					<span>
						<svg viewBox="0 0 100 80" class="fill-token w-4 h-4">
							<rect width="100" height="20" />
							<rect y="30" width="100" height="20" />
							<rect y="60" width="100" height="20" />
						</svg>
					</span>
				</button>
				<!-- Navbar buttons -->
				<div class="hidden lg:flex">
					<a href="/about" class="btn font-semibold text-primary-500">About</a>
					<!-- More buttons here -->
				</div>
			</svelte:fragment>
		</AppBar>
	</svelte:fragment>
	<svelte:fragment slot="sidebarRight">
		<Drawer position="right">
			<h2 class="p-4 text-center">Menu</h2>
			<hr />
			<Navigation />
		</Drawer>
	</svelte:fragment>

	<slot />

	<svelte:fragment slot="pageFooter">
		
		<AppBar gridColumns="grid-cols-1" slotDefault="place-self-center" slotTrail="place-content-end">
			<svelte:fragment slot="lead"></svelte:fragment>
			<p class="text-center font-mono text-xs text-white p-2">
				Creation: 5/16/23 | Latest update: 5/21/23 "Add: sidebar/navbar/about/footer"
			</p>
			<svelte:fragment slot="trail"></svelte:fragment>
		</AppBar>

	</svelte:fragment>
	
</AppShell>
