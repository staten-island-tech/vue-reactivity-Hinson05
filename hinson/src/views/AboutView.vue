<script setup>
import { ref } from "vue";

const awesome = ref(true);
const count = ref(0);

function toggle() {
  awesome.value = !awesome.value;
  count.value++;
}
</script>
<template>
  <div class="about">
    <h2>count is: {{ count }}</h2>
  </div>
  <button @click="toggle">purchase</button>
  <h1 v-if="awesome">Add item to cart</h1>
  <h1 v-else>Item Added</h1>
</template>
<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    align-items: center;
  }
}
</style>
