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






      <section class="mb-20">
        <h2 class="text-4xl font-bold text-green-800 mb-8 text-center">Nuestra Elección: Reciclaje de Vasos de Café</h2>
        <div class="bg-white shadow-lg rounded-xl p-8">
          <p class="text-lg text-gray-700 mb-6">
            En EcoSense, decidimos centrar nuestro primer esfuerzo de reciclaje en los vasos de café. A pesar de que otras opciones como el aceite o las baterías pueden parecer más urgentes en algunos aspectos, optamos por los vasos de café debido al desafío que presenta en términos de innovación. Este reto nos permite no solo implementar una solución efectiva, sino también desarrollar y probar nuevas estrategias de reciclaje que puedan ser adaptadas a otros materiales en el futuro.
          </p>
          <h3 class="text-2xl font-semibold text-green-700 mb-4">Matriz de Valor</h3>
          <div class="overflow-x-auto">
            <table class="min-w-full bg-white border border-gray-300 rounded-lg overflow-hidden">
              <thead class="bg-green-200 text-green-800">
              <tr>
                <th class="py-3 px-6 text-left">Criterio</th>
                <th class="py-3 px-6 text-center">Vasos de Café</th>
                <th class="py-3 px-6 text-center">Aceite</th>
                <th class="py-3 px-6 text-center">Baterías</th>
              </tr>
              </thead>
              <tbody>
              <tr v-for="(row, index) in matrixData" :key="index" class="odd:bg-gray-50 even:bg-gray-100">
                <td class="py-3 px-6 text-left font-medium text-gray-700">{{ row.criteria }}</td>
                <td class="py-3 px-6 text-center" :class="getScoreClass(row.coffee)">{{ row.coffee }}</td>
                <td class="py-3 px-6 text-center" :class="getScoreClass(row.oil)">{{ row.oil }}</td>
                <td class="py-3 px-6 text-center" :class="getScoreClass(row.batteries)">{{ row.batteries }}</td>
              </tr>
              <tr class="bg-blue-100 text-blue-800 font-semibold">
                <td class="py-3 px-6 text-center">Resultado Total</td>
                <td class="py-3 px-6 text-center">{{ totalScores.coffee }}</td>
                <td class="py-3 px-6 text-center">{{ totalScores.oil }}</td>
                <td class="py-3 px-6 text-center">{{ totalScores.batteries }}</td>
              </tr>
              </tbody>
            </table>
          </div>
          <p class="text-sm text-gray-600 mt-4">Escala: 1 (Bajo) - 3 (Alto)</p>
          <div class="mt-6">
            <h4 class="text-xl font-semibold text-green-700 mb-2">¿Por qué empezamos con vasos de café?</h4>
            <ul class="list-disc list-inside space-y-2 text-gray-700">
              <li>Alta frecuencia de uso en el campus universitario</li>
              <li>Facilidad de implementación y recolección</li>
              <li>Impacto visual inmediato en la comunidad</li>
              <li>Reto significativo en términos de innovación, impulsando nuevas estrategias de reciclaje</li>
            </ul>
          </div>
          <div class="mt-6">
            <h4 class="text-xl font-semibold text-green-700 mb-2">Planes Futuros</h4>
            <p class="text-gray-700">
              Aunque comenzamos con vasos de café, nuestro objetivo es expandir el ecosistema de reciclaje para incluir aceite y baterías en el futuro. Esto nos permitirá abordar una gama más amplia de desafíos de sostenibilidad y maximizar nuestro impacto positivo en el medio ambiente.
            </p>
          </div>
        </div>
      </section>


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

      <section class="mb-20">
        <h2 class="text-4xl font-bold text-green-800 mb-8 text-center">Eco Sense App(ex Ufro Sustentable)</h2>
        <div class="bg-white shadow-lg rounded-xl p-8">
          <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
            <!-- App Features and Technologies -->
            <div>
              <h3 class="text-2xl font-semibold text-green-700 mb-4">Características y Tecnologías</h3>
              <ul class="space-y-4">
                <li v-for="item in appInfo" :key="item.title" class="flex items-start">
                  <span class="material-symbols-outlined text-green-600 mr-3">{{ item.icon }}</span>
                  <div>
                    <h4 class="font-medium text-lg">{{ item.title }}</h4>
                    <p class="text-sm text-gray-600">{{ item.description }}</p>
                  </div>
                </li>
              </ul>
            </div>

            <!-- App Screenshots -->
            <div>
              <h3 class="text-2xl font-semibold text-green-700 mb-4">Vistas de la App</h3>
              <div class="relative">
                <div class="overflow-hidden rounded-lg">
                  <div class="flex transition-transform duration-300 ease-in-out" :style="{ transform: `translateX(-${currentSlide * 100}%)` }">
                    <div v-for="(screenshot, index) in appScreenshots" :key="index" class="w-full flex-shrink-0">
                      <div class="relative w-full max-h-[600px] aspect-[9/16] bg-gray-200 rounded-lg overflow-hidden">
                        <img
                            :src="screenshot.image"
                            :alt="screenshot.alt"
                            class="w-full h-full object-contain object-center rounded-lg shadow-md"
                        >
                      </div>
                      <p class="mt-2 text-center text-sm text-gray-600">{{ screenshot.description }}</p>
                    </div>
                  </div>
                </div>
                <button @click="prevSlide" class="absolute left-0 top-1/2 transform -translate-y-1/2 bg-white bg-opacity-50 rounded-full p-2 shadow-md">
                  <span class="material-symbols-outlined">chevron_left</span>
                </button>
                <button @click="nextSlide" class="absolute right-0 top-1/2 transform -translate-y-1/2 bg-white bg-opacity-50 rounded-full p-2 shadow-md">
                  <span class="material-symbols-outlined">chevron_right</span>
                </button>
              </div>
            </div>
          </div>
        </div>
      </section>

      <section class="mb-20">
        <h2 class="text-4xl font-bold text-green-800 mb-8 text-center">Metas</h2>
        <div class="bg-white shadow-lg rounded-xl p-8">
          <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-2 gap-8">
            <div v-for="indicator in studyIndicators" :key="indicator.title" class="bg-green-50 rounded-lg p-6 shadow-md transition-transform duration-300 hover:scale-105">
              <div class="flex items-center justify-center mb-4">
                <span class="material-symbols-outlined text-5xl text-green-600">{{ indicator.icon }}</span>
              </div>
              <h3 class="text-2xl font-bold text-green-800 text-center mb-2">{{ indicator.value }}</h3>
              <p class="text-lg text-green-700 text-center mb-4">{{ indicator.title }}</p>
              <p class="text-sm text-gray-600 text-center">{{ indicator.description }}</p>
            </div>
          </div>
          <div class="mt-8">
            <h3 class="text-2xl font-semibold text-green-700 mb-4">Impacto Ambiental Estimado</h3>
            <div class="bg-green-50 rounded-lg p-6 shadow-md">
              <div class="flex flex-wrap justify-around">
                <div v-for="impact in environmentalImpact" :key="impact.title" class="text-center mb-4">
                  <p class="text-3xl font-bold text-green-800">{{ impact.value }}</p>
                  <p class="text-lg text-green-700">{{ impact.title }}</p>
                </div>
              </div>
            </div>
          </div>
          <p class="text-sm text-gray-600 mt-4 text-center">
            *Cada vaso de papel pesa en promedio 11 gramos y genera aproximadamente 0.06 kg de CO2 durante su ciclo de vida. Datos basados en estudios del informe de la <a href="https://www.lifecycleinitiative.org/wp-content/uploads/2021/02/UNEP_-LCA-Beverage-Cups-Report_Web.pdf" class="text-blue-500 underline">UNEP Life Cycle Initiative</a> y <a href="https://www.sierraclub.org" class="text-blue-500 underline">Sierra Club</a>.
          </p>
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
            <p class="text-lg">&copy; 2024 EcoSense. Sin derechos.</p>
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
import {computed, ref} from 'vue'
import ThreeModel from "./components/ThreeModel.vue"
import FeatureItem from "./components/FeatureItem.vue"
import ProcessStep from "./components/ProcessStep.vue"
import PlatformItem from "./components/PlatformItem.vue"
import DownloadButton from "./components/DownloadButton.vue"


const studyIndicators = [
  {
    icon: "recycling",
    value: "15,000+",
    title: "Vasos Reciclados",
    description: "Número de vasos de café reciclados desde el inicio del programa"
  },
  {
    icon: "group",
    value: "18%",
    title: "Participación Estudiantil",
    description: "Porcentaje de estudiantes que han utilizado el sistema al menos una vez"
  },
  {
    icon: "trending_up",
    value: "35%",
    title: "Aumento en Reciclaje",
    description: "Incremento en la tasa general de reciclaje en el campus"
  },
  {
    icon: "eco",
    value: "5",
    title: "Nuevos Puntos de Reciclaje",
    description: "Puntos de recolección adicionales instalados debido a la alta demanda"
  },
]

const environmentalImpact = [
  {
    value: "0.9 toneladas",
    title: "CO₂ Evitado"
  },
  {
    value: "165 kg",
    title: "Papel No Producido"
  },
  {
    value: "8 Vasos Diarios",
    title: "Para lograr objetivo anual"
  }
]


const currentSlide = ref(0)
const selectedTab = ref('user')

const totalScores = computed(() => {
  return {
    coffee: matrixData.reduce((sum, row) => sum + row.coffee, 0),
    oil: matrixData.reduce((sum, row) => sum + row.oil, 0),
    batteries: matrixData.reduce((sum, row) => sum + row.batteries, 0)
  };
});

const matrixData = [
  { criteria: "Frecuencia de uso", coffee: 3, oil: 2, batteries: 1 },
  { criteria: "Facilidad de implementación", coffee: 1, oil: 2, batteries: 3 },
  { criteria: "Impacto ambiental", coffee: 1, oil: 2, batteries: 3 },
  { criteria: "Visibilidad en el campus", coffee: 3, oil: 1, batteries: 2 },
  // Nuevas filas basadas en la tabla
  { criteria: "Volumen", coffee: 2, oil: 1, batteries: 3 },
  { criteria: "Facilidad de recolección", coffee: 1, oil: 2, batteries: 3 },
  { criteria: "Costo de construcción(menor costo)", coffee: 2, oil: 1, batteries: 3 },
  { criteria: "Innovación", coffee: 3, oil: 2, batteries: 1 },
  { criteria: "Transporte", coffee: 1, oil: 2, batteries: 3 }
];


const getScoreClass = (score) => {
  if (score === 3) return 'bg-green-100'
  if (score === 2) return 'bg-yellow-100'
  return 'bg-red-100'
}

const appInfo = [
  { icon: "login", title: "Inicio de sesión con Google", description: "Autenticación segura con cuentas de Google" },
  { icon: "map", title: "Mapa interactivo", description: "Localiza puntos de reciclaje en el campus" },
  { icon: "qr_code_scanner", title: "Escáner QR", description: "Registra actividades de reciclaje" },
  { icon: "history", title: "Historial de solicitudes", description: "Seguimiento de tus actividades de reciclaje" },
  { icon: "redeem", title: "Recompensas", description: "Canjea puntos por premios" },
  { icon: "person", title: "Perfil personalizable", description: "Ajusta la apariencia de la app" },
  { icon: "code", title: "Kotlin Multiplatform", description: "Desarrollo multiplataforma para Android e iOS" },
  { icon: "cloud", title: "Firebase", description: "Backend robusto y en tiempo real" },
  { icon: "palette", title: "Material Design 3", description: "Interfaz moderna y consistente" },
  { icon: "view_quilt", title: "Jetpack Compose", description: "UI declarativa y eficiente" }
]

const appScreenshots = [
  {
    image: "https://hebbkx1anhila5yf.public.blob.vercel-storage.com/image-uupsza4XpOcOfwgUnpS502CSbdEYmV.png",
    alt: "Mapa de puntos de reciclaje en el campus",
    description: "Localiza fácilmente los puntos de reciclaje en todo el campus universitario"
  },
  {
    image: "https://hebbkx1anhila5yf.public.blob.vercel-storage.com/image-9mS4p2XXxuO7A2r7s7FatjpEGkRFfk.png",
    alt: "Historial de solicitudes de reciclaje",
    description: "Mantén un registro detallado de tus actividades de reciclaje y contribuciones"
  },
  {
    image: "https://hebbkx1anhila5yf.public.blob.vercel-storage.com/image-tkAzqI4BxjqVFyD5lnEkoH1hmGdgDP.png",
    alt: "Pantalla de puntos y recompensas",
    description: "Visualiza tus puntos acumulados y canjea premios por tus esfuerzos de reciclaje"
  },
  {
    image: "https://hebbkx1anhila5yf.public.blob.vercel-storage.com/image-TrcpSoEzLVv3k6F8zlX9uWm4f6KqFX.png",
    alt: "Demostración de realidad aumentada",
    description: "Reconocimiento Qr por camara"
  },
  {
    image: "https://hebbkx1anhila5yf.public.blob.vercel-storage.com/image-sduPIKrzelDDgMZ5Ag3U16VonEicSV.png",
    alt: "Perfil de usuario y configuración de accesibilidad",
    description: "Personaliza tu experiencia con opciones de contraste y modo oscuro"
  },
]

const nextSlide = () => {
  currentSlide.value = (currentSlide.value + 1) % appScreenshots.length
}

const prevSlide = () => {
  currentSlide.value = (currentSlide.value - 1 + appScreenshots.length) % appScreenshots.length
}


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

const navItems = [
  { href: "#about", text: "Acerca de" },
  { href: "#features", text: "Características" },
  { href: "#download", text: "Descargar" },
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

