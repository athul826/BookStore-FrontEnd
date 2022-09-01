<template>
  <v-form ref="form" v-model="valid" lazy-validation>
    <v-col>
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
      <div class="password">
        <v-text-field
          outlined
          dense
          :append-icon="showPassword ? 'mdi-eye' : 'mdi-eye-off'"
          @click:append="() => (showPassword = !showPassword)"
          :type="showPassword ? 'text' : 'password'"
          v-model="Password"
          :rules="passwordRules"
          label="Password"
          required
        >
        </v-text-field>
      </div>
      <div style="margin-top: -20px; ">
        <a
       
          href="http://localhost:8080/forget"
          
          class="Forget_password"
          width="368"
          height="20"
          >Forget password</a
        >
      </div>

      <div
        style="
          top: 398px;
          left: 727px;
          width: 270px;
          height: 40px;
          /* background: #a03037 0% 0% no-repeat padding-box; */
          border-radius: 3px;
          color: #ffffff;
          opacity: 1; ;
          margin-bottom: -10px;
          
        
        "
      >
        <v-btn
          :disabled="!valid"
          color="#A03037"
          class="mr-4"
          @click="validate"
        >
          Login
          <div style="width: 190px; ">
          </div>
        </v-btn>
      </div>
      <div style="padding-top: 25px; margin-left: -32px">
        <b>--OR--</b>
        <div style="margin-bottom: 50px;width: 350px;">
          <v-btn
          href="https://www.facebook.com/"
            :disabled="!valid"
            color="#4266B2"
            class="mr-4"
            @click="validate"
          >
            FaceBook
            <div style="padding-left: 5px;">

            </div>
          </v-btn >

          <v-btn :disabled="!valid" color="" class="mr-4" @click="validate">
            Google
            <div style="padding-left: 25px;">
            </div>
          </v-btn>
        </div>
      </div>
    </v-col>
  </v-form>
</template>
  
<script>
import UserService from '@/Services/UserService/UserService';

export default {
  name: "LoginComponent",
  data: () => ({
    valid: true,

    Password: "",

    passwordRules: [
      (v) => !!v || "password is required",
      (v) =>
        (v && v.length <= 15) || "password must be less than 15 characters",
    ],
    email: "",
    emailRules: [
      (v) => !!v || "E-mail is required",
      (v) => /.+@.+\..+/.test(v) || "E-mail must be valid",
    ],
    showPassword: false,
    showCPassword: false,
    sending: false,
  }),
    methods: {
    validate() {
      console.log(this.email);
      console.log(this.Password);
      let reqData = {
        email:this.email,
        password:this.Password,
      }
      UserService.prototype.loginService(reqData).then((data)=> {
        console.log("Response from login", data);
        localStorage.setItem("token", data.data.token);
        this.$router.push({path:'/dash'})
      })
      .catch((error) => {
          console.log(error);
        });
    }
  },
  

  
};
</script>
  <style>
.email {
  width: 270px;
  display: flex;
}

.password {
  width: 270px;
  display: flex;
}

.Forget_password {
  padding-left: 120px;
}

</style>