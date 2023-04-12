<template>
  <div class="explore">
    <div class="section">
      <div class="info">
        <div class="slogan">Explore</div>
        <div class="title">探索台灣每個角落</div>
        <p>
          台灣擁有高山峽谷及四面環海地理特性，因此充滿各種自然景致等待人們發現，而各縣市有其特色文化與在地必嚐美食，無論想要來場山林陶冶身心之旅，抑或體驗歷史人文深度旅行，都能在台灣這片土地上踏尋。
        </p>
      </div>
      <div class="img-intro">
        <div
          class="imgBox"
          :data-view="item"
          v-for="(item, i) in imgData"
          :key="i"
        ></div>
        <!-- <img :src="getImageUrl(item.img)" alt="" /> -->
      </div>
    </div>
    <div class="section2">
      <ul>
        <li v-for="(city, i) in cityData" :key="i">{{ city }}</li>
      </ul>
      <div class="img-intro2">
        <div
          class="imgBox2"
          :data-view="item"
          v-for="(item, i) in imgData2"
          :key="i"
        ></div>
        <!-- <img :src="getImageUrl(item.img)" alt="" /> -->
      </div>
    </div>
  </div>
</template>
<script lang="ts">
export default {
  setup() {
    let imgData: string[] = [
      "台東金剛大道",
      "日月潭文武廟",
      "台北寧夏夜市",
      "南投合歡山",
    ]
    let imgData2: string[] = [
      "北投圖書館",
      "樹林頂山步道",
      "水里車埕車站",
      "台中植物園",
      "台南孔廟",
    ]
    let cityData: string[] = [
      "都市文情：北台灣",
      "休閒樂活：中台灣",
      "人情小吃：南台灣",
      "自然生態：東台灣",
      "小島風情：離島",
    ]
    // function getImageUrl(name: string) { // require img 的方式
    //   return new URL(`../assets/explore/${name}.jpeg`, import.meta.url).href
    // }
    return { imgData, imgData2, cityData }
  },
}
</script>
<style lang="scss" scoped>
@import "../sass/pxToVw.scss";
.explore {
  margin-left: pxToVw(140);
}

.img-intro,
.img-intro2 {
  display: flex;
  $assetsPath: "../assets/explore";
  @for $i from 1 through 5 {
    .imgBox:nth-of-type(#{$i}) {
      background-image: url(#{$assetsPath}/explore_0#{$i}.jpeg);
      width: pxToVw(230);
      height: pxToVw(300);
      background-size: pxToVw(230) pxToVw(300);
      background-repeat: no-repeat;
      background-position: center;
    }
    .imgBox2:nth-of-type(#{$i}) {
      background-image: url(#{$assetsPath}/explore_0#{$i+4}.jpeg);
      width: pxToVw(230);
      height: pxToVw(300);
      background-size: pxToVw(230) pxToVw(300);
      background-repeat: no-repeat;
      background-position: center;
    }
  }
  .imgBox,
  .imgBox2 {
    margin-right: pxToVw(40);
    position: relative;
    cursor: pointer;
    transition: 0.5s;
    &:hover {
      background-size: pxToVw(300) pxToVw(360);
    }
  }
  .imgBox::after,
  .imgBox2::after {
    content: attr(data-view);
    position: absolute;
    right: pxToVw(-25);
    color: #737373;
    width: pxToVw(18);
    font-size: pxToVw(16);
  }
  h4 {
    width: pxToVw(18);
    margin: pxToVw(0);
    margin-left: pxToVw(4);
    color: #737373;
  }
}
.section {
  margin-top: pxToVw(144);
  display: flex;
  justify-content: space-between;
  .info {
    width: 30%;
    margin-right: pxToVw(36);
    .slogan {
      color: #769763;
      font-weight: 600;
      font-size: pxToVw(48);
    }
    .title {
      font-weight: 400;
      font-size: pxToVw(48);
      color: #737373;
      margin: pxToVw(20) pxToVw(0);
    }
    p {
      font-size: pxToVw(18);
      line-height: 1.4;
      letter-spacing: 0.15em;
      text-align: justify;
    }
  }
}
.section2 {
  margin-top: pxToVw(40);
  display: flex;
  ul {
    padding-left: pxToVw(20);
    li {
      position: relative;
      list-style-type: none;
      margin-bottom: pxToVw(32);
      letter-spacing: 0.15em;
      font-weight: 400;
      font-size: pxToVw(18);
      line-height: pxToVw(26);
      cursor: pointer;
    }
    li::before {
      content: "";
      position: absolute;
      height: pxToVw(8);
      width: pxToVw(8);
      background-color: #f1d675;
      border-radius: 50%;
      top: 40%;
      left: pxToVw(-25);
      transform: translate(50%, -50%);
    }
    li:hover {
      color: #769763;
    }
  }
  .img-intro2 {
    display: flex;
    margin-right: 2%;
    margin-left: pxToVw(80);
    h4 {
      width: pxToVw(18);
      margin: pxToVw(0);
      margin-left: pxToVw(4);
      color: #737373;
    }
  }
}

@media (max-width: 821px) {
  .explore {
    margin-left: 0;
  }
  .img-intro,
  .img-intro2 {
    .imgBox,
    .imgBox2 {
      margin-right: pxToVw(60);
    }
  }
}

@media (max-width: 415px) {
  .section{
    margin-bottom: 50px;
    .info{
      p{
      display: none;
      }
    }
  }
  .section2{
    ul{
      display: none;
    }
  }
}
</style>
