<template>
    <div>
      <v-card class="navigation_bar">
        <v-app-bar color="#A03037">
          
          <img style="padding-left:200px"
            class="mr-3"
            :src="require('../assets/education.svg')"
            height="35"
          />
          <v-toolbar-title style="padding-left: 10px; color: white;">BookStore</v-toolbar-title>
          <v-spacer> </v-spacer>
          
          
            <div class="right_logos">
          <!-- <img
            style="height: 30px"
            class="ma-3"
            :src="require('../assets/person.svg')"
          />--
          <img -->
            <!-- style="height: 30px"
            class="ma-3"
            :src="require('../assets/cart.svg')"
          /> -->
          </div>            
        </v-app-bar>
            </v-card>
            </div>
            </template>
  <script>
    export default {
      
        data: () => ({
        drawer: false,
        group: null,
      }),
    }
  </script>
<style>


.navigation_bar {
  margin-top: -60px;
  padding: 0;
  width: 1600px;
  height: 65px;
}
.v-text-field {
  width: 500px;
  padding-right: 100px;
}
.right_logos {
  /* width: 60px; */
  opacity: 0.5;
  
  display: flex;
  flex-direction: row;
  left: 50%;
}

</style>
