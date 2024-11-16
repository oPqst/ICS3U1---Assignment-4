<script setup>
import CosineLaw from './components/CosineLaw.vue';
import AsymptoteFinder from './components/AsymptoteFinder.vue';
import GregoryLeibnizPi from './components/GregoryLeibnizPi.vue';
</script>

<template>
  <div class="container">
    <CosineLaw />
    <AsymptoteFinder />
    <GregoryLeibnizPi />
  </div>
</template>

<style scoped>
.container {
  font-family: monospace, sans-serif;
  display: flex;
  justify-content: center; 
  height: 100vh;
  flex-wrap: wrap;
  gap: 120px;
  padding: 40px;
}
</style>
