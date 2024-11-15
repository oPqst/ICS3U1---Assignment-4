<script setup>
import { ref } from 'vue';

const nValue = ref(0);
const piApprox = ref(0);

function piApproximator() {
    let pi = 0;
    for (let i = 0; i < nValue.value; i++) {
        pi += ((Math.pow((-1), i)) / ((2 * i) + 1));
    }
    piApprox.value = (pi * 4);
}
</script>

<template>
    <form @submit.prevent="piApproximator()">
        <h1>Gregory Pi Approximation</h1>
        <label>N Value:</label>
        <input v-model="nValue" type="number" />
        <label>Pi Approximation (Result)</label>
        <input v-model="piApprox" type="number" readonly />
        <input type="submit" value="Calculate" />
    </form>
</template>

<style scoped></style>