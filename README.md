# 李腾龙 · 设计主管 · 视觉作品集

单文件静态作品集站点，纯前端（HTML + 内联 CSS/JS），无构建步骤、无外部 CDN 依赖。

**线上地址**：https://ld1465642193-boop.github.io/tenglong-portfolio/

## 本地预览

```bash
python -m http.server 8080
# 打开 http://localhost:8080
```

也可直接双击 `index.html`（所有依赖已本地化）。

## 目录结构

```
.
├── index.html      # 整站（结构 + 内联样式 + 内联动效）
├── vendor/         # 本地化动效依赖，无外网请求
│   ├── gsap.min.js
│   ├── ScrollTrigger.min.js
│   └── lenis.min.js
├── assets/         # 案例封面、详情长图、方法论文档截图
├── assets_v2/      # 品牌视觉、详情页拆解、推广素材、个人照
└── .nojekyll       # 关闭 GitHub Pages 的 Jekyll 处理
```

## 性能说明

| 项 | 数值 |
|---|---|
| 首屏完全可见（手机 4G） | 约 1.2 秒 |
| 首屏完全可见（手机 3G） | 约 2.5 秒 |
| 滚动时加载的图片总量 | 4.72 MB（68 张，全部 WebP） |
| 图片加载策略 | 全部 `loading="lazy"`，逐屏按需加载 |
| 动效库 | 本地 `vendor/`，0 个外网请求 |

图片按页面实际显示尺寸压缩（2 倍屏标准），例如详情页拆解图桌面显示 179px，原图 750px 宽已压到 420px。

## 技术栈

- **动效**：GSAP 3.15 + ScrollTrigger + Lenis（本地）
- **字体**：系统字体栈（PingFang SC / Microsoft YaHei / 宋体），无 Google Fonts
- **动效属性**：只用 `transform` / `opacity` / `clip-path`
- **无障碍**：完整 `prefers-reduced-motion` 降级 + `<noscript>` 兜底
- **移动端**：≤860px 关闭视差位移与横向画廊

## 内容结构

1. 首屏 · 岗位定位与三项核心 KPI
2. 主张「设计不只是把图做好看」
3. 关于我 · 履历 / 核心能力 / 荣誉奖项 / 工作方式
4. 在柠乐做的四件有结果的事
5. 先讲清楚为什么这么做
6. Case 01 · 膏遗
7. Case 02 · 百年医仁
8. 详情页拆解 · 7 大板块
9. 视觉产出 · 推广素材（可左右拖动）
10. 方法论与体系 · 八中心协作 / AIGC 提效 / 年终汇报
11. 联系方式
