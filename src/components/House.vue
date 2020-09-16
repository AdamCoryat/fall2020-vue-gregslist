<template>
   <div class="col-4 house">
    <router-link :to="{name: 'HouseDetails', params: {id: house._id}}">
      <div class="card">
        <img class="card-img-top" :src="house.imgUrl" alt />
        <div class="card-body">
          <h4 class="card-title">Year:{{house.year}} - ${{house.price}}</h4>
        </div>
      </div>
    </router-link>
  </div>
</template>

<script>
export default {
   name: "house",
  props: {
    house: {
      type: Object,
      required: true
    }
  }
}
</script>

<style scoped>
.house {
  transition: 0.5s ease;
  cursor: pointer;
}
.house:hover {
  transform: scale(1.05);
}

</style>