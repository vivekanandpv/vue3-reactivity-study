<script setup lang="ts">
import { ref } from 'vue';

//  wrapper, type-safe (TS)
//  recommended for simple types: number, string, boolean
//  could also work with complex types
//  auto type inference
const counter = ref(0);

//  But unwrapping by .value.x is required
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

    <button class="btn btn-primary me-2" @click="increment">Increment (Setup)</button>
    <button class="btn btn-primary me-2" @click="decrement">Decrement (Setup)</button>

    <!-- this too will work, but only in the template -->
    <button class="btn btn-primary me-2" @click="counter--">Decrement (Template Direct)</button>
  </div>
</template>

<style scoped></style>
