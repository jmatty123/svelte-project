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
		<li ><a href="/" class={routeId === '/' ? "btn font-semibold bg-surface-200-700-token" : "btn hover:bg-surface-200-700-token"} on:click={drawerClose}>Home</a></li>
		<li ><a href="/projects" class={routeId === '/projects' ? "btn font-semibold bg-surface-200-700-token " : "btn hover:bg-surface-200-700-token"} on:click={drawerClose}>Projects</a></li>
		<li ><a href="/about" class={routeId === '/about' ? "btn font-semibold bg-surface-200-700-token" : "btn hover:bg-surface-200-700-token"} on:click={drawerClose}>About</a></li>
	</ul>
	<div class="w-full h-full flex justify-center items-end">
		<div class="dark:hidden sm:hidden flex text-2xl">
			🦢
		</div>
	</div>
	<div class='flex flex-col items-center pb-4'>
	<LightSwitch class="md:hidden mb-4"/>
	<p class="text-center font-mono text-[10px] ">
		Creation: 5/16/23 | Latest update: 5/26/23</p>
	</div>
</nav>
