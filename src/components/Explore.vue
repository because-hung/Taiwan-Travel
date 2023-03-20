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
      "南投日月潭文武廟",
      "台北寧夏夜市",
      "南投合歡山",
    ]
    let imgData2: string[] = [
      "北投圖書館",
      "樹林三角埔頂山步道",
      "水里車埕車站",
      "台中科博館植物園",
      "台南孔廟",
    ]
    let cityData: string[] = [
      "都市文情：北台灣",
      "休閒樂活：中台灣",
      "人情小吃：南台灣",
      "自然生態：東台灣",
      "小島風情：離島地區",
    ]
    // function getImageUrl(name: string) { // require img 的方式
    //   return new URL(`../assets/explore/${name}.jpeg`, import.meta.url).href
    // }
    return { imgData, imgData2, cityData }
  },
}
</script>
<style lang="scss" scoped>
.explore {
  margin-left: 200px;
}

.img-intro,
.img-intro2 {
  display: flex;
  margin-right: 2%;
  $assetsPath: "../assets/explore";
  @for $i from 1 through 5 {
    .imgBox:nth-of-type(#{$i}) {
      background-image: url(#{$assetsPath}/explore_0#{$i}.jpeg);
      width: 230px;
      height: 300px;
      background-size: 230px 300px;
      background-repeat: no-repeat;
      background-position: center;
    }
    .imgBox2:nth-of-type(#{$i}) {
      background-image: url(#{$assetsPath}/explore_0#{$i+4}.jpeg);
      width: 230px;
      height: 300px;
      background-size: 230px 300px;
      background-repeat: no-repeat;
      background-position: center;
    }
  }
  .imgBox,
  .imgBox2 {
    margin-right: 2vw;
    position: relative;
    cursor: pointer;
    transition: .5s;
    &:hover {
      background-size: 300px 360px;
    }
  }
  .imgBox::after,
  .imgBox2::after {
    content: attr(data-view);
    position: absolute;
    right: -22px;
    color: #737373;
    width: 18px;
  }
  h4 {
    width: 18px;
    margin: 0px;
    margin-left: 4px;
    color: #737373;
  }
}
.section {
  margin-top: 144px;
  display: flex;
  justify-content: space-between;
  .info {
    width: 30%;
    margin-right: 36px;
    .slogan {
      color: #769763;
      font-weight: 600;
      font-size: 48px;
    }
    .title {
      font-weight: 400;
      font-size: 48px;
      color: #737373;
      margin: 20px 0px;
    }
    p {
      font-size: 18px;
      line-height: 26px;
      letter-spacing: 0.15em;
      text-align: justify;
    }
  }
}
.section2 {
  margin-top: 24px;
  display: flex;
  ul {
    margin-right: 75px;
    padding-left: 20px;
    li {
      position: relative;
      list-style-type: none;
      margin-bottom: 32px;
      letter-spacing: 0.15em;
      font-weight: 400;
      font-size: 18px;
      line-height: 26px;
      cursor: pointer;
    }
    li::before {
      content: "";
      position: absolute;
      height: 8px;
      width: 8px;
      background-color: #f1d675;
      border-radius: 50%;
      top: 40%;
      left: -25px;
      transform: translate(50%, -50%);
    }
    li:hover {
      color: #769763;
    }
  }
  .img-intro2 {
    display: flex;
    margin-right: 2%;
    h4 {
      width: 18px;
      margin: 0px;
      margin-left: 4px;
      color: #737373;
    }
  }
}
</style>
