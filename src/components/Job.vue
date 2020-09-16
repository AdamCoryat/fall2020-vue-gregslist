<template>
<div id="job" class="col-4 job">
  <router-link :to="{name :'JobDetails', params: {id: job._id}}">
    <div class="card-body">
      <div class="card">
          <h4 class="card-title">Title:{{job.company}} - ${{job.jobTitle}}</h4>
      </div>
  </router-link>
</div>
  
</template>

<script>
export default {
  name: "job",
  props: {
    job: {
      type: Object,
      required: true
    }
  }
}
</script>

<style scoped>
.job {
  transition: 0.5s ease;
  cursor: pointer;
}
.job:hover {
  transform: scale(1.05);
}
</style>