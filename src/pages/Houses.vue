<template>
<div id="houses" class="container-fluid">
  <div class="row my-3">
    <div class="col" id="form">
       <form @submit.prevent="createHouse" class="form-inline">
          <div class="form-group p-1">
            <label class="mr-1" for="bedrooms">Bedrooms</label>
            <input
              v-model="newHouse.bedrooms"
              type="text"
              name="bedrooms"
              id="bedrooms"
              class="form-control"
              placeholder="Bedrooms..."
            />
          </div>
          <div class="form-group p-1">
            <label class="mr-1" for="bathrooms">Bathrooms</label>
            <input
              v-model="newHouse.bathrooms"
              type="number"
              name="bathrooms"
              id="bathrooms"
              class="form-control"
              placeholder="Bathrooms..."
            />
          </div>
          <div class="form-group p-1">
            <label class="mr-1" for="levels">Levels</label>
            <input
              v-model="newHouse.levels"
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
              v-model="newHouse.imgUrl"
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
              v-model="newHouse.year"
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
              v-model="newHouse.price"
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
              v-model="newHouse.description"
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
  <div class="row">
    <house v-for="house in houses" :key="house._id" :house="house"/>
  </div>
</div>
</template>

<script>
import House from "../components/House.vue"
export default {
  name: "houses",
  mounted() {
  this.$store.dispatch('getAllHouses')    
  },
  data(){
    return {
      newHouse: {}
    }
  },
  computed: {
    houses(){
      return this.$store.state.houses
    }
  },
  methods: {
    createHouse(){
      this.$store.dispatch("createHouse", this.newHouse)
      for(let key in this.newHouse){
        this.newHouse[key] = null
      }
    }
  },
  components: {
    House
  }

}
</script>

<style>

</style>