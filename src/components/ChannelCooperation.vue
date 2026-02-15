<template>
  <div class="channel-cooperation">
    <img :src="gifUrl" alt="" class="channel-cooperation-background-gif" />
    <div class="channel-cooperation-overlay"></div>

    <div class="content" :class="{ 'show-content': showContent }">
      <h1 class="title-first">AI MATRIX</h1>
      <h2 class="title-second">火熱招商·全球代理商招募中</h2>
      <p class="description">
        All-in-One一站式出海行銷智能解決方案,從洞察到轉化,輕鬆出海
      </p>
      <button class="demo-btn" @click="scrollToBottom">
        <span class="btn-text">聯係我們</span>
        <img
          src="../assets/images/public/Slice 6@2x.png"
          alt=""
          class="btn-arrow"
        />
      </button>
    </div>
    <div class="section-gradient-bar"></div>
  </div>
</template>

<script>
export default {
  name: "ChannelCooperation",
  data() {
    return {
      gifUrl: "",
      showContent: false,
    };
  },
  mounted() {
    this.gifUrl = `${require("../assets/videos/4.42MB渠道合作.gif")}?t=${Date.now()}`;
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
@import "../assets/css/channelcooperation.css";
</style>
