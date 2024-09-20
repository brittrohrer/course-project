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
    <div class="card">
        <h3>
            Latitude: {{ weatherProp.latitude }} <br> Longitude: {{ weatherProp.longitude }}
        </h3>
        <div class="row">
            <div class="col-4">
                <p>
                    Sunrise: {{ weatherProp.sunrise }}
                </p>
                <p>
                    Sunset: {{ weatherProp.sunset }}
                </p>
            </div>
            <div class="col-4">
                <p>
                    Temp Max: {{ weatherProp.tempMax }}{{ tempUnits }}
                </p>
                <p>
                    Temp Min: {{ weatherProp.tempMin }}{{ tempUnits }}
                </p>
            </div>
            <div class="col-4">
                <p>
                    Wind Speed Max: {{ weatherProp.wind }}{{ windUnits }}
                </p>
            </div>
        </div>
    </div>
</template>