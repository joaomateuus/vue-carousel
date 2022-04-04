<template>
 <div>
   <CarouselComponent :slides="slides" />
 </div>
</template>

<script>
import CarouselComponent from './components/carousel/CarouselComponent.vue' 

export default {
  name: 'App',
  components: {
    CarouselComponent
  },
  data() {
    return {
      slides: [
        'https://picsum.photos/id/1032/900/400',
        'https://picsum.photos/id/1033/900/400',
        'https://picsum.photos/id/1033/900/400',
        'https://picsum.photos/id/1035/900/400',
        'https://picsum.photos/id/1036/900/400',
      ]
    }
  },
  methods: {}


}


</script>

<style>

</style>
