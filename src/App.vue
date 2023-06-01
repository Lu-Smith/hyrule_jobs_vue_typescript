<template>
  <div class="app">
    <header>
      <button @click="handleClick('title')" >order by title</button>
      <button  @click="handleClick('salary')" >order by salary</button>
      <button  @click="handleClick('location')" >order by location</button>
    </header>
    <h1>Jobs</h1>
    <JobList :jobs="jobs" :order="order"/>
  </div>
</template>

<script lang="ts">

import { defineComponent, ref} from 'vue';
import Job from './types/Job'
import OrderTerm from './types/OrderTerm'
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

  const order = ref<OrderTerm>('title')

    const handleClick = (term: OrderTerm) => {
      order.value = term 
    }

    return { jobs, handleClick, order }
  }
});
</script>

<style>

header { 
  text-align: center;
  margin-top: 20px;
}

button {
  margin: 0 10px;
  color: #1195c9;
  border: 3px solid #1195c9;
  background: #d5f0ff;
  padding: 9px 16px;
}

</style>
