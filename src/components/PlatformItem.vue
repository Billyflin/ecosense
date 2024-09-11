<template>
  <div class="text-center">
    <span class="material-symbols-outlined text-6xl text-green-600 mb-2">{{ icon }}</span>
    <p class="text-lg font-medium">{{ name }}</p>
  </div>
</template>

<script setup>
defineProps({
  icon: String,
  name: String
})
</script>
