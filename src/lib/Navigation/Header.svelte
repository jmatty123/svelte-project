<script lang='ts'>
    
    import { AppBar, drawerStore } from '@skeletonlabs/skeleton';

    function drawerOpen(): void {
		drawerStore.open({});
	}

</script>

<AppBar padding='p-0' gridColumns="grid-cols-3" slotDefault="place-self-center" slotTrail="place-content-end">
			
    <svelte:fragment slot="lead">
            <!-- Logo Home Button -->
            <a href="/" class="btn border-0 border-red-500 text-xl font-extralight pb-3 hover:scale-105">Matthew Young</a>
    </svelte:fragment>

    <svelte:fragment slot="trail">
        <!-- Mobile Hamburger Button -->
        <div class="flex justify-end items-center w-full h-full">
        <button class="sm:hidden btn hover:scale-125" on:click={drawerOpen}>
            <svg class='w-[14px] h-[14px]' xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512">! Font Awesome Pro 6.4.0 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc.<path fill="currentColor" d="M0 96C0 78.3 14.3 64 32 64H416c17.7 0 32 14.3 32 32s-14.3 32-32 32H32C14.3 128 0 113.7 0 96zM0 256c0-17.7 14.3-32 32-32H416c17.7 0 32 14.3 32 32s-14.3 32-32 32H32c-17.7 0-32-14.3-32-32zM448 416c0 17.7-14.3 32-32 32H32c-17.7 0-32-14.3-32-32s14.3-32 32-32H416c17.7 0 32 14.3 32 32z"/></svg>
            <!-- <svg class='w-[14px] h-[14px]' xmlns="http://www.w3.org/2000/svg" height="1em" viewBox="0 0 320 512">! Font Awesome Free 6.4.0 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc.<path d="M41.4 233.4c-12.5 12.5-12.5 32.8 0 45.3l160 160c12.5 12.5 32.8 12.5 45.3 0s12.5-32.8 0-45.3L109.3 256 246.6 118.6c12.5-12.5 12.5-32.8 0-45.3s-32.8-12.5-45.3 0l-160 160z"/></svg>        </button> -->
            <!-- <p class='font-extralight text-xl'>&lt</p> -->
        </div>
        <!-- Navbar buttons -->
        <div class="hidden sm:flex">
            <a href="/projects" class="btn text-xl font-extralight pb-3 hover:scale-105 duration-100">Projects</a>
            <a href="/about" class="btn text-xl font-extralight pb-3 hover:scale-105 duration-100">About</a>
            <!-- More buttons here -->
        </div>
    </svelte:fragment>

</AppBar>