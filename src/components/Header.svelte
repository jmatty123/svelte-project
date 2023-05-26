<script lang='ts'>
    
    import { AppBar, drawerStore } from '@skeletonlabs/skeleton';

    function drawerOpen(): void {
		drawerStore.open({});
	}

</script>

<AppBar gridColumns="grid-cols-3" slotDefault="place-self-center" slotTrail="place-content-end">
			
    <svelte:fragment slot="lead">
            <!-- Logo Home Button -->
            <a href="/" class="btn text-xl font-semibold pb-3">Matthew Young</a>
    </svelte:fragment>

    <svelte:fragment slot="trail">
        <!-- Mobile Hamburger Button -->
        <button class="sm:hidden btn" on:click={drawerOpen}>
            <span>
                <svg class='w-[18px] h-[18px]' xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512"><!--! Font Awesome Pro 6.4.0 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. --><path fill="currentColor" d="M0 96C0 78.3 14.3 64 32 64H416c17.7 0 32 14.3 32 32s-14.3 32-32 32H32C14.3 128 0 113.7 0 96zM0 256c0-17.7 14.3-32 32-32H416c17.7 0 32 14.3 32 32s-14.3 32-32 32H32c-17.7 0-32-14.3-32-32zM448 416c0 17.7-14.3 32-32 32H32c-17.7 0-32-14.3-32-32s14.3-32 32-32H416c17.7 0 32 14.3 32 32z"/></svg>
            </span>
        </button>
        <!-- Navbar buttons -->
        <div class="hidden sm:flex">
            <a href="/projects" class="btn font-semibold">Projects</a>
            <a href="/about" class="btn font-semibold">About</a>
            <!-- More buttons here -->
        </div>
    </svelte:fragment>

</AppBar>