<template>
    <div class="home">
      <DashboardBar></DashboardBar>
    </div>
  </template>
  
  <script>
  // @ is an alias to /src
  //import Dashboard from "@/components/DashboardBar.vue";
import DashboardBar from '../components/DashboardBar.vue';
  export default {
    name: "DashboardUI",
  
    components: {
    DashboardBar
},
  };
  </script>