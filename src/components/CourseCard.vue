<template>
  <div class="course">
    <div class="course__img">
      <div class="cart__icon">
        <v-btn icon class="primary">
          <v-icon v-text="'mdi-cart'" color="white" small />
        </v-btn>
      </div>
      <img src="https://www.socialsamosa.com/wp-content/uploads/2016/06/digital-class.jpg" alt="Course Name">
    </div>
    <div class="pa-3">
      <div class="price d-flex justify-space-between align-center">
        <div class="py-1 px-2" style="background-color: #f6f1fe; border-radius: 4px; font-size: 10px; letter-spacing: .5px; font-weight: 500;">UX/UI Design</div>
        <div class="price__amount font-weight-bold">$100</div>
      </div>
      <div class="title my-2" style="line-height: 1.25;">Lorem ipsum dolor sit amet consectetur adipisicing elit.</div>
      <v-divider />
      <div class="mt-2 d-flex justify-space-between">
        <div class="d-flex" style="grid-gap: 12px;">
          <div class="d-flex align-center" style="grid-gap: 6px;">
            <div class="d-flex align-center justify-center" style="border: .5px solid #f6f1fe; border-radius: 50%; height: 28px; width: 28px;">
              <v-icon v-text="'mdi-account'" color="secondary" size="14" />
            </div>
            <div style="font-size: 12px; font-weight: 500;">4k</div>
          </div>
          <div class="d-flex align-center" style="grid-gap: 6px;">
            <div class="d-flex align-center justify-center" style="border: .5px solid #f6f1fe; border-radius: 50%; height: 28px; width: 28px;">
              <v-icon v-text="'mdi-eye'" color="success" size="14" />
            </div>
            <div style="font-size: 12px; font-weight: 500;">9k</div>
          </div>
          <div class="d-flex align-center" style="grid-gap: 6px;">
            <div class="d-flex align-center justify-center" style="border: .5px solid #f6f1fe; border-radius: 50%; height: 28px; width: 28px;">
              <v-icon v-text="'mdi-star'" color="primary" size="14" />
            </div>
            <div style="font-size: 12px; font-weight: bold;">4.5</div>
          </div>
        </div>
        <v-avatar size="36px">
          <img alt="Avatar" src="https://avatars0.githubusercontent.com/u/9064066?v=4&s=460">
        </v-avatar>
      </div>
    </div>
  </div>  
</template>

<style>
.courses {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(22%, 1fr));
  grid-gap: 20px;
}
.course {
  box-shadow: 0 1px 10px 0 rgb(0 0 0 / 10%);
  border-radius: 6px;
  overflow: hidden;
}
.course__img { 
  position: relative;
  height: 220px; 
}
.cart__icon {
  position: absolute;
  top: 8px;
  right: 8px;
}
@media (max-width: 1060px) {
  .courses { grid-template-columns: repeat(auto-fit, minmax(31%, 1fr)); grid-gap: 16px; }
}
@media (max-width: 860px) {
  .courses { grid-template-columns: repeat(auto-fit, minmax(48%, 1fr)); grid-gap: 16px; }
}
@media (max-width: 500px) {
  .courses { grid-template-columns: repeat(auto-fit, minmax(100%, 1fr)); grid-gap: 12px; }
}
</style>