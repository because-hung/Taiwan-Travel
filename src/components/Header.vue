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
    <div class="hamMenu" :class="{ openMenu: showMenu, closeMenu: !showMenu }">
      <ul>
        <div class="search-group">
          <search class="searchIcon" />
          <input type="text" placeholder="想去哪裡?" />
        </div>
        <li>找景點 <span>attraction</span></li>
        <li>找美食 <span>delicacy</span></li>
        <li>找活動 <span>activity</span></li>
        <li>探索更多 <span>more</span></li>
      </ul>
    </div>
    <div class="btn-group">
      <div class="btn-heart"><heart /></div>
      <div class="btn-QA"><QA /></div>
    </div>
    <div class="mobileMenu" @click="toggleMenu()">☰</div>
  </div>
</template>
<script lang="ts">
import logo from "../components/icon/logoSvg.vue"
import heart from "../components/icon/heartSvg.vue"
import QA from "../components/icon/QASvg.vue"
import search from "../components/icon/searchSvg.vue"
import { ref } from "vue"
export default {
  components: {
    logo,
    heart,
    QA,
    search,
  },
  setup() {
    const showMenu = ref<boolean>(false)
    function toggleMenu(): void {
      showMenu.value = !showMenu.value
    }
    return {
      toggleMenu,
      showMenu,
    }
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
  }
}
.btn-group {
  grid-column: 6 / 8;
  display: flex;
  .btn-heart {
    margin-right: pxToVw(17);
  }
}
.mobileMenu,
.hamMenu {
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
    z-index: 999;
  }
  .hamMenu {
    cursor: pointer;
    margin: 0;
    height: 100%;
    background: #fff;
    display: flex;
    flex-direction: column;
    position: absolute;
    color: #737373;
    top: 0;
    left: 0;
    right: 0;
    z-index: 99;
    transition: all 0.5s;
    ul {
      position: relative;
      top: 20%;
    }
    li {
      margin: 32px 0px;
      margin-left: 32px;
      list-style: none;
      margin-bottom: pxToVw(10);
      letter-spacing: 0.2em;
      cursor: pointer;
      span {
        text-transform: uppercase;
        margin-top: pxToVw(5);
        font-size: pxToVw(10);
        letter-spacing: 0.05em;
      }
    }
    .search-group {
      position: relative;
      input {
        width: 90%;
        padding: 10px 35px;
        padding-left: 67px;
      }
      input::placeholder {
        letter-spacing: 0.2em;
        font-size: 16px;
        transform: translateY(2px);
      }
      .searchIcon {
        position: absolute;
        top: 5px;
        left: 32px;
      }
    }
  }
  .openMenu {
    // left: 100vw;
     transform: translate(0);
  }
  .closeMenu {
    // left: 0;
    transform: translate(100%);
  }
}
</style>
