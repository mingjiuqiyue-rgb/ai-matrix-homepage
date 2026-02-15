<template>
  <div class="about-page">
    <AboutUs />
    <CompanyProfile />
    <CompanyCulture />
    <CompetitiveAdvantage />
    <ReachOut />
  </div>
</template>

<script>
import AboutUs from "../components/AboutUs.vue";
import CompanyProfile from "../components/CompanyProfile.vue";
import CompanyCulture from "../components/CompanyCulture.vue";
import CompetitiveAdvantage from "../components/CompetitiveAdvantage.vue";
import ReachOut from "../components/ReachOut.vue";

export default {
  name: "AboutPage",
  components: {
    AboutUs,
    CompanyProfile,
    CompanyCulture,
    CompetitiveAdvantage,
    ReachOut,
  },
  mounted() {
    this.setupScrollAnimation();
  },
  methods: {
    setupScrollAnimation() {
      const sections = document.querySelectorAll(
        ".about-page > div:not(:first-child)",
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
  },
};
</script>

<style scoped>
@import "../assets/css/about.css";
</style>
