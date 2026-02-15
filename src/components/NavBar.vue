<template>
  <nav class="navbar">
    <div class="navbar-top-mobile">
      <div class="navbar-logo-mobile" @click="navigateTo('/')">
        <img src="../assets/images/NavBar/logo.png" alt="Logo" class="logo-img-mobile" />
        <span class="logo-text-mobile">AI MATRIX</span>
      </div>
      <div class="navbar-bot-icon">
        <div class="bot-circle">
          <img src="../assets/videos/客服动效.gif" alt="Bot Icon" class="bot-gif-mobile" />
        </div>
      </div>
    </div>
    <div class="navbar-container">
      <div class="navbar-logo" @click="navigateTo('/')" style="cursor: pointer;">
        <img
          src="../assets/images/NavBar/logo.png"
          alt="Logo"
          class="logo-img"
        />
        <span class="logo-text">AI Matrix</span>
      </div>

      <button class="hamburger" :class="{ open: menuOpen }" @click="toggleMenu" aria-label="Toggle menu">
        <span></span>
        <span></span>
        <span></span>
      </button>

      <ul class="navbar-menu" :class="{ 'menu-open': menuOpen }">
        <li class="menu-item" :class="{ active: activeSection === 'home' }">
          <a href="/" @click.prevent="navigateTo('/')">首頁</a>
        </li>
        <li class="menu-item" :class="{ active: activeSection === 'products' }">
          <a href="/products" @click.prevent="navigateTo('/products')"
            >產品功能</a
          >
        </li>
        <li
          class="menu-item"
          :class="{ active: activeSection === 'cooperation' }"
        >
          <a href="/cooperation" @click.prevent="navigateTo('/cooperation')"
            >渠道合作</a
          >
        </li>
        <li class="menu-item" :class="{ active: activeSection === 'about' }">
          <a href="/about" @click.prevent="navigateTo('/about')">關於我們</a>
        </li>
        <li class="menu-item">
          <a href="#contact" @click.prevent="scrollToBottom">聯繫我們</a>
        </li>
      </ul>

      <div class="navbar-action">
        <button class="btn-demo" @click="scrollToBottom">預約演示</button>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  name: "NavBar",
  data() {
    return {
      activeSection: "home",
      menuOpen: false,
    };
  },
  mounted() {
    this.updateActiveSection();
  },
  watch: {
    $route() {
      this.updateActiveSection();
    },
  },
  methods: {
    updateActiveSection() {
      const path = this.$route.path;
      if (path.startsWith("/products")) {
        this.activeSection = "products";
      } else if (path.startsWith("/cooperation")) {
        this.activeSection = "cooperation";
      } else if (path.startsWith("/about")) {
        this.activeSection = "about";
      } else {
        this.activeSection = "home";
      }
    },
    navigateTo(path) {
      this.menuOpen = false;
      if (this.$route.path !== path) {
        this.$router.push(path);
      }
    },
    toggleMenu() {
      this.menuOpen = !this.menuOpen;
    },
    scrollToBottom() {
      this.menuOpen = false;
      window.scrollTo({
        top: document.documentElement.scrollHeight,
        behavior: "smooth",
      });
    },
  },
};
</script>

<style scoped>
@import "../assets/css/navbar.css";
</style>
