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
      <swiper-slide
        ><img src="../assets/swiper/banner-1.png" alt=""
      /></swiper-slide>
      <swiper-slide
        ><img src="../assets/swiper/banner-2.png" alt=""
      /></swiper-slide>
      <swiper-slide
        ><img src="../assets/swiper/banner-3.png" alt=""
      /></swiper-slide>
      <swiper-slide
        ><img src="../assets/swiper/banner-4.png" alt=""
      /></swiper-slide>
      <swiper-slide
        ><img src="../assets/swiper/banner-5.png" alt=""
      /></swiper-slide>
    </swiper>
    <div class="search-group">
      <search />
      <input type="text" />
      <button>Go</button>
    </div>
  </div>
</template>
<script>
// import Swiper core and required modules
// Import Swiper Vue.js components
import { Swiper, SwiperSlide } from "swiper/vue"
// Import Swiper styles
import "swiper/css"
import "swiper/css/effect-fade"
import "swiper/css/navigation"
import "swiper/css/pagination"
import { EffectFade, Autoplay, Navigation, Pagination } from "swiper"
import { ref } from "vue"
import search from "../components/icon/searchSvg.vue"
export default {
  components: {
    Swiper,
    SwiperSlide,
    search,
  },
  setup() {
    const progressCircle = ref(null)
    const progressContent = ref(null)
    const onAutoplayTimeLeft = (s, time, progress) => {
      progressCircle.value.style.setProperty("--progress", 1 - progress)
      progressContent.value.textContent = `${Math.ceil(time / 1000)}s`
    }
    return {
      onAutoplayTimeLeft,
      progressCircle,
      progressContent,
      modules: [EffectFade, Autoplay, Navigation, Pagination],
    }
  },
}
</script>
<style lang="scss" scoped>
.swiper-slide img {
  width: 100%;
  height: 800px;
}
.swiper-pagination-bullet {
  width: 20px;
  height: 20px;
  background: white;
}
.swiperCom {
  position: relative;
}
.search-group {
  position: absolute;
  bottom: 15%;
  left: 50%;
  transform: translate(-50%, -15%);
  display: flex;
  align-items: center;
  z-index: 2;
  background: #ffffff;
  box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
  border-radius: 5px;
  padding: 8px 16px;
  width: 512px;
  input{
    width: 100%;
    border: none;
    &:focus{
      outline: none;
    }
  }
  button{
    border-radius: 50px;
    width: 60px;
    height: 25px;
    background: white;
    color: #769763;
    border: 1px solid #769763;
    cursor: pointer;
  }
}
</style>