# AICODE

> 新一代 AI 产品工作平台

AICODE 是一个面向 AI 产品与开发者的现代化产品官网原型。项目保持 **纯 HTML + CSS + 原生 JavaScript**，无前端框架、无 npm 依赖、无构建步骤，可直接部署到 GitHub Pages。

## ✨ 本次升级

- **AI Agent 交互工作台**：点击“运行”即可看到需求分析 → 构建 → 测试 → 部署的动态状态演示
- **更完整的产品官网结构**：Hero、AI 能力、数据指标、工作流、方案、FAQ、CTA
- **主题切换**：支持深色 / 浅色模式，并通过 LocalStorage 记住选择
- **中英文切换**：页面主要文案支持中文 / English，并记住用户选择
- **滚动入场动画**：使用原生 IntersectionObserver，无第三方动画库
- **响应式设计**：桌面、平板、手机均有适配
- **零依赖**：不需要 Node.js、npm、构建工具或第三方 UI 库
- **GitHub Pages 友好**：静态文件即可发布- **AI 工作台原型**：三栏项目 / Agent / 代码 / 任务界面，支持聊天、模型切换、代码 Tab 和新建项目
- **官网 + 工作台双模式**：保留 Landing Page，同时可进入产品工作区

> 注意：AI Agent 工作台目前是前端交互原型，不会调用真实 AI API。要变成真正的 AI 产品，需要继续接入后端、模型 API、认证和任务执行服务。

## 📁 项目结构

```text
.
├── index.html    # 官网全部页面、CSS 与原生 JavaScript
└── README.md     # 项目说明
```

当前仍然刻意保持单文件结构，方便 GitHub Pages 快速部署和原型迭代。

## 🚀 本地运行

项目没有构建步骤，可以直接使用任意静态 HTTP 服务：

```bash
python3 -m http.server 8000
```

然后打开：

```text
http://localhost:8000
```

也可以直接用浏览器打开 `index.html`。

## 🌐 在线访问

GitHub Pages：

https://aicode915.github.io/

项目仓库：

https://github.com/aicode915/aicode915.github.io

## 🛠️ 主要功能

### 1. AI Agent Demo

Hero 区域内置一个可运行的 Agent 工作台：

1. 分析产品需求与技术方案
2. 生成页面与交互逻辑
3. 运行自动化测试
4. 准备部署到生产环境

这是纯前端状态机演示，适合后续替换为真实 API / WebSocket / SSE 数据流。

### 2. 主题切换

右上角按钮可以切换深色 / 浅色主题。选择会保存到浏览器 LocalStorage。

### 3. 中英文切换

右上角语言按钮可以在中文和 English 之间切换，主要页面文案会同步更新。

### 4. FAQ

FAQ 使用原生 JavaScript 实现折叠展开，没有依赖任何组件库。

### 5. 响应式与动画### 6. AI 工作台

页面新增一个产品工作台原型，包含项目列表、AI Agent 聊天、模型选择器、HTML/CSS/JS 代码编辑区和任务状态面板。所有行为均由原生 JavaScript 模拟，不调用真实 AI 服务。

工作台可通过官网导航或 Hero 按钮进入，并提供返回官网入口。

### 7. 后续接入真实 AI

工作台当前的数据流是本地前端状态。接入真实产品时，可以将聊天发送、Agent 任务、代码生成和任务状态替换成 API、SSE 或 WebSocket。

页面使用 CSS Grid / Flexbox、媒体查询和 IntersectionObserver，适配移动端并提供轻量滚动入场效果。

## 🧩 第三阶段：Product Studio\n\n- Dashboard / Project Detail / Agent Logs 三种视图\n- 本地项目与文件内容使用浏览器 LocalStorage 持久化\n- 文件树、代码编辑器与 iframe Preview 联动\n- Agent 执行日志为前端模拟，可后续替换为真实 SSE / WebSocket\n- 仍然无需数据库、后端、npm 或第三方依赖\n\n> GitHub Pages 可以承载这一整套前端产品体验；真正的账号、跨设备数据、AI API 密钥和服务器端 Agent 执行，需要后端或第三方服务。\n\n## 🔮 下一阶段建议

如果准备把这个官网继续发展成真正的 AI SaaS，建议按以下顺序演进：

1. **前端组件化**：React / Vue / Svelte 三选一
2. **后端 API**：用户、项目、任务、模型调用等服务
3. **身份认证**：登录、注册、OAuth、团队权限
4. **模型网关**：统一管理不同 LLM Provider
5. **实时任务系统**：SSE / WebSocket 展示 Agent 执行过程
6. **数据库**：项目、知识库、会话、计费数据
7. **真实部署链路**：GitHub / CI/CD / 云平台
8. **可观测性**：日志、错误追踪、Token / 成本统计

## 📦 部署到 GitHub Pages

修改完成后：

```bash
git add .
git commit -m "feat: upgrade AICODE landing page"
git push origin main
```

如果仓库已经启用 GitHub Pages，推送到 `main` 后 GitHub 会自动更新网站。

## 📄 License

本项目用于网站展示与产品原型开发，可根据实际项目需求自行调整。
