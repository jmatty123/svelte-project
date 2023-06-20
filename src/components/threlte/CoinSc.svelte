<script lang='ts'>
    import { spring } from 'svelte/motion'
    import { T } from '@threlte/core'
    import { Environment, interactivity, useInteractivity } from '@threlte/extras';
	import PlainCoin from './Plaincoin.svelte';

    interactivity();
    const { pointer } = useInteractivity();

    const scale = spring(.75);
    const rotation = spring(0);

</script>

<T.PerspectiveCamera position={[0, 0, 3]} makeDefault />
<!-- <T.DirectionalLight position={[-3, 10, 10]} /> -->
<Environment files='/light.hdr' />
<T.Group scale={$scale} rotation.y={$rotation}>
    <T.Group rotation.y={$pointer.x} rotation.x={-$pointer.y}>
        <PlainCoin />
    </T.Group>
</T.Group>