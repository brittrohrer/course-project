<script setup>
import { ref } from "vue";
/* Create array and header variable to dynamically build page content for each grid container */
const headerOne = ref("National Park Destinations:")
const gridOne = ref([
    {
        class: `col-lg-4 col-md-6`,
        title: `Isle Royale National Park`,
        body: `Isle Royale National Park is an island located in the northern region of Lake Superior. 
                Isle Royale encompasses an area of 132,018 acres, and can only be explored by foot. The park can only be reached by ferry or seaplane and only from April to November.`
    },
    {
        class: `col-lg-4 col-md-6`,
        title: `Keweenaw National Historical Park`,
        body: `This park consists of 21 historic sites along with the old copper mines. It is home to the world’s oldest and largest lava flow, which was first mined more than 7,000 years ago.`               
    },
    {
        class: `col-lg-4 col-md-6`,
        title: `North Country National Scenic Trail`,
        body: `The North Country Trail is a 4,800 mile trail that goes from Vermont to North Dakota. It is the longest of the National Scenic Trails. The Upper Peninsula includes 550 miles of the 
                trail while the Lower Peninsula includes 600 miles. `
    },
    {
        class: `col-lg-4 col-md-6`,
        title: `Pictured Rocks National Lakeshore`,
        body: `The park includes miles of lakeshore with sandstone cliffs, beaches, waterfalls and sand dunes. It is one of the most popular and visited locations in Michigan. The minerals seeping 
                from the cliff side create an almost painted scene down the cliff to Lake Superior. `               
    },
    {
        class: `col-lg-4 col-md-6`,
        title: `River Raisin National Battlefield Park`,
        body: `This is the historic location of the River Raisin Battle that took place in January 1813 during the War of 1812. The River Raisin Battle resulted in the forced relocation and assimilation 
                of the Native Peoples who resided there.`
    },
    {
        class: `col-lg-4 col-md-6`,
        title: `Sleeping Bear Dunes National Lakeshore`,
        body: `This National Lakeshore includes the world’s largest collection of sand dunes along fresh water. They include 450 ft tall sand dunes. The lakeshore consists of 35 miles along Lake Michigan and 
                some of the prettiest beaches in the Midwest.`               
    },
],);
const headerTwo = ref("Other Top Destinations:")
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
        class: `col-lg-4`,
        title: `Tahquamenon Falls`,
        body: `The Falls consist of the Lower and Upper Falls. The Upper Falls are one of the largest waterfalls east of the Mississippi 
                River. Its spans 200 ft wide with a nearly 50 ft drop. Tannins released from the cedar and hemlock swamps, located upriver, 
                give the falls its signature brown color and white foam.`
    },
    {
        class: `col-lg-4`,
        title: `Mackinac Island`,
        body: `An island located in Lake Huron near the Straights of Mackinac. The island is listed as a National Historic Landmark and a majority 
                of the island is preserved as Mackinac Island State Park. Mackinac Island is well known for its ban on almost all motor vehicles and 
                as the home of the Grand Hotel. The Grand Hotel is famous for having the world’s largest porch and is a member of the Historic Hotels 
                of America.`               
    },
],);
const headerThree = ref("Popular Events:")
const gridThree = ref([
    {
        class: `col-lg-6`,
        title: `Michigan Renaissance Festival`,
        body: `Interactive Event that takes place annually August to October in Holly, Michigan. 
                There is music, local artisans, and even jousting.`
    },
    {
        class: `col-lg-6`,
        title: `Tulip Time Festival`,
        body: `Takes place in Holland, Michigan in the beginning of May. It is the longest running tulip festival in the United States. 
                Activities include parades, fireworks, music and more. The festival also features millions of tulips.`
    },
    {
        class: `col-lg-6`,
        title: `National Cherry Festival`,
        body: `Takes place in Traverse City, Michigan in August. It is a food festival named after the region, which is nicknamed the 
                "Cherry Capital of the World". Includes great food, family activities and live-entertainment.`
    },
    {
        class: `col-lg-6`,
        title: `National Blueberry Festival`,
        body: `Every year in August, South Haven Michigan hosts the National Blueberry Festival.
             There is live music, parades, classic car shows, and blueberry-themed competitions.`
    },
    {
        class: `col-lg-6`,
        title: `Bavarian Festival`,
        body: `Held in Frankenmuth, Michigan. Sing and dance to Bavarian music. Also includes German entertainers and polka bands`
    },
    {
        class: `col-lg-6`,
        title: `Electric Forest Music Festival`,
        body: `The festival is a multiday music festival that features a variety of bands including electronic dance music.`
    },
    {
        class: `col-lg-6`,
        title: `Faster Horses Music Festival`,
        body: `Multiday country music festival held in Brooklyn, Michigan.`
    }
],);

</script>

<template>
    <main class="container mt-5">
        <h2 class="page-header">Popular Destinations and Events</h2>
        <!-- Destinations and Events Container -->
         <!-- Ids for some future links to sections in page - maybe -->
        <div class="container">

            <!-- Grid One - Nature Destinations -->
            <div class="grid-container row" id="nature-destinations">
                <h3 class="grid-header">{{headerOne}}</h3>
                <div :class="gOne.class"
                      v-for="gOne in gridOne"
                      :key="gOne.title">
                    <h4 class="text-center">{{gOne.title}}</h4>
                    <p>{{gOne.body}}</p>
                </div>
            </div>
        
            <!-- Grid Two - Other Destinations -->
            <div class="grid-container row" id="other-destinations">
                <h3 class="grid-header">{{headerTwo}}</h3>
                <div :class="gTwo.class"
                      v-for="gTwo in gridTwo"
                      :key="gTwo.title">
                    <h4 class="text-center">{{gTwo.title}}</h4>
                    <p>{{gTwo.body}}</p>
                </div>
            </div>
        
            <!-- Grid Three - Events -->
            <div class="grid-container row" id="events-destinations">
                <h3 class="grid-header">{{headerThree}}</h3>
                <div :class="gThree.class"
                      v-for="gThree in gridThree"
                      :key="gThree.title">
                    <h4 class="text-center">{{gThree.title}}</h4>
                    <p>{{gThree.body}}</p>
                </div>
            </div>
        </div>
    </main>
    
</template>

<style scoped>
</style>
