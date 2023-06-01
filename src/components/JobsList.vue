<template>
    <p class="info">Ordered by {{ order }}</p>
    <h2>Find your dream job 🤔</h2>
  <div class="job-list">
    <ul>
      <li v-for="job in orderedJobs" :key="job.id">
        <h3>{{ job.title }} <small>in {{ job.location }}</small></h3>
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
import { computed, defineComponent, PropType } from 'vue'
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
 },
 setup(props) {
    const orderedJobs = computed(() => {
        return [...props.jobs].sort((a: Job, b: Job) => {
            return a[props.order] > b[props.order] ? 1 : -1
        })
    })
    return { orderedJobs }
 }
})
</script>

<style scoped>
h2 {
    margin: 20px 0;
    font-style: italic;
    text-align: center;
}

p {
    color: red;
}

.info {
    text-align: center;
    margin-top: 10px;
    letter-spacing: 1px;
    font-style: italic;
}

h3 {
    margin-bottom: 10px;
}

.job-list li {
    background: white;
    margin: 10px;
    border-radius: 4px;
    padding: 20px;
}

.job-list li small {
    color: #5e5d5d;
    font-weight: 400;
}

</style>