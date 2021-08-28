<template>
  <div>
    <v-container>
      <div class="display-1 mb-2">Our Courses</div>  
      <div class="courses">
        <CourseCard v-for="a in 10" :key="a" />
      </div>
    </v-container>  
  </div>  
</template>

<script>
import CourseCard from '../components/CourseCard.vue'
export default {
  components: { CourseCard }  
}
</script>