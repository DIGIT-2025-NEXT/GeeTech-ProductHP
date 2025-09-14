<template>
  <section id="contact" class="cta">
    <div class="container">
      <div class="cta-content">
        <div class="cta-text">
          <h2 class="cta-title">新しい働き方を始めませんか？</h2>
          <p class="cta-description">
            スタートアップと人材をつなぐプラットフォームで、　<br>
            共に成長し、地域を活性化させましょう。
          </p>
          <div class="cta-buttons">
            <a href="https://geetech.dokkiitech.dev/register" target="_blank" rel="noopener noreferrer" class="primary-button">
              <svg width="20" height="20" viewBox="0 0 24 24" fill="none">
                <path d="M16 4h2a2 2 0 0 1 2 2v14a2 2 0 0 1-2 2H6a2 2 0 0 1-2-2V6a2 2 0 0 1 2-2h2" stroke="currentColor" stroke-width="2"/>
                <rect x="8" y="2" width="8" height="4" rx="1" ry="1" stroke="currentColor" stroke-width="2"/>
              </svg>
              スタートアップとして参加
            </a>
            <a href="https://geetech.dokkiitech.dev/login" target="_blank" rel="noopener noreferrer" class="secondary-button">
              <svg width="20" height="20" viewBox="0 0 24 24" fill="none">
                <path d="M20 21v-2a4 4 0 0 0-4-4H8a4 4 0 0 0-4 4v2" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                <circle cx="12" cy="7" r="4" stroke="currentColor" stroke-width="2"/>
              </svg>
              人材として参加
            </a>
          </div>
        </div>
        <div class="cta-visual">
          <div class="visual-container">
            <div class="orbit">
              <div class="center-node">
                <svg width="32" height="32" viewBox="0 0 24 24" fill="none">
                  <path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0 1 18 0z" stroke="currentColor" stroke-width="2"/>
                  <circle cx="12" cy="10" r="3" stroke="currentColor" stroke-width="2"/>
                </svg>
              </div>
              <div class="orbit-node startup-node">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none">
                  <path d="M12 2L2 7l10 5 10-5-10-5z" stroke="currentColor" stroke-width="2" stroke-linejoin="round"/>
                </svg>
              </div>
              <div class="orbit-node talent-node">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none">
                  <path d="M20 21v-2a4 4 0 0 0-4-4H8a4 4 0 0 0-4 4v2" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                  <circle cx="12" cy="7" r="4" stroke="currentColor" stroke-width="2"/>
                </svg>
              </div>
              <div class="orbit-node growth-node">
                <svg width="24" height="24" viewBox="0 0 24 24" fill="none">
                  <path d="M3 3v18h18" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                  <path d="M18.7 8l-5.1 5.2-2.8-2.7L7 14.3" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                </svg>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <footer class="footer">
      <div class="container">
        <div class="footer-content">
          <div class="footer-logo">
            <span>kitaq_startup</span>
          </div>
          <div class="footer-text">
            <p>&copy; 2025 DIGITKITAQ | GeeTech</p>
          </div>
        </div>
      </div>
    </footer>
  </section>
</template>

<script>
export default {
  name: 'CallToAction',
  mounted() {
    this.animateOrbit()
  },
  methods: {
    animateOrbit() {
      const orbit = this.$el.querySelector('.orbit')
      if (orbit) {
        orbit.style.animation = 'rotate 20s linear infinite'
      }
    }
  }
}
</script>

<style scoped>
.cta {
  padding: 120px 0 0;
  background: linear-gradient(135deg, #111 0%, #333 100%);
  color: #fff;
}

.cta-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 80px;
  align-items: center;
  margin-bottom: 80px;
}

.cta-title {
  font-size: 36px;
  font-weight: 700;
  line-height: 1.2;
  margin-bottom: 24px;
  animation: slideInLeft 1s ease-out;
}

.cta-description {
  font-size: 18px;
  line-height: 1.6;
  opacity: 0.9;
  margin-bottom: 40px;
  animation: slideInLeft 1s ease-out 0.2s both;
}

.cta-buttons {
  display: flex;
  flex-direction: column;
  gap: 16px;
  animation: slideInLeft 1s ease-out 0.4s both;
}

.primary-button,
.secondary-button {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 12px;
  padding: 16px 32px;
  border-radius: 12px;
  font-size: 16px;
  font-weight: 500;
  cursor: pointer;
  transition: all 0.3s ease;
  border: none;
  max-width: 300px;
}

.primary-button {
  background: #fff;
  color: #111;
}

.primary-button:hover {
  background: rgba(255, 255, 255, 0.9);
  transform: translateY(-2px);
}

.secondary-button {
  background: transparent;
  color: #fff;
  border: 2px solid #fff;
}

.secondary-button:hover {
  background: #fff;
  color: #111;
  transform: translateY(-2px);
}

.cta-visual {
  display: flex;
  justify-content: center;
  align-items: center;
  animation: slideInRight 1s ease-out 0.6s both;
}

.visual-container {
  position: relative;
  width: 300px;
  height: 300px;
}

.orbit {
  position: relative;
  width: 100%;
  height: 100%;
  border: 1px solid rgba(255, 255, 255, 0.2);
  border-radius: 50%;
}

@keyframes rotate {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}

.center-node {
  position: absolute;
  top: 50%;
  left: 50%;
  width: 60px;
  height: 60px;
  background: rgba(255, 255, 255, 0.1);
  border: 2px solid rgba(255, 255, 255, 0.3);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  transform: translate(-50%, -50%);
  color: #fff;
}

.orbit-node {
  position: absolute;
  width: 48px;
  height: 48px;
  background: rgba(255, 255, 255, 0.05);
  border: 1px solid rgba(255, 255, 255, 0.2);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  color: #fff;
}

.startup-node {
  top: 20px;
  left: 50%;
  transform: translateX(-50%);
  animation: float 3s ease-in-out infinite;
}

.talent-node {
  bottom: 20px;
  left: 50%;
  transform: translateX(-50%);
  animation: float 3s ease-in-out infinite 1s;
}

.growth-node {
  top: 50%;
  right: 20px;
  transform: translateY(-50%);
  animation: float 3s ease-in-out infinite 2s;
}

.footer {
  background: rgba(0, 0, 0, 0.3);
  border-top: 1px solid rgba(255, 255, 255, 0.1);
  padding: 40px 0;
}

.footer-content {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 20px;
  text-align: center;
}

.footer-logo {
  display: flex;
  align-items: center;
  gap: 12px;
  font-family: var(--audiowide);
  font-weight: 400;
  font-size: 18px;
  letter-spacing: 0.5px;
}

.footer-text {
  opacity: 0.7;
  font-size: 14px;
}

@media (max-width: 1024px) {
  .cta-content {
    grid-template-columns: 1fr;
    gap: 60px;
    text-align: center;
  }
  
  .cta-title {
    font-size: 36px;
  }
  
  .cta-description {
    font-size: 16px;
  }
}

@media (max-width: 768px) {
  .cta {
    padding: 80px 0 0;
  }
  
  .cta-title {
    font-size: 28px;
  }
  
  .cta-description {
    font-size: 16px;
  }
  
  .cta-buttons {
    align-items: center;
  }
  
  .primary-button,
  .secondary-button {
    width: 100%;
    max-width: none;
  }
  
  .visual-container {
    width: 250px;
    height: 250px;
  }
}

@media (max-width: 480px) {
  .cta {
    padding: 60px 0 0;
  }
  
  .cta-content {
    gap: 50px;
  }
  
  .cta-title {
    font-size: 24px;
  }
  
  .cta-description {
    font-size: 15px;
    margin-bottom: 32px;
  }
  
  .primary-button,
  .secondary-button {
    padding: 14px 24px;
    font-size: 15px;
  }
  
  .visual-container {
    width: 200px;
    height: 200px;
  }
  
  .orbit-node {
    width: 40px;
    height: 40px;
  }
  
  .center-node {
    width: 50px;
    height: 50px;
  }
}
</style>