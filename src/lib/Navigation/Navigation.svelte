<script lang="ts">
	import { LightSwitch, drawerStore } from '@skeletonlabs/skeleton';

	function drawerClose(): void {
		drawerStore.close();
	}

	import { page } from '$app/stores';

	$: routeId = $page.route.id;

</script>

<nav class="list-nav flex flex-col justify-center items-center mt-16">
	<!-- Dummy focusable element -->
	<!-- svelte-ignore a11y-no-noninteractive-tabindex -->
	<div tabindex="0" style="position: absolute; top: -9999px;"></div>

	<ul class="flex flex-col items-center">
		<li ><a href="/" class={routeId === '/' ? "btn-sm bg-primary-700" : "btn btn-sm"} on:click={drawerClose}>Home</a></li>
		<li ><a href="/projects" class={routeId === '/projects' ? "btn btn-sm bg-primary-700" : "btn btn-sm"} on:click={drawerClose}>Projects</a></li>
		<li ><a href="/about" class={routeId === '/about' ? "btn btn-sm bg-primary-700" : "btn btn-sm"} on:click={drawerClose}>About</a></li>
	</ul>
	<LightSwitch class="mt-8 md:hidden"/>
</nav>
