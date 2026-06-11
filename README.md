# 飞鲤的自留地 - 个人主页

> Building a Personal Operating System for the AI Era

一个现代化的个人主页，展示我的技能、项目和思考。

## ✨ 特性

- 🎨 **现代化设计** - 使用 Tailwind CSS 构建，支持深色/浅色模式
- ⚡ **高性能** - 基于 Vite 构建，快速加载
- 📱 **响应式** - 完美适配各种设备
- 🎭 **动画效果** - 打字机效果、滚动动画等
- 🔧 **易于定制** - 模块化组件，方便修改
- 🚀 **自动部署** - GitHub Actions 自动部署到 GitHub Pages

## 🛠️ 技术栈

- **前端框架**: Vue 3 + TypeScript
- **构建工具**: Vite
- **样式方案**: Tailwind CSS
- **部署平台**: GitHub Pages

## 📦 安装

```bash
# 克隆项目
git clone https://github.com/your-username/personal-homepage.git

# 进入项目目录
cd personal-homepage

# 安装依赖
npm install
```

## 🚀 开发

```bash
# 启动开发服务器
npm run dev

# 构建生产版本
npm run build

# 预览生产版本
npm run preview
```

## 📁 项目结构

```
src/
├── components/
│   ├── layout/          # 布局组件
│   │   ├── Navbar.vue   # 导航栏
│   │   └── Footer.vue   # 页脚
│   └── sections/        # 页面区块
│       ├── Hero.vue     # 首屏
│       ├── About.vue    # 关于我
│       ├── Focus.vue    # 当前聚焦
│       ├── Toolbox.vue  # 工具箱
│       ├── Articles.vue # 文章
│       ├── GrowthLoop.vue # 成长循环
│       └── Contact.vue  # 联系方式
├── App.vue              # 根组件
├── main.ts              # 入口文件
└── style.css            # 全局样式
```

## 🎨 自定义

### 修改个人信息

1. **编辑 Hero.vue** - 修改首屏的标题、副标题和标签
2. **编辑 About.vue** - 修改个人介绍和核心理念
3. **编辑 Focus.vue** - 修改当前聚焦的领域
4. **编辑 Toolbox.vue** - 修改工具箱内容
5. **编辑 Articles.vue** - 修改文章列表
6. **编辑 Contact.vue** - 修改联系方式

### 修改样式

- 编辑 `src/style.css` 修改全局样式
- 使用 Tailwind CSS 类名快速调整样式

### 修改主题

- 在 `src/App.vue` 中修改主题切换逻辑
- 在 `src/style.css` 中修改 CSS 变量

## 🚀 部署

### GitHub Pages

1. 推送代码到 GitHub
2. 在仓库设置中启用 GitHub Pages
3. 选择 `gh-pages` 分支作为源
4. 访问 `https://your-username.github.io/personal-homepage`

### 自定义域名

1. 在 `public` 目录下创建 `CNAME` 文件
2. 添加你的域名，例如：`nav.v-li.com`
3. 在域名 DNS 设置中添加 CNAME 记录

## 📝 许可证

MIT License

## 🙏 致谢

- [Vue.js](https://vuejs.org/)
- [Vite](https://vitejs.dev/)
- [Tailwind CSS](https://tailwindcss.com/)
- [GitHub Pages](https://pages.github.com/)

---

**飞鲤的自留地** - Building a Personal Operating System for the AI Era
