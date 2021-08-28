<template>
  <v-container>
    <div class="display-1">Our Blogs</div>
    <div class="blogs mt-3">
      <BlogCard v-for="a in 10" :key="a" />
    </div>
  </v-container>  
</template>

<script>
import BlogCard from '../components/BlogCard.vue'
export default {
  components: { BlogCard }  
}
</script>