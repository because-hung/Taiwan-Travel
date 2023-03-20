<template>
  <div>
    <Header />
    <Swiper />
    <Explore />
    <ParticipateEnjoy />
  </div>
</template>
<script lang="ts">
import Header from '../components/Header.vue'
import Swiper from '../components/Swiper.vue'
import Explore from '../components/Explore.vue'
import ParticipateEnjoy from '../components/ParticipateEnjoy.vue'
export default {
  components: {
    Header,
    Swiper,
    Explore,
    ParticipateEnjoy
  },
  setup() {
    return {}
  },
}
</script>
<style lang="scss"></style>
