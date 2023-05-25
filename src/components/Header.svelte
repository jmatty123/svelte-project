<script lang='ts'>
    
    import { AppBar, drawerStore } from '@skeletonlabs/skeleton';

    function drawerOpen(): void {
		drawerStore.open({});
	}

</script>

<AppBar gridColumns="grid-cols-3" slotDefault="place-self-center" slotTrail="place-content-end">
			
    <svelte:fragment slot="lead">
        <div class="flex justify-center items-center">
            <!-- Logo Home Button -->
            <a href="/" class="flex btn text-xl pt-[5px] font-semibold">matthewyoung.
                <div class="flex">
                    <span class="text-success-500">x</span>
                    <span class="text-warning-500">y</span>
                    <span class="text-error-500">z</span>
                </div>
            </a>

        </div>
    </svelte:fragment>

    <svelte:fragment slot="trail">
        <!-- Mobile Hamburger Button -->
        <button class="lg:hidden btn btn-sm mr-4 pt-[8px]" on:click={drawerOpen}>
            <span>
                <svg viewBox="0 0 100 80" class="fill-token w-4 h-4">
                    <rect width="100" height="20" />
                    <rect y="30" width="100" height="20" />
                    <rect y="60" width="100" height="20" />
                </svg>
            </span>
        </button>
        <!-- Navbar buttons -->
        <div class="hidden lg:flex">
            <a href="/about" class="btn font-semibold">About</a>
            <!-- More buttons here -->
        </div>
    </svelte:fragment>

</AppBar>