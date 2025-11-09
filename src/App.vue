<script setup>
import { ref } from 'vue'

const baseUrl = import.meta.env.BASE_URL || '/'
const currentPage = ref('home')
const teamMembers = ref([
  { studentId: 'B01812623', name: 'Zhao Yifan' },
  { studentId: 'B01812563', name: 'Dou Wei' },
  { studentId: 'B01819825', name: 'Du Heng' },
  { studentId: 'B01820340', name: 'Wang Jianing' }
])

const advantages = ref([
  {
    title: 'What are AI-powered IDEs',
    description: 'Understanding how AI revolutionizes development tools.',
    icon: '🤖',
    color: 'linear-gradient(135deg, rgba(102,126,234,0.15), rgba(118,75,162,0.15))',
    sections: [
      {
        type: 'comparison',
        title: 'Traditional Editors vs AI Editors',
        leftTitle: 'Traditional Editors',
        rightTitle: 'AI-powered Editors',
        left: [
          'Manual typing, limited autocomplete',
          'Static linting, late bug discovery',
          'Refactoring requires manual effort',
          'Doc writing/testing is time-consuming'
        ],
        right: [
          'Context-aware intelligent completion',
          'Real-time error detection and hints',
          'Automated refactor suggestions',
          'Generate docs and tests automatically'
        ]
      },
      {
        type: 'list',
        title: 'Mainstream AI Tools',
        items: ['GitHub Copilot', 'ChatGPT', 'Tabnine', 'Codeium', 'Amazon CodeWhisperer']
      },
      {
        type: 'chart',
        title: 'Market Adoption Trends',
        data: [
          { label: '2019', value: 5 },
          { label: '2021', value: 18 },
          { label: '2023', value: 45 },
          { label: '2024', value: 62 }
        ]
      }
    ]
  },
  {
    title: 'Core AI Features',
    description: 'Exploring five fundamental AI capabilities.',
    icon: '⚡',
    color: 'linear-gradient(135deg, rgba(102,126,234,0.15), rgba(118,75,162,0.15))',
    sections: [
      {
        type: 'comparison',
        title: 'Intelligent Code Completion',
        leftTitle: 'Traditional',
        rightTitle: 'AI-assisted',
        left: ['Keyword-based suggestions', 'Limited understanding of context'],
        right: ['Semantic/context-aware suggestions', 'Learns project patterns']
      },
      {
        type: 'code_before_after',
        title: 'Intelligent Refactoring',
        before: `function process(items){\n  for(let i=0;i<items.length;i++){\n    if(items[i]!==null && items[i]!==undefined){\n      console.log(items[i]);\n    }\n  }\n}`,
        after: `function process(items){\n  items.filter(Boolean).forEach(console.log);\n}`
      },
      {
        type: 'table',
        title: 'Intelligent Bug Detection',
        columns: ['Issue Type', 'Detected Error', 'AI Solution'],
        rows: [
          ['Null Pointer', 'Accessing property of undefined', 'Add optional chaining / null checks'],
          ['Race Condition', 'State updated out of order', 'Use locks or atomic updates'],
          ['Memory Leak', 'Unreleased listeners/intervals', 'Dispose resources in cleanup hooks'],
          ['Off-by-one', 'Loop boundary incorrect', 'Adjust indices and add tests']
        ]
      }
    ]
  },
  {
    title: 'Real-world Applications',
    description: 'Practical use cases and comparisons.',
    icon: '🌍',
    color: 'linear-gradient(135deg, rgba(102,126,234,0.15), rgba(118,75,162,0.15))',
    sections: [
      { type: 'list', title: 'Automated Code Review', items: ['Detect anti-patterns', 'Suggest improvements', 'Style & security checks'] },
      { type: 'list', title: 'Auto Testing & Documentation', items: ['Generate unit tests', 'Create API docs from code', 'Keep docs in sync'] }
    ]
  },
  {
    title: 'Future & Best Practices',
    description: 'Trends and best practices.',
    icon: '🚀',
    color: 'linear-gradient(135deg, rgba(102,126,234,0.15), rgba(118,75,162,0.15))',
    sections: [
      { type: 'list', title: 'Future Trends', items: ['Deeper IDE-AI integration', 'Agentic workflows', 'Privacy-preserving local models'] },
      { type: 'list', title: 'Best Practices', items: ['Human-in-the-loop review', 'Secure prompt management', 'Version tests with changes'] }
    ]
  }
])

const cursorTutorial = ref([
  {
    step: 1,
    title: 'Getting Started with Cursor',
    description: 'Learn the basics of setting up and navigating Cursor AI editor.',
    icon: '🚀',
    color: 'linear-gradient(135deg, rgba(102,126,234,0.15), rgba(118,75,162,0.15))',
    image: 'cursor-tutorial-step1-setup.png',
    sections: [
      {
        type: 'list',
        title: 'Installation & Setup',
        items: [
          'Download Cursor from cursor.com',
          'Install Cursor for your PC or Mac',
          'Sign in with your Email or Github/Google/Apple account',
          'Choose your preferred theme and settings',
          'Install recommended extensions for your stack'
        ]
      },
      {
        type: 'tips',
        title: 'Pro Tips',
        items: [
          'Enable auto-save for seamless editing',
          'Configure keyboard shortcuts for efficiency',
          'Set up your preferred AI model in settings',
          'Use Git to manage code versions',
          'Configure global rules and project rules for Cursor'
        ]
      }
    ]
  },
  {
    step: 2,
    title: 'AI-Powered Code Completion',
    description: 'Master intelligent code suggestions and auto-completion features.',
    icon: '✨',
    color: 'linear-gradient(135deg, rgba(102,126,234,0.15), rgba(118,75,162,0.15))',
    image: 'cursor-tutorial-step2-completion.png',
    sections: [
      {
        type: 'comparison',
        title: 'Traditional vs AI Completion',
        leftTitle: 'Traditional IDE',
        rightTitle: 'Cursor AI',
        left: [
          'Keyword-based suggestions',
          'Static template completion',
          'Limited context awareness',
          'Manual trigger required'
        ],
        right: [
          'Context-aware intelligent suggestions',
          'Predicts entire functions',
          'Understands project structure',
          'Real-time continuous assistance'
        ]
      },
      {
        type: 'code_example',
        title: 'Code Completion Demo',
        code: `// Start typing and watch Cursor suggest:\nfunction calculateTotal(items) {\n  // Cursor suggests the full function implementation\n  return items.reduce((total, item) => total + item.price, 0);\n}\n\n// Press Tab to accept suggestions\n// Use Ctrl+→ for partial acceptance`
      }
    ]
  },
  {
    step: 3,
    title: 'Chat with Your Code',
    description: 'Use Cursor\'s AI chat to ask questions and get help with your codebase.',
    icon: '💬',
    color: 'linear-gradient(135deg, rgba(102,126,234,0.15), rgba(118,75,162,0.15))',
    image: 'cursor-tutorial-step3-chat.png',
    sections: [
      {
        type: 'code_example',
        title: 'Starting a Chat',
        code: `// Use Cmd/Ctrl+L to open chat\n// Ask questions like:\n// "How does this function work?"\n// "What are the potential bugs here?"\n// "How can I optimize this code?"\n// "Generate unit tests for this component"`
      },
      {
        type: 'list',
        title: 'Chat Capabilities',
        items: [
          'Ask questions about any part of your code',
          'Get explanations for complex functions',
          'Request code refactoring suggestions',
          'Generate documentation and comments',
          'Get help with debugging issues'
        ]
      },
      {
        type: 'code_before_after',
        title: 'Code Optimization Example',
        before: `function processUsers(users) {\n  const activeUsers = [];\n  for (let i = 0; i < users.length; i++) {\n    if (users[i].isActive) {\n      activeUsers.push(users[i]);\n    }\n  }\n  \n  const userNames = [];\n  for (let i = 0; i < activeUsers.length; i++) {\n    userNames.push(activeUsers[i].name);\n  }\n  \n  return userNames;\n}`,
        after: `function processUsers(users) {\n  return users\n    .filter(user => user.isActive)\n    .map(user => user.name);\n}`
      },
      {
        type: 'tips',
        title: 'Effective Prompting',
        items: [
          'Be specific about what you want to achieve',
          'Include context about your project structure',
          'Ask follow-up questions for clarification',
          'Use code snippets in your questions'
        ]
      }
    ]
  },
  {
    step: 4,
    title: 'AI Code Generation',
    description: 'Generate new code, functions, and entire features using natural language.',
    icon: '🛠️',
    color: 'linear-gradient(135deg, rgba(102,126,234,0.15), rgba(118,75,162,0.15))',
    image: 'cursor-tutorial-step4-generation.png',
    sections: [
      {
        type: 'code_example',
        title: 'Generating Code from Description',
        code: `// Prompt: "Create a React hook for debounced search"\n\nimport { useState, useEffect } from 'react';\n\nexport const useDebounce = (value, delay) => {\n  const [debouncedValue, setDebouncedValue] = useState(value);\n\n  useEffect(() => {\n    const handler = setTimeout(() => {\n      setDebouncedValue(value);\n    }, delay);\n\n    return () => {\n      clearTimeout(handler);\n    };\n  }, [value, delay]);\n\n  return debouncedValue;\n};`
      },
      {
        type: 'list',
        title: 'What You Can Generate',
        items: [
          'Complete project and config files',
          'Complete functions and methods',
          'React\Vue components and hooks',
          'API endpoints and routes',
          'Database schemas and queries',
          'Unit tests and documentation'
        ]
      },
      {
        type: 'tips',
        title: 'Better Results',
        items: [
          'Provide clear requirements and constraints',
          'Include examples of expected input/output',
          'Specify coding standards and patterns',
          'Iterate and refine generated code',
          'Review and test generated code thoroughly',
          'Combine generation with chat for best results'
        ]
      }
    ]
  }
])

const navigateTo = (page) => {
  currentPage.value = page
}
</script>

<template>
  <div class="app">
    <!-- Navigation -->
    <nav class="navbar">
      <div class="nav-container">
        <div class="nav-logo">
          <span class="logo-icon">🤖</span>
          <span class="logo-text">AI IDE</span>
        </div>
        <div class="nav-links">
          <button 
            @click="navigateTo('home')" 
            :class="['nav-btn', { active: currentPage === 'home' }]"
          >
            Home
          </button>
          <button 
            @click="navigateTo('advantages')" 
            :class="['nav-btn', { active: currentPage === 'advantages' }]"
          >
            Presentation
          </button>
          <button 
            @click="navigateTo('cursor-tutorial')" 
            :class="['nav-btn', { active: currentPage === 'cursor-tutorial' }]"
          >
            Cursor Tutorial
          </button>
        </div>
      </div>
    </nav>

    <!-- Home Page -->
    <div v-if="currentPage === 'home'" class="home-page">
      <!-- Hero Section -->
      <section class="hero">
        <div class="hero-content">
          <h1 class="hero-title">
            AI-Powered IDE & Code Editors
            <span class="title-highlight">Revolution</span>
          </h1>
          <p class="hero-subtitle">
            Transforming the future of software development with intelligent coding assistance, 
            real-time collaboration, and unprecedented productivity enhancement.
          </p>
          <button @click="navigateTo('advantages')" class="cta-button">
            Explore Presentation
            <span class="arrow">→</span>
          </button>
        </div>
        <div class="hero-visual">
          <div class="code-window">
            <div class="window-header">
              <div class="window-dots">
                <span class="dot red"></span>
                <span class="dot yellow"></span>
                <span class="dot green"></span>
              </div>
              <div class="window-title">main.js</div>
            </div>
            <div class="code-content">
              <div class="code-line">
                <span class="code-keyword">const</span>
                <span class="code-variable">aiAssistant</span>
                <span class="code-operator">=</span>
                <span class="code-keyword">new</span>
                <span class="code-function">AIEngine</span>();
              </div>
              <div class="code-line">
                <span class="code-variable">aiAssistant</span>.<span class="code-function">enableSmartCompletion</span>();
              </div>
              <div class="code-line">
                <span class="code-comment">// The future of coding is here</span>
              </div>
            </div>
          </div>
        </div>
      </section>

      <!-- Team Section -->
      <section class="team-section">
        <h2 class="section-title">Group Members</h2>
        <div class="team-grid">
          <div 
            v-for="(member, index) in teamMembers" 
            :key="index"
            class="team-card"
          >
            <div class="member-avatar">
              {{ member.name.charAt(0) }}
            </div>
            <h3 class="member-name">{{ member.name }}</h3>
            <p class="member-id">{{ member.studentId }}</p>
          </div>
        </div>
      </section>
    </div>

    <!-- Advantages Page -->
    <div v-if="currentPage === 'advantages'" class="advantages-page">
      <section class="advantages-hero">
        <div class="hero-background">
          <div class="floating-elements">
            <div class="float-element" style="top: 10%; left: 10%;">🤖</div>
            <div class="float-element" style="top: 20%; right: 15%;">⚡</div>
            <div class="float-element" style="bottom: 20%; left: 20%;">🌍</div>
            <div class="float-element" style="bottom: 10%; right: 10%;">🚀</div>
          </div>
        </div>
        <div class="hero-content">
          <h1 class="advantages-title">AI-Powered IDE Revolution</h1>
          <p class="advantages-subtitle">
            Exploring the four pillars of next-generation development tools
          </p>
          <div class="title-decoration"></div>
        </div>

        <!-- AI IDE Overview Section -->
        <section class="ai-overview-section">
          <div class="overview-container">
            <div class="overview-image-wrapper">
              <img src="/images/ai-ide-overview.png" alt="AI IDE Overview" class="overview-image">
              <div class="image-overlay">
                <div class="overlay-content">
                  <h3 class="overlay-title">AI-Powered Development Ecosystem</h3>
                  <p class="overlay-description">
                    Experience the future of coding where artificial intelligence enhances creativity, 
                    accelerates development, and transforms ideas into reality.
                  </p>
                  <div class="feature-highlights">
                    <div class="feature-item">
                      <span class="feature-icon">🧠</span>
                      <span class="feature-text">Intelligent Code Generation</span>
                    </div>
                    <div class="feature-item">
                      <span class="feature-icon">⚡</span>
                      <span class="feature-text">Real-time AI Assistance</span>
                    </div>
                    <div class="feature-item">
                      <span class="feature-icon">🚀</span>
                      <span class="feature-text">Accelerated Development</span>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </section>
      </section>

      <section class="advantages-content">
        <div class="content-container">
          <div 
            v-for="(advantage, index) in advantages" 
            :key="index"
            class="advantage-card-wrapper"
            :style="{ animationDelay: `${index * 0.3}s` }"
          >
            <div class="advantage-card" :style="{ background: advantage.color }">
              <div class="card-header">
                <div class="advantage-icon-wrapper">
                  <div class="advantage-icon">{{ advantage.icon }}</div>
                  <div class="icon-glow"></div>
                </div>
                <div class="card-number">{{ index + 1 }}</div>
              </div>
              <div class="card-content">
                <h3 class="advantage-title">{{ advantage.title }}</h3>
                <p class="advantage-description">{{ advantage.description }}</p>
                <div 
                  v-for="(section, si) in advantage.sections" 
                  :key="si" 
                  class="adv-section"
                >
                  <h4 class="adv-section-title">{{ section.title }}</h4>

                  <div v-if="section.type === 'comparison'" class="comparison-grid">
                    <div class="comparison-column">
                      <div class="comparison-column-title">{{ section.leftTitle }}</div>
                      <ul class="comparison-list">
                        <li v-for="(item, i) in section.left" :key="i">{{ item }}</li>
                      </ul>
                    </div>
                    <div class="comparison-column">
                      <div class="comparison-column-title">{{ section.rightTitle }}</div>
                      <ul class="comparison-list">
                        <li v-for="(item, i) in section.right" :key="i">{{ item }}</li>
                      </ul>
                    </div>
                  </div>

                  <ul v-else-if="section.type === 'list'" class="adv-list">
                    <li v-for="(item, i) in section.items" :key="i">{{ item }}</li>
                  </ul>

                  <div v-else-if="section.type === 'code_before_after'" class="code-compare">
                    <div class="code-block">
                      <div class="code-block-title">Before</div>
                      <pre>{{ section.before }}</pre>
                    </div>
                    <div class="code-block">
                      <div class="code-block-title">After</div>
                      <pre>{{ section.after }}</pre>
                    </div>
                  </div>

                  <div v-else-if="section.type === 'table'" class="adv-table">
                    <div class="adv-table-header">
                      <span v-for="(col, ci) in section.columns" :key="ci" class="adv-th">{{ col }}</span>
                    </div>
                    <div class="adv-table-row" v-for="(row, ri) in section.rows" :key="ri">
                      <span v-for="(cell, ci) in row" :key="ci" class="adv-td">{{ cell }}</span>
                    </div>
                  </div>

                  <div v-else-if="section.type === 'chart'" class="adv-chart">
                    <div class="chart-row" v-for="(d, di) in section.data" :key="di">
                      <span class="chart-label">{{ d.label }}</span>
                      <div class="chart-bar-wrap">
                        <div class="chart-bar" :style="{ width: d.value + '%' }">
                          <span class="chart-value">{{ d.value }}%</span>
                        </div>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
              <div class="card-decoration">
                <div class="decoration-line"></div>
                <div class="decoration-dots">
                  <span class="dot"></span>
                  <span class="dot"></span>
                  <span class="dot"></span>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>
    </div>

    <!-- Cursor Tutorial Page -->
    <div v-if="currentPage === 'cursor-tutorial'" class="cursor-tutorial-page">
      <section class="tutorial-hero">
        <div class="hero-background">
          <div class="floating-elements">
            <div class="float-element" style="top: 10%; left: 10%;">🚀</div>
            <div class="float-element" style="top: 20%; right: 15%;">✨</div>
            <div class="float-element" style="bottom: 20%; left: 20%;">💬</div>
            <div class="float-element" style="bottom: 10%; right: 10%;">🛠️</div>
            <div class="float-element" style="top: 50%; left: 5%;">🔧</div>
          </div>
        </div>
        <div class="hero-content">
          <h1 class="tutorial-title">Cursor AI Tutorial</h1>
          <p class="tutorial-subtitle">
            Master AI-powered code editing with our comprehensive step-by-step guide
          </p>
          <div class="title-decoration"></div>
        </div>
      </section>

      <section class="tutorial-content">
        <div class="tutorial-content-grid">
          <div 
            v-for="(step, index) in cursorTutorial" 
            :key="index"
            class="tutorial-step-wrapper"
            :class="{ 'top-aligned': index < 2 }"
            :style="{ animationDelay: `${index * 0.3}s` }"
          >
            <div class="tutorial-step" :style="{ background: step.color }">
              <div class="step-header">
                <div class="step-number">{{ step.step }}</div>
                <div class="step-icon-wrapper">
                  <div class="step-icon">{{ step.icon }}</div>
                  <div class="icon-glow"></div>
                </div>
              </div>
              
              <div class="step-content">
                <h3 class="step-title">{{ step.title }}</h3>
                <p class="step-description">{{ step.description }}</p>
                
                <div class="tutorial-image">
                  <img :src="`${baseUrl}images/tutorial/${step.image}`" :alt="step.title" class="step-image">
                </div>

                <div 
                  v-for="(section, si) in step.sections" 
                  :key="si" 
                  class="tutorial-section"
                >
                  <h4 class="tutorial-section-title">{{ section.title }}</h4>

                  <ul v-if="section.type === 'list'" class="tutorial-list">
                    <li v-for="(item, i) in section.items" :key="i">{{ item }}</li>
                  </ul>

                  <div v-else-if="section.type === 'code_example'" class="code-example">
                    <div class="code-example-title">{{ section.title }}</div>
                    <pre><code>{{ section.code }}</code></pre>
                  </div>

                  <div v-else-if="section.type === 'code_before_after'" class="code-compare">
                    <div class="code-block">
                      <div class="code-block-title">Before</div>
                      <pre>{{ section.before }}</pre>
                    </div>
                    <div class="code-block">
                      <div class="code-block-title">After</div>
                      <pre>{{ section.after }}</pre>
                    </div>
                  </div>

                  <div v-else-if="section.type === 'comparison'" class="comparison-grid">
                    <div class="comparison-column">
                      <div class="comparison-column-title">{{ section.leftTitle }}</div>
                      <ul class="comparison-list">
                        <li v-for="(item, i) in section.left" :key="i">{{ item }}</li>
                      </ul>
                    </div>
                    <div class="comparison-column">
                      <div class="comparison-column-title">{{ section.rightTitle }}</div>
                      <ul class="comparison-list">
                        <li v-for="(item, i) in section.right" :key="i">{{ item }}</li>
                      </ul>
                    </div>
                  </div>

                  <ul v-else-if="section.type === 'shortcuts'" class="shortcuts-list">
                    <li v-for="(item, i) in section.items" :key="i">{{ item }}</li>
                  </ul>

                  <ul v-else-if="section.type === 'tips'" class="tips-list">
                    <li v-for="(item, i) in section.items" :key="i">{{ item }}</li>
                  </ul>
                </div>
              </div>

              <div class="step-decoration">
                <div class="decoration-line"></div>
                <div class="decoration-dots">
                  <span class="dot"></span>
                  <span class="dot"></span>
                  <span class="dot"></span>
                </div>
              </div>
            </div>
          </div>

          <!-- Tutorial Summary -->
          <div class="tutorial-summary">
            <div class="summary-card">
              <div class="summary-icon">🎯</div>
              <h3 class="summary-title">Ready to Start?</h3>
              <p class="summary-description">
                You now have the knowledge to leverage Cursor's AI capabilities effectively. 
                Remember: AI is a tool to enhance your creativity, not replace your understanding.
              </p>

              <!-- 新增：网站价值帮助部分 -->
              <div class="website-value-section">
                <h4 class="value-title">🚀 How This Website Empowers Others</h4>
                <p class="value-description">
                  Our comprehensive AI IDE tutorials help developers and organizations rapidly build modern platforms:
                </p>
                <div class="value-points">
                  <div class="value-point">
                    <span class="value-icon">⚡</span>
                    <div class="value-content">
                      <strong>Accelerate Development:</strong> Master AI-powered tools to build applications 3-5x faster than traditional methods
                    </div>
                  </div>
                  <div class="value-point">
                    <span class="value-icon">🏗️</span>
                    <div class="value-content">
                      <strong>Platform Building:</strong> Learn to create scalable web platforms using AI assistance from concept to deployment
                    </div>
                  </div>
                  <div class="value-point">
                    <span class="value-icon">💡</span>
                    <div class="value-content">
                      <strong>Innovation Hub:</strong> Access cutting-edge AI workflows that transform ideas into production-ready solutions
                    </div>
                  </div>
                  <div class="value-point">
                    <span class="value-icon">🌍</span>
                    <div class="value-content">
                      <strong>Global Impact:</strong> Enable teams worldwide to leverage AI for digital transformation and competitive advantage
                    </div>
                  </div>
                </div>
                <p class="value-footer">
                  <em>Whether you're a startup founder, enterprise developer, or individual learner - this knowledge accelerates your platform building journey.</em>
                </p>
              </div>

              <div class="summary-actions">
                <button @click="navigateTo('home')" class="summary-btn secondary">
                  Back to Home
                </button>
                <button @click="navigateTo('advantages')" class="summary-btn primary">
                  Explore More
                </button>
              </div>
            </div>
          </div>
        </div>
      </section>
    </div>
  </div>
</template>

<style scoped>
/* Global Styles */
.app {
  min-height: 100vh;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  color: white;
}

/* Navigation */
.navbar {
  position: fixed;
  top: 0;
  width: 100%;
  background: rgba(0, 0, 0, 0.1);
  backdrop-filter: blur(10px);
  z-index: 1000;
  padding: 1rem 0;
}

.nav-container {
  max-width: 1200px;
  margin: 0 auto;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0 2rem;
}

.nav-logo {
  display: flex;
  align-items: center;
  gap: 0.5rem;
}

.logo-icon {
  font-size: 2rem;
  animation: pulse 2s infinite;
}

.logo-text {
  font-size: 1.5rem;
  font-weight: bold;
  background: linear-gradient(45deg, #fff, #64b5f6);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

.nav-links {
  display: flex;
  gap: 1rem;
}

.nav-btn {
  background: transparent;
  border: 2px solid rgba(255, 255, 255, 0.3);
  color: white;
  padding: 0.5rem 1.5rem;
  border-radius: 25px;
  cursor: pointer;
  transition: all 0.3s ease;
  font-weight: 500;
}

.nav-btn:hover,
.nav-btn.active {
  background: rgba(255, 255, 255, 0.2);
  border-color: rgba(255, 255, 255, 0.8);
  transform: translateY(-2px);
}

/* Home Page */
.home-page {
  padding-top: 80px;
}

/* Hero Section */
.hero {
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: space-between;
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
  gap: 4rem;
}

.hero-content {
  flex: 1;
  max-width: 600px;
}

.hero-title {
  font-size: 3.5rem;
  font-weight: 800;
  line-height: 1.1;
  margin-bottom: 1.5rem;
  animation: fadeInUp 1s ease-out;
}

.title-highlight {
  background: linear-gradient(45deg, #64b5f6, #42a5f5);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  display: block;
}

.hero-subtitle {
  font-size: 1.25rem;
  line-height: 1.6;
  margin-bottom: 2.5rem;
  opacity: 0.9;
  animation: fadeInUp 1s ease-out 0.2s both;
}

.cta-button {
  background: linear-gradient(45deg, #42a5f5, #1e88e5);
  border: none;
  color: white;
  padding: 1rem 2rem;
  font-size: 1.1rem;
  font-weight: 600;
  border-radius: 50px;
  cursor: pointer;
  transition: all 0.3s ease;
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  animation: fadeInUp 1s ease-out 0.4s both;
}

.cta-button:hover {
  transform: translateY(-3px);
  box-shadow: 0 10px 30px rgba(66, 165, 245, 0.4);
}

.arrow {
  transition: transform 0.3s ease;
}

.cta-button:hover .arrow {
  transform: translateX(5px);
}

/* Code Window */
.hero-visual {
  flex: 1;
  display: flex;
  justify-content: center;
  align-items: center;
}

.code-window {
  background: #1e1e1e;
  border-radius: 10px;
  box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
  overflow: hidden;
  animation: fadeInRight 1s ease-out 0.6s both;
  transform: perspective(1000px) rotateY(-5deg);
}

.window-header {
  background: #323232;
  padding: 1rem;
  display: flex;
  align-items: center;
  gap: 1rem;
}

.window-dots {
  display: flex;
  gap: 0.5rem;
}

.dot {
  width: 12px;
  height: 12px;
  border-radius: 50%;
}

.dot.red { background: #ff5f57; }
.dot.yellow { background: #ffbd2e; }
.dot.green { background: #28ca42; }

.window-title {
  color: #ccc;
  font-size: 0.9rem;
}

.code-content {
  padding: 2rem;
  font-family: 'Courier New', monospace;
  font-size: 1rem;
  line-height: 1.6;
}

.code-line {
  margin-bottom: 0.5rem;
}

.code-keyword { color: #c678dd; }
.code-variable { color: #e06c75; }
.code-function { color: #61afef; }
.code-operator { color: #56b6c2; }
.code-comment { color: #5c6370; font-style: italic; }

/* Team Section */
.team-section {
  padding: 5rem 2rem;
  max-width: 1200px;
  margin: 0 auto;
  text-align: center;
}

.section-title {
  font-size: 2.5rem;
  margin-bottom: 3rem;
  background: linear-gradient(45deg, #fff, #64b5f6);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

.team-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 2rem;
}

.team-card {
  background: rgba(255, 255, 255, 0.1);
  backdrop-filter: blur(10px);
  border-radius: 15px;
  padding: 2rem;
  text-align: center;
  transition: all 0.3s ease;
  border: 1px solid rgba(255, 255, 255, 0.2);
}

.team-card:hover {
  transform: translateY(-10px);
  background: rgba(255, 255, 255, 0.15);
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.2);
}

.member-avatar {
  width: 80px;
  height: 80px;
  border-radius: 50%;
  background: linear-gradient(45deg, #42a5f5, #1e88e5);
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 2rem;
  font-weight: bold;
  margin: 0 auto 1rem;
}

.member-name {
  font-size: 1.25rem;
  margin-bottom: 0.5rem;
}

.member-id {
  opacity: 0.8;
  font-size: 0.9rem;
  font-family: 'JetBrains Mono', monospace;
  background: rgba(255, 255, 255, 0.1);
  padding: 0.25rem 0.75rem;
  border-radius: 12px;
  display: inline-block;
  margin-top: 0.5rem;
}

/* Advantages Page */
.advantages-page {
  min-height: 100vh;
  background: linear-gradient(135deg, #0f172a 0%, #1e293b 50%, #334155 100%);
  position: relative;
  overflow: hidden;
}

/* Hero Section */
.advantages-hero {
  position: relative;
  height: 60vh;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  padding: 0 20px;
  overflow: hidden;
}

.hero-background {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  opacity: 0.1;
}

.floating-elements {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
}

.float-element {
  position: absolute;
  font-size: 2rem;
  opacity: 0.3;
  animation: float 6s ease-in-out infinite;
}

.float-element:nth-child(1) { animation-delay: 0s; }
.float-element:nth-child(2) { animation-delay: 1.5s; }
.float-element:nth-child(3) { animation-delay: 3s; }
.float-element:nth-child(4) { animation-delay: 4.5s; }

@keyframes float {
  0%, 100% { transform: translateY(0px) rotate(0deg); }
  50% { transform: translateY(-20px) rotate(5deg); }
}

.hero-content {
  position: relative;
  z-index: 2;
}

.advantages-title {
  font-size: 4rem;
  font-weight: 700;
  background: linear-gradient(135deg, #60a5fa, #c084fc, #f472b6);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  margin-bottom: 20px;
  animation: fadeInUp 1s ease-out;
}

.advantages-subtitle {
  font-size: 1.4rem;
  color: #e2e8f0;
  max-width: 700px;
  margin: 0 auto;
  animation: fadeInUp 1s ease-out 0.2s both;
}

.title-decoration {
  width: 100px;
  height: 4px;
  background: linear-gradient(90deg, #60a5fa, #c084fc);
  margin: 30px auto 0;
  border-radius: 2px;
  animation: slideInFromLeft 1s ease-out 0.4s both;
}

/* Content Section */
.advantages-content {
  padding: 80px 20px;
  position: relative;
}

.content-container {
  max-width: 1400px;
  margin: 0 auto;
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 40px;
  align-items: start;
}

.advantage-card-wrapper {
  animation: fadeInUp 0.8s ease-out;
}

.advantage-card {
  background: rgba(255, 255, 255, 0.05);
  backdrop-filter: blur(20px);
  border: 1px solid rgba(255, 255, 255, 0.1);
  border-radius: 25px;
  padding: 40px;
  position: relative;
  overflow: hidden;
  transition: all 0.5s cubic-bezier(0.4, 0, 0.2, 1);
  height: 100%;
  display: flex;
  flex-direction: column;
}

.advantage-card:hover {
  transform: translateY(-15px) scale(1.02);
  box-shadow: 0 30px 60px rgba(0, 0, 0, 0.4);
  border-color: rgba(255, 255, 255, 0.3);
}

.card-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 25px;
}

.advantage-icon-wrapper {
  position: relative;
}

.advantage-icon {
  font-size: 3.5rem;
  animation: bounce 2s infinite;
  filter: drop-shadow(0 0 20px rgba(255, 255, 255, 0.3));
}

.icon-glow {
  position: absolute;
  top: 50%;
  left: 50%;
  width: 80px;
  height: 80px;
  background: radial-gradient(circle, rgba(255, 255, 255, 0.2) 0%, transparent 70%);
  border-radius: 50%;
  transform: translate(-50%, -50%);
  animation: pulse 3s ease-in-out infinite;
}

.card-number {
  font-size: 2rem;
  font-weight: 700;
  color: rgba(255, 255, 255, 0.3);
  font-family: 'JetBrains Mono', monospace;
}

.card-content {
  flex: 1;
}

.advantage-title {
  font-size: 1.8rem;
  font-weight: 600;
  color: #f8fafc;
  margin-bottom: 20px;
  line-height: 1.3;
}

.advantage-description {
  color: #e2e8f0;
  line-height: 1.7;
  font-size: 1.1rem;
  opacity: 0.9;
}

/* Sections inside advantage card */
.adv-section {
  margin-top: 24px;
  padding-top: 16px;
  border-top: 1px solid rgba(102, 126, 234, 0.25);
}

.adv-section-title {
  font-size: 1.1rem;
  font-weight: 600;
  background: linear-gradient(135deg, #667eea, #764ba2);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  margin-bottom: 12px;
}

/* Comparison */
.comparison-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 16px;
}

.comparison-column-title {
  font-size: 0.95rem;
  color: #cbd5e1;
  margin-bottom: 8px;
}

.comparison-list {
  list-style: none;
  padding: 0;
  margin: 0;
}

.comparison-list li {
  position: relative;
  padding-left: 16px;
  margin: 6px 0;
}

.comparison-list li::before {
  content: '';
  position: absolute;
  left: 0;
  top: 8px;
  width: 6px;
  height: 6px;
  border-radius: 50%;
  background: linear-gradient(135deg, #667eea, #764ba2);
}

/* List */
.adv-list {
  list-style: none;
  padding: 0;
  margin: 0;
}

.adv-list li {
  margin: 6px 0;
  color: #e2e8f0;
}

/* Code Before/After */
.code-compare {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 16px;
}

.code-block-title {
  font-size: 0.9rem;
  color: #cbd5e1;
  margin-bottom: 6px;
}

.code-block pre {
  background: rgba(13, 19, 44, 0.9);
  border: 1px solid rgba(102, 126, 234, 0.25);
  border-radius: 10px;
  padding: 12px;
  font-family: 'JetBrains Mono', monospace;
  font-size: 0.85rem;
  color: #e2e8f0;
  overflow: auto;
}

/* Table */
.adv-table {
  border: 1px solid rgba(102, 126, 234, 0.25);
  border-radius: 12px;
  overflow: hidden;
}

.adv-table-header, .adv-table-row {
  display: grid;
  grid-template-columns: 1.2fr 1.2fr 1.6fr;
}

.adv-table-header {
  background: rgba(102, 126, 234, 0.15);
}

.adv-th, .adv-td {
  padding: 10px 12px;
  font-size: 0.95rem;
}

.adv-th {
  font-weight: 600;
  color: #e5e7eb;
}

.adv-td {
  color: #cbd5e1;
  border-top: 1px solid rgba(102, 126, 234, 0.15);
}

/* Chart */
.adv-chart {
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.chart-row {
  display: flex;
  align-items: center;
  gap: 12px;
}

.chart-label {
  width: 60px;
  color: #cbd5e1;
  font-size: 0.9rem;
}

.chart-bar-wrap {
  flex: 1;
  background: rgba(102, 126, 234, 0.12);
  border: 1px solid rgba(102, 126, 234, 0.25);
  border-radius: 8px;
  overflow: hidden;
}

.chart-bar {
  height: 22px;
  background: linear-gradient(90deg, #667eea, #764ba2);
  display: flex;
  align-items: center;
  justify-content: flex-end;
}

.chart-value {
  color: #fff;
  font-size: 0.8rem;
  padding-right: 6px;
}

.card-decoration {
  margin-top: 30px;
  padding-top: 20px;
  border-top: 1px solid rgba(255, 255, 255, 0.1);
}

.decoration-line {
  height: 2px;
  background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.5), transparent);
  margin-bottom: 15px;
}

.decoration-dots {
  display: flex;
  gap: 8px;
  justify-content: center;
}

.dot {
  width: 6px;
  height: 6px;
  background: rgba(255, 255, 255, 0.4);
  border-radius: 50%;
  animation: dotPulse 2s ease-in-out infinite;
}

.dot:nth-child(2) { animation-delay: 0.3s; }
.dot:nth-child(3) { animation-delay: 0.6s; }

@keyframes dotPulse {
  0%, 100% { opacity: 0.4; transform: scale(1); }
  50% { opacity: 1; transform: scale(1.2); }
}

/* Cursor Tutorial Page Styles */
.cursor-tutorial-page {
  min-height: 100vh;
  background: linear-gradient(135deg, #1e1b4b 0%, #312e81 50%, #1e40af 100%);
  position: relative;
  overflow: hidden;
}
/* AI Overview Section Styles */
.ai-overview-section {
  margin: 60px 0;
  padding: 0 20px;
}

.overview-container {
  max-width: 1400px;
  margin: 0 auto;
}

.overview-image-wrapper {
  position: relative;
  border-radius: 25px;
  overflow: hidden;
  /* background: rgba(255, 255, 255, 0.05); */
  background: linear-gradient(135deg, rgba(30, 27, 75, 0.3), rgba(49, 46, 129, 0.2));
  backdrop-filter: blur(20px);
  /* border: 1px solid rgba(255, 255, 255, 0.1);
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3); */
  border: 1px solid rgba(255, 255, 255, 0.05);
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.2);
}

.overview-image {
  width: 100%;
  height: auto;
  display: block;
  filter: brightness(0.5) contrast(1.1);
}

.image-overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: linear-gradient(
    45deg,
    rgba(30, 27, 75, 0.7) 0%,
    rgba(49, 46, 129, 0.5) 50%,
    rgba(30, 64, 175, 0.7) 100%
  );
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 40px;
}

.overlay-content {
  text-align: center;
  color: white;
  max-width: 600px;
}

.overlay-title {
  font-size: 2.2rem;
  font-weight: 700;
  margin-bottom: 20px;
  background: linear-gradient(45deg, #42a5f5, #1e88e5);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.overlay-description {
  font-size: 1.1rem;
  line-height: 1.6;
  margin-bottom: 30px;
  color: rgba(255, 255, 255, 0.9);
}

.feature-highlights {
  display: flex;
  justify-content: center;
  gap: 30px;
  flex-wrap: wrap;
}

.feature-item {
  display: flex;
  align-items: center;
  gap: 8px;
  background: rgba(255, 255, 255, 0.1);
  padding: 12px 20px;
  border-radius: 25px;
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255, 255, 255, 0.2);
  transition: all 0.3s ease;
}

.feature-item:hover {
  background: rgba(66, 165, 245, 0.2);
  transform: translateY(-2px);
}

.feature-icon {
  font-size: 1.2rem;
}

.feature-text {
  font-size: 0.9rem;
  font-weight: 600;
  color: white;
}

.tutorial-hero {
  position: relative;
  height: 50vh;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  padding: 0 20px;
  overflow: hidden;
}

.tutorial-title {
  font-size: 4rem;
  font-weight: 700;
  background: linear-gradient(135deg, #60a5fa, #c084fc, #f472b6);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  margin-bottom: 20px;
  animation: fadeInUp 1s ease-out;
}

.tutorial-subtitle {
  font-size: 1.4rem;
  color: #e2e8f0;
  max-width: 700px;
  margin: 0 auto;
  animation: fadeInUp 1s ease-out 0.2s both;
}

.tutorial-content {
  padding: 80px 20px;
  position: relative;
}

/* New flowing grid layout for tutorial */
.tutorial-content-grid {
  max-width: 1400px;
  margin: 0 auto;
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 40px;
  grid-auto-flow: dense;
  align-items: start;
}

.tutorial-step-wrapper {
  animation: fadeInUp 0.8s ease-out;
}

/* Top-aligned cards for first row */
.tutorial-step-wrapper.top-aligned {
  align-self: start;
}

.tutorial-step {
  background: rgba(255, 255, 255, 0.05);
  backdrop-filter: blur(20px);
  border: 1px solid rgba(255, 255, 255, 0.1);
  border-radius: 25px;
  padding: 40px;
  position: relative;
  overflow: hidden;
  transition: all 0.5s cubic-bezier(0.4, 0, 0.2, 1);
  height: auto;
  min-height: 200px;
}

.tutorial-step:hover {
  transform: translateY(-10px);
  box-shadow: 0 30px 60px rgba(0, 0, 0, 0.4);
  border-color: rgba(255, 255, 255, 0.3);
}

.step-header {
  display: flex;
  align-items: center;
  gap: 20px;
  margin-bottom: 30px;
}

.step-number {
  font-size: 3rem;
  font-weight: 700;
  color: rgba(255, 255, 255, 0.3);
  font-family: 'JetBrains Mono', monospace;
  min-width: 80px;
}

.step-icon-wrapper {
  position: relative;
}

.step-icon {
  font-size: 3.5rem;
  animation: bounce 2s infinite;
  filter: drop-shadow(0 0 20px rgba(255, 255, 255, 0.3));
}

.step-content {
  flex: 1;
}

.step-title {
  font-size: 1.8rem;
  font-weight: 600;
  color: #f8fafc;
  margin-bottom: 20px;
  line-height: 1.3;
}

.step-description {
  color: #e2e8f0;
  line-height: 1.7;
  font-size: 1.1rem;
  opacity: 0.9;
  margin-bottom: 30px;
}

.tutorial-image {
  margin: 15px 0;
  text-align: center;
}

.step-image {
  max-width: 100%;
  border-radius: 12px;
  max-height: 250px;
}

.tutorial-section {
  margin-top: 30px;
  padding-top: 20px;
  border-top: 1px solid rgba(102, 126, 234, 0.25);
}

.tutorial-section-title {
  font-size: 1.2rem;
  font-weight: 600;
  background: linear-gradient(135deg, #667eea, #764ba2);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  margin-bottom: 15px;
}

.tutorial-list {
  list-style: none;
  padding: 0;
  margin: 0;
}

.tutorial-list li {
  position: relative;
  padding-left: 20px;
  margin: 8px 0;
  color: #e2e8f0;
  line-height: 1.6;
}

.tutorial-list li::before {
  content: '▸';
  position: absolute;
  left: 0;
  color: #60a5fa;
  font-weight: bold;
}

.code-example {
  margin: 20px 0;
}

.code-example-title {
  font-size: 1rem;
  color: #cbd5e1;
  margin-bottom: 10px;
}

.code-example pre {
  background: rgba(13, 19, 44, 0.9);
  border: 1px solid rgba(102, 126, 234, 0.25);
  border-radius: 12px;
  padding: 20px;
  font-family: 'JetBrains Mono', monospace;
  font-size: 0.9rem;
  color: #e2e8f0;
  overflow-x: auto;
  line-height: 1.5;
}

.code-example code {
  color: inherit;
}

.shortcuts-list {
  list-style: none;
  padding: 0;
  margin: 0;
}

.shortcuts-list li {
  background: rgba(102, 126, 234, 0.1);
  border: 1px solid rgba(102, 126, 234, 0.2);
  border-radius: 8px;
  padding: 12px 16px;
  margin: 8px 0;
  color: #e2e8f0;
  position: relative;
  padding-left: 50px;
}

.shortcuts-list li::before {
  content: '⌨️';
  position: absolute;
  left: 16px;
  top: 12px;
}

.tips-list {
  list-style: none;
  padding: 0;
  margin: 0;
}

.tips-list li {
  background: rgba(16, 185, 129, 0.1);
  border: 1px solid rgba(16, 185, 129, 0.2);
  border-radius: 8px;
  padding: 12px 16px;
  margin: 8px 0;
  color: #e2e8f0;
  position: relative;
  padding-left: 50px;
}

.tips-list li::before {
  content: '💡';
  position: absolute;
  left: 16px;
  top: 12px;
}

.step-decoration {
  margin-top: 30px;
  padding-top: 20px;
  border-top: 1px solid rgba(255, 255, 255, 0.1);
}

/* Tutorial Summary */
.tutorial-summary {
  grid-column: 1 / -1;
  margin-top: 40px;
  text-align: center;
}

.summary-card {
  background: rgba(255, 255, 255, 0.05);
  backdrop-filter: blur(20px);
  border: 1px solid rgba(255, 255, 255, 0.1);
  border-radius: 25px;
  /* padding: 50px 40px; */
  /* max-width: 600px; */
  max-width: calc(100vw - 40px);
  padding: 30px 20px;
  margin: 0 auto;
}

.summary-icon {
  font-size: 3rem;
  margin-bottom: 20px;
  animation: pulse 2s infinite;
}

.summary-title {
  font-size: 2rem;
  font-weight: 600;
  color: #f8fafc;
  margin-bottom: 15px;
}

.summary-description {
  color: #e2e8f0;
  line-height: 1.6;
  margin-bottom: 30px;
}


/* 新增：网站价值帮助部分样式 */
.website-value-section {
  background: rgba(66, 165, 245, 0.1);
  border: 1px solid rgba(66, 165, 245, 0.2);
  border-radius: 20px;
  padding: 25px 20px;
  margin: 30px 0;
  text-align: left;
}

.value-title {
  font-size: 1.3rem;
  font-weight: 600;
  color: #42a5f5;
  margin-bottom: 15px;
  text-align: center;
}

.value-description {
  color: #e2e8f0;
  line-height: 1.5;
  margin-bottom: 20px;
  font-size: 0.95rem;
}

.value-points {
  display: flex;
  flex-direction: column;
  gap: 15px;
  margin-bottom: 20px;
}

.value-point {
  display: flex;
  align-items: flex-start;
  gap: 12px;
  padding: 10px;
  background: rgba(255, 255, 255, 0.05);
  border-radius: 12px;
  transition: all 0.3s ease;
}

.value-point:hover {
  background: rgba(66, 165, 245, 0.1);
  transform: translateX(5px);
}

.value-icon {
  font-size: 1.2rem;
  min-width: 24px;
  margin-top: 2px;
}

.value-content {
  color: #e2e8f0;
  font-size: 0.9rem;
  line-height: 1.4;
}

.value-content strong {
  color: #42a5f5;
  font-weight: 600;
}

.value-footer {
  color: #cbd5e1;
  font-size: 0.9rem;
  text-align: center;
  margin-top: 20px;
  padding: 15px;
  background: rgba(255, 255, 255, 0.03);
  border-radius: 10px;
  border-left: 3px solid #42a5f5;
}

.summary-actions {
  display: flex;
  gap: 15px;
  justify-content: center;
  flex-wrap: wrap;
}

.summary-btn {
  padding: 12px 24px;
  border-radius: 25px;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.3s ease;
  border: none;
}

.summary-btn.primary {
  background: linear-gradient(45deg, #42a5f5, #1e88e5);
  color: white;
}

.summary-btn.secondary {
  background: transparent;
  color: #e2e8f0;
  border: 2px solid rgba(255, 255, 255, 0.3);
}

.summary-btn:hover {
  transform: translateY(-2px);
}

.summary-btn.primary:hover {
  box-shadow: 0 10px 30px rgba(66, 165, 245, 0.4);
}

.summary-btn.secondary:hover {
  background: rgba(255, 255, 255, 0.1);
}

/* Animations */
@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes fadeInRight {
  from {
    opacity: 0;
    transform: translateX(30px);
  }
  to {
    opacity: 1;
    transform: translateX(0);
  }
}

@keyframes pulse {
  0%, 100% { transform: scale(1); }
  50% { transform: scale(1.1); }
}

@keyframes bounce {
  0%, 20%, 50%, 80%, 100% { transform: translateY(0); }
  40% { transform: translateY(-10px); }
  60% { transform: translateY(-5px); }
}

@keyframes rotate {
  from { transform: rotate(0deg); }
  to { transform: rotate(360deg); }
}

/* Responsive Design */
@media (max-width: 1200px) {
  .content-container {
    grid-template-columns: 1fr;
    max-width: 800px;
  }
}

@media (max-width: 768px) {
  .hero {
    flex-direction: column;
    text-align: center;
    gap: 2rem;
  }
  
  .hero-title {
    font-size: 2.5rem;
  }
  
  .hero-subtitle {
    font-size: 1.1rem;
  }
  
  .advantages-title {
    font-size: 2.8rem;
  }
  
  .tutorial-title {
    font-size: 2.8rem;
  }
  
  .advantages-subtitle,
  .tutorial-subtitle {
    font-size: 1.2rem;
  }
  
  .content-container {
    grid-template-columns: 1fr;
    gap: 30px;
  }
  
  .advantage-card {
    padding: 30px 25px;
  }

  .tutorial-step {
    padding: 30px 25px;
  }
  
  .advantage-title,
  .step-title {
    font-size: 1.5rem;
  }
  
  .advantage-description,
  .step-description {
    font-size: 1rem;
  }
  
  .advantage-icon,
  .step-icon {
    font-size: 3rem;
  }
  
  .nav-container {
    padding: 0 1rem;
  }
  
  .nav-links {
    gap: 0.5rem;
  }
  
  .nav-btn {
    padding: 0.4rem 1rem;
    font-size: 0.9rem;
  }
  
  .team-grid {
    grid-template-columns: 1fr;
  }
  
  .advantages-hero,
  .tutorial-hero {
    height: 50vh;
  }

  .step-header {
    flex-direction: column;
    align-items: flex-start;
    gap: 15px;
  }

  .step-number {
    min-width: auto;
    font-size: 2rem;
  }

  .code-compare {
    grid-template-columns: 1fr;
  }

  .comparison-grid {
    grid-template-columns: 1fr;
  }

  .summary-actions {
    flex-direction: column;
    align-items: center;
  }

  .summary-btn {
    width: 200px;
  }

  /* Mobile grid adjustments */
  .tutorial-content-grid {
    grid-template-columns: 1fr;
    gap: 30px;
  }
}

@media (max-width: 480px) {
  .advantages-title,
  .tutorial-title {
    font-size: 2.2rem;
  }
  
  .advantages-subtitle,
  .tutorial-subtitle {
    font-size: 1rem;
  }
  
  .advantage-card,
  .tutorial-step {
    padding: 25px 20px;
  }
  
  .card-header,
  .step-header {
    flex-direction: column;
    align-items: flex-start;
    gap: 15px;
  }
  
  .advantage-title,
  .step-title {
    font-size: 1.3rem;
  }
  
  .float-element {
    font-size: 1.5rem;
  }
}

/* 移动端：AI概览部分响应式样式 */
  .ai-overview-section {
    margin: 30px 0;
    padding: 0 10px;
  }
  
  .image-overlay {
    padding: 20px;
  }
  
  .overlay-title {
    font-size: 1.6rem;
    margin-bottom: 15px;
  }
  
  .overlay-description {
    font-size: 1rem;
    margin-bottom: 20px;
  }
  
  .feature-highlights {
    gap: 15px;
  }
  
  .feature-item {
    padding: 10px 15px;
  }
  
  .feature-text {
    font-size: 0.8rem;
  }

</style>