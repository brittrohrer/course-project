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
        <AppHeader />

        <slot />

        <AppFooter />
    </div>

</template>
