<template>
  <div class="wrap">
    <div class="participate">
      <div class="pic">
        <img :src="picCom" alt="" />
      </div>
      <div class="txt">
        <h2>Participate</h2>
        <h2>參與四季的更迭</h2>
        <h5>根據季節的熱門活動主題，邀請你一同享受旅行中的每一個時刻。</h5>
        <ul>
          <li @mouseenter="changePic(1)">精彩藝術知性之旅</li>
          <li @mouseenter="changePic(2)">好廟好妙求神問卜</li>
          <li @mouseenter="changePic(3)">親自踏上山海之旅</li>
          <li @mouseenter="changePic(4)">體驗台灣文化慶典</li>
        </ul>
      </div>
    </div>
    <div class="enjoy">
      <div class="txt">
        <div class="slogan">
          <h2>Enjoy</h2>
          <h2>享受在地獨特風味</h2>
        </div>
        <div class="title">
          <p>
            充斥在台灣大街小巷的在地美食，融合當地生活與文化特色，發展出各式各樣風味，從銅板小吃到精緻料理，數不清的美味讓你飽餐一頓。
          </p>
          <button>享受更多美食</button>
        </div>
      </div>
      <div class="pic">
        <div class="swiperCom">
          <swiper
            :centeredSlides="true"
            :autoplay="{
              delay: 3000,
              disableOnInteraction: false,
            }"
            :loop="true"
            :modules="modules"
            :slides-per-view="4"
            :spaceBetween="30"
            :pagination="{ clickable: true }"
            class="mySwiper"
          >
            <swiper-slide
              ><div class="info">
                <h2>祥發海產餐廳</h2>
                <p>
                  位面對東石舊漁港，堤防外有一長排竹蚵屋，是每日青蚵嫂集體剖蚵的好所在，所以在祥發用餐，不但可以品嚐美味，還可以欣賞當地人文風景及剝蚵的光景。
                </p>
              </div>
              <img src="../assets/enjoy/enjoy_01.png" alt=""
            /></swiper-slide>
            <swiper-slide
              ><div class="info">
                <h2>石碇一粒粽</h2>
                <p>
                  粽子主打不油膩、吃了不脹氣，且選用最優質的材料，其中又以桂花粽最為特別，將整朵桂花加入粽子做調味，品嘗粽子的同時也能嚐到桂花香。
                </p>
              </div>
              <img src="../assets/enjoy/enjoy_02.png" alt=""
            /></swiper-slide>
            <swiper-slide
              ><div class="info">
                <h2>鄭記香腸</h2>
                <p>
                  位於小琉球的老街上，最古早的鄭記琉球香腸老店創立於民國43年，已成為小琉球當地的名產之一。
                </p>
              </div>
              <img src="../assets/enjoy/enjoy_03.png" alt=""
            /></swiper-slide>
            <swiper-slide>
              <div class="info">
                <h2>兩支北方麵食館</h2>
                <p>
                  專營北方麵食點心，從各式蒸餃、牛肉麵、酸辣麵等風味佳餚，堅持道地美味的執著，從醒麵、桿皮、包餡到成品，每一個環節都是對客戶的尊重與責任。
                </p>
              </div>
              <img src="../assets/enjoy/enjoy_04.png" alt=""
            /></swiper-slide>
            <swiper-slide
              ><div class="info">
                <h2>阿妃健康廚房</h2>
                <p>
                  每顆水餃從肉餡、使用豐富的蔬菜、調味料的比例、水餃皮的手感與功夫，層層步驟讓水餃能兼具口感與高纖維，也讓營養價值更高。
                </p>
              </div>
              <img src="../assets/enjoy/enjoy_05.png" alt=""
            /></swiper-slide>
            <swiper-slide
              ><div class="info">
                <h2>鶴岡紅茶舖</h2>
                <p>
                  店內販售花蓮瑞穗有機生態農場所種植的有機茶，坐下品嚐一杯香甜回甘的好茶，可以讓人暫時放掉煩惱，享受純淨的片刻。
                </p>
              </div>
              <img src="../assets/enjoy/enjoy_06.png" alt=""
            /></swiper-slide>
            <swiper-slide
              ><div class="info">
                <h2>三家村陽春麵</h2>
                <p>
                  餐點上桌前，將佐料瑤舀進碗內，再加入一大早熬製的大骨高湯，最後放進麵條，保持麵體彈性口感不軟爛。
                </p>
              </div>
              <img src="../assets/enjoy/enjoy_07.png" alt=""
            /></swiper-slide>
          </swiper>
        </div>
      </div>
    </div>
  </div>
</template>
<script lang="ts">
import { Pagination, Autoplay } from "swiper"
import { Swiper, SwiperSlide } from "swiper/vue"
import "swiper/css"
import "swiper/css/pagination"
import { computed, ref } from "vue"
export default {
  components: {
    Swiper,
    SwiperSlide,
  },
  setup() {
    const showPic = ref(1)
    function changePic(num: number) {
      showPic.value = num
    }

    const picCom = computed(() => {
      let defaultPic = new URL(
        `../assets/participate/participate_${showPic.value}.png`,
        import.meta.url
      ).href
      let res
      if (showPic.value !== 1) {
        res = new URL(
          `../assets/participate/participate_${showPic.value}.png`,
          import.meta.url
        ).href
      } else {
        res = defaultPic
      }
      return res
    })
    return {
      changePic,
      picCom,
      modules: [Pagination, Autoplay],
    }
  },
}
</script>
<style lang="scss" scoped>
.participate {
  margin-top: 100px;
  display: flex;
  align-items: center;
  .pic {
    width: 1000px;
    height: 466px;
    margin-right: 80px;
    img {
      width: 100%;
      height: 100%;
      vertical-align: middle;
    }
  }
  .txt {
    h2 {
      font-size: 48px;
    }
    h2:first-of-type {
      color: #769763;
      margin-top: 20px;
    }
    h2:last-of-type {
      color: #737373;
    }
    h5 {
      font-size: 18px;
    }
    ul {
      padding-left: 20px;
    }
    li {
      position: relative;
      font-size: 18px;
      padding: 16px 8px;
      color: #737373;
      letter-spacing: 1.5px;
      list-style-type: none;
      cursor: pointer;
      width: 160px;
    }
    li::before {
      content: "";
      position: absolute;
      height: 8px;
      width: 8px;
      background-color: #f1d675;
      border-radius: 50%;
      top: 50%;
      left: -20px;
      transform: translate(50%, -50%);
    }
    li:hover {
      color: #769763;
    }
  }
}

.enjoy {
  margin-top: 100px;
  .txt {
    display: flex;
    justify-content: center;
    align-items: center;
    .slogan {
      h2 {
        font-size: 48px;
      }
      h2:first-of-type {
        color: #769763;
        margin-top: 20px;
      }
      h2:last-of-type {
        color: #737373;
      }
    }
    .title {
      margin-left: 80px;
      color: #737373;
      font-weight: 400;
      font-size: 18px;
      display: flex;
      flex-direction: column;
      p {
        width: 528px;
        height: 46px;
        line-height: 1.7;
      }
      button {
        align-self: flex-end;
        margin-top: 20px;
        background: white;
        border-radius: 20px;
        padding: 5px 20px;
        color: #737373;
        border: #737373 1px solid;
        cursor: pointer
      }
    }
  }
}

.swiper-slide {
  margin-top: 20px;
  position: relative;
  .info {
    margin: 0;
    position: absolute;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0; // 沒有寬高 自然拉伸填滿父元素
    background-color: rgba(0, 0, 0, 0.6);
    display: flex;
    flex-direction: column;
    justify-content: center;
    opacity: 0;
    transition: opacity 0.5s;
    color: white;
    text-align: center;
    width: 75%;
    height: 100%;
    padding: 0 20px;
    box-sizing: border-box;
  }
  &:hover .info {
    opacity: 1;
  }
}
.swiper-slide img {
  width: 75%;
  height: 500px;
  cursor: pointer;
  vertical-align: middle;
}

.swiperCom {
  position: relative;
}
</style>
