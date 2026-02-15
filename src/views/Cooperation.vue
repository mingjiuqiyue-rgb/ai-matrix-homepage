<template>
  <div class="cooperation-page">
    <ChannelCooperation />
    <MutuallyBeneficial />
    <CooperationProcess />
    <WorkTogether />
  </div>
</template>

<script>
import ChannelCooperation from "../components/ChannelCooperation.vue";
import MutuallyBeneficial from "../components/MutuallyBeneficial.vue";
import CooperationProcess from "../components/CooperationProcess.vue";
import WorkTogether from "../components/WorkTogether.vue";

export default {
  name: "CooperationPage",
  components: {
    ChannelCooperation,
    MutuallyBeneficial,
    CooperationProcess,
    WorkTogether,
  },
  mounted() {
    this.setupScrollAnimation();
  },
  methods: {
    setupScrollAnimation() {
      const sections = document.querySelectorAll('.cooperation-page > div:not(:first-child)');
      
      const observer = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
          if (entry.isIntersecting) {
            entry.target.classList.add('animate');
          }
        });
      }, {
        threshold: 0.1 // 当模块10%进入视口时触发
      });
      
      sections.forEach(section => {
        observer.observe(section);
      });
    }
  }
};
</script>

<style scoped>
@import "../assets/css/cooperation.css";
</style>
