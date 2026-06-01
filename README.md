# SixingWang2025.github.io

GitHub Pages 主仓库，聚合子项目到同一域名下。线上地址：[sixingwang2025.github.io](https://sixingwang2025.github.io)

## 路径映射

| 路径 | 来源仓库 | 构建方式 |
|------|---------|---------|
| `/` | 本仓库 | 静态文件 |
| `/nav/` | [Tangent-nav](https://github.com/SixingWang2025/Tangent-nav) | Hugo → gh-pages |
| `/blog/` | [Tangent-blog](https://github.com/SixingWang2025/Tangent-blog) | Hugo → gh-pages |
| `/page/` | [Tangent-page](https://github.com/SixingWang2025/Tangent-page) | 静态文件 → gh-pages |

## 部署流程

```
子仓库 push → 子仓库 CI 部署到 gh-pages 分支
    → 子仓库 CI 发送 repository_dispatch 到本仓库
        → 本仓库 CI 检出所有子仓库的 gh-pages 分支
            → 复制到 /nav、/blog、/page 目录
                → 部署到 GitHub Pages
```

## 目录结构

```
SixingWang2025.github.io/
├── index.html              # 首页
├── 404.html                # 自定义 404 页面
├── cardgame.html           # 额外页面
├── LoveJiang.html          # 额外页面
├── MakeCards/              # 额外项目
├── .github/workflows/      # CI：接收子仓库通知，聚合部署
├── nav/                    # CI 生成（Tangent-nav 构建产物）
├── blog/                   # CI 生成（Tangent-blog 构建产物）
└── page/                   # CI 生成（Tangent-page 构建产物）
```

## 手动触发部署

在 GitHub Actions 页面手动运行 "Build and Deploy Full Site" workflow，或者修改任一子仓库并推送，会自动触发。

## 本地开发

本仓库无需本地运行，直接编辑静态文件即可。子仓库变更在各子仓库中开发，推送后由 CI 自动汇聚到这里。
