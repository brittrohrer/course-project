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
let on = ref(false)
function displayColorTemp(e) {
    on = !on;
    console.log(on);
}

//let btnActive = ref(false); // create starting value of the isActive variable to false/inactive


/* function displayColorTemp(e, weatherProp, btnActive) {
   this.btnActive = !this.btnActive; // create the toggle of active and not active on each click
    console.log(this.btnActive);
    if (this.btnActive === true) { // if the image is active, log index and change border to active
        if (weatherProp.currentTemp > 90) {
             e.target.style.backgroundColor = "#E66B39";
             e.target.style.border = "none";
        }
        else if (weatherProp.currentTemp < 90 && weatherProp.currentTemp > 80 ) {
            e.target.style.backgroundColor = "#F4B96D";
            e.target.style.border = "none";
        }
        else if (weatherProp.currentTemp < 80 && weatherProp.currentTemp > 70 ) {
            e.target.style.backgroundColor = "#F5EFB2";
            e.target.style.border = "none";
        }
        else if (weatherProp.currentTemp < 70 && weatherProp.currentTemp > 60 ) {
            e.target.style.backgroundColor = "#74B985";
            e.target.style.border = "none";
        }
        else {
            e.target.style.backgroundColor = "#26798A";
            e.target.style.border = "none";
        }
       
    }
    else {  // if the image is not active then log is not active and make border none
        e.target.style.backgroundColor = "white";
        e.target.style.border = "solid gray 1px";
    }
} */

</script>
<template>
    <div class="weather-card card">
        <div class="row">
            <h3 class="col">Location:</h3>
            <p class="col">Lat: {{ weatherProp.latitude }} <br>
                           Long: {{ weatherProp.longitude }}
            </p>
        </div>
        <div class="row">
            <div class="col-lg-6">
                <p>Temp: <br>
                   High/Low: {{ weatherProp.tempMax }}{{ weatherProp.tempUnits }} / {{ weatherProp.tempMin }}{{ weatherProp.tempUnits }} <br>
                   Current: {{ weatherProp.currentTemp }}{{ weatherProp.tempUnits }}
                </p>
            </div>
            <div class="col-lg-6">
                <p>Wind Speed Max: <br>
                   {{ weatherProp.wind }}{{ weatherProp.windUnits }}
                </p>
            </div
            ><div class="col-lg-12">
                <p>Sunrise: {{ weatherProp.sunrise }} <br>
                   Sunset: {{ weatherProp.sunset }}
                </p>
            </div>
        </div>
        <button class="weather-button" @click="displayColorTemp">
            Click for Current Temp Color!
        </button>
       <!-- <button class="weather-button" @click="displayColorTemp($event, weatherProp)">
            Click for Current Temp Color!
        </button> -->
    </div>
</template>