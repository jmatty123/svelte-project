<script>
    import { T, useFrame } from '@threlte/core'
    import { interactivity } from '@threlte/extras'
    import { spring } from 'svelte/motion'

    interactivity()
    const scale = spring(.15)

    let rotation = 0
    useFrame((state, delta) => {
        rotation += delta
    })
</script>

<T.PerspectiveCamera
  makeDefault
  position={[10, 10, 10]}
  on:create={({ ref }) => {
    ref.lookAt(0, 1, 0)
  }}
/>

<T.DirectionalLight position={[3, 10, 7]} />

<T.Mesh
    rotation.y={rotation}
    rotation.x={rotation}
    position.y={1}
    scale={$scale}
    on:pointerenter={() => scale.set(.15)}
    on:pointerleave={() => scale.set(.15)}    
>
  <T.TorusKnotGeometry args={[10, 3, 100, 16, 1, 3]} />
  <T.MeshStandardMaterial color="white" />
</T.Mesh>