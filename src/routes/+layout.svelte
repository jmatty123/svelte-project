<script lang='ts'>
	// The ordering of these imports is critical to your app working properly
	import '@skeletonlabs/skeleton/themes/theme-skeleton.css';
	// If you have source.organizeImports set to true in VSCode, then it will auto change this ordering
	import '@skeletonlabs/skeleton/styles/skeleton.css';
	// Most of your app wide CSS should be put in this file
	import '../app.postcss';
	
	import { AppShell, AppBar } from '@skeletonlabs/skeleton';
</script>

<AppShell>
	<svelte:fragment slot="pageHeader">
		<AppBar gridColumns="grid-cols-3" slotDefault="place-self-center" slotTrail="place-content-end">
			<svelte:fragment slot="lead">
				<span class="font-semibold text-xl tracking-tight">matthewyoung.<span style="color: cyan;">x</span><span style="color: yellow;">y</span><span style="color: magenta;">z</span></span>
			</svelte:fragment>
			<svelte:fragment slot="trail">
				<a href="/" class="px-4 text-white hover:text-gray-900">Home</a>
				<a href="/about" class="px-4 text-white hover:text-gray-900">About</a>
				<a href="/services" class="px-4 text-white hover:text-gray-900">Services</a>
				<a href="/contact" class="px-4 text-white hover:text-gray-900">Contact</a>
			</svelte:fragment>
		</AppBar>
	</svelte:fragment>

	<slot />

	<svelte:fragment slot="footer">Footer</svelte:fragment>
</AppShell>
