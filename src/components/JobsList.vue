<template>
  <h2>hello..................</h2>
  <p>Ordered by {{ order }}</p>
  <div class="job-list">
    <ul>
      <li v-for="job in jobs" :key="job.id">
        <h2>{{ job.title }} in {{ job.location }}</h2>
        <div class="salary"> 
            <p>
                £{{ job.salary }}
            </p>
      </div>
    </li>
    </ul>
  </div>

</template>

<script lang="ts">
import { defineComponent, PropType } from 'vue'
import Job from '@/types/Job'
import OrderTerm from '@/types/OrderTerm';

export default  defineComponent ({
 name: 'JobsList',
 props: {
    jobs: {
        required: true,
        type: Array as PropType<Job[]>
    },
    order: {
        required: true,
        type: String as PropType<OrderTerm>
    }
 }
})
</script>

<style scoped>

</style>