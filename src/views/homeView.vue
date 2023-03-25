<template>
  <div>
    <Header />
    <Swiper />
    <Explore />
    <ParticipateEnjoy />
    <Footer />
  </div>
</template>
<script lang="ts">
import Header from '../components/Header.vue'
import Swiper from '../components/Swiper.vue'
import Explore from '../components/Explore.vue'
import ParticipateEnjoy from '../components/ParticipateEnjoy.vue'
import Footer from '../components/Footer.vue'
export default {
  components: {
    Header,
    Swiper,
    Explore,
    ParticipateEnjoy,
    Footer
  },
  setup() {
    return {}
  },
}
</script>
<style lang="scss">
*{
  box-sizing: border-box;
}</style>
 