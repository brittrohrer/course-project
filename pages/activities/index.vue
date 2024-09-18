<script setup>

import { ref } from "vue";
const name = ref("GridPage");

/* Create array and header variable to dynamically build page content for each grid container */
const headerOne =ref("Natural Wonders")
const gridOne = ref([
    {
        class: `col-lg-12`,
        title: `Title`,
        body: `There are six locations in Michigan that are managed by the National Park Service.`
    },
    {
        class: `col-lg-4 text-center`,
        title: `Isle Royale National Park`,
        body: `Isle Royale National Park is an island located in the northern region of Lake Superior. 
                Isle Royale encompasses an area of 132,018 acres, and can only be explored by foot. The park can only be reached by ferry or seaplane and only from April to November.`
    },
    {
        class: `col-lg-4 text-center`,
        title: `Keweenaw National Historical Park`,
        body: `This park consists of 21 historic sites along with the old copper mines. It is home to the world’s oldest and largest lava flow, which was first mined more than 7,000 years ago.`               
    },
    {
        class: `col-lg-4 text-center`,
        title: `North Country National Scenic Trail`,
        body: `The North Country Trail is a 4,800 mile trail that goes from Vermont to North Dakota. It is the longest of the National Scenic Trails. The Upper Peninsula includes 550 miles of the 
                trail while the Lower Peninsula includes 600 miles. `
    },
    {
        class: `col-lg-4 text-center`,
        title: `Pictured Rocks National Lakeshore`,
        body: `The park includes miles of lakeshore with sandstone cliffs, beaches, waterfalls and sand dunes. It is one of the most popular and visited locations in Michigan. The minerals seeping 
                from the cliff side create an almost painted scene down the cliff to Lake Superior. `               
    },
    {
        class: `col-lg-4 text-center`,
        title: `River Raisin National Battlefield Park`,
        body: `This is the historic location of the River Raisin Battle that took place in January 1813 during the War of 1812. The River Raisin Battle resulted in the forced relocation and assimilation 
                of the Native Peoples who resided there.`
    },
    {
        class: `col-lg-4 text-center`,
        title: `Sleeping Bear Dunes National Lakeshore`,
        body: `This National Lakeshore includes the world’s largest collection of sand dunes along fresh water. They include 450 ft tall sand dunes. The lakeshore consists of 35 miles along Lake Michigan and 
                some of the prettiest beaches in the Midwest.`               
    },
],);
const headerTwo = ref("Other Destinations")
const gridTwo = ref([
    {
        class: `col-lg-4`,
        title: `Lighthouses`,
        body: `There are over 120 lighthouses across the State of Michigan. There are actually more in Michigan than any other 
                state. One of the more visited lighthouses is Whitefish Point Lighthouse. It is the oldest operating lighthouse 
                on Lake Superior. The lighthouse sits on a notorious stretch of shoreline known as “Lake Superior’s Shipwreck Coast”. 
                Out of the 500 plus known shipwrecks, this stretch is home to at least 200 of them. The most famous of them being the 
                Edmund Fitzgerald. `
    },
    {
        class: `col-lg-4 text-center`,
        title: `Tahquamenon Falls`,
        body: `The Falls consist of the Lower and Upper Falls. The Upper Falls are one of the largest waterfalls east of the Mississippi 
                River. Its spans 200 ft wide with a nearly 50 ft drop. Tannins released from the cedar and hemlock swamps, located upriver, 
                give the falls its signature brown color and white foam.`
    },
    {
        class: `col-lg-4 text-center`,
        title: `Mackinac Island`,
        body: `An island located in Lake Huron near the Straights of Mackinac. The island is listed as a National Historic Landmark and a majority 
                of the island is preserved as Mackinac Island State Park. Mackinac Island is well known for its ban on almost all motor vehicles and 
                as the home of the Grand Hotel. The Grand Hotel is famous for having the world’s largest porch and is a member of the Historic Hotels 
                of America.`               
    },
],);
const headerThree = ref("Title")
const gridThree = ref([
    {
        class: `col-sm-6`,
        title: `title`,
        body: `body` 
    },
    {
        class: `col-sm-6`,
        title: `title`,
        body: `body`
    },
],);
</script>

<template>
    <main class="container">
        <!-- use a v-for for each grid section to display the header, title and body with each of their specified layouts-->
        <div class="row bg-primary">
            <h2>{{headerOne}}</h2>
            <div :class="gOne.class"
            v-for="gOne in gridOne"
            :key="gOne.title">
                <h3 class="text-center">{{gOne.title}}</h3>
                <p>{{gOne.body}}</p>
            </div>
        </div>
        
        <div class="row bg-info">
            <h2>{{headerTwo}}</h2>
            <div :class="gTwo.class"
                v-for="gTwo in gridTwo"
                :key="gTwo.title">
                <h3 class="text-center">{{gTwo.title}}</h3>
                <p>{{gTwo.body}}</p>
            </div>
        </div>
        
        <div class="row bg-warning">
            <h2>{{headerThree}}</h2>
            <div :class="gThree.class"
                v-for="gThree in gridThree"
                :key="gThree.title">
                <h3 class="text-center">{{gThree.title}}</h3>
                <p>{{gThree.body}}</p>
            </div>
        </div>
    </main>
</template>

<style scoped>
h2,h3,p {
    color: black;
}
</style>
