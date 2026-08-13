# AI-native 个人知识库

## 地点编排、信息归属与跨地点连续性合同 v1.0 — Active Place、Surface Owner、Entry Context 与 Attention Routing

> 日期：2026-08-06；结构修订：2026-08-07  
> 文档性质：终局产品导航、地点职责、跨地点投影、注意力与现场连续性合同；不是站点地图、页面清单、MVP 范围或原型授权  
> Canonical 产品定义：`AI-native-个人知识库-终局产品设计文档-v4.0.md`；本合同只证明归属与连续性责任，不得反向改写 v4.0  
> 2026-08-07 写入冻结：用户 thought 经安全 Direct Edit Commit 成为当前知识；Edit Buffer、Recovery、Explicit Draft、Proposal、Sync 与 Projection 分开，地点编排不使用“完成并采用”  
> v4.0 探索连续性覆写：ReturnStack 只负责时间回返，DepthTrail 只负责结构位置，ResumePoint / PathProgress 单独负责继续；SavedPath 不保存 `last_position`，跨 Place 的 Open 才写 ReturnEnvelope  
> 历史深层模型：`AI-native-个人知识库-产品定义-v3.0.md`  
> 表面架构：`AI-native-个人知识库-产品表面架构与完整设计证明合同-v1.0.md`  
> 对象层级：`AI-native-个人知识库-产品对象层级与身份治理合同-v1.0.md`  
> 核心体验：`AI-native-个人知识库-核心体验与知识群生命周期-v1.0.md`  
> Library：`AI-native-个人知识库-Library浏览与动态视图合同-v1.0.md`  
> 来源与证据：`AI-native-个人知识库-来源证据与可追溯性合同-v1.0.md`  
> 知识形成与维护：`AI-native-个人知识库-知识形成与维护循环-v1.0.md`  
> 交互基线：`AI-native-个人知识库-交互架构与设计系统-v1.0.md`  
> 流程与覆盖：`AI-native-个人知识库-产品流程板与组件状态图-v1.0.md`  
> 复杂度收敛：`AI-native-个人知识库-核心导航与复杂度收敛合同-v1.0.md`  
> 视觉审查：`design-audit-ardot/Ardot-设计审查与全量设计蓝图-v1.0.md`
> 探索路径、回返与继续：`AI-native-个人知识库-探索路径、回返与继续合同-v1.0.md`

> **2026-08-07 Library-first 领域覆写：**本文原“四个稳定 Places”数量决定已被`AI-native-个人知识库-核心心智模型与连续探索合同-v1.0.md`取代。当前只有一个 Knowledge Library 主地点；旧 Home 映射为 Library Resume region，旧 Library 映射为 Groups view，旧 Atlas 映射为 Library Network / R3，旧 Sources 映射为 supporting Source utility。本文关于 `Surface Owner / Entry Context / Return Envelope / Attention Routing / Destination Receipt / failure isolation` 的连续性规则继续有效；`Active Place / Place State / Place Handoff`在当前模型中分别读取为`Active Library Surface / Surface State / Surface Handoff`。后文所有“四 Places”数量、顺序、快捷键和 per-Place state 只保留为历史架构，不再约束新设计。
> **2026-08-09 Scale Invariance 领域覆写：**数量跨越 F1 / F10 / F100 / F10K 时，Active Library Surface、owner、entry context、ordinary open、Continue 与 ReturnEnvelope 不变。Resume、Pins、Catalog、Recent 分权；Network 超预算先 Summary + List + Anchor；全库 Ask 显示 Group coverage。完整规则见`AI-native-个人知识库-规模化知识空间与长期可浏览性合同-v1.0.md`。

---

# 0. 执行决定

现有定义已经回答“为什么需要稳定 Places”，但还没有回答一个日常产品必须持续回答的问题：用户进入一个 Group、Node、Source、Answer 或 Decision Surface 后，当前究竟属于哪个地点；同一变化为何会同时出现在 Home、owner Workspace 与维护表面；一次 Capture 完成后又应去哪里找。

如果这些问题不冻结，四个地点会在设计时退化成四个功能页，同一个对象被复制成多张卡，同一变化制造多个红点，同一 Group 从 Home、Library 与 Atlas 打开后形成三套互不一致的页面。

本合同冻结六十七项决定：

1. **四个 Places 是四种稳定全局语境，不是四个对象仓库。** Home、Library、Atlas、Sources 说明用户此刻以什么全局目的工作，不拥有第二份知识真相。
2. **Active Place、Surface Owner 与 Entry Context 必须分开。** “我在什么全局语境”“我正在处理谁”“我从哪里进入”不是同一个字段。
3. **Selection State 与 Active Place 也必须分开。** 选择一个 Group、Node、Source 或 Relation 不自动切换 Place。
4. **打开 owner Workspace 默认继承当前 Active Place。** 从 Atlas 打开 Group，Group Workspace 仍处于 Atlas 探索语境；从 Library 打开同一 Group，则处于 Library 浏览语境，但 canonical Group 与 Workspace contract 完全相同。
5. **只有显式地点动作改变 Active Place。** 点击一级导航、执行“在图谱中查看 / 在来源中打开”、恢复一个 Place state 或解析无来源深链，才改变 Active Place；打开 Knowledge Decision 不新增地点。
6. **同一 owner Workspace 不按入口复制。** Home、Library、Atlas、Sources 只改变入口、默认 Lens 与 Return Envelope，不产生 Home Group、Library Group 或 Atlas Group。
7. **每个 Workspace 只允许一个 Surface Owner。** Group Workspace 的 owner 是 Group；Node Workspace 的 owner 是 Node；Answer Workspace 的 owner 是 Query Turn / Answer Snapshot；入口 Place 不是 owner。
8. **Entry Context 保存来源动作而非知识身份。** 它包括 origin Place / surface、origin selection、trigger、scope、result set 与 return target，可以丢弃而不损坏知识。
9. **一级导航始终固定为 Home、Library、Atlas、Sources。** Knowledge Decision、Settings、Trash、Search、Ask、Add、Command、History 与 Answer 不成为第五个地点。
10. **点击非当前 Place 恢复该 Place 上一次稳定状态。** 它不是 Back，也不清除当前 Place 的状态。
11. **点击当前 Place 回到该 Place Root。** 若有未提交高风险 Decision 或未落盘输入，先保存 draft / recovery 再返回，不静默丢失。
12. **Back / Forward 按真实进入历史恢复，一级导航按地点状态切换。** 两种机制不能合并成一套含混“返回”。
13. **应用普通启动优先恢复上一个可恢复 Workspace。** Home 是稳定地点，不是每次启动强制经过的启动页。
14. **没有合法上次状态、新建窗口、首次使用或用户显式选择时才进入 Home Root。** Crash recovery、external deep link 与 OS-level Capture 使用各自优先级。
15. **Home 的第一印象是知识与返回，不是 Ask / Search 输入框。** 全局 Ask、Search、Add 已在 Shell 可用，不在 Home 再成为视觉 Hero。
16. **Home 只呈现 Orientation Projections。** 它显示进入理由与目的地，不复制 Group Overview、Library rows、Atlas graph、Source cards 或 Decision 内容。
17. **Knowledge Library 首屏顺序固定为：最多一条可解释 Resume、紧凑 Pins、穷尽 All Groups、次级 Paths / Answers / Views / Recent / Archived、最多一条高影响 contextual notice、安静的全局动作。** 缺失部分直接省略，不保留空区块；Recent 不成为 feed。
18. **Home 最多显示一个主 Resume。** 多个最近对象进入 Library Recent 或明确的“查看全部最近”，不做横向最近卡片瀑布。
19. **历史 Home / 当前 Library Resume 的 Group entrances 必须克制。** 用户固定的 Group 进入 Pins；最多一条 Resume 来自 last-safe checkpoint；`review_due`只能形成一条 contextual notice，不能与最近使用混成推荐排序，也不影响 Search / Ask / Network truth。
20. **Home 的 Ask 入口退为全局动作或当前 Group 的次级动作。** 空知识库时 Ask 诚实说明还没有可回答的个人知识，不用通用 AI 回答掩盖空库。
21. **Library 是 Group / Node / Path / Saved Answer / View / Archive 的稳定目录。** 它完整负责“我拥有什么”，不接管 Source Registry、Relations、Proposal queue、system jobs 或 Trash。
22. **Atlas 是正式关系的全局探索地点。** 它完整负责 Group Relation 与选中范围的语义连接，不成为目录、来源网络、历史图或 AI similarity map。
23. **Sources 是材料与 provenance 的全局地点。** 新来源、解析、版本、Representation、Annotation、Fragment、Binding、rights 与 availability 在这里完整成立，不要求先形成知识。
24. **Knowledge Decision 是高影响判断 Workspace，不是 Place。** 只有 identity、truth、structure、schema、migration、destructive 或 accepted-knowledge impact 需要用户决定时才进入；它不做 Inbox。
25. **Group Structure Lens 与 Library 使用同一 Placement truth，但责任不同。** 前者只组织当前 Group，后者能穷尽浏览整个 Space；两者不复制 hierarchy state。
26. **Group Map Lens 与 Atlas 使用同一 Relation truth。** 前者默认 R0–R2 当前范围，后者提供跨群 R3；“在图谱中查看”是显式 Place handoff。
27. **Group Sources Lens 与 Sources Place 使用同一 Source / Binding truth。** 前者只显示当前 Group 的支持与材料语境，后者管理 Registry、Revision、Representation 与 lifecycle。
28. **Overview notice、owner History / Impact 与 Knowledge Decision 使用同一 Change Set / Proposal truth。** 前两者解释当前 Group 受到什么影响；只有需要判断的项才打开 Decision Workspace。
29. **Group Overview 不等于 Home。** Overview 是一个 Scope 的 canonical knowledge product；Home 只投影“为什么值得进入这个 Group”。
30. **同一事件最多有一个 Primary Destination。** 它可以是 Place、owner 或 Decision Workspace；其他表面只能显示带 owner 与去向的 Projection，不能复制完整操作、状态或待处理计数。
31. **每个可见 Projection 都必须回答：为什么出现在这里、完整内容在哪里、关闭或处理后会怎样。** 不允许匿名卡片或只有时间标题的 Feed item。
32. **Recent、Resume、Pin、Attention 与 Importance 分开。** 最近访问是事件，Resume 是现场恢复，Pin 是用户入口偏好，Attention 是当前行动理由，Knowledge importance 是知识语义；五者不共享排序分。
33. **Library Recent 保存访问事实；Home Resume 保存一个可恢复任务现场。** Home 不直接展示原始 Recent 列表。
34. **Pin 只影响进入便利。** Home 只可以优先展示 pinned Groups；Node、View、Path 与 Source pins 留在各自 Place / Shell 快捷区，不影响权威、Ask、Search 或 Atlas salience。
35. **Attention Signal 是可重建的路由记录，不是 Primary Resource、知识状态或通知。** 它归属于 owner / event，并指向唯一 Primary Destination。
36. **Attention 不使用通用 severity 分数。** 它分别保存 `reason_now`、`affected_scope`、`decision_required`、`time_condition`、`reversibility`、`current_relevance` 与 `suppression_reason`。
37. **阻塞当前任务的变化在 owner Workspace 内联出现。** 不先把用户赶到独立维护中心。
38. **需要高影响判断的变化以 Knowledge Decision Workspace 为 Primary Destination。** Home 最多显示一条高层 notice，owner Workspace 显示局部影响，二者都链接到同一 Decision Surface。
39. **不需要判断但值得回看的变化留在 owner Place / View。** Source added、Working saved、View evaluation changed、recent open 与 low-risk projection refresh 都不进入 Decision。
40. **System health 进入全局 Status Center。** storage、index、sync、AI、permission、migration runtime 与 backup health 不与知识变化混成 Home / Decision 红点。
41. **产品默认不发送逐项系统通知。** 只有用户显式开启且满足时间敏感、影响明确、当前不可自然遇见的条件，才产生一条合并通知；通知打开后仍进入 Primary Destination。
42. **Defer 不复制 item。** 它只改变同一 Attention / Decision 的 next-eligible condition；无新证据、时间条件或相关语境时不重新浮现。
43. **产品没有 Universal Inbox。** 外部材料进入 Sources；未完成 / 未归类知识进入 Library Views；高影响决定从受影响语境打开 Knowledge Decision；系统问题进入 Status Center；Quick Capture 用 receipt 指明落点。
44. **Capture 先提交真实输入，再决定后续去向。** 入口位置只提供默认 Scope，不能决定真实落点或自动采用。
45. **每次 Capture 都有 Destination Receipt。** 它明确保存了什么、保存到哪里、是否已成为当前知识、是否仍在处理、怎样继续和怎样撤销。
46. **用户想法默认成为可恢复 Working Node。** 它在 Library 的 Unfinished / Unplaced 找回；只有当前明确 Group / Topic 时才创建 Placement；不进入 Decision。
47. **外部材料默认成为 Source。** 它进入 Sources Registry；zero-yield、parse pending 或 Source-only 都是成功，不进入 Decision。
48. **Capture 产生高影响 Proposal 时只创建一个 Decision Bundle。** Source 仍在 Sources，Working / Accepted knowledge 各在自身 owner，需要判断时从 receipt / owner 打开同一 Decision。
49. **全局 Search、Quick Ask、Add 与 Command 继承 Active Place / Selection，但继承范围必须可见。** 关闭后恢复同一 Place、Workspace、Selection 与 focus。
50. **Full Answer 默认继承发起时 Active Place。** 保存后的 Answer Snapshot 归入 Library 的 Paths & Answers；从深链打开 Saved Answer 时默认 Active Place 为 Library。
51. **无 Entry Context 的 deep link 使用确定性 Default Place。** Knowledge / Contents / View / Path / Snapshot → Library；Relation → Atlas；Source / Provenance → Sources；Decision / Change 先解析 owner 再以其 Default Place 打开 Decision；system / settings → Service Workspace。
52. **有 Entry Context 的 deep link 不强行切换到 Default Place。** Evidence、Source Reader、Relation Inspector 与 supporting record 可以在原 Place 上下文中暂时打开；“在来源中打开”等显式动作才切 Place。
53. **每个 Place 独立保存 Place State。** Home、Library、Atlas、Sources 分别保存 root / workspace、selection、filters、scroll、expanded、viewport、last safe focus 与 open decision reference。
54. **Place State 属于 Workspace Continuity，可重置、不同步或不导出而不伤害知识。** View Definitions、Relations、Sources、Change Sets 与 Pins 等 canonical / supporting records不因此删除。
55. **每个窗口拥有独立 Active Place、Return Stack 与 Place States。** 多窗口共享 canonical resources、accepted revisions、View Definitions 与 decisions，不互相抢 focus。
56. **每个 Space 拥有独立四地点状态。** 默认单 Space 不显示复杂切换；硬隔离 Space 不共享隐式 Relations、Sources scope、Decision draft 或 Return Stack。
57. **响应式只改变 PlaceNav 的呈现。** desktop 用 sidebar，compact / tablet 可折叠，mobile 用稳定 tab / sheet；顺序、名称、Active Place 和返回语义不变。
58. **Keyboard 与辅助技术明确区分 focus、selection、active place 与 current owner。** 聚焦导航项不切地点；激活后才切换并把 focus 移到新 Surface 的可理解起点。
59. **完整设计必须证明同一 Journey 跨 Home、Library、Atlas、Sources 与 contextual Decision 往返，而不是分别画四张 Root 和一张维护页。** 每个 handoff 都需要 entry、state transfer、failure、return 与 focus evidence。
60. **本合同不授权原型。** 先确认 Active Place / Owner / Entry Context、Home 顺序、Primary Destination、Attention routing 与 Destination Receipt，再进入 Surface skeleton 或高保真设计。
61. **Back、Up、Close、Place switch 与 Resume 是五种不同动作。** Back 沿 ReturnStack，Up 沿 DepthTrail，Close 移除 transient layer，Place switch 恢复该 Place State，Resume 恢复一个 safe checkpoint。
62. **跨 Place Open 才写 ReturnEnvelope。** Hover、Focus、Inspect、scene expand / filter、Companion follow 与 PlaceNav focus 不写跨地点历史。
63. **ReturnEnvelope 必须足以恢复现场。** 至少包含 Place、owner、primary target、placement context、root / lens、anchor、filter、viewport、scroll 与 focus return。
64. **Home Resume 只引用 ResumePoint。** 它可以同时说明关联 SavedPath 与 PathProgress，但不会把 Recent、Pin 或 Path identity 合并进一张记录。
65. **普通 Group open 与 explicit Continue 分开。** 前者进入 Overview；后者才恢复 exact target / anchor / Path step。存在 Progress 不能替用户改变入口意图。
66. **多窗口分别拥有 ReturnStack、ExplorationSession 与 ResumePoint。** 清除一个窗口的现场不影响另一个窗口、SavedPath 或 canonical knowledge。
67. **恢复失败使用 nearest safe state。** 原 anchor / placement 失效时依次 repair、redirect、parent fallback，并说明变化；不能静默回 Home、Root 或页面顶部。

---

# 1. 当前定义中的十八个结构缺口

## 1.1 Home 的产品承诺与流程顺序冲突

主定义要求 Home 第一印象是“我的知识世界”，但流程板把 Ask / Search 放在首屏第一顺位。若不修订，方向会再次滑向 AI 输入框产品。

## 1.2 打开 Group 后 Active Place 未定义

从 Home、Library、Atlas、Search 或 Decision 打开同一 Group，现有规格没有说明一级导航选中谁、点击一级导航发生什么、返回怎样恢复。

## 1.3 Place、owner 与 origin 混成“当前位置”

`current_location` 无法同时表达 Atlas 探索语境、当前 Group owner 与来自一条 Relation edge 的进入路径。

## 1.4 Home Recent 与 Library Recent 边界不够硬

若 Home 直接复制最近列表，它会变成 Library Recent 的推荐版；若算法再加入“重要性”，访问偏好会污染知识显著性。

## 1.5 Home notice 与 Decision 可能复制同一任务

没有 Primary Destination 与 Projection 规则时，同一 Change Set 会在 Home、Group、Sources 与 Decision 各出现一张可操作卡，状态、defer 和完成容易分叉。

## 1.6 Sources changed 与 Decision 的路由未分级

新 Revision、locator relocated、support changed 与 accepted knowledge conflict 并不具有相同后果；全部进 Decision 会制造队列，全部留 Sources 又会隐藏高影响决定。

## 1.7 Library 状态 View 可能冒充待办

Unfinished、Unplaced、Stale、Contested 是动态观察；只有其中一小部分需要决定。若都显示 attention badge，Library 会变成清零型 Inbox。

## 1.8 scoped Lens 与 global Place 容易重复

Group Map / Atlas、Group Sources / Sources、owner History / Decision、Group Contents / Library 使用同一底层 truth，却没有冻结 scoped-to-global handoff 与 state transfer。

## 1.9 Capture 完成后的“去哪找”未完整定义

已有落点语义，但还缺统一 Receipt；用户可能看到“已保存”，却不知道进入 Sources、Library、Working、Proposal 还是 Accepted knowledge。

## 1.10 启动时 Home 与 Resume 的优先级不确定

每次启动回 Home 会破坏本地桌面工作连续性；永远恢复最后页面又可能把用户送回失败、已删除或未完成危险决定。

## 1.11 一级导航与 Back 可能互相替代

若点击 Library 只是 Back 到上次目录，或 Back 被实现成“返回 Home”，用户无法建立稳定的地点心智。

## 1.12 deep link 只有 owner-first，没有 Default Place

一个 Source Revision、Relation、Saved Answer 或 Change Set 从系统外打开时，必须有确定的全局语境；只恢复 owner 仍不能解释一级导航。

## 1.13 Pin 的跨地点显示规则不完整

Group pin、Node pin、Source pin、View pin 与 Path pin 如果都进入 Home，会形成快捷入口墙；若全部只在 Library，又会让 Sources pin 失去语境。

## 1.14 Attention、Recent、Resume 与 Importance 没有统一拆分

它们已在不同文档零散禁止互相污染，但还没有一份可执行路由模型，设计仍可能用一个 has-attention / badge 解决全部问题。

## 1.15 系统状态与知识变化可能共享红点

Index partial、storage low、Source changed、Overview change 与 Knowledge Decision 都“需要注意”，但用户后果完全不同。

## 1.16 Place State 只存在 Return Stack 片段

Library 和 Atlas 各有恢复细节，但 Home、Sources 与 contextual Decision 的 root / workspace、filter、selection、scroll 和 focus 没有同一级合同。

## 1.17 多窗口与多 Space 的地点连续性不完整

若一个窗口切 Atlas 让另一个窗口也切换，或者 Space switch 共用一条 Return Stack，本地知识应用会失去可预测性。

## 1.18 当前视觉概念没有证明跨地点 Journey

现有七屏分别命名 Home、Workspace、Map、Capture、Answer、Overview、Sources，却没有一个连续 Home → Group → Atlas → Source → Decision → return 流程，因此 Screen 数不能证明地点架构成立。

---

# 2. 产品目标、非目标与证据边界

## 2.1 终局目标

1. 用户始终能区分当前全局语境、当前知识 owner 与进入来源；
2. 同一 Group、Node、Source、Relation、Answer 或 Change 在不同地点只拥有一份 truth；
3. Home 帮助返回知识世界，不成为 Dashboard、Feed、Chat hero 或 Inbox；
4. 每个变化只拥有一个 Primary Destination，其他投影可以解释且不会分叉；
5. Capture、Search、Ask、deep link 与跨地点进入都能准确回到原现场；
6. 离线、失败、窄屏、多窗口与辅助技术下仍保持地点心智。

## 2.2 永久非目标

- 不新增 Today、Inbox、Activity、Notifications、Agents 或 Tasks 作为一级 Place；
- 不把 Home 做成对象类型预览目录、每日笔记、AI 日报或全部 Recents；
- 不让每个 Place 保存自己的 Group / Node / Relation / Source 副本；
- 不用一个 relevance / attention / importance 分数统一排序所有入口；
- 不把 Pin、Recent、打开次数或编辑次数当作知识重要性；
- 不把所有变化送入 Decision；
- 不把所有未处理状态写成 overdue、debt 或清零目标；
- 不因 mobile 而把四地点改成 Capture / Search / Chat 三入口产品；
- 不在本合同冻结颜色、卡片样式、动效、栏宽或最终图标。

## 2.3 证据边界

- **[用户确认]**：产品本质是个人知识库；知识以知识群组织，存在群间关系、Overview 到细节的层级、AI 查询与知识网络探索；方向 3 + 2 是视觉偏好；当前先定义产品，不做原型。
- **[现有规格事实]**：主定义曾固定五 Places，并已定义 App Shell、Selection 与 Return Envelope；本轮将 Review 降为 contextual Decision，并收敛为四 Places，但 Active Place / Owner / Entry Context 与跨表面 Primary Destination 仍需统一合同。
- **[研究事实]**：成熟知识工具把 sidebar destinations、Library / object catalog、daily capture、query、full-page / preview / side panel / tabs 分成不同责任；可访问性标准要求多种定位方式、可预测焦点与明确层级。
- **[产品决定]**：三层位置模型、启动优先级、Home 顺序、Primary Destination、Attention routing、Destination Receipt 与 scoped-to-global handoff 是本产品选择。
- **[待验证假设]**：用户是否理解 Active Place 与 owner 的区别、Home 信息密度、Resume 优先级与 Decision 门槛，需要真实任务测试，本文不把它们写成已验证事实。

---

# 3. 三层位置模型

## 3.1 Active Place / 当前全局语境

Active Place 回答：**我现在是为了定位、浏览、探索还是核验材料而进入？** 判断是当前任务，不新增全局地点。

合法值只有：

```text
home | library | atlas | sources | review
```

Active Place 不是对象类型、URL prefix 或数据 owner。一个 Group Workspace 可以在不同 Active Place 下打开，但只有一份 Group identity、Overview 与 content。

## 3.2 Surface Owner / 当前工作对象

Surface Owner 回答：**这个 Workspace、Lens、Inspector 或 Decision 最终属于谁？**

典型 owner：

- Space；
- Group；
- Topic；
- Node；
- Source；
- Relation；
- Query Turn / Answer Snapshot；
- View；
- Saved Path / Snapshot；
- Proposal / Change Set；
- Property Definition / Migration。

Surface Owner 读取产品对象层级合同，不因 Surface 或 Place 改变 identity class / Truth Role。

## 3.3 Entry Context / 进入语境

Entry Context 回答：**我从哪个可恢复现场、通过什么动作来到这里？**

```text
EntryContext
  origin_place
  origin_surface_role
  origin_owner_ref
  origin_selection
  trigger: open | inspect | view_in_place | search_result | ask_claim | deep_link | restore
  query_or_filter_snapshot?
  relation_or_evidence_ref?
  return_envelope_ref
```

Entry Context 可以随窗口关闭而丢失；知识、关系、来源与历史不能依赖它才能成立。

## 3.4 Selection State / 当前焦点

Selection 回答：**在当前 owner 和语境中，我正在看哪一个 identity、Placement、Anchor、Relation 或 Evidence？**

Active Place、Owner、Entry 与 Selection 正交：

| 场景 | Active Place | Surface Owner | Entry Context | Selection |
|---|---|---|---|---|
| 从 Library 打开 Node | Library | Node | Library row / Placement | Node + Anchor |
| 从 Atlas 进入 Group | Atlas | Group | selected Group Relation / viewport | Group / related path |
| 从 Answer Claim 核验 Source | 发起 Ask 时的 Place | Source | Claim + Binding | Fragment + locator |
| 在 Decision 处理 Overview Diff | origin / owner Place | Change Set | notice / affected Group | changed Blocks |
| 无历史的 Source deep link | Sources | Source | external deep link | Revision + locator |

## 3.5 三层状态的用户语言

P0 不显示 Active Place、Surface Owner、Entry Context 术语，而显示：

- 一级导航当前项；
- `长期记忆系统 / 外部记忆 / 来源`等 DepthTrail；
- `从“图谱”进入 · 返回这条关系`；
- `查看完原文后回到这条回答`；
- `这项变化需要你判断`。

P3 才显示完整 owner、record role、snapshot 与 Return Envelope。

---

# 4. Place topology 与一级导航合同

## 4.1 Place 是稳定 root + 可恢复子现场

每个 Place 都包含：

```text
Place
  root_surface
  launched_workspaces[]
  place_state
  default_empty_state
  local_filters_or_scope
  primary_resources_or_evaluations
  explicit_handoffs
```

Place root 不是数据 root：Library Root 不拥有所有知识，Atlas Root 不拥有 Relations，Sources Root 不拥有文件。Knowledge Decision 不拥有 Decisions，也不是 Place；它是从 owner / event 打开的任务表面。

## 4.2 一级导航行为

| 用户动作 | 正确结果 |
|---|---|
| 点击另一个 Place | 切换 Active Place，恢复该 Place 最近稳定状态 |
| 点击当前 Place | 回到当前 Place Root，保留当前 Workspace 可返回状态 |
| Back | 返回真实上一步，包括跨 Place handoff |
| Forward | 恢复 Back 前的完整状态 |
| Up | 返回 owner hierarchy 的父 Scope，不改变 Active Place |
| Close Overlay / Inspector | 恢复触发点与 focus，不改变 Active Place |
| “在图谱中查看” | 显式切 Atlas，并转移相同 Selection / scope |

## 4.3 Active Place indicator

- Place root 与从该 Place 启动的 owner Workspace 都保持该 Place 处于 current-context；
- 若用户显式切到另一个 Place，owner Workspace 可在新的 Entry Context 下重新打开，但不复制；
- Service Workspace（Settings）和 Recovery Workspace（Trash）显示来源 Place 与返回目标，不伪装第六个 current Place；
- nav focus 与 current-context 分开，键盘经过一个 Place 不触发切换。

## 4.4 Place order

顺序固定：

```text
Home → Library → Atlas → Sources
```

这不是用户行为漏斗，而是从定位、拥有、连接到核验的知识顺序。判断在需要时从受影响语境打开；Attention、recentness、AI 状态与 viewport 不能重排或临时增加第五项。

## 4.5 Group Switcher 不是 Place switcher

Group Switcher 在当前 Active Place 中更换 Surface Owner：

- Home 下切 Group 保留 Home entry semantics；
- Library 下切 Group 保留目录 / Placement context；
- Atlas 下切 Group 保留 graph selection / viewport；
- Sources 下选择 Group 只改变 Source filter，不把 Group 变成 Source owner；
- Knowledge Decision 中切换 affected owner 只改变当前比较语境，不修改 decision truth，也不改变 Active Place。

---

# 5. 启动、恢复与新窗口

## 5.1 普通启动优先级

```text
1. crash / storage recovery that protects unsaved input
2. valid explicit deep link or OS intent
3. last restorable window workspace
4. user preference: always open Home, if explicitly chosen
5. Home Root
```

普通启动不自动重跑上次 Ask、Compiler、Migration、Restore 或 Knowledge Commit。它恢复输入与现场，并让用户决定是否继续副作用操作。

## 5.2 Last restorable workspace

必须同时满足：

- owner 仍存在或有合法 redirect；
- Place 仍可用；
- 无未解决的 destructive commit；
- snapshot / View revision 可解释；
- local state integrity 通过；
- focus target 可以恢复或降级到最近有效父级。

否则回到 owner 的稳定父级；仍失败才进入 Place Root，不直接清空到 Home。

## 5.3 New Window

新窗口默认 Home Root，因为它代表新的工作语境；用户从对象菜单选择“在新窗口打开”时，目标 owner 与 Entry Context 优先。新窗口不会复制另一窗口的 temporary filter、cursor 或 graph viewport，除非动作明确要求复制当前现场。

## 5.4 First use

首次进入 Home：

1. 一句话解释这是个人知识空间；
2. `建立知识群 / 写下知识 / 添加来源`三条平行动作；
3. Search 可用但返回诚实空态；
4. Ask 说明“你的知识库还没有可用于回答的内容”；
5. 不自动生成示例知识、空图谱、教程任务清单或伪 Overview。

## 5.5 External deep link

- 有 app window：在新 Return Envelope 中打开，不破坏原 Place state；
- 无 app window：按 Default Place map 打开；
- supporting record：先恢复 owner，再进入历史 / forensic mode；
- target moved：使用 redirect 并说明；
- target unavailable：保留 owner / Place 与 recovery actions；
- target deleted permanently：说明无法恢复，不用相似对象冒充。

## 5.6 OS-level Capture / widget

Capture intent 不强制打开 Home：

- 成功后显示 Destination Receipt；
- `完成并关闭`保持原应用现场；
- `查看来源 / 继续编辑 / 放入知识群`才打开对应 Place / Workspace；
- failure 保留输入和 recovery export。

---

# 6. Home / Knowledge Orientation 合同

## 6.1 唯一问题

> **我现在最值得回到自己知识世界的哪里？**

Home 不回答：所有知识在哪里、所有关系是什么、所有来源发生了什么、还有多少待处理。

## 6.2 首屏结构

```text
Home
  Space orientation
  Resume one context?          optional
  Knowledge Group entrances   3–7
  Continue Path               0–2
  Knowledge Changes           0–3
  Quiet global actions
```

若没有 Resume / Path / Change，相应区块完全省略；Home 可以非常安静。

## 6.3 Resume candidate

主 Resume 必须来自明确现场：

- 用户上次正在阅读 / 编辑的 owner；
- 与 Saved Path 分离保存的 PathProgress / ResumePoint；
- dirty Buffer 的 Recovery-protected 现场，或用户主动保留的 Explicit Draft；
- `changes_available / review_due` Group 中用户明确 deferred 的判断入口。

它显示：owner、原 Place、上次动作、可恢复深度、此后是否变化。仅“最近打开”不足以成为 Resume。

## 6.4 Group entrance selection

顺序：

1. 用户 pinned Groups，按用户顺序；
2. 当前 Resume 所属 Group，若未重复；
3. 具有用户相关高影响变化的 `changes_available / review_due` Group；
4. 最近进入且仍 active 的 Group；
5. 稳定名称作为 tie-breaker。

每个 Group 只显示：名称、一句边界 / orientation、继续位置或一项真实变化、formation presentation。禁止节点计数、来源数量、活跃度分数、成熟度环与 AI 摘要。

## 6.5 Knowledge Changes projection

进入 Home 的变化必须：

- 已影响 Accepted knowledge、Group boundary、Overview、正式 Relation、Saved Answer 或可核验性；
- 对当前用户仍相关；
- 具有确定 Primary Destination；
- 能用一句话说明 why now；
- 不与主 Resume 重复。

Home 只提供`查看影响 / 需要你判断 / 查看来源 / 继续阅读`，完整操作留在 Primary Destination / owner Workspace。

## 6.6 Home 不显示

- Ask / Search hero；
- 全量 Recents；
- All Groups catalog；
- Source import queue；
- Unplaced / Unfinished counts；
- Decision backlog count；
- system health card wall；
- AI daily brief；
- notification feed；
- activity streak；
- decorative whole-space graph。

## 6.7 Home state

Home state 保存：

- selected entrance；
- dismissed / deferred projection references；
- scroll；
- collapsed optional sections；
- last focus；
- displayed basis snapshot。

Home projection 更新时不在用户阅读中静默重排；显示`知识入口有更新`，用户刷新后创建 successor evaluation。

---

# 7. Library / Stable Ownership 合同

## 7.1 唯一问题

> **我稳定拥有哪些知识范围、知识身份、路径、回答与视图，它们在哪里？**

## 7.2 Primary Destination responsibility

Library 是以下内容的完整日常目录：

- Groups；
- Topic / Placement hierarchy；
- All Knowledge Nodes；
- Saved Paths；
- Saved Answers / Knowledge Snapshots；
- View Definitions；
- Archived knowledge resources；
- Unfinished / Unplaced / Stale / Contested 等 System Views。

Supporting Records 通过 owner 的 History / Definition / Evidence 进入，不显示 All Records。

## 7.3 从 Library 打开 owner Workspace

- Active Place 保持 Library；
- Surface Owner 切为 Group / Node / View / Path / Snapshot；
- Entry Context 保存 row、identity / placement、View evaluation、filters、sort、expanded、scroll；
- Back 返回原 row；
- “在图谱中查看”显式切 Atlas；
- “查看来源”可以先开 Evidence / Sources Lens，只有`在来源中打开`才切 Sources。

## 7.4 状态 View 不制造 Attention

Unfinished、Unplaced、Stale、Contested 与 Archived 只是可浏览集合：

- 不自动 badge；
- 不产生 overdue；
- 不进入 Home，除非形成合法 Resume 或 high-impact change；
- 不进入 Decision，除非存在需要用户作高影响判断的 Proposal / Change Set；
- View empty 是正常结果。

## 7.5 Library pins 与 recents

- Group pin 可以在 Home Group entrances 投影；
- Node / Topic / View / Path / Saved Answer pin 保留在 Library / Shell shortcuts；
- Source pin 不进入 Library pin list，Sources 自己管理；
- Recent 保存 open / edit / create / update / ask / use 等事件类型；
- Recent 不直接决定 Home、Search rank 或 Ask factual basis。

## 7.6 Library handoff

| 目标 | 动作 | 转移状态 |
|---|---|---|
| Atlas | 在图谱中查看 | selected Group / Node、relation scope、origin Placement |
| Sources | 在来源中打开 | owner / Claim / Binding / Source filter |
| Knowledge Decision | 需要你判断 | Proposal / Change Set / affected owner |
| Home | 回到首页 | Home previous state，不把当前 Node 自动设为 Home hero |

---

# 8. Atlas / Relational Exploration 合同

## 8.1 唯一问题

> **我的知识范围如何通过真实关系相连，我能沿哪条路径继续探索？**

## 8.2 Primary Destination responsibility

Atlas 完整承担：

- Group-level accepted Relations；
- Group selection 与一跳关系；
- supporting typed paths；
- Relation statement、direction、Applicability、limits 与 Evidence；
- Saved Path exploration overlay；
- Graph / List Equivalent；
- R3 global relation radius。

Node Local Graph、Group Map 与 Answer Route 是 scoped / temporary views，不复制 Atlas canonical layout。

## 8.3 从 Atlas 打开 Group / Node

- Active Place 保持 Atlas；
- Group Workspace 默认使用 Map-dominant profile：Relations 为 Primary，Overview 或当前 Reading Path 为可选 Companion，而不是完全不同 Atlas Detail page；
- Selection、selected edge、viewport、filters、relation family 与 list / graph mode 进入 Entry Context；
- Back 恢复 edge 与 viewport；
- 打开 Reading Path 不改变 Active Place；
- `在知识库中查看位置`显式切 Library 并 auto-reveal Placement。

## 8.4 Atlas projections

Atlas 不显示：

- shared Source edge；
- similarity edge；
- View membership；
- co-open / recent；
- query retrieval jump；
- provenance activity；
- supporting record node；
- rejected / proposed Relations by default。

需要核验 Relation 时可打开 Evidence Inspector / Source Reader，但 Active Place 保持 Atlas，除非选择`在来源中打开`。

## 8.5 One Group / no Relation

Atlas 的空态解释：

- 这个 Space 目前只有一个 Group；或
- 还没有已接受的群关系；
- 可以进入 Group、浏览 Library、搜索或手工建立 Relation；
- 不显示随机星点、候选线、相似度云或“让 AI 补全关系”。

## 8.6 Atlas attention

Relation review_due 在 selected edge / Inspector 中出现；只有高影响 relation identity / truth decision 打开 Knowledge Decision。Atlas Root 不显示 Decision badge count，也不因某个 Source 新版本立即重排 resting layout。

---

# 9. Sources / Material & Provenance 合同

## 9.1 唯一问题

> **我的原始材料是什么、当前能否核验、它支撑或挑战了什么？**

## 9.2 Primary Destination responsibility

Sources 完整承担：

- Source Registry；
- Source identity / Revision / Representation；
- Reader、Find、Annotation；
- Fragment、Binding、Selector 与 locator repair；
- managed / linked / reference-only；
- parse / OCR / transcript / translation；
- rights / permission / availability；
- import、disconnect、archive、trash 与 reconnect；
- Source change impact analysis。

## 9.3 Sources root views

稳定 Views：

- All Sources；
- Newly Added；
- Processing / Partial；
- Changed；
- Unavailable / Permission Lost；
- Unbound but usable；
- Archived。

它们是状态与材料管理，不是 Decision debt。`Newly Added`不会因为存在时间产生 overdue。

## 9.4 从 Sources 进入 Knowledge

- Source → Binding → Target Node / Claim 可以打开 owner Workspace；
- Active Place 默认保持 Sources，以便 Back 回到 Source / Revision / locator；
- `在知识库中查看`显式切 Library 并 auto-reveal owner identity / Placement；
- `在图谱中查看关系`只在已有正式 Relation 时切 Atlas；
- 共享材料不自动生成 Relation。

## 9.5 Source change routing

| Source event | Primary Destination | 其他投影 |
|---|---|---|
| Source added | Sources | Capture Receipt；无 Home / Decision |
| Parse partial / failed | Sources / Status Center | owner Citation 显示 coverage |
| Locator relocated | Sources | affected Citation 轻提示；不进入 Decision |
| Representation regenerated | Sources | Forensic history；不改知识 |
| Support materially changed | Sources impact | affected owner notice / History |
| Accepted knowledge needs decision | Knowledge Decision Workspace | Home 最多一条 notice；Sources 保留 impact details |
| Permission lost | Sources | owner Evidence availability；必要时 Status Center |

## 9.6 Source pins

Source / locator pin 只在 Sources 快捷区或 Shell recent targets 出现，不成为 Home Group、Library knowledge pin 或 Atlas node。用户要保存跨知识阅读顺序时创建 Saved Path step，而不是把 Fragment 变成全局 favorite。

---

# 10. Knowledge Decision / High-impact Judgment 合同（非 Place）

## 10.1 唯一问题

> **哪些变化会改变身份、当前知识、正式结构、定义或可恢复性，需要我作判断？**

## 10.2 Decision admission

必须至少满足：

1. 需要用户作不可由既有安全规则替代的判断；
2. 会改变 Accepted knowledge、identity、formal Relation、Group / Topic structure、schema / policy、migration mapping 或 destructive outcome；
3. 具有明确 Base、affected scope、reversibility 与 defer consequence；
4. 不能只通过 owner Workspace 的小型可撤销动作完成。

## 10.3 Decision 不接收

- Source added；
- parse / OCR pending；
- ordinary Working content；
- Unplaced / Unfinished；
- empty / zero-yield；
- low-risk projection refresh；
- View member changed；
- Search / Ask history；
- all AI candidates；
- system health；
- “很久没整理”。

## 10.4 Decision entry identity

Decision entry 只是 Proposal / Change Set / Conflict / Migration 的 presentation：

- 显示 owner、reason now、affected、decision class、defer condition；
- 不复制完整 Diff / Evidence；
- 打开统一 Decision Surface；
- Home / owner projections 指向同一 decision id；
- accept / reject / defer 后所有投影同时更新。

## 10.5 Decision context

Decision Workspace 围绕当前决定组织，不提供默认全局队列。可处理的 decision classes 包括：

- Identity；
- Truth / Applicability；
- Structure；
- Relation；
- Overview；
- Source impact；
- Definition / Migration；
- Destructive / Recovery。

同一 owner 或同一 Change Set 可以在 Workspace 内切换 related bundles；不显示“还有 287 项”制造清零压力，也不要求用户从导航主动巡检。

## 10.6 Decision completion

- 完成后回到 Entry Context 或 affected owner；
- partial commit 保留未处理部分为同一 successor bundle；
- defer 保存 next-eligible condition；
- reject 在无新 Evidence / Base 变化时不再出现；
- failure 保留 draft decision 和已提交原子边界；
- Undo 根据 Change Set 恢复，不依赖 Decision entry 是否仍在触发位置。

---

# 11. scoped Lens 与 global Place 的唯一真相

## 11.1 对应关系

| scoped surface | global Place | shared truth | scoped responsibility | handoff action |
|---|---|---|---|---|
| Group Contents | Library | Topic / Placement | 当前 Group 目录 | 在知识库中查看位置 |
| Group Map / Local Graph | Atlas | Relation / connection families | 当前范围 R0–R2 | 在图谱中查看 |
| Group / Node Sources | Sources | Source / Fragment / Binding | 当前 owner 的依据 | 在来源中打开 |
| Owner notice / History | Knowledge Decision（非 Place） | Proposal / Change Set | 当前 owner 影响摘要 | 需要你判断 |
| Answer Knowledge Route | Atlas overlay | current accepted Relations + retrieval jumps | 本次 Run | 查看长期关系 |
| Evidence Inspector | Sources / Reader | Fragment / Binding / Revision | 当前 Claim 核验 | 打开完整来源 |

## 11.2 scoped surface 不拥有第二状态

- Group Map 不保存另一份 Relation standing；
- Group Sources 不保存另一份 Source availability；
- owner notice / History 不保存另一份 decision state；
- Library hierarchy 与 Group Contents 不保存两棵 Topic tree；
- Answer Route 可以保存 historical query overlay，但不能改写 Atlas layout 或 formal edge。

## 11.3 local-to-global handoff

handoff 必须传递：

- owner / selected identity；
- current scope；
- exact relation / binding / proposal；
- filters compatible with target Place；
- source Entry Context；
- Back target；
- focus target。

目标 Place 无法表达某个临时 filter 时，明确显示“仅保留了范围，未带入临时排序”，不能静默猜测。

## 11.4 global-to-local handoff

从 Atlas / Sources / Knowledge Decision 进入 owner Workspace 时：

- 使用同一 canonical Workspace；
- 默认打开与 entry 最相关 Lens；
- 不隐藏 Group Overview / Node Reading 主轴；
- 允许一键回到 Place Root / selected row；
- 不把局部检查状态写入 owner truth。

---

# 12. 信息归属与投影矩阵

| 信息 / 资源 | Primary Destination | Home | Library | Atlas | Sources | Contextual Decision / History |
|---|---|---|---|---|---|---|
| Group identity / boundary | Library | entrance projection | 完整目录 | relation endpoint | source filter only | affected owner only |
| Topic / Placement | Library | 不显示 | 完整结构 | structural context only | 不显示 | structure impact only |
| Node identity / content | Library / owner | resume / Group entrance only | 完整目录与阅读 | selected endpoint / summary | Binding target | affected owner |
| Overview | owner / Library entry | orientation excerpt only | owner entry | Group summary only | support target | Diff decision only |
| Formal Relation | Atlas | high-impact notice only | summary / inspect link | 完整图与列表 | Evidence only | relation decision only |
| Source identity | Sources | 默认不显示 | support link | 不作 canonical node | 完整 Registry / Reader | impact decision only |
| Fragment / Binding | Sources / owner Evidence | 不显示 | Evidence link | relation support only | 完整核验 | changed support decision |
| Explicit Draft / Recovery Resume | Library / owner | one Resume when active | Draft / Recovery entry | 默认不显示 | source-derived proposal link | conflict only |
| Proposal | owner context | 默认不显示 | 状态提示 only | candidate layer explicit | source impact link | high-impact bundle only |
| Change Set | owner History / Decision | at most one high-impact notice | affected history link | affected relation | source impact | decision / history |
| Saved Path | Library | continue projection | 完整目录 | path overlay | source steps only | impacted path only |
| Saved Answer | Library | resume / impacted notice | Paths & Answers | historical route overlay | cited sources | re-evaluation decision only |
| View Definition | Library or owning Place | 不显示 | knowledge Views | Atlas Views if relation-specific | Source Views | Decision filters are workspace state |
| View Evaluation | owning Place | entrance projection only | current results | current graph filter | source results | current affected scope |
| Pin | owning Place / Shell | pinned Groups only | knowledge pins | optional saved Atlas view | source pins | no decision pin priority |
| Recent event | owning Place / Library Recent | not raw list | typed Recent | local history only | source recent | owner decision history |
| Attention Signal | owner event + Primary Destination | eligible projection | owner state | selected edge | source impact | decision-required |
| System health | Status Center | only if product unusable | compact state | compact state | relevant details | not a decision item |
| Trash item | Trash Recovery Workspace | 不显示 | archived / trash entry link | historical references | source trash entry | destructive decision link |

矩阵中的“Primary Destination”表示完整发现与操作责任，不改变对象的 Truth Role、owner、导出或删除规则。

---

# 13. Capture、Destination 与 Receipt

## 13.1 Capture intent 不等于 destination

Capture 入口可以来自：

- global Add；
- Group / Topic / Node context；
- Sources；
- OS share sheet / widget；
- browser / email / connector；
- Answer Transform；
- drag and drop。

入口只提供默认 Scope 和 Return Envelope。系统必须先判断输入身份，再确定 Source、Working Node、Annotation、Fragment、Proposal、Relation 或其他合法结果。

## 13.2 Destination Receipt

```text
DestinationReceipt
  receipt_id
  input_ref
  committed_results[]
    result_ref
    result_role
    primary_place
    owner_ref
    persistence_state
    acceptance_state
    processing_state
  proposed_results[]
  failed_results[]
  continue_actions[]
  undo_scope
  return_envelope_ref
```

Receipt 是一次动作的结果说明，可以进入 History，但不是 Primary Resource 或知识真相。

## 13.3 人话完成语义

| 结果 | 首要文案 | Primary Destination | 继续动作 |
|---|---|---|---|
| user thought current | 已更新当前知识 | Library / owner | 继续编辑 / 放入知识群 / 撤销 |
| recovery protected | 近期修改已在本机保护，尚未更新当前知识 | owner / Recovery | 检查并继续 / 另存草稿 / 复制 |
| explicit draft saved | 已保存为草稿，不用于默认回答 | Library / owner | 继续草稿 / 设为当前知识 |
| Source committed | 来源已保存；解析可以继续 | Sources | 查看来源 / 后台处理 / 稍后形成知识 |
| Source-only complete | 来源已保存；没有发现需要形成的知识变化 | Sources | 阅读 / 标注 / 归档 |
| Proposal created | 已形成 1 项需要判断的建议；知识尚未改变 | owner / Knowledge Decision when high impact | 查看影响 / 稍后决定 |
| reviewed change committed | 已更新当前知识 | owner / Library | 查看变化 / 撤销 |
| partial success | 已保存 7 项，2 项尚未完成 | each owner + Receipt | 查看失败项 / 重试 |
| write failed | 还有内容未写入本机 | current surface | 复制 / 导出恢复 / 重试 |

## 13.4 多结果 Capture

一份输入可以同时产生：

- 1 个 Source；
- 0–N 个 Working / Proposed knowledge changes；
- 0–N 个 Evidence Bindings；
- 0–N 个 Decision Bundles。

Receipt 按结果角色汇总，不把 50 个候选写成 50 个 toast。Source Commit 的成功不因 Knowledge Proposal 失败而回滚。

## 13.5 Capture return

- 从 owner Workspace Add：完成后默认回原 Workspace，并显示局部 receipt；
- 从 Sources Add：留在 Sources，选中新 Source；
- 从 OS intent：默认关闭或留在轻量 receipt；
- 从 Answer Transform：回 Answer，并说明新结果在哪里；
- 只有用户选择`需要你判断`才打开 Knowledge Decision，并保持原 Active Place；
- 只有用户选择`在知识库中查看`才切 Library。

---

# 14. Attention routing 与安静产品合同

## 14.1 Attention Signal

Attention Signal 是根据 owner state、event、用户当前语境与产品政策产生的可重建观察：

```text
AttentionSignal
  signal_id
  owner_ref
  trigger_event_ref
  primary_destination
  reason_now
  affected_scope
  decision_required: none | optional | required
  time_condition
  current_relevance_basis
  reversibility
  eligible_surfaces[]
  suppression_reason?
  next_eligible_condition?
  supersedes_signal_ref?
```

它不保存“知识是否重要”“用户应该焦虑到什么程度”或模型 confidence。

## 14.2 路由优先级

```text
Does it block the current task?
  yes → inline owner surface
  no
    Does it require high-impact judgment?
      yes → Knowledge Decision primary + optional owner/Home projection
      no
        Is it material/provenance state?
          yes → Sources / Evidence owner
          no
            Is it knowledge browse state?
              yes → Library / owner View
              no → Status Center or silent history
```

## 14.3 Home eligibility

一个 Signal 进入 Home 必须同时满足：

- 会改变用户对一个 Group / Path / Answer 的理解或恢复路径；
- 当前仍相关；
- 不是 raw system health；
- 不是普通 unfinished / unplaced / source added；
- Primary Destination 已确定；
- 与主 Resume 不重复；
- 最多形成一句变化摘要与一个主动作。

## 14.4 Knowledge Decision eligibility

一个 Signal 打开 Knowledge Decision 必须拥有：

- decision class；
- Base；
- proposed outcome；
- affected scope；
- locked / preserved；
- defer consequence；
- undo / rollback；
- Evidence / rationale。

缺一时留在 owner context 补齐，不以不完整 AI 卡片占据 Decision Workspace。

## 14.5 Suppress / Merge / Defer

- **Suppress**：没有当前行动价值，不显示但保留必要 event history；
- **Merge**：多个事件要求同一个用户决定，合并为一个 bundle；
- **Defer**：用户或政策等待新证据、时间条件、相关打开或显式回访；
- **Dismiss projection**：只隐藏一个 Surface 的投影，不等于 reject decision；
- **Reject decision**：保存判断与 Base，无新依据不重现；
- **Resolve**：所有投影读取同一 successor state。

## 14.6 通知边界

默认没有逐项系统通知。可选通知必须：

1. 用户显式开启对应类别；
2. 事件时间敏感；
3. 影响明确且超过用户允许阈值；
4. 用户不会在当前 owner / Place 自然遇见；
5. 可以安全合并；
6. 不展示敏感正文；
7. 点击进入 Primary Destination 并恢复 owner；
8. 可在应用内关闭该类别。

通知点击率、红点清零率与 Decision 打开量都不是成功指标。

---

# 15. 跨地点 Transition Contract

## 15.1 每次 handoff 必须转移

```text
PlaceHandoff
  source_place
  target_place
  source_owner
  target_owner
  selection_transfer
  scope_transfer
  exact_reason_ref
  compatible_filters
  dropped_temporary_state[]
  target_lens
  return_envelope
  focus_target
```

## 15.2 核心转场

| 转场 | 目标默认 Lens / Surface | 必须带入 | Back 恢复 |
|---|---|---|---|
| Home → Group | Overview / last safe Lens | Group、resume anchor、formation context | Home entrance / evaluation |
| Home → Knowledge Decision | Decision Surface | signal、Change Set、affected owner | Home notice |
| Library → Node | Reading | identity、Placement、Anchor、View row | Library View / row / scroll |
| Library → Atlas | Graph / List | selected Group / Node、origin Placement | Library selection |
| Atlas → Group | Map + Overview / Reading | selected edge、relation path、viewport | edge / graph focus |
| Atlas → Sources | Source Reader / Evidence | Relation support Binding | selected Relation Inspector |
| Sources → Node | Reading + Evidence focus | Binding、Target、Revision | Source locator / Registry state |
| Sources → Knowledge Decision | Source impact Decision | impact group、changed Fragment、Target | Source change impact |
| Knowledge Decision → Group | affected owner + notice / History | Decision / Change Set / changed Anchors | Decision section |
| Knowledge Decision → Sources | Source impact | Revision / Fragment / Binding | Decision Evidence section |

## 15.3 Search / Ask 不改变 Place

Global Search、Quick Ask、Add、Command 打开 Overlay 时保留 Active Place。打开结果或 Full Answer 仍继承该 Place；只有结果中的显式 Place handoff 改变。Search 关闭后恢复 Query、filters、result set 与 origin Place；Answer 关闭后恢复 question origin、Selection 与 focus。

## 15.4 同一 owner 的 Place re-entry

用户在 Atlas 的 Group Workspace 选择`在知识库中查看`：

1. Active Place 改为 Library；
2. Surface Owner 仍是同一 Group；
3. Selection / Anchor 保留；
4. target Lens 变 Structure / Reading；
5. Atlas viewport 保存到 Atlas Place State；
6. Back 回到 Atlas 同一 edge；
7. Library Back 回到它自己的前一目录状态。

## 15.5 Failure isolation

- target Place index unavailable：保留 source Place 与 owner，提供本地 / list fallback；
- target owner deleted：显示 redirect / recovery，不切空 Place；
- Source unavailable：保持 Claim / Relation context，显示 last available Representation；
- Knowledge Decision stale：打开 before / current Base compare，不自动提交；
- Place State corrupted：重置该 Place Workspace State，不影响其他 Places 或 canonical data；
- focus restore failed：移动到新 Surface 标题并播报，不留在隐藏 Overlay。

---

# 16. Deep link 与 Default Place Resolution

## 16.1 Default map

| Target role | 无 Entry Context 的 Default Place | 打开方式 |
|---|---|---|
| Space Orientation | Home | Home Root / specified projection |
| Group / Topic / Node / Overview | Library | owner Workspace + hierarchy context |
| View / Saved Path / Saved Answer / Snapshot | Library | corresponding Workspace / historical mode |
| Formal Relation / Relation type path | Atlas | selected edge + Inspector |
| Source / Revision / Representation | Sources | Registry / Reader |
| Annotation / Fragment / Binding | Sources | owner Source Reader + forensic focus |
| Proposal / Conflict / Change Set | owner Default Place | Knowledge Decision Surface |
| Property Definition / Migration | Settings / owner Default Place by intent | Definition Service / Migration Decision |
| Trash / Tombstone | Trash | Recovery Workspace |
| Query Turn current unsaved | inherit stored origin if valid | Answer Workspace |
| system health / backup | Settings / Status Center | service surface |

## 16.2 Owner-first record resolution

Supporting record link 解析顺序：

```text
record ID
  → verify owner
  → verify record standing / revision
  → resolve Default or stored origin Place
  → restore owner Workspace
  → open forensic Lens / Inspector
  → establish return / parent fallback
```

## 16.3 Shareable links

复制链接时允许选择：

- `打开这条知识`：Default Place；
- `打开这个位置`：包含 Placement / Anchor；
- `打开我现在的查看方式`：包含 non-sensitive Lens / filters / relation scope；
- `打开历史版本`：包含 revision / snapshot；
- `打开这项需要判断的变化`：包含 decision id 与 Base。

Workspace cursor、unsaved input、private temporary Query、sensitive selection 与 raw Return Stack 默认不进入分享链接。

## 16.4 Link expired / inaccessible

必须说明：

- target 是否曾存在；
- owner 是否仍存在；
- moved / redirected / archived / trashed / permanently deleted / unavailable；
- 当前可以进入的最近合法父级；
- 是否有历史 snapshot；
- Back / Close 返回哪里。

不使用相似对象自动替换精确 target。

---

# 17. Place State、窗口与 Space

## 17.1 Place State schema

```text
PlaceState
  place
  root_or_workspace
  owner_ref?
  selected_identity?
  placement_or_anchor?
  local_scope
  active_view_revision?
  evaluation_snapshot?
  filters / sorts / grouping
  expanded_items
  scroll
  graph_or_list_state?
  open_inspector?
  last_safe_focus
  open_decision_draft_ref?
  saved_at
  integrity_state
```

## 17.2 Persistence classes

| State | persistence | sync | export |
|---|---|---|---|
| Active Place / last owner | local durable | optional | optional continuity |
| filters / expanded / scroll / viewport | local durable | optional | optional |
| View Definition | canonical / supporting | yes | required |
| Pin | embedded user preference | optional by device policy | required in full package |
| Return Stack | session / local durable bounded | no by default | no |
| decision draft | supporting recovery | yes if safe | required while live |
| Explicit Draft / Recovery Checkpoint | supporting / recovery record | yes / local-first | required |

## 17.3 Restart

Restart 恢复：

- window bounds / responsive mode；
- Active Place；
- owner Workspace；
- Place State；
- last safe focus；
- durable input / decision draft；
- system limitation summary。

不自动恢复：

- ephemeral hover；
- stale streaming cursor；
- uncommitted destructive confirmation；
- expired temporary external results；
- hidden sensitive clipboard content。

## 17.4 Multi-window

- window A 的 Atlas filters 不改变 window B；
- window B 接受 Relation 后，window A 显示 current graph changed / refresh；
- current Selection 不跨窗口抢占；
- accepted content / View Definition / Source Revision / Decision state 共享；
-同一 decision 另一窗口已完成时，当前窗口转为 completed / compare，不允许重复提交；
- 关闭窗口只关闭其 Workspace State，不删除 owner。

## 17.5 Space switch

每个 Space 独立保存四个 Place States。切换 Space：

- 当前窗口写入原 Space state；
- 恢复目标 Space Active Place / owner；
- Search / Ask scope 重置或显式确认，不静默跨硬隔离边界；
- external Source connection、Decision 与 Atlas 都使用目标 Space policy；
- Back 可以回原 Space，但显示边界切换；
- 默认单 Space 不暴露多 Space 管理复杂度。

## 17.6 Reset

`重置当前地点布局`只清除当前 Place State；`重置所有界面布局`清除所有 Workspace Continuity。两者都不删除 View Definitions、Pins、Paths、Relations、Sources、Decisions、Explicit Draft、Recovery protection 或 knowledge。

---

# 18. 响应式、移动端与可访问性

## 18.1 Desktop wide

- 四 Places 在 sidebar 固定顺序；
- owner Workspace 可用 content + Context Rail / Relation Lens；
- Place handoff 不打开不可预测新窗口；
- focus groups 区分 sidebar、hierarchy / list、content、rail；
- current Place、current owner、selected item 与 focused control 有四种不同视觉语义。

## 18.2 Desktop compact / tablet

- sidebar 可折叠，但当前 Place 在 top bar / navigation control 可见；
- Group Split 变 tabs / sequential panes，owner 与 Entry Context 不变；
- Atlas 默认可在 Graph / List Equivalent 间切换；
- Knowledge Decision 可以全屏 Sheet；
- Sources Reader 与 Binding Inspector 顺序排列；
- 返回触发点不被遮挡。

## 18.3 Mobile

- 四 Places 顺序保持，可使用 tab bar + More / sheet；Decision 通过 notice / owner / Search / Command 可发现，但不临时加入导航；
- Quick Capture 是全局动作，不替换 Home；
- 普通启动恢复上次安全 Workspace，widget / share intent 直接进 Capture；
- Home 仍知识 / Resume 优先，Ask 不变成唯一首屏；
- Atlas 默认 List Equivalent，选中小范围后可开 Graph；
- Source Reader、Evidence、History、Working edit 与恢复能力继续成立；
- 高影响批量 migration / restore 可以只读检查并明确要求 desktop 完成，但不能静默缺席。

## 18.4 Keyboard

- `Tab` 在 landmark / focus group 间移动；
- arrow keys 在 PlaceNav / tree / list / tabs 内移动；
- focus Place item 不切换；Enter / Space 激活；
- `Cmd/Ctrl+1…4`可直接切四 Places，顺序固定；
- Search / Ask / Add 有全局快捷键并播报继承 Scope；
- Back / Forward 与 Up / Close Detail 使用不同快捷键；
- Place handoff 后 focus 到目标标题、selected row 或 exact locator；
- Return 后 focus 回触发控件或等价替代。

## 18.5 Screen reader

必须播报：

- current Place；
- owner title / role；
- Entry Context summary；
- selected vs focused；
- projection reason / Primary Destination；
- Graph List relation direction / standing；
- decision affected / undo；
- receipt destination；
- return target。

## 18.6 200% zoom / reflow

- PlaceNav 不以只剩图标且无 accessible name 的方式收缩；
- current Place / owner / return target 保持可见或一键可查；
- Home 不因卡片重排把变化放到 Resume 之前；
- Decision primary action 与 consequence 不被 sticky layer 遮挡；
- source locator、relation list 与 Library row 可以单列完成任务；
- horizontal pan 只用于必要 graph / media，不用于普通阅读或表单。

## 18.7 Non-color semantics

Current Place、has projection、decision required、source unavailable、selected edge 与 active filter 不能只靠颜色。使用文字、shape / icon、position、accessible state 与详细说明的组合。

---

# 19. State families 与错误归属

## 19.1 Place root states

每个 Place 至少覆盖：

- first-use；
- true empty；
- populated；
- filtered empty；
- partial / stale；
- offline-local；
- target unavailable；
- Place State corrupted；
- large-scale；
- recovery / redirect。

## 19.2 Home states

| 状态 | 正确行为 |
|---|---|
| no knowledge | 三条开始路径；不伪造 Group / Ask answer |
| knowledge, no recent | stable Groups；无 Resume 区 |
| resume target changed | 显示变化与 current / previous 选择 |
| all Groups dormant | 显示 pinned / stable catalog入口；不催促激活 |
| high-impact changes | 最多 1 条 notice；Primary Destination 明确 |
| projection stale | 保留 last good entrances + refresh |

## 19.3 Primary Destination unavailable

- Library index unavailable：stable Group tree / canonical open 仍可用；
- Atlas graph projection unavailable：List Equivalent / known Relations 可用；
- Sources remote unavailable：local snapshots / metadata / Bindings 可用；
- Decision evaluation unavailable：已知 decision records 可用，不显示 zero；
- Home projection unavailable：直接进入四 Places 与 last stable owner；
- AI unavailable：不改变 Place topology。

## 19.4 Cross-place partial

若 handoff 只能带入部分状态：

- 明确列出保留与未保留内容；
- 仍保存 source Return Envelope；
- 不创建第二对象补偿；
- 不把未支持 filter 解释为 no result；
- 允许取消并留在 source Place。

## 19.5 Attention evaluation failure

Attention 计算失败不隐藏 canonical owner state，也不把所有 events 推到 Home / Decision。保留 last good projection、显示 evaluation limitation，用户仍可从 Library / Sources 与 affected owner 主动进入。

---

# 20. 二十个代表场景

## 20.1 普通启动继续 Node

上次在 Library 语境阅读“外部记忆”L4 Explanation。普通启动恢复 Library + Node + Anchor，而不是先跳 Home。

## 20.2 新窗口进入 Home

用户新建窗口。没有显式 target 时进入 Home Root；原窗口的 Atlas viewport 和 Working edit 不复制。

## 20.3 Home 不是 Ask hero

已有 12 个 Groups。Home 先显示一个 Resume 与 3–7 个 Group entrances；Ask 保留在全局动作，不占据视觉中心。

## 20.4 从 Home 进入 Group 再返回

Home Resume 打开“AI 产品设计”Group 的一个 Anchor。Active Place 保持 Home；Back 恢复同一个 Resume projection 和 scroll。

## 20.5 从 Library 进入同一 Group

Library hierarchy 打开同一 Group。Workspace content 与 Home 入口完全相同，但默认 Structure / Reading context、Entry 与 Return 不同。

## 20.6 从 Atlas 进入同一 Group

用户沿 provides_foundation_for Relation 打开 Group。Active Place 为 Atlas，默认 Map + Overview；Back 回到选中 edge 和 viewport。

## 20.7 Atlas → Library handoff

在 Group Workspace 选择“在知识库中查看位置”。Active Place 切 Library，auto-reveal Placement；Back 回 Atlas edge，Library state 仍可单独恢复。

## 20.8 Node → Source → return

从 Node Claim 打开 Evidence Inspector / Source Reader。Active Place 仍 Library；返回恢复 Claim。只有“在来源中打开”才切 Sources。

## 20.9 Relation → Source → return

从 Atlas Relation Inspector 核验 Evidence。Source Reader 继承 Atlas；返回恢复 edge。切 Sources 后 Registry 选中同一 Source / Revision。

## 20.10 新来源不进 Knowledge Decision

添加一份 PDF。Receipt 写“来源已保存”，Primary Destination 为 Sources；Home、Library 与 Decision 没有红点。

## 20.11 Source change 只影响定位

网页内容移动但 quote digest 未变。Sources 自动标记 relocated，Citation 更新 locator；不创建 Knowledge Decision。

## 20.12 Source change 改变支持

新 Revision 使关键 Claim support changed。Sources 显示 impact，受影响 Node / Overview 显示同一 notice；只有 accepted knowledge 需要判断时打开同一 Decision bundle，Home 最多一条 projection。

## 20.13 Unplaced Working 不进 Home

全局记录一条想法。Receipt 指向 Library Unfinished / Unplaced；它只有作为唯一明确 Resume 时才可能出现在 Home，不显示待整理红点。

## 20.14 Knowledge Decision 从 Home 打开

Home 显示“法国租房的入住期限依据发生变化”。打开同一 Knowledge Decision，完成后返回 Home，Group / Sources projections 同步消失或更新。

## 20.15 Defer 不重复

用户将一项 identity merge 延后到“下一份来源到达”。第二天启动不提醒；新相关 Source Commit 后同一 Decision successor 才重新 eligible。

## 20.16 Saved Answer deep link

从系统外打开 Saved Answer。无 origin 时 Active Place 为 Library；Original Snapshot、current impact 与 Re-evaluate 可查。

## 20.17 Supporting record deep link

打开一个 Evidence Binding URL。系统先恢复 Source owner 与 Target Claim，再在 Sources forensic focus 中显示 record，不出现 UUID 页面。

## 20.18 Place State corrupted

Atlas viewport state 损坏。只重置 Atlas layout，Relations、Library selection、Home、Sources、Decision 与 owner content 不变。

## 20.19 两窗口同时处理决定

窗口 A 打开 Knowledge Decision，窗口 B 从受影响 Group notice 接受同一 Diff。窗口 A 立即转 completed / compare，不能再次提交；两个窗口的 Place States 保留。

## 20.20 Mobile share capture

用户从浏览器分享网页。移动端直接进入 Capture，Source Commit 后显示 Receipt；可以关闭回浏览器或选择“在来源中查看”，不强制经过 Home。

---

# 21. Given / When / Then 验收

## 21.1 三层位置可区分

**Given** 用户从 Atlas 一条 Relation 打开 Group  
**When** 查看 App Shell 与 Surface header  
**Then** Atlas 为 Active Place，Group 为 owner，Relation edge 为 Entry Context；三者不合并成一个 breadcrumb。

## 21.2 同一 Group 不复制

**Given** 同一 Group 分别从 Home、Library、Atlas 打开  
**When** 比较 Overview、content revision 与 Selection  
**Then** owner identity 与 canonical content 相同，仅 Entry、default Lens 与 Return Envelope 不同。

## 21.3 Home 知识优先

**Given** Space 已有成熟知识  
**When** 打开 Home  
**Then** Resume / Group entrances 在 Ask / Search 之前；页面不以 AI composer 为视觉 Hero。

## 21.4 普通启动恢复现场

**Given** 上次安全关闭在 Library Node Anchor  
**When** 重新启动  
**Then** 恢复 Library、Node、Placement、Anchor、scroll 与 focus；不强制先到 Home。

## 21.5 New Window 使用 Home

**Given** 用户已有一个工作窗口  
**When** 新建空窗口  
**Then** 新窗口进入 Home Root；原窗口 Workspace State 不复制或改变。

## 21.6 一级导航与 Back 分工

**Given** 用户 Home → Group → Atlas → Source  
**When** 分别使用 Back 与点击 Library  
**Then** Back 逐步恢复真实历史；Library 恢复自己的最近稳定 state，不冒充 Back。

## 21.7 Home 不复制 Recent

**Given** Library 有 30 条 typed Recent events  
**When** 打开 Home  
**Then** 最多一个可解释 Resume；不显示原始 Recent list，也不因打开次数提升知识权威。

## 21.8 一个事件一个 Primary Destination

**Given** Source change 产生 Knowledge Decision  
**When** Home、Group、Sources 与 Decision 同时可见投影 / 任务  
**Then** 完整决定只在 Knowledge Decision Workspace；所有入口共享 decision id、owner 与状态。

## 21.9 新 Source 不制造债务

**Given** 用户添加 Source 并只保存  
**When** Commit 完成  
**Then** Sources 为 Primary Destination；Decision / Home 无 badge，Receipt 明确 zero-yield 也可成功。

## 21.10 Working 与 Knowledge Decision 分开

**Given** 用户保存 unplaced Working Node  
**When** 离开 Editor  
**Then** Library Unfinished / Unplaced 可找回；Decision 不出现，Home 只有合法 Resume 才投影。

## 21.11 scoped-to-global 同义

**Given** Group Map 选中一条 Relation  
**When** 选择“在图谱中查看”  
**Then** Atlas 显示同一 endpoints、type、direction、standing 与 Evidence；没有复制 edge。

## 21.12 Evidence 不强切 Place

**Given** 用户从 Library Node 打开 Citation  
**When** 进入 Source Reader  
**Then** Active Place 仍 Library，Back 回 Claim；显式“在来源中打开”才切 Sources。

## 21.13 Destination Receipt 完整

**Given** Capture 同时产生 Source、Working Patch 与 Proposal  
**When** 完成  
**Then** Receipt 分别说明三个结果的 Primary Destination、persistence、acceptance、processing、continue 与 undo。

## 21.14 Defer 有条件

**Given** 用户延后一个 Decision bundle  
**When** 没有新 Evidence、时间或相关语境  
**Then** item 不因日期或 backlog count 重现；条件满足时产生 successor eligibility。

## 21.15 System health 不进入 Knowledge Decision

**Given** Index rebuilding、storage low、AI unavailable 同时发生  
**When** 用户回到受影响 owner 或打开 Status Center  
**Then** Knowledge Decision 不因系统状态新增事项；Status Center 分别说明影响，owner Surfaces 使用相关局部状态。

## 21.16 Deep link Default Place

**Given** 从系统外分别打开 Node、Relation、Source Revision 与 Change Set  
**When** 没有 stored origin  
**Then** 分别进入 Library、Atlas、Sources；Decision 先按 owner 进入对应 Place，再恢复 exact record focus。

## 21.17 Place State 隔离

**Given** Atlas State 损坏  
**When** 选择重置当前地点布局  
**Then** 只清 Atlas Workspace State；Library、Home、Sources、Decision draft 与 canonical data 不变。

## 21.18 多窗口不抢状态

**Given** 两窗口打开不同 Places  
**When** 一个窗口切换、过滤或选择  
**Then** 另一个窗口 Active Place、Selection、viewport 与 focus 不变；canonical commit 以更新提示传播。

## 21.19 Responsive 责任不变

**Given** desktop Group Workspace 缩到 mobile  
**When** PlaceNav、Split、Rail 改为 tab / sheet  
**Then** Active Place、owner、Entry、Search、Ask、Evidence、Decision handoff 与 return 仍成立。

## 21.20 Focus 不触发导航

**Given** keyboard 用户在 PlaceNav 移动 focus  
**When** 尚未按 Enter / Space  
**Then** Active Place 与 content 不变；激活后 focus 到目标 Surface 的可理解起点，返回后回到触发项。

---

# 22. 官方研究依据与产品推论

## 22.1 Capacities Navigation

Capacities 官方文档把同一个 object 的 full-page、preview modal、side panel 与多个 tabs 分开，并让 tabs 各自保留 breadcrumb 和 panel state。

产品推论：同一知识 identity 可以在不同 Surface 与进入语境中出现，但不能复制 content；Entry Context、Return 与 per-workspace state 必须独立于 owner truth。

[Capacities Navigation](https://docs.capacities.io/reference/navigation)

## 22.2 Capacities Object Dashboards 与 Queries

Capacities 的 object types 位于 sidebar，每种 type 有可定制 dashboard；Queries 根据规则动态更新，Dashboard sections、All content、filter / sort / group 与 saved queries 是不同机制。

产品推论：目录、动态观察、快捷 section 与对象 truth 必须分开；但本产品不采用 type-first sidebar / dashboard 作为核心，因为用户目标是知识群、层级阅读与关系，而不是按对象类型管理数据库。

[Capacities Object Types](https://docs.capacities.io/reference/content-types)、[Capacities Queries](https://docs.capacities.io/reference/queries)

## 22.3 Capacities Daily Notes

Capacities 官方把 Daily Note 定义为低摩擦 catch-all，并在之后 Review 决定哪些内容转为其他对象。

产品推论：先保护输入、后形成结构是成立的；但本产品不新增 Today / Daily / Inbox Place。时间重要的记录可以保留时间属性，想法进入 Working，材料进入 Sources，真正高影响判断才打开 Knowledge Decision。

[Capacities Daily Notes](https://docs.capacities.io/reference/use-cases/daily-notes)

## 22.4 Anytype Sidebar

Anytype 官方 Sidebar 分为 channel actions、Pinned 与 Objects / types，并允许对象、queries 与 collections 使用不同 sidebar layouts。

产品推论：Pin 是进入便利，sidebar object catalog 是一种组织选择；本产品只让 Pin 改变快捷入口，不让 sidebar item、Pin 或布局影响知识权威、Home importance 或 Atlas salience。

[Anytype Sidebar](https://doc.anytype.io/anytype-docs/getting-started/customize-and-edit-the-sidebar)

## 22.5 Tana Interface 与 Library

Tana 官方界面使用 flat sidebar，分开 Today、Activity、Tasks、People、Library、spaces、Search 与 Account；Library 按 kind 浏览，Quick chat 和 create menu 从任何位置调用，窄屏 sidebar 变 overlay。

产品推论：稳定 destinations、global actions、Library 与 responsive navigation 是不同责任；同时，目标不同会合理地产生很多一级 destination。本产品范围更窄，因此拒绝 Today、Activity、Tasks、People、Agents 与 Review 等入口扩张，保持四 Places。

[Tana Interface](https://tana.inc/learn/features/interface)

## 22.6 W3C Multiple Ways、Focus Order 与 Breadcrumb

W3C 说明用户需要不止一种方式定位内容，逻辑 focus order 必须保持 meaning / operation；Breadcrumb 帮助理解层级位置，focus 与 selected state 也需要区分。

产品推论：Library hierarchy、Search、Atlas / List 与 Home entrances 可以共同定位同一内容，但必须保持同一 identity；PlaceNav focus 不触发 context change，DepthTrail、Active Place 与 Selection 分工。

[Multiple Ways](https://www.w3.org/WAI/WCAG22/Understanding/multiple-ways)、[Focus Order](https://www.w3.org/WAI/WCAG22/Understanding/focus-order.html)、[Breadcrumb Pattern](https://www.w3.org/WAI/ARIA/apg/patterns/breadcrumb/)

## 22.7 Apple Sidebars 与 Focus

Apple HIG 把 sidebar 定义为同级内容区域 / modes 的宽平导航，建议层级超过两层时使用额外 content list；focus 与 selection 在可能产生上下文切换时应分开。

产品推论：四 Places 适合稳定 sidebar / compact equivalent，Group / Topic hierarchy 不塞进全局 sidebar；keyboard focus Place item 不自动切换。

[Apple Sidebars](https://developer.apple.com/design/human-interface-guidelines/sidebars)、[Apple Focus and Selection](https://developer.apple.com/design/human-interface-guidelines/focus-and-selection)

## 22.8 研究不证明什么

以上官方文档证明多种导航、动态查询、capture staging、sidebar、multiple ways 与 focus semantics 是真实产品责任；它们不证明四 Places、Active Place inheritance、Home 顺序、Primary Destination matrix、Attention routing 或 Destination Receipt 是唯一正确方案。这些仍是待真实任务验证的产品决定。

---

# 23. 对相邻合同的同步要求

## 23.1 产品定义

- 冻结 Active Place / Surface Owner / Entry Context；
- Home 从 Ask-first 改为 knowledge / resume-first；
- 冻结普通启动 restore、New Window Home、Default Place map；
- 新增 Primary Destination、Attention routing 与 Destination Receipt；
- 冻结 scoped Lens ↔ global Place 对应关系。

## 23.2 交互架构

- App Shell 分开 Place current-context、owner、entry 与 selection；
- 新增 PlaceState、PlaceHandoff、DestinationReceipt、AttentionProjection 组件；
- PlaceNav focus 不切换；
- Settings / Trash 显示 origin Place；
- 多窗口与 responsive state 完整。

## 23.3 流程板

- PB-00 增加 launch precedence、Place switch、same-owner re-entry、Default Place deep link；
- PB-01 Library 顺序改为 Resume / Pins / exhaustive All Groups / secondary browse / optional notice / quiet actions；
- PB-05 增加 Destination Receipt；
- PB-06 / 07 增加 Primary Destination 与 attention handoff；
- PB-08 增加 Place State corrupted、partial handoff；
- 保持 81 Coverage ID 与唯一 Primary Board，不新增假覆盖。

## 23.4 产品语言

- P0 稳定地点使用首页、知识库、图谱、来源；
- `从图谱进入 / 返回这条关系 / 在来源中打开 / 需要你判断`表达 Entry 与 handoff；
- 禁止 Active Place、Surface Owner、Entry Context、Attention Signal、Primary Destination、Destination Receipt 作为默认术语；
- 禁止`AI 每日总结 / 待整理 23 / 未读变化 12 / 关系置信度`。

## 23.5 设计审查

- 不再把四个 Place Root screens 当完整导航；
- 必须画同一 owner 的 Home / Library / Atlas entry variants；
- 必须证明 Home 不以 Ask hero 开场；
- 必须证明 Primary Destination projection、receipt、defer 与多窗口 / responsive；
- 当前七屏继续留在 Archive，不因命名 Home / Map / Sources 获得通过。

---

# 24. 结论

四个 Places 真正成立的条件不是“侧边栏有四个按钮”，而是每个地点拥有唯一知识问题、同一对象跨地点仍只有一份真相、每个变化只有一个完整处理目的地、每次进入都可以解释并返回。

方向 3 + 2 也因此获得更准确的产品位置：方向 3 负责 owner Workspace 内的连续阅读与层级深入，方向 2 负责 Atlas / Map 中的关系语境；Active Place 与 Entry Context 让两种视觉语言可以在同一个 Group 上切换，而不复制内容、丢失位置或制造两套产品。

本轮最重要的修正是：

> **Home 不再以 Ask 开始。它先让用户回到自己的知识；AI 查询只是随处可用的能力。**
