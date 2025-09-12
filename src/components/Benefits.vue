<template>
  <section id="benefits" class="benefits">
    <div class="container">
      <div class="section-header">
        <h2 class="section-title">社会への効果</h2>
        <p class="section-description">
          プラットフォームが生み出す循環型の価値創造
        </p>
      </div>
      <div class="benefits-flow">
        <div class="benefit-item" v-for="(benefit, index) in benefits" :key="index">
          <div class="benefit-icon" v-html="getIcon(benefit.icon)">
          </div>
          <div class="benefit-content">
            <h3 class="benefit-title">{{ benefit.title }}</h3>
            <p class="benefit-description">{{ benefit.description }}</p>
          </div>
          <div v-if="index < benefits.length - 1" class="flow-arrow">
            <svg width="24" height="24" viewBox="0 0 24 24" fill="none">
              <path d="M7 17l5-5-5-5" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>
          </div>
        </div>
      </div>
      <div class="impact-stats">
        <div class="stat-item">
          <div class="stat-number">∞</div>
          <div class="stat-label">持続可能な成長</div>
        </div>
        <div class="stat-item">
          <div class="stat-number">100%</div>
          <div class="stat-label">地域密着型</div>
        </div>
        <div class="stat-item">
          <div class="stat-number">0¥</div>
          <div class="stat-label">初期費用</div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Benefits',
  data() {
    return {
      benefits: [
        {
          title: 'スタートアップの成長',
          description: '必要な人材を獲得することで、スタートアップの事業が成長し、売上が向上します。',
          icon: 'GrowthIcon'
        },
        {
          title: '人材への報酬',
          description: '成長による売上向上で、協力してくれた人材に適正な報酬を提供できます。',
          icon: 'RewardIcon'
        },
        {
          title: '税収の増加',
          description: 'スタートアップの成長により税収が増加し、地域経済の活性化につながります。',
          icon: 'TaxIcon'
        },
        {
          title: '雇用創出',
          description: '成功した協力関係が正式な採用に発展し、新たな雇用機会を創出します。',
          icon: 'JobIcon'
        },
        {
          title: '地域の繁栄',
          description: '循環する経済活動により、北九州市が「稼げる街」として発展します。',
          icon: 'CityIcon'
        }
      ]
    }
  },
  methods: {
    getIcon(iconName) {
      const icons = {
        GrowthIcon: `<svg width="32" height="32" viewBox="0 0 24 24" fill="none">
          <path d="M3 3v18h18" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
          <path d="M18.7 8l-5.1 5.2-2.8-2.7L7 14.3" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
        </svg>`,
        RewardIcon: `<svg width="32" height="32" viewBox="0 0 24 24" fill="none">
          <circle cx="9" cy="21" r="1" stroke="currentColor" stroke-width="2"/>
          <circle cx="20" cy="21" r="1" stroke="currentColor" stroke-width="2"/>
          <path d="M1 1h4l2.68 13.39a2 2 0 0 0 2 1.61h9.72a2 2 0 0 0 2-1.61L23 6H6" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
        </svg>`,
        TaxIcon: `<svg width="32" height="32" viewBox="0 0 24 24" fill="none">
          <path d="M2 3h6a4 4 0 0 1 4 4v14a3 3 0 0 0-3-3H2z" stroke="currentColor" stroke-width="2" stroke-linejoin="round"/>
          <path d="M22 3h-6a4 4 0 0 0-4 4v14a3 3 0 0 1 3-3h7z" stroke="currentColor" stroke-width="2" stroke-linejoin="round"/>
        </svg>`,
        JobIcon: `<svg width="32" height="32" viewBox="0 0 24 24" fill="none">
          <path d="M20 21v-2a4 4 0 0 0-4-4H8a4 4 0 0 0-4 4v2" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
          <circle cx="12" cy="7" r="4" stroke="currentColor" stroke-width="2"/>
        </svg>`,
        CityIcon: `<svg width="32" height="32" viewBox="0 0 24 24" fill="none">
          <path d="M6 22V4a2 2 0 0 1 2-2h8a2 2 0 0 1 2 2v18Z" stroke="currentColor" stroke-width="2"/>
          <path d="M6 12H4a2 2 0 0 0-2 2v8h20v-8a2 2 0 0 0-2-2h-2" stroke="currentColor" stroke-width="2"/>
          <path d="M10 6h4" stroke="currentColor" stroke-width="2" stroke-linecap="round"/>
          <path d="M10 10h4" stroke="currentColor" stroke-width="2" stroke-linecap="round"/>
          <path d="M10 14h4" stroke="currentColor" stroke-width="2" stroke-linecap="round"/>
          <path d="M10 18h4" stroke="currentColor" stroke-width="2" stroke-linecap="round"/>
        </svg>`
      }
      return icons[iconName] || ''
    }
  }
}
</script>

<style scoped>
.benefits {
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

.benefits-flow {
  display: flex;
  flex-direction: column;
  gap: 40px;
  max-width: 800px;
  margin: 0 auto 80px;
}

.benefit-item {
  display: flex;
  align-items: center;
  gap: 32px;
  padding: 32px;
  background: linear-gradient(135deg, rgba(17, 17, 17, 0.02) 0%, rgba(17, 17, 17, 0.01) 100%);
  border-radius: 16px;
  border: 1px solid rgba(17, 17, 17, 0.05);
  position: relative;
  transition: all 0.3s ease;
}

.benefit-item:hover {
  transform: translateY(-4px);
  box-shadow: 0 12px 48px rgba(17, 17, 17, 0.08);
  border-color: rgba(17, 17, 17, 0.1);
}

.benefit-icon {
  flex-shrink: 0;
  width: 80px;
  height: 80px;
  background: #fff;
  border-radius: 20px;
  display: flex;
  align-items: center;
  justify-content: center;
  color: #111;
  border: 1px solid rgba(17, 17, 17, 0.08);
  transition: all 0.3s ease;
}

.benefit-item:hover .benefit-icon {
  background: #111;
  color: #fff;
  transform: scale(1.1);
}

.benefit-content {
  flex: 1;
}

.benefit-title {
  font-size: 20px;
  font-weight: 600;
  color: #111;
  margin-bottom: 8px;
}

.benefit-description {
  font-size: 15px;
  line-height: 1.6;
  color: #666;
}

.flow-arrow {
  position: absolute;
  bottom: -20px;
  left: 50%;
  transform: translateX(-50%) rotate(90deg);
  color: #111;
  opacity: 0.3;
}

.impact-stats {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 40px;
  max-width: 800px;
  margin: 0 auto;
}

.stat-item {
  text-align: center;
  padding: 32px 20px;
  background: linear-gradient(135deg, #111 0%, #333 100%);
  border-radius: 16px;
  color: #fff;
  transition: all 0.3s ease;
}

.stat-item:hover {
  transform: translateY(-8px) scale(1.05);
}

.stat-number {
  font-size: 48px;
  font-weight: 700;
  margin-bottom: 12px;
  background: linear-gradient(135deg, #fff 0%, rgba(255, 255, 255, 0.8) 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.stat-label {
  font-size: 14px;
  font-weight: 500;
  opacity: 0.9;
  text-transform: uppercase;
  letter-spacing: 0.5px;
}

@media (max-width: 768px) {
  .benefits {
    padding: 80px 0;
  }
  
  .section-title {
    font-size: 32px;
  }
  
  .section-description {
    font-size: 16px;
  }
  
  .benefit-item {
    flex-direction: column;
    text-align: center;
    gap: 20px;
    padding: 24px;
  }
  
  .flow-arrow {
    position: static;
    transform: none;
    margin: 20px 0;
  }
  
  .impact-stats {
    grid-template-columns: 1fr;
    gap: 24px;
  }
  
  .stat-number {
    font-size: 36px;
  }
}
</style>