# FlyLi Personal OS Homepage - AI 生成 Prompt

> 这是一个完整的项目 Prompt，用于指导 AI 生成 Dribbble 展示级别的个人主页。

---

## 项目名称

FlyLi Personal OS Homepage

## 项目定位

这是一个独立个人主页，而不是博客首页、作品集网站或商业 Landing Page。

目标是打造：

> Apple × Linear × Arc Browser × Raycast × Read.cv × Digital Garden

的视觉风格。

整个网站应该像一本正在缓慢生长的数字花园，而不是一个 AI 博主官网。

关键词：

* 大量留白
* 超大字体
* Glassmorphism
* Bento Grid
* 沉浸式
* 柔和动画
* 高级感
* 不对称布局
* Apple 风格滚动体验

---

## 技术栈

使用：

* Next.js 15
* React 19
* TypeScript
* Tailwind CSS v4
* Framer Motion
* Lucide React
* Canvas API
* SVG
* next-themes

不要使用：

* Bootstrap
* Material UI
* Ant Design

---

## 配色

### 浅色模式

```css
background: #f6f7fb
card: rgba(255, 255, 255, .7)
border: rgba(255, 255, 255, .4)
text: #111
secondary: #666
accent: #22c55e
```

### 深色模式

```css
background: #0b0d12
card: rgba(255, 255, 255, .06)
border: rgba(255, 255, 255, .08)
text: #fff
secondary: #999
accent: #4ade80
```

自动检测系统主题。支持手动切换。切换时有平滑动画。

---

## 全局设计系统

```css
圆角: 40px
阴影: 0 20px 60px rgba(0, 0, 0, .08)
模糊: backdrop-filter: blur(40px)
风格: Glassmorphism
```

---

## 页面结构

```
Hero
↓
About
↓
Current Focus
↓
Digital Garden
↓
Principles
↓
Philosophy
↓
Contact
↓
Footer
```

页面总长度控制在 6~7 屏。

---

## Hero

高度：100vh

左右布局

### 左侧

```
飞鲤
AI时代的个人操作系统实践者
研究 AI · 构建系统 · 记录思考
```

按钮：
- 探索数字花园
- Github

### 右侧

动态知识网络。节点：

- AI Agent
- Memory & MCP
- Context Engineering
- Enterprise AI
- Data Intelligence
- Knowledge Management
- Future of Work

### Hero 特效

**Canvas 粒子系统**

类似 Linear 官网。粒子缓慢漂浮。有连线。支持 Retina。60fps。

**Mouse Glow**

鼠标移动时出现柔和光晕。`mix-blend-mode: screen`。blur 120px。不影响性能。

**Parallax**

知识节点不同速度漂浮。使用 Framer Motion。

---

## About

杂志风布局。不要卡片。最大宽度：760px。字体：24px。行高：2。

滚动进入时：
- opacity: 0 → 1
- y: 40 → 0

使用 Framer Motion。

---

## Current Focus

使用 Bento Grid。

### 布局

```
┌────────────┬──────┐
│ AI Agent   │Memory│
│ (最大卡)   │ MCP  │
├────────────┼──────┤
│ Enterprise │ Data │
│ AI         │      │
├────────────┴──────┤
│ Context Engineering│
│ (横向大卡)         │
└───────────────────┘
```

### 卡片样式

- Glassmorphism
- 圆角：40px
- Hover：translateY(-10px) + box-shadow 增强

---

## Digital Garden

这是整个网站最重要的部分。

不要成长飞轮。不要普通流程图。

使用 SVG 贝塞尔曲线，形成一条河流。

### 节点

阅读 → 理解 → 思考 → 记录 → 输出 → 分享 → 沉淀

### 视觉效果

- 节点是发光圆点
- 连接线有渐变
- 线条缓慢流动
- 滚动时：河流产生视差
- 节点有上下浮动动画

参考：Apple 地图路径、Obsidian Graph

---

## Principles

四张超大引用卡。

### 内容

1. 真正重要的事情，需要时间积累。
2. 回到问题本身，而不是停留在经验。
3. AI 的价值，在于放大人的能力。
4. 保持好奇心，持续进化。

### 布局

2×2。卡片高度不一致。形成杂志风。

---

## Philosophy

整屏。100vh。沉浸式。

### 背景

动态星空。缓慢移动。

### 内容

```
技术变化很快。
原则会不断复利。
系统能够穿越时间。
```

字体：90px。超大字。

滚动时：逐字淡入。类似 Apple WWDC。

### 下方

```
构建系统 · 分享思考 · 持续学习
```

---

## Contact

极简。居中。

### 内容

```
感谢你的到来。
如果这里的内容对你有所启发，欢迎交流。
```

### 链接

- 邮箱：hcshi@outlook.com
- Github
- RSS
- 微信公众号

---

## 动画规范

统一使用 Framer Motion。

### 进入动画

```javascript
opacity: 0 → 1
y: 40 → 0
duration: 0.8
easing: easeOut
```

### Hover

```javascript
scale: 1.03
```

### 滚动

Parallax

### 禁止

- 夸张动画
- bounce

整体动画应该像：Apple + Linear

---

## 最终要求

- 代码结构清晰
- 组件化
- 支持：桌面端、平板、移动端
- 保证整体达到：Dribbble 展示级别

---

## 关键提醒

> **不要生成"程序员作品集网站"风格，不要生成 SaaS Landing Page 风格，不要生成 AI 博主模板风格。整个网站应该像一本正在缓慢生长的数字花园，具有 Apple、Linear 和 Arc Browser 的高级感。**

这一句的重要性甚至超过技术栈。因为真正决定最终效果的，不是 Tailwind，而是设计语言。

---

## 组件拆分

```
Hero.tsx
About.tsx
Focus.tsx
DigitalGarden.tsx
Principles.tsx
Philosophy.tsx
Contact.tsx
ParticleBackground.tsx
MouseGlow.tsx
ThemeSwitcher.tsx
```
