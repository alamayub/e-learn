<template>
  <div>
    <v-container class="instructors">  
      <div class="instructor pa-3 pa-sm-4 pa-md-5 pa-lg-6" v-for="a in 5" :key="a">
        <div class="instructor__img">
          <img src="https://www.stata-press.com/img/instructors-300.png" alt="instructor name">  
        </div>
        <div>
          <div class="title">Dr. Mathew Gordan</div> 
          <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Asperiores, rerum hic! Consequatur veritatis pariatur molestiae! Dolore non accusantium odit deleniti sequi excepturi aut ipsa! Natus placeat corrupti distinctio laborum odit?</p> 
          <span>Microbiology, 2 yrs</span>
        </div>
      </div>    
    </v-container>
  </div>  
</template>

<style scoped>
.instructors {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(48%, 1fr));
  grid-gap: 20px;  
}
.instructor {
  display: flex;
  border: 1px solid rgb(0 0 0 / 5%); 
  grid-gap: 20px; 
}
p, span {
  line-height: 1.3;
  font-size: 14px;
  letter-spacing: .25px;  
}
span { color: grey; }
@media (max-width: 660px) {
  .instructors { grid-template-columns: repeat(auto-fit, minmax(100%, 1fr)); }  
}
@media (max-width: 500px) {
  .instructor {
    flex-direction: column;  
  }  
}
</style>