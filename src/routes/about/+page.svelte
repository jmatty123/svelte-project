<script lang="ts">

	import { writable } from 'svelte/store';
	import { fade } from 'svelte/transition';
	import { Avatar } from '@skeletonlabs/skeleton';
	import AboutMenu from '/src/components/AboutMenu.svelte';
	import Map from '/src/components/Map.svelte';

	let visibility = writable(true);

	function toggleVisibility() {
		visibility.update(v => !v);
	}

</script>

<div class="flex flex-col justify-center items-center h-full w-full relative overflow-hidden"
transition:fade>

{#if $visibility}

	
<div class="flex flex-col justify-center items-center h-full w-full p-8 space-y-8 relative box-border overflow-hidden"
transition:fade>

	<a href="https://www.linkedin.com/in/jmatty123/" >
		<Avatar
		cursor="cursor-pointer"
		src="https://media.licdn.com/dms/image/D4E03AQF2w8D3R9HUfg/profile-displayphoto-shrink_800_800/0/1684272249639?e=1691020800&v=beta&t=JhaTiP6FfjBy3X3Tkar-q_acBEziyemUMEy1n5P69IQ"
		initials="MY"
		width="w-40"
		class="border-2 border-surface-200-700-token hover:scale-125 duration-100 shadow-lg"
		rounded="rounded-full" 
		/>
	</a>

	<AboutMenu />
	
</div>


{:else}

	<Map />

{/if}

	<button on:click={toggleVisibility} class="absolute bottom-10 btn variant-filled-surface bg-surface-100-800-token text-black font-semibold"
	transition:fade>
		{$visibility ? 'Show Map' : 'Hide Map'}
	</button>

</div>
