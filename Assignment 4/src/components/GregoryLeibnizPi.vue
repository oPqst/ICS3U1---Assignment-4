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