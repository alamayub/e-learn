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
html {
  scroll-behavior: smooth;
}
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
.v-text-field--outlined.v-input--is-focused fieldset { border: 1px solid #4a4dc7  !important; }
.v-text-field--outlined.v-input--has-state fieldset { border: 1px solid #f36c27 !important; }

/* Blogs */
.blogs {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(23%, 1fr));
  grid-gap: 12px;
}

/* Media Queries */
@media (max-width: 960px) {
  .blogs { grid-template-columns: repeat(auto-fit, minmax(31%, 1fr)); }
}
@media (max-width: 760px) {
  .blogs { grid-template-columns: repeat(auto-fit, minmax(48%, 1fr)); }
}
@media (max-width: 500px) {
  .blogs { grid-template-columns: repeat(auto-fit, minmax(100%, 1fr)); }
}
</style>