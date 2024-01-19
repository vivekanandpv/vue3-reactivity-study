<script setup lang="ts">
import { ref } from 'vue';

//  wrapper, type-safe (TS), recommended for simple types: number, string, boolean
const counter = ref(0);

const increment = () => {
  counter.value++;
}

const decrement = () => {
  counter.value--;
}
</script>

<template>
  <div class="p-5">
    <h2>Vue 3 Reactivity API</h2>
    <hr>
    <!-- bind directly to the wrapper -->
    <p>Counter: {{ counter }}</p>

    <button class="btn btn-primary me-2" @click="increment">increment</button>
    <button class="btn btn-primary me-2" @click="decrement">Decrement</button>

    <!-- this too will work, but only in the template -->
    <button class="btn btn-primary me-2" @click="counter--">Decrement</button>
  </div>
</template>

<style scoped></style>
