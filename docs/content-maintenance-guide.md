# 内容维护指南

## 开发原则

- 高内聚：每类内容、模板和组件只处理自己的职责。
- 低耦合：内容数据、页面模板、样式资产和发布流程尽量分离。
- 可扩展：新增项目、AI Skill、案例和 Blog 时优先新增内容文件，不改核心模板。
- 易维护：字段命名稳定，媒体与对应 `index.md` 放在同一目录。
- 高效简洁：非必需不复杂化；第一版先用手动字段和静态生成，后续有稳定需求再自动化。

## 内容更新流程

1. 收集原始材料、链接、截图或视频。
2. 整理成对应语言路径下的 Markdown 页面。
3. 更新 front matter 字段。
4. 图片和小视频放在对应页面目录。
5. 本地运行 Hugo 构建检查。
6. 提交并推送，GitHub Actions 自动发布。

## AI Skill 下载量

第一版使用手动维护：

```yaml
platforms:
  skillhub:
    url: "https://skillhub.cn/skills/example"
    downloads: null
  clawhub:
    url: "https://clawhub.ai/example"
    downloads: null
```

如果下载量未知，保持 `null`，前端显示为 `--`。

## 媒体规则

- 每个页面优先使用 Hugo Page Bundle：`content/ch/skills/example/index.md`。
- 图片和小视频放在同目录。
- 大视频使用外链，并保留本地封面图。
- 图片命名使用小写英文和连字符，例如 `cover.png`、`workflow-preview.jpg`。

## 移动端与网页端

- 桌面端优先使用 1120px 内容容器。
- 移动端所有网格降为单栏。
- 导航允许换行，不强行塞进一行。
- 按钮高度至少 40px。
- 文本不能依赖图片才能理解。
