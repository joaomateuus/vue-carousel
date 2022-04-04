<template>
    <div class="carousel">
        <!--Here we are iterating our array-->
        <div class="carousel-inner">
            <!--Slide is a prop from app and and the key is from the CarosuelItem
            and we set the key as item+index to identify easier-->
            <CarouselItem v-for="(slide, index) in slides"
            :slide="slide" :key="`item-${index}`" 
            :currentSlide="currentSlide" :index="index"/>
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
    data() {
        return {
            currentSlide: 0,
            slideInterval: null
        }
    },
    methods: {
        //setting the current slide as the index for the right timw
        setCurrentSlide(index) {
            this.currentSlide = index;
        }
    },
    //function to set the interval and get the index
    mounted() {
        this.slideInterval = setInterval(()=>{
            //we are getting the index trough a conditional
            const index = this.currentSlide < this.slides.length -1 ? this.currentSlide +1 : 0;
            //if its smaller than array-1 or its the current+1 and else is zero 
            this.setCurrentSlide(index);
        }, 3000)
    },
    beforeUnmount(){
        clearInterval(this.slideInterval);
    }
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