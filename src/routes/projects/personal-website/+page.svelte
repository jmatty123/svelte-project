<script lang='ts'>
    import OrbitSc from '/src/components/threlte/OrbitSc.svelte'
    import TorusKnotSc from '/src/components/threlte/TorusKnotSc.svelte'
    import Coin from '/src/components/threlte/Coin.svelte'
</script>

<div class="flex flex-col justify-center sm:justify-start items-center sm:items-start max-w-screen-lg lg:mx-auto mt-10">
<h1 class='mx-10 mb-3 text-center text-2xl font-thin'>Personal Website</h1>
<h2 class="mx-10 mb-6 pt-3 text-lg font-thin border-t-[1px] border-current">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Proin ultrices nunc elit, sed commodo justo feugiat in. Aenean hendrerit lobortis semper. Pellentesque at nisl quis diam fringilla blandit eu quis arcu. Ut ultricies mi ante. Fusce aliquam, erat vel condimentum finibus, mauris lorem laoreet quam, quis ullamcorper nisl libero ac ipsum. Interdum et malesuada fames ac ante ipsum primis in faucibus. Cras vulputate convallis libero, maximus congue leo sodales id.

</h2>

    <div class="logo-cloud rounded-none grid-cols-5 gap-1 sm:w-[420px] mx-1 sm:mx-10">
        <a class="logo-item p-2 text-xs font-extralight" href="https://svelte.dev/">
            <span>Svelte</span>
        </a>
        <a class="logo-item p-2 text-xs font-extralight" href="https://next.threlte.xyz/">
            <span>Threlte</span>
        </a>
        <a class="logo-item p-2 text-xs font-extralight" href="https://tailwindcss.com/">
            <span>TailwindCSS</span>
        </a>
        <a class="logo-item p-2 text-xs font-extralight" href="https://vitejs.dev/">
            <span>Vite</span>
        </a>
        <a class="logo-item p-2 text-xs font-extralight" href="https://vercel.com/">
            <span>Vercel</span>
        </a>
        <!-- ... -->
    </div>
</div>

<div class='flex flex-col justify-center sm:justify-start items-center sm:items-start max-w-screen-lg lg:mx-auto mt-16'>
    <h1 class='mx-10 mb-3 text-center text-xl font-thin'>Threlte Components</h1>
    <h2 class='mx-10 mb-6 pt-3 text-base font-thin border-t-[1px] border-current'>Threlte is a renderer and component library for Svelte to build and render three.js scenes declaratively and state-driven in Svelte apps. Below you will find a few components i've created as I learn and experiment with Three.js and Threlte.</h2>
    </div>
    
    <div class="box-border border-0 border-red-500 h-auto m-10 lg:mx-auto max-w-[960px] grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-10">
        <div class="card rounded-none pt-[90%] text-center overflow-clip relative flex justify-center items-center">
            <div class="flex items-center justify-center absolute inset-0 mx-2">
                <TorusKnotSc />
            </div>
        </div>
        <div class="card rounded-none pt-[90%] text-center overflow-clip relative flex justify-center items-center">
            <div class="absolute inset-0">
                <Coin />
            </div>
        </div>
        <div class="card rounded-none pt-[90%] text-center overflow-clip relative flex justify-center items-center">
            <div class="flex items-center justify-center absolute inset-0 mx-2">
                <OrbitSc />
            </div>
        </div>
    </div>
