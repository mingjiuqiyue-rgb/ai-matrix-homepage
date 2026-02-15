<template>
  <div class="data-collection">
    <div class="content-left">
      <video
        ref="videoPlayer"
        :src="videos[currentStep]"
        class="content-video"
        autoplay
        muted
        @ended="onVideoEnded"
        @loadedmetadata="onVideoLoaded"
        tabindex="0"
        @blur="handleBlur"
        @focus="handleFocus"
      ></video>
    </div>
    <div class="content-right">
      <div
        class="content-item"
        :class="{ active: currentStep === 0 }"
        @click="jumpToStep(0)"
      >
        <div class="item-title-row">
          <span class="item-number">01</span>
          <span class="item-title">登錄賬號</span>
        </div>
        <div v-if="currentStep === 0" class="item-description">
          輕鬆登陸社媒，輸入賬號密碼或選擇已經儲存記憶的賬號，進行批量登陸。
        </div>
        <div v-if="currentStep === 0" class="progress-bar-container">
          <div class="progress-bar-bg"></div>
          <div
            class="progress-bar-fill"
            :style="{ width: progressWidth + '%' }"
          ></div>
        </div>
      </div>

      <div
        class="content-item"
        :class="{ active: currentStep === 1 }"
        :style="{
          marginTop:
            currentStep === 0 ? '40px' : currentStep === 1 ? '48px' : '48px',
        }"
        @click="jumpToStep(1)"
      >
        <div class="item-title-row">
          <span class="item-number">02</span>
          <span class="item-title">開始檢索</span>
        </div>
        <div v-if="currentStep === 1" class="item-description">
          輸入或批量導入關鍵詞，添加至列表，輸入完畢後，點擊按鈕開始檢索。
        </div>
        <div v-if="currentStep === 1" class="progress-bar-container">
          <div class="progress-bar-bg"></div>
          <div
            class="progress-bar-fill"
            :style="{ width: progressWidth + '%' }"
          ></div>
        </div>
      </div>

      <div
        class="content-item"
        :class="{ active: currentStep === 2 }"
        :style="{
          marginTop:
            currentStep <= 1
              ? '48px'
              : currentStep === 2
              ? '48px'
              : currentStep === 3
              ? '40px'
              : '48px',
        }"
        @click="jumpToStep(2)"
      >
        <div class="item-title-row">
          <span class="item-number">03</span>
          <span class="item-title">查看數據</span>
        </div>
        <div v-if="currentStep === 2" class="item-description">
          查看採集結果，可複製具體數據，並多選無用數據進行批量刪除。
        </div>
        <div v-if="currentStep === 2" class="progress-bar-container">
          <div class="progress-bar-bg"></div>
          <div
            class="progress-bar-fill"
            :style="{ width: progressWidth + '%' }"
          ></div>
        </div>
      </div>

      <div
        class="content-item"
        :class="{ active: currentStep === 3 }"
        :style="{
          marginTop:
            currentStep <= 2 ? '48px' : currentStep === 3 ? '40px' : '48px',
        }"
        @click="jumpToStep(3)"
      >
        <div class="item-title-row">
          <span class="item-number">04</span>
          <span class="item-title">導出數據</span>
        </div>
        <div v-if="currentStep === 3" class="item-description">
          選擇採集結果，可一鍵批量導出采集數據。
        </div>
        <div
          v-if="currentStep === 3"
          class="progress-bar-container"
          :style="{ marginTop: '60px' }"
        >
          <div class="progress-bar-bg"></div>
          <div
            class="progress-bar-fill"
            :style="{ width: progressWidth + '%' }"
          ></div>
        </div>
      </div>

      <button
        class="content-demo-btn"
        :style="{ marginTop: currentStep === 3 ? '45px' : '53px' }"
        @click="scrollToBottom"
      >
        <span class="datacollection-btn-text">預約演示</span>
      </button>
    </div>
  </div>
</template>

<script>
export default {
  name: "DataCollection",
  data() {
    return {
      currentStep: 0,
      progressWidth: 0,
      videos: [
        require("../assets/videos/1数据采集-登录.mp4"),
        require("../assets/videos/2-数据采集-检索.mp4"),
        require("../assets/videos/3-数据采集-查看.mp4"),
        require("../assets/videos/4-数据采集-导出.mp4"),
      ],
      progressInterval: null,
      wasPlayingBeforeBlur: false,
    };
  },
  beforeUnmount() {
    if (this.progressInterval) {
      clearInterval(this.progressInterval);
    }
  },
  methods: {
    onVideoLoaded() {
      this.startProgress();
    },
    startProgress() {
      if (this.progressInterval) {
        clearInterval(this.progressInterval);
      }
      this.progressWidth = 0;
      const video = this.$refs.videoPlayer;
      if (!video) return;

      this.progressInterval = setInterval(() => {
        if (video.duration) {
          const progress = (video.currentTime / video.duration) * 100;
          this.progressWidth = Math.min(progress, 100);

          if (this.progressWidth >= 100) {
            clearInterval(this.progressInterval);
          }
        }
      }, 30);
    },
    onVideoEnded() {
      if (this.progressInterval) {
        clearInterval(this.progressInterval);
      }
      this.progressWidth = 100;
      setTimeout(() => {
        this.progressWidth = 0;
        this.currentStep = (this.currentStep + 1) % 4;
        this.$nextTick(() => {
          this.playVideo();
        });
      }, 200);
    },
    async playVideo() {
      const video = this.$refs.videoPlayer;
      if (video) {
        try {
          await video.play();
          this.startProgress();
        } catch (error) {
          console.log("Video play interrupted:", error);
          setTimeout(() => {
            this.playVideo();
          }, 100);
        }
      }
    },
    jumpToStep(step) {
      if (this.progressInterval) {
        clearInterval(this.progressInterval);
      }
      this.currentStep = step;
      this.progressWidth = 0;
      const video = this.$refs.videoPlayer;
      if (video) {
        video.currentTime = 0;
        this.$nextTick(() => {
          this.playVideo();
        });
      }
    },
    scrollToBottom() {
      window.scrollTo({
        top: document.documentElement.scrollHeight,
        behavior: "smooth",
      });
    },
    handleBlur() {
      const video = this.$refs.videoPlayer;
      if (video && !video.paused) {
        this.wasPlayingBeforeBlur = true;
        video.pause();
        if (this.progressInterval) {
          clearInterval(this.progressInterval);
        }
      }
    },
    handleFocus() {
      const video = this.$refs.videoPlayer;
      if (video && this.wasPlayingBeforeBlur) {
        this.wasPlayingBeforeBlur = false;
        video.play();
        this.startProgress();
      }
    },
  },
};
</script>

<style scoped>
@import "../assets/css/datacollection.css";
</style>
