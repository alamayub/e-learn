<template>
  <div>
    <v-container class="contact">
      <div class="contact__info">
        <div class="mb-3">
          <div class="display-1 mb-2">Contact Info</div>
          <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Magnam perspiciatis dolor, aperiam temporibus assumenda, porro unde distinctio aliquid saepe accusamus numquam</p>
        </div> 
        <div class="contacts d-flex flex-column" style="grid-gap: 12px;">
          <div v-for="(inf, i) in info" :key="i" class="d-flex align-center">
            <div class="contact__circle secondary">
              <v-icon color="white">{{ inf.icon }}</v-icon>
            </div>
            <div style="line-height: 1;" class="ml-3">
              <div class="title mb-1" style="line-height: 1;">{{ inf.head }}</div>  
              <span>{{ inf.title }}</span>
            </div>
          </div>
        </div> 
        <div class="socials mt-6">
          <v-btn icon v-for="(social, s) in socials" :style="{ color: social.color }" large :key="s" target="_blank" :href="social.to">
            <v-icon v-text="social.icon" :style="{ color: social.color }" size="24" />
          </v-btn>
        </div>
      </div>
      <v-form v-model="valid" ref="form" lazy-validation class="form pa-3 pa-sm-4 pa-md-5 pa-lg-6">
        <div class="headline">Message Us</div>
        <v-text-field v-model="item.name" label="Full Name*" :rules="[ v => !!v || '' ]" outlined dense hide-details />
        <v-text-field v-model="item.email" label="Email*" :rules="[ v => !!v || '' ]" outlined dense hide-details />
        <v-text-field v-model="item.phone" label="Phone Number*" :rules="[ v => !!v || '' ]" outlined dense hide-details /> 
        <v-textarea v-model="item.message" label="Your message..." outlined dense hide-details />   
        <v-btn rounded max-width="200" color="secondary" :disabled="!valid" @click.stop="submit">submit</v-btn>  
      </v-form>
    </v-container>  
    <v-container>
      <div class="map mt-3">
        <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3554.482279355477!2d84.87663421500014!3d27.01492238308371!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x39935440af3b59e3%3A0x5aa0411733213e6a!2sBirgunj%20Ghanta%20Ghar!5e0!3m2!1sen!2snp!4v1629135428021!5m2!1sen!2snp" style="border:0;" allowfullscreen="" loading="lazy" />
      </div>
    </v-container>
  </div>
</template>

<script>
export default {
  data: () => ({
    info: [
      { icon: 'mdi-map-marker', title: 'Kathmandu-10, Nepal', head: 'Address' },
      { icon: 'mdi-email', title: 'info@medriasis.com', head: 'Email' },
      { icon: 'mdi-phone', title: '(051) 546 5456', head: 'Phone Number' }
    ],
    socials: [
      { icon: 'mdi-facebook', to: 'https://www.facebook.com', color: '#3b5998' },
      { icon: 'mdi-twitter', to: 'https://www.twitter.com', color: '#00acee'  },
      { icon: 'mdi-linkedin', to: 'https://www.linkedin.com', color: '#0e76a8' },
      { icon: 'mdi-instagram', to: 'https://www.instagram.com', color: '#8a3ab9' }
    ],
    valid: true,
    item: {
      name: null,
      email: null,
      phone: '',
      message: null
    }
  }),
  methods: {
    submit() {
      if(this.$refs.form.validate()) console.log('validated')
      else console.log('not validated')
    }
  } 
}
</script>

<style scoped>
p, span {
  line-height: 1.3;
  font-size: 13px;  
}
.contact {
  display: grid;
  grid-template-columns: calc(50% - 30px) calc(50% - 30px);
  grid-gap: 60px;
}
.contact__circle {
  height: 48px;
  width: 48px;
  border-radius: 6px;
  display: flex;
  align-items: center;
  justify-content: center;  
}
.map {
  height: 40vh;
  width: 100%;
  border-radius: 6px;
  overflow: hidden;
}
iframe {
  height: 100%;
  width: 100%;
}
.form {
  border-radius: 6px;
  box-shadow: 0 1px 10px 0 rgb(0 0 0 / 10%);
  display: flex;
  flex-direction: column;
  grid-gap: 12px;
}
@media (max-width: 700px) {
  .contact { grid-template-columns: 100%; grid-gap: 30px; }
}
</style>