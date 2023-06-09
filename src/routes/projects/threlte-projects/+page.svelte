<script lang="ts">
    import OrbitSc from '/src/components/threlte/OrbitSc.svelte'
    import TorusKnotSc from '/src/components/threlte/TorusKnotSc.svelte'
</script>

<div class='flex flex-col justify-center items-center max-w-[640px] mx-auto'>
<h1 class='my-10 text-center text-xl font-semibold'>Geometry Components</h1>
<h2 class='mx-10 mb-10'>Threlte is a renderer and component library for Svelte to build and render three. js scenes declaratively and state-driven in Svelte apps. Here you will find some small components I've created as I experiment and learn more.</h2>
</div>

<div class="box-border sm:w-[90%] max-w-screen my-4 mx-2 sm:mx-auto grid grid-cols-1 sm:grid-cols-2 xl:grid-cols-3 gap-4 sm:gap-10">
    <div class="card border-none pt-[100%] text-center overflow-clip relative flex justify-center items-center">
        <div class="flex items-center justify-center absolute inset-0 mx-2">
            <OrbitSc />
        </div>
    </div>
    <div class="card pt-[100%] text-center overflow-clip relative flex justify-center items-center">
        <div class="flex items-center justify-center absolute inset-0 mx-2">
            <TorusKnotSc />
        </div>
    </div>
    <div class="card pt-[100%] text-center overflow-clip relative flex justify-center items-center">
        <div class="flex items-center justify-center absolute inset-0 mx-2">
            
        </div>
    </div>
</div>