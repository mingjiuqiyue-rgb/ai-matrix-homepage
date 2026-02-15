<template>
  <div class="product-features-page">
    <ProductFunction />
    <FunctionDisplay />
    <OneclickBookingFunction />
  </div>
</template>

<script>
import ProductFunction from "../components/ProductFunction.vue";
import FunctionDisplay from "../components/FunctionDisplay.vue";
import OneclickBookingFunction from "../components/OneclickBookingFunction.vue";

export default {
  name: "ProductFeaturesPage",
  components: {
    ProductFunction,
    FunctionDisplay,
    OneclickBookingFunction,
  },
  mounted() {
    this.setupScrollAnimation();
  },
  methods: {
    setupScrollAnimation() {
      const sections = document.querySelectorAll('.product-features-page > div:not(:first-child)');
      
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
@import "../assets/css/productfeatures.css";
</style>

