<template>
  <div id="house-details" class="container">
    <div class="row pt-3" v-if="house._id">
      <div class="col-6">
        <img class="card-img-top" :src="house.imgUrl" />
        <h2>Bedrooms:{{house.bedrooms}} - Levels:{{house.levels}} - Year:{{house.year}}</h2>
        <p>${{house.price.toFixed(2)}}</p>
        <h4>{{house.description}}</h4>
        <div class="d-flex justify-content-between">
          <button class="btn btn-outline-danger" @click="deleteHouse">Delete</button>
          <button class="btn btn-outline-info" @click="bid">+ $10000</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "housedetails",
  mounted(){
    this.$store.dispatch("getHouseById", this.$route.params.id)
  },
  computed: {
    house(){
      return this.$store.state.activeHouse
    }
  },
  methods: {
    deleteHouse(){
      this.$store.dispatch("deleteHouse", this.house._id)
    },
    bid(){
      let bid = { id: this.house._id, price: this.house.price + 10000}
      this.$store.dispatch("bidHouse", bid)
    }
  }

}
</script>

<style>

</style>