<template>
  <swiper  :spaceBetween="30" :centeredSlides="true" :autoplay="{
    delay: 2500,
    disableOnInteraction: false,
  }" :pagination="{
        clickable: true,
      }" :navigation="true" :modules="modules" class="mySwiper swipper-slider">
    <swiper-slide><img src="/img/img1.png" alt=""></swiper-slide>
    <swiper-slide><img src="/img/img2.png" alt=""></swiper-slide>
    <swiper-slide><img src="/img/img3.png" alt=""></swiper-slide>
    <swiper-slide><img src="/img/img4.png" alt=""></swiper-slide>
    <swiper-slide><img src="/img/img5.png" alt=""></swiper-slide>


  </swiper>
</template>
<script> 
import { Swiper, SwiperSlide } from 'swiper/vue'; 
import 'swiper/css'; 
import 'swiper/css/pagination';
import 'swiper/css/navigation'; 
// import '@/style.css'; 
import { Autoplay, Pagination, Navigation } from 'swiper/modules';

export default {
  components: {
    Swiper,
    SwiperSlide,
  },
  setup() {
    return {
      modules: [Autoplay, Pagination, Navigation],
    };
  },
};
</script>
<style scoped>
.swipper-slider {
  margin-top: 100px;  
  padding: 2rem;
  height: 100vh;  
  background-color: #f8f9fa;
}
</style>