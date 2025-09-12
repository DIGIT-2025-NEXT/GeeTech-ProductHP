<template>
  <section class="hero">
    <div class="container">
      <div class="hero-content">
        <div class="hero-text">
          <h1 class="hero-title">
            スタートアップと<br>
            人材をつなぐ<br>
            プラットフォーム
          </h1>
          <p class="hero-description">
            資金がなくても成長したい企業と、経験を積みたい人材をマッチング。
            新しい働き方で、共に未来を築きませんか？
          </p>
          <div class="hero-buttons">
            <a href="https://geetech.dokkiitech.dev/" target="_blank" rel="noopener noreferrer" class="primary-button">
              <svg width="20" height="20" viewBox="0 0 24 24" fill="none">
                <path d="M13 7l5 5-5 5M6 12h12" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
              </svg>
              今すぐ始める
            </a>
            <a href="#features" class="secondary-button">
              <svg width="20" height="20" viewBox="0 0 24 24" fill="none">
                <circle cx="12" cy="12" r="10" stroke="currentColor" stroke-width="2"/>
                <polygon points="10,8 16,12 10,16" fill="currentColor"/>
              </svg>
              詳しく見る
            </a>
          </div>
        </div>
        <div class="hero-visual">
          <div class="floating-cards">
            <div class="card startup-card">
              <svg width="24" height="24" viewBox="0 0 24 24" fill="none">
                <path d="M12 2L2 7l10 5 10-5-10-5z" stroke="currentColor" stroke-width="2" stroke-linejoin="round"/>
                <path d="M2 17l10 5 10-5" stroke="currentColor" stroke-width="2" stroke-linejoin="round"/>
                <path d="M2 12l10 5 10-5" stroke="currentColor" stroke-width="2" stroke-linejoin="round"/>
              </svg>
              <span>スタートアップ</span>
            </div>
            <div class="connection-line"></div>
            <div class="card talent-card">
              <svg width="24" height="24" viewBox="0 0 24 24" fill="none">
                <path d="M20 21v-2a4 4 0 0 0-4-4H8a4 4 0 0 0-4 4v2" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                <circle cx="12" cy="7" r="4" stroke="currentColor" stroke-width="2"/>
              </svg>
              <span>人材</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Hero'
}
</script>

<style scoped>
.hero {
  padding: 160px 0 120px;
  background: linear-gradient(135deg, #f8f9fa 0%, #fff 100%);
  overflow: hidden;
  position: relative;
}

.hero::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-image: 
    radial-gradient(circle at 25% 25%, rgba(17, 17, 17, 0.02) 0%, transparent 50%),
    radial-gradient(circle at 75% 75%, rgba(17, 17, 17, 0.02) 0%, transparent 50%);
}

.hero-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 80px;
  align-items: center;
  position: relative;
  z-index: 1;
}

.hero-title {
  font-size: 56px;
  font-weight: 700;
  line-height: 1.2;
  color: #111;
  margin-bottom: 24px;
  animation: slideInLeft 1s ease-out;
}

.hero-description {
  font-size: 20px;
  line-height: 1.6;
  color: #666;
  margin-bottom: 40px;
  animation: slideInLeft 1s ease-out 0.2s both;
}

.hero-buttons {
  display: flex;
  gap: 16px;
  animation: slideInLeft 1s ease-out 0.4s both;
}

.primary-button {
  display: flex;
  align-items: center;
  gap: 8px;
  background: #111;
  color: #fff;
  border: none;
  padding: 16px 32px;
  border-radius: 12px;
  font-size: 16px;
  font-weight: 500;
  cursor: pointer;
  transition: all 0.3s ease;
}

.primary-button:hover {
  background: #333;
  transform: translateY(-2px);
}

.secondary-button {
  display: flex;
  align-items: center;
  gap: 8px;
  background: transparent;
  color: #111;
  border: 2px solid #111;
  padding: 14px 30px;
  border-radius: 12px;
  font-size: 16px;
  font-weight: 500;
  cursor: pointer;
  transition: all 0.3s ease;
}

.secondary-button:hover {
  background: #111;
  color: #fff;
  transform: translateY(-2px);
}

.hero-visual {
  display: flex;
  justify-content: center;
  align-items: center;
  animation: slideInRight 1s ease-out 0.6s both;
}

.floating-cards {
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 80px;
}

.card {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 12px;
  background: #fff;
  padding: 32px;
  border-radius: 16px;
  box-shadow: 0 8px 32px rgba(17, 17, 17, 0.1);
  border: 1px solid rgba(17, 17, 17, 0.05);
  font-weight: 500;
  color: #111;
  min-width: 160px;
  animation: float 4s ease-in-out infinite;
}

.startup-card {
  animation-delay: 0s;
}

.talent-card {
  animation-delay: 2s;
}

.connection-line {
  position: absolute;
  top: 50%;
  left: 50%;
  width: 2px;
  height: 60px;
  background: linear-gradient(to bottom, #111, transparent);
  transform: translate(-50%, -50%);
  opacity: 0.3;
}

.connection-line::after {
  content: '';
  position: absolute;
  bottom: -4px;
  left: -2px;
  width: 0;
  height: 0;
  border-left: 3px solid transparent;
  border-right: 3px solid transparent;
  border-top: 8px solid #111;
  opacity: 0.6;
}

@media (max-width: 1024px) {
  .hero-content {
    grid-template-columns: 1fr;
    gap: 60px;
    text-align: center;
  }
  
  .hero-title {
    font-size: 48px;
  }
  
  .hero-description {
    font-size: 18px;
  }
}

@media (max-width: 768px) {
  .hero {
    padding: 120px 0 80px;
  }
  
  .hero-title {
    font-size: 32px;
  }
  
  .hero-description {
    font-size: 16px;
  }
  
  .hero-buttons {
    flex-direction: column;
    align-items: center;
  }
  
  .primary-button,
  .secondary-button {
    width: 100%;
    max-width: 300px;
    justify-content: center;
  }
  
  .visual-container {
    width: 280px;
    height: 280px;
  }
}

@media (max-width: 480px) {
  .hero {
    padding: 100px 0 60px;
  }
  
  .hero-title {
    font-size: 28px;
    line-height: 1.1;
  }
  
  .hero-description {
    font-size: 15px;
  }
  
  .primary-button,
  .secondary-button {
    padding: 14px 28px;
    font-size: 15px;
  }
  
  .visual-container {
    width: 240px;
    height: 240px;
  }
  
  .card {
    padding: 24px;
    min-width: 120px;
  }
}
</style>