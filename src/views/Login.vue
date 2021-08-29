<template>
  <div class="login">
    <div class="register__container white pa-4 pa-sm-6 pa-md-8 pa-lg-10">
      <v-form ref="regForm" lazy-validation v-model="regValid" v-if="show">
        <div>
          <div class="display-1">Registration</div>   
          <div>Lorem ipsum dolor sit amet consectetur adipisicing elit.</div>   
        </div>
        <div class="form__item mt-3 mt-sm-4 mt-md-5 mt-lg-6">
          <span>Full Name <span class="red--text">*</span></span>
          <v-text-field v-model="form2.name" outlined dense hide-details placeholder="John Doe" :rules="[ v => !!v || '' ]" />  
        </div>
        <div  class="form__item mt-3 mt-sm-4 mt-md-5 mt-lg-6">
          <span>Email <span class="red--text">*</span></span>
          <v-text-field v-model="form2.email" outlined dense hide-details placeholder="example@example.com" :rules="[ v => !!v || '' ]" />  
        </div>
        <div  class="form__item mt-3 mt-sm-4 mt-md-5 mt-lg-6">
          <span>Phone Number <span class="red--text">*</span></span>
          <v-text-field v-model="form2.phone" outlined dense hide-details placeholder="9876543210" :rules="[ v => !!v || '' ]" :counter="10" />  
        </div>
        <div  class="form__item mt-3 mt-sm-4 mt-md-5 mt-lg-6">
          <span>Gender <span class="red--text">*</span></span>
          <v-radio-group v-model="form2.gender" row mandatory class="ma-0" dense hide-details>
            <v-radio label="Male" value="Male" />
            <v-radio label="Female" value="Female" />
          </v-radio-group>
        </div>
        <div  class="form__item mt-3 mt-sm-4 mt-md-5 mt-lg-6">
          <span>Password <span class="red--text">*</span></span>
          <v-text-field v-model="form2.password" outlined dense hide-details placeholder="******" :rules="[ v => !!v || '' ]" />  
        </div>
        <div class="mt-3 mt-sm-4 mt-md-5 mt-lg-6 d-flex justify-space-between">
          <v-btn rounded class="secondary" width="150" :disabled="!regValid" @click="register">register</v-btn>  
          <div class="toggle" @click="show = !show">{{ show ? 'Login' : 'Register' }}</div>
        </div>
      </v-form>
      <v-form ref="logForm" lazy-validation v-model="logValid" v-else>
        <div>
          <div class="display-1">Login</div>   
          <div>Lorem ipsum dolor sit amet consectetur adipisicing elit.</div>   
        </div>
        <div  class="form__item mt-3 mt-sm-4 mt-md-5 mt-lg-6">
          <span>Email <span class="red--text">*</span></span>
          <v-text-field v-model="form1.email" outlined dense hide-details placeholder="example@example.com" :rules="[ v => !!v || '' ]" />  
        </div>
        <div  class="form__item mt-3 mt-sm-4 mt-md-5 mt-lg-6">
          <span>Password <span class="red--text">*</span></span>
          <v-text-field v-model="form1.password" outlined dense hide-details placeholder="******" :rules="[ v => !!v || '' ]" />  
        </div>
        <div class="mt-3 mt-sm-4 mt-md-5 mt-lg-6 d-flex justify-space-between">
          <v-btn rounded class="secondary" width="150" :disabled="!logValid" @click="login">login</v-btn>  
          <div class="toggle" @click="show = !show">{{ show ? 'Login' : 'Register' }}</div>
        </div>
      </v-form>
    </div>  
  </div>  
</template>

<script>
export default {
  data: () => ({
    show: true,
    logValid: true,
    form1: {
      email: null,
      password: null  
    },
    regValid: true,
    form2: {
      name: null,
      email: null,
      phone: null,
      gender: null,
      password: null,  
    }
  }),
  methods: {
    register() {
      if(this.$refs.regForm.validate()) console.log('register validated')
      else console.log('not validated')  
    },
    login() {
      if(this.$refs.logForm.validate()) console.log('login validated')
      else console.log('not validated')  
    }   
  }
}
</script>

<style scoped>
.login {
  background-image: url('https://medicalserviceinternational.com/wp-content/uploads/2020/10/medicalservice-home-doctor.jpg');
  background-position: center center;
  background-size: cover;
  height: calc(100vh - 70px);   
  display: grid;
  grid-template-columns: 50% 50%; 
  align-items: center;
}

.register__container {
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  grid-gap: 12px;  
}
.form__item {
  display: grid;
  grid-template-columns: 120px calc(100% - 140px);
  grid-gap: 20px;  
}
.toggle {
  color: #ffc62d;
  text-decoration: underline;
  cursor: pointer;  
}

@media (max-width: 760px) {
  .login { grid-template-columns: 100%; }  
}
@media (max-width: 500px) {
  .form__item { grid-template-columns: 100%; grid-gap: 8px; }  
}
</style>