<script lang='ts'>
	import { fade } from 'svelte/transition';
	import { onMount } from 'svelte';
	import { writable } from 'svelte/store';
	import OrbitSc from '/src/components/threlte/OrbitSc.svelte'
	
	let show = writable(true);
	onMount(() => {
		setTimeout(() => {
			show.update(() => false);
		}, 10000);  // Set your delay time here
	});
</script>

{#if $show}
<div class='border-0 h-full w-full flex flex-col justify-center items-center text-center'out:fade={{duration:500}}>
	<span class='text-5xl font-thin m-4' in:fade={{duration: 2000, delay:1000}}>Hi</span>
	<span class='text-5xl font-thin m-4' in:fade={{duration: 2000, delay: 3000}}>Welcome to my website</span>
</div>
{/if}