<template>
  <div id="jobs" class="container-fluid">
    <div class="row my-3">
      <div class="col" id="form">
        <form @submit.prevent="createHouse" class="form-inline">
          <div class="form-group p-1">
            <label class="mr-1" for="company">Company</label>
            <input
              v-model="newJob.company"
              type="text"
              name="company"
              id="company"
              class="form-control"
              placeholder="Bedrooms..."
            />
          </div>
          <div class="form-group p-1">
            <label class="mr-1" for="jobTitle">Job Title</label>
            <input
              v-model="newJob.jobTitle"
              type="number"
              name="jobTitle"
              id="jobTitle"
              class="form-control"
              placeholder="Bathrooms..."
            />
          </div>
          <div class="form-group p-1">
            <label class="mr-1" for="levels">Levels</label>
            <input
              v-model="newJob.levels"
              type="number"
              name="levels"
              id="levels"
              class="form-control"
              placeholder="Levels..."
            />
          </div>
          <div class="form-group p-1">
            <label class="mr-1" for="imgUrl">Image URL</label>
            <input
              v-model="newJob.imgUrl"
              type="url"
              name="imgUrl"
              id="imgUrl"
              class="form-control"
              placeholder="Image Url..."
            />
          </div>
          <div class="form-group p-1">
            <label class="mr-1" for="year">Year</label>
            <input
              v-model="newJob.year"
              type="number"
              name="year"
              id="year"
              class="form-control"
              placeholder="Year..."
              min="1700"
              max="2020"
            />
          </div>
            <div class="form-group p-1">
            <label class="mr-1" for="price">Price</label>
            <input
              v-model="newJob.price"
              type="number"
              name="price"
              id="price"
              class="form-control"
              placeholder="Price..."
            />
            </div>
            <div class="form-group p-1">
            <label class="mr-1" for="description">Description</label>
            <input
              v-model="newJob.description"
              type="text"
              name="description"
              id="description"
              class="form-control"
              placeholder="Description..."
            />
          </div>
          <button type="submit" class="btn btn-outline-success">Add House</button>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "jobs",


}
</script>

<style>

</style>