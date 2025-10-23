<script setup> 
import { ref } from 'vue';
const message = ref('Frontend projekt vejr app');
</script>

<template>
  <header>
    <input v-model="message" />
    <p>{{ message }}</p>
  </header>
</template>