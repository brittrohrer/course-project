<script setup>
import {ref} from "vue";

/* use variable that can be changed and create web content dynamically */
const title =ref(`Michigan`);

/* use variable that can be changed and create web content dynamically */
const footerTitle = ref (`Footer Info`);
const footerText= ref(`Lorem ipsum dolor sit amet consectetur adipisicing elit. Placeat, incidunt maiores eos quis quo cupiditate 
            et odit laudantium a impedit nesciunt autem? Exercitationem cum laborum repudiandae animi. Neque, repudiandae 
            nihil a molestias natus corporis vero culpa praesentium provident optio aspernatur! Accusantium ipsam quis, 
            voluptas ut laborum perferendis. Quas, quidem modi?`);

</script>
<template>
    <div>
        <header class="bg-light">
            <h1>{{ title }}</h1>
            <nav class="navbar navbar-expand-sm bg-dark navbar-dark">
                <ul class="nav navbar-nav">
                    <li class="nav-item">
                        <NuxtLink to="/home">Home</NuxtLink>
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

        <slot />

        <footer class="footer bg-light mt-auto">
            <h4 class="text-center">{{footerTitle}}</h4>
            <p>{{footerText}}</p>
        </footer>
    </div>
</template>
<style scoped>
    li {
        padding: 0 1rem;
    }
    li a {
        text-decoration: none;
    }
</style>
