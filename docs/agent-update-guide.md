# Agent 更新指南

## 基本原则

更新网站时遵守：

- 高内聚，低耦合。
- 可扩展，易维护。
- 高效简洁，非必需不复杂化。
- 先改内容文件，少改模板。
- 不为了单个页面创建全局复杂机制。

## 新增 GitHub 项目

1. 在 `content/ch/projects/<slug>/index.md` 新增中文页面。
2. 在 `content/en/projects/<slug>/index.md` 新增英文页面。
3. 保持两个语言版本使用同一 slug。
4. 如需展示在首页，将 `featured` 设为 `true`。

## 新增 AI Skill

1. 在 `content/ch/skills/<slug>/index.md` 新增中文页面。
2. 在 `content/en/skills/<slug>/index.md` 新增英文页面。
3. 必须填写 `platforms.skillhub.url` 和 `platforms.clawhub.url`，没有则留空字符串。
4. 下载量未知时使用 `downloads: null`。

## 新增 Blog

1. 使用日期加 slug：`content/ch/blog/2026-06-example/index.md`。
2. 英文页使用相同 slug。
3. 分类优先使用已有类别，不轻易增加新分类。

## 修改样式

优先修改 `assets/css/main.css` 中的 token 或现有组件。

避免：

- 为单个页面写大量一次性样式。
- 引入复杂前端框架。
- 把内容写死在模板里。
- 在模板中散落平台 URL 或下载量。
