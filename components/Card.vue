<script setup>
import {defineProps, ref} from "vue";
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
});
let btnActive = ref(false); // create starting value of the isActive variable to false/inactive
function displayColorTemp(e, weatherProp) {
    this.btnActive = !this.btnActive; // create the toggle of active and not active on each click
    if (this.btnActive === true) { // if the image is active, log index and change border to active
        if (weatherProp.tempMax > 80) {
             e.target.style.backgroundColor = "red";
        }
        else if (weatherProp.tempMax < 80 && weatherProp.tempMax > 70 ) {
            e.target.style.backgroundColor = "green";
        }
        else {
            e.target.style.backgroundColor = "blue";
        }
       
    }
    else {  // if the image is not active then log is not active and make border none
        e.target.style.backgroundColor = "white";
    }
}

</script>
<template>
    <div class="weather-card card">
        <div class="row">
            <h3 class="col">Location:</h3>
            <p class="col">Lat: {{ weatherProp.latitude }} 
            <br> 
            Long: {{ weatherProp.longitude }}</p>
        </div>
        <div class="row">
            <div class="col-lg-6">
                <p>
                    Temp:
                    High/Low: {{ weatherProp.tempMax }}{{ tempUnits }} / {{ weatherProp.tempMin }}{{ tempUnits }}
                </p>
            </div>
            <div class="col-lg-6">
                <p>
                    Wind Speed Max: 
                    <br> 
                    {{ weatherProp.wind }}{{ windUnits }}
                </p>
            </div
            ><div class="col-lg-12">
                <p>
                    Sunrise: {{ weatherProp.sunrise }}
                    <br>
                    Sunset: {{ weatherProp.sunset }}
                </p>
            </div>
        </div>
        <button class="weather-button" @click="displayColorTemp($event, weatherProp)">
            CLick here for Temp Color!
        </button>
    </div>
</template>