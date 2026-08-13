# 设计资产选型清单（AI Coding 时代 · 定稿版）

> 核心原则：**每一层有且只有一个默认项，遇到问题才换。**
> 默认组合是训练语料中高频共现的组合，AI 生成质量最稳、踩坑最少。
> 设计稿即产品：探索期纯前端做设计决策，固化期在同一代码库上补产品层，无交接、无重写。

---

## 一、地基层

| 层 | 默认 | 替代 / 何时启用 |
|---|---|---|
| 框架 | Vite + React + TypeScript | Next.js（需要 SSR/SEO/文件路由时） |
| 样式引擎 | Tailwind CSS v4 | UnoCSS；CSS Modules |
| 设计 token | Tailwind theme + CSS 变量，**颜色用 OKLCH** | — |
| 主题/暗色 | CSS 变量 + `data-theme` / `.dark` class | next-themes（Next 项目） |
| 路由 | —（探索期单页不需要） | React Router（固化期多页 SPA）；Next 自带 |

### Token 规范要点

- **颜色**：OKLCH 色彩空间（`oklch()`），语义色阶（primary / surface / muted / destructive…），暗色模式直接翻转色阶，对比度更稳
- **圆角**：固定词表，如 `button: 8px / card: 12px / dialog: 16px`，禁止词表外取值
- **间距**：基于 4px 栅格，组件内间距与布局间距分档（如 `card: 24px / section: 64px`）
- **字阶**：固定 type scale（display / title / body / caption…），禁止散养字号
- **栅格与断点**：文档化断点、容器宽度、栏数——设计系统的布局规范必须写成文档，不能只靠工具默认

---

## 二、组件与交互行为层

| 层 | 默认 | 替代 / 何时启用 |
|---|---|---|
| 组件体系 | **shadcn/ui**（源码入仓、AI 可改、零锁定） | Mantine（全家桶开箱即用）；AntD（中后台存量） |
| 无头行为库 | Radix UI（shadcn 底座，键盘/焦点/ARIA 内置） | Base UI；React Aria（无障碍最深）；Ark UI |
| 复杂交互状态机 | —（默认用不上） | Zag.js；XState（多步流程/向导） |
| 动效 | Motion（弹簧物理、布局补间、手势） | CSS transitions（够用就行）；AutoAnimate（列表自动动画） |
| 手势 | @use-gesture | 简单拖拽直接用 Motion 的 drag |
| 拖拽排序 | dnd-kit | Pragmatic DnD（Atlassian） |

### 交互规范要点（写进组件规范，比事后审计更根本）

- 键盘导航、焦点管理、ARIA 由 Radix 内置保证，自定义组件不得破坏
- 全局 `:focus-visible` 焦点环样式，不得 `outline: none` 后无替代
- 尊重 `prefers-reduced-motion`，动效可降级
- 行为标准参照 WAI-ARIA Authoring Practices（W3C 交互规范原典）

---

## 三、内容元素层

| 层 | 默认 | 替代 / 何时启用 |
|---|---|---|
| 图标 | Lucide | Iconify（聚合 200+ 图标集）；Heroicons |
| 英文字体 | Inter（拉丁子集自托管，fontsource） | — |
| 中文字体 | **系统字体兜底**（苹方/微软雅黑/思源黑体栈） | 思源黑体子集化自托管（品牌强需求时）；禁止全量自托管拖慢首屏 |
| 图表 | Recharts | Tremor（仪表盘）；ECharts（复杂可视化）；visx（完全自定义） |
| 富文本 | — | Tiptap（需要时）；Lexical |
| 轮播 | — | Embla；Swiper |

---

## 四、复杂组件层（自写成本最高，直接用库）

| 层 | 默认 | 备注 |
|---|---|---|
| 表格 | TanStack Table | 排序/筛选/列固定/虚拟化 |
| 虚拟列表 | TanStack Virtual | 万级数据 |
| 命令面板 | cmdk | ⌘K 式交互 |
| Toast | sonner | 一行接入 |
| 表单 | React Hook Form + Zod | 校验规则即类型 |
| 日期 | react-day-picker + date-fns | — |
| 流程图/画布 | — | React Flow；白板 tldraw；3D react-three-fiber |

---

## 五、产品层（固化期才接入，探索期不需要）

| 层 | 默认 | 备注 |
|---|---|---|
| 服务端状态 | TanStack Query | 替代手写 useEffect+fetch，必须项 |
| 应用级状态 | Zustand | 跨组件客户端状态；有了 Query 后需求量很小，勿滥用 |
| 工程化 | Biome（或 ESLint + Prettier）+ Vitest | AI 产出代码的一致性兜底 |
| 国际化 | 暂不接入 | **纪律：文案不集中硬编码**；首个多语言需求出现时接 react-i18next / next-intl |
| Token ↔ Figma 同步 | 不启用（代码是唯一真相源） | **仅当团队有专职设计师驻场用 Figma** 时启用 Tokens Studio / Style Dictionary 双向同步 |

---

## 六、质量保障层（设计稿模式可砍，产品模式保留）

| 层 | 默认 | 备注 |
|---|---|---|
| 组件文档 | Storybook | 相当于代码版组件库页面 |
| 交互测试 | Playwright | 真实浏览器回归 |
| 无障碍回归 | axe + Testing Library | 与"前置规范"互补，非二选一 |
| 视觉回归 | Playwright 截图对比 | 防改一处坏一片 |

---

## 参考：大厂开源设计系统（规范怎么写的范本）

- **Shopify Polaris**、**GitHub Primer**、**Atlassian Design System** —— 规范文档 + token + 组件全套开源

## 两阶段工作流

1. **探索期（设计工作）**：纯前端 + 假数据，只做设计决策——视觉、交互、动效。产出是可运行代码，不是一次性图稿
2. **固化期（开发工作）**：方向确认后，在同一代码库补第五节产品层，设计资产（token/组件/动效）零损耗保留至上线
