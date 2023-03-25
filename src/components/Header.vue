<template>
  <div class="container">
    <div class="logo"><logo /></div>
    <ul class="topMenu">
      <li>
        找景點 <span>attraction</span>
        <ul class="sub-item"></ul>
      </li>
      <li>找美食 <span>delicacy</span></li>
      <li>找活動 <span>activity</span></li>
      <li>探索更多 <span>more</span></li>
    </ul>
    <div class="btn-group">
      <div class="btn-heart"><heart /></div>
      <div class="btn-QA"><QA /></div>
    </div>
    <div class="mobileMenu">☰</div>
  </div>
</template>
<script lang="ts">
import logo from "../components/icon/logoSvg.vue"
import heart from "../components/icon/heartSvg.vue"
import QA from "../components/icon/QASvg.vue"
export default {
  components: {
    logo,
    heart,
    QA,
  },
}
</script>
<style lang="scss" scoped>
@import "../sass/pxToVw.scss";
.container {
  display: grid;
  align-items: center;
}
.logo {
  grid-column: 3 / 4;
}
.topMenu {
  display: flex;
  grid-column: 4 / 5;
  padding-left: 0;
  li {
    color: #737373;
    list-style: none;
    margin: pxToVw(0) pxToVw(24);
    text-align: center;
    margin-bottom: pxToVw(10);
    letter-spacing: 0.2em;
    position: relative;
    font-weight: 400;
    cursor: pointer;
    span {
      text-transform: uppercase;
      margin-top: pxToVw(5);
      display: block;
      font-size: pxToVw(10);
      letter-spacing: 0.05em;
    }
    .sub-items {
      display: none;
    }
  }
  li:hover {
    &::before {
      content: "";
      width: pxToVw(15);
      height: pxToVw(15);
      position: absolute;
      top: pxToVw(-35);
      left: 48%;
      transform: translateX(-50%);
      border-radius: 50%;
      background: #f1d675;
    }

    // .sub-item{
    //   display: block;
    // }
  }
}
.btn-group {
  grid-column: 6 / 8;
  display: flex;
  .btn-heart {
    margin-right: pxToVw(17);
  }
}
.mobileMenu {
   display: none;
  }
@media (max-width: 821px) {
  .topMenu,
  .btn-group {
    display: none;
  }
  .logo {
    grid-column: 1 / 4;
  }
  .mobileMenu {
    display: block;
    position: absolute;
    right: 30px;
    top: 40px;
    font-size: 36px;
    color: #769763;
  }
}
</style>
