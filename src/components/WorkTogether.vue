<template>
  <div class="work-together">
    <img :src="gifUrl" alt="" class="work-together-bg-gif" />
    <div class="work-together-overlay"></div>

    <div class="work-together-content">
      <div class="work-together-header">
        <span class="work-together-header-text">/ AI MATRIX</span>
        <span class="work-together-header-text"
          >/ Intelligent efficiency improvement</span
        >
        <span class="work-together-header-text">/ Overseas marketing</span>
      </div>

      <h2 class="work-together-title">讓增長持續發生</h2>

      <button class="work-together-demo-btn" @click="scrollToBottom">
        <span class="work-together-demo-text">聯係我們</span>
        <img
          src="../assets/images/public/Slice 6@2x.png"
          alt=""
          class="work-together-demo-arrow"
        />
      </button>

      <div class="work-together-icons">
      <img
        v-for="(icon, index) in icons"
        :key="index"
        :src="icon.src"
        :alt="icon.alt"
        class="work-together-icon"
        @click="showModal(icon)"
      />
    </div>
  </div>

  <!-- 使用Teleport将弹窗传送到body内部 -->
  <teleport to="body">
    <div
      v-if="modalVisible"
      class="work-together-modal-overlay"
      @click="closeModal"
    >
      <div class="work-together-modal-content" @click.stop>
        <img
          :src="currentIcon.modalImage"
          :alt="currentIcon.alt"
          class="work-together-modal-image"
        />
        <img
          src="../assets/images/QRcode/Slice 41@2x.png"
          alt="关闭"
          class="work-together-modal-close-icon"
          @click="closeModal"
        />
      </div>
    </div>
  </teleport>
  </div>
</template>

<script>
export default {
  name: "WorkTogether",
  data() {
    return {
      modalVisible: false,
      currentIcon: null,
      gifUrl: "",
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
    this.gifUrl = `${require("../assets/videos/4.16MB渠道合作-结尾.gif")}?t=${Date.now()}`;
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
@import "../assets/css/worktogether.css";
</style>
