<template>
  <div
    :class="[job.type === 'Full-time' ? 'green' : 'red', 'job-card']"
    @mouseenter="moveCard"
    @mouseleave="resetCard"
    ref="card"
  >
    <img :src="job.image" alt="Company Logo" class="company-logo" />
    <h3><strong>{{ job.name }}</strong></h3>
    <h4>Company: {{ job.company }}</h4>
    <h4>Location: {{ job.location }}</h4>
    <h4>Job Type: {{ job.type }}</h4>
    <h4>Salary: {{ job.salary }}</h4>
    <h4>Category: {{ job.category }}</h4>
    <h4>Deadline: {{ job.deadline }}</h4>
    <a :href="job.apply_link" target="_blank" class="apply-button">Apply Now</a>
  </div>
</template>

<script>
export default {
  name: 'SingleJob',
  props: {
    job: Object
  },
  methods: {
    moveCard() {
      const card = this.$refs.card;
      card.style.transition = 'transform 0.3s ease';
      card.style.transform = 'translateY(-10px)';
    },
    resetCard() {
      const card = this.$refs.card;
      card.style.transform = 'translateY(0)';
    }
  }
};
</script>

<style scoped>
.green {
  background-color: #68822d;
  color: white;
}

.red {
  background-color: #264653;
  color: white;
}

.job-card {
  padding: 1em;
  margin-bottom: 1em;
  width: 90%;
  margin-left: auto;
  margin-right: auto;
  border-radius: 8px;
}

.company-logo {
  width: 100px;
  height: 50px;
  margin-bottom: 10px;
}

h3 {
  font-size: 20px;
  margin-bottom: 0.5em;
}

h4 {
  margin-bottom: 0.1em;
}

.apply-button {
  display: inline-block;
  margin-top: 10px;
  padding: 10px 15px;
  background-color: #2196f3;
  color: white;
  text-decoration: none;
  border-radius: 5px;
  font-weight: bold;
  border: 1px solid white;
}

.apply-button:hover {
  background-color: white;
  color: #2196f3;
  border: 1px solid #2196f3;
}

@media screen and (max-width: 768px) {
  .job-container {
    padding: 1em;
    width: 90%;
  }

  h3 {
    font-size: 18px;
  }

  h4 {
    font-size: 15px;
  }

  .company-logo {
    width: 90px;
    height: 45px;
  }

  .apply-button {
    padding: 8px 12px;
    font-size: 14px;
  }
}

@media screen and (max-width: 500px) {
  .job-container {
    padding: 0.75em;
    width: 95%;
  }

  h3 {
    font-size: 15px;
  }

  h4 {
    font-size: 14px;
  }

  .company-logo {
    width: 80px;
    height: 40px;
  }
}
</style>
