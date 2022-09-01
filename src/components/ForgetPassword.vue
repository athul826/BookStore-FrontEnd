<template>
    <div>
        <AppBar></AppBar>
    <div class="centrealign">
        <div class="heading_tag">
                  
                  <h3>Forgot Your Password?</h3>
                
              </div>
        <div class="centerebox">
        <div class="box_with_paddingg">
          
            <div class="leftBox">
            <v-form ref="form" v-model="valid" lazy-validation>
              <v-col>
              
                <span>Enter your email address and we'll send you a link to reset your
      password</span>
  
                <div class="email">
                    <v-text-field
          outlined
          dense
          autocomplete="off"
          v-model="email"
          :rules="emailRules"
          label="E-mail"
          required
        >
        </v-text-field>
                </div>
                <div class="reset_button">
                  <v-btn
                    :disabled="!valid"
                    color="#A03037"
                    class="mr-4"
                    @click="validate"
                  >
                    Reset Password
                    
                  </v-btn>
                </div>
                
              </v-col>
            </v-form>
          </div>
        </div>
      </div>
    </div>
</div>
  </template>
  
  <script>
import AppBar from './AppBar.vue';
  //import UserService from '@/services/userService/userService';
  
  export default {
    name: "ForgetPasswordComponent",
    data: () => ({
        valid: true,
        Password: "",
        passwordRules: [
            (v) => !!v || "password is required",
            (v) => (v && v.length <= 10) || "password must be less than 10 characters",
        ],
        email: "",
        emailRules: [
            (v) => !!v || "E-mail is required",
            (v) => /.+@.+\..+/.test(v) || "E-mail must be valid",
        ],
    }),
    components: { AppBar }
}
  </script>
  <style>
  .centrealign {
    display: flex;
    /* justify-content: center; */
    align-content: center;
    margin: 70px;
    margin-left: 300px;
    
  }
  
  .centerebox {
    width: 310px;
    height: 300px;
    padding: 48px 40px 36px 40px;
    margin: 0;
    border-style: solid;
    border-width: 1px;
    border-color: #9a9a9c;
    border-radius: 5px;
    box-sizing: content-box;
    
  }
  
  .box_with_paddingg {
    display: flex;
    
  }
  
  .leftBox {
    width: 300px;
    height: 400px;
  }
  
  .first_last_name {
    width: 75%;
    display: flex;
    flex-direction: row;
    gap: 40px;
  }
  
  .create_tag {
    font-family: "sans-serif";
    font-size: 24px;
    align-content: center;
  }
  
  .email {
    padding-top: 40px;
    width: 270px;
  }
  
  .password {
    width: 270px;
    display: flex;
  }
  
  
  .reset_button {
    top: 379px;
left: 559px;
width: 292px;
height: 37px;
/* UI Properties */
background: #A03037 0% 0% no-repeat padding-box;
border-radius: 3px;
opacity: 1;
  }
  
  .heading_tag {
    /* width: 368px;
    height: 50px;
    margin-top: -50px;
    margin-left: 200px;
    box-sizing: border-box; */
    position: relative;
  left: 300px;
  top: -40px;
  }
  .paragraph {
    padding-left: 10px;
  }
  </style>