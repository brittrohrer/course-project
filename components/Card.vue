<script setup>
import {defineProps, ref} from "vue";

/* Define values from our data */
const weatherProp = defineProps({
        latitude: Number,
        longitude: Number,
        sunrise: String,
        sunset: String,
        tempMax: Number,
        tempMin: Number,
        wind: Number,
        tempUnits: String,
        windUnits: String,
        currentTemp: Number,
});


let on = ref(false);

//Click Function to Change Button
function displayColorTemp(e) {
    let temps = weatherProp.currentTemp;
    on = !on; //toggle true/false  //First click needs double click why?
    console.log('toggle ' + on);
    if(on === true) { // True change color of button to different color based on current temps
        console.log('Should say true: ' + on);
        console.log(temps);
        if (temps > 90) {
            e.target.style.backgroundColor = "#E66B39";
            e.target.style.border = "none";
        } else if (temps < 90 && temps > 80) {
            e.target.style.backgroundColor = "#F4B96D";
            e.target.style.border = "none";
        } else if (temps < 80 && temps > 70) {
            e.target.style.backgroundColor = "#F5EFB2";
            e.target.style.border = "none";
        } else if (temps < 70 && temps > 60) {
            e.target.style.backgroundColor = "#74B985";
            e.target.style.border = "none";
        } else {
            e.target.style.backgroundColor = "#5fc0d3";
            e.target.style.border = "none";
        }
    } else { // False - go back to original style
        console.log('Should say false:' + on);
        e.target.style.backgroundColor = "white";
        e.target.style.border = "solid gray 1px";
    }
}
</script>
<template>
    <div class="weather-card card">
        <div class="row">
            <h3 class="col-lg-6 col-md-12 weather-card-title">Location:</h3>
            <p class="col-lg-6 col-md-12">Lat: {{ weatherProp.latitude }} <br>
                           Long: {{ weatherProp.longitude }}
            </p>
        </div>
        <div class="row">
            <div class="col-lg-6">
                <h4 class="weather-card-sub-title">Temp:</h4>
                <p>
                   High/Low: {{ weatherProp.tempMax }}{{ weatherProp.tempUnits }} / {{ weatherProp.tempMin }}{{ weatherProp.tempUnits }} <br>
                   Current: {{ weatherProp.currentTemp }}{{ weatherProp.tempUnits }}
                </p>
            </div>
            <div class="col-lg-6">
                <h4 class="weather-card-sub-title">Wind Speed Max:</h4>
                <p>
                   {{ weatherProp.wind }}{{ weatherProp.windUnits }}
                </p>
            </div>
        </div>
        <div class="row">
            <div class="col-lg-6">
                <h4 class="weather-card-sub-title">Sunrise:</h4>
                <p>{{ weatherProp.sunrise }}</p>
            </div>
            <div class="col-lg-6">
                <h4 class="weather-card-sub-title">Sunset:</h4>
                <p>{{ weatherProp.sunset }}</p>
            </div>
        </div>
        <button class="weather-button" @click="displayColorTemp">
            Click for Current Temp Color!
        </button>
    </div>
</template>