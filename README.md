# SixingWang2025.github.io

GitHub Pages 主仓库，星空粒子动画入口页 + 聚合三个子站点。  
线上地址：[**sixingwang2025.github.io**](https://sixingwang2025.github.io)

## 站点结构

| 路径 | 内容 | 来源仓库 | 技术栈 |
|------|------|---------|--------|
| `/` | 星空入口页 | 本仓库 | 静态 HTML + Three.js |
| `/nav/` | 网址导航 | [Tangent-nav](https://github.com/SixingWang2025/Tangent-nav) | Hugo + WebStack |
| `/blog/` | 个人博客 | [Tangent-blog](https://github.com/SixingWang2025/Tangent-blog) | Hugo + Stack |
| `/page/` | 个人主页 | [Tangent-page](https://github.com/SixingWang2025/Tangent-page) | 静态 HTML + APlayer |

## 本仓库页面

| 文件 | 说明 |
|------|------|
| `index.html` | 星空粒子背景 + 打字机动画，入口链接到三个子站 |
| `404.html` | 自定义 404 页面 |
| `cardgame.html` | 记忆翻牌小游戏 |
| `LoveJiang.html` | 额外页面 |

## 子站点聚合架构

```
SixingWang2025.github.io/    ← 主仓库（你在这里）
├── index.html               ← 本仓库静态页面
├── 404.html
├── cardgame.html
├── LoveJiang.html
├── MakeCards/               ← 三国杀制牌器
├── nav/                     ← Tangent-nav 的 gh-pages
├── blog/                    ← Tangent-blog 的 gh-pages
└── page/                    ← Tangent-page 的 gh-pages
```

## 部署

三种触发方式：

| 触发方式 | 说明 |
|---------|------|
| 推送 `main` 分支 | 自动部署 |
| `repository_dispatch` | 子仓库 CI 完成后通知主仓库更新 |
| 手动触发 | GitHub Actions → "Build and Deploy Full Site" |

流程：检出本仓库 → 拉取各子仓库 `gh-pages` 分支 → 复制到 `nav/` `blog/` `page/` → 统一部署到 GitHub Pages。

## 本地预览

```bash
python3 -m http.server 8080
# 访问 http://localhost:8080
```

> 本地无法加载子站点（它们由 CI 从子仓库拉取），入口页的星空动画可直接预览。

## 相关仓库

- [Tangent-nav](https://github.com/SixingWang2025/Tangent-nav) — 网址导航
- [Tangent-blog](https://github.com/SixingWang2025/Tangent-blog) — 个人博客
- [Tangent-page](https://github.com/SixingWang2025/Tangent-page) — 个人主页
