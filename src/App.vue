<script setup lang="ts">
import { ref, onMounted, onUpdated } from "vue";

//  https://vuejs.org/api/composition-api-lifecycle

onMounted(() => {
  console.log("onMounted");
});

const counter = ref(0);

const increment = () => {
  counter.value++;
};

const decrement = () => {
  counter.value--;
};

onUpdated(() => {
  console.log("onUpdated");
});
</script>

<template>
  <div class="p-5">
    <h2>Vue 3 Reactivity API</h2>
    <hr />
    <p>Counter: {{ counter }}</p>

    <button class="btn btn-primary me-2" @click="increment">
      Increment (Setup)
    </button>
    <button class="btn btn-primary me-2" @click="decrement">
      Decrement (Setup)
    </button>
  </div>
</template>

<style scoped></style>
