<template>
   <div class="col-4 car">
    <router-link :to="{name: 'HouseDetails', params: { id: house._id}}">
      <div class="card">
        <img class="card-img-top" :src="house.imgUrl" alt />
        <div class="card-body">
          <h4 class="card-title">{{house.make}} - {{house.model}} - {{house.year}}</h4>
        </div>
      </div>
    </router-link>
  </div>
</template>

<script>
export default {
  name: "house"

}
</script>

<style>

</style>