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

</script>
<template>
    <div class="weather-card card">
        <h3>
            Latitude: {{ weatherProp.latitude }} <br> Longitude: {{ weatherProp.longitude }}
        </h3>
        <div class="row">
            <div class="col-lg-12">
                <p>
                    Sunrise: {{ weatherProp.sunrise }}
                    <br>
                    Sunset: {{ weatherProp.sunset }}
                </p>
            </div>
            <div class="col-lg-6">
                <p>
                    Temp Max: {{ weatherProp.tempMax }}{{ tempUnits }} 
                    <br>
                    Temp Min: {{ weatherProp.tempMin }}{{ tempUnits }}
                </p>
            </div>
            <div class="col-lg-6">
                <p>
                    Wind Speed Max: 
                    <br> 
                    {{ weatherProp.wind }}{{ windUnits }}
                </p>
            </div>
        </div>
    </div>
</template>