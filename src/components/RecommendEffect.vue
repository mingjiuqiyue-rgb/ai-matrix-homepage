<template>
  <div class="recommend-effect">
    <div class="recommend-effect-badge">
      <svg class="badge-icon" width="22" height="22" viewBox="0 0 22 22">
        <defs>
          <radialGradient
            id="recommendEffectIconGradient"
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
          fill="url(#recommendEffectIconGradient)"
          stroke="#ffffff4d"
          stroke-width="2"
        />
      </svg>
      <span class="badge-text">recommend</span>
    </div>

    <h2 class="recommend-effect-title">種草營銷·增益提效</h2>

    <img
      src="../assets/images/public/Underscore.png"
      alt=""
      class="recommend-effect-image"
    />

    <div class="recommend-content">
      <div class="recommend-bg-layers" aria-hidden="true">
        <div class="bg-layer layer-1"></div>
        <div class="bg-layer layer-2"></div>
        <div class="bg-layer layer-3"></div>
        <div class="bg-layer layer-4"></div>
      </div>
      <img
        src="../assets/videos/首页-种草营销-3.97MB.gif"
        alt="种草营销"
        class="recommend-bg-gif"
      />

      <div class="info-box info-box-01">
        <div class="info-number">01</div>
        <div class="info-title">科學洞察</div>
        <div class="info-text">市場洞察，幫您看清市場脈絡，挖掘潛力賽道</div>
        <div class="info-text">人群洞察，定位和採集目標人群信息</div>
      </div>

      <div class="info-box info-box-02">
        <div class="info-number">02</div>
        <div class="info-title">智能生成</div>
        <div class="info-text">藉助TK MATRIX快速生產內容</div>
        <div class="info-text">
          自定義生成專屬文案、配音、視頻，極大縮短內容創作時間
        </div>
      </div>

      <div class="info-box info-box-03">
        <div class="info-number">03</div>
        <div class="info-title">內容投放</div>
        <div class="info-text">使用RPA自動化功能，批量登錄、發帖、點讚</div>
        <div class="info-text">精準覆蓋目標人群</div>
      </div>

      <div class="info-box info-box-04">
        <div class="info-number">04</div>
        <div class="info-title">跨渠道管理</div>
        <div class="info-text">
          藉助指紋瀏覽器功能，一站式管理多個社交平台賬號
        </div>
        <div class="info-text">提升運營效率</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "RecommendEffect",
};
</script>

<style scoped>
@import "../assets/css/recommendeffect.css";
</style>
