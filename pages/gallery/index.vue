<script setup>

import { ref } from "vue";

/* Gallery Images Array */
const images = ref([
    {
        src: '/Copperharbor.jpeg',
        alt: 'Copper Mountain in the Fall',
        title: 'Copper Mountain, Michigan',
        class: 'img-fluid h-100 p-0 d-block mx-auto'
    },
    {
        src: 'macisland.jpeg',
        alt: 'Mackinac Island in the Fog',
        title: 'Mackinac Island, Michigan',
        class: 'img-fluid h-100 p-0 d-block mx-auto'
    },
    {
        src: '/falls.jpeg',
        alt: 'Tahquamenon Falls in the winter',
        title: 'Tahquamenon Falls, Michigan',
        class: 'img-fluid h-100 p-0 d-block mx-auto'
    },    
    {
        src:'/freighter.jpeg',
        alt: 'Freighter in Lake Superior',
        title: 'Lake Superior, Michigan',
        class: 'img-fluid h-100 p-0 d-block mx-auto'
    },
    {
        src: '/grandhaven.jpeg',
        alt: 'Grand Haven Breakwall',
        title: 'Grand Haven, Michigan',
        class: 'img-fluid h-100 p-0 d-block mx-auto'
    },
    {
        src: '/kitch.jpeg',
        alt: 'Kitch-iti-kipi',
        title: 'Kitchitikipi, Michigan',
        class: 'img-fluid h-100 p-0 d-block mx-auto'
    },
    {
        src: '/MacBridge.jpeg',
        alt: 'Mackinac Bridge',
        title: 'Mackinac Bridge, Michigan',
        class: 'img-fluid h-100 p-0 d-block mx-auto'
    },
    {
        src: '/macbridge2.jpeg',
        alt: 'Mackinac Bridge',
        title: 'Mackinac Bridge, Michigan',
        class: 'img-fluid h-100 p-0 d-block mx-auto'
    },
    {
        src: '/petstone.jpeg',
        alt: 'Petoskey stones stacked on each other',
        title: 'Petoskey, Michigan',
        class: 'img-fluid h-100 p-0 d-block mx-auto'
    },
    {
        src: '/pic4.jpg',
        alt: 'Northern Lights over the bay',
        title: 'Petoskey, Michigan',
        class: 'img-fluid h-100 p-0 d-block mx-auto'
    },
    {
        src: '/PicRocks.jpeg',
        alt: 'Pictured Rocks',
        title: 'Munising, Michigan',
        class: 'img-fluid h-100 p-0 d-block mx-auto'
    },
    {
        src: '/picrocks2.jpeg',
        alt: 'Pictured Rocks',
        title: 'Munising, Michigan',
        class: 'img-fluid h-100 p-0 d-block mx-auto'
    },
    {
        src: '/SleepingBear.jpeg',
        alt: 'Sleeping Bear Sand Dunes',
        title: 'Empire, Michigan',
        class: 'img-fluid h-100 p-0 d-block mx-auto'
    },
    {
        src: '/stjoseph.jpg',
        alt: 'St. Joseph lighthouse at sunset',
        title: 'St Joseph, Michigan',
        class: 'img-fluid h-100 p-0 d-block mx-auto'
    },
    {
        src: '/tawas.jpg',
        alt: 'Tawas Lighthouse',
        title: 'Tawas, Michigan',
        class: 'img-fluid h-100 p-0 d-block mx-auto'
    },
    ],);
/* Carousel Images Array */
const imagesCarousel = ref([
    {
        class: 'carousel-item active',
        src: '/cutriver.jpeg',
        alt: 'Cutriver Bridge Ariel Shot',
        title: 'Cut River Bridge, Michigan',
    },
    {
        class: 'carousel-item',
        src: '/nightsky.jpeg',
        alt: 'Milky Way night sky',
        title: 'Milky Way over Michigan'
    },
    {
        class: 'carousel-item',
        src: '/tulip.jpeg',
        alt: 'Tulip Field infront of Windmill',
        title: 'Holland, Michigan'
    },
 ],);

/* Change head for this page */
useHead({
    title: 'Michigan | Image Gallery',
    meta: [
        {name: 'description', content: 'View images of Michigan'}
    ]
})
</script>


<template>
   <main class="container mt-5">
        <h2 class="page-header">A Picture Worth A Thousand Words</h2>

        <!--Image Gallery -->
        <div class="img-cont mt-5 d-flex flex-wrap gap-1 justify-content-center">
            <!-- ImageGalley Component
                - Name the props we are passing down to Image List from the specified array
                - Use v-for to loop through the array and display each object (dynamic props)
            -->
            <ImageGallery 
                 v-for="(image, index) in images"
                 :key='index'
                 :src='image.src' 
                 :alt='image.alt'
                 :title='image.title'
                 :class='image.class'
                 :index="index"
            />
        </div>

        <!--Image Carousel-->
        <div id="myFirstCarousel" class="carousel slide container mt-5 mb-5 w-25">
                <div class="carousel-inner">
                <!--Create image carousel 
                    - Use v-for to loop thrue imagesCarousel array
                    - Use imageC.class to make sure the first image of the array has 'active' while the following images don't
                -->
                    <img
                    v-for='imageC in imagesCarousel' 
                    :key='imageC.src'
                    :src='imageC.src' 
                    :alt='imageC.alt'
                    :title='imageC.title'
                    :class='imageC.class'
                    >
                </div>
                <!-- Buttons to move thru the image carousel-->
                <button class="carousel-control-prev" 
                        type="button" 
                        data-bs-target="#myFirstCarousel" 
                        data-bs-slide="prev"
                        >
                  <span class="carousel-control-prev-icon" aria-hidden="true"></span>
                  <span class="visually-hidden">Previous</span>
                </button>
                <button class="carousel-control-next" 
                        type="button" 
                        data-bs-target="#myFirstCarousel" 
                        data-bs-slide="next"
                        >
                  <span class="carousel-control-next-icon" aria-hidden="true"></span>
                  <span class="visually-hidden">Next</span>
                </button>
        </div>
   </main>

   
</template>

<style scoped>

</style>