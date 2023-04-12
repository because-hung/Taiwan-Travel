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
    <div class="m_participate">
      <div class="txt">
        <div class="title">
          <h2>Participate</h2>
          <h2>參與四季的更迭</h2>
        </div>
        <h5>根據季節的熱門活動主題，邀請你一同享受旅行中的每一個時刻。</h5>
      </div>
      <div class="pic">
        <div class="pic-item">
          <h2>精彩藝術知性之旅</h2>
          <img src="../assets/participate/participate_1.png" alt="" />
        </div>
        <div class="pic-item">
          <h2>好廟好妙求神問卜</h2>
          <img src="../assets/participate/participate_2.png" alt="" />
        </div>
        <div class="pic-item">
          <h2>親自踏上山海之旅</h2>
          <img src="../assets/participate/participate_3.png" alt="" />
        </div>
        <div class="pic-item">
          <h2>體驗台灣文化慶典</h2>
          <img src="../assets/participate/participate_4.png" alt="" />
        </div>
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
          <button class="btn">享受更多美食</button>
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
      <button class="btn m_btn">享受更多美食</button>
    </div>
    <div class="subscribe">
      <div class="container">
        <div class="pic">
          <img src="../assets/subscribe/Subscribe.jpeg" alt="" />
        </div>
        <div class="txt">
          <h2>Subscribe</h2>
          <h3>每個月來一場自在旅行</h3>
          <h5>如果您願意收到每月旅遊資訊，一起感受台灣旅行的美好</h5>
          <p class="txtBox">youremail@example.com <send /></p>
        </div>
      </div>
    </div>
    <div class="m_subscribe">
      <div class="container">
        <div class="txt">
          <h2>Subscribe</h2>
          <h3>每個月來一場自在旅行</h3>
        </div>
        <div class="pic">
          <img src="../assets/subscribe/Subscribe.jpeg" alt="" />
        </div>
      </div>
      <div class="bot">
        <h5>如果您願意收到每月旅遊資訊，一起感受台灣旅行的美好</h5>
        <p class="txtBox">youremail@example.com <send /></p>
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
import send from "../components/icon/sendMail.vue"
export default {
  components: {
    Swiper,
    SwiperSlide,
    send,
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
@import "../sass/pxToVw.scss";
.participate {
  margin-top: pxToVw(100);
  display: flex;
  align-items: center;
  .pic {
    width: pxToVw(1000);
    height: pxToVw(466);
    margin-right: pxToVw(80);
    img {
      width: 100%;
      height: 100%;
      vertical-align: middle;
    }
  }
  .txt {
    h2 {
      font-size: pxToVw(48);
    }
    h2:first-of-type {
      color: #769763;
      margin-top: pxToVw(20);
    }
    h2:last-of-type {
      color: #737373;
    }
    h5 {
      font-size: pxToVw(18);
    }
    ul {
      padding-left: pxToVw(20);
    }
    li {
      position: relative;
      font-size: pxToVw(18);
      padding: pxToVw(16) pxToVw(8);
      color: #737373;
      letter-spacing: pxToVw(1.5);
      list-style-type: none;
      cursor: pointer;
    }
    li::before {
      content: "";
      position: absolute;
      height: pxToVw(8);
      width: pxToVw(8);
      background-color: #f1d675;
      border-radius: 50%;
      top: 50%;
      left: pxToVw(-20);
      transform: translate(50%, -50%);
    }
    li:hover {
      color: #769763;
    }
  }
}
.m_participate {
  display: none;
}
.enjoy {
  margin-top: pxToVw(100);
  .txt {
    display: flex;
    justify-content: center;
    align-items: center;
    .slogan {
      h2 {
        font-size: pxToVw(48);
      }
      h2:first-of-type {
        color: #769763;
        margin-top: pxToVw(20);
      }
      h2:last-of-type {
        color: #737373;
      }
    }
    .title {
      margin-left: pxToVw(80);
      color: #737373;
      font-weight: 400;
      font-size: pxToVw(18);
      display: flex;
      flex-direction: column;
      p {
        width: pxToVw(528);
        line-height: 1.7;
        margin: 0;
      }
    }
  }
  button,
  .m_btn {
    align-self: flex-end;
    background: white;
    border-radius: pxToVw(20);
    padding: pxToVw(5) pxToVw(15);
    color: #737373;
    border: #737373 1px solid;
    cursor: pointer;
  }
  .m_btn {
    display: none;
  }
}

.swiper-slide {
  margin-top: pxToVw(20);
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
    padding: 0 pxToVw(20);
    box-sizing: border-box;
  }
  &:hover .info {
    opacity: 1;
  }
}
.swiper-slide img {
  width: 75%;
  height: pxToVw(500);
  cursor: pointer;
  vertical-align: middle;
}

.swiperCom {
  position: relative;
}

.subscribe,
.m_subscribe {
  margin-top: pxToVw(140);
  background-color: #769763;
  padding: pxToVw(144) pxToVw(200);
  .container {
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .pic {
    width: pxToVw(600);
    height: pxToVw(300);
    img {
      width: 100%;
      height: 100%;
      vertical-align: middle;
    }
  }
  .txt {
    width: 400px;
    margin-left: pxToVw(40);
    h2 {
      color: #f1d675;
      font-size: pxToVw(48);
      margin: 0;
    }
    h3 {
      color: #fff;
      font-size: pxToVw(36);
      margin: pxToVw(15) 0;
      letter-spacing: pxToVw(2);
    }
    h5 {
      font-size: pxToVw(18);
      color: rgba(255, 255, 255, 0.5);
      margin: 0;
      letter-spacing: pxToVw(1.5);
      line-height: 1.5;
    }
    .txtBox {
      padding: 10px 15px;
      color: rgba(255, 255, 255, 0.5);
      display: flex;
      align-items: center;
      justify-content: space-between;
      border: 1px solid rgba(255, 255, 255, 0.5);
      letter-spacing: pxToVw(1.5);
    }
  }
}

.m_subscribe {
  display: none;
}

@media (max-width: 821px) {
  .participate {
    display: none;
  }
  .m_participate {
    margin-top: 80px;
    display: block;
    .title {
      display: flex;
      align-items: center;
      h2 {
        margin: 0;
        color: #769763;
      }
      h2:last-child {
        margin-left: 20px;
        color: #737373;
      }
    }
    h5 {
      color: #737373;
    }
    .pic {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      grid-template-rows: repeat(2, 1fr);
      gap: 12px;
      box-sizing: border-box;
      .pic-item {
        position: relative;
        width: 100%;
        img {
          width: 100%;
          height: 100%;
          border-radius: 10px;
        }
        h2 {
          position: absolute;
          margin: 0;
          position: absolute;
          top: 0;
          right: 0;
          bottom: 0;
          left: 0; // 沒有寬高 自然拉伸填滿父元素
          background-color: rgba(0, 0, 0, 0.2);
          display: flex;
          align-items: center;
          justify-content: center;
          color: rgba(255, 255, 255, 0.8);
        }
      }
    }
  }
  .enjoy {
    .txt {
      justify-content: space-evenly;
      margin-bottom: 20px;
    }
    button {
      display: none;
    }
    .m_btn {
      display: flex;
      margin: auto;
      margin-top: 25px;
      padding: 10px 25px;
    }
  }
  .swiper-slide img {
    width: 90%;
    height: pxToVw(450);
  }
  .swiper-slide{
    .info{
      width: 90%;
      p{
        display: none;
      }
    }
  }
}

@media (max-width: 415px) {
  .enjoy {
    .title {
      p {
        display: none;
      }
    }
  }
  .m_participate {
    h2 {
      font-size: 20px;
    }
  }
  .swiper-slide img {
    width: 100%;
  }
    .swiper-slide{
    .info{
      width: 100%;
      h2{
        font-size: 14px;
      }

    }
  }
  .subscribe {
    display: none;
  }
  .m_subscribe {
    display: block;
    .container {
      .pic {
        width: 100%;
      }
      .txt {
        width: 400px;
        margin-left: pxToVw(40);
      }
    }
    .bot {
      margin-top: 10px;
      h5 {
        font-size: pxToVw(16);
        color: rgba(255, 255, 255, 0.5);
        margin: 0;
        letter-spacing: pxToVw(1.5);
        line-height: 1.5;
      }
      .txtBox {
        padding: 10px 15px;
        color: rgba(255, 255, 255, 0.5);
        display: flex;
        align-items: center;
        justify-content: space-between;
        border: 1px solid rgba(255, 255, 255, 0.5);
        letter-spacing: pxToVw(1.5);
      }
    }
  }
}
</style>
