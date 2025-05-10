<template>
  <!-- Header Section -->
  <MyHeader
    appTitle="JobFinder"
    caption="Connecting Talent with Opportunity"
    author="Rishitha Rani Pakam"
  />

  <!-- Job Listings Display -->
  <JobBox :joblistings="joblistings" />
</template>

<script>
import MyHeader from './components/MyHeader.vue';
import JobBox from './components/JobBox.vue';

export default {
  name: 'App',
  components: {
    MyHeader,
    JobBox
  },
  data() {
    return {
      joblistings: []
    };
  },
  methods: {
    async fetchJobs() {
      const res = await fetch("https://rishitha-node.onrender.com/api");
      const data = await res.json();
      return data[0].joblistings;
    }
  },
  async created() {
    this.joblistings = await this.fetchJobs();
  }
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@300&display=swap');

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: 'Montserrat', sans-serif;
  background-color: #f3f5b4;
  min-height: 100vh;
}


.container {
  max-width: 400px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 0.3em solid black;
  padding: 30px;
  border-radius: 5px;
}

div {
  margin-bottom: 0.5em;
  text-align: center;
}
</style>
