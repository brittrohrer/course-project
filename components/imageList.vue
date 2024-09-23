<script setup>

import {defineProps, ref} from "vue";


/* 
    Create Prop with simple type validator
    Declare what type of variables and what type of data we are recieving from the parent
*/
const prop = defineProps({
        src: String,
        alt: String,
        title: String,
        class: String,
        index: Number,
});

/* 
    The function used to put border on clicked image
*/

let isActive = ref(false); // create starting value of the isActive variable to false/inactive
function useBorderFunc(e, index) {
    this.isActive = !this.isActive; // create the toggle of active and not active on each click
    if (this.isActive === true) { // if the image is active, log index and change border to active
        console.log (index + ' is active');
        e.target.style.border = "solid black";
    }
    else {  // if the image is not active then log is not active and make border none
        console.log (index + ' is not active');
        e.target.style.border = "none";
    }
}

</script>

<!-- 
    How we want our component structured
-->
<template>
    <div class= "col-3">
        <!-- 
            bind with prop objects
            use click event to call funtion
            pass parameters(event and index) to function
        -->
        <img :key="index"
            :src="prop.src"
            :alt="prop.alt"
            :class="prop.class"
            :title="prop.title"
            @click = "useBorderFunc($event, index)"
        >
    </div>
</template>

<style>

</style>