<script setup>
import {ref} from "vue";

</script>
<template>
    <!--Default Page Structure-->
    <div>
        <AppHeader />
        <!-- Use Header Component -->
        
        <slot />
        <!-- Slot
            - Our Changing Page Slot 
            - Bring in out Page from our <NuxtLink> here 
        -->
        
        <AppFooter />
        <!-- Use Header Component -->
    </div>

</template>
