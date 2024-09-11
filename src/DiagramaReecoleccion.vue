<template>
  <section class="mb-20 bg-white p-8 rounded-lg shadow-xl">
    <h2 class="text-3xl font-bold text-green-800 mb-6 text-center">Flujo de Recolección de Materiales</h2>
    <p class="text-green-800 mb-6 text-center">
      Este diagrama describe el flujo de recolección de materiales, en el cual
      <strong class="text-green-700">Eco Sense facilita el monitoreo y la incentivación</strong>,
      pero <strong class="text-red-500">no se encarga del proceso de reciclaje.</strong>
    </p>
    <div class="overflow-x-auto">
      <pre class="mermaid text-green-800 mx-auto">
        graph LR
        A[Usuario deposita material reciclable en el contenedor] --> B[Eco Sense registra datos del reciclaje]
        B --> C[Eco Sense actualiza la app con los datos]
        C --> D[Datos accesibles para el monitor - empresa/entidad recicladora]
        D --> E[Empresa recicladora recoge los materiales]
        E --> F[Empresa recicla los materiales]
        B --> G[Eco Sense incentiva a la población con recompensas]
      </pre>
    </div>
  </section>
</template>

<script>
import mermaid from 'mermaid';

export default {
  name: 'DiagramaRecoleccion',
  mounted() {
    mermaid.initialize({ startOnLoad: true });
    this.$nextTick(() => {
      mermaid.contentLoaded();
    });
  }
}
</script>

<style scoped>
/* Estilos adicionales si es necesario */
</style>
