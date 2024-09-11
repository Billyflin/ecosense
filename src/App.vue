<template>
  <div class="min-h-screen bg-gradient-to-br from-green-50 via-green-100 to-green-200">
    <header class="bg-white shadow-md sticky top-0 z-10">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-4 flex justify-between items-center">
        <img
            src="https://hebbkx1anhila5yf.public.blob.vercel-storage.com/EcoSenseLogo-DHVwhz2SZjI9llKKwW9GgqxFEIykwO.svg"
            alt="Logo de EcoSense"
            class="w-48 transition-transform duration-300 hover:scale-105"
        />
        <nav>
          <ul class="flex space-x-6">
            <li v-for="item in navItems" :key="item.href">
              <a :href="item.href" class="text-green-600 hover:text-green-800 transition-colors duration-300 font-medium">
                {{ item.text }}
              </a>
            </li>
          </ul>
        </nav>
      </div>
    </header>

    <main class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-12">
      <section id="about" class="mb-20">
        <h2 class="text-4xl font-bold text-green-800 mb-8 text-center">Acerca de EcoSense</h2>
        <div class="grid gap-8 md:grid-cols-2">
          <div class="bg-white shadow-lg rounded-xl overflow-hidden transform transition-all duration-300 hover:scale-105">
            <div class="p-6">
              <h3 class="text-2xl font-semibold mb-3 text-green-700">Recolector Inteligente de Vasos de Café</h3>
              <p class="text-gray-600 mb-4">Solución innovadora para la gestión de residuos</p>
            </div>
            <div class="h-64 bg-gray-100">
              <three-model></three-model>
            </div>
          </div>
          <div class="bg-white shadow-lg rounded-xl p-6 transform transition-all duration-300 hover:scale-105">
            <h3 class="text-2xl font-semibold mb-6 text-green-700">Características Principales</h3>
            <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
              <feature-item v-for="feature in features" :key="feature.title" v-bind="feature" />
            </div>
          </div>
        </div>
      </section>

      <process-step></process-step>

      <section class="mb-20">
        <h2 class="text-4xl font-bold text-green-800 mb-8 text-center">Aplicación EcoSense</h2>
        <div class="bg-white shadow-lg rounded-xl overflow-hidden">
          <div class="grid grid-cols-2">
            <button
                v-for="tab in ['user', 'admin']"
                :key="tab"
                @click="selectedTab = tab"
                :class="[
                'p-4 transition-colors duration-300 font-semibold text-lg',
                selectedTab === tab ? 'bg-green-500 text-white' : 'bg-gray-100 text-gray-700 hover:bg-green-100'
              ]"
            >
              {{ tab === 'user' ? 'Funciones de Usuario' : 'Funciones de Administrador' }}
            </button>
          </div>
          <div class="p-6">
            <div v-if="selectedTab === 'user'">
              <h3 class="flex items-center text-2xl font-semibold mb-6 text-green-700">
                <span class="material-symbols-outlined mr-3 text-3xl">person</span>
                Funcionalidades para Usuarios
              </h3>
              <ul class="space-y-4">
                <li v-for="feature in userFeatures" :key="feature.text" class="flex items-start">
                  <span class="material-symbols-outlined text-green-500 mr-3 text-2xl">{{ feature.icon }}</span>
                  <span class="text-lg">{{ feature.text }}</span>
                </li>
              </ul>
            </div>
            <div v-if="selectedTab === 'admin'">
              <h3 class="flex items-center text-2xl font-semibold mb-6 text-green-700">
                <span class="material-symbols-outlined mr-3 text-3xl">admin_panel_settings</span>
                Panel de Administración
              </h3>
              <ul class="space-y-4">
                <li v-for="feature in adminFeatures" :key="feature.text" class="flex items-start">
                  <span class="material-symbols-outlined text-green-500 mr-3 text-2xl">{{ feature.icon }}</span>
                  <span class="text-lg">{{ feature.text }}</span>
                </li>
              </ul>
            </div>
          </div>
        </div>
      </section>

      <section id="download" class="mb-20">
        <h2 class="text-4xl font-bold text-green-800 mb-8 text-center">Plataformas Soportadas</h2>
        <div class="bg-white shadow-lg rounded-xl p-8">
          <div class="flex justify-center space-x-12">
            <platform-item v-for="platform in platforms" :key="platform.name" v-bind="platform" />
          </div>
        </div>
      </section>

      <section class="text-center mb-20">
        <h2 class="text-4xl font-bold text-green-800 mb-6">¡Únete a EcoSense Hoy!</h2>
        <p class="mb-8 text-xl text-green-600">Descarga la aplicación y sé parte del cambio hacia un campus más sostenible.</p>
        <div class="flex flex-wrap justify-center gap-6">
          <download-button v-for="button in downloadButtons" :key="button.platform" v-bind="button" />
        </div>
      </section>
    </main>

    <footer class="bg-green-800 text-white py-12">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="flex flex-col md:flex-row justify-between items-center">
          <div class="mb-6 md:mb-0">
            <img
                src="https://hebbkx1anhila5yf.public.blob.vercel-storage.com/EcoSenseLogoBlanco-vqrjUQ4yuYgXlXn5r14s2BXzsYxs8l.svg"
                alt="Logo de EcoSense"
                class="w-40 mb-4"
            />
            <p class="text-lg">&copy; 2024 EcoSense. Todos los derechos reservados.</p>
          </div>
          <div>
            <a href="https://github.com/Billyflin/UfroSustentableApp" target="_blank" rel="noopener noreferrer" class="text-white hover:text-green-200 transition-colors flex items-center text-lg">
              <span class="material-symbols-outlined mr-2">code</span>
              Ver en GitHub
            </a>
          </div>
        </div>
      </div>
    </footer>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import ThreeModel from "./components/ThreeModel.vue"
import FeatureItem from "./components/FeatureItem.vue"
import ProcessStep from "./components/ProcessStep.vue"
import PlatformItem from "./components/PlatformItem.vue"
import DownloadButton from "./components/DownloadButton.vue"

const selectedTab = ref('user')

const navItems = [
  { href: "#about", text: "Acerca de" },
  { href: "#features", text: "Características" },
  { href: "#download", text: "Descargar" },
]

const features = [
  { icon: "sensors", title: "Sensores de nivel", description: "Monitoreo preciso del llenado" },
  { icon: "wifi", title: "Conectividad LoRa", description: "Transmisión eficiente de datos" },
  { icon: "design_services", title: "Diseño ergonómico", description: "Fácil uso para todos los usuarios" },
  { icon: "scale", title: "Báscula de peso", description: "Indica peso para medir contenedor de agua y vasos" },
  { icon: "local_cafe", title: "Capacidad optimizada", description: "Diseñado para vasos de café" },
  { icon: "battery_charging_full", title: "Batería de larga duración", description: "Litio con configuración 3s6p" },
  { icon: "local_shipping", title: "Retiro rápido de material reciclado", description: "Diseño modular que facilita la extracción y transporte" },
  { icon: "local_drink", title: "Lavado de vasos", description: "Limpiador de vasos de alta presión" },
]


const userFeatures = [
  { icon: "star", text: "Ver puntuación actual de reciclaje" },
  { icon: "redeem", text: "Lista de beneficios obtenidos" },
  { icon: "history", text: "Historial personal de reciclaje" },
  { icon: "eco", text: "Consejos para reducir el uso de desechables" },
]

const adminFeatures = [
  { icon: "monitoring", text: "Monitoreo en tiempo real de los recolectores" },
  { icon: "analytics", text: "Estadísticas de uso y eficiencia" },
  { icon: "map", text: "Gestión de rutas de recolección" },
  { icon: "nature", text: "Análisis de impacto ambiental" },
]

const platforms = [
  { icon: "android", name: "Android" },
  { icon: "phone_iphone", name: "iOS" },
  { icon: "desktop_windows", name: "Windows (Nativo)" },
]

const downloadButtons = [
  { platform: "Android", icon: "android", color: "bg-green-500 hover:bg-green-600" },
  { platform: "iOS", icon: "phone_iphone", color: "bg-blue-500 hover:bg-blue-600" },
  { platform: "Windows", icon: "desktop_windows", color: "bg-gray-700 hover:bg-gray-800" },
]
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined:opsz,wght,FILL,GRAD@20..48,100..700,0..1,-50..200');

.material-symbols-outlined {
  font-variation-settings:
      'FILL' 0,
      'wght' 400,
      'GRAD' 0,
      'opsz' 48
}
</style>

