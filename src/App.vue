<template>
  <div class="app">
    <h1>Jobs</h1>
    <ul>
      <li v-for="job in jobs" :key="job.id">
      {{ job.title }}</li>
    </ul>
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
    const jobs = ref<Job[]>([
      { title: 'accountant', location: 'Edinburgh', salary: 3000, id: '1' },
      { title: 'developer', location: 'Glasgow', salary: 4000, id: '2'},
      { title: 'manager', location: 'London', salary: 5000, id: '3' },
      { title: 'designer', location: 'Manchester', salary: 3500, id: '4' },
      { title: 'engineer', location: 'Birmingham', salary: 4500, id: '5' },
      { title: 'marketing specialist', location: 'Liverpool', salary: 3200, id: '6' },
      { title: 'analyst', location: 'Leeds', salary: 3800, id: '7' },
      { title: 'consultant', location: 'Newcastle', salary: 4200, id: '8' },
      { title: 'project manager', location: 'Bristol', salary: 4700, id: '9' },
      { title: 'sales representative', location: 'Cardiff', salary: 3400, id: '10' }
  ])

    return { jobs }
  }
});
</script>

<style>

</style>
