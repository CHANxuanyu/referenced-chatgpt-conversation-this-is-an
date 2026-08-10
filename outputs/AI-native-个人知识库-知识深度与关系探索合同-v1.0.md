# AI-native 个人知识库

## 知识深度与关系探索合同 v1.0

> 日期：2026-08-06  
> 文档性质：产品定义补充；冻结 Overview → Evidence、关系语义、图谱可见性、探索路径与 Ask 联动，不是视觉稿、原型或研发排期  
> Canonical 产品定义：`AI-native-个人知识库-终局产品设计文档-v4.0.md`；本合同只证明深度与关系责任，不得反向改写 v4.0  
> v4.0 层级覆写：Scope L2 可以递归出现；每一级 Topic 都可用局部 Overview 建立方向感，但只缩小阅读范围，不产生新的语义对象类型、群级入口或正式 Relation endpoint  
> v4.0 策展覆写：Explore Recommendation 与 Query Route 属于本次会话；只有用户显式把既有 Saved Path 推荐到 Scope，才成为长期阅读策展，且不改变 Topic semantic order  
> v4.0 Knowledge Paper 覆写：L3 Knowledge 与 L4 Deep Detail 使用同一 identity / current Revision；Section、Inline Claim 与 Anchor 只提供正文深度和精确定位，不成为 Relation endpoint；需要独立关系时先显式 Promotion 为 Knowledge  
> v4.0 Relation 覆写：Relation 是拥有稳定 identity、完整自然语言陈述、端点角色、canonical direction、Applicability、Evidence、Revision 与 History 的知识陈述；inverse label、symmetric edge、derived path 与 Relation Bundle 都不创建第二份 truth  
> v4.0 跨群覆写：跨群 Knowledge Relation 只形成可走的 exit；Direct / Accepted Aggregated Group Relation 才进入 Atlas。Aggregated Relation 的 supporting path 变化触发 review_due，不静默改义  
> v4.0 Query 覆写：Answer Route 只展示真实结构、正式 Relation、Evidence connection 与显式标注的 runtime jump；同次使用不生成 Relation，无法形成路径时使用 Used Knowledge List  
> v4.0 探索连续性覆写：DepthTrail、ReturnStack、ExplorationTrail、SavedPath 与 PathProgress / ResumePoint 是五种不同状态；SavedPath 不再包含 `last_position`，详情以`AI-native-个人知识库-探索路径、回返与继续合同-v1.0.md`为准  
> 2026-08-08 Topic Opening 冻结：Scope L2 的 Open 进入同一 Topic Reading 顶部的局部开场；Expand / Inspect 不改变 Scope，Knowledge / Anchor deep link 直达，Bare / Compact / Editorial 只改变真实内容密度  
> 2026-08-08 Relation Presentation 冻结：R0–R3 只表示关系半径；Quiet / Peek / Companion / Explore 独立表示注意力强度。普通打开为 Quiet，Companion 只跟随 explicit Open，Explore 必须由用户显式进入  
> 2026-08-09 Scale Invariance 冻结：F1 / F10 / F100 / F10K 使用同一范围、深度与关系语法；R3 超出可理解预算时进入 Anchor Required，以 Scope Summary + List Equivalent 保留全局语境，再围绕明确焦点展开，不创建自动 Group regions、核心 Top N 或第二套“大库图谱”  
> 2026-08-10 Relation Lifecycle 冻结：Candidate 与正式 Relation 分离；Relation 使用 assertion disposition、change condition、Evidence / Challenge、temporal qualifiers 与 lifecycle 正交表达；Evidence 更新不制造语义 Revision；End / Supersede / Retract / Archive 分开；Split / Merge 后不静默复制或 retarget 边。完整合同见`AI-native-个人知识库-关系陈述生命周期与网络可信性合同-v1.0.md`  
> 2026-08-10 Group Relation Aggregation 冻结：cross-group exit、Aggregation Signal、Group RelationCandidate 与 maintained Group Relation 分层；多个 paths 只有通过 Effective Support Unit collapse、Boundary coverage、type-specific policy、CounterSignal 与 removal test 才有 Candidate 资格。完整合同见`AI-native-个人知识库-群级关系聚合门槛与支撑充分性合同-v1.0.md`  
> 2026-08-10 Group Relation Type Registry 冻结：Group-level 使用十一种 formal types；`partially_overlaps_with`取代旧 Group overlap，shared core 成为 derived Observation，并新增 `complements / challenges`。完整合同见`AI-native-个人知识库-群级关系类型注册表与语义互斥合同-v1.0.md`  
> 2026-08-10 Knowledge Relation Type Registry 冻结：Knowledge-level 使用五个 families、二十五种 formal types；`prevents`取代含糊 `blocks`，`partially_overlaps_with`取代旧 Knowledge overlap，新增 `implements`；`supersedes / retracts / reopens / uncertain_about`移出 ordinary Relation。完整合同见`AI-native-个人知识库-知识关系类型注册表与跨层语义合同-v1.0.md`  
> 历史深层模型：`AI-native-个人知识库-产品定义-v3.0.md`  
> 核心体验：`AI-native-个人知识库-核心体验与知识群生命周期-v1.0.md`  
> 交互基线：`AI-native-个人知识库-交互架构与设计系统-v1.0.md`
> 知识群边界与跨群架构：`AI-native-个人知识库-知识群边界与跨群架构合同-v1.0.md`
> 知识节点粒度与内容组成：`AI-native-个人知识库-知识节点粒度与内容组成合同-v1.0.md`
> Overview 形成、编辑与更新：`AI-native-个人知识库-Overview形成编辑与更新合同-v1.0.md`
> AI 查询与知识回答：`AI-native-个人知识库-AI查询与知识回答合同-v1.0.md`
> 来源、证据与可追溯性：`AI-native-个人知识库-来源证据与可追溯性合同-v1.0.md`
> 关系陈述生命周期与网络可信性：`AI-native-个人知识库-关系陈述生命周期与网络可信性合同-v1.0.md`
> 产品对象层级与身份治理：`AI-native-个人知识库-产品对象层级与身份治理合同-v1.0.md`

---

# 0. 执行判断

用户最初要求的两个核心体验是：

1. 知识能从 Overview 逐层深入到细节和来源；
2. 知识群之间有可见关系，用户可以在网络里探索，也可以用 AI 查询。

现有规格已经定义 L0–L5、Relation、Atlas、Local Graph 与 Knowledge Route，但仍存在三个会让产品实际偏离的问题。

## 0.1 缺口一：L0–L5 混合了三种不同变化

当前层级同时表达：

- 知识范围从 Space 缩到 Group、Topic、Node；
- 同一知识从简短定位展开为完整解释；
- 关系图从全局变成局部。

如果不把这三种变化分开，产品会把“看得更细”“进入子对象”和“展开更多邻居”都叫 Zoom，最终只剩一种放大缩小动画，没有稳定信息语义。

## 0.2 缺口二：Relation 的真值和显示逻辑尚未彻底分离

当前模型把 Explicit、Inferred、Suggested、Rejected 并列，但它们不在同一维度：

- Explicit / Inferred 是关系如何形成；
- Suggested / Accepted / Rejected 是关系是否进入正式知识；
- lifecycle / epistemic / freshness 是关系现在的状态；
- “当前是否显示”只是界面决策。

若继续混用，一条 AI 推断但经用户接受的关系无法被准确表达，图上的虚线也会同时承担“模型推断”“尚未确认”“低证据”三个不同含义。

## 0.3 缺口三：AI Knowledge Route 可能制造伪关系

检索会因为关键词、向量相似、共同来源或当前问题，把两个对象一起使用。这不意味着二者已经拥有正式 Relation。

如果回答图把所有检索跳转都画成知识关系，用户会误以为知识库已经知道“为什么相连”；一次 AI 回答会悄悄污染长期知识网络。

## 0.4 本文件冻结的二十五项决定

1. L0–L5 继续保留，但被重新解释为**范围阶梯**，不是一个万能 Zoom；
2. 同一范围内部使用 Orientation → Synthesis → Explanation → Evidence 的**阅读深度**；
3. Relation Lens 使用 Direct → Path → Atlas 的**关系半径**，不与阅读深度绑定；
4. L3 Knowledge Node 必须有稳定阅读骨架，并按 Node 类型提供不同内容合同；
5. “结构位置、来源引用、普通链接、正式关系、检索跳转”是五类不同连接；
6. 正式 Relation 必须同时记录形成依据、提案状态、知识状态与证据；
7. `related_to` 不再承担默认万能正式关系；无法命名语义的连接只保留为普通链接或候选；
8. 图谱默认只呈现当前任务最重要的少量关系，并提供 List Equivalent；
9. AI Route 必须逐步标注正式关系、层级跳转、证据引用和本次检索跳转；
10. Search、Ask、Explore 是三个承诺不同但可连续切换的入口，系统只建议切换，不静默改模式。
11. Overview D0–D1 使用一个 content tree；Overview Anchor 通过 Support Map 回到知识对象，不把 Overview 自身当作 Evidence；
12. AI 生成的 Overview-like Answer 仍是 Query Result；只有显式 Semantic Diff 或 Claim Promotion 才能改变长期知识。
13. Query Route 属于具体 Query Run；Requested / Effective / Used Context、Claim Support 与 Coverage 共同决定“本次为什么使用这些对象”，Query overlay 与 Saved Answer 都不自动进入长期 Relation truth。
14. DepthTrail 只表达结构位置，Back / Forward 由独立 ReturnStack 负责；Up 与 Back 不共享语义。
15. Hover、Focus、Inspect、Expand、Filter 与 Viewport 不写 ExplorationTrail；有意义的 Open 才写入。
16. Back 后 Open 新目标形成轻量分支；用户可以恢复“刚才的另一条分支”，但日常表面不显示完整路径树。
17. SavedPath 是用户主动筛选、带目的的长期路线，不是原始访问流水；manual step 不制造 Relation。
18. SavedPathRevision 保存 ordered steps 与 revision basis；当前 step、完成状态与 scroll 属于 PathProgress。
19. Continue / Reset Progress 不修改 SavedPath identity 或 Revision；Re-evaluate 只提出 successor，不覆盖原路线。
20. QueryRoute、ExplorationTrail 与 SavedPath 的转换都必须由用户显式触发，并经过真实 connector 检查。
21. Relation Presentation 与 Relation Radius 正交：普通阅读 Quiet，选择一条关系进入 Peek，显式查看进入唯一 Companion，显式地图探索才进入 Explore；hover、Focus、AI proposal 与普通 Open 不自动升级。
22. F1 / F10 / F100 / F10K 只是验收夹具；数量变化不改变 Scope Ladder、Reading Depth、Relation Radius、Open 或 Return 语义。
23. R3 超出视图预算时进入 Anchor Required；先给出 effective scope、隐藏数量、过滤原因与 List Equivalent，再要求 Group、Search、Facet、Saved View 或 Path 焦点。
24. 大规模 Network 不按 degree、recency、AI relevance 或 embedding cluster 截出“核心知识群”，也不把自动 cluster 固化为 Group region、Boundary 或 Relation。
25. Anchor 确定后，以 selected Group + 约 3–7 个 accepted neighbours 为初始表达；更多内容按 relation family、direction、standing 或下一跳显式展开，unconnected Groups 始终合法。

---

# 1. “丰富层级”的产品定义

## 1.1 层级不是文件夹深度

丰富层级不是允许用户无限创建子页面。它意味着用户在任何时刻都能：

- 先理解当前范围；
- 看见它由哪些部分构成；
- 选择一个可独立理解的知识；
- 展开机制、论证、条件、例子和限制；
- 最后回到具体来源和上下文；
- 返回时仍知道自己从哪里来。

## 1.2 三个独立维度

### A. Scope Level / 知识范围

```text
L0 Space / Atlas
  → L1 Knowledge Group
  → L2 Topic
  → L3 Knowledge Node
```

范围阶梯回答：“我正在看哪一部分知识？”

### B. Reading Depth / 阅读深度

```text
D0 Orientation / 最短定位
  → D1 Synthesis / 当前整体理解
  → D2 Explanation / 机制、论证、条件、例子与限制
  → D3 Evidence / 原始依据、版本与上下文
```

阅读深度回答：“我需要理解到多细？”

### C. Relation Radius / 关系半径

```text
R0 Hidden or List / 不主动显示图
  → R1 Direct / 当前对象的一跳关系
  → R2 Path / 一条有解释的多步路径
  → R3 Atlas / 群级整体关系地形
```

关系半径回答：“我需要看多远的连接？”

## 1.3 三维可以独立组合

例如：

- 用户可在 L1 Group 看 D2 深度的完整 Synthesis，但 Relation Lens 只保持 R1；
- 用户可在 L3 Node 只读 D0 定义，同时打开 R2 跨群路径；
- Ask 可以从 L0 发起，直接返回 L3 Nodes 和 D3 Evidence，同时 Atlas 以 R2 高亮使用路径；
- Evidence Reader 处于 D3，但不需要把关系半径扩大到全局。

这避免所有屏幕被固定成“左树、中正文、右图谱”三栏，也避免用户为了看证据被迫进入一个完全不同的应用模式。

## 1.4 对现有 L0–L5 的兼容解释

现有文档的 L0–L5 对用户仍然成立：

| 现有层级 | 新解释 | 是否需要独立正式对象 |
|---|---|---|
| L0 Atlas | Scope L0 + Reading D0 + Relation R3 | Space / Group 已存在 |
| L1 Group Overview | Scope L1 + D0–D1 | Group + Overview |
| L2 Topic Structure | Scope L2 + D0–D1 | Topic + Overview |
| L3 Knowledge Node | Scope L3 + D0–D1 | Node |
| L4 Deep Detail | 当前 Node 的 D2 阅读表达 | 不新增对象 |
| L5 Evidence | 当前知识的 D3 核验表达 | Evidence Fragment + Source |

L4 不是“每个 Node 必须再有一个 Detail 页面”；L5 也不是“每条知识必须有外部证据”。它们是按需进入的表达深度。

---

# 2. Scope Ladder / 范围阶梯合同

## 2.1 L0 Space / Atlas

必须回答：

- 我拥有哪些主要知识群；
- 每个群的边界是什么；
- 哪些群之间存在值得理解的正式关系；
- 当前查询或探索位于哪里。

不能回答：

- 所有知识节点如何互连；
- 每个群有多少对象；
- 用户今天完成了多少整理；
- embedding 相似形成了多少簇。

## 2.2 L1 Knowledge Group

必须回答：

- 这是什么知识范围，包含与不包含什么；
- 当前主要理解是什么；
- 由哪些主题构成；
- 最关键的内部与跨群关系是什么；
- 哪里未知、变化或覆盖不足；
- 从哪里继续。

Group Overview 不是 Group 中所有卡片的摘要拼接，也不是项目仪表盘。

## 2.3 L2 Topic

L2 可在 `Topic > Subtopic > …` 中递归出现。每一级必须回答：

- 当前分支在父级 Group 中承担什么作用；
- 它有哪些子主题和代表知识；
- 哪些知识跨越相邻 Topic；
- 当前分支的知识缺口是什么；
- 深入哪个 Node 最能建立理解。

Topic 不拥有 canonical Node 正文。它拥有局部 Overview、结构和 Placements；局部关系来自后代 Nodes 的正式 Relations 与结构出口投影，不形成 Topic Relation truth。

Scope L2 的进入合同：

- Expand 只显露结构，不改变 Scope Level；
- Inspect 只显示局部 Preview，不写 History；
- Open Topic 才把 Scope 切到当前 L2，并在同一 Reading surface 顶部先给局部 Orientation；
- Open Knowledge / Anchor 直接进入 L3 / 当前 Reading Depth，不插入 L2 中转页；
- Up 回到父 Scope，Back 回 caller，Resume 回 exact scene。

Topic opening 默认是 Compact；空、Source-only 或单一分支时诚实退化为 Bare；只有存在 accepted local synthesis 时扩展为 Editorial。默认 Structure Projection 只显示 direct children，descendant rollup 按需展开，避免每一级重复同一批 Knowledge 与 Relations。

## 2.4 L3 Knowledge Node

必须回答：

- 这条知识是什么；
- 它在当前语境为什么重要；
- 当前接受、争议、时效与来源状态如何影响使用；
- 它通过哪些正式关系与其他知识相连；
- 深入解释和证据在哪里；
- 它还出现在哪些 Group / Topic 语境。

## 2.5 直接跳转是合法的

用户不必每次逐级点击 L0 → L1 → L2 → L3：

- Search 可以直接打开 L3，但 DepthTrail 必须恢复当前 Placement；
- Ask 可以从 L1 直接聚焦一个 L3 Node，同时显示使用路径；
- 来源引用可以从 L3 直接进入 D3 Evidence；
- Back 返回实际访问历史，Up 返回语义父级。

“丰富层级”提供方向感，不制造强制点击税。

---

# 3. Overview 的阅读深度合同

## 3.1 D0 Orientation

Orientation 是进入任一 Scope 后最短、可独立理解的定位，不是截断的长摘要。

它应回答：

- 这是什么；
- 为什么值得进入；
- 当前最重要的边界或状态是什么。

默认只需要一至三句话。若系统无法可靠形成，应显示边界、用户原始描述和覆盖不足，而不是用模型常识补齐。

## 3.2 D1 Synthesis

Synthesis 是当前范围内最好的整体理解，包括：

- 核心概念或主张；
- 主要结构；
- 关键关系；
- 重要条件、分歧和未知；
- 代表性来源覆盖；
- 继续阅读入口。

它不是独立生成的文章。Overview 中每个重要段落通过 Support Map 回到构成它的 Node Anchors、Relations、Structure Projection、Boundary 或 Historical Overview；Evidence 仍连接到 Node / Relation，而不是停在 Overview。

## 3.3 D2 Explanation

Explanation 只在用户继续深入时展开：

- Why / Mechanism；
- How / Steps；
- When / Applicability；
- Examples；
- Counterexamples；
- Limitations；
- Comparison；
- Open questions。

不同 Node 类型不需要强行填满所有区块。空区块不显示，缺少但重要的区块可作为知识缺口。

## 3.4 D3 Evidence

Evidence 必须同时呈现：

- 来源身份和版本；
- exact locator；
- 引用片段；
- 足够的前后文；
- 原文、翻译、OCR、转写和 AI 解释的区别；
- Material Origin、Derivation Distance、Extraction Fidelity 与 Verification State；
- 由 Evidence Binding 说明它支持、反驳、限定、定义或举例哪条具体知识；
- 当前位置是否仍可核验。

用户原创的观察、综合和原则可以没有外部 Source。此时 D3 显示作者、形成方式、历史和用户说明，而不是伪造 Evidence。

## 3.5 深度展开必须可逆

- 展开 D2 不改变 Node identity；
- 打开 D3 不清空正文滚动位置；
- 返回时恢复原段落、选区和 Relation Lens；
- 用户可以固定某个 Scope 的默认阅读深度；
- AI 回答点击引用后，关闭 Evidence 返回原 Answer claim，而不只返回 Node 顶部。

## 3.6 Overview Anchor 的纵向核验路径

Overview 中的定位句、主题结构、综合判断和状态说明不共享同一种“依据”：

```text
Overview Anchor
  → boundary statement
  → structure projection rule + matched Topics / Placements
  → Node Anchor / Relation
  → Evidence Fragment
  → Source locator
```

- Editorial prose 可以由用户直接写下，但需要核验的 Claim 应建立 Support Map；
- Projection 先显示查询规则与当前匹配对象，再允许进入其 Nodes / Relations；
- Historical statement 可以指向旧 Overview revision，但若继续用于当前判断，仍需回到当时的 Nodes / Evidence；
- Ask Route 不能以“Overview 写过”结束依据链；
- 一段 Overview 文字需要成为正式 Evidence target、Relation endpoint 或跨群复用对象时，必须先保存为独立 Node。

---

# 4. Knowledge Node 的阅读骨架

## 4.1 每个 Node 的稳定六段

不是每个 Node 都要显示六张卡，但信息语义保持稳定：

1. **Identity**：名称、类型、当前语境；
2. **Orientation**：一句定义或当前结论；
3. **Core Understanding**：最重要的解释；
4. **Conditions & Limits**：适用条件、例外、争议与新鲜度；
5. **Connections**：关键正式关系、其他出现位置与探索入口；
6. **Evidence & History**：来源、形成方式、版本与变化。

默认阅读只展开 1–3。4 在影响判断时提高优先级，5 按当前任务显示，6 一跳可达。

## 4.2 Concept / 概念

| 层 | 内容 |
|---|---|
| Orientation | 一句定义与边界 |
| Core | 组成、机制、与相邻概念区别 |
| Deep | 例子、反例、常见误解、不同定义 |
| Evidence | 定义来源、研究或用户综合依据 |

Concept 不应退化为词典释义；它需要说明“在当前知识群中为什么重要”。

## 4.3 Claim / 主张

| 层 | 内容 |
|---|---|
| Orientation | 可被判断真假的完整陈述 |
| Core | 理由与当前结论 |
| Conditions | Applicability、假设、例外 |
| Connections | supports / contradicts / qualifies / derived_from |
| Evidence | 支持、挑战和证据不足部分 |

一个可独立被反驳或更新的陈述应拆成独立 Claim，而不是藏在长篇 Concept 正文中。

## 4.4 Method / 方法

| 层 | 内容 |
|---|---|
| Orientation | 解决什么问题 |
| Core | 前提、步骤与预期输出 |
| Conditions | 适用场景、不适用场景、资源要求 |
| Deep | 失败模式、变体、例子与对照 |
| Evidence | 方法来源、实践结果或用户经验 |

## 4.5 Decision / 决策

| 层 | 内容 |
|---|---|
| Orientation | 选择了什么 |
| Context | 当时问题、约束和时间 |
| Rationale | 为什么这样选择，放弃了什么 |
| Consequence | 影响哪些对象、规则和后续工作 |
| Evolution | current successor、独立 `refines` Relation、Decision / Question lifecycle 与 disposition history |
| Evidence | 当时依据与 Knowledge Snapshot |

Decision 的当前状态和历史状态都必须可读；“被替代”不等于删除。

## 4.6 Question / 问题

| 层 | 内容 |
|---|---|
| Orientation | 清楚的问题陈述 |
| Importance | 为什么值得回答 |
| Current Answers | 当前候选答案与分支 |
| Unknown | 缺什么知识或证据 |
| Path | 已探索路线与下一步 |
| History | 问题如何被重写、部分回答或关闭 |

## 4.7 Principle / 原则

| 层 | 内容 |
|---|---|
| Orientation | 约束行为的一句规则 |
| Rationale | 为什么存在 |
| Applicability | 适用于哪些范围，何时需要例外 |
| Examples | 正确应用与违反案例 |
| Relations | supports / qualifies / contradicts / applies_to / implements 等精确语义；不得使用未注册的泛化动词 |
| History | 原则如何形成和被修订 |

## 4.8 Entity、Event、Example

- Entity 强调身份、属性、时间线、关系和来源；
- Event 强调发生时间、参与者、前因后果和证据；
- Example 必须明确“它例证了什么”和“哪里不能类推”。

它们共享六段骨架，但不强迫使用 Concept 或 Claim 的正文结构。

---

# 5. 五类连接，只有一种是正式 Relation

## 5.1 Structural Connection / 结构连接

来自 Knowledge Space→Group、Topic 的直接 parent 与 Placement：

- 回答“它在哪里”；
- Group membership 当且仅当存在 active Placement，由此推导而不另存；
- Topic children、ancestors 与 breadcrumb 由唯一直接父级推导；
- 由结构对象直接产生；
- 不重复存成 `contains` / `belongs_to_group` Relation；
- 可在地图中显示，但视觉语法与正式语义关系不同。

## 5.2 Evidence Connection / 证据连接

来自 Node / Relation 到 Evidence Fragment：

- 回答“依据是什么”；
- 由 Evidence Binding 保存对具体 target / anchor 的 Support Role；
- Fragment 自身不拥有全局 supports / challenges；
- 不与 supports / contradicts Relation 混为一条普通边；
- 进入 Source Reader 时可核验。

## 5.3 Reference Link / 普通引用

用户在正文中引用另一个知识，但没有说明确切语义：

- 形成 backlink；
- 可以支持导航和候选关系发现；
- 默认不进入 Atlas 正式关系；
- 用户或 AI 可以建议升级为 typed Relation。

## 5.4 Semantic Relation / 正式关系

正式 Relation 是一条可被解释、修订、争议和核验的知识陈述：

> A 在指定条件下，以某种明确方式与 B 相连。

它必须拥有类型、方向、适用范围、形成依据和状态。

正式端点只允许 Node↔Node 或 Group↔Group。Topic↔Topic 使用结构或 Saved Path，Topic↔Node 使用 Placement，Node / Relation→Evidence 使用 Evidence Connection；这些连接不因画成线就成为 Semantic Relation。

## 5.5 Retrieval Jump / 本次检索跳转

Ask 或 Search 因关键词、向量相似、共同来源或问题需要，把两个对象同时取回：

- 只属于本次 Query Route；
- 文字表达为“本次问题中一起使用”或具体检索原因；
- 不进入长期图谱；
- 用户补全 endpoints、类型、方向、statement、Applicability 与依据并提交后，才形成 maintained Relation；若只保存系统发现，则形成 RelationCandidate。

## 5.6 为什么必须分开

如果五类连接共用同一种实线：

- Topic 结构会被误解为知识主张；
- 引用会被误解为强关系；
- 检索相似会被误解为长期知识；
- Evidence 会被误解为普通邻居；
- 图谱无法解释“为什么这条线存在”。

---

# 6. Relation 数据模型修订

## 6.1 修订后的模型

```text
Relation
  identity
    relation_id
    current_revision_ref

  continuity
    assertion_disposition:
      maintained | ended | superseded | retracted
    successor_relation_refs[]

  maintenance
    change_condition:
      no_material_change | changes_available | review_due | transition_in_progress
    open_review_case_refs[]
    open_challenge_refs[]

  lifecycle
    lifecycle_state: current | archived | trash

  presentation
    user_pinned
    visibility_scopes[]
    derived_salience

  lineage
    created_by
    formation_basis
    adopted_by?
    created_at
    revision_history

RelationRevision
  relation_revision_id
  canonical_from_ref / canonical_to_ref
  from_role / to_role
  from_anchor_ref? / to_anchor_ref?
  canonical_relation_type
  relation_statement
  inverse_reading_label?
  applicability?
  qualifiers[]
  valid_from? / valid_to?
  exceptions_or_limits[]
  why_it_matters

RelationCandidate
  candidate_id
  proposed_statement / endpoints / type / applicability
  why_suggested
  formation_basis
  candidate_state: open | adopted | dismissed | expired

EvidenceBinding
  target_relation_revision_ref
  fragment_ref
  support_role: supports | challenges | qualifies | defines | exemplifies | provides_context
```

## 6.2 五个维度不能合并

例子：

```text
formation_basis = system_inferred
adoption_event = user_accepted
assertion_disposition = maintained
change_condition = review_due
lifecycle_state = current
evidence_summary = no_external_evidence + 1 open challenge
```

含义是：这条关系最初由系统建议，经用户采用后才物化为正式 Relation；它当前仍被采纳，但有变化需要检查、没有外部支持且存在一个未解决挑战。Candidate 是否被采用、陈述是否当前、是否需复核、依据是什么和对象是否归档，不能靠一条虚线或一个状态 enum 同时表达。

## 6.3 `from_ref` 取代含糊的 `source_ref`

原模型中的 `source_ref` 容易同时被理解为关系起点和证据来源。修订后：

- `from_ref` / `to_ref` 表示关系端点；
- `EvidenceBinding.target_relation_revision_ref` 表示支撑、挑战或限定哪一个具体 Revision；
- `created_by` / `formation_basis` 表示关系如何形成。

## 6.4 显示优先级不是知识状态

`derived_salience` 只回答“当前任务中是否值得显示”，可以由以下信号计算：

- 用户固定；
- 当前 Selection；
- 当前 Query；
- 是否是跨群桥接；
- 是否解释关键 Claim；
- 是否是受影响路径；
- 当前 Scope 是否需要。

它不能改变 relation type、assertion disposition、change condition、Evidence / Challenge 或 Candidate adoption，也不显示为“关系置信度 83%”。

## 6.5 Relation identity 与 Revision 边界

Relation identity 回答“这是哪一条长期关系陈述”；Revision 回答“它在当前版本中怎样表达”。以下变化通常形成同一 Relation 的新 Revision：

- 文案澄清但核心主张不变；
- 增补 why_it_matters 或修订 endpoint Anchor 的语义参与位置；
- 收窄 Applicability 或补充 exception；
- 修复 endpoint redirect，但语义角色不变。

新增、替换或重新定位 Evidence 默认只创建 / 更新 Binding；它不改变 statement 意义，因此不创建 RelationRevision。只有 Evidence 促使用户改写方向、类型、statement 或 qualifier 时，改写结果才进入新 Revision。

以下变化默认是新 Relation，并根据语义连续性 supersede 或并列旧 Relation：

- canonical type 改变到另一个语义家族；
- from / to 的角色发生反转，而不是从另一端阅读 inverse label；
- Applicability 改变到一条可以独立成立或冲突的主张；
- 原关系被确认只是另一条关系的 supporting path；
- 用户希望同时保留两个不同“为什么相连”。

只有新 Relation 承担旧 Relation 的当前解释角色时，旧 Relation 才进入 superseded 并指向 successor；过去范围正确但已经结束使用 ended；没有 successor 且不再采纳使用 retracted；只想排除当前默认使用则 Archive。

## 6.6 canonical direction、inverse 与 symmetric

有方向类型只保存一份 canonical assertion。类型定义同时提供：

```text
canonical_label
inverse_reading_label
from_role
to_role
symmetry: directed | symmetric
```

`A provides_foundation_for B` 从 B 端读作 `B builds_on A`，仍解析到同一个 `relation_id`。Knowledge-level `similar_to / contrasts_with / overlaps_with` 与 Group-level `partially_overlaps_with / complements / contrasts_with` 等对称关系按 endpoint identity 规范化，只保存一条；交换端点不创建镜像记录。

同一 endpoint pair 可以存在多条 Relations，但 type、Applicability 或 relation statement 必须表达真正不同的主张。Presentation Bundle 只折叠显示，不合并 identities。

## 6.7 类型约束与 derived paths

每个 RelationTypeDefinition 至少声明：

- allowed endpoint kinds；
- directed / symmetric；
- canonical / inverse labels；
- self 是否允许，默认否；
- cycle 是否允许；
- transitivity 是否允许，默认否；
- mutually exclusive / conflicting types；
- 必要 qualifier，例如 `similar_to` 的比较维度、`contradicts` 的同一 Applicability 检查。

即使类型允许 transitive query，也只生成 `derived_path`，不创建 maintained Relation。`A supports B` + `B supports C`、`A similar_to B` + `B similar_to C` 都不推出新的直接关系。UI 必须把 direct assertion 与 derived path 分开。

## 6.8 Endpoint Anchor 只解释局部参与

`from_anchor_ref / to_anchor_ref` 说明长 Node 的哪一部分参与 Relation，不改变 endpoint identity。它们遵守 resolved / redirected / ambiguous / orphaned：

- 唯一可重定位时更新 locator 并保留历史；
- ambiguous / orphaned 时 Relation 进入 review_due；
- 不把相似段落静默当成新 endpoint；
- 局部主张需要独立 Relation neighborhood、Applicability、Evidence 或状态时，先 Promotion 为 Node。

## 6.9 用户直接创建与 RelationCandidate

- 用户明确选择两个 endpoints、校正完整 relation statement 并本地保存后，Relation 默认成为 maintained current truth；
- 用户可以在没有外部 Evidence 时表达自己的理解，formation_basis = user_asserted，界面说明`你的理解；暂无外部依据`；
- AI、来源抽取、相似度、共同引用、空间邻近或 Query 共现只能形成独立 RelationCandidate；
- 直接创建与 Candidate 采用都必须通过完整句子回读方向和限定；
- Candidate 被拒绝只保留 suppression memory，不创建 rejected Relation；
- 撤销 Relation 不删除 endpoints、Evidence、Path 或历史 Answer。

---

# 7. Knowledge Relation 类型体系收敛

本节是阅读摘要；完整 definition、required qualifiers、相邻类型互斥、迁移与验收，以`AI-native-个人知识库-知识关系类型注册表与跨层语义合同-v1.0.md`为准。Internal key 使用 `knowledge.*` namespace；以下省略 namespace 只为阅读简洁。

## 7.1 Classification & Composition / 分类与组成

- `subtype_of`：Concept → Concept；inverse `supertype_of`只读；
- `instance_of`：Entity / Event / Example → Concept；
- `exemplifies`：具体对象展示 Principle / Method / Claim 的某一方面；
- `defines`：Definition-like Knowledge → Concept / term；inverse `defined_by`只读；
- `component_of`：component → whole；inverse `has_component`只读。

这五种类型分别表达分类、实例、例证、定义与语义组成。Topic hierarchy、Block containment 与 Placement 永远保留为结构连接。

## 7.2 Explanation & Causal Structure / 解释与因果结构

- `explains`；
- `causes`；
- `contributes_to`；
- `enables`；
- `prevents`；
- `depends_on`；
- `provides_foundation_for`；inverse `builds_on`只读。

`causes`要求机制、时序与适用条件；`contributes_to`明确非充分；`enables`只承诺使其成为可能；`prevents`表达主动阻止；`depends_on`从 dependent 指向 prerequisite。旧 `blocks` 必须逐条迁移为 `prevents`、反向 `depends_on` 或其他对象。

## 7.3 Argument & Inference / 论证与推导

- `supports`；
- `contradicts`；
- `qualifies`；
- `assumes`；
- `derived_from`。

`knowledge.supports`只连接 premise / reason Knowledge → Claim / Decision Knowledge；SourceFragment 支持某陈述是 EvidenceBinding，本次回答的依据是 ClaimSupport。`contradicts`前必须比较 Applicability；`derived_from`表达知识推导，不替代 Source provenance 或 KnowledgeRevision。

## 7.4 Comparison & Application / 比较与应用

- `contrasts_with`；
- `similar_to`；
- `partially_overlaps_with`；
- `applies_to`；
- `implements`。

`similar_to`要求相似维度、依据与重要差异；`partially_overlaps_with`要求共享语义与双方各自独立的 material contribution；same / near duplicate 进入 identity resolution。`applies_to`只表达潜在适用，`implements`才表达真实采用或落实。Embedding、共现与共同来源只能解释 Candidate discovery。

## 7.5 Time & Evolution / 时间与演化

- `precedes`；
- `refines`；
- `evolved_from`。

`precedes`不推出因果；`refines`连接两个都需保留的 Knowledge identities，同一 identity 的改字与补证据只形成 Revision；`evolved_from`要求思想、模型或方法的 transformation lineage。

## 7.6 从 ordinary Relation 移出的对象

- `supersedes` → KnowledgeIdentityTransition / successor standing；
- `retracts` → Relation 或 Knowledge disposition event；
- `reopens` → QuestionLifecycleEvent；
- `uncertain_about` → Question Knowledge + QuestionTargetReference；
- `related_to` → ReferenceLink、manual Path step 或 ambiguous RelationCandidate；
- `overlaps_with` → 逐条迁移为 `partially_overlaps_with`、identity resolution、taxonomy / composition 或无正式关系。

这些对象仍可导航、回读和进入 History，但不会出现在 ordinary Knowledge Relation filter、Local Graph current edge 或 Answer 的 formal Relation truth 中。

---

# 8. Group Relation / 群关系的产品合同

## 8.1 群关系不是共享标签

一个正式 Group Relation 应表达：

> 为什么理解 Group A 会改变、支持、限定或应用于 Group B。

它不是“两个群都有 AI 标签”。

Group Relation 只连接两个 Groups。Formal registry 包含 `scope_within`、`partially_overlaps_with`、`provides_foundation_for`、`applies_to`、`provides_method_for`、`complements`、`contrasts_with`、`challenges`、`constrains`、advanced `influences`与`evolved_from`。`scope_within`不产生 Subgroup、存储所有权或级联删除；`builds_on`只是 `provides_foundation_for` 的 inverse reading，不另存镜像关系。Shared core 是 derived Observation，不是第十二种 Relation。

## 8.2 群关系必须拥有解释包

```text
GroupRelationExplanation
  relation_statement
  relation_type
  why_it_matters
  supporting_paths[]
  shared_canonical_nodes[]
  evidence_refs[]
  exceptions_or_limits[]
  last_reviewed_at
```

Atlas 只显示一句关系陈述；选择后 Relation Inspector 展开 supporting paths 和证据。

## 8.3 聚合关系与人工关系

- 直接断言只来自用户明确选择 endpoints、完成 statement / type / direction / Applicability 并亲自提交；可靠来源陈述与带类型导入仍先形成 Candidate；
- 单条跨群 Node Relation、共享 Node、Gateway、Saved Path、Reference 或 Query Route 只形成 cross-group exit / supporting path，不足以生成 Group Relation；
- 多个正式跨群 paths 只触发 Aggregation Signal；系统必须先折叠 assertion / content / provenance / traversal 重复，再通过九道资格门；
- 两个 Effective Support Units 只是系统主动建议的最低输入，不是充分条件；支撑还必须触及双方 Boundary、支持同一 typed statement、方向与 Applicability 一致、检查 CounterSignals，并执行 strongest-unit removal；
- 合法 coverage 为 bilateral-core、anchor-and-spread 或写入 Applicability 的 named-subscope；fringe-only 只保留 exits；
- relation type 不共用一个聚合器：`scope_within` 不可聚合，`evolved_from` 需要 direct / indirect lineage，`provides_method_for` 需要实际应用，`complements`需要非冗余贡献，`contrasts_with` 需要共同维度，`challenges`需要明确被削弱对象，因果 / 约束关系不能由共现或相似度推出；
- 聚合建议必须列出 statement、Boundary coverage、Effective Support Units、collapsed / excluded signals、CounterSignals 与 removal result；
- 聚合结果接受前保持 RelationCandidate，不能进入默认 Atlas；
- 一个共享 Node 或单次跳转不足以形成聚合关系；
- 底层 path 变化时，已采用群关系创建 Support Set Revision 并进入 review_due，而不是自动消失或退回 Candidate；
- 任何资格门失败都不能用更多 paths、degree、confidence 或 edge weight 抵消；真实 exits 仍保留。

## 8.4 群关系的可见层级

- Atlas resting state：只显示固定、基础性和高解释价值关系；
- 选中一个 Group：展开其直接正式关系；
- Ask 高亮：显示本次问题使用的 Group paths；
- 候选关系：进入单独的 Suggested layer，不污染默认 Atlas；
- 关系失效或争议：仍可查看，但说明影响。

## 8.5 同一 Group pair 的多关系

同一对 Groups 可以同时存在多个独立 relation statements。Atlas 使用 Relation Bundle 收敛线条，但：

- 每条 Relation 保留独立 identity、direction / inverse、Applicability、Evidence、state 与 history；
- 默认只展示一条 pinned 或当前任务最重要的 accepted statement，并说明还有几条；
- Inspect 展开全部 members 与 supporting paths；
- Bundle 不产生新的 epistemic truth，也不能把 members 合并为 `related_to`；
- 某一 member review_due / superseded 不改变其他 members。

---

# 9. 图谱的可见性预算

## 9.1 为什么需要预算

“所有关系都可见”不等于“用户能理解关系”。图谱每增加一条边，都会增加标签冲突、交叉线和视觉选择成本。预算是默认表达约束，不是数据容量上限。

## 9.2 Atlas / R3

设计起始预算：

- effective scope 在预算内时，同一视口优先显示 6–20 个群；
- resting state 只保留少量固定或基础关系；
- 选中 Group 后重点显示约 3–7 条直接关系，其余淡出或进入列表；
- 一个 Group pair 的多条底层关系先聚合为一条群关系，Inspector 再展开；
- effective scope 超出预算时不先画任意子集：显示 Scope Summary、当前总量 / 可见量、排除原因与穷尽 List Equivalent，并进入 Anchor Required；
- Anchor 可以来自 Group、Search、Facet、Saved View 或 Saved Path。定位后围绕该焦点展开，不用 degree / recency / AI relevance 选 Top N，也不恢复未定义的 Subgroup 容器；
- 自动 cluster 只可作为可清除的临时 overlay，不形成 Group region、Boundary、Relation 或 catalog section。

这些数字用于首轮设计压力测试，不成为业务数据限制。

## 9.3 Group Map / R1–R2

- 默认围绕主要 Topics 和少量 bridge Nodes；
- 结构区域优先于所有 Node；
- 当前路径保持最显著；
- 跨群出口只显示最重要的 1–3 个方向；
- 候选与正式关系不处于同一默认层；
- 用户展开某一 Topic 后，其他区域降低细节而不完全消失。

## 9.4 Local Graph / R1

- 当前 Node 是唯一视觉中心；
- 初始呈现约 4–8 个与当前任务最相关的一跳对象；
- `Show more` 按关系类型或方向逐步展开；
- 二跳内容只在 Query Route 或用户明确展开时出现；
- backlinks、Reference Links、formal Relations 与 Evidence 分组；
- 图与 List Equivalent 使用同一过滤和排序。

## 9.5 Query Route / R2

- 默认一条主要解释路径；
- 最多同时呈现两条真正改变答案的替代分支；
- 其他检索对象进入 Evidence / Used knowledge list，不强行连成路径；
- 清除 Query Highlight 后恢复原图布局和过滤。

## 9.6 数字不是视觉 KPI

产品不默认显示：

- 总节点数；
- 总边数；
- 连通率；
- 图谱增长；
- “孤立知识”惩罚；
- 每日建立关系数量。

一个没有正式关系的知识群可以是合法、清楚且有用的 Bare 或 Oriented Group。

## 9.7 呈现强度不是关系半径

关系显示使用两套正交状态：

```text
RelationPresentation = quiet | peek | companion | explore
RelationRadius       = R0 | R1 | R2 | R3
```

| Presentation | 进入条件 | 可承载半径 | 状态后果 |
|---|---|---|---|
| Quiet | ordinary open、reading、writing | R0 cues | 无独立关系 surface；不写导航 |
| Peek | explicit Inspect Relation / endpoint | 单条 R1–R3 relation | transient；Close 回触发点；不改 Reading Target |
| Companion | explicit `查看相关知识 / 显示关系` | R1 Local 或 R2 Group | Reading 保持 Primary；最多一个；默认 follow explicit Open |
| Explore | explicit `在地图中探索 / 打开知识网络` | R1、R2 或 R3 | Relation Space 成为 Primary；保存 ReturnEnvelope |

普通打开、hover、Focus、text selection、scroll、AI proposal、Answer generation 与后台 refresh 都不能自动升级 presentation。Relation deep link 默认以 Peek 解释单条关系；只有保存了 Map / Network scene 的 link 或显式 Resume 才可直接进入 Explore。

数量表达遵守语义而非图形欲望：0 条 maintained current relation 不画空图；1 条使用完整 statement / Inspector；2–8 条可使用 Local Graph / List；超过预算先保留 maintained、applicable、与当前目标有解释价值的 4–8 条当前关系，再按 family、direction、Group、Challenge 或 review state 展开。RelationCandidate 与 History 始终分层；recency、click count、AI similarity 与布局中心性都不能单独提高长期关系显著性。

---

# 10. 稳定地图与 Focus + Context

## 10.1 稳定位置

- Group 的 Atlas 区域位置在没有结构变更时保持稳定；
- 自动布局更新形成可预览 View Change，不在每次打开时重新漂移；
- 选中对象可以局部展开，但原位置保留视觉锚点；
- Back 恢复原平移、缩放、过滤和选中路径；
- 用户固定位置属于 View，不改变 Relation truth。

## 10.2 选择，而不是无限缩放

- 滚轮只改变几何大小；
- 点击对象才改变 Scope；
- 展开邻居改变 Relation Radius；
- 阅读“更多”改变 Reading Depth；
- 四种动作不能共享一个含糊 Zoom 状态。

## 10.3 图谱和列表等价

List Equivalent 必须支持：

- 相同关系类型、方向和状态；
- 相同过滤；
- 相同 Selection State；
- 相同 Open from / to endpoint；
- 相同保存 Path；
- 键盘完成跨群探索。

列表不是图谱失败时的降级截图，而是完整产品表面。

---

# 11. Explore 的完整循环

## 11.1 探索的起点

用户可能从以下状态开始：

- “我不知道该问什么”；
- “我理解这个概念，但想知道它通向哪里”；
- “两个知识群为什么相连”；
- “这个答案还依赖什么”；
- “我上次走过哪条理解路径”。

## 11.2 一次探索循环

```text
选择当前范围或知识
  → 看见少量高价值邻接
  → 选择一条关系
  → 理解类型、方向、依据与目标语境
  → 决定保持当前群还是切换 Placement
  → 阅读目标 Orientation
  → 继续、返回、提问或保存 Path
```

## 11.3 Explore Recommendation

每次只提供 2–4 条路径，并明确原因：

- 补足当前理解缺口；
- 查看关键对照；
- 进入支撑当前 Claim 的基础知识；
- 检查一个争议或限制；
- 沿上次未完成 Path 继续；
- 跨到真正使用这条知识的另一个 Group。

“你可能感兴趣”不是合格理由。

这些推荐属于当前 Explore context。访问次数、完成率或模型排序不会让它自动变成 Scope 的`从这里开始`或推荐路线。用户选择`推荐这条路径`时，只在 Scope Overview 建立一条带目的与理由的 curation reference；原 Saved Path identity、步骤与历史保持不变。

## 11.4 Location、Return、Trail、Path 与 Progress 不同

| 责任 | 产品记录 | 不做什么 |
|---|---|---|
| 结构位置 | DepthTrail | 不记录访问顺序 |
| 临时回返 | ReturnStack / ReturnEnvelope | 不成为长期知识 |
| 本轮探索 | ExplorationSession / Trail | 不自动永久保存 |
| 长期路线 | SavedPath / Revision | 不保存当前进度 |
| 继续现场 | PathProgress / ResumePoint | 不修改路线 identity |

Relation 说明两个对象为什么相连；Trail 说明这一次实际走过哪里；SavedPath 保存用户为何按某个顺序理解多个对象。三者不能由同一条 edge 或 array 替代。

## 11.5 Path 与 Relation 不同

```text
SavedPath
  path_id
  title
  purpose
  current_revision_ref
  lifecycle

SavedPathRevision
  ordered_steps[]
    target_ref
    placement_context_ref?
    connector_kind
    connector_ref?
    step_rationale?
    target_revision_ref?
  revision_basis
```

SavedPath 不包含 `last_position`、completed steps、scroll 或 viewport。Path 中没有正式 Relation 的用户跳转标为 manual step；它不会生成 `related_to`。Path 被 Scope 推荐，只建立 RecommendedPathReference，不改变 canonical Topic order 或复制 Path。

## 11.6 Explore 动作副作用

- Hover / Focus：只高亮或移动键盘位置；
- Inspect：显示 Relation、Orientation 与 Preview，不写历史；
- Open：改变 primary target、写 ReturnEnvelope，并按条件写 Trail；
- Compare：临时有界集合；
- Expand / Filter / Dismiss / Pan / Zoom：只改变 scene state；
- Save Path：从 Trail 选择步骤并补 purpose / rationale；
- Continue Path：只更新 PathProgress。

## 11.7 分支

Trail 为 A → B → C 时，用户 Back 到 B 再 Open D，当前分支成为 A → B → D；Forward 可以失效，但 session 保留`刚才的另一条分支：C`。用户可以恢复另一分支或从两个分支中选择步骤保存，系统不默认展示复杂树。

## 11.8 Path 发生变化

- Node 移动 Placement：使用 redirect 恢复语境；
- Relation 被 supersede：Path 保留保存时 statement 并标记 changed；
- Source unavailable：相关 Evidence step 显示不可核验；
- Group 归档：Path 仍可按 historical mode 打开；
- split / merge 产生多个 successor：要求用户选择；
- Re-evaluate Path：提出当前 successor / draft revision，不覆盖原路线。

每个 step 使用 current、redirected、changed、historical-only 或 unavailable 表达影响。

## 11.9 Query Route 转换

Query Route 只属于具体 Run。用户选择`整理成探索路线`时，先进入 SavedPath draft，系统标出 formal relation、structure、evidence、reference 与 runtime retrieval jump；用户删除纯检索步骤、补目的并确认 manual connector 后才能保存。

---

# 12. Search、Ask、Explore 的边界与转换

## 12.1 Search / 定位

用户承诺：输入名称、关键词、来源片段或属性，返回已有对象和所在路径。

Search 不：

- 生成综合答案；
- 建立新的 Relation；
- 自动扩大到外部知识；
- 把相似结果画成正式路径。

## 12.2 Ask / 回答

用户承诺：在可预测的 Requested Context 下综合现有知识，回答后说明 Effective / Used Context，并给出 Claim-level support、真实路径或 Used Knowledge、证据、冲突、未知与 Coverage。

Ask 不：

- 静默保存为正式知识；
- 把检索顺序冒充知识关系；
- 用模型常识填平知识库缺口而不标注；
- 把所有相关对象展示成图谱。
- 用上一条 AI Answer 代替原始 Nodes / Evidence；
- 把 Saved Answer 默认当作当前 Knowledge Truth；
- 在没有真实 Route 时为视觉完整性补边。

## 12.3 Explore / 发现

用户承诺：从当前对象或范围出发，看见少量可解释连接，逐步进入相邻知识。

Explore 不：

- 默认生成长篇答案；
- 用无限推荐流替代用户选择；
- 以全局 hairball 证明知识丰富；
- 自动把访问路径写成正式关系。

## 12.4 合法转换

| 当前模式 | 用户信号 | 提供的转换 | 是否自动 |
|---|---|---|---|
| Search | 输入完整问题 | “用这些知识回答” | 否 |
| Search | 打开 Node | “查看关系” | 否 |
| Ask | 点击结论 | 打开对应 Node / Scope | 用户点击后 |
| Ask | 点击 Knowledge Route | 进入 Explore 并保留 Answer | 用户点击后 |
| Explore | 选中一个 Path | “基于这条路径提问” | 否 |
| Explore | 发现稳定关系 | “保存为关系建议” | 否 |
| Evidence | 选中片段 | Ask selected evidence / Create Claim | 否 |

界面可以预测用户意图，但不能在没有动作的情况下改变模式或写入知识。

---

# 13. AI Knowledge Route 的忠实度合同

## 13.1 Route 不是装饰图

Knowledge Route 必须解释：

- 回答使用了哪些知识；
- 每一步为什么能从 A 到 B；
- 哪些是正式关系；
- 哪些只是层级或证据连接；
- 哪些只是本次检索同时使用；
- 哪条 Answer Claim 由哪些 steps 支撑。
- 这条 Route 属于哪一次 Query Run，以及这些 steps 是否真正进入 Used Context。

## 13.2 RouteStep 模型

```text
RouteStep
  from_ref
  to_ref
  step_kind:
    structural_connection
    formal_relation
    evidence_connection
    retrieval_jump
    external_knowledge
  relation_ref?
  evidence_refs[]
  reason
  supports_answer_claim_refs[]
```

## 13.3 图上语法

- formal_relation：显示正式类型和方向；
- structural_connection：显示路径层级，不伪装成语义断言；
- evidence_connection：指向 Source Revision / Evidence Fragment，并由 Binding 说明对当前 Claim 的作用与可核验状态；
- retrieval_jump：明确标为“本次问题中一起使用”；
- external_knowledge：与个人知识库分层，并标明来源策略。

颜色不能单独承担上述区别。

## 13.4 禁止编造中间边

如果 Answer 同时使用 Node A 和 Node B，但没有正式关系：

- 可以把 A、B 分别连接到 Answer Claim；
- 可以显示共同 Source 或本次检索原因；
- 不能自动生成 A → related_to → B；
- 可以在回答后提出“是否保存为关系建议”，但必须给出候选类型和理由。

## 13.5 Route 与 Answer Claim 对齐

回答中的每个主要结论必须能高亮使用的 Route steps。点击结论：

- Reading Path 打开主要 Node；
- Relation Companion 高亮对应路径；
- Evidence Rail 只显示支撑该结论的片段；
- Back 返回 Answer 原结论位置。

如果无法形成可靠 Route，系统应显示 Used Knowledge List 与 Evidence，而不是生成一条看似完整的假路径。

Route 只是一种 Grounding 表达，不是全部 Grounding。用户原创 Node 可以直接支撑 Answer Claim 而没有外部 Evidence；外部 Source 可以支撑 Claim 但不进入 personal graph；reasoned derivation 必须显示输入 support。完整 Claim basis、Coverage、Follow-up 与 Saved Answer 历史语义以 `AI-native-个人知识库-AI查询与知识回答合同-v1.0.md` 为准。

---

# 14. 三个代表场景

## 14.1 认知科学：纵向深度

路径：

```text
L1 认知科学
  → L2 记忆研究
  → L3 情境依赖检索
  → D2 编码特异性与检索线索机制
  → D3 某实验的方法、结果片段和限制
```

合格体验：

- Group Overview 不复制 Topic Overview；
- Topic 展示代表 Nodes 和分支缺口；
- Concept Node 区分定义、机制、例子和不同理论；
- Claim 拥有适用条件和可挑战证据；
- 返回后恢复“情境依赖检索”正文原段落；
- Relation Lens 默认只显示理解当前概念所需的一跳关系。

## 14.2 AI Agent 产品设计：横向跨群

路径：

```text
AI Agent 产品设计 / 可逆行动
  → provides_foundation_for
人机协作 / 可控性
  → applies_to
高风险自动化 / Approval Gate
```

合格体验：

- 每条 Relation 有类型、方向和理由；
- 同一 Node 的 canonical content 不复制；
- 跨群时用户选择 Placement context；
- Group Relation Inspector 展示底层 supporting paths；
- 保存 Path 不自动新建任何 Relation；
- Ask 可基于 Saved Path 提问并保留原路线。

## 14.3 法国租房：条件、时间与伪冲突

问题：“入住前必须完成哪些手续？”

合格体验：

- Ask 先绑定身份、地点和日期等必要 Applicability；
- 不同时间或人群规则形成 qualified branches；
- 只有条件相同且不能同时成立时显示 contradicts；
- Answer Route 区分正式依赖、来源证据和本次检索跳转；
- 官方规则更新后原 Saved Answer 和 Route Snapshot 保留；
- Re-evaluate 生成当前路径，不覆盖旧路径。

---

# 15. 极端状态与可访问性

## 15.1 无正式关系

- Atlas 可以只有 Groups，没有连线；
- Group Overview 仍然完整；
- Explore 可以从层级、Placements 和 Reference Links 开始；
- 系统不为了视觉效果生成候选边。

## 15.2 单一超级节点

当一个 Node 拥有大量关系：

- Local Graph 只显示当前任务相关邻居；
- 按 relation family 分组；
- 默认不超过初始可理解预算；
- 提供 Search within relations；
- List Equivalent 支持排序和筛选；
- 不用无限缩小或物理模拟容纳全部对象。

## 15.3 100+ Groups / 10k+ Nodes

- Atlas / Network 先显示 Scope Summary 与穷尽 List Equivalent，并在超出预算时进入 Anchor Required；
- Search、Group、Facet、Saved View 或 Path 负责给出明确焦点；
- 不按度数、最近使用、AI relevance 或 embedding cluster 选取“核心”Top N，不创建 canonical Group regions；
- 自动 cluster 只作为可清除的临时观察 overlay；
- Local Graph 从当前选择按需展开；
- 图布局在本地缓存并增量更新；
- 所有图状态有列表等价；
- 性能降级时优先保留 Selection、标题和路径，不显示空白画布。

## 15.4 AI unavailable

- 正式 Relations、Reference Links、结构和 Saved Paths 可浏览；
- 用户可人工建立 Relation；
- Ask 与 Relation Suggestions 不可用；
- 已保存 Answer Route 仍可按 snapshot 查看；
- AI failure 不改变 Relation assertion disposition、change condition、Evidence / Challenge、lifecycle 或 Candidate decision。

## 15.5 键盘与屏幕阅读器

- 图谱拥有与视觉顺序无关但可预测的关系列表；
- 每条边可读为“来源对象 — 关系类型与方向 — 目标对象 — 状态”；
- Expand、Open、Back、Save Path 均可键盘完成；
- focus 不因图布局更新丢失；
- 颜色之外使用文字、线型、图标和分组；
- 200% zoom 时自动转为 Reading + Relation List，不压缩成不可读图。

---

# 16. 验收测试

## 16.1 范围、深度和半径不混淆

**Given** 用户正在 L3 Node 阅读 D2 Explanation，并打开 R1 Local Graph  
**When** 用户展开更多关系  
**Then**：

- Scope 仍是当前 Node；
- Reading Depth 与滚动位置不变；
- 只改变 Relation Radius；
- DepthTrail 不增加虚假的层级；
- Back 恢复此前邻接集合。

## 16.2 Search 直接进入 Node + Anchor

**Given** 用户搜索“情境依赖检索”中的一条限制  
**When** 打开 L3 + Anchor 结果  
**Then**：

- 当前 Group / Topic Placement 可理解；
- 正文精确定位到同一 Content Revision 的命中位置，不创建片段 Node；
- Up 返回 Topic，Back 返回 Search；
- 其他 Placements 一跳可达；
- Anchor moved / ambiguous / orphaned 时解释并提供恢复；
- 不要求先经过 Atlas 和 Group Overview。

## 16.3 Node 类型阅读合同

**Given** 用户分别打开 Concept、Claim、Method 与 Decision  
**When** 从 D0 展开到 D2  
**Then**：

- 四类对象使用共同六段骨架；
- 每类核心内容适配其任务；
- 缺少的重要部分被标为知识缺口，不显示空模板；
- Evidence 与 History 一跳可达。
- D0–D2 从同一 content tree 投影，不保存互相漂移的摘要与详细正文。

## 16.4 Connection 类型不混淆

**Given** 当前 Node 同时有 Topic Placement、普通 backlink、正式 Relation、Evidence 与 Query retrieval jump  
**When** 打开 Relation Lens  
**Then**：

- 五类连接可被文字识别；
- 只有正式 Relation 进入 Relation Inspector 的知识状态；
- retrieval jump 不进入长期图；
- 用户可以把 Reference Link 补全并提交为 maintained Relation；AI 只可建议 RelationCandidate；
- List Equivalent 表达相同区别。

## 16.5 AI 推断关系被用户接受

**Given** RelationCandidate 由系统推断  
**When** 用户检查证据并接受  
**Then**：

- Candidate 的 formation_basis 保持 system_inferred；
- 系统物化 Relation 与首个 RelationRevision，Candidate 标记 adopted；
- assertion disposition = maintained，Evidence / open Challenges 独立保留；
- Suggested layer 不再保留第二条候选边；
- History 可解释谁在何时接受、修改了什么。

## 16.6 Answer 不制造伪关系

**Given** Ask 同时检索 Node A 和 Node B，但两者没有正式 Relation  
**When** 生成 Knowledge Route  
**Then**：

- A、B 可分别支撑 Answer Claim；
- 显示 retrieval reason 或共同 Evidence；
- 不自动创建 `related_to`；
- 用户可以选择创建关系建议；
- 关闭 Answer 后长期图不新增边。

## 16.7 群关系可解释

**Given** Atlas 显示 Group A `provides_foundation_for` Group B  
**When** 用户选择这条边  
**Then**：

- 一句说明为什么重要；
- 至少一个 supporting path 可进入；
- 底层 Nodes、Relations 与 Evidence 可核验；
- Applicability、exceptions / limits、formation basis 与 review state 可检查；
- 共享标签或 embedding 相似不被当作依据；
- List Equivalent 可完成相同检查。

## 16.8 正式关系端点不混淆

**Given** 用户尝试连接一个 Topic 与一个 Node  
**When** 打开 Relation Editor  
**Then** 系统引导使用 Placement；Topic parent-child、Evidence、Reference 与 Retrieval Jump 也各自保持原连接类型，只有 Node↔Node 或 Group↔Group 可以提交正式 Semantic Relation。

## 16.9 图谱保持可读

**Given** 当前 Node 有 60 个一跳连接  
**When** 打开 Local Graph  
**Then**：

- 初始只显示当前任务最相关的一组；
- 用户知道还有更多；
- 可按类型、方向、状态和 Group 展开；
- 选择与 Back 保持稳定；
- 200% zoom 和键盘模式可完成探索。

## 16.10 Saved Path 历史影响

**Given** Path 中一条 Relation 已被 supersede  
**When** 用户重新打开 Path  
**Then**：

- 原路线按历史 snapshot 保留；
- 受影响 step 有清楚说明；
- 可查看当前等价路径；
- 新路线不会覆盖原路线；
- 未受影响的 Placement 和阅读位置保持。

## 16.11 Overview 到 Evidence 的核验路径

**Given** Group Overview 中一段综合判断由两个 Nodes、一条 Relation 和三个 Evidence Fragments 支撑  
**When** 用户从该 Overview Anchor 选择“这段内容依据什么”  
**Then**：

- 先显示 Support Map 中各对象承担的角色；
- 点击 Node 后进入精确 Node Anchor，而不是 Node 顶部；
- Evidence 继续进入 Source exact locator 并可返回原 Overview Anchor；
- Overview 自身不被显示为 Evidence endpoint；
- 若该段只有 Overview 文字而没有可核验对象，界面标明用户表述或建议“保存为独立知识”，不得伪造来源路径。

## 16.12 Direction、inverse 与多关系不混淆

**Given** A `provides_foundation_for` B，A 与 B 另有 `contrasts_with`  
**When** 用户从 B 打开关系并在图中检查同 pair  
**Then** `builds_on` 只是第一条 Relation 的 inverse reading label；两条 Relations 保持独立 identities；对称关系只保存一份 normalized edge；Bundle 可展开，不生成镜像记录或 `related_to`。

## 16.13 跨群出口不越权

**Given** 不同 Groups 中两个 Nodes 存在 maintained current Relation  
**When** Group Map 显示跨群出口而 Atlas 尚无 Group Relation  
**Then** 用户可沿 path 进入目标 Placement；Atlas 不因单条 path、共享 Node、Gateway、Saved Path 或 Query Route 自动生成 edge；系统只能另提 Group RelationCandidate，采用后才产生正式 Group Relation。

## 16.14 Aggregated Group Relation 变化传播

**Given** 用户接受了基于多个 supporting paths 的 Group Relation  
**When** 一条主要 path 被 supersede 或 endpoint Anchor orphaned  
**Then** Group Relation 的 Support Set 创建新 Revision，Relation 保持 maintained 并进入 review_due，保留 original relation revision 与 remaining support；不静默消失、改类型或影响同 pair 的其他 Relations；用户可 Maintain、更新限定、换支撑、End、Retract、Supersede 或 Defer。

## 16.15 Inspect 与 scene 操作不污染 Trail

**Given** 用户依次 Inspect 四个 Nodes，并执行 expand、filter 与 zoom  
**When** 保存探索路线  
**Then** 只有实际 Open 的语义目标进入候选步骤；scene state 可以恢复但不进入 SavedPath、Relation 或 Recent。

## 16.16 Back 后分支可恢复

**Given** 用户沿 A → B → C 探索  
**When** Back 到 B 并 Open D  
**Then** 当前 Trail 成为 A → B → D，C 所在分支以`刚才的另一条分支`可恢复；保存时只使用用户选中的步骤。

## 16.17 SavedPath 与 Progress 分离

**Given** 用户沿一条被 Overview 推荐的 Path 读到第 4 步  
**When** 关闭、继续或 reset progress  
**Then** 只更新 PathProgress / ResumePoint；Path revision、ordered steps、RecommendedPathReference 与 relation truth 不变。

## 16.18 Query Route 显式转 Path

**Given** Answer Route 含正式 Relation、Evidence 与 runtime retrieval jump  
**When** 用户选择保存路线  
**Then** 先进入可编辑 draft，连接类型可核验；runtime jump 不冒充 Relation；保存不会把 Answer 或相邻步骤自动写入 Knowledge Graph。

## 16.19 L2 Topic opening 不打断直接深入

**Given** 一个四层 Topic path 同时有 Bare、Compact、Editorial 与 single-child scopes  
**When** 用户 Expand / Inspect / Open Topic、直接 Open L3 Knowledge、从 Search 进入 D2 Anchor、执行 Up / Back / Resume  
**Then** Scope Level、Reading Depth 与 Return semantics 分别变化；Topic Open 给局部方向但不自动打开第一篇 Knowledge，deep target 不被 L2 截停，祖先 Overview 不重复，single-child 不自动 redirect，Relation Radius 保持当前选择。

## 16.20 Relation Presentation 与 Radius 不混淆

**Given** 用户在同一 L3 Knowledge 上普通阅读，并存在 R1 Local Relations、R2 Group paths 与一条 Relation deep link  
**When** 依次 hover、Inspect、打开 Companion、进入 Explore、切换 R1 / R2、Pin、Close、Back 与 ordinary open  
**Then** Quiet / Peek / Companion / Explore 只改变注意力强度，R1 / R2 只改变范围；hover 不升级，Peek 不改 Reading Target，Companion 只 follow explicit Open，Explore 由显式动作进入；ordinary open 回到 Quiet，只有 Resume 可恢复安全 scene；各动作不重置 Anchor、scroll、DepthTrail、Ask scope、Trail 或 map viewport。

## 16.21 F1 到 F100 的 Network 仍是同一种探索

**Given** 同一 Space 从 1 个 Group 增长到 10、100+ 个 Groups，并包含无关系、单一高连接点、多关系 pair 与 dormant Groups  
**When** 用户进入 Network、选择焦点、切换 Graph / List、清除筛选并返回 Reading  
**Then** 预算内可以显示 effective scope；超预算先显示 Scope Summary / hidden counts / exhaustive List 并要求 Anchor；定位后只展开 selected Group 与约 3–7 个 accepted neighbours；无自动 Top N、Group regions 或关系补边；Graph / List 共享 Selection、filters、open 与 ReturnEnvelope；规模变化不创建新模式。

---

# 17. 研究事实与产品推论

本轮只使用公开官方资料验证交互模式，不把竞品功能直接复制为需求。

## 17.1 生成式 Mind Map 可以连接 Overview、展开与提问

NotebookLM 官方说明 Mind Map 可用于快速理解整体、展开或折叠分支，并可直接选择节点向 Chat 提问。[NotebookLM Mind Maps](https://support.google.com/notebooklm/answer/16212283?hl=en)

产品推论：图谱节点与 Ask 共享 Selection 是有效模式；但本产品的关系网络是长期可编辑知识，不应把一次生成的 Mind Map 直接视为 canonical structure。

## 17.2 局部图比全局图更适合日常对象探索

Capacities 官方文档把 Graph 定义为当前对象的局部上下文，可查看入向与出向连接并逐步 `Show more`；同一文档明确当前没有全局 Graph。[Capacities Views](https://docs.capacities.io/reference/views) 其网络化笔记指南也明确提醒“链接越多并不一定越有帮助”，应建立有价值的连接。[Capacities Networked Note-taking](https://docs.capacities.io/tutorials/networked-note-taking)

产品推论：本产品需要 Group-level Atlas 和 Node-level Local Graph 两套范围清楚的地图，而不是把全部对象塞进一个万能全局图；关系预算和语义类型比连线数量重要。

## 17.3 方向、标签和过滤是图谱的基础可解释能力

Anytype 官方 Graph 文档说明图中可查看对象连接与流向，并提供标题、箭头、图标、链接、属性和未连接对象等显示设置。[Anytype Graph](https://doc.anytype.io/anytype-docs/advanced/feature-list-by-platform/graph)

产品推论：关系方向、显示层与过滤是基础能力；本产品还必须进一步区分正式 Relation、结构、证据、普通链接和检索跳转。

## 17.4 空间布局本身可以承载用户语境，但不应等同于正式关系

Heptabase 官方 Wiki 将白板 sense-making、nested whiteboards、卡片组织和 AI 并列为主要工作流；其 MCP 文档说明 AI 可以读取白板中的卡片、section、文字、mind map 及其空间组织，并在需要时深入读取单个对象。[Heptabase Public Wiki](https://wiki.heptabase.com/) [Heptabase MCP](https://support.heptabase.com/en/articles/12679581-how-to-use-heptabase-mcp)

产品推论：空间编排可以保存思考语境，因此未来 Canvas 可以作为派生 View；但卡片距离、分区和手工连线不能自动升级为 canonical Relation。

## 17.5 密度既是理解问题，也是性能问题

Heptabase 官方性能说明指出，单个白板超过约 100–150 张卡片可能出现明显延迟，大量复杂元素甚至在更少卡片时也会影响性能。[Heptabase Performance](https://support.heptabase.com/en/articles/11430704-troubleshooting-performance-and-lag-issues-in-heptabase)

产品推论：具体阈值不能直接移植，但“默认只显示任务相关的局部集合、按需展开，并用 Scope Summary / List 保留全局语境”同时是认知和工程要求；这不授权把自动聚类固化成 Group regions 或长期结构。

## 17.6 Wikibase：qualifier 属于陈述意义

Wikibase 官方数据模型把 Statement 分为 subject、main statement、qualifiers、references 与 rank；Primer 明确指出 qualifier 是陈述意义的一部分，移除 qualifier 会改变 statement，而 reference 承担不同责任。[Wikibase Data Model](https://www.mediawiki.org/wiki/Wikibase/DataModel) · [Wikibase Data Model Primer](https://www.mediawiki.org/wiki/Wikibase/DataModel/Primer)

产品推论：Applicability、时间与比较维度不能只是隐藏 metadata；它们改变 Relation 意义，需要进入 statement revision、Inspect 与冲突判断。Evidence 可以为空或后补，但形成依据和 evidence-limited 必须诚实。

## 17.7 SKOS：direct、inverse、symmetric 与 transitive closure 分开

W3C SKOS 区分 direct `broader / narrower` 与只用于推导查询的 transitive super-property，并分别定义 inverse 和 symmetric 语义。[SKOS Reference](https://www.w3.org/TR/skos-reference/)

产品推论：本产品保存 direct Relation truth；inverse label 是同一 assertion 的反向读法；对称 edge 只存一份；只有类型明确允许时才显示 derived path，并且 derived path 不自动成为 maintained Relation。

## 17.8 W3C：Breadcrumb、Focus 与 Activation 分工

WAI-ARIA Breadcrumb Pattern 把 breadcrumb 定义为当前页面在层级中的位置；Tree View 与 Keyboard Interface 区分 focus、selection 与 activation，并要求可预测的键盘与焦点恢复。[Breadcrumb](https://www.w3.org/WAI/ARIA/apg/patterns/breadcrumb/) · [Tree View](https://www.w3.org/WAI/ARIA/apg/patterns/treeview/) · [Keyboard Interface](https://www.w3.org/WAI/ARIA/apg/practices/keyboard-interface/)

产品推论：DepthTrail 不能承担 Back history；Focus / Inspect 不能写 Open 的副作用；Up、Back 与 Close 必须分别可预测。

## 17.9 Obsidian：Local Graph 与 Page Preview 分开

Obsidian 官方将 Global Graph 与围绕 active note 的 Local Graph 分开，并用 Page Preview 支持 hover 查看而不离开当前 note。[Graph View](https://obsidian.md/help/plugins/graph) · [Page Preview](https://obsidian.md/help/plugins/page-preview)

产品推论：局部探索需要当前中心与有界半径；Preview 不应污染 ReturnStack 或 ExplorationTrail。

## 17.10 Neo4j 与 TheBrain：scene state 和访问序列都不是 Saved Path

Neo4j 官方把 expand、dismiss、filter、group、undo / redo 与 viewport 作为当前图谱 scene 操作；TheBrain 用 Past Thought List 顺序保留访问过的 Thoughts。[Neo4j Scene Interactions](https://neo4j.com/docs/aura/explore/explore-visual-tour/scene-interactions/) · [TheBrain Navigation](https://help.thebrain.com/androidphone/navigating.html)

产品推论：scene state 可以恢复但不写知识；visited sequence 有助于回返，但只有用户挑选、补目的与理由后才成为 SavedPath。

## 17.11 Supporting Pane：支撑内容有主次，并随窗口自适应

Apple Split View 指南允许主内容旁组合 supplementary panes，也建议在编辑时隐藏其他 pane 以减少干扰；Material 3 Adaptive Supporting Pane 让 main pane 保持主焦点，在大窗口并列 supporting pane、小窗口一次只显示一个 pane并提供返回；Capacities 又把 preview modal、side panel 与 full page 明确分开。[Apple Split Views](https://developer.apple.com/design/human-interface-guidelines/split-views) · [Android Supporting Pane](https://developer.android.com/develop/adaptive-apps/guides/build-a-supporting-pane-layout) · [Capacities Navigation](https://docs.capacities.io/reference/navigation)

产品推论：关系视图可以按意图从 Peek 长成 Companion / Explore，且在 desktop / mobile 采用不同排列；但 pane 的存在和大小不能决定关系范围或知识状态。本产品的 Quiet default、follow-open 与单 Companion 上限是进一步的产品约束。

---

# 18. 对下一阶段设计的约束

在产品定义审阅完成前，不创建原型。后续视觉设计必须先证明以下十七组真实状态：

1. 同一 Node 中 D0 → D2 → D3 的连续阅读；
2. 同一 Selection 下 R0 List、R1 Local Graph 与 R2 Query Route 的切换；
3. Structural、Reference、Formal Relation、Evidence、Retrieval Jump 五类连接不会混淆；
4. Atlas resting、selected Group、Query Highlight、100+ Groups 四种密度状态；
5. Answer Claim → Route Step → Evidence → 返回 Answer 的可逆链路。
6. Overview Anchor → Support Map → Node Anchor / Relation → Evidence → Source → 返回 Overview 的可逆链路。
7. Requested / Effective / Used Context 与 Follow-up Delta 可检查，但不遮蔽 Direct Answer；
8. Claim Support、Coverage、Saved Answer Original / Re-evaluate 与无 Route fallback 均不改变 canonical graph。
9. 有方向 Relation 的 inverse reading、对称 Relation 的单一 identity，以及同 pair 多 Relation Bundle；
10. cross-group exit → Group Relation Candidate → adopted Relation / Atlas edge → Support Set change → review_due / Decision 的完整循环；
11. endpoint Anchor moved / ambiguous / orphaned 后的 Relation impact、修复与历史返回。
12. DepthTrail、Back / Forward、Up、Close 与 Resume 的不同后果；
13. Hover / Focus / Inspect / Open / Compare 与 scene operations 的写入差异；
14. Back 后新 Open 的分支、`刚才的另一条分支`与分支恢复；
15. Trail 筛选成 SavedPath、manual step、Path revision 与独立 PathProgress；
16. Path changed / historical / re-evaluate 以及 Graph / List / mobile / keyboard 等价。
17. Quiet / Peek / Companion / Explore 的显式升级、follow-open / pinned、ordinary open / Resume 分权、0 / 1 / dense relation 与 desktop / mobile 等价。
18. F1 / F10 / F100 / F10K 的同构 Network、Anchor Required、Scope Summary、穷尽 List、unconnected Group 与清除临时 cluster overlay。

“2 + 3”的视觉结合因此进一步收敛为：

- 方向 3 承担 Scope 与 Reading Depth 的连续主轴；
- 方向 2 承担 Relation Radius 与 Route Highlight；
- 用户动作明确改变其中一个维度，不让所有面板同时重排；
- 图谱只显示真实知识对象和明确连接类别；
- Bare / Oriented / review_due / Paused 仍使用同一语法，只改变真实内容权重、受影响路径与注意力说明。

---

## 结论

这款产品的“深”不应来自更多页面、更多小字或更密的连线，而应来自三件事：

> **范围可以连续定位，知识可以逐层解释，关系可以逐步扩展且每一步都说得清为什么。**

Overview、Detail、Evidence、Atlas、Local Graph 与 Ask 不是六个功能模块。它们是同一份知识在不同范围、阅读深度和关系半径下的表达；用户每次深入或横跳，都能保持身份、语境、依据和返回路径。
