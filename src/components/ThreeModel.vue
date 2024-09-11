<template>
  <div ref="threeContainer" class="three-container h-full w-full"></div>
</template>

<script setup>
import { onMounted, ref } from 'vue'
import * as THREE from 'three'
import {GLTFLoader} from 'three/examples/jsm/loaders/GLTFLoader.js'
import {OrbitControls} from 'three/examples/jsm/controls/OrbitControls.js'

const threeContainer = ref(null)

onMounted(() => {
  const scene = new THREE.Scene()
  const camera = new THREE.PerspectiveCamera(75, threeContainer.value.clientWidth / threeContainer.value.clientHeight, 0.1, 1000)
  const renderer = new THREE.WebGLRenderer({antialias: true})

  renderer.setSize(threeContainer.value.clientWidth, threeContainer.value.clientHeight)
  renderer.setPixelRatio(window.devicePixelRatio)
  threeContainer.value.appendChild(renderer.domElement)

  const controls = new OrbitControls(camera, renderer.domElement)
  controls.enableDamping = true
  controls.dampingFactor = 0.25
  controls.screenSpacePanning = false
  controls.maxPolarAngle = Math.PI / 2

  const ambientLight = new THREE.AmbientLight(0xffffff, 1)
  scene.add(ambientLight)

  const directionalLight = new THREE.DirectionalLight(0xffffff, 1)
  directionalLight.position.set(0, 10, 10)
  scene.add(directionalLight)

  // Acercar la cámara al modelo
  camera.position.set(1, 0.7, 0) // Ajusta la posición según necesites; más cerca y a la altura del modelo

  const loader = new GLTFLoader()

  loader.load('/CajaEco.glb', (gltf) => {
    const model = gltf.scene

    // Si el modelo ya mide 1 metro en Blender, mantendremos la escala
    model.scale.set(1, 1, 1) // Escala 1:1 según el tamaño original en Blender

    model.position.set(0, 0, 0)

    scene.add(model)
    console.log('Modelo agregado a la escena:', model)
  }, undefined, (error) => {
    console.error('Error al cargar el modelo:', error)
  })

  const animate = () => {
    requestAnimationFrame(animate)
    controls.update()
    renderer.render(scene, camera)
  }

  window.addEventListener('resize', () => {
    const width = threeContainer.value.clientWidth
    const height = threeContainer.value.clientHeight
    renderer.setSize(width, height)
    camera.aspect = width / height
    camera.updateProjectionMatrix()
  })

  animate()
})
</script>

<style scoped>
.three-container {
  width: 100%;
  height: 100%;
  position: relative;
  background-color: #f3f4f6; /* Color de fondo gris para el contenedor */
}
</style>

