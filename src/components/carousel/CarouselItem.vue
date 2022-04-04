<template>
    <transition name="slide-in">
        <!--Only show if the slide is the same as the index-->
        <div class="carousel-item" v-show="currentSlide === index">
            <!--Here we receive the slide of v-for as a prop-->
            <img :src="slide" alt="">
        </div>   
    </transition>
</template>

<script>

export default {
    name: 'CarouselItem',
    //Here we receive the slide of v-for as a prop
    props: ["slide", "currentSlide", "index"],
}
</script>

<style>
.carousel-item{
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
}

.slide-in-enter-active,
.slide-in-leave-active {
    transition: all 1s ease-in-out;
}

.slide-in-enter-from {
    transform: translateX(-100%);
}

.slide-in-leave-to {
    transform: translateX(100%);
}
</style>