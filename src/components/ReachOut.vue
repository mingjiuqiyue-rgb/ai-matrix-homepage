<template to="body">
  <div class="reach-out">
    <div class="reach-out-content">
      <div class="reach-out-header">
        <span class="reach-out-header-text">/ AI MATRIX</span>
        <span class="reach-out-header-text"
          >/ Intelligent efficiency improvement</span
        >
        <span class="reach-out-header-text">/ Overseas marketing</span>
      </div>

      <h2 class="reach-out-title">讓增長持續發生</h2>

      

      <div class="reach-out-icons">
        <img
          v-for="(icon, index) in icons"
          :key="index"
          :src="icon.src"
          :alt="icon.alt"
          class="reach-out-icon"
          @click="showModal(icon)"
        />
      </div>
    </div>

    <img
      src="../assets/images/ReachOut/Slice 5@2x.png"
      alt=""
      class="reach-out-bg-img"
    />
  </div>

  <!-- 使用Teleport将弹窗传送到body内部 -->
  <teleport to="body">
    <div
      v-if="modalVisible"
      class="reach-out-modal-overlay"
      @click="closeModal"
    >
      <div class="reach-out-modal-content" @click.stop>
        <img
          :src="currentIcon.modalImage"
          :alt="currentIcon.alt"
          class="reach-out-modal-image"
        />
        <img
          src="../assets/images/QRcode/Slice 41@2x.png"
          alt="关闭"
          class="reach-out-modal-close-icon"
          @click="closeModal"
        />
      </div>
    </div>
  </teleport>
</template>

<script>
export default {
  name: "ReachOut",
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
@import "../assets/css/reachout.css";
</style>
