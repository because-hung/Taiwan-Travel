<template>
   <div class="swiperCom">
      <swiper
      :centeredSlides="true"
      :autoplay="{
      delay: 5000,
      disableOnInteraction: false,
    }"
      :spaceBetween="30"
    :effect="'fade'"
    :watchSlidesProgress="true"
    :watchSlidesVisibility="true"
    :pagination="{
      clickable: true,
    }"
    @autoplayTimeLeft="onAutoplayTimeLeft"
    :modules="modules"
    class="mySwiper"
        >
        <swiper-slide><img src="../assets/swiper/banner-1.png" alt=""></swiper-slide>
        <swiper-slide><img src="../assets/swiper/banner-2.png" alt=""></swiper-slide>
        <swiper-slide><img src="../assets/swiper/banner-3.png" alt=""></swiper-slide>
        <swiper-slide><img src="../assets/swiper/banner-4.png" alt=""></swiper-slide>
        <swiper-slide><img src="../assets/swiper/banner-5.png" alt=""></swiper-slide>
      </swiper>
    </div>
</template>
<script>
// import Swiper core and required modules

// Import Swiper Vue.js components
import { Swiper, SwiperSlide } from 'swiper/vue';

// Import Swiper styles
import 'swiper/css';
import "swiper/css/effect-fade";
import 'swiper/css/navigation';
import 'swiper/css/pagination';
import {EffectFade,Autoplay, Navigation, Pagination } from 'swiper';
import { ref } from 'vue';

export default {
    components: {
    Swiper,
    SwiperSlide,
  },
  setup() {
    const progressCircle = ref(null);
      const progressContent = ref(null);
      const onAutoplayTimeLeft = (s, time, progress) => {
        progressCircle.value.style.setProperty('--progress', 1 - progress);
        progressContent.value.textContent = `${Math.ceil(time / 1000)}s`;
      };
    return {
      onAutoplayTimeLeft,
        progressCircle,
        progressContent,
      modules: [EffectFade,Autoplay, Navigation, Pagination],
      
    }
  },
}
</script>
<style lang="scss">
.swiper-slide img{
    width: 100%;
    height: 800px;
}
.swiper-pagination-bullet{
    width: 20px;
    height: 20px;
    background: white;
}
</style>