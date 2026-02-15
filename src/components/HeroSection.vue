<template>
  <div class="hero-section" :style="{ backgroundImage: backgroundImage }">
    <img
      v-if="showGif"
      :src="gifUrl"
      alt=""
      class="hero-gif"
      @click="skipAnimation"
    />

    <div class="hero-content" :class="{ 'show-content': showContent }">
      <h2 class="hero-subtitle">AI賦能·跨境出海矩陣營銷</h2>

      <div class="hero-title">
        <h1 class="title-main">AI MATRIX</h1>
        <div class="title-info">
          <div class="info-top">
            <span class="year">2026</span>
            <div class="desc-en">
              <span>Global Operation</span>
              <span>Intelligent Efficiency Enhancement</span>
            </div>
          </div>
          <p class="desc-cn">全球運營 智能增效</p>
        </div>
      </div>

      <div class="hero-action">
        <div class="action-btn">
          <img
            src="../assets/images/HeroSection/Slice 7@2x.png"
            alt=""
            class="btn-icon"
          />
          <span class="btn-text">即刻啟程,沉浸體驗!</span>
        </div>
        <button class="hero-btn-demo" @click="scrollToBottom">
          <span class="hero-demo-text">預約演示</span>
          <img
            src="../assets/images/public/Slice 6@2x.png"
            alt=""
            class="hero-demo-arrow"
          />
        </button>
      </div>
    </div>
    <div class="section-gradient-bar"></div>
  </div>
</template>

<script>
export default {
  name: "HeroSection",
  data() {
    return {
      showGif: true,
      showContent: false,
      backgroundImage: "none",
      gifDuration: 5910,
      animationTimer: null,
      gifUrl: "",
    };
  },
  mounted() {
    this.initHeroSection();
    window.addEventListener("scroll", this.handleScroll);
    window.addEventListener("click", this.skipAnimation);
  },
  activated() {
    this.initHeroSection();
  },
  beforeUnmount() {
    window.removeEventListener("scroll", this.handleScroll);
    window.removeEventListener("click", this.skipAnimation);
    if (this.animationTimer) {
      clearTimeout(this.animationTimer);
    }
  },
  deactivated() {
    if (this.animationTimer) {
      clearTimeout(this.animationTimer);
    }
  },
  methods: {
    initHeroSection() {
      this.showGif = true;
      this.showContent = false;
      this.backgroundImage = "none";
      this.gifUrl = `${require("../assets/videos/首页-banner-3.78MB.gif")}?t=${Date.now()}`;
      this.startAnimation();
    },
    startAnimation() {
      this.animationTimer = setTimeout(() => {
        this.showContentNow();
      }, this.gifDuration);
    },
    showContentNow() {
      this.showGif = false;
      // 设置背景图
      this.backgroundImage = `url(${require("../assets/images/HeroSection/首页banner-静态.png")})`;
      // 强制重新渲染
      this.$forceUpdate();
      setTimeout(() => {
        this.showContent = true;
        // 确保背景图样式正确应用
        setTimeout(() => {
          const heroSection = document.querySelector(".hero-section");
          if (heroSection) {
            heroSection.style.backgroundSize = "cover";
            heroSection.style.backgroundPosition = "center";
            heroSection.style.backgroundRepeat = "no-repeat";
          }
        }, 100);
      }, 100);
    },
    skipAnimation() {
      if (this.showGif) {
        if (this.animationTimer) {
          clearTimeout(this.animationTimer);
        }
        this.showContentNow();
      }
    },
    handleScroll() {
      this.skipAnimation();
    },
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
@import "../assets/css/herosection.css";
</style>
