<script lang="ts">
	import { LightSwitch, drawerStore } from '@skeletonlabs/skeleton';

	function drawerClose(): void {
		drawerStore.close();
	}

	import { page } from '$app/stores';

	$: routeId = $page.route.id;

</script>

<nav class="h-full flex flex-col items-center justify-between">
	<!-- Dummy focusable element -->
	<!-- svelte-ignore a11y-no-noninteractive-tabindex -->
	<div tabindex="0" style="position: absolute; top: -9999px;"></div>

	<ul class="flex flex-col items-center mt-8 space-y-2">
		<li ><a href="/" class={routeId === '/' ? "btn text-lg font-medium hover:scale-110 duration-100" : "btn text-lg font-thin hover:scale-110 duration-100"} on:click={drawerClose}>Home</a></li>
		<li ><a href="/projects" class={routeId === '/projects' ? "btn text-lg font-medium hover:scale-110 duration-100" : "btn text-lg font-thin hover:scale-110 duration-100"} on:click={drawerClose}>Projects</a></li>
		<li ><a href="/about" class={routeId === '/about' ? "btn text-lg font-medium hover:scale-110 duration-100" : "btn text-lg font-thin hover:scale-110 duration-100"} on:click={drawerClose}>About</a></li>
		<li ><a href="/contact" class={routeId === '/contact' ? "btn text-lg font-medium hover:scale-110 duration-100" : "btn text-lg font-thin hover:scale-110 duration-100"} on:click={drawerClose}>Contact</a></li>
	</ul>
	<div class='flex flex-col items-center pb-8'>
	<LightSwitch class="sm:hidden mb-2"/>
	</div>
</nav>
