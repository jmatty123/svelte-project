<script lang='ts'>
    import { T, useFrame } from '@threlte/core'
    import { interactivity } from '@threlte/extras'
    import { spring } from 'svelte/motion'

    interactivity()
    const scale = spring(.5)

    let rotation = 0
    useFrame((state, delta) => {
        rotation -= delta/5
    })

    let morph = 0
    useFrame((state, delta) => {
        morph += delta
    })

</script>


<T.PerspectiveCamera
  makeDefault
  position={[0, 10, 0]}
  on:create={({ ref }) => {
    ref.lookAt(0, 1, 0)
  }}
/>

<T.DirectionalLight position={[3, 10, 7]} />

<T.Mesh
    rotation.z={rotation}
    rotation.x={0}
    rotation.y={0}
    position.y={1}
    scale={$scale}
    on:pointerenter={() => scale.set(.5)}
    on:pointerleave={() => scale.set(.5)}    
>
  <T.TorusKnotGeometry args={[5, .1, 1000, 100, 5, 3]} />
  <T.MeshStandardMaterial color="darkgray" />
</T.Mesh>
