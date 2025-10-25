<script setup>
import Header from './components/Header.vue'
import Input from './components/Input.vue'
import { ref } from 'vue';

const result = ref(null)


const apiKey = import.meta.env.TOKEN;
let city = ref('');


const fetchWeather = async (e) => {
  if (e.key == 'Enter') {
    const url = `https://api.openweathermap.org/data/2.5/weather?q=${city}&appid=${apiKey}&units=metric&lang=da`;

    try {
      const response = await fetch(url);
      const data = await response.json();
      console.log(data);
      result.value = data;
    } catch (error) {
      console.error('Fejl i søgning:', error);
    }
  }
};


</script>

<template>
  <Header></Header>
  <hr />
  <form id="app">
        <input v-model="city" v-on:keypress="fetchWeather" placeholder="Indtast by" />
        <button type="submit">Søg</button>
    </form>
</template>

<style scoped>

</style>
