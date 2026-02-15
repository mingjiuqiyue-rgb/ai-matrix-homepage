<template>
  <div class="company-profile">
    <div class="company-profile-badge">
      <svg class="badge-icon" width="22" height="22" viewBox="0 0 22 22">
        <defs>
          <radialGradient
            id="companyProfileIconGradient"
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
          fill="url(#companyProfileIconGradient)"
          stroke="#ffffff4d"
          stroke-width="2"
        />
      </svg>
      <span class="badge-text">company</span>
    </div>

    <h2 class="company-profile-title">公司简介</h2>

    <img
      src="../assets/images/public/Underscore.png"
      alt=""
      class="company-profile-image"
    />

    <div class="company-profile-content">
      <img
        src="../assets/images/CompanyProfile/Slice 7@2x.png"
        alt=""
        class="profile-left-image"
      />

      <div class="profile-bottom-box">
        <div class="bottom-box-item bottom-box-left">
          <div class="bottom-box-content">
            <span class="bottom-box-number">3000</span>
            <span class="bottom-box-plus">+</span>
          </div>
          <div class="bottom-box-label">服务客户数量</div>
        </div>

        <div class="bottom-box-item bottom-box-middle">
          <div class="bottom-box-content">
            <span class="bottom-box-number">200</span>
            <span class="bottom-box-plus">+</span>
          </div>
          <div class="bottom-box-label">行业解决方案</div>
        </div>

        <div class="bottom-box-item bottom-box-right">
          <div class="bottom-box-content">
            <span class="bottom-box-number">100</span>
            <span class="bottom-box-plus">+</span>
          </div>
          <div class="bottom-box-label">国家地区覆盖</div>
        </div>
      </div>

      <div class="profile-right-box">
        <h3 class="profile-right-title">AI MATRIX</h3>
        <h4 class="profile-right-subtitle">易客达科技有限公司</h4>
        <p class="profile-right-text">
          易客达科技（AI MATRIX）致力于以AI技术赋能社媒营销。我们通过深度数据洞察与自动化引擎，为企业打造智能引流获客方案，精准提升转化效率。
        </p>
        <p class="profile-right-text">
          我们的解决方案已获众多海外企业验证，正持续驱动业务增长。
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "CompanyProfile",
};
</script>

<style scoped>
@import "../assets/css/companyprofile.css";
</style>

