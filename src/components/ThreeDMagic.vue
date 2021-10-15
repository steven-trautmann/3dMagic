<template>
  <h1>NANI?!</h1>
</template>

<script>
import * as THREE from 'three'

export default {
  name: '3dMagic',

  data () {
    return {}
  },
  created () {
    const scene = new THREE.Scene()
    const camera = new THREE.PerspectiveCamera(75, window.innerWidth / window.innerHeight, 0.1, 1000)
    const renderer = new THREE.WebGLRenderer({
        canvas: document.querySelector('#bg')
    })
    renderer.setPixelRatio( window.devicePixelRatio )
    renderer.setSize(window.innerWidth, window.innerHeight)
    camera.position.setZ(30)

    const geometry = new THREE.TorusGeometry(10, 3, 16, 100)
    const material = new THREE.MeshBasicMaterial({ color: 0xFF6347, wireframe: true })
    const torus = new THREE.Mesh(geometry, material)
    scene.add(torus)
    let backwards = false

    function animate () {
        requestAnimationFrame(animate)
        if (torus.position.x > 20) {
            backwards = true
        }
        if (torus.position.x < -20) {
            backwards = false
        }
        torus.position.x += backwards ? -0.05 : 0.05
        torus.rotation.x += 0.001
        torus.rotation.y += 0.005
        torus.rotation.z += 0.09

        renderer.render(scene, camera)
    }
    animate()
  }
}
</script>

<style scoped>
</style>
