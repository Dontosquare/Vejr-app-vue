<script setup> 
import { ref } from 'vue';
const message = ref('Tjekvejret.dk');
</script>

<template>
  <header>
    <h1>{{ message }}</h1>
  </header>
</template>