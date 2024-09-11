<template>
  <div class="flex items-start">
    <span class="material-symbols-outlined text-green-500 mr-3 text-2xl">{{ icon }}</span>
    <div>
      <h4 class="font-medium text-lg">{{ title }}</h4>
      <p class="text-sm text-gray-600">{{ description }}</p>
    </div>
  </div>
</template>

<script setup>
defineProps({
  icon: String,
  title: String,
  description: String
})
</script>
