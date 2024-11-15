<script setup>
import { ref } from 'vue';

const mValue = ref(0);
const nValue = ref(0);
const asymType = ref("");

function asymptoteFinder() {
    if (mValue.value === nValue.value) {
        asymType.value = "Asymptote is Horizontal";
    } else if (mValue.value < nValue.value) {
        asymType.value = "The asymptote is the x-axis";
    } else if (mValue.value > nValue.value) {
        const asymTypes = ["Linear", "Quadratic", "Cubic", "Quartic", "Quintic",
            "Sextic", "Septic", "Octic", "Nonic", "Decic"];
        asymType.value = "The asymptote is " + asymTypes[mValue.value - nValue.value - 1];
    } else {
        asymType.value = "Error - Please try again!";
    }
}
</script>

<template>
    <form @submit.prevent="asymptoteFinder()">
        <h1>Asymptote Type Finder</h1>
        <label>M Value:</label>
        <input v-model="mValue" type="number" />
        <label>N Value:</label>
        <input v-model="nValue" type="number" />
        <label>Asymptote Type (Result)</label>
        <input v-model="asymType" readonly />
        <input type="submit" value="Calculate" />
    </form>
</template>

<style scoped></style>