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
        const asymTypes = ["Linear", "Quadratic", "Cubic", "Quartic", "Quintic", "Sextic", "Septic", "Octic", "Nonic", "Decic"];
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

<style scoped>
form {
    background-color: white;
    border-radius: 8px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.153);
    padding: 20px;
    width: 350px;

    text-align: center;
}

label {
    display: block;
    font-size: 14px;
    margin: 10px;
    text-align: left;
    color: #333;
    font-weight: bold;
}

input {
    width: 100%;
    padding: 8px;
    margin-bottom: 15px;
    border: 1px solid gray;
    border-radius: 4px;
    font-size: 16px;
}

input[type="submit"] {
    width: 100%;
    padding: 10px;
    background-color: #007bff;
    color: white;
    border: none;
    border-radius: 4px;
    font-size: 16px;
    cursor: pointer;
    transition: background-color 0.3s ease;
}

input[type="submit"]:hover {
    background-color: #0056b3;
}

input[readonly] {
    background-color: #f0f0f0;
    color: #666;
}
</style>