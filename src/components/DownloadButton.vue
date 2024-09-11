<template>
  <button :class="['py-3 px-6 rounded-lg flex items-center transition-all duration-300 transform hover:scale-105 text-white', color]">
    <span class="material-symbols-outlined mr-2">{{ icon }}</span>
    Descargar para {{ platform }}
  </button>
</template>

<script setup>
defineProps({
  platform: String,
  icon: String,
  color: String
})
</script>
