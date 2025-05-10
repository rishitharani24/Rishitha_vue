<template>
  <div class="job-grid">
    <SingleJob v-for="job in joblistings" :key="job.id" :job="job" />
  </div>
</template>

<script>
import SingleJob from './SingleJob.vue';

export default {
  name: 'JobBox',
  props: {
    joblistings: Array
  },
  components: {
    SingleJob
  }
};
</script>

<style scoped>

.job-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 20px;
  padding: 2em;
  max-width: 1200px;
  margin: 0 auto;
  box-sizing: border-box;
}
@media screen and (max-width: 500px) {
   .job-grid {
    display: grid;
    grid-template-columns: 1fr ;
    gap: 10px;
  }
}
</style>
