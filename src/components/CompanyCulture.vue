<template>
  <div class="company-culture">
    <div class="company-culture-badge">
      <svg class="badge-icon" width="22" height="22" viewBox="0 0 22 22">
        <defs>
          <radialGradient
            id="companyCultureIconGradient"
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
          fill="url(#companyCultureIconGradient)"
          stroke="#ffffff4d"
          stroke-width="2"
        />
      </svg>
      <span class="badge-text">culture</span>
    </div>

    <h2 class="company-culture-title">AI MATRIX·企業文化</h2>

    <img
      src="../assets/images/public/Underscore.png"
      alt=""
      class="company-culture-image"
    />

    <div class="company-culture-content">
      <img :src="gifUrl" alt="" class="culture-bg-gif" />

      <div class="culture-center-text">價值觀</div>

      <div class="culture-item culture-item-1">
        <div class="culture-item-title">用戶愉悅</div>
        <div class="culture-item-subtitle">洞察需求，用心服務</div>
      </div>

      <div class="culture-item culture-item-2">
        <div class="culture-item-title">激情成長</div>
        <div class="culture-item-subtitle">敢於挑戰，突破自我</div>
      </div>

      <div class="culture-item culture-item-3">
        <div class="culture-item-title">團隊協同</div>
        <div class="culture-item-subtitle">合作共贏，追求效益</div>
      </div>

      <div class="culture-item culture-item-4">
        <div class="culture-item-title">工匠精神</div>
        <div class="culture-item-subtitle">專業執著，精益求精</div>
      </div>
    </div>


    <!-- Mobile Culture Cards -->
    <div class="culture-mobile-list">
      <div class="culture-mobile-card">
        <img src="../assets/images/Phone/Slice 8@2x.png" alt="" class="card-icon" />
        <div class="card-text">
          <div class="card-title">願景</div>
          <div class="card-desc">賦能全球夥伴，成為品牌成長驅動</div>
        </div>
      </div>
      <div class="culture-mobile-card">
        <img src="../assets/images/Phone/Slice 9@2x.png" alt="" class="card-icon" />
        <div class="card-text">
          <div class="card-title">使命</div>
          <div class="card-desc">智驅品牌增長，鏈通全球共創未來</div>
        </div>
      </div>
      <div class="culture-mobile-card">
        <img src="../assets/images/Phone/Slice 10@2x.png" alt="" class="card-icon" />
        <div class="card-text">
          <div class="card-title">經營理念</div>
          <div class="card-desc">心懷客戶體驗，智驅精準服務</div>
        </div>
      </div>
      <div class="culture-mobile-card">
        <img src="../assets/images/Phone/Slice 11@2x.png" alt="" class="card-icon" />
        <div class="card-text">
          <div class="card-title">商業價值觀</div>
          <div class="card-desc">極致創新，協作共贏</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "CompanyCulture",
  data() {
    return {
      gifUrl: "",
    };
  },
  mounted() {
    this.gifUrl = `${require("../assets/videos/4.2MB关于我们-企业文化-gif.gif")}?t=${Date.now()}`;
  },
};
</script>

<style scoped>
@import "../assets/css/companyculture.css";
</style>

