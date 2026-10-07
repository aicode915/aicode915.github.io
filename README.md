# AICODE

> 新一代 AI 产品工作平台

AICODE 是一个面向 AI 产品与开发者的现代化产品官网示例。项目采用纯 HTML + CSS 构建，无需前端框架和第三方依赖，可直接部署到 GitHub Pages。

## ✨ 项目特点

- **现代化 AI 产品视觉**：深色背景、渐变光效、玻璃拟态与响应式布局
- **AI Agent 展示**：模拟需求分析、代码生成、测试和部署的完整工作流
- **能力展示**：AI Agent、智能编程、知识增强、自动化工作流、多模型协同、极速部署
- **响应式设计**：适配桌面、平板和移动端
- **零依赖**：纯 HTML / CSS，无需 Node.js、构建工具或第三方 UI 库
- **GitHub Pages 友好**：提交代码后即可通过 GitHub Pages 发布

## 📁 项目结构

```text
.
├── index.html    # 官网首页，包含页面结构与全部样式
└── README.md     # 项目说明
```

## 🚀 本地运行

由于项目没有构建步骤，可以直接使用任意静态 HTTP 服务运行。

例如：

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

## 🛠️ 修改网站

网站主要内容都在 `index.html` 中：

1. 修改 Hero 区域，可以调整品牌介绍、标题和 CTA。
2. 修改 `#features`，可以增加或删除 AI 产品能力。
3. 修改 `#workflow`，可以调整产品工作流。
4. 修改 `#start`，可以替换最终 CTA 和项目链接。
5. 修改 `<style>` 中的 CSS，可以调整颜色、字体、间距和响应式效果。

## 📦 部署到 GitHub Pages

修改完成后：

```bash
git add .
git commit -m "feat: update website"
git push origin main
```

如果仓库已经启用 GitHub Pages，推送到 `main` 后 GitHub 会自动更新网站。

## 📄 License

本项目仅用于网站展示与产品原型开发，可根据实际项目需求自行调整。