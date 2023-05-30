<script lang='ts'>
    import Map from '/src/components/Map.svelte';
</script>

<div class='box-border m-8 w-auto h-auto grid grid-cols-1 sm:grid-cols-2 xl:grid-cols-3 gap-8'>
    <a href="/" class="card project-card bg-surface-100-800-token shadow-md hover:scale-105">
        <div class="content">
            <Map />
            <div class='relative w-full py-2 flex flex-col justify-center items-center bg-surface-200-700-token opacity-75'>
            <p class="relative text-4xl">Personal Website</p>
            <p class="font-normal relative text-2xl mb-1">5/16/23</p>
            </div>
        </div>
    </a>
    <a href="/" class="card project-card bg-surface-100-800-token shadow-md hover:scale-105">
        <div class="content">
            <div class='relative w-full py-2 flex flex-col justify-center items-center opacity-75'>
                <p class="relative text-4xl">2</p>
                <p class="font-normal relative text-2xl mb-1">Coming soon!</p>
            </div>
        </div>
    </a>
    <a href="/" class="card project-card bg-surface-100-800-token shadow-md hover:scale-105">
        <div class="content">
            <div class='relative w-full py-2 flex flex-col justify-center items-center opacity-75'>
                <p class="relative text-4xl">3</p>
                <p class="font-normal relative text-2xl mb-1">Coming soon!</p>
            </div>
        </div>
    </a>
</div>
