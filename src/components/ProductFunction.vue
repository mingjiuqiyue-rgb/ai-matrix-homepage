<template>
  <div class="product-function">
    <img :src="gifUrl" alt="" class="product-function-gif" />
    <div class="product-function-overlay"></div>

    <div class="product-function-content" :class="{ 'show-content': showContent }">
      <h1 class="product-function-title-first">AI MATRIX</h1>
      <h2 class="product-function-title-second">让海外營銷更簡單</h2>
      <p class="product-function-description">
        All-in-One一站式出海行銷智能解決方案，從洞察到轉化，輕鬆出海
      </p>
      <button class="product-function-demo-btn" @click="scrollToBottom">
        <span class="product-function-btn-text">預約演示</span>
        <img
          src="../assets/images/public/Slice 6@2x.png"
          alt=""
          class="product-function-btn-arrow"
        />
      </button>
    </div>
    <div class="section-gradient-bar"></div>
  </div>
</template>

<script>
export default {
  name: "ProductFunction",
  data() {
    return {
      gifUrl: "",
      showContent: false,
    };
  },
  mounted() {
    this.gifUrl = `${require("../assets/videos/4.6MB banner.gif")}?t=${Date.now()}`;
    setTimeout(() => {
      this.showContent = true;
    }, 300);
  },
  methods: {
    scrollToBottom() {
      window.scrollTo({
        top: document.documentElement.scrollHeight,
        behavior: "smooth",
      });
    },
  },
};
</script>

<style scoped>
@import "../assets/css/productfunction.css";
</style>
