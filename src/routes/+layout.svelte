<script lang='ts'>
	// The ordering of these imports is critical to your app working properly
	import '../theme.postcss';
	// If you have source.organizeImports set to true in VSCode, then it will auto change this ordering
	import '@skeletonlabs/skeleton/styles/skeleton.css';
	// Most of your app wide CSS should be put in this file
	import '../app.postcss';
	
	import { AppShell, Drawer } from '@skeletonlabs/skeleton';

	import Navigation from '/src/lib/Navigation/Navigation.svelte';
	
	import Header from '/src/components/Header.svelte';

	import Footer from '/src/components/Footer.svelte';

</script>

<AppShell class="flex flex-col" slotFooter='z-10' slotSidebarRight="w-0">
	<svelte:fragment slot="header">
		<Header />
	</svelte:fragment>

	<svelte:fragment slot="sidebarRight">
		<Drawer position="right">
			<Navigation />
		</Drawer>
	</svelte:fragment>
	
		<slot />

	<svelte:fragment slot="footer">	
		<Footer />
	</svelte:fragment>
	
</AppShell>
