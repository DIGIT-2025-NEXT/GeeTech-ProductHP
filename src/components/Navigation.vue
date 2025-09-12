<template>
  <nav class="navigation" :class="{ 'scrolled': isScrolled }">
    <div class="container">
      <div class="nav-content">
        <div class="logo">
          <span>kitaq_startup</span>
        </div>
        <ul class="nav-links desktop-nav">
          <li><a href="#features">特徴</a></li>
          <li><a href="#how-it-works">仕組み</a></li>
          <li><a href="#benefits">効果</a></li>
          <li><a href="https://geetech.dokkiitech.dev/" target="_blank" rel="noopener noreferrer" class="cta-button">始める</a></li>
        </ul>
        <button class="hamburger-menu" :class="{ 'menu-open': isMobileMenuOpen }" @click="toggleMobileMenu">
          <svg v-if="!isMobileMenuOpen" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
            <line x1="3" y1="6" x2="21" y2="6"></line>
            <line x1="3" y1="12" x2="21" y2="12"></line>
            <line x1="3" y1="18" x2="21" y2="18"></line>
          </svg>
          <svg v-else width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
            <line x1="18" y1="6" x2="6" y2="18"></line>
            <line x1="6" y1="6" x2="18" y2="18"></line>
          </svg>
        </button>
      </div>
    </div>
    <div class="mobile-menu" :class="{ 'active': isMobileMenuOpen }">
      <div class="mobile-menu-content">
        <ul class="mobile-nav-links">
          <li><a href="#features" @click="closeMobileMenu">特徴</a></li>
          <li><a href="#how-it-works" @click="closeMobileMenu">仕組み</a></li>
          <li><a href="#benefits" @click="closeMobileMenu">効果</a></li>
          <li><a href="https://geetech.dokkiitech.dev/" target="_blank" rel="noopener noreferrer" class="mobile-cta-button" @click="closeMobileMenu">始める</a></li>
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
      isScrolled: false,
      isMobileMenuOpen: false
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
    },
    toggleMobileMenu() {
      this.isMobileMenuOpen = !this.isMobileMenuOpen
      if (this.isMobileMenuOpen) {
        document.body.style.overflow = 'hidden'
      } else {
        document.body.style.overflow = ''
      }
    },
    closeMobileMenu() {
      this.isMobileMenuOpen = false
      document.body.style.overflow = ''
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
  font-family: var(--audiowide);
  font-weight: 400;
  font-size: 18px;
  color: #111;
  letter-spacing: 0.5px;
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

.hamburger-menu {
  display: none;
  justify-content: center;
  align-items: center;
  width: 40px;
  height: 40px;
  background: none;
  border: none;
  cursor: pointer;
  padding: 8px;
  z-index: 1001;
  color: #111;
  transition: color 0.3s ease;
}

.hamburger-menu:hover {
  background: rgba(17, 17, 17, 0.05);
  border-radius: 8px;
}

.hamburger-menu.menu-open {
  color: #fff;
}

.mobile-menu {
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  background: rgba(17, 17, 17, 0.98);
  backdrop-filter: blur(10px);
  z-index: 1000;
  opacity: 0;
  visibility: hidden;
  transition: all 0.3s ease;
}

.mobile-menu.active {
  opacity: 1;
  visibility: visible;
}

.mobile-menu-content {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 100%;
  padding: 80px 20px 20px;
}

.mobile-nav-links {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 40px;
  list-style: none;
  padding: 0;
  margin: 0;
}

.mobile-nav-links a {
  text-decoration: none;
  color: #fff;
  font-size: 28px;
  font-weight: 500;
  transition: all 0.3s ease;
  text-align: center;
}

.mobile-nav-links a:hover {
  color: rgba(255, 255, 255, 0.7);
  transform: translateY(-2px);
}

.mobile-cta-button {
  background: #fff !important;
  color: #111 !important;
  padding: 16px 32px;
  border-radius: 12px;
  font-weight: 600;
  margin-top: 20px;
}

.mobile-cta-button:hover {
  background: rgba(255, 255, 255, 0.9) !important;
  color: #111 !important;
}

@media (max-width: 1024px) {
  .nav-links {
    gap: 24px;
  }
  
  .nav-links a {
    font-size: 14px;
  }
}

@media (max-width: 768px) {
  .nav-content {
    height: 70px;
  }
  
  .logo {
    font-size: 16px;
  }
  
  .desktop-nav {
    display: none;
  }
  
  .hamburger-menu {
    display: flex;
  }
}

@media (max-width: 480px) {
  .nav-content {
    height: 60px;
    padding: 0 16px;
  }
  
  .logo {
    font-size: 14px;
    gap: 8px;
  }
  
  .logo svg {
    width: 24px;
    height: 24px;
  }
  
  .mobile-nav-links a {
    font-size: 24px;
  }
  
  .mobile-nav-links {
    gap: 32px;
  }
  
  .mobile-cta-button {
    padding: 14px 28px;
    font-size: 16px;
  }
}
</style>