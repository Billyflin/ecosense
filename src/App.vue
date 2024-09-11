<template>
  <div class="min-h-screen bg-gradient-to-b from-green-50 to-green-100">
    <header class="bg-white shadow-md">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-4 flex justify-between items-center">
        <img
            src="https://hebbkx1anhila5yf.public.blob.vercel-storage.com/EcoSenseLogo-DHVwhz2SZjI9llKKwW9GgqxFEIykwO.svg"
            alt="Logo de EcoSense"
            class="w-48"
        />
        <nav>
          <ul class="flex space-x-4">
            <li><a href="#about" class="text-green-600 hover:text-green-800">Acerca de</a></li>
            <li><a href="#features" class="text-green-600 hover:text-green-800">Características</a></li>
            <li><a href="#download" class="text-green-600 hover:text-green-800">Descargar</a></li>
          </ul>
        </nav>
      </div>
    </header>

    <main class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-12">
      <section id="about" class="mb-16">
        <h2 class="text-3xl font-bold text-green-800 mb-6">Acerca de EcoSense</h2>
        <div class="grid gap-8 md:grid-cols-2">
          <div class="bg-white shadow-md rounded-lg overflow-hidden">
            <div class="p-6">
              <h3 class="text-xl font-semibold mb-2">Recolector Inteligente de Vasos de Café</h3>
              <p class="text-gray-600 mb-4">Solución innovadora para la gestión de residuos</p>
            </div>
            <div class="h-64 bg-gray-100">
              <three-model></three-model>
            </div>
          </div>
          <div class="bg-white shadow-md rounded-lg p-6">
            <h3 class="text-xl font-semibold mb-4">Características Principales</h3>
            <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
              <div class="flex items-start">
                <span class="material-icons text-green-500 mr-2">sensors</span>
                <div>
                  <h4 class="font-medium">Sensores de nivel</h4>
                  <p class="text-sm text-gray-600">Monitoreo preciso del llenado</p>
                </div>
              </div>
              <div class="flex items-start">
                <span class="material-icons text-green-500 mr-2">wifi</span>
                <div>
                  <h4 class="font-medium">Conectividad LoRa</h4>
                  <p class="text-sm text-gray-600">Transmisión eficiente de datos</p>
                </div>
              </div>
              <div class="flex items-start">
                <span class="material-icons text-green-500 mr-2">design_services</span>
                <div>
                  <h4 class="font-medium">Diseño ergonómico</h4>
                  <p class="text-sm text-gray-600">Fácil uso para todos los usuarios</p>
                </div>
              </div>
              <div class="flex items-start">
                <span class="material-icons text-green-500 mr-2">local_cafe</span>
                <div>
                  <h4 class="font-medium">Capacidad optimizada</h4>
                  <p class="text-sm text-gray-600">Diseñado para vasos de café</p>
                </div>
              </div>
              <div class="flex items-start">
                <span class="material-icons text-green-500 mr-2">battery_charging_full</span>
                <div>
                  <h4 class="font-medium">Batería de larga duración</h4>
                  <p class="text-sm text-gray-600">Litio con configuración 3s6p</p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>

      <section id="features" class="mb-16">
        <h2 class="text-3xl font-bold text-green-800 mb-6">Cómo Funciona</h2>
        <div class="bg-white shadow-md rounded-lg p-6">
          <div class="flex flex-wrap justify-center items-center gap-4">
            <div class="flex flex-col items-center text-center w-40">
              <span class="material-icons text-4xl text-green-600 mb-2">recycling</span>
              <h3 class="font-semibold mb-1">Recolector Inteligente</h3>
              <p class="text-sm text-gray-600">Recopila datos de uso y llenado</p>
            </div>
            <div class="flex flex-col items-center">
              <span class="material-icons text-gray-400">arrow_forward</span>
              <span class="text-xs text-gray-500">LoRa</span>
            </div>
            <div class="flex flex-col items-center text-center w-40">
              <span class="material-icons text-4xl text-green-600 mb-2">router</span>
              <h3 class="font-semibold mb-1">Gateway LoRa</h3>
              <p class="text-sm text-gray-600">Recibe datos de múltiples recolectores</p>
            </div>
            <div class="flex flex-col items-center">
              <span class="material-icons text-gray-400">arrow_forward</span>
              <span class="text-xs text-gray-500">Internet</span>
            </div>
            <div class="flex flex-col items-center text-center w-40">
              <span class="material-icons text-4xl text-green-600 mb-2">dns</span>
              <h3 class="font-semibold mb-1">Servidor Central</h3>
              <p class="text-sm text-gray-600">Procesa y agrega datos</p>
            </div>
            <div class="flex flex-col items-center">
              <span class="material-icons text-gray-400">arrow_forward</span>
              <span class="text-xs text-gray-500">API</span>
            </div>
            <div class="flex flex-col items-center text-center w-40">
              <span class="material-icons text-4xl text-green-600 mb-2">cloud_upload</span>
              <h3 class="font-semibold mb-1">Firebase</h3>
              <p class="text-sm text-gray-600">Almacena y distribuye información</p>
            </div>
            <div class="flex flex-col items-center">
              <span class="material-icons text-gray-400">arrow_forward</span>
              <span class="text-xs text-gray-500">SDK</span>
            </div>
            <div class="flex flex-col items-center text-center w-40">
              <span class="material-icons text-4xl text-green-600 mb-2">devices</span>
              <h3 class="font-semibold mb-1">App EcoSense</h3>
              <p class="text-sm text-gray-600">Interfaz para usuarios y administradores</p>
            </div>
          </div>
        </div>
      </section>

      <section class="mb-16">
        <h2 class="text-3xl font-bold text-green-800 mb-6">Aplicación EcoSense</h2>
        <div>
          <div class="grid w-full grid-cols-2">
            <button @click="selectedTab = 'user'" :class="[
              'p-4 transition-colors duration-200',
              selectedTab === 'user' ? 'bg-green-500 text-white' : 'bg-gray-200 text-gray-700 hover:bg-green-100'
            ]">
              Funciones de Usuario
            </button>
            <button @click="selectedTab = 'admin'" :class="[
              'p-4 transition-colors duration-200',
              selectedTab === 'admin' ? 'bg-green-500 text-white' : 'bg-gray-200 text-gray-700 hover:bg-green-100'
            ]">
              Funciones de Administrador
            </button>
          </div>
          <div v-if="selectedTab === 'user'" class="bg-white shadow-md rounded-lg p-6 mt-4">
            <h3 class="flex items-center text-xl font-semibold mb-4">
              <span class="material-icons mr-2 text-green-500">person</span>
              Funcionalidades para Usuarios
            </h3>
            <ul class="space-y-3">
              <li class="flex items-start">
                <span class="material-icons text-green-500 mr-2">star</span>
                <span>Ver puntuación actual de reciclaje</span>
              </li>
              <li class="flex items-start">
                <span class="material-icons text-green-500 mr-2">redeem</span>
                <span>Lista de beneficios obtenidos</span>
              </li>
              <li class="flex items-start">
                <span class="material-icons text-green-500 mr-2">history</span>
                <span>Historial personal de reciclaje</span>
              </li>
              <li class="flex items-start">
                <span class="material-icons text-green-500 mr-2">eco</span>
                <span>Consejos para reducir el uso de desechables</span>
              </li>
            </ul>
          </div>
          <div v-if="selectedTab === 'admin'" class="bg-white shadow-md rounded-lg p-6 mt-4">
            <h3 class="flex items-center text-xl font-semibold mb-4">
              <span class="material-icons mr-2 text-green-500">admin_panel_settings</span>
              Panel de Administración
            </h3>
            <ul class="space-y-3">
              <li class="flex items-start">
                <span class="material-icons text-green-500 mr-2">monitoring</span>
                <span>Monitoreo en tiempo real de los recolectores</span>
              </li>
              <li class="flex items-start">
                <span class="material-icons text-green-500 mr-2">analytics</span>
                <span>Estadísticas de uso y eficiencia</span>
              </li>
              <li class="flex items-start">
                <span class="material-icons text-green-500 mr-2">map</span>
                <span>Gestión de rutas de recolección</span>
              </li>
              <li class="flex items-start">
                <span class="material-icons text-green-500 mr-2">nature</span>
                <span>Análisis de impacto ambiental</span>
              </li>
            </ul>
          </div>
        </div>
      </section>

      <section id="download" class="mb-16">
        <h2 class="text-3xl font-bold text-green-800 mb-6">Plataformas Soportadas</h2>
        <div class="bg-white shadow-md rounded-lg p-6">
          <div class="flex justify-center space-x-8">
            <div class="text-center">
              <span class="material-icons text-5xl text-green-600">android</span>
              <p>Android</p>
            </div>
            <div class="text-center">
              <span class="material-icons text-5xl text-blue-500">phone_iphone</span>
              <p>iOS</p>
            </div>
            <div class="text-center">
              <span class="material-icons text-5xl text-gray-700">desktop_windows</span>
              <p>Windows (Nativo)</p>
            </div>
          </div>
        </div>
      </section>

      <section class="text-center">
        <h2 class="text-3xl font-bold text-green-800 mb-4">¡Únete a EcoSense Hoy!</h2>
        <p class="mb-6 text-lg text-green-600">Descarga la aplicación y sé parte del cambio hacia un campus más sostenible.</p>
        <div class="flex flex-wrap justify-center gap-4">
          <button class="bg-green-500 hover:bg-green-600 text-white py-3 px-6 rounded-lg flex items-center transition-colors duration-200 transform hover:scale-105">
            <span class="material-icons mr-2">android</span>
            Descargar para Android
          </button>
          <button class="bg-blue-500 hover:bg-blue-600 text-white py-3 px-6 rounded-lg flex items-center transition-colors duration-200 transform hover:scale-105">
            <span class="material-icons mr-2">phone_iphone</span>
            Descargar para iOS
          </button>
          <button class="bg-gray-700 hover:bg-gray-800 text-white py-3 px-6 rounded-lg flex items-center transition-colors duration-200 transform hover:scale-105">
            <span class="material-icons mr-2">desktop_windows</span>
            Descargar para Windows
          </button>
        </div>
      </section>
    </main>

    <footer class="bg-green-800 text-white py-8">
      <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="flex flex-col md:flex-row justify-between items-center">
          <div class="mb-4 md:mb-0">
            <img
                src="https://hebbkx1anhila5yf.public.blob.vercel-storage.com/EcoSenseLogoBlanco-vqrjUQ4yuYgXlXn5r14s2BXzsYxs8l.svg"
                alt="Logo de EcoSense"
                class="w-36 mb-2"
            />
            <p>&copy; 2023 EcoSense. Todos los derechos reservados.</p>
          </div>
          <div>
            <a href="https://github.com/Billyflin/UfroSustentableApp" target="_blank" rel="noopener noreferrer" class="text-white hover:text-green-200 transition-colors flex items-center">
              <span class="material-icons mr-2">code</span>
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
import ThreeModel from "./components/ThreeModel.vue";

const selectedTab = ref('user')
</script>

<style>
@import url('https://fonts.googleapis.com/icon?family=Material+Icons');
</style>