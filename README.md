# 李腾龙 · 设计主管 · 视觉作品集

单文件静态作品集站点，纯前端（HTML + 内联 CSS/JS），无构建步骤、无外部 CDN 依赖。

## 本地预览

```bash
# 任选一种
python -m http.server 8080
# 然后打开 http://localhost:8080
```

也可以直接双击 `index.html` 用浏览器打开（所有依赖均已本地化）。

## 目录结构

```
.
├── index.html          # 整站（结构 + 内联样式 + 内联动效脚本）
├── vendor/             # 本地化的动效依赖，无外网请求
│   ├── gsap.min.js
│   ├── ScrollTrigger.min.js
│   └── lenis.min.js
├── assets/             # 案例封面、长图切片、方法论文档截图
├── assets_v2/          # 品牌视觉、详情页拆解、推广素材、个人照片
└── .nojekyll           # 关闭 GitHub Pages 的 Jekyll 处理
```

## 部署到 GitHub Pages

```bash
# 1. 在 GitHub 新建一个仓库，例如 tenglong-portfolio（不要勾选任何初始化文件）
# 2. 在本目录执行：
git remote add origin https://github.com/<你的用户名>/tenglong-portfolio.git
git push -u origin main

# 3. 打开仓库 → Settings → Pages
#    Source 选择 "Deploy from a branch"
#    Branch 选择 main，目录选 / (root)，Save
# 4. 约 1 分钟后访问：
#    https://<你的用户名>.github.io/tenglong-portfolio/
```

## 技术说明

| 项 | 说明 |
|---|---|
| 动效库 | GSAP 3.15 + ScrollTrigger + Lenis（全部本地 `vendor/`，无 CDN） |
| 字体 | 系统字体栈（`PingFang SC` / `Microsoft YaHei` / 宋体），无 Google Fonts |
| 动效实现 | 只用 `transform` / `opacity` / `clip-path`，不触发重排 |
| 无障碍 | 完整实现 `prefers-reduced-motion: reduce`；脚本失效时有 `<noscript>` 兜底样式 |
| 移动端 | `≤860px` 自动关闭视差位移与横向画廊，保留文字淡入 |
| 图片 | 全部 `loading="lazy"`，总约 9.3 MB |
| 站点体积 | 约 9.7 MB |

## 内容结构

1. 首屏 · 岗位定位与三项核心 KPI
2. 主张「设计不只是把图做好看」
3. 关于我 · 履历 / 核心能力 / 荣誉奖项 / 工作方式
4. 在柠乐做的四件有结果的事
5. 先讲清楚为什么这么做
6. Case 01 · 膏遗（品牌 0→1、五专标准、多色系规范）
7. Case 02 · 百年医仁（选品逻辑、分众人群、5 方向 6 策略）
8. 详情页拆解 · 7 大板块
9. 视觉产出 · 推广素材（可左右拖动）
10. 方法论与体系 · 八中心协作 / AIGC 提效 / 年终汇报
11. 联系方式
