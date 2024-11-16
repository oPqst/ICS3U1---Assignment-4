<script setup>
import { ref } from 'vue';

const aSide = ref(0);
const bSide = ref(0);
const cAngle = ref(0);
const cSide = ref(0);

function cosineLaw() {
  const c = Math.sqrt(Math.pow(aSide.value, 2) + Math.pow(bSide.value, 2) - 2 * aSide.value * bSide.value * Math.cos(cAngle.value * Math.PI / 180));
  cSide.value = c.toFixed(5);
}
</script>

<template>
  <form @submit.prevent="cosineLaw()">
    <h1>Cosine Law Calculator</h1>
    <label>Side A:</label>
    <input v-model="aSide" type="number" />
    <label>Side B:</label>
    <input v-model="bSide" type="number" />
    <label>Angle C:</label>
    <input v-model="cAngle" type="number" />
    <label>Side C (Result)</label>
    <input v-model="cSide" type="number" readonly />
    <input type="submit" value="Calculate" A />
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