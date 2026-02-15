<template>
  <div class="oneclick-booking-function">
    <div class="booking-function-header">
      <span class="function-header-text">/ AI MATRIX</span>
      <span class="function-header-text">/ Intelligent efficiency improvement</span>
      <span class="function-header-text">/ Overseas marketing</span>
    </div>

    <h2 class="booking-function-title">一鍵預約，一對一專屬演示</h2>

    <button class="booking-function-demo-btn" @click="scrollToBottom">
      <span class="booking-function-demo-text">預約演示</span>
      <img
        src="../assets/images/public/Slice 6@2x.png"
        alt=""
        class="booking-function-demo-arrow"
      />
    </button>

    <div class="booking-function-icons">
      <img
        v-for="(icon, index) in icons"
        :key="index"
        :src="icon.src"
        :alt="icon.alt"
        class="booking-function-icon"
        @click="showModal(icon)"
      />
    </div>
  </div>

  <!-- 使用Teleport将弹窗传送到body内部 -->
  <teleport to="body">
    <div v-if="modalVisible" class="function-modal-overlay" @click="closeModal">
      <div class="function-modal-content" @click.stop>
        <img
          :src="currentIcon.modalImage"
          :alt="currentIcon.alt"
          class="function-modal-image"
        />
        <img
          src="../assets/images/QRcode/Slice 41@2x.png"
          alt="关闭"
          class="function-modal-close-icon"
          @click="closeModal"
        />
      </div>
    </div>
  </teleport>
</template>

<script>
export default {
  name: "OneclickBookingFunction",
  data() {
    return {
      modalVisible: false,
      currentIcon: null,
      icons: [
        {
          src: require("../assets/images/OneclickBooking/Slice 35@2x.png"),
          alt: "图标1",
          modalImage: require("../assets/images/QRcode/Slice 40@2x (2).png"),
        },
        {
          src: require("../assets/images/OneclickBooking/Slice 35@2x (1).png"),
          alt: "图标2",
          modalImage: require("../assets/images/QRcode/Slice 40@2x.png"),
        },
        {
          src: require("../assets/images/OneclickBooking/Slice 35@2x (2).png"),
          alt: "图标3",
          modalImage: require("../assets/images/QRcode/Slice 40@2x (1).png"),
        },
        {
          src: require("../assets/images/OneclickBooking/Slice 42@2x.png"),
          alt: "图标4",
          modalImage: require("../assets/images/QRcode/Slice 40@2x (1).png"),
        },
      ],
    };
  },
  methods: {
    showModal(icon) {
      this.currentIcon = icon;
      this.modalVisible = true;
    },
    closeModal() {
      this.modalVisible = false;
      this.currentIcon = null;
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
@import "../assets/css/oneclickbookingfunction.css";
</style>
