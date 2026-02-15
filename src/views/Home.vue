<template>
  <div class="home-page">
    <div class="home-bg-image"></div>
    <HeroSection />
    <div class="mobile-section-tabs">
      <button class="tab-item active" @click="scrollToSection('section-highlights')">
        亮點展示
      </button>
      <button class="tab-item" @click="scrollToSection('section-success')">
        成功案例
      </button>
      <button class="tab-item" @click="scrollToSection('section-recommend')">
        種草營銷
      </button>
      <button class="tab-item" @click="scrollToSection('section-global')">
        一鍵全球
      </button>
    </div>
    <div id="section-highlights">
      <ProductHighlights ref="section" />
    </div>
    <div id="section-success">
      <CustomerSuccess ref="section" />
    </div>
    <div id="section-recommend">
      <RecommendEffect ref="section" />
    </div>
    <div id="section-global">
      <MultipleRoutes ref="section" />
    </div>
    <div id="section-booking">
      <OneclickBooking ref="section" />
    </div>
  </div>

</template>

<script>
import HeroSection from "../components/HeroSection.vue";
import ProductHighlights from "../components/ProductHighlights.vue";
import CustomerSuccess from "../components/CustomerSuccess.vue";
import RecommendEffect from "../components/RecommendEffect.vue";
import MultipleRoutes from "../components/MultipleRoutes.vue";
import OneclickBooking from "../components/OneclickBooking.vue";

export default {
  name: "HomePage",
  components: {
    HeroSection,
    ProductHighlights,
    CustomerSuccess,
    RecommendEffect,
    MultipleRoutes,
    OneclickBooking,
  },
  mounted() {
    this.setupScrollAnimation();
  },
  methods: {
    setupScrollAnimation() {
      const sections = document.querySelectorAll(
        ".home-page > div:not(.hero-section)",
      );

      const observer = new IntersectionObserver(
        (entries) => {
          entries.forEach((entry) => {
            if (entry.isIntersecting) {
              entry.target.classList.add("animate");
            }
          });
        },
        {
          threshold: 0.1, // 当模块10%进入视口时触发
        },
      );

      sections.forEach((section) => {
        observer.observe(section);
      });
    },
    scrollToSection(id) {
      const target = document.getElementById(id);
      if (!target) {
        return;
      }
      target.scrollIntoView({ behavior: "smooth", block: "start" });
    },
  },
};

</script>

<style scoped>
@import "../assets/css/home.css";
</style>
