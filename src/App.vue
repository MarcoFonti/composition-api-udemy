<!-- JS -->
<script>
/* IMPORTAZIONE DEL REF */
import { ref } from 'vue';

export default {
    name: 'NomeFile',

    /* LOGICA DEL COMPONENTE */
    setup() {

        /* VARIABILI REATTIVI GRAZIE AL REF */
        const message = ref('hello')
        const quantity = ref(1)

        /* INCREMENTIAMO E DECREMENTIAMO , '.VALUE' = PER VEDERE IL VALORE CORRENTE DI QUANTITY */
        const increment = () => quantity.value++
        const decrement = () => quantity.value--

        /* RESTITUISCO PER VEDERE IN PAGINA */
        return {
            message,
            quantity,
            increment,
            decrement
        }
    }
};

</script>

<!-- HTML -->
<template>

    <!-- MESSAGGIO -->
    <h1>{{ message }}</h1>

    <!-- NUMERO DI QUANTITA' -->
    <h2>{{ quantity }}</h2>

    <!-- INCREMENTO -->
    <button @click="increment"> + </button>

    <!-- DECREMENTO -->
    <button @click="decrement"> - </button>

</template>

<!-- CSS -->
<style scoped></style>
