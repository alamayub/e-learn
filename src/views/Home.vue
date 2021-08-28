<template>
  <div class="Home">
    <div class="home__banner">
      <v-container class="home__content">
        <div class="d-flex flex-column justify-center">
          <div class="text-h5 text-sm-h4 text-md-h3 text-lg-h2 font-weight-bold">Move beyond <br>the limitations of <br>e-learning.</div>
          <div class="my-4 my-sm-5 my-md-6 my-lg-7">Anytime, anywhere to do discover yourself.</div>
          <v-btn large class="elevation-0" color="secondary" max-width="150" to="/contact">get started</v-btn>
        </div>
        <div class="home__banner__img">
          <img src="https://versanthealth.com/wp-content/uploads/2019/06/guy-glasses-laptop.jpg" alt="">
        </div>
      </v-container>
    </div>
    <div class="my-10 my-sm-12 my-md-14 my-lg-16 items">
      <div v-for="(item, i) in items" :key="i" class="item">
        <div class="item__circle" :style="{ backgroundColor: item.bg }">
          <v-icon :color="item.color">{{ item.icon }}</v-icon>
        </div>
        <div style="font-weight: 500; letter-spacing: .5px;" v-text="item.title" />
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

    <!-- About Us -->
    <div class="py-10 py-sm-12 py-md-14 py-lg-16" style="background-color: #f7f6ee;">
      <v-container class="home__about">
        <div class="d-flex flex-column" style="grid-gap: 20px;">
          <div class="display-1 font-weight-bold">Get know about us</div>
          <div>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Ratione maxime quam possimus, facilis, enim rem quo ipsum, cumque pariatur tempore qui. Ex unde id adipisci explicabo veniam, molestias cum? Enim?</div>
          <ul>
            <li v-for="a in 4" :key="a">Lorem ipsum dolor, sit amet consectetur adipisicing elit.</li>
          </ul>
          <v-btn color="secondary elevation-0"  max-width="150" to="/about">
            <span>explore</span>
            <v-icon v-text="'mdi-chevron-right'" right size="16" />
          </v-btn>
        </div>
        <div>
          <img src="https://s3.envato.com/files/318012278/_MG_0451.jpg" alt="">
        </div>
      </v-container>
    </div>

    <!-- Latest Post -->
    <div class="py-10 py-sm-12 py-md-14 py-lg-16">
      <v-container>
        <div class="d-flex justify-space-between">
          <div class="headline font-weight-bold">Our Latest Post</div>
          <v-btn class="secondary white--text elevation-0" height="30" to="/blogs">
            <span>more</span>
            <v-icon right size="16">mdi-arrow-right</v-icon>
          </v-btn>
        </div>
        <div class="blogs mt-3">
          <BlogCard v-for="a in 4" :key="a" />
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
import BlogCard from '../components/BlogCard.vue'
export default {
  components: { CourseCard, BlogCard },
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
.home__content { 
  display: grid;
  grid-template-columns: calc(50% - 30px) calc(50% - 30px);
  grid-gap: 60px;
}
.home__banner__img { max-height: 70vh; }
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

/* Home About */
.home__about {
  display: grid;
  grid-template-columns: calc(50% - 40px) calc(50% - 40px);
  grid-gap: 80px;
  font-size: 14px;
  align-items: center;
}
@media (max-width: 1060px) {
  .home__about { grid-template-columns: calc(50% - 30px) calc(50% - 30px); grid-gap: 60px; }
}
@media (max-width: 960px) {
  .home__banner { height: 62vh; }
  .home__banner__img { max-height: 62vh; }
  .items { 
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(45%, 1fr));
    grid-gap: 30px;
  }
  .item { justify-content: start; padding: 9px; }
  .home__about { grid-template-columns: calc(50% - 25px) calc(50% - 25px); grid-gap: 50px; }
}
@media (max-width: 760px) {
  .home__banner { height: 55vh; }
  .home__banner__img { max-height: 55vh; }
  .home__about { grid-template-columns: calc(50% - 20px) calc(50% - 20px); grid-gap: 40px; }
  
}
@media (max-width: 660px) {
  .home__about { grid-template-columns: repeat(auto-fit, minmax(100%, 1fr)); grid-gap: 30px; }
  .home__content { grid-template-columns: 100%; }
  .home__banner__img { display: none; }
}
@media (max-width: 500px) {
  .home__banner { height: 40vh; }
  .items { grid-template-columns: repeat(auto-fit, minmax(100%, 1fr)); grid-gap: 10px; }
  .item { padding: 6px; }
}
</style>
