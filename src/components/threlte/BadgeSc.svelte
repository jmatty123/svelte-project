<script lang='ts'>
    import { T } from '@threlte/core'
	import RealCoin from './RealCoin.svelte';
</script>

<T.PerspectiveCamera position={[0, 0, 10]} makeDefault />
<T.DirectionalLight position={[-3, 10, 10]} />

<RealCoin />