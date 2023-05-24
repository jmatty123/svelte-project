<script lang="ts">
	import { drawerStore } from '@skeletonlabs/skeleton';

	function drawerClose(): void {
		drawerStore.close();
	}

	import { page } from '$app/stores';

	$: routeId = $page.route.id;

</script>

<nav class="list-nav flex justify-center items-center mt-16">
	<!-- Dummy focusable element -->
	<!-- svelte-ignore a11y-no-noninteractive-tabindex -->
	<div tabindex="0" style="position: absolute; top: -9999px;"></div>

	<ul class="">
		<li ><a href="/" class={routeId === '/' ? "btn-sm bg-primary-700" : "btn btn-sm"} on:click={drawerClose}>Homepage</a></li>
		<li ><a href="/about" class={routeId === '/about' ? "btn btn-sm bg-primary-700" : "btn btn-sm"} on:click={drawerClose}>About</a></li>
	</ul>
</nav>