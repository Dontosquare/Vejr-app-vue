<script setup>
import Header from './components/Header.vue'
import Input from './components/Input.vue'
import { ref } from 'vue';

const result = ref(null)

const apiKey = '73d60521ff71fd2cf36e01d86667d70d';
const city = '';
const url = `https://api.openweathermap.org/data/2.5/weather?q=${city}&appid=${apiKey}&units=metric&lang=da`;

fetch(url)
  .then(response => response.json())
  .then(data => {
    console.log(data);
    return { result }
  }) 
</script>

<template>
  <Header></Header>
  <hr />
  <Input></Input>
</template>

<style scoped>

</style>
