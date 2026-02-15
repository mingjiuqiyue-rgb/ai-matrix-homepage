<template>
  <div class="multiple-routes">
    <div class="multiple-routes-badge">
      <svg class="badge-icon" width="22" height="22" viewBox="0 0 22 22">
        <defs>
          <radialGradient
            id="multipleRoutesIconGradient"
            cx="50%"
            cy="50%"
            r="50%"
          >
            <stop offset="29.98%" stop-color="#ffffff" stop-opacity="0" />
            <stop offset="100%" stop-color="#ffffff" stop-opacity="0.6" />
          </radialGradient>
        </defs>
        <circle
          cx="11"
          cy="11"
          r="10"
          fill="url(#multipleRoutesIconGradient)"
          stroke="#ffffff4d"
          stroke-width="2"
        />
      </svg>
      <span class="badge-text">globalization</span>
    </div>

    <h2 class="multiple-routes-title">一鍵全球·多途並達</h2>

    <img
      src="../assets/images/public/Underscore.png"
      alt=""
      class="multiple-routes-image"
    />

    <div class="multiple-routes-content">
      <img
        src="../assets/images/MultipleRoutes/Slice 31@2x.png"
        alt="多途並達"
        class="routes-bg-image"
      />

      <div class="routes-text-content">
        <h3 class="routes-main-title">海外全渠道·API介面聚合群發</h3>

        <div class="routes-description">
          <p>指紋瀏覽器，RPA自動化出海，打造全球私域流量生態圈</p>
          <p>1套軟件批量管理N個社媒平台帳號，</p>
          <p>精準觸達全球精準客戶</p>
        </div>

        <button class="routes-demo-btn" @click="scrollToBottom">
          <span class="routes-demo-text">預約演示</span>
          <img
            src="../assets/images/public/Slice 6@2x.png"
            alt=""
            class="routes-demo-arrow"
          />
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "MultipleRoutes",
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
@import "../assets/css/multipleroutes.css";
</style>
