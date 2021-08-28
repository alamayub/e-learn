<template>
  <v-app-bar app color="white" height="70" elevate-on-scroll>
    <div class="logo font-weight-bold title">
      <span class="primary--text">e</span><span>-learn</span>
    </div> 
    <div class="ml-md-8 ml-lg-10 d-none d-sm-none d-md-block nav">
      <v-btn text active-class="active__nav" tile v-for="(nav, n) in navs" :key="n" :to="nav.to">
        <span>{{ nav.title }}</span>
      </v-btn>
    </div>
    <v-spacer />
    <div class="mr-0 mr-md-3">
      <v-btn icon height="36" width="36">
        <v-icon size="16" v-text="'mdi-magnify'" />
      </v-btn>
      <v-badge bordered color="primary" content="3">
        <v-btn icon height="36" width="36">
          <v-icon size="16" v-text="'mdi-cart'" />
        </v-btn>
      </v-badge>  
    </div>
    <v-app-bar-nav-icon @click.stop="setDrawer(!drawer)" class="white d-block d-sm-block d-md-none ml-3" />
    <v-divider class="primary d-none d-sm-none d-md-block" vertical />
    <div class="ml-3 d-none d-sm-none d-md-flex" style="grid-gap: 8px;">
      <v-btn color="secondary" tile text>Sign In</v-btn>
      <v-btn color="primary" class="elevation-0 black--text">Register</v-btn>  
    </div>
  </v-app-bar>  
</template>

<script>
import { mapState, mapMutations } from 'vuex'
export default {
  data: () => ({
    navs: [
      { title: 'Home', icon: '', to: '/' },  
      { title: 'About', icon: '' },
      { title: 'Courses', icon: '' },
      { title: 'Blog', icon: '' },
      { title: 'Reviews', icon: '' },
      { title: 'Instructor', icon: '' } 
    ]  
  }),
  computed: {
    ...mapState(['drawer']),
  },
  methods: {
    ...mapMutations({
      setDrawer: 'SET_DRAWER',
    }),
  },  
}
</script>

<style>
.nav .theme--light.v-btn--active:hover::before, .nav .theme--light.v-btn--active::before { opacity: 0 !important; }
.nav .v-btn { height: 70px !important; }
.active__nav {
  border-bottom: 3px solid #4a4dc7;
  color: #4a4dc7 !important;
  font-weight: 500 !important;
}
.v-divider--vertical {
  margin-top: 12px !important;  
  max-height: 40px !important;
  min-height: 40px !important;  
}

.v-badge__wrapper {
  left: -12px !important;
  top: 10px !important;
}
.v-badge__badge {
  font-size: 7px !important;
  height: 14px !important;
  min-width: 14px !important;
  padding: 4px !important;
}
</style>