<template>
<div id="jobdetails">
  <div class="row pt-3" v-if="job._id">
      <div class="col-6">
        <h2>Company:{{job.company}} - Title:{{job.jobTitle}} - Hours:{{job.hours}} - Rate:{{job.rate}}</h2>
        <h4>{{job.description}}</h4>
        <div class="d-flex justify-content-between">
          <button class="btn btn-outline-danger" @click="deleteJob">Delete</button>
        </div>
      </div>
    </div>
</div>
  
</template>

<script>
export default {
  name: "jobDetails",
  mounted(){
    return this.$store.dispatch("getJobById", this.$route.params.id)
  },
  computed: {
    job(){
      return this.$store.state.activeJob
    }
  },
  methods: {
    deleteJob(){
      this.$store.dispatch("deleteJob", this.job._id)
    },
  }

}
</script>

<style>

</style>