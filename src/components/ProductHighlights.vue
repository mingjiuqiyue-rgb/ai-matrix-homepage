<template>
  <div class="product-highlights">
    <div class="highlights-badge">
      <svg class="badge-icon" width="22" height="22" viewBox="0 0 22 22">
        <defs>
          <radialGradient id="iconGradient" cx="50%" cy="50%" r="50%">
            <stop offset="29.98%" stop-color="#ffffff" stop-opacity="0" />
            <stop offset="100%" stop-color="#ffffff" stop-opacity="0.6" />
          </radialGradient>
        </defs>
        <circle
          cx="11"
          cy="11"
          r="10"
          fill="url(#iconGradient)"
          stroke="#ffffff4d"
          stroke-width="2"
        />
      </svg>
      <span class="badge-text">highlights</span>
    </div>

    <h2 class="highlights-title">產品功能·亮點展示</h2>

    <img
      src="../assets/images/public/Underscore.png"
      alt=""
      class="highlights-image"
    />

    <div class="highlights-content">
      <div
        class="feature-box"
        :class="{
          'feature-data-collection': true,
          'feature-active': activeFeature === 'data-collection',
          'feature-small': activeFeature !== 'data-collection',
        }"
        @click="setActiveFeature('data-collection')"
      >
        <h3 class="feature-title" v-if="activeFeature === 'data-collection'">
          數據採集
        </h3>
        <h4 class="feature-small-title" v-else>數據採集</h4>

        <p class="feature-subtitle" v-if="activeFeature === 'data-collection'">
          告別手動重複，效率提升300%
        </p>
        <p class="feature-small-subtitle" v-else>告別手動重複</p>

        <div v-if="activeFeature === 'data-collection'">
          <p class="feature-desc">
            好友、小組、達人、主頁、同行數據，批量採集，高效導出
          </p>
          <button class="feature-btn" @click.stop="scrollToBottom">
            <span class="btn-text">預約演示</span>
          </button>
          <img
            src="../assets/images/ProductHighlights/Slice 4@2x.png"
            alt=""
            class="feature-image"
          />
        </div>
        <div v-else>
          <p class="feature-small-desc">效率提升300%</p>
          <p class="feature-small-desc">好友、小組、達人、</p>
          <p class="feature-small-desc">主頁、同行數據高效導出</p>
          <img
            src="../assets/images/ProductHighlights/Slice 13@2x.png"
            alt=""
            class="feature-small-icon"
          />
        </div>
      </div>

      <div
        class="feature-box"
        :class="{
          'feature-browser': true,
          'feature-active': activeFeature === 'browser',
          'feature-small': activeFeature !== 'browser',
        }"
        @click="setActiveFeature('browser')"
      >
        <h3 class="feature-title" v-if="activeFeature === 'browser'">
          指紋瀏覽器
        </h3>
        <h4 class="feature-small-title" v-else>指紋瀏覽器</h4>

        <p class="feature-subtitle" v-if="activeFeature === 'browser'">
          賬號安全管理的"隱形護盾"，集中管理1000+賬號
        </p>
        <p class="feature-small-subtitle" v-else>賬號安全的"隱形護盾"</p>

        <div v-if="activeFeature === 'browser'">
          <p class="feature-desc">權限一鍵移交，杜絕密碼泄露</p>
          <button class="feature-btn" @click.stop="scrollToBottom">
            <span class="btn-text">預約演示</span>
          </button>
          <img
            src="../assets/images/ProductHighlights/Slice 4@2x(2).png"
            alt=""
            class="feature-image"
          />
        </div>
        <div v-else>
          <p class="feature-small-desc">集中管理1000+賬號</p>
          <p class="feature-small-desc">權限一鍵移交</p>
          <img
            src="../assets/images/ProductHighlights/Slice 13@2x.png"
            alt=""
            class="feature-small-icon"
          />
        </div>
      </div>

      <div
        class="feature-box"
        :class="{
          'feature-rpa': true,
          'feature-active': activeFeature === 'rpa',
          'feature-small': activeFeature !== 'rpa',
        }"
        @click="setActiveFeature('rpa')"
      >
        <h3 class="feature-title" v-if="activeFeature === 'rpa'">RPA自動化</h3>
        <h4 class="feature-small-title" v-else>RPA自動化</h4>

        <p class="feature-subtitle" v-if="activeFeature === 'rpa'">
          模擬人工操作
        </p>
        <p class="feature-small-subtitle" v-else>模擬人工操作</p>

        <div v-if="activeFeature === 'rpa'">
          <p class="feature-desc">
            覆蓋批量登錄、發帖、點讚、跨平臺同步等200+動作
          </p>
          <button class="feature-btn" @click.stop="scrollToBottom">
            <span class="btn-text">預約演示</span>
          </button>
          <img
            src="../assets/images/ProductHighlights/Slice 4@2x(1).png"
            alt=""
            class="feature-image"
          />
        </div>
        <div v-else>
          <p class="feature-small-desc">批量登錄、發帖、點贊</p>
          <p class="feature-small-desc">跨平台同步等200+動作</p>
          <img
            src="../assets/images/ProductHighlights/Slice 13@2x.png"
            alt=""
            class="feature-small-icon"
          />
        </div>
      </div>

      <div
        class="feature-box"
        :class="{
          'feature-matrix': true,
          'feature-active': activeFeature === 'matrix',
          'feature-small': activeFeature !== 'matrix',
        }"
        @click="setActiveFeature('matrix')"
      >
        <h3 class="feature-title" v-if="activeFeature === 'matrix'">
          TKMATRIX
        </h3>
        <h4 class="feature-small-title" v-else>TKMATRIX</h4>

        <p class="feature-subtitle" v-if="activeFeature === 'matrix'">
          一鍵託管萬號矩陣，智能引流引爆全球！
        </p>
        <p class="feature-small-subtitle" v-else>一鍵託管矩陣</p>

        <div v-if="activeFeature === 'matrix'">
          <p class="feature-desc">成本直降80%，流量暴漲200%</p>
          <button class="feature-btn" @click.stop="scrollToBottom">
            <span class="btn-text">預約演示</span>
          </button>
          <img
            src="../assets/images/ProductHighlights/Slice 4@2x(3).png"
            alt=""
            class="feature-image"
          />
        </div>
        <div v-else>
          <p class="feature-small-desc">智能引流引爆全球</p>
          <p class="feature-small-desc">成本直降80%</p>
          <p class="feature-small-desc">流量暴漲200%</p>
          <img
            src="../assets/images/ProductHighlights/Slice 13@2x.png"
            alt=""
            class="feature-small-icon"
          />
        </div>
      </div>
    </div>

    <div
      class="highlights-carousel"
      @touchstart="onTouchStart"
      @touchend="onTouchEnd"
    >
      <div
        class="carousel-preview left"
        aria-hidden="true"
        :style="{ backgroundImage: `url(${prevItem.image})` }"
      ></div>
      <div
        class="carousel-preview right"
        aria-hidden="true"
        :style="{ backgroundImage: `url(${nextItem.image})` }"
      ></div>
      <div
        class="carousel-track"
        :style="{ transform: `translateX(calc((100% - var(--slide-width, 100%)) / 2 - ${activeSlide + 1} * var(--slide-width, 100%)))` }"
      >

        <div
          class="carousel-slide"
          v-for="(item, index) in displaySlides"
          :key="`${item.key}-${index}`"
        >

          <div class="carousel-card" :class="`carousel-${item.key}`">

            <h3 class="carousel-title">{{ item.title }}</h3>
            <p class="carousel-subtitle">{{ item.subtitle }}</p>
            <div class="carousel-desc">
              <p v-for="(line, idx) in item.descLines" :key="idx">
                {{ line }}
              </p>
            </div>
            <button class="carousel-btn" @click.stop="scrollToBottom">
              <span class="btn-text">預約演示</span>
            </button>
            <img :src="item.image" alt="" class="carousel-image" />
          </div>

        </div>
      </div>
      <button class="carousel-arrow left" @click="prevSlide" aria-label="上一條">
        <img
          :src="require('../assets/images/Phone/Slice 36@2x.png')"
          alt=""
        />
      </button>
      <button class="carousel-arrow right" @click="nextSlide" aria-label="下一條">
        <img
          :src="require('../assets/images/Phone/Slice 36@2x(1).png')"
          alt=""
        />
      </button>
      <div class="carousel-dots">
        <button
          v-for="(item, index) in carouselFeatures"
          :key="item.key + '-dot'"
          class="carousel-dot"
          :class="{ active: activeSlide === index }"
          @click="setSlide(index)"
          aria-label="切換展示"
        ></button>
      </div>

    </div>
  </div>
</template>


<script>
export default {
  name: "ProductHighlights",
  data() {
    return {
      activeFeature: "data-collection",
      activeSlide: 0,
      touchStartX: 0,
      touchEndX: 0,
      carouselFeatures: [
        {
          key: "data-collection",
          title: "數據採集",
          subtitle: "告別手動重複，效率提升300%",
          descLines: ["好友、小組、達人、主頁、同行數據，批量採集，高效導出"],
          image: require("../assets/images/ProductHighlights/Slice 4@2x.png"),
        },
        {
          key: "browser",
          title: "指紋瀏覽器",
          subtitle: "賬號安全管理的\"隱形護盾\"，集中管理1000+賬號",
          descLines: ["權限一鍵移交，杜絕密碼泄露"],
          image: require("../assets/images/ProductHighlights/Slice 4@2x(2).png"),
        },
        {
          key: "rpa",
          title: "RPA自動化",
          subtitle: "模擬人工操作",
          descLines: ["覆蓋批量登錄、發帖、點讚、跨平臺同步等200+動作"],
          image: require("../assets/images/ProductHighlights/Slice 4@2x(1).png"),
        },
        {
          key: "matrix",
          title: "TKMATRIX",
          subtitle: "一鍵託管萬號矩陣，智能引流引爆全球！",
          descLines: ["成本直降80%，流量暴漲200%"],
          image: require("../assets/images/ProductHighlights/Slice 4@2x(3).png"),
        },
      ],
    };
  },
  computed: {
    displaySlides() {
      if (!this.carouselFeatures || this.carouselFeatures.length === 0) return [];
      const last = this.carouselFeatures[this.carouselFeatures.length - 1];
      const first = this.carouselFeatures[0];
      return [last, ...this.carouselFeatures, first];
    },
    prevItem() {
      const total = this.carouselFeatures.length;
      const index = (this.activeSlide - 1 + total) % total;
      return this.carouselFeatures[index];
    },
    nextItem() {
      const total = this.carouselFeatures.length;
      const index = (this.activeSlide + 1) % total;
      return this.carouselFeatures[index];
    },
  },
  methods: {

    setActiveFeature(feature) {
      this.activeFeature = feature;
    },
    setSlide(index) {
      this.activeSlide = index;
    },
    nextSlide() {
      const nextIndex = (this.activeSlide + 1) % this.carouselFeatures.length;
      this.activeSlide = nextIndex;
    },
    prevSlide() {
      const prevIndex =
        (this.activeSlide - 1 + this.carouselFeatures.length) %
        this.carouselFeatures.length;
      this.activeSlide = prevIndex;
    },
    onTouchStart(event) {
      this.touchStartX = event.changedTouches[0].clientX;
    },
    onTouchEnd(event) {
      this.touchEndX = event.changedTouches[0].clientX;
      const deltaX = this.touchEndX - this.touchStartX;
      if (Math.abs(deltaX) < 40) {
        return;
      }
      if (deltaX < 0) {
        this.nextSlide();
      } else {
        this.prevSlide();
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
@import "../assets/css/producthighlights.css";
</style>
