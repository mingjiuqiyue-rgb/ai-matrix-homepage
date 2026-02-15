<template>
  <div class="competitive-advantage">
    <div class="advantage-badge">
      <svg class="badge-icon" width="22" height="22" viewBox="0 0 22 22">
        <defs>
          <radialGradient id="advantageIconGradient" cx="50%" cy="50%" r="50%">
            <stop offset="29.98%" stop-color="#ffffff" stop-opacity="0" />
            <stop offset="100%" stop-color="#ffffff" stop-opacity="0.6" />
          </radialGradient>
        </defs>
        <circle
          cx="11"
          cy="11"
          r="10"
          fill="url(#advantageIconGradient)"
          stroke="#ffffff4d"
          stroke-width="2"
        />
      </svg>
      <span class="badge-text">advantage</span>
    </div>

    <h2 class="advantage-title">企業優勢</h2>

    <img
      src="../assets/images/public/Underscore.png"
      alt=""
      class="advantage-image"
    />

    <div class="advantage-content">
      <div class="advantage-box">
        <img
          src="../assets/images/CompetitiveAdvantage/Slice 9@2x.png"
          alt=""
        />
        <div class="advantage-box-text">專業的團隊</div>
      </div>

      <div class="advantage-box">
        <img
          src="../assets/images/CompetitiveAdvantage/Slice 9@2x (1).png"
          alt=""
        />
        <div class="advantage-box-text">超高應答率</div>
      </div>

      <div class="advantage-box">
        <img
          src="../assets/images/CompetitiveAdvantage/Slice 9@2x (2).png"
          alt=""
        />
        <div class="advantage-box-text">1對1專人演示</div>
      </div>

      <div class="advantage-box">
        <img
          src="../assets/images/CompetitiveAdvantage/Slice 9@2x (3).png"
          alt=""
        />
        <div class="advantage-box-text">個性化的服務</div>
      </div>

      <div class="advantage-box">
        <img
          src="../assets/images/CompetitiveAdvantage/Slice 9@2x (4).png"
          alt=""
        />
        <div class="advantage-box-text">定製化服務</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "CompetitiveAdvantage",
};
</script>

<style scoped>
@import "../assets/css/competitiveadvantage.css";
</style>

