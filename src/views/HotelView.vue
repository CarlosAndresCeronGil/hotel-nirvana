<template>
  <div id="hotel">
    <div id="nav-image">
      <img alt="Hotel" src="../assets/hotel1.jpg" />
    </div>
    <div id="form-hotel-info">
      <p id="hotel-title">Hotel numero 1</p>
      <p id="hotel-address">Carrera 50 No 70-24</p>
      <p id="hotel-near-sites">A 1 km del centro de la ciudad</p>
      <p id="hotel-score">9.2/10</p>
      <div v-for="dato in info" :key="dato">
        {{ dato.id }}
        {{ dato.name }}
        <!-- {{ datos.image }} -->
      </div>
    </div>
  </div>
  <button type="submit" id="hotel-button">Reservar</button>
  <button type="submit" id="score-button">Calificar</button>
  <input type="number" min="1" max="10" id="score-input" />
  <HotelGallery />
  <HotelOfferts />
</template>

<script>
import HotelGallery from '../components/HotelGallery.vue'
import HotelOfferts from '../components/HotelOfferts.vue'
import axios from 'axios'

export default {
  name: 'HotelView',
  components: {
    HotelGallery,
    HotelOfferts
  },
  data () {
    return {
      info: null
    }
  },
  mounted () {
    axios
      .get('https://rickandmortyapi.com/api/character/1,2,3,4')
      .then(response => (this.info = response.data))
      .catch(error => console.log(error))
  }
}
</script>

<style scoped>
#hotel {
  margin-top: 50px;
  display: flex;
}

#nav-image {
  margin-right: 15px;
}

#nav-image img {
  width: 100%;
  height: 100%;
}

#form-hotel-info {
  display: block;
  text-align: initial;
}

#hotel-title {
  font-size: 30px;
  font-weight: bold;
  color: #2c3e50;
  text-decoration: underline;
}

#hotel-address,
#hotel-near-sites,
#hotel-score {
  font-size: 20px;
}

#hotel-button {
  font-size: 20px;
  margin-left: 10px;
  background-color: #ffb703;
  border-radius: 5px;
}

#score-button {
  font-size: 20px;
  margin-left: 10px;
  background-color: #ffb703;
  border-radius: 5px;
  margin-right: 5px;
}
</style>
