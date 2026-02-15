<template>
  <div class="mutually-beneficial">
    <div class="benefit-badge">
      <svg class="badge-icon" width="22" height="22" viewBox="0 0 22 22">
        <defs>
          <radialGradient id="benefitIconGradient" cx="50%" cy="50%" r="50%">
            <stop offset="29.98%" stop-color="#ffffff" stop-opacity="0" />
            <stop offset="100%" stop-color="#ffffff" stop-opacity="0.6" />
          </radialGradient>
        </defs>
        <circle
          cx="11"
          cy="11"
          r="10"
          fill="url(#benefitIconGradient)"
          stroke="#ffffff4d"
          stroke-width="2"
        />
      </svg>
      <span class="badge-text">cooperation</span>
    </div>

    <h2 class="benefit-title">互利共赢·同舟共濟</h2>

    <img
      src="../assets/images/public/Underscore.png"
      alt=""
      class="benefit-image"
    />

    <button class="benefit-demo-btn" @click="scrollToBottom">聯係我們</button>

    <div class="benefit-content">
      <div
        class="benefit-box"
        :class="{
          'benefit-first': true,
          'benefit-active': activeBenefit === 'first',
          'benefit-small': activeBenefit !== 'first',
        }"
        @click="setActiveBenefit('first')"
      >
        <h3 class="benefit-large-title" v-if="activeBenefit === 'first'">
          市場營銷
        </h3>
        <h4 class="benefit-small-title" v-else>市場營銷</h4>

        <div v-if="activeBenefit === 'first'">
          <p class="benefit-large-text">與合作夥伴聯合開展市場營銷活動共拓市場，联合营销活动</p>
          <p class="benefit-large-text">有效降低各自的获客成本，实现"1+1>2"的传播效果</p>
        </div>
      </div>

      <div
        class="benefit-box"
        :class="{
          'benefit-second': true,
          'benefit-active': activeBenefit === 'second',
          'benefit-small': activeBenefit !== 'second',
        }"
        @click="setActiveBenefit('second')"
      >
        <h3 class="benefit-large-title" v-if="activeBenefit === 'second'">
          培訓賦能
        </h3>
        <h4 class="benefit-small-title" v-else>培訓賦能</h4>

        <div v-if="activeBenefit === 'second'">
          <p class="benefit-large-text">提供伙伴专属的技术、产品、解决方案培训，全面提升合作伙伴</p>
          <p class="benefit-large-text">业务能力帮助合作伙伴的团队快速掌握核心知识和技能</p>
        </div>
      </div>

      <div
        class="benefit-box"
        :class="{
          'benefit-third': true,
          'benefit-active': activeBenefit === 'third',
          'benefit-small': activeBenefit !== 'third',
        }"
        @click="setActiveBenefit('third')"
      >
        <h3 class="benefit-large-title" v-if="activeBenefit === 'third'">
          專業產品技術
        </h3>
        <h4 class="benefit-small-title" v-else>專業產品技術</h4>

        <div v-if="activeBenefit === 'third'">
          <p class="benefit-large-text">承诺持续投入研发资源，推动产品的持续优化升级，以此保障</p>
          <p class="benefit-large-text">合作伙伴能长期为客户提供具备竞争优势的技术与解决方案</p>
        </div>
      </div>

      <div
        class="benefit-box"
        :class="{
          'benefit-fourth': true,
          'benefit-active': activeBenefit === 'fourth',
          'benefit-small': activeBenefit !== 'fourth',
        }"
        @click="setActiveBenefit('fourth')"
      >
        <h3 class="benefit-large-title" v-if="activeBenefit === 'fourth'">
          售後支持
        </h3>
        <h4 class="benefit-small-title" v-else>售後支持</h4>

        <div v-if="activeBenefit === 'fourth'">
          <p class="benefit-large-text">專屬客服保障客戶系統的長期穩定運行，快速解決客戶</p>
          <p class="benefit-large-text">的後顧之憂，維護合作夥伴的商業信譽</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "MutuallyBeneficial",
  data() {
    return {
      activeBenefit: "first",
    };
  },
  methods: {
    setActiveBenefit(benefit) {
      this.activeBenefit = benefit;
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
@import "../assets/css/mutuallybeneficial.css";
</style>
