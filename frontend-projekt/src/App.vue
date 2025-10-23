<script setup>
import Header from './components/Header.vue'
import Input from './components/Input.vue'
import { ref } from 'vue';

const result = ref(null)

fetch('73d60521ff71fd2cf36e01d86667d70d')
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
