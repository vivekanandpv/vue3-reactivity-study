<script lang="ts">
import { ref } from 'vue';

export default {
  setup() {
    const counter = ref(0);

    const increment = () => {
      counter.value++;
    }

    const decrement = () => {
      counter.value--;
    }

    return {
      counter,
      increment,
      decrement
    }
  },
  methods: {
    secondaryIncrement() {
      //  this.counter is a reactive property now
      //  It's not a wrapper anymore!
      this.counter++;
      // this.increment();  //  this too is possible
    }
  }
}
</script>

<template>
  <div class="p-5">
    <h2>Vue 3 Reactivity API</h2>
    <hr>
    <!-- bind directly to the wrapper -->
    <p>Counter: {{ counter }}</p>

    <button class="btn btn-primary me-2" @click="increment">Increment (Setup Export)</button>
    <button class="btn btn-primary me-2" @click="decrement">Decrement (Setup Export)</button>

    <!-- this too will work, but only in the template -->
    <button class="btn btn-primary me-2" @click="counter--">Decrement (Direct Template)</button>

    <!-- composition api way of handling events -->
    <button class="btn btn-primary me-2" @click="secondaryIncrement">Increment (Composition API)</button>
  </div>
</template>

<style scoped></style>
