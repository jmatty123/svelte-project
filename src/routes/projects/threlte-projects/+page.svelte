<script lang="ts">
    import OrbitSc from '/src/components/threlte/OrbitSc.svelte'
    import TorusKnotSc from '/src/components/threlte/TorusKnotSc.svelte'
    import Coin from '/src/components/threlte/Coin.svelte'
</script>

<div class='flex flex-col justify-center sm:justify-start items-center sm:items-start max-w-screen-lg lg:mx-auto mt-10'>
<h1 class='mx-10 mb-3 text-center text-2xl font-thin'>Threlte Components</h1>
<h2 class='mx-10 mb-6 pt-3 text-lg font-thin border-t-[1px] border-current'>Threlte is a renderer and component library for Svelte to build and render three.js scenes declaratively and state-driven in Svelte apps. Below you will find a few components i've created as I learn and experiment with Three.js and Threlte.</h2>
</div>

<div class="box-border h-auto m-10 xl:mx-auto xl:w-[80%] grid grid-cols-1 sm:grid-cols-2 xl:grid-cols-3 gap-10">
    <div class="card rounded-none pt-[90%] text-center relative flex justify-center items-center">
        <div class="absolute inset-0">
            <Coin />
        </div>
    </div>
    <div class="card rounded-none pt-[90%] text-center overflow-clip relative flex justify-center items-center">
        <div class="flex items-center justify-center absolute inset-0 mx-2">
            <TorusKnotSc />
        </div>
    </div>
    <div class="card rounded-none pt-[90%] text-center overflow-clip relative flex justify-center items-center">
        <div class="flex items-center justify-center absolute inset-0 mx-2">
            <OrbitSc />
        </div>
    </div>
</div>