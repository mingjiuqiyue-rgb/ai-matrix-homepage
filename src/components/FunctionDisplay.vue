<template>
  <div class="function-display">
    <div class="function-badge">
      <svg class="badge-icon" width="22" height="22" viewBox="0 0 22 22">
        <defs>
          <radialGradient id="functionIconGradient" cx="50%" cy="50%" r="50%">
            <stop offset="29.98%" stop-color="#ffffff" stop-opacity="0" />
            <stop offset="100%" stop-color="#ffffff" stop-opacity="0.6" />
          </radialGradient>
        </defs>
        <circle
          cx="11"
          cy="11"
          r="10"
          fill="url(#functionIconGradient)"
          stroke="#ffffff4d"
          stroke-width="2"
        />
      </svg>
      <span class="badge-text">detail</span>
    </div>

    <h2 class="function-title">產品細節·功能展示</h2>

    <img
      src="../assets/images/public/Underscore.png"
      alt=""
      class="function-image"
    />

    <div class="function-tabs">
      <div
        class="function-tab"
        :class="{ active: activeTab === 'collection' }"
        @click="activeTab = 'collection'"
      >
        <img
          src="../assets/images/FunctionDisplay/Slice 142@2x.png"
          alt=""
          class="tab-icon"
        />
        <div class="tab-text">數據採集</div>
      </div>

      <div
        class="function-tab"
        :class="{ active: activeTab === 'fingerprint' }"
        @click="activeTab = 'fingerprint'"
      >
        <img
          src="../assets/images/FunctionDisplay/Slice 142@2x (1).png"
          alt=""
          class="tab-icon"
        />
        <div class="tab-text">指紋瀏覽器</div>
      </div>

      <div
        class="function-tab"
        :class="{ active: activeTab === 'rpa' }"
        @click="activeTab = 'rpa'"
      >
        <img
          src="../assets/images/FunctionDisplay/Slice 142@2x (2).png"
          alt=""
          class="tab-icon"
        />
        <div class="tab-text">RPA自動化</div>
      </div>

      <div
        class="function-tab"
        :class="{ active: activeTab === 'tk' }"
        @click="activeTab = 'tk'"
      >
        <img
          src="../assets/images/FunctionDisplay/Slice 142@2x (3).png"
          alt=""
          class="tab-icon"
        />
        <div class="tab-text">TK MATRIX</div>
      </div>

      <div
        class="function-tab"
        :class="{ active: activeTab === 'simulator' }"
      >
        <img
          src="../assets/images/FunctionDisplay/Slice 142@2x (4).png"
          alt=""
          class="tab-icon"
        />
        <div class="tab-text">模擬器</div>
      </div>
    </div>

    <div class="function-content">
      <DataCollection v-if="activeTab === 'collection'" />
      <FingerprintBrowser v-if="activeTab === 'fingerprint'" />
      <RPAAutomation v-if="activeTab === 'rpa'" />
      <TKMatrix v-if="activeTab === 'tk'" />
    </div>
  </div>
</template>

<script>
import DataCollection from "./DataCollection.vue";
import FingerprintBrowser from "./FingerprintBrowser.vue";
import RPAAutomation from "./RPAAutomation.vue";
import TKMatrix from "./TKMatrix.vue";

export default {
  name: "FunctionDisplay",
  components: {
    DataCollection,
    FingerprintBrowser,
    RPAAutomation,
    TKMatrix,
  },
  data() {
    return {
      activeTab: "collection",
    };
  },
};
</script>

<style scoped>
@import "../assets/css/functiondisplay.css";
</style>
