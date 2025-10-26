<script setup>

</script>

<template>
  <div v-if="result">
      <h2>{{ result.name }}, {{ result.sys.country }}</h2>
      <p>Temperatur: {{ result.main.temp }} °C</p>
      <p>Vejr: {{ result.weather[0].description }}</p>
      <p>Luftfugtighed: {{ result.main.humidity }}%</p>
      <p>Vindhastighed: {{ result.wind.speed }} m/s</p>
  </div>  
</template>

<style scoped>

</style>
