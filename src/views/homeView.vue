<template>
  <div>
    <Header />
    <Swiper />
    <Explore />
  </div>
</template>
<script lang="ts">
import Header from '../components/Header.vue'
import Swiper from '../components/Swiper.vue'
import Explore from '../components/Explore.vue'
export default {
  components: {
    Header,
    Swiper,
    Explore
  },
  setup() {
    return {}
  },
}
</script>
<style lang="scss"></style>
