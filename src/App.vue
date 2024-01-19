<script lang="ts">
import { reactive } from 'vue';
export interface Person {
  firstName: string;
  lastName: string;
  email: string;
}

export default {
  setup() {
    //  wrapper, type-safe (TS), only for simple types: number, string, boolean
    const person = reactive<Person>({
      firstName: 'Harish',
      lastName: 'S',
      email: 'harish@gmail.com'
    });

    const changeFirstName = () => {
      person.firstName = 'Ramesh'
    }

    return {
      person,
      changeFirstName
    }
  }
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
