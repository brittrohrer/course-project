<script setup>
import {ref} from "vue";
/* use variable that can be changed and create web content dynamically */
const footerTitle = ref (`Destination Michigan`);
const footerText= ref(`Lorem ipsum dolor sit amet consectetur adipisicing elit. Placeat, incidunt maiores eos quis quo cupiditate 
            et odit laudantium a impedit nesciunt autem? Exercitationem cum laborum repudiandae animi. Neque, repudiandae.`);
const phoneContact= ref('555-555-5555');
const emailContact= ref('email@email.com');
</script>
<template>
    <footer class="footer bg-dark mt-5">
        <div class="container pt-5">
            <div class="row">
                <div class="col-md-6 col-lg-6">
                    <h2 class="footer-header text-center">{{footerTitle}}</h2>
                    <p class="footer-text">{{footerText}}</p>
                </div>
                <div class="col-md-3 col-lg-3">
                    <h3 class="footer-title">Contact</h3>
                    <p class="footer-text">{{ phoneContact }}</p>
                    <p class="footer-text">{{ emailContact }}</p>
                </div>
                <div class="col-md-3 col-lg-3">
                    <h3 class="footer-title">Links</h3>
                    <p>
                        <NuxtLink to="/">Home</NuxtLink>
                    </p>
                    <p>
                        <NuxtLink to="/lakes">The Great Lakes</NuxtLink>
                    </p>
                    <p>
                        <NuxtLink to="/activities">Things To Do</NuxtLink>
                    </p>
                    <p>
                        <NuxtLink to="/gallery">Gallery</NuxtLink>
                    </p>
                </div>
            </div>
            <div class="row">
                <p class="footer-text text-center">Created by Brittni Rohrer : 2024</p>
            </div>
        </div>
            
        </footer>
</template>