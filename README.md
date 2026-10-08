# AICODE

> 新一代 AI 产品工作平台 / AI Product Studio

AICODE 是一个面向 AI 产品与开发者的现代化产品工作平台原型。当前版本已经从单纯的 Landing Page 升级为 **官网 + AI Workspace + Product Studio** 三合一体验，并保持 **纯 HTML + CSS + 原生 JavaScript**：无 React / Vue、无 npm 依赖、无构建步骤，可直接部署到 GitHub Pages。

## ✨ 当前版本

### 1. 产品官网 Landing Page

- **完整产品官网**：Hero、AI 能力、数据指标、工作流、方案、FAQ、CTA
- **主题切换**：深色 / 浅色，并使用 LocalStorage 记住选择
- **中英文切换**：中文 / English，并使用 LocalStorage 记住选择
- **滚动动画**：原生 IntersectionObserver
- **响应式布局**：桌面、平板、手机适配
- **Agent Demo**：需求分析 → 构建 → 测试 → 部署

### 2. AI Workspace

进入官网的“工作台 / Workspace”后，可以体验一个产品化的 AI coding workspace：
- 项目列表与项目切换
- AI Agent 对话区
- AICODE Fast / Reasoning / Code 模型选择器
- HTML / CSS / JS 代码 Tab
- Agent 状态与任务面板
- 新建项目、返回官网
- 前端模拟 Agent 响应，不调用真实模型 API

### 3. Product Studio

Product Studio 是当前项目的核心产品原型，提供从项目管理到代码预览的一体化体验：
- **Dashboard**：项目数量、Agent Run、文件数量等概览
- **Project Detail**：项目名称、路径、文件树、代码编辑器
- **Preview**：通过 iframe + srcdoc 实时预览项目页面
- **Agent Logs**：Plan → Build → Test → Ship 执行时间线
- **Local-first persistence**：项目、文件和编辑结果保存在浏览器 LocalStorage
- **New Project / Reset Demo**：支持本地创建项目和恢复演示数据
- 示例项目包含 index.html、style.css、app.js、README.md

## 🧱 技术架构

当前版本刻意采用最简单的静态架构：

```text
GitHub Pages
│
├── Landing Page
├── AI Workspace
├── Product Studio
│   ├── Dashboard
│   ├── Project Detail
│   └── Agent Logs
│
└── Browser LocalStorage
    ├── Theme
    ├── Language
    └── Studio Projects / Files
```

### 为什么现在不需要数据库？

因为当前目标是先把完整的产品体验跑通。GitHub Pages 负责静态资源托管，浏览器 LocalStorage 负责 Demo 数据持久化，因此：
- 不需要服务器
- 不需要数据库
- 不需要 Node.js / npm
- 不需要 API Key
- 不需要 CI 构建服务

但这是一套 **local-first 产品原型架构**，不是完整的多用户 SaaS 后端。

## ⚠️ 当前边界

以下能力目前仍是前端模拟或本地能力：
- AI Agent：模拟执行，不调用真实 LLM
- 登录 / 注册：尚未接入
- 跨设备同步：不支持
- 多用户协作：不支持
- 服务端项目存储：不支持
- 安全保存 AI API Key：不支持
- 真正的代码执行、测试与部署：尚未接入服务器

如果要升级为真正的 AI SaaS，需要在现有前端之上增加后端 API、认证、数据库、模型网关和 Agent Runtime。

## 📁 项目结构

```text
.
├── index.html    # 官网、Workspace、Product Studio、CSS 与原生 JavaScript
└── README.md     # 项目说明与架构文档
```

当前继续保持单文件结构，目的是降低部署和迭代成本。后续进入正式产品开发阶段，再考虑拆分组件与模块。

## 🚀 本地运行

项目没有构建步骤，可以直接使用任意静态 HTTP 服务：

```bash
python3 -m http.server 8000
```

然后打开：

```text
http://localhost:8000
```

也可以直接用浏览器打开 index.html。

## 🌐 在线访问

GitHub Pages：
https://aicode915.github.io/

项目仓库：
https://github.com/aicode915/aicode915.github.io

## 🛠️ 主要交互说明

### Agent Demo

首页 Agent Demo 通过原生 JavaScript 定时器模拟任务状态变化，展示：
1. 分析需求与技术方案
2. 生成产品界面
3. 运行测试
4. 准备部署

### Workspace

Workspace 将项目、Agent、代码和任务状态集中到同一个界面，适合后续接入真实聊天 API、SSE 或 WebSocket。

### Product Studio

Product Studio 的核心数据模型类似：

```text
Project
├── name
└── files
    ├── index.html
    ├── style.css
    ├── app.js
    └── README.md
```

项目数据默认保存在：

```text
aicode-studio-projects
```

这是浏览器 LocalStorage 的 key。刷新页面后，当前浏览器中的项目数据仍可恢复。

## 🔮 下一阶段建议

如果准备继续把 AICODE 发展成真正的 AI SaaS，推荐按这个顺序演进：
1. **前端组件化**：将单文件原型拆成 React / Vue / Svelte 等组件
2. **真实 AI API**：聊天、代码生成、Agent Planning 接入模型服务
3. **Agent Runtime**：增加任务队列、工具调用、代码执行与测试沙箱
4. **后端 API**：用户、项目、文件、任务、Agent Run 等服务
5. **身份认证**：登录、OAuth、团队与权限体系
6. **数据库**：项目、会话、知识库、计费与审计数据
7. **实时通信**：使用 SSE / WebSocket 推送 Agent 执行日志
8. **部署链路**：GitHub / CI/CD / 云平台自动部署
9. **可观测性**：日志、错误追踪、Token、成本与任务成功率

届时可以继续保留 GitHub Pages 作为前端入口，把后端能力独立部署，不需要推翻当前 UI 和产品结构。

## 📦 部署到 GitHub Pages

修改完成后：

```bash
git add .
git commit -m "feat: upgrade AICODE"
git push origin main
```

如果仓库已经启用 GitHub Pages，推送到 main 后 GitHub 会自动更新网站。

## 📄 License

本项目用于网站展示与产品原型开发，可根据实际项目需求自行调整。