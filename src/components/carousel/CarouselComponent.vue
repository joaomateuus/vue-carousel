<template>
    <div class="carousel">
        <!--Here we are iterating our array-->
        <div class="carousel-inner">
            <!--Slide is a prop from app and and the key is from the CarosuelItem
            and we set the key as item+index to identify easier-->
            <CarouselItem v-for="(slide, index) in slides" :slide="slide" :key="`item-${index}`" />
        </div>
    </div>
</template>

<script>
import CarouselItem from './CarouselItem.vue'
export default {
    name: 'CarouselComponent',
    //slides cuz we´ll receive the array as a prop
    props: ["slides"],
    components: {
        CarouselItem,
    },
}
</script>

<style>
.carousel{
    display: flex;
    justify-content: center;
}

.carousel-inner{
    position: relative;
    width: 900px;
    height: 400px;
    overflow: hidden;
}
</style>