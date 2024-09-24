<script setup>

import {defineProps, ref} from "vue";


/* Image Prop
   - Create Prop with simple type validator
   - Declare what type of variables and what type of data we are recieving from the parent
*/
const prop = defineProps({
        src: String,
        alt: String,
        title: String,
        class: String,
        index: Number,
});

// Function Add Border Around Clicked Image

let isActive = ref(false); // create starting value of the isActive variable to false/inactive

function addBorder(e) {
    isActive = !isActive; // Toggle of Active/Not Active on each click  //First click needs double click why?
    if (isActive === true) { // Active - activate border
        console.log ('Is active');
        e.target.style.border = "solid black";
    } else {  // Not Active - no border
        console.log ('Is not active');
        e.target.style.border = "none";
    }
}
</script>

<!-- 
   Structure the Image Component
-->
<template>
    <div class= "col-3">
        <!-- Image Structure
            - Bind with prop objects
            - Click event to activate add Border Function
        -->
        <img :key="index"
            :src="prop.src"
            :alt="prop.alt"
            :class="prop.class"
            :title="prop.title"
            @click = "addBorder"
        >
    </div>
</template>

<style>

</style>