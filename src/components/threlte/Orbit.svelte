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

    let spherePos1 = { x: 2.25, y: 2.25, z: 0 }
    useFrame((state, delta) => {
        spherePos1.x = 2.25 * Math.cos(rotation);
        spherePos1.y = -2.25 * Math.sin(rotation);
    })
    
    let spherePos2 = { x: 2.25, y: 2.25, z: 0 }
    useFrame((state, delta) => {
        spherePos2.x = -2.25 * Math.cos(rotation);
        spherePos2.y = 2.25 * Math.sin(rotation);
    })

</script>


<T.PerspectiveCamera
  makeDefault
  position={[0, 10, 0]}
  on:create={({ ref }) => {
    ref.lookAt(0, 0, 0)
  }}
/>

<T.DirectionalLight position={[3, 10, 7]} />

<T.Mesh
    rotation.x={0}
    rotation.y={0}
    rotation.z={rotation}
    scale={$scale} 
>
  <T.TorusKnotGeometry args={[5, .1, 1000, 100, 5, 3]} />
  <T.MeshStandardMaterial color="white" />
</T.Mesh>

<T.Mesh
    position={[spherePos1.x, spherePos1.y, spherePos1.z]}
    scale={$scale}
    rotation.x={rotation*2}
    rotation.y={0}
    rotation.z={rotation*2}  
>
  <T.IcosahedronGeometry args={[.7, 0]} />
  <T.MeshStandardMaterial color="red" />
</T.Mesh>

<T.Mesh
    position={[spherePos2.x, spherePos2.y, spherePos2.z]}
    scale={$scale}
    rotation.x={-rotation*2}
    rotation.y={0}
    rotation.z={rotation*2} 
>
  <T.IcosahedronGeometry args={[.7, 0]} />
  <T.MeshStandardMaterial color="white" />
</T.Mesh>