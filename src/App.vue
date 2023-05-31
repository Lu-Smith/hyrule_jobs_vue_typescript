<template>
  <div class="app">
    <h1>{{ jobs }}</h1>
  </div>
</template>

<script lang="ts">

import { defineComponent, ref} from 'vue';
import Job from './types/Job'

export default defineComponent({
  name: 'App',
  components: {

  },
  setup() {
    const jobs = ref<Job[]>([{
      title: 'accountant', location: 'Edinburgh', salary: 3000, id: '1'
    }])

    return { jobs }
  }
});
</script>

<style>

</style>
