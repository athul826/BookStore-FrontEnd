<template>
    <v-form>
      <v-text-field
        outlined
        dense
        v-model="form.role"
        label="Role"
        autocomplete="off"
        :rules="[nameRules.required, nameRules.name_length,nameRules.regex]"
      ></v-text-field>
      <v-text-field
        outlined
        dense
        v-model="form.firstName"
        label="FirstName"
        autocomplete="off"
        :rules="[nameRules.required, nameRules.name_length,nameRules.regex]"
      ></v-text-field>
      <v-text-field
        outlined
        dense
        v-model="form.lastName"
        label="LastName"
        required
        autocomplete="off"
        :rules="[nameRules.required, nameRules.name_length,nameRules.regex]"
      ></v-text-field>
      <v-text-field
        outlined
        dense
        label="E-mail"
        v-model="form.email"
        autocomplete="off"
        :rules="[emailRules.required, emailRules.email_validation]"
      ></v-text-field>
      <v-text-field
        outlined
        dense
        :append-icon="showPassword ? 'mdi-eye' : 'mdi-eye-off'"
        @click:append="() => (showPassword = !showPassword)"
        :type="showPassword ? 'text' : 'password'"
        v-model="form.password"
        label="Password"
        :rules="[passwordRules.required, passwordRules.minLength]"
      ></v-text-field>
      <v-text-field
        outlined
        dense
        label="Confirm Password"
        :append-icon="showCPassword ? 'mdi-eye' : 'mdi-eye-off'"
        @click:append="() => (showCPassword = !showCPassword)"
        :type="showCPassword ? 'text' : 'password'"
        v-model="form.cpassword"
        :rules="[passwordRules.required, passwordRules.minLength]"
      ></v-text-field>
      <button  class="button" @click="validate">SignUp</button>
    </v-form>
  </template>
  
  
  <script>
  //import { registration } from '../services/UserService'
  export default {
      name: 'RegistrationComponent',
      data: () => ({
          form: {
              role: '',
              firstName: '',
              lastName: '',
              email: '',
              password: '',
              cpassword: '',
          },
          showPassword: false,
          showCPassword: false,
          sending: false,
          nameRules: {
              required: (v) => !!v || "Name is required",
              name_length: (v) =>
                  (v && v.length <= 10) || "Name must be less than 10 characters",
              regex: (v) => /^[a-zA-Z]/.test(v) || "Name can not be a Number",
          },
          emailRules: {
              required: (v) => !!v || "E-mail is required",
              email_validation: (v) => /.+@.+\..+/.test(v) || "E-mail must be valid",
          },
          passwordRules: {
              required: (v) => !!v || "Name is required",
              minLength: (v) => (v && v.length > 7) || "Password must be 8 characters",
          },
      }),
      methods: {
          validate() {
              console.log(this.role)
              console.log(this.firstName)
              console.log(this.lastName)
              console.log(this.email)
              console.log(this.password)
              console.log(this.cpassword)
              let reqData = {
                  role: this.role,
                  first_name: this.firstName,
                  last_name: this.lastName,
                  email: this.email,
                  password: this.password,
                  confirm_password: this.cpassword
              }
              console.log(reqData)
    //           registration(reqData).then((responce) => {
    //               console.log(responce);
    //           }).catch((error) => {
    //               console.log(error);
    //           })
    //       },
    //   }
          },
        }
  }
  </script>
  <style scoped>
  .button {
      background: grey;
      /* width: 352px;
      height: 37px;
      left: 727px;
      font-size: 18px;
      top:300px;
      color: white; */
  }
  .brown {
      background-color: brown;
  }
  .lightBrown {
      background-color: lightblue;
  }
  </style>