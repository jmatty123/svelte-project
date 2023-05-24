<script lang="ts">
	import { drawerStore } from '@skeletonlabs/skeleton';

	function drawerClose(): void {
		drawerStore.close();
	}

import { page } from '$app/stores';

$: routeId = $page.route.id;

</script>

<nav class="list-nav pt-10 flex items-center justify-center">
	<ul class="flex flex-col items-center">
		<li ><a href="/" class={routeId === '/' ? "btn btn-sm bg-primary-500 text-center" : "btn btn-sm text-center"} on:click={drawerClose}>Homepage</a></li>
		<li ><a href="/about" class={routeId === '/about' ? "btn btn-sm bg-primary-500 text-center" : "btn btn-sm text-center"} on:click={drawerClose}>About</a></li>
	</ul>
</nav>