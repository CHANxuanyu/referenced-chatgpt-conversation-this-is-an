# AI-native 个人知识库

## 关键产品决策审阅稿 v1.0

> 文档日期：2026-08-10  
> 文档性质：`终局产品设计文档 v6.0` 的决策审阅伴侣；不是新的 Canonical、功能路线图、界面稿或原型授权  
> 当前阶段：确认产品本体；不修改 Ardot，不制作新 Screen，不开始可点击原型  
> 研究范围：层级阅读、关系图谱、AI 查询与长期知识维护；不把价格、协作、任务管理或插件生态带入产品中心  
> 事实边界：官方资料说明现有产品怎样工作；社区反馈只提供问题信号；本产品选择仍是需要验证的产品决定  

---

# 如何使用这份审阅稿

`v6.0`负责完整定义产品；本文件只回答一个问题：

> **在进入任何新视觉设计之前，哪些决定一旦选错，会让产品再次变成另一种东西？**

阅读顺序：

1. 先读`0. 当前判断`；
2. 再读`3. 十四项关键产品决定`；
3. 重点检查`4. 十一个高影响选择`；
4. 最后在`8. 用户确认页`表达反对或修改。

状态含义：

| 状态 | 含义 |
|---|---|
| **用户已确认** | 用户已经明确表达，不应被竞品或实现便利覆盖 |
| **用户已确认方向** | 核心方向明确，精确语义仍是产品建议 |
| **产品推荐** | 当前证据下最完整、最克制的选择，仍需用户整体确认 |
| **设计 Gate** | 不决定本体，但后续设计必须证明 |
| **待验证假设** | 没有真实用户或长期使用证据，不能写成已成立结果 |

---

# 0. 当前判断

## 0.1 产品方向已经收敛，但产品选择尚未全部确认

这不是一个 Cognitive OS、项目恢复系统、AI 聊天容器或文件管理器。它的本体已经足够明确：

> **一个以知识群为范围、以 Overview → detail 为阅读主干、以有语义关系为横向网络，并允许用户搜索、AI 查询和主动探索的本地优先个人知识库。**

当前真正未完成的不是再补一批功能，而是确认十四项会决定整个产品气质和复杂度的选择。它们在用户表面必须收敛为一个稳定地点`知识库`、五个日常内容概念`知识群 / 主题 / 知识 / 关系 / 来源`和三个全局动作`搜索 / 提问 / 添加`；内部术语不能重新变成第二套用户产品。

## 0.2 方向 3 + 2 是产品结构，不只是视觉偏好

- 方向 3 决定默认体验：先理解整体，再逐层深入；
- 方向 2 决定第二维度：需要连接、比较或迁移时打开关系空间；
- 两者共享同一 Knowledge identity、Source、History 与 Return path；
- 关系空间不永久占据阅读界面；
- 阅读也不会把所有关系降级成正文链接。

## 0.3 当前最大风险

| 风险 | 如果发生，产品会退化成什么 |
|---|---|
| 全局图承担默认首页 | 漂亮但低效的节点云 |
| 每种内容都变成对象类型 | 用户维护数据库，而不是理解知识 |
| 每个 Claim 都拆成卡片 | 长知识失去阅读连续性 |
| Overview 自动生成且不可编辑 | AI 摘要层，不是个人理解入口 |
| AI Answer 自动进入当前知识 | 流畅但不可控的真相覆盖器 |
| Relation 只是一条无类型线 | 可视化 backlinks，不是知识网络 |
| 每个 Group 复制自己的内容 | 项目孤岛和版本分叉 |
| Review / Inbox 成为首页 | 维护系统重新占据产品中心 |
| 用七张功能页代表完整产品 | 页面彼此漂亮，但同一知识、失败和返回无法连续 |

---

# 1. 外部研究给出的信号

## 1.1 全局图很容易变成展示，局部图更容易服务任务

**观察事实：**Obsidian 官方区分显示整个 vault 的 Graph View 与围绕 active note、可以调 depth 的 Local Graph。Graph 的默认边来自 note links，节点大小主要随引用数量变化。

**社区信号：**多个 2025–2026 年讨论反复出现“全局图漂亮但很少使用”“Local Graph 更有用”“规模增长后需要 hierarchy、named clusters 和 stronger bonds”等反馈。也有用户把全局图用于发现孤立内容、宏观浏览和意外连接，因此不能推导“全局图没有价值”。

**产品推论：**

- Library Network 的 resting level 应以 Groups 为主要节点，而不是铺开所有 Knowledge；
- Knowledge-level 图默认从当前对象或明确范围展开；
- 图必须从一个具体任务开始：理解邻接、比较两个 Groups、沿路径探索或检查关系；
- 全库视图可以存在，但必须有 Anchor、Scope、List equivalent 和返回现场；
- “好看”不是验收，用户能解释为什么出现每条边才是验收。

来源：

- [Obsidian Graph View 官方说明](https://obsidian.md/help/plugins/graph)
- [社区讨论：Is graph view really useful?](https://www.reddit.com/r/ObsidianMD/comments/1kbgrs1/is_graph_view_really_useful/)
- [社区讨论：Making Graph View Useful](https://www.reddit.com/r/ObsidianMD/comments/1tuaxqf/making_graph_view_useful/)

## 1.2 层级和关系不是二选一

**观察事实：**Zotero 允许同一 item 位于多个 hierarchical collections，并明确说明这样不会复制 item；Capacities 区分人工判断 membership 的 Collection 与按规则更新的 Query。

**产品推论：**

- 层级负责建立稳定阅读顺序；
- 关系负责表达跨层级的语义连接；
- 同一 Knowledge 可以多 Placement，不复制正文；
- 用户选择的成员、动态规则结果与正式 Relation 不能使用同一“包含”概念；
- Product Surface 不应让用户先设计类型系统，才能开始组织知识。

来源：

- [Zotero Collections and Tags](https://www.zotero.org/support/collections_and_tags)
- [Capacities Queries vs Collections](https://docs.capacities.io/faq/editing/queries-vs-collections)
- [社区讨论：Anytype Collections vs Types](https://www.reddit.com/r/Anytype/comments/1p1ybv7/collections_vs_types/)

## 1.3 AI 查询很强，但查询层本身不是长期知识库

**观察事实：**NotebookLM 的官方模型把本次选用 Sources、回答中的 citation 和 Save to Note 分开。社区反馈同时出现组织 notebooks / sources 困难、原始来源阅读割裂、长期项目之间 sources 隔离、回答很强但缺少持续整理等问题。

**产品推论：**

- Ask 必须是一项全局能力，而不是产品首页；
- Requested、Effective 与 Used Context 必须可区分；
- Citation、保存 Answer、形成 Knowledge、更新 Overview 和建立 Relation 是不同动作；
- 同一 Source / Knowledge identity 可以跨 Groups 使用，不能被 notebook 边界复制；
- AI 的价值是帮助理解并回到知识，不是制造更多聊天记录。

来源：

- [NotebookLM：Use chat](https://support.google.com/notebooklm/answer/16179559?hl=en)
- [NotebookLM：Create and add notes](https://support.google.com/notebooklm/answer/16262519?hl=en)
- [社区讨论：The Biggest Workflow Gaps in NotebookLM](https://www.reddit.com/r/notebooklm/comments/1rale3g/the_biggest_workflow_gaps_in_notebooklm/)
- [社区讨论：NotebookLM for a whole-life knowledge base](https://www.reddit.com/r/notebooklm/comments/1qhwmvi/notebooklm_is_great_for_projects_but_what_are_you/)

## 1.4 “AI 看过全部资料”不能成为默认假设

**社区信号：**有用户报告大型来源只被部分处理，或无法知道本次回答实际覆盖了什么。单一讨论不能证明平台普遍行为，但它暴露出一个通用可信度问题：用户容易把“已上传”误解成“本次回答完整使用”。

**产品推论：**

- `已保存`、`已解析`、`可检索`、`本次使用`和`足够回答`必须分开；
- Coverage 说明缺失范围，不显示虚构精确 confidence；
- 索引 partial 时必须说明本次可见边界；
- 无法穷尽时给诚实的 partial / indeterminate，而不是“知识库里没有”。

来源：

- [社区讨论：NotebookLM limitations](https://www.reddit.com/r/notebooklm/comments/1l2aosy/i_now_understand_notebook_llms_limitations_and/)

## 1.5 自动组织可能降低维护成本，也可能让理解变成被动消费

**社区信号：**有学习用户担心自动生成 Overview / Mind Map 给出了组织结果，却跳过用户主动组织知识的过程。该信号属于观点和学习假设，不是本产品结论。

**产品推论：**

- AI 可以生成 Overview Proposal，但用户可以直接编辑 accepted Overview；
- AI 可以建议 Topic、Relation 和 Placement，但不能静默改变当前结构；
- 产品不强迫所有人手工整理；
- 产品也不能把“生成了结构”冒充“用户形成了理解”。

来源：

- [社区讨论：NotebookLM critique from a learning professional](https://www.reddit.com/r/notebooklm/comments/1plovfe/notebooklm_critique_from_a_learning_professional/)

## 1.6 研究证据没有证明什么

以上资料不能证明：

- 本产品一定比 Obsidian、NotebookLM、Anytype、Capacities 或 Zotero 更好；
- 用户一定理解 Knowledge Group、Placement 或 Relation statement；
- 方向 3 + 2 的最终视觉比例；
- Group-level resting Network 一定优于其他入口；
- Knowledge Paper 一定优于卡片；
- 五个日常概念足够；
- 用户愿意长期维护 Overview、Relation 或 Evidence；
- 本产品已经有留存、学习或商业效果。

这些只能通过真实个人知识库和连续任务验证。

## 1.7 研究信号强度

| 问题信号 | 类型 | 严重度 | 频率信号 | 证据置信度 | 产品杠杆 |
|---|---|---|---|---|---|
| 全局图规模增长后成为低解释力节点云 | 产品 UI / workflow | 高 | 中高 | 中；官方模型 + 多个社区讨论 | 高；决定 Network 本体 |
| hierarchy、links、types、collections 需要用户自行协调 | 组织与 onboarding | 高 | 中 | 中；官方复杂度 + 社区讨论 | 高；决定五个日常概念 |
| AI 查询强，但 notebooks / sources / outputs 难形成长期结构 | 产品 workflow / missing structure | 高 | 中 | 中；官方分权 + 多个社区讨论 | 高；决定 Ask 与 Library 关系 |
| 已上传不等于本次完整可用，覆盖范围难判断 | reliability / transparency | 高 | 低到中 | 低到中；通用风险 + 少量报告 | 高；决定 Coverage contract |
| 自动 Overview 可能给出组织结果，却没有形成用户理解 | 用户能动性 / learning hypothesis | 中 | 低 | 低；观点型证据 | 中；决定 Proposal 与直接编辑边界 |

这里的“频率信号”不是发生率。社区内容存在自选样本、发布偏差和版本差异，只能决定下一步研究优先级，不能作为市场规模或用户占比。

## 1.8 Source map 与证据缺口

| 来源 | 提供了什么 | 没有提供什么 |
|---|---|---|
| Obsidian、Capacities、Zotero、NotebookLM 官方资料 | 当前对象模型、Graph 范围、collection / query、citation / save 等明确行为 | 用户痛点频率、长期效果、为什么弃用 |
| Reddit 产品社区 | 真实工作流描述、反复出现的语言、规模增长后的摩擦 | 代表性样本、统一版本、可核验使用时长 |
| 三份本产品真实夹具 | 对空库直接写作、时效资格规则与稳定概念学习三类任务的结构压力 | 真实用户学习成本、长期维护意愿、留存 |
| 当前 Ardot 七屏 | 已选择的视觉气质和历史构图 | 可执行交互、错误状态、真实内容承载、完整产品覆盖 |
| 内部用户访谈 / telemetry | **当前没有** | 不能据此声称真实需求频率或成功指标 |

因此本轮可以收紧产品决定，但不能宣布产品已验证。

---

# 2. 产品本体：六句不可丢失的定义

1. 用户拥有的是一个 Knowledge Library，不是一组互相隔离的 projects、notebooks 或 chats。
2. Library 由一个个有边界、可整体进入的 Knowledge Groups 组成。
3. 每个 Group 通过 Overview 和递归 Topic hierarchy，从整体进入 Knowledge 与 Evidence。
4. 同一 Knowledge 可以在多个语境承担不同作用，但只有一份正文和 current identity。
5. Relation 是一条可读、有方向、有条件的知识陈述；Network 是这些陈述的探索表面。
6. Search、Ask 与 Explore 都必须把用户送回可继续阅读、编辑和核验的长期知识。

任何后续设计如果不能同时保留这六句，就不是这个产品。

---

# 3. 十四项关键产品决定

| ID | 产品决定 | 当前选择 | 当前状态 | 主要风险 |
|---|---|---|---|---|
| KPD-01 | 产品中心 | 一个稳定个人 Knowledge Library；冷启动先到 Catalog | **用户已确认本体；入口行为为产品推荐** | 未来能力再次把中心拉向聊天、任务、全图或自动 Resume |
| KPD-02 | 顶层结构 | Groups / Network 是同一 Library 的两种视图；All Knowledge 为次级 inventory | **产品推荐** | 用户可能把两者理解成两个系统，或把 inventory 当第三主视图 |
| KPD-03 | Group 定义 | 有边界、可长期整体进入的知识范围 | **用户已确认方向** | 退化成文件夹、标签或临时项目 |
| KPD-04 | 深入方式 | Overview → Topic Opening → Knowledge → Claim → Evidence 共用连续 Reading Shell | **用户已确认方向** | Topic Opening 过多造成层层中转 |
| KPD-05 | 默认知识形态 | 单一 content tree 的连续 Knowledge Paper；Outline、Block、Anchor 负责扫描与定位 | **产品推荐** | 长文难扫描；反向风险是卡片汤 |
| KPD-06 | 多语境复用 | 一条 Knowledge 多 Placements，不复制正文 | **产品推荐** | 用户不理解“同一条为什么在两处” |
| KPD-07 | Relation 含义 | 完整语义陈述，不是相似度或无类型链接 | **用户已确认方向** | 创建成本高、类型词汇过重 |
| KPD-08 | Network resting level | Library 先显示 Groups；Knowledge 图按范围展开 | **产品推荐** | Group 级可能隐藏有价值的弱连接 |
| KPD-09 | 3 + 2 组合与用户表面 | 一个 App Shell 承载连续阅读与按需关系；关系按 Quiet → Peek → Companion → Explore 增长，跨场景携带 Return Envelope；用户只见一个`知识库`、五个日常概念与`搜索 / 提问 / 添加` | **用户已确认方向；语言为产品推荐** | 转场过多、Companion 抢占阅读、内部 Scene / Surface 术语外露，或不同 Scene 重新变成孤立页面 |
| KPD-10 | AI 位置 | Ask 是随处可调用能力，不是聊天首页 | **用户已确认方向** | AI 价值不够显眼 |
| KPD-11 | AI 与真相 | Answer / Proposal 不自动推进 Current Knowledge | **产品推荐** | 写回显得慢；反向风险是静默覆盖 |
| KPD-12 | 未知与冲突 | Question Knowledge 与 Conflict 可长期存在 | **产品推荐** | 对简单知识库显得过重 |
| KPD-13 | 维护方式 | 变化在相关上下文出现，不以 Inbox / Review 驱动首页 | **产品推荐** | 低频用户可能错过重要变化 |
| KPD-14 | 所有权 | 本地 current knowledge、可导出可恢复；云与 AI 是增强 | **产品推荐** | 实现责任高，但不应变成产品表面负担 |

---

# 4. 十一个高影响选择

## 4.1 一个 Library，而不是多个互相隔离的 notebooks

**推荐选择**

- 每条 Knowledge、Source 和 Relation 在 Library 内拥有稳定 identity；
- Group 是语境和进入范围，不是数据孤岛；
- Ask 默认尊重当前 Scope，需要扩张时显式说明；
- 同一内容跨群复用不重新导入。
- 冷启动、正常重开和新窗口先进入 Stable Library；最多一条安全 Resume 由用户选择后才恢复深层现场；
- 普通 Open Group 进入 Current Overview，Continue 才恢复该 Group 内最近安全场景；
- Resume、Pin、Recent、Saved View、Saved Path 与 Recovery 分权，任何快捷入口都不能替代 All Groups。

**不选择**

- 每个 Group 拥有独立数据库；
- 每个 notebook 重新上传一份 Sources；
- “全库模式”和“项目模式”维护两套真相。
- 打开应用自动深开上次页面，把用户挡在稳定目录之外；
- 用星图、Recent feed、推荐或待整理列表替代 All Groups。

**理由**

用户要求的是知识网络。若 Group 之间只有视觉连线、底层内容却被隔离，关系无法真正复用，AI 也无法形成连续理解。

**反转条件**

只有当真实用户明确需要彼此不可见、不同所有权或不同安全边界的数据空间时，才增加多个 Libraries；不能为导航方便复制数据边界。

## 4.2 Overview 是可编辑导读，不是自动摘要

**推荐选择**

Overview 先回答范围、结构、稳定入口、关键未知与跨群出口。每个 Group / Topic scope 至多有一个 Current Overview identity；Editorial prose、Structure projection 与 Reference 分权。AI 可以提出局部变化建议，用户可直接编辑 Current Overview。

**不选择**

- 纯自动摘要；
- Recent feed；
- 卡片 Dashboard；
- 系统根据点击量自动重排的“最重要内容”。

Bare Overview 是完整合法状态：没有用户 prose 时只诚实显示真实 structure 与写作入口，不用 AI 成熟文案填空。Overview 中需要独立 Evidence、Relation、复用或修订节奏的判断提升为 Knowledge，原位置保留 Reference。

**理由**

从 Overview 深入是用户明确需求。如果 Overview 只是对当前内容的即时压缩，它不能承担长期方向，也无法表达“为什么这样组织”。

**主要风险**

维护成本可能过高。产品必须允许“不写完整 Overview 也能开始”，并让 AI 提案按局部变化更新，而不是要求用户定期重写。

## 4.3 Topic 可以递归，但不强迫每层中转

**推荐选择**

- Topic 是 Group 内稳定分支；
- 显式打开 Topic 时提供最低必要 orientation，并与 direct structure / root Knowledge 位于同一连续阅读现场；
- 目录 Expand 不改变阅读位置；
- 用户可以从 Overview、Search、Ask、Evidence、Relation 或 Resume 直接进入 Knowledge / Anchor；
- Up 与 Back 分开。

Groups 不结构性嵌套：Group 内的阅读深入由 Topic 承担；两个独立范围之间的“子领域、基础、组成或应用”用完整 Group Relation 表达；只为在 Catalog 中一起浏览则使用 Saved View。

**不选择**

- 所有层都变成完整页面；
- Topic 与 Subgroup 混用；
- 只允许固定三层；
- 无限 nesting 但没有 Overview 和返回语义。

**反转条件**

若真实夹具证明深层 Topic Overview 只增加点击、不增加方向，应允许更多层仅作为结构节点；但仍不能删除丰富层级本身。

## 4.4 Knowledge Paper 优先于原子卡片墙

**推荐选择**

一条主要理解任务对应一篇连续可读 Knowledge Paper。Orientation、Outline、正文与 Claim view 来自同一 Current content tree；Section、Block、Claim 和 Anchor 支持编辑、引用和关系，但阅读时不都显示成卡片。

**不选择**

- 每段自动成为知识对象；
- 每个 Claim 都用独立卡片表示；
- 为图谱密度主动把长知识拆碎。

**理由**

方向 3 的价值来自阅读深度和上下文连续性。若所有内容都原子化，Overview 到 detail 会变成 Overview 到更多卡片，无法承载复杂论证、条件和证据。

**主要风险**

长文可扫描性下降。正确解法是 section hierarchy、local outline、stable Anchor、Find 和局部关系，不是按字数、token 或 AI chunk 自动拆成正文副本。Anchor 是 locator，不是新的 Knowledge identity；歧义、失效和身份变化不能静默跳转。

**需要用户明确确认**

这是 v6 中影响视觉与编辑体验最大的尚未直接确认选择之一。

## 4.5 同一 Knowledge 多 Placement，而不是复制

**推荐选择**

同一 Knowledge 在不同 Group / Topic 可以拥有不同 contextual summary、role、neighbor priority 和 return target，但正文、current revision、Evidence 与 identity 相同。

**不选择**

- “复制到另一个群”；
- 自动同步的镜像卡片；
- 用 symbolic link 掩盖用户不知道自己是否在编辑原文。

**理由**

知识网络的真实价值之一，是同一理解能在不同语境承担不同作用。复制会让来源、AI 查询、Relation 和历史迅速分叉。

**主要风险**

用户可能误以为两个入口是两份内容。所有入口必须明确“同一知识 · 在这里作为……”，并能查看其他 Placements。

## 4.6 Relation 先是一句话，Graph 才是一条线

**推荐选择**

正式 Relation 至少拥有 endpoints、direction、完整 statement、必要条件、formation basis 和 standing。Candidate 与 Current 分开；共享位置、来源支持、引用、共现、Search / Ask route 各自保留，不混成语义边。

**不选择**

- `related_to`；
- embedding similarity 直接入图；
- 被同一次 Ask 使用就连边；
- 用颜色和箭头替代可读语义。

**理由**

用户要求“可以看见关系”，但可见不等于可理解。没有陈述的边只能证明系统检测到连接，不能解释连接对理解有什么意义。

**主要风险**

历史 25 个 Knowledge relation types 和 11 个 Group relation types 已降为 Experimental Appendices。v6 只冻结六类自然语言意图、完整句法和生命周期；没有真实测试前不把精确 registry 固化到默认 UI 或 schema。

## 4.7 Library Network 以 Group 为 resting level

**推荐选择**

- R3 Library Network 默认显示 Current Groups 和 Current Group Relations；没有群关系合法；
- Knowledge-level 网络从当前 Knowledge、Group、Saved View 或 Pair 展开；
- Shared Knowledge 是动态观察，不自动变成 Group edge；
- 0 条用诚实文本而非空星云，1 条用完整句，少量关系才进入图；
- Graph 与 List 等价。

`All Groups`始终是 exhaustive Catalog；Pins、Resume、Recent 和 Saved Views 只是 Lens。Saved View 可以手工策展或按规则动态返回 Groups，但不拥有 Group、不创建 Relation，也不递归嵌套成第二棵目录树。

`All Knowledge`是按 Knowledge identity 浏览的次级完整 inventory，用于找回、多 Placement 检查和独立知识浏览；它不是第三个主视图、第二棵层级或卡片墙首页。Resume 最多一条且只恢复安全 committed scene；Pin 只表示用户固定；Recent 只记录成功 Open；Saved View / Saved Path 来自用户显式保存；Recovery 保护未提交内容，六者不能用一个“继续”区域混合。

**不选择**

- 默认显示全库所有 Knowledge；
- 以节点度数自动决定重要性；
- 关系越多越成功；
- 用美观布局掩盖 edge 无法解释。

**主要风险**

用户可能想在全局发现意外知识连接。产品可以提供明确的`展开到 Knowledge`或 Saved View，但不能让这一需求破坏 resting clarity。

## 4.8 AI 查询必须能返回知识，而不是被困在聊天

**推荐选择**

一次 Ask 至少说明 scope、used knowledge、claim-level basis、coverage 和 unknowns，并提供互相独立的动作：保存回答、写入现有知识、形成新知识、保存问题、建立关系、采纳 Resolution。用户可以只阅读答案并离开，不被强迫写回。

**不选择**

- Chat history 作为主要资产；
- 一个`保存全部`按钮；
- 回答自动更新 Overview；
- 模型 confidence 代替 coverage；
- 为解释回答制造虚假 Knowledge Route。

**理由**

AI 查询是用户明确需求，但知识库的长期资产不是每次对话。只有回答能够回到现有结构、被选择性写回并保持依据，AI 才与知识库真正汇合。

**主要风险**

分权动作可能显得繁琐。默认可以只显示`保存回答`和`用于知识`，后者再展开精确目标；内部仍必须按不同对象结算。

## 4.9 无 Group 的 Knowledge 是独立知识，不是 Inbox

**推荐选择**

在 Library 直接写下的 Current Knowledge 可以没有 Placement，并稳定出现在`独立知识`。它是由零 active Placements 推导的 Library view，不是新类型、状态、待办或清理队列；Group archive 不结束 Placement，也不会把整群知识重新分类为独立。

**不选择**

- 保存前强迫用户先建或选择 Group；
- 无 Group 内容只能通过 Search 找回；
- 自动进入带红点和数量压力的 Inbox；
- AI 按相似度自动移动到某个 Group。

**理由**

Knowledge identity 应先于组织位置。第一条知识必须能直接写、立即保存并在 Library 再次找到；延迟决定 Placement 是合法使用方式，不是未完成工作。

**主要风险**

成熟 Library 中独立 Knowledge 可能过多。约 10 条后只在 Library 显示少量继续项和`查看全部`，达到 100 / 10K 量级时使用 List、Search、filters 与显式批量 Placement；首页不显示待整理数量，具体阈值仍需验证。

**反转条件**

只有真实测试证明 Search-only 在空库、离线与 index partial 下仍不会降低保存信任，才考虑移除这一入口。

## 4.10 Ask 是 Answer Paper，Query history 不自动成为知识

**推荐选择**

Ask 从当前知识现场发起；提交后 Answer 成为同一 Library Shell 中的连续 Paper。用户可以从具体 Claim 检查 Knowledge / Source、进入 Relation Explore，并精确回到原 Claim。普通 Query Workspace 只为本地恢复和审计保留，不进入 Library、Network 或未来回答真相；Saved Answer Snapshot、Question 与 Current Knowledge 必须显式分权。

**不选择**

- 聊天首页和无限气泡历史成为 AI 主体验；
- 每次对话自动保存为 Library object；
- 点击引用或进入图谱后无法回到原 Claim；
- retrieval jump 画成正式 Relation；
- 保存 Answer Snapshot 后自动成为未来 Ask 的依据。

**理由**

用户需要的是“向自己的知识提问并继续理解”，不是积累另一套聊天资料。只有 Context、Claim support、Network selection 和 Return 连续，AI 查询、关系探索与长期知识才属于同一个产品。

**主要风险**

Answer Paper 可能让快速追问显得不如聊天轻。Composer 和 Follow-up 仍可保持轻量，但最新 Answer 应始终是主阅读对象，旧轮次折叠为 investigation lineage，而不是让消息流接管产品。

## 4.11 直接写作是 Current，保存资料不等于形成知识

**推荐选择**

用户自己的写作安全保存后直接成为 Current Knowledge；Edit Buffer、Recovery Checkpoint、Current Revision、Explicit Draft、Proposal 与 Sync 分权，只有 safe commit 推进 Current，History 按有意义编辑会话分组，Restore 以新 revision 向前恢复。外部材料先成为可返回 Source。Highlight / Annotation、添加 Evidence、形成新 Knowledge、更新旧 Knowledge、Placement、Relation 与 Overview Diff 分别提交。AI 可以起草和提示重要变化，但 zero-yield 合法，不建立“抽取卡片 → 逐条接受”的审批队列。

**不选择**

- 用户写下的内容也必须先进入 Draft / Candidate；
- 用一个“已保存”同时表示 local commit、sync、index 与 AI analysis；
- 把 Recovery 当作另一条 Draft Knowledge，或恢复旧版时抹掉后续历史；
- Source 保存、解析成功和 Knowledge formation 被一个`确认捕获`合并；
- Highlight 自动成为 Knowledge；
- 给旧 Knowledge 加 Evidence 时自动改写正文；
- 以提取数量、置信度或 Review 清零衡量形成质量。

**理由**

知识库必须能准确回答“这是我写的理解、外部材料、原文标记，还是 AI 建议”。让用户直接拥有自己的写作，同时允许资料只作为资料存在，才能避免系统用自动整理取代思考。

**主要风险**

分权可能让用户担心操作变多。产品应根据当前现场只突出一个自然动作，并让 Evidence-only、new Knowledge 和 semantic update 使用同一清楚 Preview；底层事务分开，不等于把全部术语暴露给用户。

---

# 5. 过度设计审计

## 5.1 十四类 Primary Resources

**为什么可能过重：**对象名称多，容易让产品像数据库设计文档。

**v6 修订：**不再保留十四类平级 Primary Resources。当前只有 Group、Knowledge、Relation、Source 四类 canonical truth families；Library 是根，Topic 是 Group 内稳定结构身份，Overview、Placement、Question state、Answer Run、Proposal、Change Set、View 与 Saved Path 都由 owner / supporting layer 承担。

**仍保留的深度：**被降级的概念继续拥有必要 identity、history、delete、export 或 restore 责任，但不能因为内部精确就提升为导航、创建菜单或用户心智模型。

## 5.2 25 + 11 Relation registries

**为什么可能过重：**用户不会为了连两条知识先学习 ontology。

**v6 修订：**主产品只保留 Support / Explain、Challenge / Qualify、Extend / Refine、Apply / Implement、Example / Instance、Compare / Contrast 六类意图。精确 types 只有在真实使用证明能稳定区分并改变行为后，才从实验附录升级。

**不变底线：**不能退回无语义`相关`。先问“你想表达什么”，再回读 endpoints、direction、qualifier 和完整 statement。

## 5.3 Question / Resolution / pursuit

**为什么可能过重：**大部分普通笔记不需要求解状态机。

**v6 修订：**Question 是 Knowledge 的一种 role，不再作为平级对象系统。长期问题仍可区分“现在有可用回答”“是否继续追问”“依据是否变化”。

**Surface 约束：**普通问题仍然只是一条可读 Knowledge；只有用户保存为长期问题，才逐层显示标准、状态和复核。

## 5.4 Evidence 与精确定位

**为什么可能过重：**并非所有个人想法都需要 citation。

**当前保留理由：**AI 查询、来源变化和研究型知识需要返回原位置；没有它，可信度只能靠来源标题和模型口吻。

**Surface 约束：**用户直接写的想法可以是 authored basis；缺少外部来源不阻止写作。Evidence 只在影响判断时展开。

## 5.5 Local-first、Export 与 Restore

**为什么可能过重：**这是大量实现责任，用户也已表示不必过度讨论隐私。

**当前保留理由：**本地不仅是隐私选择，也保证长期知识在 AI、网络或供应商不可用时仍然存在。

**Surface 约束：**不把 storage health、hash 或 package schema 放在日常界面；它们属于 Forensic 层。

## 5.6 审计结论

v6 已经把“内部正确性写得比用户产品选择更响”作为真实结构问题处理。正确修正不是删除长期责任，而是：

1. 先确认十一个高影响选择；
2. 默认 Surface 只围绕阅读、探索和调用；
3. 四类 canonical truth families 与 Topic 以外的责任留在 owner context；
4. 精确 relation registry 保持实验状态；
5. 任何新增对象先证明不能由现有模型承担；
6. 任何新增首页模块先证明它不是维护负担。

---

# 6. 用户日常看到的产品循环

## 6.1 进入

用户每次先回到`知识库`：最多一条安全的`继续上次…`、少量固定内容与完整`知识群`目录同时可见。选择知识群时从当前概览开始；只有选择`继续`才恢复该知识群内的深层现场。`最近打开、已保存视图、全部知识`是次级入口，不接管知识库。进入知识群后首先看见概览：范围、主要结构、稳定入口、关键未知和少量跨群出口。

## 6.2 深入

用户沿 Topic hierarchy 进入一篇 Knowledge Paper。当前位置、上一级、正文结构和返回路径始终清楚；Evidence 和 Relation 默认安静。

## 6.3 探索

当用户明确查看连接时，关系从一句话 Peek 增长为 Companion 或 Relation Space。只有显式 Open 才改变阅读对象；关闭后回到原 Anchor。

## 6.4 查询

用户从 Library、Group、Topic、Knowledge 或 Group Pair 提问。Answer 说明实际范围、使用的知识、主要依据、覆盖情况与未知。

## 6.5 形成

用户选择性保存 Answer、修改现有 Knowledge、形成新 Knowledge、保存 Question 或建立 Relation。每项后果独立，不存在自动全部写回。

## 6.6 演化

来源、条件或理解变化时，产品只在受影响的位置提示 Review。用户检查 Diff、Evidence 和影响后决定维护、修订、结束或保留历史。

这个循环没有 Inbox 清零、每日 Review、任务完成率或 AI feed。产品的复访理由是继续理解，而不是维护系统。

---

# 7. 对后续视觉设计的约束

本文件不启动视觉工作，但冻结未来设计必须证明的内容：

1. 一个稳定 App Shell 承载 Library、Continuous Reading、Relation Space、Answer 与 Source Reader；Scene 不是五个一级 Place；
2. Primary、Companion、Inspector、Overlay、Decision / Recovery 与 Utility 的任务责任清楚，Back / Up / Close / Library 后果不混淆；
3. Screen 不能只证明一个漂亮 Overview；必须证明 Overview → Topic → long Knowledge → Evidence；
4. Relation Space 必须显示完整 statement、direction、standing 和 exact return；
5. 同一 Knowledge 的两个 Placements 必须可辨，但正文 identity 相同；
6. Ask 必须显示 scope、basis、coverage 和原子写回；
7. Group-level relation、Shared Knowledge、cross-group exit 与 Candidate 必须分层；
8. Quiet、Peek、Companion、Explore 必须由动作触发，不是固定多栏布局；
9. 长标题、限定条件、partial / offline / historical 状态必须来自三份真实内容夹具；G100 / K10K 另用 synthetic scale fixture 证明；
10. List、keyboard 和 narrow screen 不能得到更弱的关系语义；
11. 完整度按 DPB-01–18 的 entry、result、failure、recovery、return 与责任等价计算，不按 Screen 数量计算；
12. 每个 DPB 同时交付真实 default / partial / error / return copy、disclosure level 与 accessible name；占位文案不算设计证明；
13. 现有 Ardot 七屏全部只作 Visual Specimens；Screen 2 保留视觉母体，Screen 3 保留艺术气质，不沿用`知识星图、双镜工作区、八类对象、AI 新析出、提问 / 收录`等旧用户语言；
14. 用户确认本文件前，不制作新的视觉选项或原型。

---

# 8. 用户确认页

## 8.1 已经可以视为确认的方向

- 产品本体是个人知识库；
- 知识以一个个知识群存在；
- 知识群之间的关系可以看见；
- 知识具有从 Overview 到细节的丰富层级；
- AI 查询与知识网络探索都是核心动作；
- 视觉方向以 3 的层级阅读结合 2 的关系空间；
- 当前先定义产品，不马上制作原型。

## 8.2 最值得先反对或确认的十一项

| 编号 | 推荐默认 | 如果不同意，最可能的替代 |
|---|---|---|
| 1 | 一个 Stable Library 与一个稳定 App Shell；用户可见地点固定叫`知识库`，以`知识群 / 知识网络`两视图进入；冷启动先到完整目录，显式`继续`才恢复深层现场 | 多个互相隔离的 Libraries / notebooks、每个功能一套页面、自动深开或推荐 / 全图首页 |
| 2 | 无 Group 的 Current Knowledge 以`独立知识`合法存在 | 强制归群、Search-only 或 Inbox |
| 3 | Overview 是可编辑导读；Editorial / Projection / Reference 分权 | Overview 主要由 AI 自动生成或结构刷新直接改写用户文字 |
| 4 | Topic Opening 与单一 content tree 的 Knowledge Paper 构成连续阅读；Anchor 负责精确深入 | 更扁平的层级、强制中转或原子卡片优先 |
| 5 | 同一 Knowledge 多 Placements | 每个 Group 保留自己的内容副本 |
| 6 | Relation 是完整语义陈述；Candidate 与 Current 分开 | 简单双链、相似度线或 AI Candidate 直接进图 |
| 7 | Network 默认以 Current Groups / Relations 为全库层；没有关系合法 | 默认展开所有 Knowledge 或用相似度填满空图 |
| 8 | Ask 不自动改变当前知识 | AI 默认整理并直接更新知识 |
| 9 | 维护提示留在相关上下文 | 需要独立 Inbox / Review 首页 |
| 10 | Ask 是同一 Shell 中的 Answer Paper；Query history 不自动成为知识；Answer ↔ Network 可逆 | 聊天首页、自动保存所有对话或 Answer / Graph 分离 |
| 11 | 用户直接写作就是 Current；Buffer / Recovery / Draft / Proposal / Sync 分权；Source save、Annotation、Evidence、Formation 与 semantic update 分权 | 所有输入统一进入 AI 抽取 / Review 流程，或用一个保存状态混淆所有后果 |

这十一项共同决定五个 Scene families 和 DPB-01–18 的证明结构；它们在用户表面固定表达为一个`知识库`、五个日常内容概念`知识群 / 主题 / 知识 / 关系 / 来源`和三个全局动作`搜索 / 提问 / 添加`。Scene、Surface role、Current、Placement 与 Proof Bundle 是设计责任语言，不是额外要求用户学习的产品概念，也不构成第十二项选择。

## 8.3 什么不需要现在决定

- 颜色、字体、圆角、动效和图形语言；
- 最终品牌名；
- 具体技术栈、数据库或模型；
- 第一批实现顺序；
- 是否制作可点击原型；
- relation type 的最终中文措辞；
- 每个 Inspector 的具体布局。

这些决定不应抢在产品本体之前。

---

# 9. 与 v6.0 的关系

本审阅稿不新增对象、页面或能力。它只把 v6.0 中的推荐默认压缩为可反对、可确认的选择：

- `v6.0 §0–3`定义产品中心、决定账本和单一骨架；
- `v6.0 §4–10`定义日常概念、canonical truth families、核心行为、真相边界与所有权；
- `v6.0 §11`定义 3 + 2 的产品含义与表面架构；
- `v6.0 §12–15`提供旅程、状态、指标与 32 条核心验收；
- `v6.0 §16–17`提供研究边界、文档权威与设计 Gate；
- `AI-native-个人知识库-知识群层级、目录规模与结构演化合同-v1.0.md`、`AI-native-个人知识库-AI查询、知识探索与返回连续性合同-v1.0.md`、`AI-native-个人知识库-知识进入、来源保存与知识形成合同-v1.0.md`、`AI-native-个人知识库-关系、群级网络与探索连续性合同-v1.0.md`、`AI-native-个人知识库-Overview、连续阅读与知识正文合同-v1.0.md`、`AI-native-个人知识库-Library入口、目录浏览与继续阅读合同-v1.0.md`、`AI-native-个人知识库-表面架构、场景家族与完整设计证明合同-v1.0.md`与`AI-native-个人知识库-用户可见信息架构、产品语言与复杂度披露合同-v1.0.md`分别深化层级结构、查询—探索连续性、知识进入、关系网络、Overview—正文—编辑连续性、Library 日常入口—目录—继续连续性、统一 Shell—场景—表面—状态—完整设计证明，以及用户信息架构—产品语言—复杂度披露；
- 本文只承担进入视觉设计前的产品决策审阅。

发生冲突时，按用户最新明确意图 → v6.0 → `文档权威注册表`中允许的证据与附录处理；本文不能暗改 v6.0。

---

# 结论

当前产品最值得保留的不是功能数量，而是一个清楚的认知秩序：

> **先在知识群中获得整体方向，再沿层级读到具体理解；需要连接时打开有语义的关系空间；需要调用时让 AI 在明确范围和依据上回答；最后把有价值的结果选择性地变成长久知识。**

如果这条秩序成立，方向 3 + 2 就有产品意义；如果它不成立，再漂亮的关系图、再强的 AI 和再完整的对象模型也只会组成三个并排的功能。
