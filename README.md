# UI Design Optimizer

Claude Code Skill - 消除 AI 生成前端的"AI 味"

---

## 核心理念

AI 默认生成的设计往往平淡无奇、缺乏特色。本 Skill 帮助生成专业、独特、有品牌特色的前端界面。

## 功能概览

| 模块 | 功能 | 描述 |
|------|------|------|
| 排版 | Typography | 字体选择、配对原则 |
| 颜色 | Color & Theme | 配色方案、CSS 变量 |
| 动画 | Motion | 页面加载、交互效果 |
| 背景 | Background | 渐变、图案、玻璃拟态 |
| 错误修复 | 15 Mistakes | 常见错误与修复方案 |
| 设计风格 | Styles | 玻璃拟态、Neobrutalism 等 |
| 组件库 | Components | shadcn/ui、Tailwind |
| 响应式 | Responsive | 移动优先、间距系统 |

---

## 核心原则

### ❌ AI 味的特征
- Inter/Roboto/Arial 字体
- 紫色渐变白色背景
- 保守的蓝色配色
- 缺乏层次感的间距

### ✅ 专业设计的特征
- 独特字体选择 (Clash Display, JetBrains Mono)
- 暗色主题 + 锐利点缀色
- CSS 渐变背景
- 交错动画效果

---

## 15 个常见错误与修复

| # | 错误 | 修复 |
|---|------|------|
| 1 | 使用"Clean and Modern" | 指定具体风格 |
| 2 | 不指定平台 | iOS/Android/Web |
| 3 | 一次性要求整个应用 | 一次一个屏幕 |
| 4 | 缺少用户上下文 | 添加用户场景 |
| 5 | 忽略空/加载状态 | 包含所有状态 |
| 6 | 使用占位符文本 | 真实数据 |
| 7 | 未指定颜色 | Hex 代码 |
| 8 | 忽略排版层次 | 指定字体层级 |
| 9 | 屏幕功能过多 | 一屏一主操作 |
| 10 | 未指定间距 | 8pt 网格 |
| 11 | 未提供视觉参考 | 参考真实应用 |
| 12 | 接受第一次输出 | 迭代优化 |
| 13 | 多屏幕不一致 | 保持主题一致 |
| 14 | 忽略可访问性 | WCAG AA |
| 15 | 未使用组件库 | shadcn/ui |

---

## 使用示例

```
/ui 优化这个登录页面
/ui 设计一个 SaaS 仪表板
/ui 暗色主题配色方案
/ui 修复按钮样式
```

---

## 参考资源

- Anthropic Frontend Aesthetics Guide
- GenDesigns AI UI Mistakes
- shadcn/ui 组件库
- Google Fonts

---

## License

MIT