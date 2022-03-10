<template>
  <div class="home">
    <WhereYouGo/>
    <ListHotels/>
    <HelloWorld/>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import WhereYouGo from '@/components/WhereYouGo.vue'
import ListHotels from '@/components/ListHotels.vue'

export default {
  name: 'HomeView',
  components: {
    HelloWorld,
    WhereYouGo,
    ListHotels
  }
}
</script>
