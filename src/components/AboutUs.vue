<template>
  <div class="about-us">
    <video class="about-us-video" autoplay loop muted playsinline>
      <source :src="videoUrl" type="video/gif" />
    </video>
    <img :src="gifUrl" alt="" class="about-us-gif" />
    <div class="about-us-overlay"></div>

    <div class="about-us-content" :class="{ 'show-content': showContent }">
      <h1 class="about-us-title-first">AI MATRIX</h1>
      <h2 class="about-us-title-second">火熱招商·全球代理商招募中</h2>
      <p class="about-us-description">
        All-in-One一站式出海行銷智能解決方案,從洞察到轉化,輕鬆出海
      </p>
      <button class="about-us-demo-btn" @click="scrollToBottom">
        <span class="about-us-btn-text">聯係我們</span>
        <img
          src="../assets/images/public/Slice 6@2x.png"
          alt=""
          class="about-us-btn-arrow"
        />
      </button>
    </div>
    <div class="section-gradient-bar"></div>
  </div>
</template>

<script>
export default {
  name: "AboutUs",
  data() {
    return {
      gifUrl: "",
      showContent: false,
    };
  },
  computed: {
    videoUrl() {
      return require("../assets/videos/4.5MB关于我们.gif");
    },
  },
  mounted() {
    this.gifUrl = `${require("../assets/videos/4.5MB关于我们.gif")}?t=${Date.now()}`;
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
@import "../assets/css/aboutus.css";
</style>
