<template>
  <div class="app">
    <h1>{{ name }}</h1>
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
      name: 'Hyrule Jobs'
    }
  }
});
</script>

<style>

</style>
