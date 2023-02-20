<template>
  <div class="container">
    <div class="logo"><logo /></div>
    <ul class="topMenu">
      <li>
        找景點 <span>attraction</span>
        <ul class="sub-item">
        </ul>
      </li>
      <li>找美食 <span>delicacy</span></li>
      <li>找活動 <span>activity</span></li>
      <li>探索更多 <span>more</span></li>
    </ul>
    <div class="btn-group">
      <div class="btn-heart"><heart /></div>
      <div class="btn-QA"><QA /></div>
    </div>
  </div>
</template>
<script>
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
<style lang="scss">
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
    margin: 0px 24px;
    text-align: center;
    margin-bottom: 10px;
    letter-spacing: 0.2em;
    position: relative;
    font-weight: 400;
    cursor: pointer;
    span {
      text-transform: uppercase;
      margin-top: 5px;
      display: block;
      font-size: 10px;
      letter-spacing: 0.05em;
    }
    .sub-items {
      display: none;
    }
  }
  li:hover {
    &::before {
      content: "";
      width: 15px;
      height: 15px;
      position: absolute;
      top: -35px;
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
    margin-right: 17px;
  }
}
</style>
