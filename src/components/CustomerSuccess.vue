<template>
  <div class="customer-success">
    <div class="success-badge">
      <svg class="badge-icon" width="22" height="22" viewBox="0 0 22 22">
        <defs>
          <radialGradient id="successIconGradient" cx="50%" cy="50%" r="50%">
            <stop offset="29.98%" stop-color="#ffffff" stop-opacity="0" />
            <stop offset="100%" stop-color="#ffffff" stop-opacity="0.6" />
          </radialGradient>
        </defs>
        <circle
          cx="11"
          cy="11"
          r="10"
          fill="url(#successIconGradient)"
          stroke="#ffffff4d"
          stroke-width="2"
        />
      </svg>
      <span class="badge-text">success</span>
    </div>

    <h2 class="success-title">客戶實證·成功案例</h2>

    <img
      src="../assets/images/public/Underscore.png"
      alt=""
      class="success-image"
    />

    <div class="success-content">
      <div class="cases-container" :style="{ '--active-case': activeCase }">
        <div
          class="case-box case-software"
          :class="{
            'case-active': activeCase === 0,
            'case-small': activeCase !== 0,
            'case-visible': isVisible(0),
          }"
          @click="setActiveCase(0)"
        >
          <div v-if="activeCase === 0" class="case-content">
            <div class="case-header">
              <img
                src="../assets/images/CustomerSuccess/Slice 14@2x.png"
                alt="软件"
                class="industry-icon"
              />
              <span class="industry-text">軟 件</span>
            </div>

            <div class="case-name">Jonathan</div>

            <div class="case-position">Social Media Manager</div>

            <img
              src="../assets/images/CustomerSuccess/Slice 41@2x.png"
              alt="Jonathan"
              class="case-person-photo"
            />

            <div class="active-info-box">
              <div class="case-data">
                <div class="data-title">獲客成本</div>
                <div class="data-content">
                  <img
                    src="../assets/images/CustomerSuccess/Slice 15@2x.png"
                    alt="下降"
                    class="data-icon"
                  />
                  <div class="data-text-group">
                    <span class="data-text">下降</span>
                    <span class="data-number">25</span>
                    <span class="data-percent">%</span>
                  </div>
                </div>
              </div>
              <div class="case-description">
                AI
                MATRIX降低了付費廣告浪費，精準定位高意向用戶，減少無效線索數量。提高線索轉化率，縮短成交路徑，自動化培育潛在客戶。
              </div>
            </div>
          </div>

          <div v-else class="case-small-content">
            <img
              src="../assets/images/CustomerSuccess/Slice 40@2x.png"
              alt="Jonathan"
              class="small-person-photo"
            />
            <div class="small-info-container">
              <div class="small-name">Jonathan</div>
              <div class="small-position-group">
                <div class="small-position">軟件</div>
                <div class="small-industry">Social Media Manager</div>
              </div>
            </div>
          </div>
        </div>

        <div
          class="case-box case-beauty"
          :class="{
            'case-active': activeCase === 1,
            'case-small': activeCase !== 1,
            'case-visible': isVisible(1),
          }"
          @click="setActiveCase(1)"
        >
          <div v-if="activeCase === 1" class="case-content">
            <div class="case-header">
              <img
                src="../assets/images/CustomerSuccess/Slice 20@2x.png"
                alt="美妆"
                class="industry-icon"
              />
              <span class="industry-text">美 妝</span>
            </div>
            <div class="case-name">Oliver</div>
            <div class="case-position">Social Media Manager</div>
            <img
              src="../assets/images/CustomerSuccess/Slice 41@2x (1).png"
              alt="Oliver"
              class="case-person-photo"
            />
            <div class="active-info-box">
              <div class="case-data">
                <div class="data-title">每年節省人工成本</div>
                <div class="data-content case2-data">
                  <div class="data-text-group">
                    <span class="data-number">800</span>
                    <span class="data-percent">萬</span>
                  </div>
                </div>
              </div>
              <div class="case-description">
                TK
                MATRIX的出現讓原本需要昂貴外包或專職設計師完成的社交媒體文案、廣告語、甚至圖片和視頻，現在可以透過工具快速低成本生成。
              </div>
            </div>
          </div>
          <div v-else class="case-small-content">
            <img
              src="../assets/images/CustomerSuccess/Slice 40@2x (1).png"
              alt="Oliver"
              class="small-person-photo"
            />
            <div class="small-info-container">
              <div class="small-name">Oliver</div>
              <div class="small-position-group">
                <div class="small-position">美妝</div>
                <div class="small-industry">Social Media Manager</div>
              </div>
            </div>
          </div>
        </div>

        <div
          class="case-box case-food"
          :class="{
            'case-active': activeCase === 2,
            'case-small': activeCase !== 2,
            'case-visible': isVisible(2),
          }"
          @click="setActiveCase(2)"
        >
          <div v-if="activeCase === 2" class="case-content">
            <div class="case-header">
              <img
                src="../assets/images/CustomerSuccess/Slice 45@2x.png"
                alt="食品"
                class="industry-icon"
              />
              <span class="industry-text">食 品</span>
            </div>
            <div class="case-name">Sophia</div>
            <div class="case-position">Social Media Manager</div>
            <img
              src="../assets/images/CustomerSuccess/Slice 41@2x (2).png"
              alt="Sophia"
              class="case-person-photo"
            />
            <div class="active-info-box">
              <div class="case-data">
                <div class="data-title">內容與創意生產效率</div>
                <div class="data-content case3-data">
                  <img
                    src="../assets/images/CustomerSuccess/Slice 15@2x.png"
                    alt="上升"
                    class="data-icon rotated-icon"
                  />
                  <div class="data-text-group">
                    <span class="data-text">提升</span>
                    <span class="data-number">80</span>
                    <span class="data-percent">%</span>
                  </div>
                </div>
              </div>
              <div class="case-description">
                AI
                MATRIX工具可以代替銷售完成初步的數據採集、資訊跟進、信息私信等工作，将销售人力从重复性劳动中解放出来。
              </div>
            </div>
          </div>
          <div v-else class="case-small-content">
            <img
              src="../assets/images/CustomerSuccess/Slice 40@2x (2).png"
              alt="Sophia"
              class="small-person-photo"
            />
            <div class="small-info-container">
              <div class="small-name">Sophia</div>
              <div class="small-position-group">
                <div class="small-position">食品</div>
                <div class="small-industry">Social Media Manager</div>
              </div>
            </div>
          </div>
        </div>

        <div
          class="case-box case-jewelry"
          :class="{
            'case-active': activeCase === 3,
            'case-small': activeCase !== 3,
            'case-visible': isVisible(3),
          }"
          @click="setActiveCase(3)"
        >
          <div v-if="activeCase === 3" class="case-content">
            <div class="case-header">
              <img
                src="../assets/images/CustomerSuccess/Slice 46@2x.png"
                alt="珠宝"
                class="industry-icon"
              />
              <span class="industry-text">珠寶</span>
            </div>
            <div class="case-name">Daily Vu</div>
            <div class="case-position">Social Media Manager</div>
            <img
              src="../assets/images/CustomerSuccess/Slice 41@2x (3).png"
              alt="Daily Vu"
              class="case-person-photo"
            />
            <div class="active-info-box">
              <div class="case-data">
                <div class="data-title">推廣預算</div>
                <div class="data-content">
                  <img
                    src="../assets/images/CustomerSuccess/Slice 15@2x.png"
                    alt="降低"
                    class="data-icon"
                  />
                  <div class="data-text-group">
                    <span class="data-text">降低</span>
                    <span class="data-number">40</span>
                    <span class="data-percent">%</span>
                  </div>
                </div>
              </div>
              <div class="case-description">
                數據採集工具可以清晰告訴你哪個渠道帶來的客戶最優質，從而果斷削減無效渠道的預算，將資源集中到高產出的地方，避免浪費。
              </div>
            </div>
          </div>
          <div v-else class="case-small-content">
            <img
              src="../assets/images/CustomerSuccess/Slice 40@2x (3).png"
              alt="Daily Vu"
              class="small-person-photo"
            />
            <div class="small-info-container">
              <div class="small-name">Daily Vu</div>
              <div class="small-position-group">
                <div class="small-position">珠寶</div>
                <div class="small-industry">Sales manager</div>
              </div>
            </div>
          </div>
        </div>

        <div
          class="case-box case-apparel"
          :class="{
            'case-active': activeCase === 4,
            'case-small': activeCase !== 4,
            'case-visible': isVisible(4),
          }"
          @click="setActiveCase(4)"
        >
          <div v-if="activeCase === 4" class="case-content">
            <div class="case-header">
              <img
                src="../assets/images/CustomerSuccess/Slice 27@2x.png"
                alt="服饰"
                class="industry-icon"
              />
              <span class="industry-text">服 飾</span>
            </div>
            <div class="case-name">Emma</div>
            <div class="case-position">Social Media Manager</div>
            <img
              src="../assets/images/CustomerSuccess/Slice 41@2x (4).png"
              alt="Emma"
              class="case-person-photo"
            />
            <div class="active-info-box">
              <div class="case-data">
                <div class="data-title">量產超60萬播放量的爆款視頻</div>
                <div class="data-content case5-data">
                  <div class="data-text-group">
                    <span class="data-number">60</span>
                    <span class="data-percent">萬</span>
                  </div>
                </div>
              </div>
              <div class="case-description">
                TK
                MATRIX工具大幅降低模特拍攝、外景、修圖、平面設計的成本和時間，加快上新速度。
              </div>
            </div>
          </div>
          <div v-else class="case-small-content">
            <img
              src="../assets/images/CustomerSuccess/Slice 40@2x (4).png"
              alt="Emma"
              class="small-person-photo"
            />
            <div class="small-info-container">
              <div class="small-name">Emma</div>
              <div class="small-position-group">
                <div class="small-position">服飾</div>
                <div class="small-industry">Social Media Manager</div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div class="nav-arrows">
      <img
        src="../assets/images/CustomerSuccess/Slice 34@2x.png"
        alt="上一个"
        class="nav-arrow left-arrow"
        @click="prevCase"
      />
      <img
        src="../assets/images/CustomerSuccess/Slice 34@2x (1).png"
        alt="下一个"
        class="nav-arrow right-arrow"
        @click="nextCase"
      />
    </div>
  </div>
</template>

<script>
export default {
  name: "CustomerSuccess",
  data() {
    return {
      activeCase: 0,
      previousCase: 0,
      isTransitioning: false,
      isMobile: false,
      resizeHandler: null,
    };
  },
  mounted() {
    this.updateIsMobile();
    this.resizeHandler = () => this.updateIsMobile();
    window.addEventListener("resize", this.resizeHandler);
  },
  beforeUnmount() {
    if (this.resizeHandler) {
      window.removeEventListener("resize", this.resizeHandler);
    }
  },
  methods: {
    updateIsMobile() {
      if (typeof window === "undefined") {
        return;
      }
      this.isMobile = window.innerWidth <= 768;
    },
    isVisible(index) {
      if (this.isMobile) {
        return true;
      }
      if (this.isTransitioning) {
        if (this.previousCase === 4 && this.activeCase === 0) {
          return [3, 4, 0, 1].includes(index);
        }
        if (this.previousCase === 0 && this.activeCase === 4) {
          return [3, 4, 0, 1].includes(index);
        }
      }

      if (this.activeCase === 0) {
        return [0, 1, 2].includes(index);
      } else if (this.activeCase === 4) {
        return [2, 3, 4].includes(index);
      } else {
        const prevIndex = this.activeCase - 1;
        const nextIndex = this.activeCase + 1;
        return [prevIndex, this.activeCase, nextIndex].includes(index);
      }
    },
    setActiveCase(index) {
      this.previousCase = this.activeCase;
      this.activeCase = index;

      if (
        (this.previousCase === 0 && index === 4) ||
        (this.previousCase === 4 && index === 0)
      ) {
        this.isTransitioning = true;
        setTimeout(() => {
          this.isTransitioning = false;
        }, 500);
      }
    },
    prevCase() {
      this.previousCase = this.activeCase;
      this.activeCase = (this.activeCase - 1 + 5) % 5;

      if (
        (this.previousCase === 0 && this.activeCase === 4) ||
        (this.previousCase === 4 && this.activeCase === 0)
      ) {
        this.isTransitioning = true;
        setTimeout(() => {
          this.isTransitioning = false;
        }, 500);
      }
    },
    nextCase() {
      this.previousCase = this.activeCase;
      this.activeCase = (this.activeCase + 1) % 5;

      if (
        (this.previousCase === 0 && this.activeCase === 4) ||
        (this.previousCase === 4 && this.activeCase === 0)
      ) {
        this.isTransitioning = true;
        setTimeout(() => {
          this.isTransitioning = false;
        }, 500);
      }
    },
  },
};
</script>

<style scoped>
@import "../assets/css/customersuccess.css";
</style>
