<template>
  <section class="mb-20 p-6 rounded-lg shadow-lg bg-white">
      <h2 class="text-3xl font-bold text-green-800 text-center mb-8">INCENTIVOS</h2>
      <p class="text-lg text-gray-700 text-center mb-12">¿Qué puedo hacer con mis puntos de reciclaje?</p>
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6">
        <div v-for="(incentive, index) in incentives" :key="index" class="bg-gradient-to-br from-green-600 to-green-800 rounded-lg shadow-lg p-6 flex flex-col items-center text-center">
          <div class="mb-4">
            <span class="material-symbols-outlined text-white" style="font-size: 48px;">
              {{ incentive.icon }}
            </span>
          </div>
          <h3 class="text-lg font-semibold mb-2 text-white">{{ incentive.title }}</h3>
          <p v-if="incentive.description" class="text-sm text-gray-300">{{ incentive.description }}</p>
          <p v-if="incentive.highlight" class="text-lg font-bold text-orange-500 mt-2">{{ incentive.highlight }}</p>
        </div>
      </div>
  </section>
</template>

<script>
export default {
  name: 'IncentivesSection',
  data() {
    return {
      incentives: [
        {
          icon: 'directions_car',
          title: 'DESCUENTOS PATENTE DE AUTOS',
          description: 'Posible acuerdo con municipalidades'
        },
        {
          icon: 'local_cafe',
          title: 'DESCUENTOS EN CAFETERIAS',
          description: 'Descuentos en cafeterías donde se ubicarán los prototipos'
        },
        {
          icon: 'checklist',
          title: 'HORAS EXTRACURRICULARES',
          description: 'Los principales interesados son los estudiantes',
          highlight: 'UNIVERSITARIOS'
        },
        {
          icon: 'group',
          title: 'PARTNER EXCHANGE',
          description: 'Cualquier otro tratado comercial con beneficio al usuario'
        }
      ]
    };
  }
}
</script>

<style scoped>
/* Puedes agregar estilos adicionales aquí si es necesario */
</style>
