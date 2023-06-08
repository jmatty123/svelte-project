<script lang="ts">
    import OrbitSc from '/src/components/threlte/OrbitSc.svelte'
    import TorusKnotSc from '/src/components/threlte/TorusKnotSc.svelte'
</script>

<div class="box-border border-0 border-red-500 sm:w-[90%] max-w-screen-2xl my-4 sm:my-8 mx-2 sm:mx-auto grid grid-cols-1 sm:grid-cols-2 xl:grid-cols-3 gap-4 sm:gap-8 xl:gap-12">
    <div class="card pt-[100%] text-center relative flex justify-center items-center">
        <div class="flex items-center absolute inset-0 mx-2">
            <OrbitSc />
        </div>
    </div>
    <div class="card pt-[100%] text-center relative flex justify-center items-center">
        <div class="flex items-center absolute inset-0 mx-2">
            <TorusKnotSc />
        </div>
    </div>
    <div class="card pt-[100%] text-center relative flex justify-center items-center">
        <div class="flex items-center absolute inset-0 mx-2">
            <OrbitSc />
        </div>
    </div>
    <div class="card pt-[100%] text-center relative flex justify-center items-center">
        <div class="flex items-center absolute inset-0 mx-2">
            <OrbitSc />
        </div>
    </div>
    <div class="card pt-[100%] text-center relative flex justify-center items-center">
        <div class="flex items-center absolute inset-0 mx-2">
            <OrbitSc />
        </div>
    </div>
</div>