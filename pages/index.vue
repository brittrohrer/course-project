<script setup>

import { ref, onMounted } from "vue";

/* Jumbotron
    - jumbotron ref variables
*/
const touchButton = ref(true);
const jumboTitle = ref(`Discovering Michigan!`);
const jumboText = ref(`“The best sky was in Italy or Spain and in Northern Michigan in the fall” - Ernest Hemingway, Green Hills of Africa`);
const jumboText2 = ref(`Experience the seasons of Michigan. It's a place for food lovers, outdoor adventurers, cultural experiences, and endless memories.`);       


/* Weather API
    - create array from API
*/

const weather = ref([]);
onMounted(async() => {
    try{
        /* fetch data from api */
        const response = await fetch(
        "https://api.open-meteo.com/v1/forecast?latitude=46.5435,45.7452,45.4014,42.9634,42.3314&longitude=-87.3954,-87.0646,-84.9083,-85.6681,-83.0457&current=temperature_2m&daily=temperature_2m_max,temperature_2m_min,sunrise,sunset,precipitation_probability_max,wind_speed_10m_max&temperature_unit=fahrenheit&wind_speed_unit=mph&precipitation_unit=inch&timezone=America%2FNew_York&forecast_days=1"
        );

        /* Turn response into structured json */
        weather.value = await response.json();
        /* console.log data to see what it looks like */
        console.log(weather.value); 

    } catch (error) {
        /* catch the error if it puts out one and display error */
        console.error(error);
    } 
        
});
</script>

<template>
    <main class="container mt-5">

        <!-- Jumbotron -->
        <div class="jumbotron jumbotron-fluid jumbo-container">
            <div class="container p-2"> 
                <h2 class="display-4">{{jumboTitle}}</h2>
                
                <!-- Toggle between two different paragraphs of text with button click -->
                <p v-if ="touchButton" class="lead mt-2">{{jumboText}}</p>
                <p v-else class="lead mt-2">{{jumboText2}}</p>
                <button class="btn btn-warning" @click="touchButton = !touchButton">Your journey starts here ...  </button>
            </div>
        </div>

        <!-- Homepage main content -->
        <div class= "container">
            <h2 class="page-header">Today's Weather Across Michigan</h2>

            <!-- Render API into a card component-->
            <ul  class="card-container d-flex flex-row justify-content-evenly mt-5 mb-5 flex-wrap gap-3">
                <li
                    v-for="w in weather" :key="w.latitude">
                    <!-- Bring in api objects based on property names that will be used in card compoent -->
                    <Card 
                        :latitude="w.latitude"
                        :longitude="w.longitude"
                        :sunrise="w.daily.sunrise[0]"
                        :sunset="w.daily.sunset[0]"
                        :tempMax="w.daily.temperature_2m_max[0]"
                        :tempMin="w.daily.temperature_2m_min[0]"
                        :wind="w.daily.wind_speed_10m_max[0]"
                        :tempUnits="w.daily_units.temperature_2m_max"
                        :windUnits="w.daily_units.wind_speed_10m_max"
                        :currentTemp="w.current.temperature_2m"
                    />
                </li>
            </ul>
        </div>
    </main>
    
</template>

<style scoped>
    
</style>
