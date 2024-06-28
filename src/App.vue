<!-- JS -->
<script>
/* IMPORTAZIONE DEL REF */
import { ref, reactive } from 'vue';

export default {
    name: 'NomeFile',

    /* LOGICA DEL COMPONENTE */
    setup() {

        /* VARIABILI REATTIVI GRAZIE AL REF UTILIZZATTO PRINCIPALMENTE PER STRINGHE, NUMERI, BOOLEANI, ARRAY */
        const message = ref('hello')
        const quantity = ref(1)

        /* MEDOTO REACTIVE USATO PRINCIPALMENTE PER GLI OGGETTO */
        const item = reactive({
            name: 'Product 1',
            price: 10
        })

        /* INCREMENTIAMO E DECREMENTIAMO , '.VALUE' = PER VEDERE IL VALORE CORRENTE DI QUANTITY */
        const increment = () => quantity.value++
        const decrement = () => quantity.value--

        /* FUNZIONE PER CAMBAIRE IL NOME E IL PREZZO DI ITEM */
        const swapProduct = () => {
            item.name = 'Product A'
            item.price = 30
        }

        /* RESTITUISCO PER VEDERE IN PAGINA */
        return {
            message,
            quantity,
            increment,
            decrement,
            item,
            swapProduct
        }
    }
};

</script>

<!-- HTML -->
<template>

    <!-- NOME E PREZZO DEL PRODOTTO -->
    <h1>{{ item.name }} : {{ item.price }}</h1>

    <!-- AL CLICK RICHIAMO LA FUNZIONE PER CAMBIARE I VALORI DI ITEM -->
    <button @click="swapProduct">Scambia Prodotto</button>

    <!-- NUMERO DI QUANTITA' -->
    <h2>{{ quantity }}</h2>

    <!-- INCREMENTO -->
    <button @click="increment"> + </button>

    <!-- DECREMENTO -->
    <button @click="decrement"> - </button>

</template>

<!-- CSS -->
<style scoped></style>
