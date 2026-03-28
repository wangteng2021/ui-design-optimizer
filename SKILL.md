# UI Design Optimizer

## 概述

消除 AI 生成前端的"AI 味"，生成专业、独特、有品牌特色的前端界面。采用 Anthropic 官方前端美学指南 + 15 个常见错误修复策略。

## 激活条件

当用户提及以下关键词时自动激活：
- UI 设计
- 前端美化
- 去除 AI 味
- AI slop
- 界面优化
- 前端美学
- 排版设计
- 配色方案
- 动画效果
- 字体选择
- Tailwind
- 组件库
- shadcn/ui
- 玻璃拟态
- 暗色主题

---

## 核心原则：AI 味是怎么产生的

AI 默认生成的设计特点：
- ❌ 使用通用字体 (Inter, Roboto, Arial)
- ❌ 紫色渐变白色背景
- ❌ 可预测的布局和组件
- ❌ 缺乏上下文特色的模板式设计
- ❌ 保守的颜色方案
- ❌ 缺乏层次感的间距

---

## 模块一：排版 Typography (字体设计)

### 1.1 必须避免的字体

```markdown
# ❌ 永远不要使用
- Inter (最常见)
- Roboto
- Open Sans
- Lato
- System fonts (默认)
```

### 1.2 推荐字体选择

| 风格 | 推荐字体 | 来源 |
|------|----------|------|
| 代码风格 | JetBrains Mono, Fira Code, Space Grotesk | Google Fonts |
| 编辑风格 | Playfair Display, Crimson Pro, Fraunces | Google Fonts |
| 创业风格 | Clash Display, Satoshi, Cabinet Grotesk | Custom |
| 技术风格 | IBM Plex family, Source Sans 3 | Google Fonts |
| 独特风格 | Bricolage Grotesque, Obviously, Newsreader | Google Fonts |

### 1.3 字体配对原则

```markdown
# 配对原则：高对比度
- 展示字体 + 等宽字体
- 衬线体 + 几何无衬线
- 同一字体的不同粗细

# 使用极端值
- 100/200 极细 vs 800/900 极粗 (不是 400 vs 600)
- 字号跳跃 3倍以上 (不是 1.5倍)
```

### 1.4 字体使用示例

```css
/* ✅ Good: 独特字体选择 */
font-family: 'Clash Display', sans-serif;
font-family: 'JetBrains Mono', monospace;

/* ❌ Bad: 通用字体 */
font-family: 'Inter', sans-serif;
font-family: 'Roboto', sans-serif;
```

---

## 模块二：颜色与主题 Color & Theme

### 2.1 必须避免的配色

```markdown
# ❌ 永远不要使用
- 紫色渐变白色背景 (最常见)
- 蓝色按钮 + 白色背景
- 灰色文字在白色背景
- 过于均匀分布的颜色
```

### 2.2 正确的配色策略

```markdown
# 核心原则：主色 + 锐利点缀
- 主色调 + 突出点缀色 > 平淡均匀的配色
- 从 IDE 主题和文化美学中汲取灵感

# 配色来源参考
- IDE 主题: VS Code, Zed, Arc
- 文化美学: 赛博朋克, 蒸汽朋克, 极简主义
```

### 2.3 配色模板

```css
/* ✅ 暗色高级风 */
--primary: #6366f1;        /* 靛蓝 */
--background: #0a0a0a;      /* 近黑 */
--surface: #171717;         /* 卡片 */
--accent: #22c55e;          /* 绿色点缀 */
--text: #fafafa;            /* 白 */

/* ✅ 温暖大地色 */
--primary: #d97706;         /* 琥珀 */
--background: #fef3c7;      /* 奶油白 */
--surface: #ffffff;
--accent: #059669;          /* 翡翠绿 */
--text: #292524;

/* ✅ 赛博朋克 */
--primary: #f472b6;         /* 粉色 */
--background: #0f172a;      /* 深蓝黑 */
--surface: #1e293b;
--accent: #22d3ee;          /* 青色 */
--text: #f8fafc;
```

### 2.4 CSS 变量一致性

```css
:root {
  /* 主色调 */
  --color-primary: #6366f1;
  --color-primary-hover: #4f46e5;
  
  /* 背景 */
  --color-bg: #0a0a0a;
  --color-surface: #171717;
  --color-surface-hover: #262626;
  
  /* 文字 */
  --color-text-primary: #fafafa;
  --color-text-secondary: #a1a1aa;
  --color-text-muted: #71717a;
  
  /* 状态 */
  --color-success: #22c55e;
  --color-warning: #f59e0b;
  --color-error: #ef4444;
}
```

---

## 模块三：动画 Motion

### 3.1 动画原则

```markdown
# 核心原则
- 使用 CSS-only 方案优先 (HTML)
- React 项目使用 Motion 库
- 聚焦高光时刻：一个精心编排的页面加载 > 零散的微交互

# 关键时机
- 页面加载：交错揭示动画 (staggered reveals)
- 悬停效果：平滑过渡
- 状态切换：淡入淡出
```

### 3.2 动画示例

```css
/* ✅ 交错揭示动画 */
.card {
  animation: fadeInUp 0.5s ease-out forwards;
  opacity: 0;
}

.card:nth-child(1) { animation-delay: 0.1s; }
.card:nth-child(2) { animation-delay: 0.2s; }
.card:nth-child(3) { animation-delay: 0.3s; }

@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

/* ✅ 悬停效果 */
.button {
  transition: all 0.2s ease;
}

.button:hover {
  transform: translateY(-2px);
  box-shadow: 0 4px 12px rgba(99, 102, 241, 0.3);
}
```

### 3.3 推荐的动画库

| 框架 | 库 | 用途 |
|------|-----|------|
| React | Framer Motion | 复杂动画 |
| React | Motion One | 轻量级 |
| Vue | VueUse/Motion | Vue 动画 |
| 通用 | CSS animations | 基础动画 |

---

## 模块四：背景 Background

### 4.1 必须避免的背景

```markdown
# ❌ 永远不要使用
- 纯色白色背景
- 简单的单色渐变
- 无聊的空白
```

### 4.2 背景设计策略

```markdown
# 创造氛围和深度
- 层叠 CSS 渐变
- 几何图案
- 符合整体美学的上下文效果
```

### 4.3 背景示例

```css
/* ✅ 渐变叠加 */
.background {
  background: 
    radial-gradient(ellipse at top, rgba(99, 102, 241, 0.15) 0%, transparent 50%),
    radial-gradient(ellipse at bottom right, rgba(236, 72, 153, 0.1) 0%, transparent 50%),
    linear-gradient(180deg, #0a0a0a 0%, #171717 100%);
}

/* ✅ 几何图案 */
.background-pattern {
  background-color: #0a0a0a;
  background-image: 
    radial-gradient(circle at 25% 25%, rgba(99, 102, 241, 0.1) 0%, transparent 50%),
    radial-gradient(circle at 75% 75%, rgba(236, 72, 153, 0.08) 0%, transparent 50%);
}

/* ✅ 玻璃拟态 */
.glass {
  background: rgba(255, 255, 255, 0.05);
  backdrop-filter: blur(12px);
  border: 1px solid rgba(255, 255, 255, 0.1);
}
```

---

## 模块五：15 个常见错误与修复

### Mistake 1: 使用"Clean and Modern"描述

```markdown
# ❌ Bad
"Design a clean, modern mobile app dashboard"

# ✅ Good
"Design an iOS fitness app dashboard with dark premium theme — 
near-black background (#0a0a0a), subtle gradients on metric cards, 
mint green (#4ade80) accent color."
```

### Mistake 2: 不指定平台

```markdown
# ❌ Bad
"Design a mobile app login screen"

# ✅ Good
"Design an iOS app login screen with tab bars, large titles, SF Pro font"
```

### Mistake 3: 一次性要求整个应用

```markdown
# ❌ Bad
"Design a social media app with feed, profiles, messaging, stories..."

# ✅ Good (一次一个屏幕)
"Design an iOS social media feed screen first. Then follow up with profile screen."
```

### Mistake 4: 缺少用户上下文

```markdown
# ❌ Bad
"Design a dashboard"

# ✅ Good
"Design a dashboard for a freelance graphic designer tracking projects, 
deadlines, invoices, and monthly revenue."
```

### Mistake 5: 忽略空状态/加载状态

```markdown
# 必须包含
- "Show empty state for new users"
- "Show loading skeleton"
- "Show error state"
```

### Mistake 6: 使用占位符文本

```markdown
# ❌ Bad
"Design a banking transaction list"

# ✅ Good
"Design a banking transaction list showing: 
Whole Foods Market $67.23, Netflix $15.99, Uber $24.50"
```

### Mistake 7: 未指定颜色

```markdown
# ❌ Bad
"Design with nice colors"

# ✅ Good
"Primary color #6366f1, background #fafafa"
```

### Mistake 8: 忽略排版层次

```markdown
# 必须指定
- 字体族
- 标题/正文粗细
- 字号层次
```

### Mistake 9: 屏幕功能过多

```markdown
# 遵循"一屏一主操作"原则
- 识别用户最常用的操作
- 让它占主导地位
- 次要操作放到标签页/菜单
```

### Mistake 10: 未指定间距

```markdown
# ❌ Bad
"Design a settings page"

# ✅ Good
"Design a settings page with 24px between sections, 
16px horizontal margins, 12px between items"
```

### Mistake 11: 未提供视觉参考

```markdown
# 参考真实应用
"Layout similar to Spotify's home screen"
"Card style like Linear's issue cards"
```

### Mistake 12: 接受第一次输出

```markdown
# 迭代优化
1. 第一轮：基础布局
2. 第二轮：样式优化
3. 第三轮：细节完善
```

### Mistake 13: 多屏幕设计不一致

```markdown
# 保持一致
"Use the same theme as before: 
primary color #6366f1, background #0a0a0a"
```

### Mistake 14: 忽略可访问性

```markdown
# 添加无障碍要求
"Ensure WCAG AA compliance with 4.5:1 contrast ratio"
```

### Mistake 15: 未使用组件库

```markdown
# 引用组件库
"Use shadcn/ui components"
"Use Material Design 3 components"
```

---

## 模块六：设计风格参考

### 6.1 玻璃拟态 Glassmorphism

```css
.glassmorphism {
  background: rgba(255, 255, 255, 0.1);
  backdrop-filter: blur(20px);
  border: 1px solid rgba(255, 255, 255, 0.2);
  border-radius: 16px;
}
```

### 6.2 新拟态 Neobrutalism

```css
.neobrutalism {
  border: 3px solid #000;
  border-radius: 0;
  box-shadow: 4px 4px 0 #000;
  background: #fef3c7;
}
```

### 6.3 极简 with 慷慨留白

```css
.minimal {
  max-width: 680px;
  margin: 0 auto;
  padding: 80px 24px;
  line-height: 1.8;
}
```

### 6.4 iOS Native

```css
.ios-native {
  font-family: -apple-system, BlinkMacSystemFont, 'SF Pro Display', sans-serif;
  -webkit-font-smoothing: antialiased;
}
```

### 6.5 Material Design 3

```css
.material {
  border-radius: 16px;
  elevation: 2;
  background: var(--md-sys-color-surface);
}
```

### 6.6 暗色高级 Dark Premium

```css
.dark-premium {
  background: #0a0a0a;
  color: #fafafa;
  accent: #a855f7;
}
```

---

## 模块七：组件库使用

### 7.1 推荐组件库

| 平台 | 组件库 |
|------|--------|
| Web | shadcn/ui, Radix UI, Tailwind UI |
| React | shadcn/ui, Mantine, Chakra UI |
| Vue | Naive UI, Element Plus, Vuetify |
| Mobile | SwiftUI, Jetpack Compose |

### 7.2 shadcn/ui 使用

```tsx
import { Button } from "@/components/ui/button"
import { Card } from "@/components/ui/card"
import { Input } from "@/components/ui/input"

/* 使用示例 */
<Card className="p-6">
  <h2 className="text-lg font-semibold">Welcome</h2>
  <p className="text-muted-foreground">Get started</p>
  <Button>Click me</Button>
</Card>
```

---

## 模块八：响应式设计

### 8.1 移动优先

```css
/* 默认移动端 */
.container {
  padding: 16px;
}

/* 平板 */
@media (min-width: 768px) {
  .container {
    padding: 24px;
  }
}

/* 桌面 */
@media (min-width: 1024px) {
  .container {
    padding: 32px;
    max-width: 1200px;
  }
}
```

### 8.2 间距系统

```css
/* 8pt 网格系统 */
.space-1 { padding: 4px; }
.space-2 { padding: 8px; }
.space-3 { padding: 12px; }
.space-4 { padding: 16px; }
.space-6 { padding: 24px; }
.space-8 { padding: 32px; }
.space-12 { padding: 48px; }
```

---

## 输出格式示例

### UI 优化建议

```
🎨 UI 优化建议

## 1. 排版问题
❌ 当前使用: Inter 字体
✅ 建议使用: Clash Display 或 Space Grotesk

## 2. 配色问题
❌ 当前: 白色背景 + 紫色渐变
✅ 建议: 深色背景 (#0a0a0a) + 青色点缀 (#22d3ee)

## 3. 动画缺失
❌ 当前: 无动画
✅ 建议: 页面加载添加交错揭示动画

## 4. 背景单调
❌ 当前: 纯白背景
✅ 建议: 添加渐变叠加 + 几何图案

## 5. 组件建议
- 使用 shadcn/ui 组件
- 采用玻璃拟态卡片
- 添加微妙边框
```

---

## 使用示例

### 示例 1: 优化现有 UI
```
用户: 优化这个登录页面，看起来太"AI 味"了
Skill: 分析现有代码，提供具体优化建议
```

### 示例 2: 从头设计
```
用户: 设计一个 SaaS 仪表板
Skill: 应用美学原则生成专业设计
```

### 示例 3: 主题一致
```
用户: 保持和首页一致的主题设计详情页
Skill: 提取主题配置，确保多页面一致
```

### 示例 4: 修复特定问题
```
用户: 按钮看起来太普通
Skill: 提供按钮样式优化建议和代码
```

---

## 关键原则总结

1. **避免通用选择** - 不要 Inter、Roboto、紫色渐变
2. **指定具体风格** - 不要说"clean and modern"
3. **提供上下文** - 用户、平台、目的
4. **迭代优化** - 3轮迭代优于1次输出
5. **保持一致性** - 多页面使用相同主题
6. **关注细节** - 空状态、加载状态、错误状态
7. **注重可访问性** - WCAG 对比度要求

---

## 参考资源

- Anthropic Frontend Aesthetics Guide
- GenDesigns AI UI Mistakes
- shadcn/ui 组件库
- Google Fonts
- Tailwind CSS