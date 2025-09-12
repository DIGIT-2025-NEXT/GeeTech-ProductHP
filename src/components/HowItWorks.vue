<template>
  <section id="how-it-works" class="how-it-works">
    <div class="container">
      <div class="section-header">
        <h2 class="section-title">仕組み</h2>
        <p class="section-description">
          シンプルな3ステップで、理想のマッチングを実現
        </p>
      </div>
      <div class="steps">
        <div class="step" v-for="(step, index) in steps" :key="index">
          <div class="step-number">{{ index + 1 }}</div>
          <div class="step-content">
            <div class="step-icon" v-html="getIcon(step.icon)">
            </div>
            <h3 class="step-title">{{ step.title }}</h3>
            <p class="step-description">{{ step.description }}</p>
          </div>
          <div v-if="index < steps.length - 1" class="step-connector"></div>
        </div>
      </div>
      <div class="user-types">
        <div class="user-type">
          <h3 class="user-type-title">スタートアップ向け</h3>
          <ul class="user-type-list">
            <li>プロジェクトの無料掲載</li>
            <li>人材のスキルマッチング</li>
            <li>柔軟な契約形態</li>
            <li>成果に応じた報酬設定</li>
          </ul>
        </div>
        <div class="user-type">
          <h3 class="user-type-title">人材向け</h3>
          <ul class="user-type-list">
            <li>実践的な経験獲得</li>
            <li>地元での働く機会</li>
            <li>スキルアップの場</li>
            <li>将来的な採用への道筋</li>
          </ul>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'HowItWorks',
  data() {
    return {
      steps: [
        {
          title: 'プロジェクト掲載',
          description: 'スタートアップが必要な人材やプロジェクトを掲載します。詳細な要件と条件を明記できます。',
          icon: 'PostIcon'
        },
        {
          title: 'マッチング',
          description: '興味のある人材がプロジェクトに応募。スキルと要件を照合して最適なマッチングを行います。',
          icon: 'MatchIcon'
        },
        {
          title: 'プロジェクト開始',
          description: '合意が成立したらプロジェクトを開始。成果に応じて報酬が支払われます。',
          icon: 'StartIcon'
        }
      ]
    }
  },
  methods: {
    getIcon(iconName) {
      const icons = {
        PostIcon: `<svg width="24" height="24" viewBox="0 0 24 24" fill="none">
          <path d="M14.5 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V7.5L14.5 2z" stroke="currentColor" stroke-width="2" stroke-linejoin="round"/>
          <polyline points="14,2 14,8 20,8" stroke="currentColor" stroke-width="2" stroke-linejoin="round"/>
          <line x1="16" y1="13" x2="8" y2="13" stroke="currentColor" stroke-width="2" stroke-linecap="round"/>
          <line x1="16" y1="17" x2="8" y2="17" stroke="currentColor" stroke-width="2" stroke-linecap="round"/>
        </svg>`,
        MatchIcon: `<svg width="24" height="24" viewBox="0 0 24 24" fill="none">
          <path d="M16 4h2a2 2 0 0 1 2 2v14a2 2 0 0 1-2 2H6a2 2 0 0 1-2-2V6a2 2 0 0 1 2-2h2" stroke="currentColor" stroke-width="2"/>
          <rect x="8" y="2" width="8" height="4" rx="1" ry="1" stroke="currentColor" stroke-width="2"/>
          <path d="M9 14l2 2 4-4" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
        </svg>`,
        StartIcon: `<svg width="24" height="24" viewBox="0 0 24 24" fill="none">
          <circle cx="12" cy="12" r="10" stroke="currentColor" stroke-width="2"/>
          <polygon points="10,8 16,12 10,16" fill="currentColor"/>
        </svg>`
      }
      return icons[iconName] || ''
    }
  }
}
</script>

<style scoped>
.how-it-works {
  padding: 120px 0;
  background: linear-gradient(135deg, #f8f9fa 0%, #fff 100%);
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

.steps {
  display: flex;
  justify-content: center;
  align-items: flex-start;
  gap: 60px;
  margin-bottom: 100px;
  position: relative;
}

.step {
  display: flex;
  flex-direction: column;
  align-items: center;
  max-width: 300px;
  position: relative;
}

.step-number {
  width: 40px;
  height: 40px;
  background: #111;
  color: #fff;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-weight: 600;
  font-size: 18px;
  margin-bottom: 24px;
  z-index: 2;
  position: relative;
}

.step-content {
  text-align: center;
}

.step-icon {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 60px;
  height: 60px;
  background: rgba(17, 17, 17, 0.05);
  border-radius: 16px;
  margin-bottom: 20px;
  color: #111;
  transition: all 0.3s ease;
}

.step:hover .step-icon {
  background: rgba(17, 17, 17, 0.1);
  transform: scale(1.1);
}

.step-title {
  font-size: 20px;
  font-weight: 600;
  color: #111;
  margin-bottom: 12px;
}

.step-description {
  font-size: 15px;
  line-height: 1.6;
  color: #666;
}

.step-connector {
  position: absolute;
  top: 20px;
  left: calc(100% + 10px);
  width: 40px;
  height: 2px;
  background: linear-gradient(to right, #111, rgba(17, 17, 17, 0.3));
  z-index: 1;
}

.step-connector::after {
  content: '';
  position: absolute;
  right: -4px;
  top: -2px;
  width: 0;
  height: 0;
  border-top: 3px solid transparent;
  border-bottom: 3px solid transparent;
  border-left: 6px solid rgba(17, 17, 17, 0.6);
}

.user-types {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
  gap: 60px;
  max-width: 1000px;
  margin: 0 auto;
}

.user-type {
  background: #fff;
  padding: 40px;
  border-radius: 16px;
  border: 1px solid rgba(17, 17, 17, 0.08);
  transition: all 0.3s ease;
}

.user-type:hover {
  transform: translateY(-4px);
  box-shadow: 0 12px 48px rgba(17, 17, 17, 0.1);
}

.user-type-title {
  font-size: 24px;
  font-weight: 600;
  color: #111;
  margin-bottom: 24px;
  text-align: center;
}

.user-type-list {
  list-style: none;
  padding: 0;
}

.user-type-list li {
  padding: 12px 0;
  color: #666;
  font-size: 15px;
  display: flex;
  align-items: center;
  gap: 12px;
}

.user-type-list li::before {
  content: '';
  width: 6px;
  height: 6px;
  background: #111;
  border-radius: 50%;
  flex-shrink: 0;
}

@media (max-width: 1024px) {
  .steps {
    flex-direction: column;
    align-items: center;
    gap: 40px;
  }
  
  .step-connector {
    display: none;
  }
  
  .user-types {
    grid-template-columns: 1fr;
    gap: 40px;
  }
}

@media (max-width: 768px) {
  .how-it-works {
    padding: 80px 0;
  }
  
  .section-title {
    font-size: 32px;
  }
  
  .section-description {
    font-size: 16px;
  }
  
  .steps {
    margin-bottom: 80px;
  }
  
  .step-icon {
    width: 50px;
    height: 50px;
  }
  
  .step-title {
    font-size: 18px;
  }
  
  .step-description {
    font-size: 14px;
  }
  
  .user-types {
    grid-template-columns: 1fr;
    max-width: none;
  }
  
  .user-type {
    padding: 32px 24px;
  }
  
  .user-type-title {
    font-size: 20px;
  }
}

@media (max-width: 480px) {
  .how-it-works {
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
  
  .steps {
    gap: 32px;
    margin-bottom: 60px;
  }
  
  .step-number {
    width: 32px;
    height: 32px;
    font-size: 16px;
    margin-bottom: 20px;
  }
  
  .step-icon {
    width: 44px;
    height: 44px;
  }
  
  .step-title {
    font-size: 17px;
  }
  
  .step-description {
    font-size: 13px;
  }
  
  .user-types {
    gap: 32px;
  }
  
  .user-type {
    padding: 24px 20px;
  }
  
  .user-type-title {
    font-size: 18px;
    margin-bottom: 20px;
  }
  
  .user-type-list li {
    font-size: 14px;
    padding: 10px 0;
  }
}
</style>