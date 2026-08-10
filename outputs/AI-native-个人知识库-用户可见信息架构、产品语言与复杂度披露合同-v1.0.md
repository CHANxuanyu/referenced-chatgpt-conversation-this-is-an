# AI-native 个人知识库

## 用户可见信息架构、产品语言与复杂度披露合同 v1.0

> Canonical：`AI-native-个人知识库-终局产品设计文档-v6.0.md`  
> 文档状态：**ACTIVE_APPENDIX；已完成 Canonical 同步、注册与相邻责任划分**  
> 深化范围：v6 §0.5、§3、§11、§13、§15 AC-01–AC-32 与 Surface Active Appendix 的用户可见表达  
> 本合同拥有：用户可见信息架构、日常概念、动作命名、结果与错误文案责任、复杂度披露、accessible naming 与 DPB copy proof  
> 本合同不拥有：Group / Knowledge / Relation / Source 真相、对象 schema、视觉造型、具体布局、品牌名、技术栈、研发排期或可点击原型  
> 迁移证据：`AI-native-个人知识库-v6用户可见语言迁移审计-v1.0.md`  
> 日期：2026-08-10

---

# 0. 执行结论

## 0.1 一句话

**用户不需要学习知识数据库，仍然必须准确知道：我在哪里、我正在看什么、这个动作会改变什么、什么没有完成、怎样回到原处。**

## 0.2 冻结的 40 项决定

1. **唯一稳定地点在界面中固定叫`知识库`。**不再出现 Home、首页、工作台、Atlas 或知识星图作为并列产品中心。
2. **用户日常只需要五个核心内容概念：知识群、主题、知识、关系、来源。**
3. **`知识库`是地点，`概览、证据、回答、路线、历史、建议`是任务词。**它们不成为平级本体。
4. **内部模型可以使用 Current、Placement、Anchor、Proposal、Scene、Surface、DPB 等精确术语。**完成普通任务不得要求用户理解这些词。
5. **三个全局动作固定为`搜索 / 提问 / 添加`。**不增加 Command、Review、Explore 或 Inbox 作为第四动作。
6. **Explore 是从当前知识、关系或回答进入的任务，不是全局模式。**
7. **Search、Ask、Add 不使用一个含混 omnibox。**若视觉共用位置，仍须先显式选择动作，并在输入前说明后果。
8. **动作标签优先使用结果动词。**`保存来源`、`保存回答`、`形成知识`、`更新知识`不能统一写成`保存`。
9. **`查看`只表示临时检查，`打开`才改变主要对象。**Inspect / Open 的内部差异必须在用户动作上成立。
10. **`回到上一处 / 回到上一级 / 关闭当前查看 / 回到知识库 / 继续上次…`分别命名。**不能用一个无目标的`返回`承担全部后果。
11. **Calm 状态只有一个主要任务和一个主要动作。**次要动作安静可达，不与主动作竞争。
12. **复杂度固定为 Calm、Focused、Decision、Forensic 四层。**它们是披露责任，不是用户模式或页面名。
13. **复杂信息只因当前任务需要或用户明确动作出现。**不能因为内部有字段、状态或 AI 结果就常驻。
14. **Calm 顶层可见核心概念不超过五个，主要状态句不超过一条。**
15. **数量只在支持目录、范围、覆盖、筛选或影响判断时出现。**笔记数、关系数、引用数和 AI 处理量不作为首页价值证明。
16. **AI 输出固定区分五种声音：你的知识、来源原文、本次外部资料、基于知识推断、尚未采用的建议。**
17. **Source truth 与 Knowledge truth 使用不同动词。**`来源写道`不等于`你采用的知识是`。
18. **Current / Proposal / History 用日常后果表达。**分别是`当前采用的内容 / 尚未改变知识的建议 / 当时的版本`。
19. **用户直接写作经安全提交后就是知识。**界面不称`想法、未完成知识、待采用内容`，也不要求采用自己的文字。
20. **零 Placement 的 Knowledge 固定叫`独立知识`。**不使用`未归类、尚未整理、Inbox`。
21. **保存来源本身是成功。**解析、整理或形成知识失败时，必须继续承认来源已保存。
22. **保存 Answer 与形成 Knowledge 分权。**`保存这次回答`不参与当前事实；`形成知识 / 更新知识`才改变长期知识。
23. **Relation 在任何用户层都先以完整句表达。**Graph line、颜色、相似度和类型名不能替代陈述。
24. **Current / Suggested / Past Relations 使用文字与区域分层。**不能只用实线、虚线和透明度。
25. **Graph 与 List 使用同一对象名、关系句、筛选、选择和动作。**切换呈现不改变任务语言。
26. **Group 数、Knowledge 数、scope 和 coverage 必须带单位。**不使用含混的`共 1284 条`。
27. **错误文案固定回答三件事：什么仍然存在、什么未完成、现在能做什么。**
28. **partial / offline / unavailable 不清空输入、范围、选择和返回现场。**
29. **Empty 使用事实语言，不使用羞辱、完成率、激活、健康度或知识债务。**
30. **高后果动作必须说明改变、保留、恢复和失败隔离。**不能只给`确认 / 取消`。
31. **可见标签必须足以让视觉用户理解。**关键后果不能只藏在 tooltip、图标、hover 或 accessible name。
32. **accessible name 与可见主标签使用同一核心动词和对象。**语音输入可以用用户看到的名字激活动作。
33. **颜色、空间位置、线型、亮度和动画不能单独承担 truth、standing、direction 或 state。**
34. **responsive 只改变排布，不改变词义与动作后果。**mobile 不另造一套更弱的产品语言。
35. **产品价值不以`笔记、节点、星图`为中心词。**`笔记`只可出现在导入来源或用户原始文件语境。
36. **品牌隐喻不能替代信息。**Warm Paper 与 Relation Night 可以保留；星云、生命、成长等隐喻不能表达 Current truth。
37. **当前 Ardot 的`知识星图、双镜工作区、八类对象、AI 新析出、提问 / 收录`均不进入现行语言。**
38. **每个 DPB-01–18 必须登记 Default user copy、Disclosure level、error / partial copy、return copy 与 accessible name。**
39. **语言证明使用三份真实 fixture 和 synthetic G100 / K10K fixture。**抽象短标签、`Lorem ipsum`或只有按钮名不算证明。
40. **本合同不授权制作视觉或原型。**先确认用户概念、动作与语言证明，再进入 Surface Skeleton。

## 0.3 产品语言的两层权力

| 层 | 目的 | 允许内容 |
|---|---|---|
| Internal contract language | 精确定义 truth、identity、state、transition 与 evidence | Current、Placement、Anchor、Proposal、Surface、Return Envelope、DPB 等 |
| Product language | 让用户完成任务并理解后果 | 知识库、知识群、主题、知识、关系、来源，以及清楚动作和状态句 |

翻译不是删减责任。内部精度必须完整保留；界面通过用户可以判断的对象、结果与后果表达同一语义。

---

# 1. 用户可见信息架构

## 1.1 唯一稳定地点

App Shell 的固定地点名是：

```text
知识库
```

不显示：

- 首页；
- Home；
- 工作台；
- 知识星图；
- Atlas；
- AI 中心；
- 今日；
- 待整理；
- Review Inbox。

启动、正常重开、新窗口和`回到知识库`都落在同一个地点。`继续上次阅读 / 继续上次探索`是知识库中的一条入口，不是另一个首页。

## 1.2 两个主视图

| 内部责任 | 用户标签 | 用户问题 |
|---|---|---|
| Groups view | `知识群` | 我有哪些长期知识范围，从哪里进入 |
| Network view | `知识网络` | 这些知识群为什么相连，可以向哪里探索 |

两者是同一知识库的视图切换。切换前后的 scope、selection 和 filters 如能映射则保留；无法映射时用一句话解释，而不是假装成功。

不把`全部知识、来源、回答、路线、历史、设置`做成与`知识群 / 知识网络`同权的主视图。

## 1.3 三个全局动作

| 动作 | 用户承诺 | 输入前必须知道 |
|---|---|---|
| `搜索` | 找回已经存在的知识、来源或位置 | 当前搜索范围 |
| `提问` | 在明确范围内综合、比较或解释 | 本次将使用的范围与是否允许外部资料 |
| `添加` | 写下知识、建立知识群、保存来源或迁入内容 | 选择的入口会保存什么 |

禁止：

- `问任何事`同时承担 Search 与 Ask；
- `提问 / 收录`同时承担 Ask 与 Add；
- 根据输入内容静默猜测模式；
- 用 Enter 在未确认模式时产生不同写入后果。

## 1.4 Supporting navigation

次级入口按用户任务组织：

- `全部知识`；
- `独立知识`；
- `来源`；
- `历史与恢复`；
- `导入与导出`；
- `已归档`；
- `废纸篓`；
- `设置`。

`回答历史、最近搜索、已保存路线、视图`从相关位置或次级菜单进入，不加入主导航。

## 1.5 Shell 始终能被用户回答的问题

不暴露 Surface 模型，但用户必须始终能说清：

1. 我仍在同一个知识库吗；
2. 我当前看的是哪个知识群、主题、知识、回答或来源；
3. 我从哪里进入；
4. 关闭或返回会回到哪里；
5. 搜索、提问、添加和回到知识库在哪里。

---

# 2. 日常概念合同

## 2.1 五个核心概念

| 用户词 | 一句话解释 | 不是 |
|---|---|---|
| 知识群 | 一个值得整体反复进入、拥有边界和概览的知识范围 | 文件夹、标签、临时项目 |
| 主题 | 知识群中的一条理解分支 | 子群、独立数据库、强制中转页 |
| 知识 | 一个可以连续阅读、修改、引用和复用的理解单元 | 节点、卡片、AI chunk |
| 关系 | 两条知识或两个知识群为什么相连的完整陈述 | 相似度、无类型链接、同次访问 |
| 来源 | 原始材料及其版本、位置和可核验上下文 | 自动等于知识、统一附件卡 |

## 2.2 合法的支持词

这些词使用日常含义，不需要用户先学习本体：

| 用户词 | 责任 |
|---|---|
| 概览 | 先理解一个知识群或主题 |
| 证据 / 依据 | 检查一段结论为什么成立或受限 |
| 回答 | 一次提问的结果，不自动成为知识 |
| 问题 | 可以临时提问，也可以显式保存为长期未知 |
| 路线 | 用户保存的探索顺序，不等于关系 |
| 视图 | 一组查看条件，不拥有知识 |
| 历史 | 当时的版本与变化，不是当前真相 |
| 建议 | 尚未改变知识的系统或 AI 提议 |
| 独立知识 | 当前没有放入任何知识群的合法知识 |

## 2.3 默认禁止词

以下词只可出现在产品定义、工程、诊断、导出清单或高级帮助，不进入 Calm / Focused：

- canonical；
- Current Revision；
- Placement；
- Anchor / selector bundle；
- Proposal / Candidate；
- Projection；
- Query Context / Requested / Effective / Used；
- Claim Support / Coverage enum；
- Source Revision / Representation / Binding；
- Scene / Surface / Primary / Companion / Inspector / Overlay；
- Return Envelope / Workspace state；
- DPB / AC / SEC；
- RAG、embedding、chunk、vector、compiler、materialized view；
- node、edge、schema、enum、cardinality；
- lifecycle、epistemic、freshness、standing。

Forensic 可以显示技术词，但先给人话结论，再显示 ID、字段与内部枚举。

---

# 3. 动作语法

## 3.1 导航动作

| 用户动作 | 后果 | 不得混成 |
|---|---|---|
| `查看` | 临时检查摘要、关系或来源片段；关闭回触发点 | Open |
| `在旁边查看` | desktop 打开与当前阅读直接相关的内容 | 新地点 |
| `打开完整知识` | 改变当前主要阅读对象并进入访问历史 | 查看 |
| `在知识网络中打开` | 让关系探索成为当前主任务 | 切换模式 |
| `比较两个知识群` | 建立临时对照，不改变两端知识 | 建立关系 |
| `关闭当前查看` | 关闭临时内容并恢复触发控件 | Back / Up |
| `回到上一处` | 按访问时间恢复刚才现场 | 回到上一级 |
| `回到上一级` | 进入结构父级 | Back |
| `回到知识库` | 回到稳定 Library | 关闭窗口 |
| `继续上次阅读 / 探索` | 恢复一条安全 committed scene | 普通 Open |

只有一个通用箭头图标时，visible tooltip / accessible name 必须写出具体目标，例如`回到“记忆研究”概览`。

## 3.2 创建与保存动作

| 用户动作 | 产生什么 | 不产生什么 |
|---|---|---|
| `写下知识` | 一条可再次打开的 Knowledge | 不先成为 AI Proposal |
| `建立知识群` | 一个合法 Bare Group | 不自动生成成熟 Overview |
| `保存来源` | Source identity 与可返回材料 | 不自动形成 Knowledge |
| `保存这次回答` | Saved Answer Snapshot | 不改变 Current Knowledge |
| `形成一条知识` | 新 Knowledge | 不保存全部聊天 |
| `更新已有知识` | 对明确 target 的 Knowledge Revision | 不静默更新 Overview / Relation |
| `保存这个问题` | Question Knowledge | 不产生 Inbox debt |
| `建立关系` | 用户直接提交的 Current Relation | 不根据相似度自动入图 |
| `采用这项关系建议` | AI / Source Candidate 变为 Current Relation | 不批量采用其他建议 |
| `保存这条路线` | Saved Path | 不把点击序列变 Relation |

## 3.3 编辑与恢复动作

| 内部状态 | 用户语言 |
|---|---|
| Edit Buffer | `正在修改` |
| Recovery protected | `近期修改已在本机保护，尚未保存为这条知识` |
| Direct commit in progress | `正在保存` |
| Current Revision advanced | `已保存这条知识` |
| Sync pending | `已保存到本机，等待同步` |
| Projection lag | `搜索和概览正在更新；知识已经保存` |
| Explicit Draft | `草稿；不会用于默认回答` |
| AI Proposal | `建议尚未改变你的知识` |
| Historical revision | `正在查看当时的版本` |

禁止用一个`Saved`、绿色对勾或云图标同时表示 recovery、current、sync 与 index。

## 3.4 删除与结束动作

| 动作 | 用户后果 |
|---|---|
| `只从这个主题移除` | Knowledge identity、其他位置、关系、来源和历史保留 |
| `归档` | 从 current 默认浏览隐藏，可恢复，历史保留 |
| `移到废纸篓` | 暂时移除，可恢复，受影响引用可见 |
| `永久删除` | 删除明确目标；提交前列出不可恢复内容 |
| `标记为已结束` | 关系过去可能成立，当前不再成立 |
| `用新关系替代` | 建立 successor，旧关系留在历史 |
| `撤回这项关系` | 用户不再采纳，依据与历史保留 |

垃圾桶图标不能同时承担移除位置、归档、Trash 与永久删除。

---

# 4. 复杂度披露合同

## 4.1 Calm

用户只看到：

- 当前地点与对象；
- 主内容或完整 Catalog；
- 一个主要动作；
- 最多一个真正影响当前任务的状态句；
- 搜索、提问、添加和回到知识库。

默认隐藏：完整历史、全部关系邻接、所有来源版本、AI 候选、内部状态轴、技术诊断和影响矩阵。

Calm 不是无信息。scope、historical、read-only、partial save、不可逆后果等会改变行动的事实必须显示。

## 4.2 Focused

由选择、查看或展开触发，显示：

- 当前选择；
- 局部结构或关系；
- 当前段落的依据；
- 其他出现位置；
- 一句状态原因；
- 返回目标。

Focused 不自动显示全库邻接、全部历史、完整 forensic IDs 或所有 AI 建议。

## 4.3 Decision

用于将改变 truth、identity、membership、history 或可恢复性的动作。固定回答：

1. 现在依据哪个对象或版本；
2. 准备改变什么；
3. 哪些内容会保留；
4. 失败只会影响哪里；
5. 完成后去哪里；
6. 如何撤销或恢复。

Decision 不能被压成 toast，也不能只显示数量摘要。

## 4.4 Forensic

用户主动核验时才显示：

- stable ID；
-完整 revision chain；
- source representation、locator 与 binding；
- index / coverage / restore manifest；
- internal type / state；
-修复与诊断工具。

Forensic 仍先显示一句自然语言结论，例如：

> 这段引用在来源新版中移动了；系统已经找到唯一新位置，引用文字没有改变。

随后才显示 old selector、new selector 与 revision IDs。

## 4.5 信息预算

| 项目 | Calm 预算 |
|---|---:|
| 主要任务 | 1 |
| 主动作 | 1 |
| 顶层核心概念 | ≤ 5 |
| 强状态句 | ≤ 1 |
| disclosure control | ≤ 1 个主控件 |
| 建议 | 0；仅相关 cue |
| 技术词 | 0 |

数量不是绝对视觉计数，而是注意力责任。一个主动作可以拥有安静的替代路径；不能出现三个同权彩色 CTA。

---

# 5. Library 语言合同

## 5.1 Empty Library

标题：

> 这里还没有知识。

说明：

> 先写下你已经理解的一件事。你也可以建立知识群、保存一份来源，或迁入已有内容；以后再整理也可以。

动作顺序：

1. `写第一条知识`；
2. `建立知识群`；
3. `保存来源`；
4. `迁入已有内容`；
5. `提问`作为可达但不主导的动作。

禁止：

- `激活知识库`；
- `三步完成你的知识系统`；
- `上传资料让 AI 理解你`；
- `0 个节点`；
- `知识健康度 0%`。

## 5.2 Daily Library

视觉与阅读顺序固定为：

```text
继续上次…（最多一条，可无）
固定（可无）
全部知识群（必须完整）
独立知识（有内容时）
次级入口：最近打开 / 已保存视图 / 全部知识
```

`继续`卡必须写清：

- target；
- 当前 safe revision；
- 是继续阅读、探索还是回答；
- 会恢复到什么位置；
- 目标不可用时的降级说明。

`固定`不写`重要`，不影响 Ask 权重。`最近打开`不混入最近修改、AI 使用或后台变化。

## 5.3 Group entry

每个 Group entry 默认只承担：

- 名称；
- 一句 Boundary / orientation；
- 普通主体 Open；
- 有安全现场时的次级`继续`；
- 必须解释的 lifecycle 状态，例如已归档。

不默认显示：成熟度、健康度、置信度、关系数、笔记数、AI 活跃度、待整理数。

普通主体 Open 的可访问名称示例：

```text
打开知识群“认知科学”，从概览开始
```

Continue 示例：

```text
继续“认知科学”，回到“情境依赖检索”的证据段落
```

## 5.4 Independent Knowledge

标题固定：`独立知识`。

说明只在需要时出现：

> 这些知识目前没有放入知识群，但已经完整保存在知识库中。

禁止：

- 未归类；
- 待整理；
- Inbox；
- 零散笔记；
- 孤立节点；
- 建议尽快归档。

## 5.5 Groups ↔ Network

切换标签：`知识群 / 知识网络`。

Network 零关系状态：

> 当前知识群之间还没有已建立的关系。你仍然可以打开任何知识群，或比较两个知识群；系统不会用相似度补线。

Graph unavailable：

> 关系图暂时无法显示。下面的列表仍包含同一批知识群和关系。

List title：`关系列表`，不是`降级模式`。

## 5.6 G100 / K10K

大规模只说范围、数量、未显示原因与下一步：

- `全部知识群 · 120`；
- `当前显示 18 / 120 个知识群`；
- `还有 102 个未显示：94 个在当前范围外，8 个关系索引尚未完成`；
- `选择一个知识群开始查看关系`；
- `搜索覆盖 93 / 120 个知识群；完整目录仍可浏览`。

禁止`Top 20 核心知识群、AI 自动分区、知识库太大、孤立群、低连接价值`。

---

# 6. Continuous Reading 语言合同

## 6.1 路径与标题

自然路径示例：

```text
认知科学 › 记忆 › 检索机制 › 情境依赖检索
```

不显示 D0–D5、Scope L2、Topic Workspace 或 Node ID。

深层打开时仍能看到：

- 当前 Knowledge title；
- 所在 Group / Topic；
- `回到上一级`目标；
- `回到上一处`目标；
- 当前是否 historical。

## 6.2 Overview

日常标题固定`概览`。它先回答：

- 这个知识群想理解什么；
- 主要结构是什么；
- 从哪里开始；
- 哪些限制或未知值得先知道；
- 可以沿哪几条真实关系继续。

不显示`AI Overview、自动摘要、完成度、覆盖率、成熟度`。

用户编辑：`编辑概览`；直接保存成功：`已保存概览`。结构 projection 刷新：`已根据当前知识刷新结构；你写的概览没有改变`。

## 6.3 Topic Opening

用户只看见`主题`与自然 Opening，不看生命周期名称 Structural / Oriented / Authored。

Bare Topic：

> 这个主题目前只有结构，还没有单独的开场说明。

动作：`继续查看其中的知识`，不是`生成主题概览`作为强制门槛。

## 6.4 Knowledge Paper

正文使用`知识`，不使用笔记、节点或卡片。默认连续阅读，不显示 Block 边框和编号。

选中局部内容后可以显示：

- `复制此处链接`；
- `查看这一段的依据`；
- `从这里提问`；
- `把这一节变成独立知识`。

界面使用`这一节 / 这一段 / 此处`，不要求理解 Anchor。

## 6.5 Evidence

Citation 的 Calm / Focused 文案：

```text
法国政府学生住房指南 · 2026-03 版 · 第 12 页
用于限定适用地区
```

Source Reader 打开后说明：

- 原文或保存版本；
- 页码、段落或时间码；
- 为什么用于当前结论；
- 当前是否可重新核验；
- 关闭后回到哪一句。

## 6.6 Relation cue

Quiet 不显示状态名。相关 Claim 附近只允许：

- 一条完整关系句；或
- `还有 2 条相关关系`；或
- 一个明确的`查看关系`动作。

关系空间不因 AI 发现、后台索引或上次打开而自动常驻。

---

# 7. Relation Space 语言合同

## 7.1 进入阶梯

| Presentation | 用户动作 | 用户承诺 |
|---|---|---|
| Quiet | 无状态名 | 正文保持主任务 |
| Peek | `查看关系` | 查看局部说明，关闭回原 Claim |
| Companion | `在旁边查看相关知识` | 正文仍是主任务 |
| Explore | `在知识网络中打开` | 关系成为主任务，可精确返回 |

不显示 Quiet / Peek / Companion / Explore 作为用户模式名。

## 7.2 关系句

任何关系至少能读成：

```text
“认知负荷理论”为“AI Agent 交互设计”提供理论基础。
```

按需展开：

- 在什么条件下；
- 为什么重要；
- 由谁建立；
- 依据是什么；
- 当前仍采用、已结束、被替代还是已撤回；
- 查看两端知识。

禁止`related_to、支持 0.82、边权 7、AI connection、虚线代表可能`。

## 7.3 三个 truth layers

| 内部 | 用户标题 | 状态句 |
|---|---|---|
| Current | `当前关系` | 当前被知识库采用 |
| Suggested | `关系建议` | 尚未改变知识网络 |
| History | `过去的关系` | 当时被采用，当前不参与默认浏览 |

Suggested 即使视觉上接近 Current，也必须有可见文字。Past 不能只变灰。

## 7.4 Connection families

界面根据具体任务使用不同句子：

- 结构：`位于“记忆”主题`；
- 证据：`这段来源限定了这项结论`；
- 引用：`在这里提到另一条知识`；
- 正式关系：`A 为 B 提供基础`；
- 本次查询：`这两条知识在本次回答中一起使用`。

后两者不能因为都画线而统一叫`关系`。

## 7.5 Group Network

Resting level 只显示 Current Groups 与 Current Group Relations。Shared Knowledge 写：

> 这条知识同时出现在两个知识群；这是当前位置产生的观察，不是一条已建立的群关系。

Cross-group exit 写：

> 你可以沿这条知识进入“AI Agent 产品设计”；这不代表两个知识群整体已经建立关系。

## 7.6 Graph / List accessibility

同一 selection 的图与列表必须使用相同：

- Group / Knowledge title；
- 完整关系句；
- Current / Suggested / Past 标题；
- filters；
- `查看 / 打开 / 比较 / 回到上一处`；
- result count 与 scope。

Graph failure、mobile 或 keyboard path 不得引入`简化版关系`。

---

# 8. Search 与 Ask 语言合同

## 8.1 Search

输入标签必须说明 scope：

- `搜索全部知识`；
- `在“法国租房”中搜索`；
- `在这条知识中查找`；
- `选择要关联的知识`；
- `查找动作`。

结果先显示 object、path、snippet、match reason：

```text
知识 · 押金
法国租房 › 费用 › 入住前
“押金通常不得超过……”
正文包含这句话 · 共 3 处
```

不显示 relevance confidence。`含义相近`只是匹配原因，不是 Relation。

## 8.2 Search empty / partial

Scoped no result：

> 在“法国租房”中没有找到“CUDA occupancy”。全部知识中有 2 个可能结果。

Index partial：

> 结果可能不完整：当前已完成 93 / 120 个知识群的索引。完整目录仍可浏览。

Search failed：

> 搜索没有完成。搜索词、范围和筛选已经保留；你可以重试或使用标题与正文精确搜索。

## 8.3 Ask composer

提交前显示 requested scope：

```text
将在“AI Agent 产品设计”中回答 · 仅使用你的知识
```

展开`调整范围`后才显示：包含子主题、直接关系、时间、是否允许外部资料等。

空 Library：

> 你的知识库里还没有可用于回答这个问题的知识。

动作：`为这个问题写下知识 / 保存来源 / 保存这个问题 / 本次允许外部资料`。

## 8.4 Answer Paper

默认阅读顺序：

1. 直接回答；
2. 决定性条件和限制；
3. 主要结论与逐条依据；
4. 这次实际使用的知识和来源；
5. 覆盖范围与仍不知道的部分；
6. 继续提问、探索或形成知识。

不显示聊天气泡历史作为主阅读结构。

## 8.5 Context translation

| 内部 | 用户语言 |
|---|---|
| Requested Context | `你让我查的范围` |
| Effective Context | `系统实际采用的范围` |
| Used Context | `这次真正用到` |
| Coverage sufficient | `已检查当前选择和可用来源，可以回答这个问题` |
| Coverage partial | `当前只能给出部分回答，因为…` |
| Coverage insufficient | `现有知识不足以支持可靠结论` |
| Coverage indeterminate | `目前无法确认已检查到什么程度` |

## 8.6 Claim basis

固定五种标签：

- `来自你的知识`；
- `来源原文`；
- `本次外部资料`；
- `基于这些知识推断`；
- `尚未确认的建议`。

每个主要 Claim 可进入具体 Knowledge Anchor 或 Source Fragment，并从那里`回到这条回答`。

## 8.7 Answer actions

彼此独立：

- `保存这次回答`；
- `形成一条知识`；
- `更新已有知识`；
- `保存这个问题`；
- `建立关系建议`；
- `保存探索路线`；
- `根据当前知识重新回答`。

不提供一个`保存全部`。

## 8.8 Answer failure

AI unavailable：

> 现在无法完成回答。问题、范围和已找到的依据都已保留；你仍可搜索、阅读来源，或稍后重试。

Stopped：

> 回答已停止。当前内容尚未完成，不能作为可引用回答；你可以保留未完成内容或重新开始。

关闭 Answer 不提示保存为知识，也不产生待办。

---

# 9. Add、Source 与 Formation 语言合同

## 9.1 Add entry

标题：`添加到知识库`

选项：

- `写下知识`；
- `建立知识群`；
- `保存来源`；
- `迁入已有内容`。

从当前 Group / Topic 发起时说明 placement：

> 新知识将放在“法国租房 › Visale”。你可以之后添加或移除其他位置。

## 9.2 Direct writing

最小流程：

```text
写下知识
→ 正在保存
→ 已保存这条知识
→ 回到刚才位置或打开这条知识
```

没有 Group 时：

> 已保存到独立知识。它已经完整保存在知识库中。

不出现`待 AI 整理、未完成、草稿、采用`，除非用户主动选择显式草稿。

## 9.3 Source save

四次承诺分别表达：

1. `来源已保存`；
2. `正在解析 / 文字识别尚未完成`；
3. `尚未形成知识`或`有几项形成建议`；
4. `尚未更新已有知识`或`有一项修改建议`。

Source-only 完成：

> 来源已保存。你可以阅读、搜索和标注；不需要现在形成知识。

## 9.4 Partial source

Parse failed：

> 来源已保存，但正文解析没有完成。你仍可打开原件；可以稍后重试解析。

OCR partial：

> 目前只识别了部分文字。已识别内容可搜索；原件和你的标注都已保留。

Zero-yield：

> 没有发现值得形成知识的变化。来源仍已保存，可以以后再整理。

## 9.5 Annotation / Evidence / Knowledge

选中文字后的动作分权：

- `高亮`；
- `添加批注`；
- `用作这条知识的依据`；
- `保存为知识`；
- `建立关系建议`。

删除高亮：

> 只删除阅读标记；已经用于知识的来源片段会保留。

## 9.6 Formation proposal

标题：`这些建议会改变什么？`

每次只提交一种 truth change：

- 建立新知识；
- 更新一条知识；
- 增加证据；
- 建立关系；
- 更新概览。

主动作使用`应用所选修改`；说明`未选择和失败的部分不会改变`。不使用逐卡`接受 / 拒绝`队列作为默认流程。

## 9.7 Source Reader

头部先显示：

- 来源 title / author / date；
- 当前看到的是原文、保存网页、PDF、OCR、转写或翻译；
- current / historical revision；
- original 是否可访问；
- 返回目标。

禁止一个`AI 生成`标签替代 OCR、translation、summary 与 inference。

---

# 10. History、Recovery 与 Utility 语言合同

## 10.1 History

标题按 owner：

- `这条知识的历史`；
- `这项关系的历史`；
- `这份来源的版本`；
- `这次回答当时使用的知识`。

历史打开时固定提示：

> 正在查看 2026 年 7 月 12 日的版本；当前版本没有改变。

恢复动作：`从这个版本开始修改`，不是`回滚到这里`。

## 10.2 Recovery

Recovery notice：

> 近期修改已在本机保护，尚未保存为这条知识。请检查后继续；上一个已保存版本仍用于默认回答。

Recovery 与 Resume 同时存在时，Recovery 先保护未提交内容；解决后不自动跳到 Resume。

## 10.3 Conflict

标题：`这里有两份修改需要决定`

说明：

> 另一处也修改了这里。两份内容都已保留；没有冲突的部分已经合并。

动作：`使用这个合并结果 / 保留当前版本 / 查看两份内容 / 稍后决定`。

## 10.4 Export / restore

Export 先说内容：

> 导出知识、知识群、主题、关系、来源、版本和历史。搜索索引、关系布局和最近位置可以重新生成。

Restore partial：

> 知识已经恢复。搜索索引和最近位置正在重新生成；这不影响知识内容。

## 10.5 Settings

按用户问题组织：

- 知识保存在哪里；
- 最近是否成功备份；
- 搜索是否完整；
- AI 会使用什么；
- 是否同步；
- 阅读与操作偏好；
- 查看技术详情。

不以 Storage / Sync / Index / AI Providers 的工程模块为一级结构。

---

# 11. Universal state language

所有主要 Scene 使用同一状态句结构：

```text
事实：什么仍然存在或已经完成
限制：什么尚未完成、不可用或发生变化
动作：现在最有帮助的下一步
```

| State | 必须说明 | 禁止表达 |
|---|---|---|
| Empty | 真正为空、筛选为空还是当前 scope 为空 | `没有任何知识`冒充 scoped empty |
| Loading | 正在处理什么、原任务是否仍可用 | 无限 spinner |
| Generating | 正在查找、核对还是组织 | `AI 正在思考` |
| Partial | 已完成部分、缺少部分、结果能否使用 | `完成` |
| Failed | 失败范围、保留内容、恢复动作 | `发生未知错误` |
| Offline | 本地仍可做什么、哪些增强不可用 | `保存失败` |
| Changed | 什么变化影响哪一项判断 | `内容已过期` |
| Historical | 当前看到哪个版本、如何去 Current | 静默显示旧内容 |
| Unavailable | 哪个原件 / AI / index / graph 不可用 | 产品级错误页 |
| Conflict | 两份内容都已保留、需要决定什么 | `冲突解决失败` |
| Recovery | 什么已保护、什么尚未 Current | `已保存` |
| Destructive preview | 删除目标、数量、影响、恢复性 | 泛化`确定吗` |
| Large-scale | 当前 scope、显示数、未显示原因 | `知识库太大` |

## 11.1 Truthful empty states

- Empty Library：`这里还没有知识`；
- Empty Group：`这个知识群刚刚开始`；
- Filter empty：`当前条件下没有结果`；
- Network zero relation：`目前没有已建立的群关系`；
- Ask insufficient：`现有知识不足以支持可靠结论`；
- Source zero-yield：`没有发现值得形成知识的变化；来源仍已保存`。

它们不能共用一张`空空如也`插画和一句`开始添加内容`。

## 11.2 Status priority

同一对象多个状态时，Calm 只显示最影响当前行动的一句：

1. destructive / conflict / recovery；
2. historical / read-only；
3. failed / offline / unavailable；
4. changed / review needed；
5. loading / partial；
6. ordinary current 无需徽章。

展开后才显示其他状态。禁止`当前 · 已保存 · 已同步 · 已索引 · 有依据 · 无冲突`徽章墙。

---

# 12. 高后果动作模板

## 12.1 修改多 Placement Knowledge

标题：`你想修改哪里？`

- `修改这条知识`：所有出现位置都会显示新内容；
- `只修改它在当前主题中的说明和位置`：Knowledge 正文不变；
- `另存为一条独立知识`：原知识不变，之后分别维护。

不使用 canonical / contextual / fork。

## 12.2 Remove Placement

标题：`只从这个主题移除？`

说明：

> 这条知识仍会保留在其他位置，也可以通过搜索找到。关系、来源和历史不会删除。

动作：`从这里移除`。

## 12.3 Archive Group

标题：`归档“长期记忆系统”？`

说明：

> 它会从当前知识群目录隐藏；内容、关系、来源、历史和旧链接仍保留。你可以之后恢复。

## 12.4 Trash Knowledge

标题：`将这条知识移到废纸篓？`

依次显示：

1. 将移除哪些出现位置；
2. 哪些 Overview、Relations、Answers 与 Paths 会显示受影响；
3. 可恢复时间与入口；
4. 失败时哪些内容不会改变。

此处不提供`永久删除`。

## 12.5 Source deletion

分别提供：

- `停止以后同步`；
- `从默认来源列表隐藏`；
- `移到废纸篓`；
- `不再把这段材料用于当前知识`；
- `永久删除受管原件和快照`。

每项都说明已形成 Knowledge 是否保留、哪些 Claims 会失去可核验依据。

## 12.6 Restore history

标题：`从这个版本开始修改？`

说明：

> 这会创建一个新的当前版本；现在的版本和中间历史都会保留。

动作：`创建新的当前版本`。

## 12.7 Apply AI change

标题：`这些修改会改变什么？`

先显示 semantic Diff，再显示影响对象。主动作：`应用所选修改`。未选择、失败和零变化项目明确保持不变。

## 12.8 Create relation

标题：`它们为什么相连？`

字段：

- 从；
- 到；
- 完整关系句；
- 成立条件（可选）；
- 依据或说明（可选）。

用户直接写的动作：`建立关系`；AI 建议：`采用这项关系建议`。

---

# 13. Accessibility、responsive 与 localization

## 13.1 可见标签与 accessible name

- visible label 与 accessible name 使用同一核心动词和对象；
- `打开`按钮不能在读屏中叫`查看详情`；
- 图标按钮必须有具体对象，例如`固定知识群“认知科学”`；
- 关系 edge 的 accessible name 是完整句，不是`边 12`；
- Current / Suggested / Past 作为文字进入关系名称或描述；
-状态变化通过 live region 或等价机制宣布，但不重复整页内容；
- error 与其 input / decision context 明确关联。

## 13.2 Speech input

用户说出可见动作即可激活：

- `搜索`；
- `提问`；
- `添加`；
- `打开知识群“认知科学”`；
- `回到上一处`；
- `关闭当前查看`。

不让可见文字`继续`对应内部 accessible name `resume-workspace-scene`。

## 13.3 非视觉等价

读屏关系顺序：

```text
当前关系
认知科学 为 AI Agent 产品设计 提供理论基础
条件：设计高风险自主行动时
依据：2 条知识，1 份来源
操作：查看起点、查看终点、查看依据、打开完整关系
```

Graph layout、节点距离、边方向和色彩需有同义文本；装饰星云没有替代文本。

## 13.4 Responsive

desktop `在旁边查看`在 compact / mobile 变为 sheet 或顺序 page 时，动作仍叫`查看相关知识`，并显示`关闭后回到…`。不写`切换到移动版关系`。

Graph 在 mobile 默认 List 时仍叫`知识网络`，提供`图 / 列表`只在空间图可用时出现。

## 13.5 Localization

- 中文为默认规范语言；英文内部词不混入中文 Calm；
- 日期避免歧义，使用`2026 年 8 月 10 日`或 locale-aware format；
- 不依赖`左侧 / 右侧 / 上方 / 下方`作为唯一指示；
- 链接文本描述目标，不写`点击这里`；
- 按钮使用动词 + 对象，避免只有抽象名词；
- 不使用难以翻译的双关、拟人或星图隐喻表达状态。

---

# 14. 当前 Ardot 语言处置

| Screen | 保留 | 删除 / 替换 |
|---|---|---|
| 1 | Warm Paper / Relation Night 的情绪对比 | `知识星图 · Codex`、星图价值主张、笔记 / 引用数量、`提问 / 收录`、AI 新析出、精选星群 |
| 2 | 连续阅读气质 | `双镜工作区`模式名、`新建笔记`、常驻 AI 析出；关系名词节点改完整关系句 |
| 3 | Relation Night 艺术气质 | 八对象、L0 Atlas、Ask / Search / Explore 模式教学、行星装饰语义 |
| 4 | 分阶段节奏 | `AI 已建立知识`、逐卡接受、保存 / 解析 / 形成混成一次完成 |
| 5 | Answer Paper 气质 | 模糊`参考资料`、confidence、一个`保存`覆盖所有后果 |
| 6 | user-owned Overview | 常驻建议栏、`采用自己的内容`、保存 / Recovery / Current 混义 |
| 7 | local ownership concern | Storage 作为核心屏；改为任务型来源、导出、恢复与设置语言 |

未来 Frame 必须使用本合同的真实文案，不允许先画占位字再宣称信息架构成立。

---

# 15. 十八个语言证明场景

## LPX-01 · Empty Library

用户能区分写知识、建群、存来源和提问；没有激活、模板或 AI 门槛。

## LPX-02 · Daily Library

用户能说清 Resume、固定、全部知识群、最近打开与独立知识的差异。

## LPX-03 · G100 / index partial

用户知道目录仍完整、搜索只覆盖 93 / 120、下一步如何缩小范围。

## LPX-04 · Groups ↔ Network zero relation

用户理解仍是同一知识库；零关系不等于错误，也不被相似度补线。

## LPX-05 · Overview → Topic → Knowledge

用户不学习 D0–D5，仍能指出当前位置、上一级和普通打开后果。

## LPX-06 · Claim → Evidence → Back

用户能说出来源版本、位置、为何用于该 Claim，以及关闭后的返回句。

## LPX-07 · Multi-Placement edit

用户能区分修改 Knowledge、只改当地 context 和另存新 Knowledge。

## LPX-08 · Quiet → Explore

用户看不到 presentation 模式名，仍能区分查看、旁边查看、在知识网络中打开和精确返回。

## LPX-09 · Relation truth layers

Current、Suggested、Past 即使去掉颜色和线型仍能被正确识别。

## LPX-10 · Search exact Anchor

用户知道搜了哪里、为什么命中、打开后如何返回原结果和筛选。

## LPX-11 · Ask scope / claim support

用户能说清要求范围、实际采用范围、真正用到的知识及每个 Claim 的依据角色。

## LPX-12 · Answer → Explore → write-back

用户能区分保存回答、形成知识、更新知识、保存问题、建立关系与返回。

## LPX-13 · Direct writing / recovery

用户能区分正在修改、本机已保护、Knowledge 已保存、等待同步和索引更新。

## LPX-14 · Source partial

用户知道 Source 已保存、parse 未完成、原件可打开、尚未形成 Knowledge。

## LPX-15 · Source change / local Diff

用户知道哪些 Claim 受影响、正文尚未改变、Evidence-only 与 semantic update 后果不同。

## LPX-16 · Offline / AI / graph / index failure

每个失败都明确保留的 truth、不可用增强与下一步；不进入统一错误页。

## LPX-17 · Export / clean restore

用户知道 canonical truth 已恢复、哪些 projection 正在重建、没有内容丢失。

## LPX-18 · mobile / keyboard / screen reader

同一动作、对象和关系句在不同输入与呈现方式下保持一致。

---

# 16. 专项验收合同

| ID | Canonical | 验收条件 |
|---|---|---|
| LAC-01 | AC-01 | 全部主要 Scene 的唯一稳定地点名是`知识库`，没有 Home / Atlas / Review 第二中心 |
| LAC-02 | AC-01 / 02 | `知识群 / 知识网络`是同一 view switch，scope / selection 变化有解释 |
| LAC-03 | AC-01 / 03 | Empty / Bare / daily Library 使用事实语言，不用成熟度、激活或债务 |
| LAC-04 | AC-04 / 05 | Overview / Topic / Knowledge 使用自然路径，不暴露 D0–D5、Node 或 shadow summary |
| LAC-05 | AC-06 | 正文始终叫`知识`并连续阅读，不恢复笔记卡片语言 |
| LAC-06 | AC-07 / 08 | `出现位置`、`只从这里移除`与`修改这条知识`后果可复述 |
| LAC-07 | AC-09 | 正在修改 / Recovery / 保存 Knowledge / Sync / Index 五层不被一个 Saved 合并 |
| LAC-08 | AC-10 / 17 | 查看 Evidence / Relation 后的具体返回目标可见且可访问 |
| LAC-09 | AC-11 | 每条 Relation 在图、列表和 Inspector 中都有同一完整句 |
| LAC-10 | AC-12 | Structure / Evidence / Reference / Formal Relation / Query Route 使用不同用户语言 |
| LAC-11 | AC-13 / 14 | exit / shared observation 明确写出不是 Group Relation |
| LAC-12 | AC-15 | 关系只因`查看 / 旁边查看 / 在网络中打开`逐级增长，不显示模式名 |
| LAC-13 | AC-16 | Graph / List 的对象、关系句、筛选、选择和动作名称同义 |
| LAC-14 | AC-18 | Search label 显示 scope；结果显示 object、path、snippet 与 match reason |
| LAC-15 | AC-19 | Ask 提交前显示 requested scope，回答后可查 effective / used scope |
| LAC-16 | AC-20 | Answer Claim 明确区分用户知识、来源原文、外部资料与推断 |
| LAC-17 | AC-21 | Coverage 使用范围与缺口句，不使用 confidence 百分比 |
| LAC-18 | AC-22 | 关闭 Answer、保存 Answer 与形成 Knowledge 的文案后果不同 |
| LAC-19 | AC-23 | 每个 write-back action 只有一个 target / result；不提供保存全部 |
| LAC-20 | AC-24 | 临时 unknown 不产生 Inbox / badge；只有`保存这个问题`才长期存在 |
| LAC-21 | AC-25 | Source save / parse / formation / update 使用四次独立回执 |
| LAC-22 | AC-26 | zero-yield 与 reject 使用成功 / 零副作用语言，不制造待处理任务 |
| LAC-23 | AC-27 | Source change 先说明 affected Claim 与正文未改变，再进入 local Diff |
| LAC-24 | AC-28 | History / Recovery / restore forward / query history 的标题和动作不混淆 |
| LAC-25 | AC-29 | offline / AI / index / graph failure 先说明可继续的 canonical task |
| LAC-26 | AC-30 | export / restore 文案区分 canonical assets 与可重建 projections |
| LAC-27 | AC-31 | desktop / compact / mobile 保持同一核心动词、对象和后果 |
| LAC-28 | AC-32 | visible labels 足够理解，不把关键后果只放在 aria-label / tooltip |
| LAC-29 | AC-32 | accessible name 与 visible label 使用同一核心动词和对象 |
| LAC-30 | AC-31 / 32 | 非颜色、无动画、200% zoom 和线性阅读仍能识别 truth / state / return |
| LAC-31 | AC-01–32 | DPB-01–18 均登记 default / partial / error / return copy 与 disclosure level |
| LAC-32 | AC-01–32 | 当前 Ardot 旧词不进入新 Surface Skeleton；真实 fixture 文案替代占位内容 |

---

# 17. 外部模式与产品推论

## 17.1 Apple：最常用内容先出现

[Apple Disclosure controls](https://developer.apple.com/design/human-interface-guidelines/disclosure-controls)建议把最常用内容放在披露层级顶部、高级能力默认隐藏，并让 disclosure control 与其内容保持清楚关系。

**产品推论：**Calm 保留当前主任务与关键真相；Focused / Decision / Forensic 就近出现。不能为每个内部字段放一个折叠控件，也不能把必要后果藏进`高级选项`。

## 17.2 Apple：简单不等于极简

[Apple Design principles](https://developer.apple.com/design/human-interface-guidelines/design-principles)强调 familiarity、agency、清楚反馈、错误恢复，以及使用准确而必要的词。

**产品推论：**产品语言既要删掉内部术语，也要保留范围、写入后果、未知和恢复。短并不比准确更优先。

## 17.3 Microsoft：内容是设计材料

[Microsoft Fluent 2 Content Design](https://fluent2.microsoft.design/content-design)把语言视为与图形同等的设计材料，并强调关键决定、下一步、清楚标题、主动语态和可扫描结构。

**产品推论：**Frame 必须交付真实文案与信息顺序；占位标题、空标签和`稍后补文案`不能证明产品设计。

## 17.4 W3C：标签要让所有人知道该做什么

[W3C Labels or Instructions](https://www.w3.org/WAI/WCAG21/Understanding/labels-or-instructions.html)要求输入和选项拥有足够标签或说明，并指出只有 accessible name 并不足以帮助视觉用户。

**产品推论：**Ask scope、Add 后果、Relation direction 和 destructive target 必须可见；无障碍名称与可见标签还要支持 speech input 的一致识别。

## 17.5 W3C：清楚内容与可理解界面

[W3C Clear and Understandable Content](https://www.w3.org/WAI/WCAG2/supplemental/objectives/o3-clear-content/)建议使用常见词、短句、清楚结构、非含混内容，并避免依赖数学能力。

**产品推论：**confidence、edge weight、完成率和内部枚举不能替代完整状态句；复杂证据可以在 Forensic 保留，但先给自然语言结论。

## 17.6 GOV.UK：具体错误与保留输入

[GOV.UK Error message](https://design-system.service.gov.uk/components/error-message/)要求说明发生了什么、如何修复、避免技术术语与泛化错误，并保留用户已有输入。

**产品推论：**Search / Ask / Add / Decision 失败都保留 query、scope、selection 与 draft；`发生未知错误`和清空表单均不通过。

## 17.7 研究没有证明什么

外部规范没有证明：

- 本合同的中文词汇已经通过用户测试；
- 五个核心概念已能在 10 分钟内稳定理解；
- `知识群 / 主题 / 知识`在所有用户背景中都无歧义；
- Calm 的具体信息预算适合所有屏幕；
- 任一当前 Ardot 文案已通过可访问性验证；
- 本产品应该复制 Apple、Microsoft 或 GOV.UK 的视觉组件。

它们只支持清楚语言、渐进披露、标签、错误恢复与证据边界。

---

# 18. 与相邻现行合同的边界

| Contract | 它拥有 | 本合同拥有 |
|---|---|---|
| Canonical v6 | 产品真相、资源、场景、旅程、AC | 用户看到什么词、动作与状态句 |
| Library | Resume / Pin / Recent / Catalog / Open / Continue 语义 | 它们的用户标签、顺序说明与空态文案 |
| Hierarchy | Group / Topic / Placement / Saved View truth | 知识群、主题、出现位置、视图的日常表达 |
| Reading | Overview / Knowledge / Anchor / History truth | 概览、正文、局部依据、编辑与历史语言 |
| Relation | Relation statement / standing / Graph / List truth | 完整关系句、Current / Suggested / Past 与探索动作 |
| Query | Search / Ask / Answer / Claim support truth | scope、basis、coverage、回答动作与错误文案 |
| Formation | Add / Source / Annotation / Proposal truth | 保存回执、partial、zero-yield 与 formation 动作 |
| Surface | Scene / Surface role / transition / DPB | 用户如何理解这些表面、进入、返回与 copy proof |

本文不允许通过“更自然的词”改变 truth、scope、identity 或 transaction。

---

# 19. 进入视觉设计前的语言 Gate

必须满足：

1. 用户确认或接受 v6 / Decision Companion 的十一项推荐默认；
2. 五个核心概念、唯一`知识库`与三个全局动作没有第二套命名；
3. `独立知识`替代所有现行`未归类 / Inbox`；
4. Direct Knowledge、Source、Answer、Proposal、Recovery 与 Sync 的结果文案不混淆；
5. Back / Up / Close / Library / Continue 有不同可见标签与 accessible name；
6. DPB-01–18 登记 default、partial、error、return copy 与 disclosure level；
7. 使用三份真实 fixture 与 synthetic scale 文案；
8. Screen 1 successor 先冻结 Empty / Daily / G100 / Network zero relation 文案；
9. Screen 2 successor 先冻结 Reading / Evidence / Quiet → Explore / return 文案；
10. Screen 3 successor 先冻结 relation statement、truth layers、zero / dense、Graph / List 文案；
11. 视觉选项不得靠删除必要文字获得“高级感”；
12. clickable prototype 仍在关键 Frame family 被确认后才开始。

---

# 20. 语言设计完成定义

只有同时满足以下条件，才能称产品语言已经完整：

- 用户只需五个核心内容概念即可完成日常任务；
- 一个`知识库`与三个全局动作在所有主要 Scene 一致；
- Search / Ask / Add、查看 / 打开 / 继续、Back / Up / Close、保存回答 / 形成知识没有混义；
- Current / Proposal / History、Source / Knowledge、Recovery / Current / Sync / Index 通过自然语言可辨；
- Relation 在图、列表、Inspector 和读屏中保持同一完整句；
- Empty / partial / failure / offline / historical / conflict / recovery / destructive / scale 使用 truthful templates；
- visible label、accessible name、keyboard hint 与 speech input 名称一致；
- desktop / compact / mobile 不改变词义和核心责任；
- DPB-01–18 的语言证据至少达到 CONTINUOUS；DPB-18 达到 EQUIVALENT；
- 旧`Home / Atlas / 笔记中心 / AI 新析出 / 未归类 / Command / Review Inbox / 81 screens`不再进入现行设计；
- 所有完成声明可以定位到真实 Frame / state / annotation / runtime evidence；
- 用户测试仍被诚实标为未完成，而不是由文档内部一致性代替。

---

# 21. 最终判断

这个产品的用户语言不应该像一份数据库说明，也不应该为了显得轻而含糊后果。它应该像一座认真编辑过的个人图书馆：

- 地点稳定；
- 目录完整；
- 正文可读；
- 关系可说清；
- 来源可核验；
- AI 有边界；
- 错误讲真话；
- 每次离开都知道怎样回来。

内部模型继续负责严谨，用户语言负责把严谨变成自然行动。
