<template>
  <section class="mb-20 p-6 rounded-lg shadow-lg bg-white">
    <h2 class="text-2xl font-bold text-green-800 mb-4">Proceso de Uso del Contenedor Inteligente</h2>
    <p class="text-green-800 mb-4">Este diagrama describe el flujo de acciones del usuario al interactuar con un contenedor inteligente que incluye un limpiador a presión de vasos.</p>
    <pre class="mermaid text-green-800">
      graph LR
      A[Usuario coloca el vaso en el limpiador a presión] --> B[Vaso es limpiado]
      B --> C[Usuario inserta el vaso boca abajo en el tubo del contenedor]
      C --> D[Contenedor acumula puntos]
      D --> E{¿Usuario quiere canjear los puntos?}
      E -->|Sí| F[Usuario escanea el código QR]
      E -->|No| G[Puntos quedan acumulados en el contenedor]
    </pre>
  </section>
</template>

<script>
import mermaid from 'mermaid';

export default {
  name: 'MermaidDiagram',
  mounted() {
    mermaid.initialize({ startOnLoad: true });
    this.$nextTick(() => {
      mermaid.contentLoaded();
    });
  }
}
</script>

<style scoped>
/* Puedes agregar estilos adicionales si es necesario */
</style>
