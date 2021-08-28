<template>
  <v-app>
    <Navbar />
    <Sidebar />
    <v-main>
      <router-view/>
    </v-main>
    <Footer />
  </v-app>
</template>

<script>
import Navbar from './components/Navbar.vue'
import Sidebar from './components/Sidebar.vue'
import Footer from './components/Footer.vue'
export default {
  name: 'App',
  components: { Navbar, Sidebar, Footer },
  data: () => ({
    //
  }),
};
</script>


<style>
/* Container */
.container {
  max-width: 1250px !important;
  margin-right: auto !important;
  margin-left: auto !important;
  padding: 12px !important;
}
/* Button */
.v-btn {
  text-transform: capitalize !important;
  font-weight: 400 !important;
  font-size: 12px !important;
}

/* Image */
img {
  height: 100%;
  width: 100%;
  display: block;
  object-fit: cover;
}

/* Inputs */
.v-input input, .v-input textarea { 
  font-size: 13px !important; 
  letter-spacing: .75px !important; 
  /* color: #9c27b0 !important;  */
}
.v-input .v-label { 
  font-size: 13px !important; 
  letter-spacing: 1px !important; 
  /* color: rgb(156 39 176 / 40%) !important; */
}
.v-input__icon .v-icon.v-icon, .v-select-list .v-icon.v-icon { font-size: 16px !important; }
.v-text-field--outlined.v-input--is-focused fieldset { border: 1px solid #f7f6ee !important; }
.v-text-field--outlined.v-input--has-state fieldset { border: 1px solid #f36c27 !important; }
</style>