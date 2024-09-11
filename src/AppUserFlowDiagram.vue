<template>
  <p class="text-green-800 mb-4">Este diagrama describe el flujo cotidiano de uso de la app, desde reciclar hasta canjear puntos acumulados en el contenedor o dejarlos para que otro usuario los canjee.</p>
  <pre class="mermaid text-green-800">
    graph TD
    A[Usuario recicla en el contenedor] --> B[Contenedor acumula puntos]
    B --> C{¿Usuario escanea el QR?}
    C -->|Sí| D[Recibe puntos en la app]
    C -->|No| E[Contenedor mantiene puntos acumulados]
    E --> F[Otro usuario puede escanear el QR y recibe los puntos acumulados]
    D --> G[Usuario canjea puntos por recompensas]
    F --> G
  </pre>
</template>


<script>
import mermaid from 'mermaid';

export default {
  name: 'AppUserFlowDiagram',
  mounted() {
    mermaid.initialize({startOnLoad: true});
    this.$nextTick(() => {
      mermaid.contentLoaded();
    });
  }
}
</script>

<style scoped>
/* Estilos adicionales si es necesario */
</style>
