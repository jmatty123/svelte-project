<script>
	import { fade } from 'svelte/transition';
	let isInitialLoad = !sessionStorage.getItem('isNotFirstLoad');
	if (isInitialLoad) {
		sessionStorage.setItem('isNotFirstLoad', 'true');
	}
</script>

{#if isInitialLoad}
<div class='border-0 h-full w-full flex flex-col justify-center items-center text-center'>
	<span class='text-5xl font-thin m-4' in:fade={{duration: 5000}}>Hi</span>
	<span class='text-5xl font-thin m-4' in:fade={{duration: 5000}}>Welcome to my website</span>
</div>
{:else}
<div class='border-0 h-full w-full flex flex-col justify-center items-center text-center'>
	<span class='text-5xl font-thin m-4'>Hi</span>
	<span class='text-5xl font-thin m-4'>Welcome to my website</span>
</div>
{/if}