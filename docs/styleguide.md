# 样式资产库

本站视觉系统基于暖米色画布、编辑型 serif 标题、珊瑚色强调和深色产品展示卡片。

## 设计 Tokens

```yaml
colors:
  canvas: "#faf9f5"
  surface_soft: "#f5f0e8"
  surface_card: "#efe9de"
  surface_dark: "#181715"
  surface_dark_elevated: "#252320"
  ink: "#141413"
  body: "#3d3d3a"
  muted: "#6c6a64"
  hairline: "#e6dfd8"
  primary: "#cc785c"
  primary_active: "#a9583e"

typography:
  display: "Tiempos Headline, Garamond, Times New Roman, serif"
  body: "Inter, system sans-serif"
  code: "JetBrains Mono, ui-monospace"

radii:
  button: "8px"
  card: "12px"
  media: "16px"
```

## 组件

- 个人品牌首屏：简介、照片预留位、社交媒体。
- 个人标签卡片：四个高层身份标签。
- 时间线条目：时间周期、周期概述、介绍标题、主要经历。
- 项目卡片：标题、摘要、标签、详情链接。
- Skill 卡片：简介、Skillhub 下载量、Clawhub 下载量、平台跳转。
- 深色产品展示卡片：用于代码、流程、平台数据和关键能力。

## 响应式规则

- 桌面端：主内容容器 1120px，首页首屏双栏。
- 移动端：所有网格降为单栏，导航换行，避免横向溢出。
- 按钮和平台卡片保持清晰触控区域。
- 不在最终网页导航中展示样式库；样式库作为 `docs` 维护资产存在。
