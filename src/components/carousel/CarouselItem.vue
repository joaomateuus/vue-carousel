<template>
    <div class="carousel-item">
        <!--Here we receive the slide of v-for as a prop-->
        <img :src="slide" alt="">
    </div>
</template>

<script>

export default {
    name: 'CarouselItem',
    //Here we receive the slide of v-for as a prop
    props: ["slide"],
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
</style>