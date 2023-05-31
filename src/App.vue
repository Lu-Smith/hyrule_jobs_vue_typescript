<template>
  <div class="app">
    <h1>{{ name }} - {{  age }}</h1>
    <button @click="changeName('Zelda')">change name</button>
    <button @click="changeAge(30)">change age</button>
  </div>
</template>

<script lang="ts">

import { defineComponent } from 'vue';

export default defineComponent({
  name: 'App',
  components: {

  },
  data() {
    return {
      name: 'Hyrule Jobs',
      age: 25 as number | string
    }
  },
  methods: {
    changeName(name: string) {
      this.name = name

      return name
    },
    changeAge(age: string | number) {
      this.age = age
      
      return age
    }
  }
});
</script>

<style>

</style>
