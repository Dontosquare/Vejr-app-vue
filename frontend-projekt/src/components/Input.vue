<script setup>
import { ref } from 'vue';

const soegefterby = ref('');

const onSubmitForm = () => {
    console.log(soegefterby.value);
    todoList.value.push(soegefterby.value);
    soegefterby.value = '';
    console.table(soegefterby.value);
};
</script>

<template>
    <form v-on:submit.prevent="onSubmitForm">
        <input v-model="soegefterby" placeholder="Indtast by" />
        <button type="submit">Søg</button>
    </form>
</template>