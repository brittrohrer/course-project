<script setup>
import {ref} from "vue";
</script>
<template>
    <!--Default Page Structure-->
    <div>
        <AppHeader />
        
        <slot />
        <!-- 
            - Our Changing Page Slot 
            - Bring in out Page from our <NuxtLink> here 
        -->
        
        <AppFooter />
    </div>

</template>
