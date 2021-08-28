<template>
  <div class="Home">
    <div class="home__banner">
      <v-container>
        <div class="text-h5 text-sm-h4 text-md-h3 text-lg-h2 font-weight-bold">Move beyond <br>the limitations of <br>e-learning.</div>
        <div class="my-4 my-sm-5 my-md-6 my-lg-7">Anytime, anywhere to do discover yourself.</div>
        <v-btn large class="elevation-0" color="secondary" width="150">get started</v-btn>
      </v-container>
    </div>
    <div class="my-10 my-sm-12 my-md-14 my-lg-16 items">
      <div v-for="(item, i) in items" :key="i" class="item">
        <div class="item__circle" :style="{ backgroundColor: item.bg }">
          <v-icon :color="item.color">{{ item.icon }}</v-icon>
        </div>
        <div class="title" v-text="item.title" />
      </div>
    </div>
    <!-- Courses -->
    <div class="my-10 my-sm-12 my-md-14 my-lg-16">
      <v-container>
        <div class="d-flex flex-column flex-sm-row justify-space-between">
          <div class="text-h5 text-sm-h4 text-md-h3">Most Popular Courses</div>
          <div class="d-flex align-center mt-2 mt-sm-0" style="grid-gap: 10px;">
            <v-select dense hide-details outlined style="max-width: 150px;" :items="['Fashion', 'Web Dev', 'Health', 'Design']" value="Fashion" />
            <v-btn icon class="grey lighten-2">
              <v-icon v-text="'mdi-chevron-left'" />
            </v-btn>
            <v-btn icon class="primary">
              <v-icon v-text="'mdi-chevron-right'" />
            </v-btn>
          </div>
        </div>
        <div class="courses mt-6 mt-sm-7 mt-md-8 mt-lg-9">
          <CourseCard v-for="a in 4" :key="a" />
        </div>
      </v-container>
    </div>

    <!-- Popular Courses -->
    <div class="my-10 my-sm-12 my-md-14 my-lg-16">
      <v-container>
        <div class="d-flex flex-column flex-sm-row justify-space-between">
          <div class="text-h5 text-sm-h4 text-md-h3">Trending Courses</div>
          <div class="d-flex align-center mt-2 mt-sm-0" style="grid-gap: 10px;">
            <v-btn icon class="grey lighten-2">
              <v-icon v-text="'mdi-chevron-left'" />
            </v-btn>
            <v-btn icon class="primary">
              <v-icon v-text="'mdi-chevron-right'" />
            </v-btn>
          </div>
        </div>
        <div class="courses mt-6 mt-sm-7 mt-md-8 mt-lg-9">
          <CourseCard v-for="a in 4" :key="a" />
        </div>
      </v-container>
    </div>

    <div class="join__us">
      <v-container class="fill-height">
        <div class="join__us__content">
          <div class="text-h5 text-sm-h5 text-md-h4 text-lg-h3">Do you want to an instructor?</div>
          <v-btn class="secondary elevation-0 mt-3" width="130">join us</v-btn>
        </div>
      </v-container>
    </div>
  </div>
</template>

<script>
import CourseCard from '../components/CourseCard.vue'
export default {
  components: { CourseCard },
  data: () => ({
    items: [
      { title: 'Online Tutoring', icon: 'mdi-cast-education', color: '#fd8870', bg: '#feeae9' },
      { title: 'Lifetime Access', icon: 'mdi-briefcase-clock', color: '#b388fe', bg: '#f6f1fe' },
      { title: 'Active Learning', icon: 'mdi-account', color: '#ff8623', bg: '#fff4e8' },
      { title: '1k+ Courses', icon: 'mdi-post', color: '#41b365', bg: '#e6f3ee' }
    ]
  })
}
</script>

<style scoped>
.home__banner {
  background-color: #f7f6ee;
  height: 70vh;
  display: flex;
  align-items: center;
}
.items {
  display: flex;
  justify-content: space-around;
}
.item {
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 12px;
  grid-gap: 12px;
}
.item__circle {
  height: 50px;
  width: 50px;
  border-radius: 50%;
  display: flex;
  justify-content: center;
  align-items: center;
}

/* Join Us */
.join__us {
  background-image: url('https://sbfurniturenepal.com/web/image/15474/banner-1.jpg?access_token=c563c547-6f50-4c97-be53-10785d61c130');
  background-position: center center;
  background-size: cover;
  height: 30vh;
}
@media (max-width: 960px) {
  .home__banner { height: 62vh; }
  .items { 
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(45%, 1fr));
    grid-gap: 30px;
  }
  .item { justify-content: start; }
}
@media (max-width: 760px) {
  .home__banner { height: 55vh; }
}
@media (max-width: 500px) {
  .home__banner { height: 40vh; }
  .items { grid-template-columns: repeat(auto-fit, minmax(100%, 1fr)); grid-gap: 10px; }
}
</style>
