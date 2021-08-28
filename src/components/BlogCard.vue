<template>
  <div class="blog__card">
    <div class="blog__img">
      <img src="https://images.unsplash.com/photo-1432821596592-e2c18b78144f?ixid=MnwxMjA3fDB8MHxzZWFyY2h8MXx8YmxvZ3xlbnwwfHwwfHw%3D&ixlib=rb-1.2.1&w=1000&q=80" alt="">  
    </div>
    <div class="blog__content pa-3">
      <div class="blog__title">Lorem ipsum dolor sit amet consectetur adipisicing elit. Exercitationem in molestias, pariatur sequi ratione ea.</div> 
      <p class="ma-0 mt-2">22, June 2021</p>
    </div>   
  </div>  
</template>

<style scoped>
.blog__card {
  border-radius: 6px;  
  overflow: hidden;
  box-shadow: 0 1px 10px 0 rgb(0 0 0 / 10%);
}
.blog__title {
  font-weight: 600;
  font-size: 18px;  
  line-height: 1.3;
  overflow: hidden;
  text-overflow: ellipsis;
  display: -webkit-box;
  -webkit-line-clamp: 2;
  -webkit-box-orient: vertical;
}
p { 
  color: grey;
  font-size: 13px;
}
</style>