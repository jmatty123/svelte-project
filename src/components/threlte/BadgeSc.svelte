<script lang='ts'>
    import { spring } from 'svelte/motion'
    import { T } from '@threlte/core'
    import { Environment, interactivity, useInteractivity } from '@threlte/extras';
	import Coin from './Plaincoin.svelte';

    interactivity();
    const { pointer } = useInteractivity();

    const scale = spring(.5);
    const rotation = spring(0);

    function onEnter() {
        $scale = .55;
    }
    function onLeave() {
        $scale = .5;
    }
</script>

<T.PerspectiveCamera position={[0, 0, 3]} makeDefault />
<!-- <T.DirectionalLight position={[-3, 10, 10]} /> -->
<Environment files='/light.hdr' />
<T.Group scale={$scale} rotation.y={$rotation}>
    <T.Group rotation.y={$pointer.x} rotation.x={-$pointer.y}>
        <Coin on:pointerenter={onEnter} on:pointerleave={onLeave}/>
    </T.Group>
</T.Group>