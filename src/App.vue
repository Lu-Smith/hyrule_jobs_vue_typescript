<template>
  <div class="app">
    <h1>Jobs</h1>
    <JobList />
    <ul>
      <li v-for="job in jobs" :key="job.id">{{ job.title }}</li>
    </ul>
  </div>
</template>

<script lang="ts">

import { defineComponent, ref} from 'vue';
import Job from './types/Job'
import JobList from './components/JobsList.vue'

export default defineComponent({
  name: 'App',
  components: {
    JobList
  },
  setup() {
    const jobs = ref<Job[]>([
      { title: 'accountant', location: 'Edinburgh', salary: 30000, id: '1' },
      { title: 'developer', location: 'Glasgow', salary: 40000, id: '2'},
      { title: 'manager', location: 'London', salary: 50000, id: '3' },
      { title: 'designer', location: 'Manchester', salary: 35000, id: '4' },
      { title: 'engineer', location: 'Birmingham', salary: 45000, id: '5' },
      { title: 'marketing specialist', location: 'Liverpool', salary: 32000, id: '6' },
      { title: 'analyst', location: 'Leeds', salary: 38000, id: '7' },
      { title: 'consultant', location: 'Newcastle', salary: 42000, id: '8' },
      { title: 'project manager', location: 'Bristol', salary: 47000, id: '9' },
      { title: 'sales representative', location: 'Cardiff', salary: 34000, id: '10' }
  ])

    return { jobs }
  }
});
</script>

<style>

</style>
