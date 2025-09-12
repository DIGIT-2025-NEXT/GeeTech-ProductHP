<template>
  <nav class="navigation" :class="{ 'scrolled': isScrolled }">
    <div class="container">
      <div class="nav-content">
        <div class="logo">
          <svg width="32" height="32" viewBox="0 0 32 32" fill="none">
            <rect width="32" height="32" rx="8" fill="#111"/>
            <path d="M8 12h16v2H8v-2zm0 4h16v2H8v-2zm0 4h10v2H8v-2z" fill="#fff"/>
          </svg>
          <span>KITAQstartup</span>
        </div>
        <ul class="nav-links">
          <li><a href="#features">特徴</a></li>
          <li><a href="#how-it-works">仕組み</a></li>
          <li><a href="#benefits">効果</a></li>
          <li><a href="#contact" class="cta-button">始める</a></li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  name: 'Navigation',
  data() {
    return {
      isScrolled: false
    }
  },
  mounted() {
    window.addEventListener('scroll', this.handleScroll)
  },
  beforeUnmount() {
    window.removeEventListener('scroll', this.handleScroll)
  },
  methods: {
    handleScroll() {
      this.isScrolled = window.scrollY > 50
    }
  }
}
</script>

<style scoped>
.navigation {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 1000;
  background: rgba(255, 255, 255, 0.95);
  backdrop-filter: blur(10px);
  border-bottom: 1px solid transparent;
  transition: all 0.3s ease;
}

.navigation.scrolled {
  background: rgba(255, 255, 255, 0.98);
  border-bottom: 1px solid rgba(17, 17, 17, 0.1);
}

.nav-content {
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 80px;
}

.logo {
  display: flex;
  align-items: center;
  gap: 12px;
  font-weight: 600;
  font-size: 18px;
  color: #111;
}

.nav-links {
  display: flex;
  list-style: none;
  gap: 32px;
  align-items: center;
}

.nav-links a {
  text-decoration: none;
  color: #111;
  font-weight: 400;
  font-size: 15px;
  transition: color 0.2s ease;
}

.nav-links a:hover {
  color: #666;
}

.cta-button {
  background: #111 !important;
  color: #fff !important;
  padding: 12px 24px;
  border-radius: 8px;
  font-weight: 500;
  transition: all 0.2s ease;
}

.cta-button:hover {
  background: #333 !important;
  transform: translateY(-1px);
}

@media (max-width: 768px) {
  .nav-links {
    gap: 20px;
  }
  
  .nav-links a {
    font-size: 14px;
  }
  
  .cta-button {
    padding: 10px 20px;
    font-size: 14px;
  }
}
</style>