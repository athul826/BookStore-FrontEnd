<template>
    <div class="home">
      <ForgetPassword></ForgetPassword>
    </div>
  </template>
  
  <script>
  // @ is an alias to /src
  
  import ForgetPassword from '@/components/ForgetPassword.vue'
  
  export default {
    name: 'ForgetPasswordUI',
    components: {
      ForgetPassword
  }
  }
  </script>