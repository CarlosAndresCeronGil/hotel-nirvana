<template>
  <div id="container">
    <p id="hotels-title">Hoteles</p>
    <div class="character-image" v-for="image in images" :key="image">
      <router-link to="/hotel">
        <HotelCard v-bind:imageUrl="image.image" />
      </router-link>
      <!-- <HotelCard />
      <HotelCard /> -->
    </div>
  </div>
</template>

<script>
import HotelCard from './HotelCard.vue'
import axios from 'axios'

export default {
  name: 'ListHotels',
  components: {
    HotelCard
  },
  data () {
    return {
      images: null
    }
  },
  mounted () {
    axios
      .get('https://rickandmortyapi.com/api/character/1,2,3,4,5,6,7')
      .then(response => (this.images = response.data))
      .catch(error => console.log(error))
  }
}
</script>

<style scoped>
#container {
  border: 2px solid black;
  border-radius: 12px;
  margin-top: 10px;
}

#hotels-title {
  font-size: 30px;
  font-weight: bold;
  color: #219ebc;
}

a {
  text-decoration: none;
}
</style>
