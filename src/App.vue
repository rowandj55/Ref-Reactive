<script setup>
import {reactive, ref} from 'vue';

const clicks = ref(0);
const person = reactive({
    firstName: '',
    country: '',
});

function incrementClicks() {
    clicks.value++;
}

function changeCountry(newCountry) {
    person.country = newCountry;
}
</script>

<template>
    <button @click="incrementClicks">Klik mij!</button>

    <input v-model="person.firstName" placeholder="First Name" />
    <button @click="changeCountry('Nederland')">Nederland</button>
    <button @click="changeCountry('België')">België</button>

    <p>Hoi {{ person.firstName }}</p>
    <p>Je komt uit {{ person.country }}</p>
    <p>Je hebt {{ clicks }} keer op de knop geklikt.</p>
</template>
