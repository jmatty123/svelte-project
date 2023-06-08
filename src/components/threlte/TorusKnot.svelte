<script lang='ts'>
    import { T, useFrame } from '@threlte/core'
    import { interactivity } from '@threlte/extras'
    import { spring } from 'svelte/motion'

    interactivity()
    const scale = spring(.8)

    let rotation = 0
    useFrame((state, delta) => {
        rotation -= delta/5
    })

</script>


<T.PerspectiveCamera
  makeDefault
  position={[0, 3, 1]}
  on:create={({ ref }) => {
    ref.lookAt(3, 0, 1)
  }}
/>

<T.DirectionalLight position={[3, 10, 7]} />

<T.Mesh
    rotation.z={-rotation/2}
    rotation.x={0}
    rotation.y={0}
    position.z={1}
    scale={$scale}
    on:pointerenter={() => scale.set(.8)}
    on:pointerleave={() => scale.set(.8)}    
>
  <T.TorusKnotGeometry args={[3, .2, 1000, 100, 7, 20]} />
  <T.MeshStandardMaterial color="white" />
</T.Mesh>
