<template>
    <div>
        Navbar : {{ (2 + 2) }}<br />
        Return string: {{ returnString() }}<br />
        Show text: <span v-if="showText">Depending of condition!</span><br />
        <button @click="toggleText()">Show text above!</button>
    </div>
    <div v-for="data in dataObjectArray" :key="data.title">
        <span>{{ data.title }}</span><br />
        <span>{{ data.description }}</span><br />
        <span>{{ data.content }}</span><br />
    </div>
    <div v-bind:class="[changeBackground ? 'background-1' : 'background-2']">
        <button @click="changeColor()">Change color</button>
    </div>
</template>
<script setup>
import { ref } from 'vue';

const stringReturned = ref('Hola');
let showText = ref(false);
let changeBackground = ref(false);
const dataObjectArray = [{ title: 'Titulo1', description: 'Descripcion1', content: 'Contenido1' },
{ title: 'Titulo2', description: 'Descripcion2', content: 'Contenido2' },
{ title: 'Titulo3', description: 'Descripcion3', content: 'Contenido3' },]

function returnString() {
    return 'Hi, this is a string returned by a function'
}
function toggleText() {
    showText.value = !showText.value;
}
function changeColor() {
    changeBackground.value = !changeBackground.value
}
</script>
<style>
.background-1 {
    background-color: aqua;
}

.background-2 {
    background-color: blueviolet;
}
</style>