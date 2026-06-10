# Eric's Tools — 项目长期规划

## 项目定位

一个纯静态、无广告、完全本地的 Web 工具集合站。所有工具均为单个 `.html` 文件，通过 `index.html` 导航页统一索引。部署在 Netlify。

## 技术约定

- 所有新工具放在项目根目录，如 `json-formatter.html`
- 新建工具后，在 `index.html` 的 `TOOLS` 数组中加一条记录即可自动渲染
- 深色主题统一风格：背景 `#080c14`，卡片玻璃态 `rgba(15,23,42,0.4)`
- 依赖：Tailwind v4 CDN，不引入任何 JS 框架
- 工具页面自带 SVG favicon（参考 index.html 的 embedded favicon 方式）

---

## 第一阶段：导航站完善 + 5个核心工具 ✅ 已完成 (2026-06-10)

### 1.1 index.html 优化
- [x] 搜索功能
- [x] OG meta + favicon
- [x] 数据驱动渲染（TOOLS 数组）
- [x] **分类筛选 Tabs** — All / Developer / Design / Security / Conversion，与搜索联动
- [x] **`addedAt` 自动 NEW badge** — 在 TOOLS 条目中添加 `addedAt: "2026-06-10"`，30天内自动显示 NEW
- [x] **键盘快捷键** — `/` 聚焦搜索、`Esc` 清空

### 1.2 工具制作（按优先级）

| 序号 | 工具名 | 文件名 | 类别 | 难度 | 预估工时 |
|------|--------|--------|------|------|----------|
| 1 | JSON Formatter | `json-formatter.html` | Developer | ⭐⭐ | 2h |
| 2 | Color Converter | `color-converter.html` | Design | ⭐⭐ | 1.5h |
| 3 | Base64 Tool | `base64.html` | Developer | ⭐ | 1h |
| 4 | Regex Tester | `regex-tester.html` | Developer | ⭐⭐⭐ | 3h |
| 5 | Hash Generator | `hash-generator.html` | Security | ⭐ | 1h |

**JSON Formatter 排第一的原因：** 开发者搜索量最大的单体工具，SEO 价值最高，能给导航站引流。

---

## 第二阶段：品类扩展 + 交互升级 ✅ 已完成 (2026-06-10)

### 2.1 新工具

| 序号 | 工具名 | 文件名 | 类别 | 难度 |
|------|--------|--------|------|------|
| 6 | URL Encoder/Decoder | `url-encoder.html` | Developer | ⭐ |
| 7 | UUID Generator | `uuid-generator.html` | Developer | ⭐ |
| 8 | Contrast Checker | `contrast-checker.html` | Design | ⭐ |
| 9 | JWT Decoder | `jwt-decoder.html` | Security | ⭐ |
| 10 | Unit Converter | `unit-converter.html` | Conversion | ⭐⭐ |
| 11 | Number Base Converter | `number-base.html` | Conversion | ⭐ |
| 12 | Aspect Ratio Calculator | `aspect-ratio.html` | Design | ⭐ |

### 2.2 index.html 优化
- [x] **最近使用记录** — 点击工具时写入 localStorage，顶部显示"最近打开"（最多3个）
- [x] **多分类支持** — 新增 `🔢 Math & Conversion` 分类

---

## 第三阶段：进阶工具 + 社区感（第5~8周）

### 3.1 较复杂工具

| 序号 | 工具名 | 文件名 | 类别 | 难度 | 说明 |
|------|--------|--------|------|------|------|
| 13 | Diff Checker | `diff-checker.html` | Developer | ⭐⭐⭐ | 行级高亮，需引入轻量 diff 算法 |
| 14 | Shadow Studio | `shadow-studio.html` | Design | ⭐⭐ | 可视化调阴影 |
| 15 | Typography Scale | `typography-scale.html` | Design | ⭐⭐ | Tailwind/CSS 字体比例尺 |
| 16 | Cron Builder | `cron-builder.html` | Conversion | ⭐⭐⭐ | 可视化 Cron 表达式生成 |
| 17 | Lorem Ipsum Generator | `lorem-ipsum.html` | Security | ⭐ | 占位文本生成 |

### 3.2 index.html 优化
- [ ] **收藏/星标** — 卡片加星标，收藏保存到 localStorage，置顶
- [ ] **工具状态标记** — `status: "beta"` / `"new"` / `"stable"`
- [ ] 工具数量达到 15+ 时考虑**分页或"加载更多"**

---

## 第四阶段：品牌与运营（长期）

- [ ] 统一的 og-image 封面图
- [ ] 每个工具页面底部加"返回工具矩阵"链接，形成站内闭环
- [ ] 考虑添加 `/tools/*` 子目录结构（当文件超过 20 个时）
- [ ] 简单的访问统计（可选，用 GoatCounter 等隐私友好方案）

---

## 工具文件命名规范

统一用 `kebab-case.html`：
- `json-formatter.html`
- `color-converter.html`
- `regex-tester.html`

## TOOLS 数组记录模板

```js
{
  name: "JSON Formatter",
  url: "json-formatter.html",
  tag: "Format",
  tagColor: "blue",
  desc: "Format, minify, and validate JSON with collapsible tree view. Paste, click, done.",
  addedAt: "2026-06-11",  // 可选，用于自动 NEW badge
}
```

## 类别颜色参考

| 类别 | emoji | 推荐 tagColor |
|------|-------|---------------|
| Developer Utilities | 💻 | blue / cyan |
| Design & Visual | 🎨 | pink / violet / rose |
| Privacy & Security | 🔒 | emerald / teal |
| Math & Conversion | 🔢 | amber / orange |

---
> 最后更新：2026-06-10
