<template>
  <v-navigation-drawer v-model="drawer" app mobile-breakpoint="10024" color="primary" dark>
    <v-list nav dense shaped class="pl-0">
      <v-list-item-group v-model="selectedItem" color="white">
        <v-list-item v-for="(menu, i) in menus" :key="i" :to="menu.to">
          <v-list-item-icon class="mr-1 ml-2">
            <v-icon size="16">{{ menu.icon }}</v-icon>
          </v-list-item-icon>
          <v-list-item-content>
            <v-list-item-title v-text="menu.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list-item-group>
    </v-list> 
  </v-navigation-drawer>  
</template>

<script>
export default {
  data: () => ({
    menus: [
      { title: 'Home', icon: '', to: '/' },  
      { title: 'Courses', icon: '', to: '/courses' },
      // { title: 'About Us', icon: '', to: '/about' },
      { title: 'Contact Us', icon: '', to: '/contact' },
      { title: 'Blogs', icon: '', to: '/blogs' },
      { title: 'Instructor', icon: '', to: '/instructors' } 
    ],
    selectedItem: 1, 
  }),
  computed: {
    drawer: {
      get () {
        return this.$store.state.drawer
      },
      set (val) {
        this.$store.commit('SET_DRAWER', val)
      },
    },
  }
}
</script>