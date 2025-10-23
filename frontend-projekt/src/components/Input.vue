<script setup>
import { ref } from 'vue';

const message = ref('Søg efter by');
</script>

<template>
    <div>
        <input v-model="message" />
    </div>

</template>