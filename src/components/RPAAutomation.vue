<template>
  <div class="rpa-automation">
    <div class="rpa-section-first">
      <h3 class="rpa-first-title">支持多個社媒平台集中管理</h3>
      <p class="rpa-first-description">
        一站式管理所有社媒账号與任務，解放人力，極致增效。
      </p>
    </div>

    <div class="rpa-section-second">
      <div class="rpa-left-box">
        <div class="rpa-left-item">
          <div class="rpa-left-label">人工成本</div>
          <div class="rpa-left-value">120%</div>
        </div>
        <div class="rpa-left-item">
          <div class="rpa-left-label">降低指數</div>
          <div class="rpa-left-value">56%</div>
        </div>
      </div>
      <div class="rpa-right-container">
        <div class="rpa-right-top-box"></div>
        <div class="rpa-right-bottom-box" @click="scrollToBottom">
          <span class="rpa-bottom-text">預約演示</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "RPAAutomation",
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
@import "../assets/css/rpaautomation.css";
</style>

