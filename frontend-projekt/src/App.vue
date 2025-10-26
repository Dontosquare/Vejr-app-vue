<script setup>
import Header from './components/Header.vue'
 //import Input from './components/Input.vue'
// import Vejrtekst from './components/Vejrtekst.vue'
import { ref } from 'vue';

const result = ref(null)


const apiKey = import.meta.env.VITE_API_KEY;
const city = ref('');



const fetchWeather = async (event) => {
    if (event.key === 'Enter') {
        event.preventDefault();
        const response = await fetch(`https://api.openweathermap.org/data/2.5/weather?q=${city.value}&appid=${apiKey}&units=metric&lang=da`);
        result.value = await response.json();
        console.log(result.value);
    }
};

</script>

<template>
  <Header></Header>
  <hr />
  <form>
        <input v-model="city" v-on:keypress="fetchWeather" placeholder="Indtast by" />
        <button type="submit" >Søg</button>
    </form>
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
