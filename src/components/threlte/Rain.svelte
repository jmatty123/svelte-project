<script>
    import { T, useFrame } from '@threlte/core'
    import { interactivity } from '@threlte/extras'
    import { spring } from 'svelte/motion'
    import { writable } from 'svelte/store'
  
    interactivity()
    const scale = spring(1)
    let rotation = 0
    const position1 = writable({ y: 10, x: (Math.random() - 0.5) * 10, z: (Math.random() - 0.5) * 10 });
    const position2 = writable({ y: 10, x: (Math.random() - 0.5) * 10, z: (Math.random() - 0.5) * 10 });
    const position3 = writable({ y: 10, x: (Math.random() - 0.5) * 10, z: (Math.random() - 0.5) * 10 });
    const position4 = writable({ y: 10, x: (Math.random() - 0.5) * 10, z: (Math.random() - 0.5) * 10 });
    const position5 = writable({ y: 10, x: (Math.random() - 0.5) * 10, z: (Math.random() - 0.5) * 10 });

    let delay1 = Math.random() * 20;
    let delay2 = Math.random() * 20;
    let delay3 = Math.random() * 20;
    let delay4 = Math.random() * 20;
    let delay5 = Math.random() * 20;

    useFrame((state, delta) => {
      rotation += delta

      if (delay1 > 0) {
        delay1 -= delta;
      } else {
        position1.update(pos => {
          pos.y -= delta;
          if (pos.y < -14) {
              pos.y = 10;
          }
          return pos;
        })
      }

      if (delay2 > 5) {
        delay2 -= delta;
      } else {
        position2.update(pos => {
          pos.y -= delta;
          if (pos.y < -14) {
              pos.y = 10;
          }
          return pos;
        })
      }

      if (delay3 > 10) {
        delay3 -= delta;
      } else {
        position3.update(pos => {
          pos.y -= delta;
          if (pos.y < -14) {
              pos.y = 10;
          }
          return pos;
        })
      }

      if (delay4 > 15) {
        delay4 -= delta;
      } else {
        position4.update(pos => {
          pos.y -= delta;
          if (pos.y < -14) {
              pos.y = 10;
          }
          return pos;
        })
      }

      if (delay5 >= 20) {
        delay5 -= delta;
      } else {
        position5.update(pos => {
          pos.y -= delta;
          if (pos.y < -14) {
              pos.y = 10;
          }
          return pos;
        })
      }
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
    position={[ $position1.x, $position1.y, $position1.z ]}
    scale={$scale}
    on:pointerenter={() => scale.set(1.5)}
    on:pointerleave={() => scale.set(1)}
  >
    <T.DodecahedronGeometry args={[1, 0]} />
    <T.MeshStandardMaterial color="white" />
  </T.Mesh>

  <T.Mesh
  rotation.y={rotation}
  rotation.x={rotation}
  position={[ $position2.x, $position2.y, $position2.z ]}
  scale={$scale}
  on:pointerenter={() => scale.set(1.5)}
  on:pointerleave={() => scale.set(1)}
>
  <T.DodecahedronGeometry args={[1, 0]} />
  <T.MeshStandardMaterial color="white" />
</T.Mesh>
  
<T.Mesh
  rotation.y={rotation}
  rotation.x={rotation}
  position={[ $position3.x, $position3.y, $position3.z ]}
  scale={$scale}
  on:pointerenter={() => scale.set(1.5)}
  on:pointerleave={() => scale.set(1)}
>
  <T.DodecahedronGeometry args={[1, 0]} />
  <T.MeshStandardMaterial color="white" />
</T.Mesh>

<T.Mesh
  rotation.y={rotation}
  rotation.x={rotation}
  position={[ $position4.x, $position4.y, $position4.z ]}
  scale={$scale}
  on:pointerenter={() => scale.set(1.5)}
  on:pointerleave={() => scale.set(1)}
>
  <T.DodecahedronGeometry args={[1, 0]} />
  <T.MeshStandardMaterial color="white" />
</T.Mesh>

<T.Mesh
  rotation.y={rotation}
  rotation.x={rotation}
  position={[ $position5.x, $position5.y, $position5.z ]}
  scale={$scale}
  on:pointerenter={() => scale.set(1.5)}
  on:pointerleave={() => scale.set(1)}
>
  <T.DodecahedronGeometry args={[1, 0]} />
  <T.MeshStandardMaterial color="white" />
</T.Mesh>