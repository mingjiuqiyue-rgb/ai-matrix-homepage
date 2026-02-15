<template>
  <div class="fingerprint-browser">
    <div class="switch-container">
      <div class="switch-bg" :class="{ phone: activeTab === 'phone' }"></div>
      <button
        class="switch-btn"
        :class="{ active: activeTab === 'browser' }"
        @click="activeTab = 'browser'"
      >
        指紋瀏覽器
      </button>
      <button
        class="switch-btn"
        :class="{ active: activeTab === 'phone' }"
        @click="activeTab = 'phone'"
      >
        指紋手機
      </button>
    </div>

    <div class="content-section">
      <div v-if="activeTab === 'browser'" class="browser-content">
        <div class="right-box">
          <img
            src="../assets/images/FunctionDisplay/Slice 134@2x.png"
            alt="指紋瀏覽器"
            class="content-image"
          />
        </div>
        <div class="left-box">
          <div class="top-content">
            <h3 class="content-title">指紋瀏覽器</h3>
            <p class="content-description">
              幫助跨境用戶安全、高效地管理多個帳號，降低運營風險。
            </p>
            <button class="demo-btn" @click="scrollToBottom">
              <span class="fingerprint-btn-text">預約演示</span>
            </button>
          </div>
          <div class="feature-list">
            <div class="feature-item">
              <img
                src="../assets/images/FunctionDisplay/Slice 135@2x.png"
                alt=""
                class="feature-icon"
              />
              <span class="feature-text"
                >環境隔離技術，為每個帳號創建獨立環境，杜絕關聯</span
              >
            </div>
            <div class="feature-item">
              <img
                src="../assets/images/FunctionDisplay/Slice 135@2x.png"
                alt=""
                class="feature-icon"
              />
              <span class="feature-text"
                >獨享純淨IP與海外專線，保障網絡高速穩定</span
              >
            </div>
            <div class="feature-item">
              <img
                src="../assets/images/FunctionDisplay/Slice 135@2x.png"
                alt=""
                class="feature-icon"
              />
              <span class="feature-text"
                >安全高效管理跨境多帳號，顯著降低運維風險</span
              >
            </div>
          </div>
        </div>
      </div>

      <div v-if="activeTab === 'phone'" class="phone-content">
        <div class="right-box">
          <img
            src="../assets/images/FunctionDisplay/Slice 134@2x (1).png"
            alt="指紋手機"
            class="content-image"
          />
        </div>
        <div class="left-box">
          <div class="top-content">
            <h3 class="content-title">指紋手機</h3>
            <p class="content-description">
              幫助跨境用戶安全、高效地管理多個帳號，降低運營风险。
            </p>
            <button class="demo-btn" @click="scrollToBottom">
              <span class="fingerprint-btn-text">預約演示</span>
            </button>
          </div>
          <div class="feature-list">
            <div class="feature-item">
              <img
                src="../assets/images/FunctionDisplay/Slice 135@2x.png"
                alt=""
                class="feature-icon"
              />
              <span class="feature-text"
                >環境隔離技術，為每個帳號創建獨立環境，杜绝關聯</span
              >
            </div>
            <div class="feature-item">
              <img
                src="../assets/images/FunctionDisplay/Slice 135@2x.png"
                alt=""
                class="feature-icon"
              />
              <span class="feature-text"
                >獨享純淨IP與海外專線，保障網絡高速穩定</span
              >
            </div>
            <div class="feature-item">
              <img
                src="../assets/images/FunctionDisplay/Slice 135@2x.png"
                alt=""
                class="feature-icon"
              />
              <span class="feature-text"
                >安全高效管理跨境多帳號，顯著降低運維风险</span
              >
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "FingerprintBrowser",
  data() {
    return {
      activeTab: "browser",
    };
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
@import "../assets/css/fingerprintbrowser.css";
</style>
