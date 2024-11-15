<script setup>
import { ref } from 'vue';

const aSide = ref(0);
const bSide = ref(0);
const cAngle = ref(0);
const cSide = ref(0);

function cosineLaw() {
  const c = Math.sqrt(aSide.value * aSide.value + bSide.value * bSide.value - 2 * aSide.value * bSide.value * Math.cos(cAngle.value * (Math.PI / 180)));
  cSide.value = c.toFixed(2);
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

<style scoped></style>