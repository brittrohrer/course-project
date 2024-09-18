<script setup>
import {ref} from "vue";

/* use variable that can be changed and create web content dynamically */
const title =ref(`Michigan`);

</script>
<template>
    <header class="bg-light">
            <h1>{{ title }}</h1>
            <nav class="navbar navbar-expand-sm bg-dark navbar-dark">
                <ul class="nav navbar-nav">
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