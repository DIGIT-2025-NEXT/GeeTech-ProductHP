<template>
  <section id="features" class="features">
    <div class="container">
      <div class="section-header">
        <h2 class="section-title">プラットフォームの特徴</h2>
        <p class="section-description">
          革新的なマッチングシステムで、新しい働き方を実現
        </p>
      </div>
      <div class="features-grid">
        <div class="feature-card" v-for="(feature, index) in features" :key="index">
          <div class="feature-icon" v-html="getIcon(feature.icon)">
          </div>
          <h3 class="feature-title">{{ feature.title }}</h3>
          <p class="feature-description">{{ feature.description }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Features',
  data() {
    return {
      features: [
        {
          title: '無料掲載',
          description: 'スタートアップは無料でプロジェクトを掲載でき、必要な人材を効率的に見つけることができます。',
          icon: 'FreeIcon'
        },
        {
          title: '柔軟な報酬体系',
          description: '無償から有償まで、プロジェクトに応じた柔軟な報酬設定が可能です。',
          icon: 'FlexibleIcon'
        },
        {
          title: '地域密着',
          description: '地元で働きたい人材と地域のスタートアップをマッチング。移動コストを削減します。',
          icon: 'LocalIcon'
        },
        {
          title: '成長機会',
          description: '学生や経験を積みたい人材に、実践的なスキルアップの機会を提供します。',
          icon: 'GrowthIcon'
        }
      ]
    }
  },
  methods: {
    getIcon(iconName) {
      const icons = {
        FreeIcon: `<svg width="32" height="32" viewBox="0 0 24 24" fill="none">
          <path d="M12 2L2 7v10c0 5.55 3.84 9.74 9 11 5.16-1.26 9-5.45 9-11V7l-10-5z" stroke="currentColor" stroke-width="2" stroke-linejoin="round"/>
          <path d="M9 12l2 2 4-4" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
        </svg>`,
        FlexibleIcon: `<svg width="32" height="32" viewBox="0 0 24 24" fill="none">
          <path d="M12 2v6m0 4v10" stroke="currentColor" stroke-width="2" stroke-linecap="round"/>
          <path d="M17 7a5 5 0 0 0-5-5 5 5 0 0 0-5 5 5 5 0 0 0 5 5 5 5 0 0 0 5-5z" stroke="currentColor" stroke-width="2"/>
          <path d="M17 17a5 5 0 0 0-5-5 5 5 0 0 0-5 5 5 5 0 0 0 5 5 5 5 0 0 0 5-5z" stroke="currentColor" stroke-width="2"/>
        </svg>`,
        LocalIcon: `<svg width="32" height="32" viewBox="0 0 24 24" fill="none">
          <path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0 1 18 0z" stroke="currentColor" stroke-width="2"/>
          <circle cx="12" cy="10" r="3" stroke="currentColor" stroke-width="2"/>
        </svg>`,
        GrowthIcon: `<svg width="32" height="32" viewBox="0 0 24 24" fill="none">
          <path d="M3 3v18h18" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
          <path d="M18.7 8l-5.1 5.2-2.8-2.7L7 14.3" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
        </svg>`
      }
      return icons[iconName] || ''
    }
  }
}
</script>

<style scoped>
.features {
  padding: 120px 0;
  background: #fff;
}

.section-header {
  text-align: center;
  margin-bottom: 80px;
}

.section-title {
  font-size: 40px;
  font-weight: 700;
  color: #111;
  margin-bottom: 16px;
}

.section-description {
  font-size: 18px;
  color: #666;
  max-width: 600px;
  margin: 0 auto;
}

.features-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 32px;
  max-width: 1200px;
  margin: 0 auto;
}

.feature-card {
  text-align: center;
  padding: 32px 20px;
  border-radius: 16px;
  background: #fff;
  border: 1px solid rgba(17, 17, 17, 0.08);
  transition: all 0.3s ease;
  position: relative;
  overflow: hidden;
}

.feature-card::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: linear-gradient(135deg, rgba(17, 17, 17, 0.02) 0%, transparent 100%);
  opacity: 0;
  transition: opacity 0.3s ease;
}

.feature-card:hover {
  transform: translateY(-8px);
  box-shadow: 0 16px 64px rgba(17, 17, 17, 0.15);
  border-color: rgba(17, 17, 17, 0.12);
}

.feature-card:hover::before {
  opacity: 1;
}

.feature-icon {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 80px;
  height: 80px;
  background: rgba(17, 17, 17, 0.05);
  border-radius: 20px;
  margin-bottom: 24px;
  color: #111;
  transition: all 0.3s ease;
}

.feature-card:hover .feature-icon {
  background: #111;
  color: #fff;
  transform: scale(1.1);
}

.feature-title {
  font-size: 20px;
  font-weight: 600;
  color: #111;
  margin-bottom: 16px;
}

.feature-description {
  font-size: 15px;
  line-height: 1.6;
  color: #666;
}

@media (max-width: 1024px) {
  .features-grid {
    grid-template-columns: repeat(2, 1fr);
    gap: 32px;
  }
}

@media (max-width: 768px) {
  .features {
    padding: 80px 0;
  }
  
  .section-title {
    font-size: 32px;
  }
  
  .section-description {
    font-size: 16px;
  }
  
  .features-grid {
    grid-template-columns: 1fr;
    gap: 24px;
  }
  
  .feature-card {
    padding: 32px 20px;
  }
  
  .feature-icon {
    width: 70px;
    height: 70px;
  }
}

@media (max-width: 480px) {
  .features {
    padding: 60px 0;
  }
  
  .section-header {
    margin-bottom: 60px;
  }
  
  .section-title {
    font-size: 28px;
  }
  
  .section-description {
    font-size: 15px;
  }
  
  .feature-card {
    padding: 24px 16px;
  }
  
  .feature-icon {
    width: 60px;
    height: 60px;
  }
  
  .feature-title {
    font-size: 18px;
  }
  
  .feature-description {
    font-size: 14px;
  }
}
</style>