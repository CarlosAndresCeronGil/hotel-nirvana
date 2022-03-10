<template>
  <div id="container">
    <p id="hotels-title">Hoteles</p>
    <HotelCard />
    <HotelCard />
    <HotelCard />
  </div>
</template>

<script>
import HotelCard from './HotelCard.vue'

export default {
  name: 'ListHotels',
  components: {
    HotelCard
  }
}
</script>

<style scoped>
#container {
  border: 2px solid black;
  border-radius: 12px;
  margin-top: 10px;
}

#hotels-title{
    font-size: 30px;
    color: #219ebc;
}
</style>
