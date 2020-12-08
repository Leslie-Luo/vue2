<template>
  <div class="swiper">
    <div class="swiper-container">
      <div class="swiper-wrapper">
        <template v-for="item in list">
          <div class="swiper-slide" :key="item">
            <img :src="item" />
          </div>
        </template>
      </div>
      <!-- 如果需要分页器 -->
      <div class="swiper-pagination"></div>

      <!-- 如果需要导航按钮 -->
      <div class="swiper-button-prev"></div>
      <div class="swiper-button-next"></div>

      <!-- 如果需要滚动条 -->
      <div class="swiper-scrollbar"></div>
    </div>
  </div>
</template>

<script>
import "swiper/swiper-bundle.min.css";
import Swiper from "swiper/swiper-bundle.min.js";
export default {
  name: "swiper",
  props: {
    list: Array
  },
  data() {
    return {};
  },
  mounted() {
    // 初始化轮播
    this.initSwiper();
  },
  methods: {
    // 初始化轮播
    initSwiper() {
      new Swiper(".swiper-container", {
        loop: true, // 循环模式选项
        observer: true,
        observeParents: true,
        grabCursor: true,
        centeredSlides: true,
        slidesPerView: "auto",
        effect: "coverflow",
        coverflowEffect: {
          rotate: 1,
          stretch: 0,
          depth: 40,
          modifier: 4,
          slideShadows: false
        },
        // 如果需要前进后退按钮
        navigation: {
          nextEl: ".swiper-button-next",
          prevEl: ".swiper-button-prev"
        }
      });
    }
  }
};
</script>

<style lang="scss" scoped>
.swiper-container {
  width: 600px;
  height: 300px;
  .swiper-slide {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 600px;
    height: 300px;
    img {
      width: 90%;
      height: 100%;
      object-fit: cover;
    }
  }
}
</style>
