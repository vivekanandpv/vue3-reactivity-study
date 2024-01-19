<script setup lang="ts">
import { ref } from 'vue';
export interface Person {
  firstName: string;
  lastName: string;
}

//  wrapper, type-safe (TS), can also be used for complex types
//  but the unwrapping .value.x is required
const person = ref<Person>({
  firstName: 'Karan',
  lastName: 'Kumar'
});

const changeFirstName = () => {
  person.value.firstName = 'Tushar';
}
</script>

<template>
  <div class="p-5">
    <h2>Vue 3 Reactivity API</h2>
    <hr>
    <p>{{ person.firstName }} {{ person.lastName }}</p>
    <button class="btn btn-primary" @click="changeFirstName">Change First Name</button>
  </div>
</template>

<style scoped></style>
