<script setup>
import { ref } from "vue";

/* create array of accordian content to call on in template*/
const accordion = ref([
    {
        header: `Lake Superior`,
        target: `#collapseOne`,
        controls: `collapseOne`,
        id: `collapseOne`,
        body: `The Ojibwe name is gitchi-gami, which translates to “Great Sea”. Lake Superior is the largest freshwater lake in the world by surface area.  By volume, it is the largest of the Great Lakes. 
                Facts:
                Max Depth: 1333 ft
                Surrounded By: Michigan, Wisconsin, Minnesota, and Ontario`,
        img: `/lakesu.jpg`
    },
    {
        header: `Lake Michigan`,
        target: `#collapseTwo`,
        controls: `collapseTwo`,
        id: `collapseTwo`,
        body: `From the Ojibwe name, mishi-gami, which translate to “Great Water”. Lake Michigan is the second-largest lake, out of the Great Lakes, by volume. It is connected to Lake Huron through the Straits of Mackinac. The Shores of Lake Michigan is often referred to as the “Third Coast” following those of the Atlantic and Pacific Oceans.
                Facts:
                Max Depth: 925 ft
                Surrounded By: Michigan, Wisconsin, Illinois, and Indiana`,
        img: `/lakemi.jpeg`
    },
    {
        header: `Lake Huron`,
        target: `#collapseThree`,
        controls: `collapseThree`,
        id: `collapseThree`,
        body: `It is connected to Lake Michigan through the Straits of Mackinac. It is the third-largest lake, by volume, of the five Great Lakes. 
                Facts:
                Max Depth: 748 ft
                Surrounded By: Michigan and Ontario`,
        img: `/lakehur.jpg`
    },
    {
        header: `Lake Ontario`,
        target: `#collapseFour`,
        controls: `collapseFour`,
        id: `collapseFour`,
        body: `Lake Ontario is the fourth-largest lake of the five, by volume. It is also the only lake to not border the state of Michigan. This is the last lake in the chain of Great Lakes that leads to the St. Lawerence River, which ends at the Atlantic Ocean.
                Facts:
                Max Depth: 804 ft
                Surrounded By: Ontario and New York`,
        img: `/lakeo.jpg`
    },
    {
        header: `Lake Erie`,
        target: `#collapseFive`,
        controls: `collapseFive`,
        id: `collapseFive`,
        body: `It’s name is derived from the Iroquoian term “erielhonan” which translates to “long tail”Lake Erie is the smallest, by volume, of all the Great Lakes. It flows into Lake Ontario through the Niagara Falls.
                Facts:
                Max Depth: 210 ft
                Surrounded By: Michigan, Ohio, Pennsylvania, New York, and Ontario`,
        img: `/lakeer.jpg`
    },
],); 
const show = ref(true)
</script>

<template>
    <main class="container mt-5 mb-5">
        <h2 class="page-header">The Great Lakes</h2>

        <!--Accordian all 5 Lakes -->
        <div class="accordion" id="myFirstAccordion">
            <!-- Loop Accordian Array to display each lake -->
            <div class="accordion-item"
                v-for="a in accordion"
                :key="a.header">
                <h3 class="accordion-header"> 

                    <!-- Accordian Button-->
                    <button
                        class="accordion-button collapsed lake-button"
                        type="button" 
                        data-bs-toggle="collapse"
                        aria-expanded="false" 
                        :data-bs-target="a.target"
                        :aria-controls="a.controls"
                        @click= "show"
                    >
                    {{a.header}}
                    </button>
                </h3>

                <!-- Accordian Text Body 
                    - Dispay on button click
                -->
                <div :id="a.id" class="accordion-collapse collapse" data-bs-parent="#myFirstAccordion">
                    <div v-show="show" class="accordion-body">
                        <p>{{a.body}}</p>
                        <img class="img-fluid" :src="a.img">
                    </div>
                </div>
            </div>
        </div>
    </main>
    
</template>

<style scoped>

</style>