<script setup>
import { ref } from 'vue';


</script>

<template>
    <form id="app">
        <input v-model="city" v-on:keypress="fetchWeather" placeholder="Indtast by" />
        <button type="submit">Søg</button>
    </form>
</template>


<style scoped></style>