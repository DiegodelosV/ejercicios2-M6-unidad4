<template>
  <section class="instrumentos">
    <ul>
      <li v-for="instrumento in instrumentos" :key="instrumento.nombre">
        {{ instrumento.nombre }}
        <button @click="$emit('eliminarInstrumento')">Eliminar</button>
      </li>
    </ul>
  </section>
</template>

<script>
export default {
  props: {
    instrumentos: Array,
  },
};
</script>

<style scoped>
</style>
