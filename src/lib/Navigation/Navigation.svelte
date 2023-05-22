<script lang="ts">
	import { drawerStore } from '@skeletonlabs/skeleton';

	function drawerClose(): void {
		drawerStore.close();
	}
</script>
<nav class="list-nav pt-4 flex items-center justify-center">
	<ul class="flex flex-col items-center">
		<li ><a href="/" class="text-center" on:click={drawerClose}>Homepage</a></li>
		<li ><a href="/about" class="text-center" on:click={drawerClose}>About</a></li>
	</ul>
</nav>