<template>
  <div class="cooperation-process">
    <div class="process-badge">
      <svg class="badge-icon" width="22" height="22" viewBox="0 0 22 22">
        <defs>
          <radialGradient id="processIconGradient" cx="50%" cy="50%" r="50%">
            <stop offset="29.98%" stop-color="#ffffff" stop-opacity="0" />
            <stop offset="100%" stop-color="#ffffff" stop-opacity="0.6" />
          </radialGradient>
        </defs>
        <circle
          cx="11"
          cy="11"
          r="10"
          fill="url(#processIconGradient)"
          stroke="#ffffff4d"
          stroke-width="2"
        />
      </svg>
      <span class="badge-text">process</span>
    </div>

    <h2 class="process-title">合作流程·協同共進</h2>

    <img
      src="../assets/images/public/Underscore.png"
      alt=""
      class="process-image"
    />

    <div class="process-content">
      <!-- PC端内容 -->
      <img
        src="../assets/images/CooperationProcess/Slice 11@2x.png"
        alt=""
        class="process-bg-image"
      />

      <div class="process-steps-pc">
        <div class="step-item step-first">
          <h3 class="step-title">初步接觸</h3>
          <p class="step-desc">通過郵件、電話或會議</p>
          <p class="step-desc step-desc-second">進行接觸</p>
        </div>

        <div class="step-item step-second">
          <h3 class="step-title">商務洽談</h3>
          <p class="step-desc">確認合作協議及</p>
          <p class="step-desc step-desc-second">方案的設計</p>
        </div>

        <div class="step-item step-third">
          <h3 class="step-title">簽署協議</h3>
          <p class="step-desc">簽訂服務及保密協議</p>
        </div>

        <div class="step-item step-fourth">
          <h3 class="step-title">業務開展</h3>
          <p class="step-desc">業務培訓、駐點支持</p>
          <p class="step-desc step-desc-second">業務開展</p>
        </div>
      </div>

      <!-- 手机端一比一复原内容 -->
      <div class="process-mobile-container">
        <!-- 垂直背景线 -->
        <div class="process-mobile-line"></div>
        
        <div class="process-mobile-steps">
          <!-- Step 01 -->
          <div class="process-mobile-step step-right">
            <div class="step-icon-wrapper">
              <img src="../assets/images/Phone/Slice 15@2x.png" alt="" class="step-center-icon" />
            </div>
            <div class="step-content-box">
              <div class="step-number-badge">STEP 01</div>
              <h3 class="step-mobile-title">提交申請</h3>
              <p class="step-mobile-desc">提交資料申請成為合作伙伴</p>
            </div>
          </div>

          <!-- Step 02 -->
          <div class="process-mobile-step step-left">
            <div class="step-icon-wrapper">
              <img src="../assets/images/Phone/Slice 15@2x.png" alt="" class="step-center-icon" />
            </div>
            <div class="step-content-box">
              <div class="step-number-badge">STEP 02</div>
              <h3 class="step-mobile-title">初步接觸</h3>
              <p class="step-mobile-desc">通過郵件、電話或會議進行接觸</p>
            </div>
          </div>

          <!-- Step 03 -->
          <div class="process-mobile-step step-right">
            <div class="step-icon-wrapper">
              <img src="../assets/images/Phone/Slice 15@2x.png" alt="" class="step-center-icon" />
            </div>
            <div class="step-content-box">
              <div class="step-number-badge">STEP 03</div>
              <h3 class="step-mobile-title">商務洽談</h3>
              <p class="step-mobile-desc">提確認合作協議及方案的設計</p>
            </div>
          </div>

          <!-- Step 04 -->
          <div class="process-mobile-step step-left">
            <div class="step-icon-wrapper">
              <img src="../assets/images/Phone/Slice 15@2x.png" alt="" class="step-center-icon" />
            </div>
            <div class="step-content-box">
              <div class="step-number-badge">STEP 04</div>
              <h3 class="step-mobile-title">簽署協議</h3>
              <p class="step-mobile-desc">簽訂服務及保密協議</p>
            </div>
          </div>

          <!-- Step 05 -->
          <div class="process-mobile-step step-right">
            <div class="step-icon-wrapper">
              <img src="../assets/images/Phone/Slice 15@2x.png" alt="" class="step-center-icon" />
            </div>
            <div class="step-content-box">
              <div class="step-number-badge">STEP 05</div>
              <h3 class="step-mobile-title">業務開展</h3>
              <p class="step-mobile-desc">業務培訓、駐點支持業務開展</p>
            </div>
          </div>
        </div>

        <!-- 手机端背景图 -->
        <img
          src="../assets/images/Phone/渠道合作-3背景_wps图片_73.png"
          alt=""
          class="process-mobile-bg"
        />
      </div>
    </div>

    <button class="process-demo-btn" @click="scrollToBottom">聯係我們</button>
  </div>
</template>

<script>
export default {
  name: "CooperationProcess",
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
@import "../assets/css/cooperationprocess.css";
</style>
