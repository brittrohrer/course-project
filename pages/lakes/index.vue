<script setup>
import { ref } from "vue";

const name = ref("AccordionPage");

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
                Surrounded By: Michigan, Wisconsin, Minnesota, and Ontario`
    },
    {
        header: `Lake Michigan`,
        target: `#collapseTwo`,
        controls: `collapseTwo`,
        id: `collapseTwo`,
        body: `From the Ojibwe name, mishi-gami, which translate to “Great Water”. Lake Michigan is the second-largest lake, out of the Great Lakes, by volume. It is connected to Lake Huron through the Straits of Mackinac. The Shores of Lake Michigan is often referred to as the “Third Coast” following those of the Atlantic and Pacific Oceans.
                Facts:
                Max Depth: 925 ft
                Surrounded By: Michigan, Wisconsin, Illinois, and Indiana`
    },
    {
        header: `Lake Huron`,
        target: `#collapseThree`,
        controls: `collapseThree`,
        id: `collapseThree`,
        body: `It is connected to Lake Michigan through the Straits of Mackinac. It is the third-largest lake, by volume, of the five Great Lakes. 
                Facts:
                Max Depth: 748 ft
                Surrounded By: Michigan and Ontario`
    },
    {
        header: `Lake Ontario`,
        target: `#collapseFour`,
        controls: `collapseFour`,
        id: `collapseFour`,
        body: `Lake Ontario is the fourth-largest lake of the five, by volume. It is also the only lake to not border the state of Michigan. This is the last lake in the chain of Great Lakes that leads to the St. Lawerence River, which ends at the Atlantic Ocean.
                Facts:
                Max Depth: 804 ft
                Surrounded By: Ontario and New York`
    },
    {
        header: `Lake Erie`,
        target: `#collapseFive`,
        controls: `collapseFive`,
        id: `collapseFive`,
        body: `It’s name is derived from the Iroquoian term “erielhonan” which translates to “long tail”Lake Erie is the smallest, by volume, of all the Great Lakes. It flows into Lake Ontario through the Niagara Falls.
                Facts:
                Max Depth: 210 ft
                Surrounded By: Michigan, Ohio, Pennsylvania, New York, and Ontario`
    },
],); 
const show = ref(true)
</script>

<template>
    <main class="container">
        <div class="accordion" id="myFirstAccordion">
            <!-- use v-for to loop through accordian array and display header and button -->
            <div class="accordion-item"
                v-for="a in accordion"
                :key="a.header">
                <h2 class="accordion-header">{{a.header}}</h2>    
                <!-- create button with target pulled from array and click event to show the body/content when button is clicked for target-->
                <button
                    class="accordion-button collapsed"
                    type="button" 
                    data-bs-toggle="collapse"
                    aria-expanded="false" 
                    :data-bs-target="a.target"
                    :aria-controls="a.controls"
                    @click= "show"
                >
                </button>
                <!-- identify target based on id and show the body -->
                <div :id="a.id" class="accordion-collapse collapse" data-bs-parent="#myFirstAccordion">
                    <div v-show="show" class="accordion-body">
                        {{a.body}}
                    </div>
                </div>
            </div>
        </div>
    </main>
    
</template>

<style scoped>
h2 {
    color:black;
}
</style>