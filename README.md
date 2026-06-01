# SixingWang2025.github.io

GitHub Pages 主仓库，星空动画入口页 + 聚合三个子站点。线上地址：[sixingwang2025.github.io](https://sixingwang2025.github.io)

## 页面

| 文件 | 说明 |
|------|------|
| `index.html` | 星空粒子 + 打字机动画入口页，链接到三个子站 |
| `404.html` | 自定义 404 页面 |
| `cardgame.html` | 记忆翻牌小游戏 |
| `LoveJiang.html` | 额外页面 |

## 子站点路径映射

| 路径 | 来源仓库 | 构建方式 |
|------|---------|---------|
| `/` | 本仓库 | 静态 HTML |
| `/nav/` | [Tangent-nav](https://github.com/SixingWang2025/Tangent-nav) | Hugo → gh-pages |
| `/blog/` | [Tangent-blog](https://github.com/SixingWang2025/Tangent-blog) | Hugo → gh-pages |
| `/page/` | [Tangent-page](https://github.com/SixingWang2025/Tangent-page) | 静态 → gh-pages |

## 部署

支持三种触发方式：

- **推送 main 分支**（自动）
- **子仓库 repository_dispatch**（子仓库 CI 通知后自动）
- **手动触发**（GitHub Actions → "Build and Deploy Full Site"）

流程：检出本仓库 + 各子仓库 `gh-pages` 分支 → 复制到 `/nav` `/blog` `/page` → 统一部署到 Pages。

## 本地预览

```bash
python3 -m http.server 8080
# 访问 http://localhost:8080
```

注意本地无法加载子站点目录（它们由 CI 生成），入口页本身可直接预览。
