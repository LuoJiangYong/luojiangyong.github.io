# 作品集网站内容模型与信息架构 v1

## 1. 网站定位

这是 Luo Jiangyong 的中英双语个人作品集网站，同时服务三类目标：

- 个人品牌化作品集：展示个人介绍、代表项目、公开链接、社交媒体和外部导航。
- AI 工具、自动化和产品案例展示：重点呈现正在持续建设的 AI Skills、自动化工作流、产品实验和落地案例。
- Blog 与知识沉淀：发布技术笔记、产品思考、构建日志、教程和个人文章。

视觉方向：杂志感、简洁、个人品牌化。避免通用 SaaS 落地页风格，优先使用强排版、清晰留白、项目图文和高质量媒体块形成阅读节奏。

## 2. 开发原则

- 高内聚：内容类型、页面模板、视觉组件和发布流程各自承担清晰职责。
- 低耦合：Markdown 内容、front matter 数据、CSS token、Hugo 模板和 GitHub Actions 不互相写死。
- 可扩展：新增项目、AI Skill、案例和 Blog 时优先新增内容目录，不改核心结构。
- 易维护：字段稳定、命名清晰、媒体跟随页面目录管理。
- 高效简洁：非必需不复杂化；第一版先使用静态内容和手动下载量字段，确认稳定需求后再增加自动化。

## 3. 视觉风格基线

后续视觉和设计风格采用本地 `claude` 风格作为基线，参考文件：

- `C:\Users\钱多多\Desktop\AI Skill\【00】重要Skill插件备份\awesome-design-md-main\design-md\claude\README.md`
- `C:\Users\钱多多\Desktop\AI Skill\【00】重要Skill插件备份\awesome-design-md-main\design-md\claude\DESIGN.md`

本站不直接复制 Claude 品牌，而是吸收其“暖色画布 + 编辑型排版 + 克制产品展示”的设计语言，并改造成 Luo Jiangyong 的个人作品集风格。

执行原则：

- 页面底色使用暖米色画布，避免纯白和冷灰。
- 主强调色使用温和珊瑚色，主要用于主按钮、重点链接和少量强 CTA。
- 正文使用深墨色和暖灰文字层级。
- 使用深色产品展示面承载代码、流程、Skill 能力、下载量和项目截图。
- 首页、项目页和 Skill 页保持“浅色阅读区 / 深色产品展示区 / 珊瑚强调区”的节奏。
- 大标题使用有杂志感的 serif 字体，正文和 UI 使用清晰的 sans 字体。
- 代码块和技术片段使用 monospace 字体。
- 卡片圆角保持克制，主要使用 8px 到 12px。
- 避免冷蓝色、赛博风、过度渐变、纯装饰图形和通用 SaaS hero。

建议设计 tokens：

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
  accent_teal: "#5db8a6"
  accent_amber: "#e8a55a"

typography:
  display: "Tiempos Headline, Garamond, Times New Roman, serif"
  body: "Inter, -apple-system, BlinkMacSystemFont, Segoe UI, Roboto, sans-serif"
  code: "JetBrains Mono, ui-monospace, monospace"

radii:
  button: "8px"
  card: "12px"
  media: "16px"
```

第一版实现时需要在 `docs/styleguide.md` 中维护这些 tokens 和基础组件；样式资产库不生成到最终网页。

## 4. 中英双语与 URL 规则

采用独立语言路径：

- 中文：`/ch/`
- 英文：`/en/`

每个页面都需要提供语言切换入口。对应页面优先保持同一 slug，例如：

```text
/ch/skills/real-estate-strategy/
/en/skills/real-estate-strategy/
```

推荐内容策略：

- 中文为主要维护语言。
- 英文为完整平行内容，不在前端运行时自动翻译。
- 后续由 agent 生成英文草稿时，仍需人工确认后发布。

## 5. 核心栏目

### 首页

用途：作为个人品牌入口和全站导航中心。

内容：

- 个人定位声明。
- 精选 GitHub 项目。
- 精选 AI Skills。
- 精选项目案例。
- 最新 Blog。
- 社交媒体与外部导航。

### GitHub 项目

用途：把公开仓库解释成作品集资产，而不仅是代码链接。

首批展示项目：

- `real-estate-ai-skills-pack`
- GitHub: <https://github.com/LuoJiangYong/real-estate-ai-skills-pack>

每个项目应包含：

- 项目是什么。
- 面向谁。
- 解决什么问题。
- 核心能力。
- 技术栈。
- GitHub 仓库链接。
- 截图、视频或演示链接。
- 关联 AI Skills。

### AI Skills

用途：展示可复用的 AI 工作流能力，并提供 Skillhub、Clawhub 下载量与跳转入口。

首批展示四个 AI Skills：

| 展示名称 | Skillhub | Clawhub |
| --- | --- | --- |
| `real-estate-strategy` | <https://skillhub.cn/skills/real-estate-strategy> | <https://clawhub.ai/luojiangyong/real-estate-strategy> |
| `real-estate-storyline` | <https://skillhub.cn/skills/real-estate-storyline> | <https://clawhub.ai/luojiangyong/real-estate-storyline> |
| `real-estate-community-top-design` | <https://skillhub.cn/skills/real-estate-community-strategy> | <https://clawhub.ai/luojiangyong/real-estate-community-strategy> |
| `wechat-article-conversion` | <https://skillhub.cn/skills/wechat-article-exporter> | <https://clawhub.ai/luojiangyong/wechat-article-conversion> |

说明：第三、第四个 Skill 的展示名称与平台 URL slug 不完全一致，先按“展示名称 + 平台链接原样保留”的方式维护。

每个 AI Skill 应包含：

- 简介。
- 适用场景。
- 目标用户。
- 输入。
- 输出。
- 示例工作流。
- Skillhub 下载量。
- Clawhub 下载量。
- Skillhub 跳转链接。
- Clawhub 跳转链接。
- 关联 GitHub 项目或案例。
- 状态：idea、prototype、active、stable、archived。

下载量展示建议：

- 第一版先使用手动维护字段，避免依赖平台抓取。
- 后续如果 Skillhub 或 Clawhub 提供稳定 API，再改为定时抓取或构建时拉取。
- 如果下载量暂缺，前端显示为 `--` 或 “待更新”。

### 项目案例

用途：展示更完整的端到端案例。

每个案例应包含：

- 背景。
- 问题。
- 个人角色与贡献。
- 过程。
- 交付物。
- 结果或复盘。
- 截图、图表或视频。
- 关联 GitHub 项目或 AI Skills。

### Blog

用途：发布持续写作和知识沉淀。

推荐分类：

- AI 工具与自动化。
- 产品案例。
- 构建日志。
- 技术笔记。
- 个人文章。

### 外部导航

用途：集中展示社交媒体和外部入口。

推荐分组：

- GitHub。
- 社交媒体。
- 写作平台。
- 视频平台。
- Skillhub。
- Clawhub。
- 外部项目演示。

### 样式资产库

用途：维护网站视觉系统，并为后续 agent 更新提供稳定参考。

维护路径：`docs/styleguide.md`。不在最终网站导航中展示，也不生成公开页面。

建议内容：

- 色彩系统。
- 字体层级。
- 卡片。
- 按钮与链接。
- 项目列表项。
- 媒体块。
- Blog 正文排版。
- 标签与状态。
- 下载量展示组件。
- 深色产品展示卡片。
- 珊瑚色 CTA 区块。
- 中英双语页面示例。

## 6. 推荐仓库结构

```text
content/
  ch/
    projects/
    skills/
    cases/
    blog/
  en/
    projects/
    skills/
    cases/
    blog/

data/
  profile.yaml
  social_links.yaml
  featured.yaml
  navigation.yaml
  skill_platforms.yaml

assets/
  css/
  js/
  images/

layouts/
  _default/
  partials/
  shortcodes/

docs/
  portfolio-content-model-and-ia-v1.md
  content-maintenance-guide.md
  agent-update-guide.md
```

## 7. 内容模型

### GitHub 项目 Front Matter

```yaml
---
type: project
slug: real-estate-ai-skills-pack
title: "Real Estate AI Skills Pack"
summary: "一句话说明项目价值。"
status: active
featured: true
date: 2026-06-06
repo_url: "https://github.com/LuoJiangYong/real-estate-ai-skills-pack"
demo_url: ""
cover: "cover.png"
video: ""
tags: ["AI", "Automation", "Real Estate", "Skills"]
tech_stack: []
related_skills:
  - real-estate-strategy
  - real-estate-storyline
  - real-estate-community-top-design
  - wechat-article-conversion
related_cases: []
---
```

### AI Skill Front Matter

```yaml
---
type: skill
slug: real-estate-strategy
title: "real-estate-strategy"
summary: "说明这个 Skill 帮谁完成什么任务。"
status: active
featured: true
date: 2026-06-06
cover: "cover.png"
video: ""
platforms:
  skillhub:
    url: "https://skillhub.cn/skills/real-estate-strategy"
    downloads: null
  clawhub:
    url: "https://clawhub.ai/luojiangyong/real-estate-strategy"
    downloads: null
skill_inputs: []
skill_outputs: []
tags: ["AI Skill", "Real Estate", "Automation"]
related_projects:
  - real-estate-ai-skills-pack
related_cases: []
---
```

### 项目案例 Front Matter

```yaml
---
type: case
slug: example-case
title: "案例标题"
summary: "一句话说明案例成果。"
featured: true
date: 2026-06-06
cover: "cover.png"
video: ""
role: "产品设计、自动化方案、实现"
tags: ["Product Case", "AI Tool", "Automation"]
related_projects: []
related_skills: []
---
```

### Blog Front Matter

```yaml
---
type: blog
slug: example-post
title: "文章标题"
summary: "文章摘要。"
date: 2026-06-06
cover: ""
category: build-log
tags: ["Hugo", "Portfolio"]
---
```

## 8. 媒体策略

第一版规则：图片和小视频优先放在仓库内，使用 Hugo Page Bundle 管理。

建议：

- 图片尽量使用压缩后的 Web 友好格式。
- 小视频可直接放在对应内容目录。
- 大视频改用外链，并在仓库中保留封面图。
- 每个内容页面的媒体文件与 `index.md` 放在同一目录，方便后续维护和 review。

## 9. 维护流程

推荐更新流程：

1. 用户提供原始材料、链接、截图或视频。
2. Agent 整理为 Markdown 正文和 front matter。
3. 用户确认文字、补充配图或要求 AI 生成配图。
4. Agent 更新内容文件和必要的数据文件。
5. 本地构建预览。
6. 提交并推送到 GitHub。
7. GitHub Actions 自动发布到 GitHub Pages。

## 10. 构建与托管方案

仓库：`luojiangyong.github.io`

托管：

- 使用 GitHub Pages。
- 使用 GitHub Actions 作为 Pages 构建来源。
- 使用 Hugo 渲染静态站。

第一阶段交付：

- 初始化 Hugo 项目结构。
- 配置 `/ch/` 与 `/en/` 双语路径。
- 建立首页、GitHub 项目列表、AI Skills 列表、案例列表、Blog 列表，并在 `docs` 中维护样式资产库。
- 加入 `real-estate-ai-skills-pack` 项目样例。
- 加入四个 AI Skills 样例。
- 增加 Skillhub、Clawhub 链接和下载量展示组件。
- 按 `claude` 风格基线实现暖米色画布、serif 大标题、珊瑚色主按钮、深色产品展示卡片，并在 `docs/styleguide.md` 维护样式资产库。
- 添加 GitHub Actions 部署流程。
- 本地构建验证后再发布。

## 11. 待确认项

进入实现前还需要确认：

- 首批社交媒体与外部导航链接。
- 四个 AI Skills 的中文简介和英文简介。
- Skillhub、Clawhub 下载量是否先手动填写。
- 第一版是否需要真实视频，还是先用封面图和外链占位。
