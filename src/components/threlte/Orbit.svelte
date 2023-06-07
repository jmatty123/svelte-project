<script lang='ts'>
    import { T, useFrame } from '@threlte/core'
    import { interactivity } from '@threlte/extras'
    import { spring } from 'svelte/motion'

    interactivity()
    const scale = spring(.5)
    
    let rotation = 0
    let globalspeed = 5
    let orbitsize = 2.25
    let orbitspeed = 1
    let bobspeed = 1
    let bobdepth = .5
    let revolvespeed = 5
    
    let spherePos1 = { x: orbitsize, y: orbitsize, z: 0 }
    let spherePos2 = { x: orbitsize, y: orbitsize, z: 0 }
    let spherePos3 = { x: orbitsize, y: orbitsize, z: 0 }

    useFrame((state, delta) => {
        rotation = ((rotation + delta/globalspeed) % (2*Math.PI));
        
        spherePos1.x = orbitsize * Math.cos(rotation*orbitspeed);
        spherePos1.y = orbitsize * Math.sin(rotation*orbitspeed);
        spherePos1.z = bobdepth*Math.tan(rotation*bobspeed);

        spherePos2.x = orbitsize * Math.cos(rotation*orbitspeed + 4*Math.PI/3);
        spherePos2.y = orbitsize * Math.sin(rotation*orbitspeed + 4*Math.PI/3);
        spherePos2.z = bobdepth*Math.tan(rotation*bobspeed + 4*Math.PI/3);

        spherePos3.x = orbitsize * Math.cos(rotation*orbitspeed + 2*Math.PI/3);
        spherePos3.y = orbitsize * Math.sin(rotation*orbitspeed + 2*Math.PI/3);
        spherePos3.z = bobdepth*(Math.tan(rotation*bobspeed + 2*Math.PI/3));
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
    rotation.x={rotation*revolvespeed}
    rotation.y={rotation*revolvespeed}
    rotation.z={0}  
>
  <T.IcosahedronGeometry args={[.6, 0]} />
  <T.MeshStandardMaterial color="cyan" />
</T.Mesh>

<T.Mesh
    position={[spherePos2.x, spherePos2.y, spherePos2.z]}
    scale={$scale}
    rotation.x={rotation*revolvespeed}
    rotation.y={0}
    rotation.z={rotation*revolvespeed} 
>
  <T.IcosahedronGeometry args={[.6, 0]} />
  <T.MeshStandardMaterial color="yellow" />
</T.Mesh>

<T.Mesh
    position={[spherePos3.x, spherePos3.y, spherePos3.z]}
    scale={$scale}
    rotation.x={0}
    rotation.y={rotation*revolvespeed}
    rotation.z={rotation*revolvespeed}  
>
  <T.IcosahedronGeometry args={[.6, 0]} />
  <T.MeshStandardMaterial color="magenta" />
</T.Mesh>