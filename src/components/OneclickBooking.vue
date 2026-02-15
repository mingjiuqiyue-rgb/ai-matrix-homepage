<template>
  <div class="oneclick-booking" ref="bookingContainer">
    <div class="booking-header">
      <span class="header-text">/ AI MATRIX</span>
      <span class="header-text">/ Intelligent efficiency improvement</span>
      <span class="header-text">/ Overseas marketing</span>
    </div>

    <h2 class="booking-title">一鍵預約，一對一專屬演示</h2>

    <button class="booking-demo-btn" @click="scrollToBottom">
      <span class="booking-demo-text">預約演示</span>
      <img
        src="../assets/images/public/Slice 6@2x.png"
        alt=""
        class="booking-demo-arrow"
      />
    </button>

    <div class="booking-icons">
      <img
        v-for="(icon, index) in icons"
        :key="index"
        :src="icon.src"
        :alt="icon.alt"
        class="booking-icon"
        @click="showModal(icon)"
      />
    </div>

    <!-- 使用Teleport将弹窗传送到body内部 -->
    <teleport to="body">
      <div v-if="modalVisible" class="modal-overlay" @click="closeModal">
        <div class="modal-content" @click.stop>
          <img
            :src="currentIcon.modalImage"
            :alt="currentIcon.alt"
            class="modal-image"
          />
          <img
            src="../assets/images/QRcode/Slice 41@2x.png"
            alt="关闭"
            class="modal-close-icon"
            @click="closeModal"
          />
        </div>
      </div>
    </teleport>
  </div>
</template>

<script>
export default {
  name: "OneclickBooking",
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
  mounted() {
    // 组件挂载后确保背景图正确显示
    setTimeout(() => {
      if (this.$refs.bookingContainer) {
        this.$refs.bookingContainer.style.backgroundImage = "url('" + require("../assets/images/OneclickBooking/Slice 5@2x.png") + "')";
        this.$refs.bookingContainer.style.backgroundSize = "cover";
        this.$refs.bookingContainer.style.backgroundPosition = "center";
        this.$refs.bookingContainer.style.backgroundRepeat = "no-repeat";
      }
    }, 500);
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
@import "../assets/css/oneclickbooking.css";
</style>
