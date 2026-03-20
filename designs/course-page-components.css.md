# 课程页面 CSS 组件库 - Component Library

**版本：** v1.0  
**创建时间：** 2026-03-20  
**技术栈：** Tailwind CSS + Custom CSS

---

## 🎨 设计令牌 (Design Tokens)

### 颜色变量

```css
:root {
  /* 主色调 - 橙色系 */
  --color-primary: #f97316;
  --color-primary-dark: #ea580c;
  --color-primary-darker: #c2410c;
  --color-primary-light: #fed7aa;
  --color-primary-lighter: #ffedd5;
  
  /* 中性色 - 灰色系 */
  --color-gray-50: #f9fafb;
  --color-gray-100: #f3f4f6;
  --color-gray-200: #e5e7eb;
  --color-gray-300: #d1d5db;
  --color-gray-400: #9ca3af;
  --color-gray-500: #6b7280;
  --color-gray-600: #4b5563;
  --color-gray-700: #374151;
  --color-gray-800: #1f2937;
  --color-gray-900: #111827;
  
  /* 功能色 */
  --color-success: #10b981;
  --color-error: #ef4444;
  --color-warning: #f59e0b;
  --color-info: #3b82f6;
  
  /* 评分颜色 */
  --color-rating: #fbbf24;
  
  /* 背景色 */
  --bg-white: #ffffff;
  --bg-gray: #f9fafb;
  --bg-gradient: linear-gradient(135deg, #fff7ed 0%, #ffffff 100%);
  --bg-gradient-orange: linear-gradient(135deg, #f97316 0%, #ea580c 100%);
  
  /* 文字颜色 */
  --text-primary: #1f2937;
  --text-secondary: #374151;
  --text-tertiary: #6b7280;
  --text-inverse: #ffffff;
  
  /* 边框颜色 */
  --border-light: #e5e7eb;
  --border-medium: #d1d5db;
  --border-primary: #f97316;
  
  /* 阴影 */
  --shadow-sm: 0 1px 2px 0 rgba(0, 0, 0, 0.05);
  --shadow-md: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
  --shadow-lg: 0 10px 15px -3px rgba(0, 0, 0, 0.1);
  --shadow-xl: 0 20px 25px -5px rgba(0, 0, 0, 0.1);
  --shadow-2xl: 0 25px 50px -12px rgba(0, 0, 0, 0.25);
  --shadow-primary: 0 4px 12px rgba(249, 115, 22, 0.3);
  
  /* 圆角 */
  --radius-sm: 4px;
  --radius-md: 8px;
  --radius-lg: 12px;
  --radius-xl: 16px;
  --radius-2xl: 24px;
  --radius-full: 9999px;
  
  /* 间距 */
  --spacing-1: 4px;
  --spacing-2: 8px;
  --spacing-3: 12px;
  --spacing-4: 16px;
  --spacing-5: 20px;
  --spacing-6: 24px;
  --spacing-8: 32px;
  --spacing-10: 40px;
  --spacing-12: 48px;
  --spacing-16: 64px;
  --spacing-20: 80px;
  --spacing-24: 96px;
  --spacing-32: 128px;
  
  /* 字体 */
  --font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', 
                 'PingFang SC', 'Hiragino Sans GB', 'Microsoft YaHei', sans-serif;
  
  /* 字号 */
  --text-xs: 0.75rem;    /* 12px */
  --text-sm: 0.875rem;   /* 14px */
  --text-base: 1rem;     /* 16px */
  --text-lg: 1.125rem;   /* 18px */
  --text-xl: 1.25rem;    /* 20px */
  --text-2xl: 1.5rem;    /* 24px */
  --text-3xl: 2rem;      /* 32px */
  --text-4xl: 2.5rem;    /* 40px */
  --text-5xl: 3rem;      /* 48px */
  --text-6xl: 3.75rem;   /* 60px */
  
  /* 字重 */
  --font-normal: 400;
  --font-medium: 500;
  --font-semibold: 600;
  --font-bold: 700;
  
  /* 行高 */
  --leading-tight: 1.25;
  --leading-normal: 1.5;
  --leading-relaxed: 1.625;
  
  /* 断点 */
  --breakpoint-sm: 640px;
  --breakpoint-md: 768px;
  --breakpoint-lg: 1024px;
  --breakpoint-xl: 1280px;
  --breakpoint-2xl: 1536px;
  
  /* 容器 */
  --container-max: 1200px;
  --container-padding: 20px;
  
  /* 动画 */
  --transition-fast: 150ms ease;
  --transition-base: 300ms ease;
  --transition-slow: 500ms ease;
  --transition-bounce: 500ms cubic-bezier(0.68, -0.55, 0.265, 1.55);
}
```

---

## 🧩 基础组件

### 1. 按钮 (Button)

```css
/* 基础按钮 */
.btn {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: var(--spacing-2);
  padding: var(--spacing-3) var(--spacing-6);
  font-size: var(--text-base);
  font-weight: var(--font-semibold);
  line-height: 1.5;
  text-decoration: none;
  border: 2px solid transparent;
  border-radius: var(--radius-lg);
  cursor: pointer;
  transition: all var(--transition-base);
  white-space: nowrap;
}

/* 主按钮 - 橙色 */
.btn-primary {
  background-color: var(--color-primary);
  color: var(--text-inverse);
  border-color: var(--color-primary);
}

.btn-primary:hover {
  background-color: var(--color-primary-dark);
  border-color: var(--color-primary-dark);
  transform: translateY(-2px);
  box-shadow: var(--shadow-primary);
}

.btn-primary:active {
  background-color: var(--color-primary-darker);
  border-color: var(--color-primary-darker);
  transform: translateY(0);
}

.btn-primary:disabled {
  background-color: var(--color-gray-300);
  border-color: var(--color-gray-300);
  cursor: not-allowed;
  transform: none;
  box-shadow: none;
}

/* 次按钮 - 橙色边框 */
.btn-secondary {
  background-color: transparent;
  color: var(--color-primary);
  border-color: var(--color-primary);
}

.btn-secondary:hover {
  background-color: var(--color-primary);
  color: var(--text-inverse);
}

/* 白色按钮 */
.btn-white {
  background-color: var(--bg-white);
  color: var(--color-primary);
  border-color: var(--bg-white);
}

.btn-white:hover {
  background-color: var(--color-gray-50);
  transform: translateY(-2px);
  box-shadow: var(--shadow-lg);
}

/* 按钮尺寸 */
.btn-sm {
  padding: var(--spacing-2) var(--spacing-4);
  font-size: var(--text-sm);
}

.btn-lg {
  padding: var(--spacing-4) var(--spacing-8);
  font-size: var(--text-lg);
  min-width: 200px;
  height: 56px;
}

.btn-xl {
  padding: var(--spacing-5) var(--spacing-10);
  font-size: var(--text-xl);
  min-width: 280px;
  height: 64px;
}

/* 全宽按钮 */
.btn-block {
  width: 100%;
}
```

### 2. 卡片 (Card)

```css
/* 基础卡片 */
.card {
  background-color: var(--bg-white);
  border: 1px solid var(--border-light);
  border-radius: var(--radius-lg);
  box-shadow: var(--shadow-md);
  transition: all var(--transition-base);
}

.card:hover {
  transform: translateY(-4px);
  box-shadow: var(--shadow-xl);
  border-color: var(--color-primary);
}

/* 卡片内边距 */
.card-body {
  padding: var(--spacing-6);
}

.card-body-lg {
  padding: var(--spacing-8);
}

/* 高亮卡片 */
.card-highlight {
  border: 2px solid var(--color-primary);
  box-shadow: var(--shadow-lg);
}

/* 价格卡片 */
.card-price {
  max-width: 400px;
  margin: 0 auto;
  padding: var(--spacing-10);
  border: 2px solid var(--color-primary);
  border-radius: var(--radius-xl);
  box-shadow: var(--shadow-2xl);
}
```

### 3. 徽章 (Badge)

```css
/* 基础徽章 */
.badge {
  display: inline-flex;
  align-items: center;
  gap: var(--spacing-1);
  padding: var(--spacing-1) var(--spacing-3);
  font-size: var(--text-xs);
  font-weight: var(--font-medium);
  line-height: 1.4;
  border-radius: var(--radius-full);
}

/* 徽章颜色 */
.badge-primary {
  background-color: var(--color-primary-lighter);
  color: var(--color-primary-dark);
}

.badge-success {
  background-color: #d1fae5;
  color: #065f46;
}

.badge-error {
  background-color: #fee2e2;
  color: #991b1b;
}

.badge-warning {
  background-color: #fef3c7;
  color: #92400e;
}

/* 热门标签 */
.badge-hot {
  background: var(--bg-gradient-orange);
  color: var(--text-inverse);
  animation: pulse 2s infinite;
}

@keyframes pulse {
  0%, 100% { opacity: 1; }
  50% { opacity: 0.85; }
}
```

---

## 🏗️ 布局组件

### 1. 容器 (Container)

```css
.container {
  max-width: var(--container-max);
  margin: 0 auto;
  padding-left: var(--container-padding);
  padding-right: var(--container-padding);
}

@media (min-width: 768px) {
  .container {
    padding-left: var(--spacing-6);
    padding-right: var(--spacing-6);
  }
}

@media (min-width: 1024px) {
  .container {
    padding-left: var(--spacing-8);
    padding-right: var(--spacing-8);
  }
}
```

### 2. Section

```css
.section {
  padding: var(--spacing-20) 0;
}

.section-sm {
  padding: var(--spacing-16) 0;
}

.section-lg {
  padding: var(--spacing-24) 0;
}

.section-title {
  font-size: var(--text-4xl);
  font-weight: var(--font-bold);
  color: var(--text-primary);
  text-align: center;
  margin-bottom: var(--spacing-12);
}

@media (max-width: 767px) {
  .section {
    padding: var(--spacing-10) 0;
  }
  
  .section-title {
    font-size: var(--text-3xl);
    margin-bottom: var(--spacing-8);
  }
}
```

### 3. Grid 系统

```css
/* 亮点卡片网格 */
.grid-highlights {
  display: grid;
  grid-template-columns: 1fr;
  gap: var(--spacing-6);
}

@media (min-width: 640px) {
  .grid-highlights {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (min-width: 1024px) {
  .grid-highlights {
    grid-template-columns: repeat(4, 1fr);
  }
}

/* 评价卡片网格 */
.grid-testimonials {
  display: grid;
  grid-template-columns: 1fr;
  gap: var(--spacing-6);
}

@media (min-width: 768px) {
  .grid-testimonials {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (min-width: 1024px) {
  .grid-testimonials {
    grid-template-columns: repeat(3, 1fr);
  }
}
```

---

## 🎭 模块组件

### 1. Hero 区域

```css
.hero {
  background: var(--bg-gradient);
  padding: var(--spacing-20) 0;
  position: relative;
  overflow: hidden;
}

.hero-content {
  display: grid;
  grid-template-columns: 1fr;
  gap: var(--spacing-8);
  align-items: center;
}

@media (min-width: 768px) {
  .hero-content {
    grid-template-columns: 2fr 1fr;
    gap: var(--spacing-12);
  }
}

.hero-title {
  font-size: var(--text-5xl);
  font-weight: var(--font-bold);
  color: var(--text-primary);
  line-height: var(--leading-tight);
  margin-bottom: var(--spacing-4);
}

@media (max-width: 767px) {
  .hero-title {
    font-size: var(--text-3xl);
  }
}

.hero-subtitle {
  font-size: var(--text-xl);
  color: var(--text-tertiary);
  line-height: var(--leading-relaxed);
  margin-bottom: var(--spacing-6);
}

.hero-rating {
  display: flex;
  align-items: center;
  gap: var(--spacing-3);
  margin-bottom: var(--spacing-8);
}

.hero-stars {
  color: var(--color-rating);
  font-size: var(--text-xl);
}

.hero-rating-text {
  font-size: var(--text-base);
  color: var(--text-secondary);
}

.hero-instructor {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: var(--spacing-4);
}

@media (min-width: 768px) {
  .hero-instructor {
    align-items: flex-end;
  }
}

.hero-instructor-photo {
  width: 120px;
  height: 120px;
  border-radius: var(--radius-full);
  object-fit: cover;
  border: 4px solid var(--bg-white);
  box-shadow: var(--shadow-lg);
}

.hero-instructor-info {
  text-align: center;
}

@media (min-width: 768px) {
  .hero-instructor-info {
    text-align: right;
  }
}

.hero-instructor-name {
  font-size: var(--text-lg);
  font-weight: var(--font-bold);
  color: var(--text-primary);
}

.hero-instructor-title {
  font-size: var(--text-sm);
  color: var(--text-tertiary);
}

.hero-qr-code {
  width: 100px;
  height: 100px;
  border: 2px solid var(--border-light);
  border-radius: var(--radius-md);
  padding: var(--spacing-2);
  background: var(--bg-white);
}
```

### 2. 亮点卡片

```css
.highlight-card {
  background: var(--bg-white);
  border: 1px solid var(--border-light);
  border-radius: var(--radius-lg);
  padding: var(--spacing-8);
  text-align: center;
  transition: all var(--transition-base);
}

.highlight-card:hover {
  transform: translateY(-4px);
  border-color: var(--color-primary);
  box-shadow: var(--shadow-xl);
}

.highlight-icon {
  width: 64px;
  height: 64px;
  margin: 0 auto var(--spacing-6);
  font-size: 48px;
  line-height: 1;
}

.highlight-title {
  font-size: var(--text-2xl);
  font-weight: var(--font-semibold);
  color: var(--text-primary);
  margin-bottom: var(--spacing-4);
}

.highlight-description {
  font-size: var(--text-sm);
  color: var(--text-tertiary);
  line-height: var(--leading-relaxed);
  margin-bottom: var(--spacing-6);
  min-height: 60px;
}

.highlight-meta {
  display: flex;
  justify-content: center;
  gap: var(--spacing-4);
  padding-top: var(--spacing-6);
  border-top: 1px solid var(--border-light);
  font-size: var(--text-sm);
  color: var(--text-tertiary);
}

.highlight-meta-item {
  display: flex;
  align-items: center;
  gap: var(--spacing-2);
}
```

### 3. 课程大纲 (手风琴)

```css
.accordion {
  max-width: 800px;
  margin: 0 auto;
}

.accordion-item {
  background: var(--bg-white);
  border: 1px solid var(--border-light);
  border-radius: var(--radius-md);
  margin-bottom: var(--spacing-4);
  overflow: hidden;
}

.accordion-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: var(--spacing-6);
  cursor: pointer;
  transition: all var(--transition-fast);
}

.accordion-header:hover {
  background: var(--bg-gray);
}

.accordion-title {
  font-size: var(--text-lg);
  font-weight: var(--font-semibold);
  color: var(--text-primary);
}

.accordion-meta {
  font-size: var(--text-sm);
  color: var(--text-tertiary);
  margin-top: var(--spacing-1);
}

.accordion-icon {
  font-size: var(--text-xl);
  color: var(--color-primary);
  transition: transform var(--transition-base);
}

.accordion-item.active .accordion-icon {
  transform: rotate(45deg);
}

.accordion-content {
  max-height: 0;
  overflow: hidden;
  transition: max-height var(--transition-base);
}

.accordion-item.active .accordion-content {
  max-height: 500px;
}

.accordion-body {
  padding: 0 var(--spacing-6) var(--spacing-6);
}

.accordion-lessons {
  list-style: none;
  padding: 0;
  margin: 0;
}

.accordion-lesson {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: var(--spacing-3) 0;
  border-bottom: 1px solid var(--border-light);
}

.accordion-lesson:last-child {
  border-bottom: none;
}

.accordion-lesson-title {
  font-size: var(--text-sm);
  color: var(--text-secondary);
}

.accordion-lesson-duration {
  font-size: var(--text-xs);
  color: var(--text-tertiary);
}

.accordion-badges {
  display: flex;
  gap: var(--spacing-2);
  margin-top: var(--spacing-4);
}
```

### 4. 学员评价

```css
.testimonial-card {
  background: var(--bg-white);
  border: 1px solid var(--border-light);
  border-radius: var(--radius-lg);
  padding: var(--spacing-6);
  transition: all var(--transition-base);
}

.testimonial-card:hover {
  transform: translateY(-4px);
  box-shadow: var(--shadow-xl);
}

.testimonial-rating {
  color: var(--color-rating);
  font-size: var(--text-lg);
  margin-bottom: var(--spacing-4);
}

.testimonial-content {
  font-size: var(--text-base);
  color: var(--text-secondary);
  line-height: var(--leading-relaxed);
  margin-bottom: var(--spacing-6);
  min-height: 100px;
}

.testimonial-author {
  display: flex;
  align-items: center;
  gap: var(--spacing-4);
  padding-top: var(--spacing-4);
  border-top: 1px solid var(--border-light);
}

.testimonial-avatar {
  width: 48px;
  height: 48px;
  border-radius: var(--radius-full);
  object-fit: cover;
}

.testimonial-info {
  flex: 1;
}

.testimonial-name {
  font-size: var(--text-base);
  font-weight: var(--font-semibold);
  color: var(--text-primary);
}

.testimonial-role {
  font-size: var(--text-sm);
  color: var(--text-tertiary);
}

.testimonial-result {
  font-size: var(--text-xs);
  color: var(--color-success);
  font-weight: var(--font-medium);
}

/* 轮播控制 */
.testimonial-carousel {
  position: relative;
}

.testimonial-controls {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: var(--spacing-4);
  margin-top: var(--spacing-8);
}

.testimonial-nav {
  width: 40px;
  height: 40px;
  border-radius: var(--radius-full);
  border: 1px solid var(--border-light);
  background: var(--bg-white);
  cursor: pointer;
  transition: all var(--transition-fast);
}

.testimonial-nav:hover {
  background: var(--color-primary);
  color: var(--text-inverse);
  border-color: var(--color-primary);
}

.testimonial-indicator {
  font-size: var(--text-sm);
  color: var(--text-tertiary);
}
```

### 5. 价格卡片

```css
.price-card {
  max-width: 400px;
  margin: 0 auto;
  background: var(--bg-white);
  border: 2px solid var(--color-primary);
  border-radius: var(--radius-xl);
  padding: var(--spacing-10);
  box-shadow: var(--shadow-2xl);
  position: relative;
}

.price-badge {
  position: absolute;
  top: -12px;
  left: 50%;
  transform: translateX(-50%);
  background: var(--bg-gradient-orange);
  color: var(--text-inverse);
  padding: var(--spacing-2) var(--spacing-6);
  border-radius: var(--radius-full);
  font-size: var(--text-sm);
  font-weight: var(--font-semibold);
  white-space: nowrap;
}

.price-countdown {
  background: var(--bg-gradient-orange);
  color: var(--text-inverse);
  text-align: center;
  padding: var(--spacing-3);
  border-radius: var(--radius-md);
  margin-bottom: var(--spacing-8);
  font-weight: var(--font-bold);
  font-size: var(--text-lg);
}

.price-original {
  font-size: var(--text-2xl);
  color: var(--text-tertiary);
  text-decoration: line-through;
  text-align: center;
}

.price-current {
  font-size: var(--text-6xl);
  font-weight: var(--font-bold);
  color: var(--color-primary);
  text-align: center;
  line-height: 1;
}

.price-save {
  text-align: center;
  color: var(--color-error);
  font-size: var(--text-lg);
  font-weight: var(--font-semibold);
  margin-bottom: var(--spacing-8);
}

.price-features {
  list-style: none;
  padding: 0;
  margin: 0 0 var(--spacing-8);
}

.price-feature {
  display: flex;
  align-items: center;
  gap: var(--spacing-3);
  padding: var(--spacing-2) 0;
  font-size: var(--text-base);
  color: var(--text-secondary);
}

.price-feature-check {
  color: var(--color-success);
  font-size: var(--text-lg);
}

.price-actions {
  display: flex;
  flex-direction: column;
  gap: var(--spacing-4);
  margin-bottom: var(--spacing-8);
}

.price-qr-container {
  text-align: center;
  padding: var(--spacing-6);
  background: var(--bg-gray);
  border-radius: var(--radius-lg);
}

.price-qr-code {
  width: 150px;
  height: 150px;
  margin: 0 auto var(--spacing-3);
}

.price-qr-text {
  font-size: var(--text-sm);
  color: var(--text-tertiary);
}

.price-trust {
  display: flex;
  justify-content: center;
  gap: var(--spacing-6);
  padding-top: var(--spacing-6);
  border-top: 1px solid var(--border-light);
  font-size: var(--text-xs);
  color: var(--text-tertiary);
}

.price-trust-item {
  display: flex;
  align-items: center;
  gap: var(--spacing-2);
}
```

### 6. FAQ

```css
.faq {
  max-width: 800px;
  margin: 0 auto;
}

.faq-item {
  background: var(--bg-white);
  border: 1px solid var(--border-light);
  border-radius: var(--radius-md);
  margin-bottom: var(--spacing-3);
}

.faq-question {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: var(--spacing-5) var(--spacing-6);
  cursor: pointer;
  transition: all var(--transition-fast);
}

.faq-question:hover {
  background: var(--bg-gray);
}

.faq-question-text {
  font-size: var(--text-base);
  font-weight: var(--font-medium);
  color: var(--text-primary);
}

.faq-icon {
  font-size: var(--text-xl);
  color: var(--color-primary);
  transition: transform var(--transition-base);
  flex-shrink: 0;
  margin-left: var(--spacing-4);
}

.faq-item.active .faq-icon {
  transform: rotate(45deg);
}

.faq-answer {
  max-height: 0;
  overflow: hidden;
  transition: max-height var(--transition-base);
}

.faq-item.active .faq-answer {
  max-height: 300px;
}

.faq-answer-content {
  padding: 0 var(--spacing-6) var(--spacing-6);
  font-size: var(--text-sm);
  color: var(--text-secondary);
  line-height: var(--leading-relaxed);
}
```

### 7. 底部 CTA

```css
.bottom-cta {
  background: var(--bg-gradient-orange);
  padding: var(--spacing-20) var(--spacing-6);
  text-align: center;
  color: var(--text-inverse);
}

.bottom-cta-title {
  font-size: var(--text-4xl);
  font-weight: var(--font-bold);
  margin-bottom: var(--spacing-4);
}

.bottom-cta-subtitle {
  font-size: var(--text-xl);
  margin-bottom: var(--spacing-8);
  opacity: 0.9;
}

.bottom-cta-rating {
  font-size: var(--text-3xl);
  color: var(--color-rating);
  margin-bottom: var(--spacing-8);
}

.bottom-cta-button {
  background: var(--bg-white);
  color: var(--color-primary);
  padding: var(--spacing-5) var(--spacing-10);
  font-size: var(--text-xl);
  font-weight: var(--font-bold);
  border: none;
  border-radius: var(--radius-lg);
  cursor: pointer;
  transition: all var(--transition-base);
  margin-bottom: var(--spacing-4);
}

.bottom-cta-button:hover {
  transform: translateY(-2px);
  box-shadow: var(--shadow-2xl);
}

.bottom-cta-price {
  font-size: var(--text-base);
  margin-bottom: var(--spacing-6);
  opacity: 0.9;
}

.bottom-cta-countdown {
  font-size: var(--text-2xl);
  font-weight: var(--font-bold);
  margin-bottom: var(--spacing-8);
}

.bottom-cta-contacts {
  display: flex;
  justify-content: center;
  gap: var(--spacing-6);
}

.bottom-cta-contact {
  display: flex;
  align-items: center;
  gap: var(--spacing-2);
  font-size: var(--text-base);
  color: var(--text-inverse);
  text-decoration: none;
  opacity: 0.9;
  transition: opacity var(--transition-fast);
}

.bottom-cta-contact:hover {
  opacity: 1;
}
```

---

## 🎬 动画组件

### 1. 淡入动画

```css
.fade-in {
  opacity: 0;
  animation: fadeIn var(--transition-slow) forwards;
}

.fade-in-up {
  opacity: 0;
  transform: translateY(20px);
  animation: fadeInUp var(--transition-slow) forwards;
}

@keyframes fadeIn {
  to {
    opacity: 1;
  }
}

@keyframes fadeInUp {
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

/* 延迟类 */
.delay-100 { animation-delay: 100ms; }
.delay-200 { animation-delay: 200ms; }
.delay-300 { animation-delay: 300ms; }
.delay-400 { animation-delay: 400ms; }
.delay-500 { animation-delay: 500ms; }
```

### 2. 滚动动画

```css
.scroll-reveal {
  opacity: 0;
  transform: translateY(30px);
  transition: all 0.6s ease;
}

.scroll-reveal.visible {
  opacity: 1;
  transform: translateY(0);
}
```

### 3. 按钮波纹效果

```css
.btn-ripple {
  position: relative;
  overflow: hidden;
}

.btn-ripple::after {
  content: '';
  position: absolute;
  top: 50%;
  left: 50%;
  width: 0;
  height: 0;
  background: rgba(255, 255, 255, 0.3);
  border-radius: 50%;
  transform: translate(-50%, -50%);
  transition: width 0.6s, height 0.6s;
}

.btn-ripple:active::after {
  width: 300px;
  height: 300px;
}
```

---

## 📱 响应式工具类

```css
/* 显示控制 */
@media (max-width: 767px) {
  .hidden-mobile {
    display: none !important;
  }
}

@media (min-width: 768px) {
  .hidden-tablet-up {
    display: none !important;
  }
}

@media (max-width: 1023px) {
  .hidden-tablet-down {
    display: none !important;
  }
}

@media (min-width: 1024px) {
  .hidden-desktop {
    display: none !important;
  }
}

/* 文字对齐 */
.text-center-mobile {
  text-align: center;
}

@media (min-width: 768px) {
  .text-center-mobile {
    text-align: left;
  }
}

/* 间距调整 */
@media (max-width: 767px) {
  .section {
    padding: var(--spacing-10) 0;
  }
  
  .card-body {
    padding: var(--spacing-4);
  }
}
```

---

## 🔧 实用工具类

```css
/* 文字截断 */
.truncate {
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: nowrap;
}

.line-clamp-2 {
  display: -webkit-box;
  -webkit-line-clamp: 2;
  -webkit-box-orient: vertical;
  overflow: hidden;
}

.line-clamp-3 {
  display: -webkit-box;
  -webkit-line-clamp: 3;
  -webkit-box-orient: vertical;
  overflow: hidden;
}

/* 居中 */
.center {
  display: flex;
  align-items: center;
  justify-content: center;
}

/* 间距 */
.mt-8 { margin-top: var(--spacing-8); }
.mb-8 { margin-bottom: var(--spacing-8); }
.mx-auto { margin-left: auto; margin-right: auto; }

/* 尺寸 */
.w-full { width: 100%; }
.h-full { height: 100%; }
```

---

**CSS 库完成时间：** 2026-03-20 09:30 UTC  
**总耗时：** 10 分钟  
**状态：** ✅ 组件库规范完成
