<script setup>

import { ref, onMounted } from "vue";

/* Jumbotron
created ref variables for this so that in the template section the content could be rendered dynamically
and be changed easily if the text changed*/
const touchButton = ref(true);
const jumboTitle = ref(`Discovering Michigan!`);
const jumboText = ref(`“The best sky was in Italy or Spain and in Northern Michigan in the fall” - Ernest Hemingway, Green Hills of Africa`);
const jumboText2 = ref(`Experience the seasons of Michigan. It's a place for food lovers, outdoor adventurers, cultural experiences, and endless memories.`);       


/* Cards
create array of cards objects to call on in the template section*/

const weather = ref([]);
onMounted(async() => {
    try{
        const response = await fetch(
        "https://api.open-meteo.com/v1/forecast?latitude=45.4014,46.5435,42.9634,45.7452,42.3314&longitude=-84.9083,-87.3954,-85.6681,-87.0646,-83.0457&daily=temperature_2m_max,temperature_2m_min,sunrise,sunset,precipitation_probability_max,wind_speed_10m_max&temperature_unit=fahrenheit&wind_speed_unit=mph&precipitation_unit=inch&timezone=America%2FNew_York&forecast_days=1"
        );
        weather.value = await response.json();
        console.log(weather.value); 
    } catch (error) {} 
});
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
        <div class= "container">
            <h2>Today's Weather Accross Michigan</h2>
            <!-- use a vue for loop to loop thru the cards array in script section to create each card-->
            <ul  class="card-container d-flex flex-row justify-content-evenly mt-5 mb-5 flex-wrap gap-3">
                <li
                v-for="w in weather" :key="w.latitude"
                >
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
                    />
                </li>
            </ul>
        </div>
    </main>
    
</template>

<style scoped>
    
</style>
