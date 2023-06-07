<script lang='ts'>
    import { T, useFrame } from '@threlte/core'
    import { interactivity } from '@threlte/extras'
    import { spring } from 'svelte/motion'

    interactivity()
    const scale = spring(.5)

    let rotation = 0
    let spherePos1 = { x: 2.25, y: 2.25, z: 0 }
    let spherePos2 = { x: 2.25, y: 2.25, z: 0 }
    let spherePos3 = { x: 2.25, y: 2.25, z: 0 }

    useFrame((state, delta) => {
        rotation = (rotation + delta/5) % (2*Math.PI);
        
        spherePos1.x = 2.25 * Math.cos(rotation);
        spherePos1.y = -2.25 * Math.sin(rotation);

        spherePos2.x = 2.25 * Math.cos(rotation + 2*Math.PI/3);
        spherePos2.y = -2.25 * Math.sin(rotation + 2*Math.PI/3);

        spherePos3.x = 2.25 * Math.cos(rotation + 4*Math.PI/3);
        spherePos3.y = -2.25 * Math.sin(rotation + 4*Math.PI/3);
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
  <T.IcosahedronBufferGeometry args={[.5, 0]} />
  <T.MeshStandardMaterial color="cyan" />
</T.Mesh>

<T.Mesh
    position={[spherePos2.x, spherePos2.y, spherePos2.z]}
    scale={$scale}
    rotation.x={-rotation*2}
    rotation.y={0}
    rotation.z={rotation*2} 
>
  <T.IcosahedronGeometry args={[.5, 0]} />
  <T.MeshStandardMaterial color="yellow" />
</T.Mesh>

<T.Mesh
    position={[spherePos3.x, spherePos3.y, spherePos3.z]}
    scale={$scale}
    rotation.x={rotation*2}
    rotation.y={0}
    rotation.z={-rotation*2}  
>
  <T.IcosahedronBufferGeometry args={[.5, 0]} />
  <T.MeshStandardMaterial color="magenta" />
</T.Mesh>