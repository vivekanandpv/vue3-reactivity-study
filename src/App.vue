<script setup lang="ts">
import { reactive } from 'vue';

//  Better to declare the shape of the objects as interface
export interface Person {
  firstName: string;
  lastName: string;
  email: string;
}

//  No wrapper, directly reactive, type-safe (TS)
//  Doesn't work with primitives (number, string, boolean)
const person = reactive<Person>({
  firstName: 'Harish',
  lastName: 'S',
  email: 'harish@gmail.com'
});

//  No unwrapping
const changeFirstName = () => {
  person.firstName = 'Ramesh'
}
</script>

<template>
  <div class="p-5">
    <h2>Vue 3 Reactivity API</h2>
    <hr>
    <p>First Name: {{ person.firstName }}</p>
    <p>Last Name: {{ person.lastName }}</p>
    <p>Email: {{ person.email }}</p>


    <button class="btn btn-primary" @click="changeFirstName">Change First Name</button>
  </div>
</template>

<style scoped></style>
