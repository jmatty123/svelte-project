<script lang='ts'>
    import Map from '/src/components/Map.svelte';
</script>

<div class='box-border m-8 w-auto h-auto grid grid-cols-1 sm:grid-cols-2 xl:grid-cols-3 gap-8'>
    <a href="/projects/personal-website" class="card project-card bg-surface-100-800-token shadow-md hover:scale-105">  
        <div class="content">
            <div class='m-2 p-2 flex flex-col justify-center items-end bg-surface-100-800-token opacity-80 rounded'>
            <p class="text-xl">Personal Website</p>
            <p class="text-lg">5/16/23</p>
            </div>
        </div>
    </a>
    <a href="/" class="card project-card bg-surface-100-800-token shadow-md hover:scale-105">
        <div class="content">
            <div class='m-2 p-2 flex flex-col justify-center items-end bg-surface-100-800-token opacity-80 rounded'>
                <p class="text-xl">2</p>
                <p class="text-lg">Coming soon!</p>
            </div>
        </div>
    </a>
    <a href="/" class="card project-card bg-surface-100-800-token shadow-md hover:scale-105">
        <div class="content">
            <div class='m-2 p-2 flex flex-col justify-center items-end bg-surface-100-800-token opacity-80 rounded'>
                <p class="text-xl">3</p>
                <p class="text-lg">Coming soon!</p>
            </div>
        </div>
    </a>
</div>
