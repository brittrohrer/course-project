<script setup>
import {ref} from "vue";

/* use variable that can be changed and create web content dynamically */
const title =ref(`Michigan`);

</script>
<template>
    <header class="bg-light">
            
            <nav class="navbar navbar-expand-md bg-dark navbar-dark">
                <h1 class="nav-title navbar-brand">{{ title }}</h1>
                <ul class="nav navbar-nav mr-auto">
                    <li class="nav-item">
                        <NuxtLink to="/">Home</NuxtLink>
                    </li>
                    <li class="nav-item">
                        <NuxtLink to="/lakes">The Great Lakes</NuxtLink>
                    </li>
                    <li class="nav-item">
                        <NuxtLink to="/activities">Things To Do</NuxtLink>
                    </li>
                    <li class="nav-item">
                        <NuxtLink to="/gallery">Gallery</NuxtLink>
                    </li>
                </ul>
            </nav>
        </header>
</template>
<style scoped>
    .nav-title {
        font-size: 3rem;
        padding: 0 2rem;
        color: lightgrey;
    }
    li {
        padding: 0 1rem;
    }
    li a {
        text-decoration: none;
        color: lightgray;
    }
    .router-link-active {
        color: lightblue;
        font-weight: bold;
    }
</style>
