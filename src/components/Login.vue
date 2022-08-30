<template>
        
    <v-form ref="form" v-model="valid" lazy-validation>
      <div class="box_align">
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
        <div>
            <a
              href="http://localhost:8080/forget"
              class="Forget_password"
              width="350"
              height="20"
              >Forget password</a
            >
          </div>
        
        <div style="
          top: 398px;
          left: 727px;
          width: 280px;
          height: 37px;
          background: #a03037 0% 0% no-repeat padding-box;
          border-radius: 3px;
          color: #ffffff;
          opacity: 1; ;
        "
      >
          <v-btn
            :disabled="!valid"
           
            color="#a03037"
            class="mr-4"
            @click="validate"
          >
            Login
          </v-btn>
        </div>
      </v-col>
  </div>  
  </v-form>
  
</template>

<script>
// import UserService from "@/services/userService/userService";

export default {
name: "LoginComponent",
data: () => ({
  valid: true,

  Password: "",

  passwordRules: [
    (v) => !!v || "password is required",
    (v) =>
      (v && v.length <= 10) || "password must be less than 10 characters",
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
    this.$refs.form.validate();
    console.log(this.email);
    console.log(this.Password);
//       let reqData = {
//         email: this.email,
//         password: this.Password,
//       };
// //       UserService.prototype
//         .loginService(reqData)
//         .then((data) => {
//           console.log("Response from login", data);
//           localStorage.setItem("token", data.data.token);
//           this.$router.push({path:'/dashboard'})
//         })
//         .catch((error) => {
//           console.log(error);
//         });
//     },
//   },
},

},
};
</script>
<style>
.email {
width: 280px;
display: flex;
}
.password {
width: 280px;
display: flex;
}

.box_align {
padding-bottom: 45px;
margin-bottom: 90px;
margin-left: -12px;

}
.login_button {
width: 400px;
}
</style>