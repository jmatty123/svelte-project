<script lang='ts'>
    import Map from '/src/components/Map.svelte';
    import Knot from '/src/components/threlte/TorusKnotSc.svelte';
</script>


<div class='box-border h-auto m-10 xl:mt-20 xl:mx-auto xl:w-[80%] grid grid-cols-1 sm:grid-cols-2 xl:grid-cols-3 gap-10'>
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
    <a href="/projects/psql-database" class="card project-card bg-surface-100-800-token shadow-md hover:scale-105">
        <div class="content">
            <div class="m-auto h-full w-full flex items-center justify-center overflow-hidden scale-95">
                <Knot />
            </div>
            <div class='description bg-surface-200-700-token'>
                <p class="font-thin text-xl">PSQL Database</p>
                <p class="font-thin text-lg">Coming soon!</p>
            </div>
        </div>
    </a>
</div>
