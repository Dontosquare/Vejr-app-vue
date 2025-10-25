<script setup>
import { ref } from 'vue';


const query = ref('');



</script>

<template>
    <form v-on:submit.prevent="onSubmitForm">
        <input v-model="city" v-on:keypress="fetchWeather" placeholder="Indtast by" />
        <button type="submit">Søg</button>
    </form>
</template>


<style scoped></style>