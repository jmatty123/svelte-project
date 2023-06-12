<script lang='ts'>
    import Map from '/src/components/Map.svelte';
    import Orbit from '/src/components/threlte/OrbitSc.svelte';
</script>


<div class='box-border h-auto m-10 xl:mx-auto xl:w-[80%] grid grid-cols-1 sm:grid-cols-2 xl:grid-cols-3 gap-10'>
    <a href="/projects/personal-website" class="card project-card bg-surface-100-800-token shadow-md hover:scale-105">  
        <div class="content">
            <div class="m-auto h-full w-full overflow-hidden pointer-events-none">
                <Map />
            </div>
            <div class='description bg-surface-200-700-token items-center'>
            <p class="font-thin text-xl">Personal Website</p>
            <p class="font-thin text-lg">5/16/23</p>
            </div>
        </div>
    </a>
    <a href="/projects/threlte-projects" class="card project-card bg-surface-100-800-token shadow-md hover:scale-105">
        <div class="content">
            <div class="m-auto h-full w-full flex items-center justify-center overflow-hidden">
                <Orbit />
            </div>
            <div class='description bg-surface-200-700-token'>
                <p class="font-thin text-xl">Threlte Components</p>
                <p class="font-thin text-lg">6/8/23</p>
            </div>
        </div>
    </a>
    <a href="/" class="card project-card bg-surface-100-800-token shadow-md hover:scale-105">
        <div class="content">
            <div class="m-auto h-full w-full overflow-hidden">
            </div>
            <div class='description bg-surface-200-700-token'>
                <p class="font-thin text-xl">3</p>
                <p class="font-thin text-lg">Coming soon!</p>
            </div>
        </div>
    </a>
</div>
