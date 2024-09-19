<script setup>

import { ref } from "vue";
const name = ref("Home");

const touchButton = ref(true);

/* Jumbotron
created ref variables for this so that in the template section the content could be rendered dynamically
and be changed easily if the text changed*/
const jumboTitle = ref(`Discovering Michigan!`);
const jumboText = ref(`“The best sky was in Italy or Spain and in Northern Michigan in the fall” - Ernest Hemingway, Green Hills of Africa`);
const jumboText2 = ref(`Experience the seasons of Michigan. It's a place for food lovers, outdoor adventurers, cultural experiences, and endless memories.`);       


/* Cards
create array of cards objects to call on in the template section*/
const cards = ref([
                {
                    header: `Pure Michigan`,
                    text: `The official travel and tourism website for Michigan.`,
                    link: `https://www.michigan.org/`,
                    button: `Link Button`
                },
                {
                    header: `Great Lakes Guide`,
                    text: `Discover more about each of the Great Lakes and their importance below and on the Accordion Page.`,
                    link: `https://greatlakes.guide/`,
                    button: `Link Button`
                },
                {
                    header: `National Parks of Michigan`,
                    text: `All site maintained by the National Parks Service in the State of Michigan.`,
                    link: `https://www.nps.gov/state/mi/index.htm`,
                    button: `Link Button`
                },
            ],
);
</script>

<template>
    <main class="container mt-5">
        <div class="jumbotron jumbotron-fluid jumbo-container">
            <!--create jumbotron -->
            <div class="container p-2">
                <!-- call the jumbotron title from the script section -->
                <h2 class="display-4">{{jumboTitle}}</h2>
                <!--create top margin of 2 text and emphasize text with "lead"
                also create a button and clickevent that use if/else that will use the state of the button when clicked (true or false) 
                to determine with text to display-->
                <p v-if ="touchButton" class="lead mt-2">{{jumboText}}</p>
                <p v-else class="lead mt-2">{{jumboText2}}</p>
                <button class="btn btn-warning" @click="touchButton = !touchButton">Your journey starts here ...  </button>
            </div>
        </div>
        <div class= "container d-flex flex-row justify-content-evenly mt-5 mb-5 flex-wrap gap-3">
            <!-- use a vue for loop to loop thru the cards array in script section to create each card-->
            <div class="card" 
                style="width: 18rem;" 
                v-for="card in cards" :key="card.name">
                <div class="card-body">
                    <h3 class="card-title">
                    {{card.header}}</h3>
                    <p class="card-text">{{card.text}}</p>
                    <!-- bind the card link so the link can function properly-->
                    <a :href="card.link" 
                        class="btn btn-primary">
                        {{card.button}}
                    </a>
                </div>
            </div>
        </div>
    </main>
    
</template>

<style scoped>
    
</style>
