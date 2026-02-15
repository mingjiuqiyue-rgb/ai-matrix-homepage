<template>
  <div class="tk-matrix">
    <div class="tk-left-box">
      <div class="tk-step-item">
        <div class="tk-step-header">
          <span class="tk-step-label">STEP 1</span>
          <span class="tk-step-title">添加任務</span>
        </div>
        <p class="tk-step-description">輸入視頻鏈接，選擇任務類型，生成結果內容</p>
      </div>

      <div class="tk-step-item">
        <div class="tk-step-header">
          <span class="tk-step-label">STEP 2</span>
          <span class="tk-step-title">執行任務</span>
        </div>
        <p class="tk-step-description">AI快速完成生產任務，高效產出精彩內容</p>
      </div>

      <div class="tk-step-item">
        <div class="tk-step-header">
          <span class="tk-step-label">STEP 3</span>
          <span class="tk-step-title">導出結果</span>
        </div>
        <p class="tk-step-description">下載高品質視頻，發布至TikTok獲得流量收益</p>
      </div>
    </div>

    <div class="tk-right-box">
      <h3 class="tk-right-title">TK MATRIX·功能展示</h3>
      <div class="tk-video-container">
        <video
          ref="tkVideo"
          src="../assets/videos/4 TK MATRIX.mp4"
          class="tk-video"
          :class="{ paused: !isPlaying && !isSeeking, seeking: isSeeking }"
          loop
          controls
          @play="handlePlay"
          @pause="handlePause"
          @seeking="handleSeeking"
          @seeked="handleSeeked"
          @mousedown="handleMouseDown"
          tabindex="0"
          @blur="handleBlur"
          @focus="handleFocus"
        ></video>
        <div v-show="showOverlay && !isSeeking" class="tk-play-overlay" @click.stop="togglePlay">
          <div class="tk-play-button">
            <div class="play-icon"></div>
          </div>
        </div>
      </div>
      <button class="tk-demo-btn" @click="scrollToBottom">
        <span class="tk-demo-text">預約演示</span>
      </button>
    </div>
  </div>
</template>

<script>
export default {
  name: "TKMatrix",
  data() {
    return {
      isPlaying: false,
      showOverlay: true,
      isSeeking: false,
      wasPlayingBeforeBlur: false,
      observer: null,
      wasPlayingBeforeSeeking: false,
    };
  },
  mounted() {
    this.initIntersectionObserver();
  },
  beforeUnmount() {
    if (this.observer) {
      this.observer.disconnect();
    }
  },
  methods: {
    initIntersectionObserver() {
      this.observer = new IntersectionObserver(
        (entries) => {
          entries.forEach((entry) => {
            const video = this.$refs.tkVideo;
            if (video && !entry.isIntersecting && !video.paused) {
              video.pause();
            }
          });
        },
        { root: null, threshold: 0.5 }
      );
      if (this.$refs.tkVideo) {
        this.observer.observe(this.$refs.tkVideo);
      }
    },
    togglePlay() {
      const video = this.$refs.tkVideo;
      if (video.paused) {
        video.play();
      } else {
        video.pause();
      }
    },
    handlePlay() {
      this.isPlaying = true;
      this.showOverlay = false;
    },
    handlePause() {
      if (this.isSeeking) {
        this.$nextTick(() => {
          const video = this.$refs.tkVideo;
          if (video && this.wasPlayingBeforeSeeking) {
            video.play().catch(() => {});
          }
        });
        return;
      }
      this.isPlaying = false;
      this.showOverlay = true;
    },
    handleSeeking() {
      if (!this.isSeeking) {
        this.wasPlayingBeforeSeeking = this.isPlaying;
      }
      this.isSeeking = true;
    },
    handleSeeked() {
      const video = this.$refs.tkVideo;
      if (video && this.wasPlayingBeforeSeeking && video.paused) {
        video.play().catch(() => {});
      }
      setTimeout(() => {
        this.isSeeking = false;
      }, 100);
    },
    handleMouseDown() {
      this.wasPlayingBeforeSeeking = this.isPlaying;
    },
    handleBlur() {
      const video = this.$refs.tkVideo;
      if (video && !video.paused) {
        this.wasPlayingBeforeBlur = true;
        video.pause();
      }
    },
    handleFocus() {
      const video = this.$refs.tkVideo;
      if (video && this.wasPlayingBeforeBlur) {
        this.wasPlayingBeforeBlur = false;
        video.play();
      }
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
@import "../assets/css/tkmatrix.css";
</style>
