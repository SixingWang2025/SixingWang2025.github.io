# sixingwang2025.github.io

Main site aggregating sub-projects under one GitHub Pages domain.

| Path | Source |
|------|--------|
| `/` | This repo |
| `/page/` | [Tangent-page](https://github.com/SixingWang2025/Tangent-page) |
| `/blog/` | [Tangent-blog](https://github.com/SixingWang2025/Tangent-blog) |
| `/nav/` | [Tangent-nav](https://github.com/SixingWang2025/Tangent-nav) |

## Deploy

Triggered by `repository_dispatch` from sub-project workflows. Each sub-project deploys to its own `gh-pages` branch, then pings this repo to pull in the latest content and redeploy.
