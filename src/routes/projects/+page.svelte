<script lang='ts'>
    import Map from '/src/components/Map.svelte';
</script>

<div class='box-border m-10 2xl:mx-auto w-auto h-auto grid grid-cols-1 sm:grid-cols-2 xl:grid-cols-3 gap-10 max-w-screen-2xl'>
    <a href="/projects/personal-website" class="card project-card bg-surface-100-800-token shadow-md hover:scale-105">  
        <div class="content">
            <div class="m-auto h-full w-full overflow-hidden pointer-events-none">
                <Map />
            </div>
            <div class='description bg-surface-200-700-token'>
            <p class="text-lg">Personal Website</p>
            <p class="font-normal">5/16/23</p>
            </div>
        </div>
    </a>
    <a href="/projects/threlte-projects" class="card project-card bg-surface-100-800-token shadow-md hover:scale-105">
        <div class="content">
            <div class="m-auto h-full w-full overflow-hidden">
            </div>
            <div class='description bg-surface-200-700-token'>
                <p class="text-lg">Threlte Projects</p>
                <p class="font-normal ">6/8/23</p>
            </div>
        </div>
    </a>
    <a href="/" class="card project-card bg-surface-100-800-token shadow-md hover:scale-105">
        <div class="content">
            <div class="m-auto h-full w-full overflow-hidden">
            </div>
            <div class='description bg-surface-200-700-token'>
                <p class="text-lg">3</p>
                <p class="font-normal">Coming soon!</p>
            </div>
        </div>
    </a>
</div>
