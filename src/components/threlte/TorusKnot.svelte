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

</script>


<T.PerspectiveCamera
  makeDefault
  position={[0, 10, 0]}
  on:create={({ ref }) => {
    ref.lookAt(0, 0, 1)
  }}
/>

<T.DirectionalLight position={[3, 10, 7]} />

<T.Mesh
    rotation.x={0}
    rotation.y={0}
    rotation.z={-rotation}
    position.z={1}
    scale={$scale} 
>
  <T.TorusKnotGeometry args={[5, .1, 1000, 100, 5, 3]} />
  <T.MeshStandardMaterial color="white" />
</T.Mesh>
