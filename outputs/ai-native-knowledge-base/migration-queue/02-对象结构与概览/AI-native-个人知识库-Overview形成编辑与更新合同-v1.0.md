# AI-native 个人知识库

## Overview 形成、编辑与更新合同 v1.0 — Scope Orientation、Projection 与 Editorial Truth

> 文档日期：2026-08-06  
> 文档性质：产品本体合同，不是页面线框、摘要 Prompt、数据库实现或原型规格  
> Canonical 产品定义：`AI-native-个人知识库-终局产品设计文档-v4.0.md`；本合同只证明 Overview 形成与更新责任，不得反向改写 v4.0  
> v4.0 Scope Overview 覆写：任意深度 Topic 都可以拥有局部 Overview；它与 Group Overview 共用“定位、结构、代表知识、关系出口、未知、下一入口”责任，但不获得 Group roots、Group Relation 身份或第二份 Knowledge 正文  
> v4.0 阅读策展覆写：stable start、representative Knowledge 与 recommended Path 属于 Scope editorial curation；structure fallback、Resume 与 contextual recommendation 分属结构投影、工作现场和本次会话，不得通过同一自动排名互相覆盖  
> v4.0 Relation 覆写：Topic Overview 可以投影真实 cross-group exits；Group Overview 只把 maintained current Group Relations 当作正式群关系。RelationCandidate、Bundle 默认 member 与 Query Highlight 都不能静默写进 editorial prose 或稳定入口  
> v4.0 Query 覆写：Overview 在 Answer 中默认只提供 scope orientation / context_only；普通保存回答不改变 Overview，只有显式“建议更新概览”创建带 Anchor、Support Map 与影响预览的 Semantic Diff  
> v4.0 Boundary 与 Scope 覆写：Group Overview 的 Boundary 来自 current Group Boundary Revision，不由现有内容或 View result 反推；Topic Projection 必须标明 direct / descendants；Source coverage 分开 direct Attachment、used-by-accepted-knowledge 与 referenced-through-shared-knowledge  
> v4.0 探索连续性覆写：Saved Path Overview 解释路线 purpose、Revision 与 impact；`从哪里继续`来自独立 PathProgress / ResumePoint 投影，不属于 Path Overview 的 editorial truth  
> 2026-08-08 Topic Opening 冻结：Topic Overview 是 Topic Reading 顶部的局部开场，不是独立中转页；Expand / Inspect / Open / direct child open 分权，Bare / Compact / Editorial 只表达真实内容密度，deep link 与 Resume 不被 Overview 截停  
> 2026-08-09 Group State 覆写：Group 不再使用互斥 `formation_phase`；Orientation Profile 选择 Presentation，Change / Attention / Lifecycle / Boundary condition 仅叠加必要说明，任何组合都保持同一 Overview identity。完整合同见`AI-native-个人知识库-知识群状态演化与身份连续性合同-v1.0.md`  
> 2026-08-10 Relation Lifecycle 覆写：Support Map 固定 relation_revision_id；Evidence / Support Set 变化不等于 RelationRevision；ended / superseded / retracted / archived / review_due 对 Overview 使用不同影响。完整合同见`AI-native-个人知识库-关系陈述生命周期与网络可信性合同-v1.0.md`  
> 2026-08-10 Group Relation Aggregation 覆写：Group Overview 的稳定群关系投影只读取 maintained + current lifecycle + applicable Relations；cross-group exit、Aggregation Signal 与 RelationCandidate 分层呈现，不能因 path count 或 AI 建议写入 Editorial。完整合同见`AI-native-个人知识库-群级关系聚合门槛与支撑充分性合同-v1.0.md`  
> 2026-08-10 Group Relation Type Registry 覆写：正式投影只读取十一种已注册类型及其被 RelationRevision 固定的定义版本；共享核心知识是按 canonical Knowledge identity、当前 Placements 与 Boundary roles 重算的 observation，不是 Group Relation，不能进入 Editorial 或稳定“关键关系”。完整合同见`AI-native-个人知识库-群级关系类型注册表与语义互斥合同-v1.0.md`  
> 2026-08-10 Group Pair Comparison 覆写：Overview 可以提供`比较两个知识群`入口和一句 current relation / shared observation 摘要，但不内嵌完整 Pair inventory、Candidate review、History 或 migration。Compare 使用独立临时 snapshot，关闭后回到原 Overview Anchor。完整合同见`AI-native-个人知识库-知识群对照与关系检查器合同-v1.0.md`  
> 2026-08-10 Knowledge Relation Type Registry 覆写：Knowledge / Topic relation projection 只读取已维护的 25-type `knowledge.*` Relations 与 pinned definition revision；Evidence / Answer support、Reference、derived path、IdentityTransition、QuestionTarget 与 disposition 不能作为普通 edge 写进 Editorial。`applies_to`与`implements`必须使用不同句子。完整合同见`AI-native-个人知识库-知识关系类型注册表与跨层语义合同-v1.0.md`  
> 2026-08-10 Question Overview 覆写：Overview 只投影用户保存且对当前 Scope 有解释价值的 Question Knowledge；Runtime Unknown、Gap Marker、Annotation 与 Conflict 不自动进入“关键问题”。Question 的 partial / provisional / resolved、pursuit 与 review 状态分层读取。完整合同见`AI-native-个人知识库-问题知识、未知与求解生命周期合同-v1.0.md`  
> 2026-08-10 真实夹具覆写：关键 Question 若依赖时效与主体条件，Overview 在 `changes_available / review_due` 时必须显示 adopted `as_of`、变化原因与受影响 criterion；不把规则变化写成旧回答自动错误。内容证明见`AI-native-个人知识库-真实端到端使用样例与设计数据夹具-v1.0.md`  
> 历史深层模型：`AI-native-个人知识库-产品定义-v3.0.md`  
> 相邻合同：`AI-native-个人知识库-核心体验与知识群生命周期-v1.0.md`、`AI-native-个人知识库-知识深度与关系探索合同-v1.0.md`、`AI-native-个人知识库-知识形成与维护循环-v1.0.md`、`AI-native-个人知识库-知识群边界与跨群架构合同-v1.0.md`、`AI-native-个人知识库-知识节点粒度与内容组成合同-v1.0.md`、`AI-native-个人知识库-AI查询与知识回答合同-v1.0.md`、`AI-native-个人知识库-直接创作编辑与版本历史合同-v1.0.md`、`AI-native-个人知识库-属性Facet与适用条件合同-v1.0.md`、`AI-native-个人知识库-产品对象层级与身份治理合同-v1.0.md`、`AI-native-个人知识库-关系陈述生命周期与网络可信性合同-v1.0.md`  
> 核心问题：Overview 如何成为一个知识范围可维护的入口，同时不复制 Node 正文、不伪造完整性、不把动态查询写死、不让 AI 静默重写用户对这个范围的整体理解

---

# 0. 执行决定

本轮冻结四十四项产品决定。

1. **Overview 是一个 Scope 的可维护方向说明，不是一次性摘要。** 它帮助用户理解“这里是什么、由什么组成、目前知道什么、哪里不确定、下一步去哪里”。
2. **Overview 是 Primary Product Resource，但不是 Knowledge Node。** Node 保存可独立复用的知识 identity；Overview 保存一个 Scope 的进入方式、整体叙事和导航意图。Projection Definition 内嵌于 Overview，Projection Evaluation / cached result 属于可重建观察，不是第二个 Overview。
3. **每个可拥有 Overview 的 Scope 只有一个 canonical Overview identity。** 历史版本、阶段快照和分享快照不是第二个 canonical Overview。
4. **Overview 目前只允许属于 Space、Group、Topic 或 Saved Path。** Home、Search result、AI Answer、View 和临时 Selection 不创建 Overview identity。
5. **Home 不是 Space Overview。** Space Overview 是稳定的知识范围解释；Home 是由 Space Overview、最近焦点和高影响变化组成的情境入口。
6. **Overview 不是 View。** View 按规则筛选、排序和布局现有对象；Overview 还包含有作者、有版本、有意图的编辑性叙事。
7. **Overview 的正文只有一棵 canonical content tree。** `orientation / structure / synthesis / coverage / conflicts / unknowns` 不再分别保存成与正文平行的文本真相。
8. **Orientation、Structure、Synthesis 是阅读语义区，不是三份独立正文。** 它们由同一 Overview Content Revision 中的 Blocks 与 Projections 组成。
9. **Overview 同时包含可版本化叙事与动态投影，但两者必须显式区分。** 叙事不会因为输入变化自动改写；投影可以按规则刷新。
10. **Editorial Block 保存这个 Scope 自己的表达。** 它可以解释边界、整体理解、阅读顺序和为何重要，但不能偷偷承担应有独立 Node identity 的可复用 Claim。
11. **Projection Block 保存规则，不保存第二份对象真相。** Topic 结构、代表 Nodes、关键 Relations、变化、未知和覆盖都从 canonical objects 动态重建。
12. **Reference Block 复用 Node / Anchor。** 它必须选择 Link、Live excerpt、Pinned excerpt 或 Explicit quote，不能无语义复制正文。
13. **Navigation Block 只表达进入路径。** 它不创造 Placement、Relation、Group membership 或知识状态。
14. **Status Block 是派生说明，不是 Overview 自己的认识状态。** Overview 不拥有一个混合所有内容的 confidence 或 epistemic score。
15. **Overview 不成为 Evidence Connection 的正式知识端点。** 需要被证据支持的独立主张应存在于 Node；Overview 通过 Node / Relation / Structure provenance 解释自己的内容。
16. **Overview Support Map 以 Anchor 粒度连接叙事与支撑对象。** 支撑对象可以是 Node Anchor、Relation、Structure Projection、Scope Boundary 或历史 Overview Anchor。
17. **作者来源、更新策略和锁定状态是三个正交轴。** `User-owned / AI-assisted / Generated` 不再用一个枚举同时表达谁写的、谁能改和是否自动更新。
18. **AI 生成的叙事一旦被接受，就成为有 revision 的已接受文本。** 后续变化只产生新 Diff，不在打开页面时静默替换。
19. **只有 Projection Block 可以自动刷新。** 自动刷新改变显示结果，不改变 Node、Topic、Relation 或 Overview Editorial truth。
20. **锁定保护具体 Block 不被替换，但不隐藏输入已变化。** Locked + out-of-sync 是合法同时状态。
21. **Overview alignment 与 knowledge state 分开。** `aligned / changes_available / review_due / knowingly_diverged` 只说明 Overview 与当前 Scope 输入是否一致，不宣称范围内知识“可信或成熟”。
22. **Orientation Profile 只改变默认编排和信息权重。** Bare、Structuring、Oriented 不复制 Overview identity，也不自动生成另一份正文；Change、Attention、Lifecycle 与 Boundary condition 是独立 overlays。
23. **Bare Group Overview 可以没有叙事正文。** 名称、边界句、已有内容和一个首要开始动作已经是合法 Overview；产品不能用 AI 长文填补空白。
24. **Oriented Overview 不等于完成。** 它可以包含明确未知、争议和覆盖边界，且不显示完整度百分比。
25. **Change Overlay 先保留最后稳定理解，再显示变化。** “当前版本”“变化建议”“变化前版本”必须可区分，不能先重写再展示 Diff；Changes 不会把 Oriented Overview 换成另一类页面。
26. **Ask 生成的“概览回答”不是 Overview 更新。** 只有显式选择“建议更新概览”并通过 Overview Diff / Change Set，才改变 canonical Overview。
27. **Search 可以命中 Overview Block，但结果身份必须是 Overview + Anchor + Scope。** 它不能把 Overview 段落伪装成 Knowledge Node。
28. **Scope 结构变换不使用正文拼接。** Topic Promotion、Group Split / Merge、Absorb 和 Saved Path 变化都要重新判断 Overview identity、lineage、projection 和 editorial content。
29. **Overview 变化传播由依赖类型决定。** 结构投影刷新、Node live reference 更新、Pinned reference 保持、Editorial prose 进入 Diff、历史 snapshot 永不改写。
30. **AI unavailable 时 Overview 仍可读、可写、可导航和查看历史。** 只有生成建议、语义归纳和某些排序会暂停。
31. **完整导出必须同时保留 accepted text、Blocks、Anchors、Projection definitions、Support Map、revisions、locks、lineage 与可读降级文本。**
32. **Overview 质量不以篇幅、AI 生成频率、引用数量或覆盖百分比衡量。** 用户能否快速定位、理解边界、进入正确知识并识别变化，才是质量。
33. **Group Boundary Revision 是 Overview Orientation 的规范输入。** Boundary 的 rename / clarification 可以更新当前定义；现有 Topic、Placement、Attachment 或 View result 不会反向重写它。
34. **Boundary 与内容暂时不一致是可表达状态。** Overview 可以说明 example / bridge / reference / needs relocation 等 tension，但不把它包装成错误、完整度下降或自动整理任务。
35. **Topic Overview 必须区分 direct 与 descendant projection。** 默认讲清当前 Topic 本身；包含子主题时明确标注、按 Knowledge identity 去重并保留 paths，不为 ancestors 创建镜像 Placement。
36. **Source coverage 不等于证据覆盖。** Overview 分开材料被直接加入何处、哪些材料实际支撑当前知识、哪些只因共享 Knowledge 被引用；Source-only Attachment 可以构成材料覆盖，但不能冒充 Claim support。
37. **Topic Overview 是 Topic Reading 的开头区域，不是额外页面。** Open Topic 后 Orientation 与 direct structure 位于同一连续 scroll surface，不再经过“概览页 → 目录页”两次跳转。
38. **Disclosure、Inspect、Open 与 direct child open 后果分开。** Expand 只展开 children；Inspect 只预览；Open Topic 进入局部开场；点击 Knowledge / Anchor 直接进入目标。
39. **Topic 默认投影 direct children。** Descendant scope 只作为 branch summary 或显式`包含子主题`rollup；不在每个祖先层重复铺开相同 Knowledge。
40. **Topic opening 有 Bare、Compact、Editorial 三种密度。** 它们由真实 accepted content 与结构决定，不是 formation phase、质量等级、用户模板或三套 identity。
41. **Bare 是完整合法状态。** 空 Topic、single-child Topic、Source-only Topic 可以只有 title、path、一句说明、真实子项与动作；不生成 AI 占位 prose、空图、空 gaps。
42. **Single-child Topic 不自动重定向。** 若它长期没有独立 Orientation、兄弟边界或路径作用，系统可以提出 flatten Change Set；拒绝不改变结构、URL、History 或 Saved Path。
43. **Deep link、Search、Ask、Relation 与 Resume 不被 Topic Overview 截停。** 明确目标直接打开 exact Knowledge / Anchor / scene；Overview 通过 DepthTrail、Up 与 owner context 可达。
44. **递归 Overview 只表达相对父级的新信息。** 祖先压缩为 DepthTrail 与最多一句 context；Boundary、父级 synthesis、全部 Relations、Sources 与变化状态不复制到每层。

---

# 1. 当前规格中的六个结构冲突

## 1.1 Schema 与正文重复

旧 schema 同时保存：

```text
orientation
structure
synthesis
coverage
conflicts
unknowns
```

如果这些字段各自存一份文本，正文又使用 Blocks，就会出现“改了 Overview 正文但 Orientation 没变”“AI 更新 Synthesis 却覆盖用户段落”的多份真相。

## 1.2 动态结构与编辑性叙事混合

Topic tree、代表 Nodes、关系和变化应该从 canonical objects 重建；“为什么这个范围重要”“建议怎样开始理解”则需要有作者和历史。若两者都是普通段落，要么结构很快过期，要么用户无法真正编辑。

## 1.3 Ownership 同时承担三种含义

`User-owned / AI-assisted / Generated` 混合了：

- 最初是谁写的；
- 后续谁可以修改；
- 是否会自动刷新；
- 用户是否锁定。

这会产生难以回答的问题：用户编辑过一段 AI Generated 文本后，它还是 Generated 吗？锁定 AI-assisted 是改变作者还是更新权限？

## 1.4 Overview 可能成为隐藏知识层

如果 Overview 允许写入大量没有 Node / Relation provenance 的事实主张，Ask 会读取到一套无法单独维护、无法精确核验、不会进入图谱的“影子知识”。

## 1.5 “生成 Overview”没有时间语义

系统未明确区分：

- 当前用户正在看的 Current Overview Revision；
- AI 生成但未接受的 preview；
- 因知识变化而产生的 proposed revision；
- 自动刷新的 projection results；
- 变化前的 historical snapshot。

结果是“最新”可能同时意味着模型刚生成、用户刚接受、来源刚变化或结构刚刷新。

## 1.6 状态配置可能被错误实现成多套页面真相

Bare、Oriented 与 Change Overlay 的信息顺序不同，但如果每种状态各存一份 Overview，状态变化就会复制文本、丢失编辑、改变 URL 和破坏 Saved Path。它们必须组合在同一个 Overview identity 上。

---

# 2. 目标与非目标

## 2.1 产品目标

Overview 必须同时做到：

1. 十秒内让用户说清当前 Scope 是什么；
2. 让用户看见主要结构，而不是先读文件列表或全量图谱；
3. 让“当前整体理解”可以被人工编辑、AI 协助和长期版本化；
4. 让每个重要概括都能回到支撑 Node、Relation 或结构依据；
5. 在输入变化时解释“什么变了、什么没变、是否需要决定”；
6. 从 Orientation 连续进入 Topic、Node、Relation 与 Evidence；
7. 在 AI、索引或来源不可用时仍然成立。

## 2.2 非目标

- 不把 Overview 变成日报、任务中心、统计仪表盘或 AI feed；
- 不为每个查询结果、View 或 Answer 创建 Overview；
- 不用一段 AI 长摘要代替 Topic structure 与 Node content；
- 不在 Overview 内建立第二套 Group membership 或 Relation truth；
- 不要求所有 Scope 都填满同一模板；
- 不用“知识完整度”“可信度 87%”或字数评价 Overview；
- 不因进入本合同而开始视觉稿、原型或技术实现。

---

# 3. Overview、Node、View、Home 与 Answer 的边界

| 对象 / 表面 | 保存什么 | 是否有稳定 identity | 是否版本化 | 是否可自动刷新 | 是否是知识 truth |
|---|---|---:|---:|---:|---:|
| Overview | Scope 的编辑性叙事、投影规则、进入路径 | 是 | 是 | 只有 Projection | 只保存 scope-level editorial truth，不替代 Nodes |
| Knowledge Node | 可独立维护与复用的知识 | 是 | 是 | 否；更新形成 revision | 是 |
| View | 筛选、排序、分组和布局规则 | 是 | 配置可版本化 | 是 | 否 |
| Home | 当前用户的情境入口 | 否，属于产品 surface | 否 | 是 | 否 |
| AI Answer | 一次问题在 Query Context 下的回答 | session / saved identity | 保存后有 snapshot | Re-evaluate 新建版本 | 否，除非显式保存为知识 |
| Source Summary | 对原始输入的派生说明 | 属于 Source revision | 随 Source 版本 | 可以重算 | 否 |

## 3.1 一条内容何时属于 Overview

适合留在 Overview：

- Scope 的边界与目的；
- 多个 Nodes 共同构成的整体解释；
- “从哪里开始”的编辑性阅读建议；
- 对主题地形、覆盖边界和当前变化的说明；
- 不需要在其他 Scope 独立复用的过渡与连接句。

应该成为或引用 Node：

- 可独立成立、反驳或修订的 Claim；
- 有独立 Applicability 或 Evidence 的判断；
- 会跨 Group / Topic 复用的 Concept、Method、Decision 或 Principle；
- 需要正式 Relation 的内容；
- Overview 改写后仍应保持 identity 的知识。

## 3.2 Overview 不是 Node 拼贴

Overview 不按以下方式生成：

```text
Node A orientation + Node B orientation + Node C orientation
  → 一篇看似流畅的 AI 摘要
```

它应先理解 Scope boundary、Topic structure、代表知识、关系、未知和用户进入意图，再形成少量有 provenance 的 editorial synthesis。

---

# 4. 修订后的对象模型

## 4.1 Overview identity

```text
Overview
  identity
    overview_id
    scope_ref: Space | Group | Topic | SavedPath
    canonical_role: scope_orientation

  content
    accepted_revision_ref
    working_revision_ref?

  policy
    default_generation_policy
    accepted_knowledge_only: true
    include_working_by_default: false
    projection_refresh_policy

  state
    lifecycle: active | archived
    alignment: aligned | changes_available | review_due | knowingly_diverged
    last_alignment_check_at
    alignment_basis_ref

  lineage
    previous_overview_refs[]
    successor_overview_refs[]
    origin_scope_snapshot_ref?
    revision_history
```

不再保存以下重复正文：

```text
orientation
structure
synthesis
coverage
conflicts
unknowns
locked_fragments[]
source_snapshot
```

它们分别由 Content Blocks、Projection results、Block policy、Support Map 和 Revision Basis 表达。

## 4.2 Overview Content Revision

```text
OverviewContentRevision
  revision_id
  overview_id
  revision_state: working | accepted | historical
  content_root_refs[]
  block_records[]
  support_map_ref
  scope_basis
    boundary_revision_ref
    topic_structure_revision_ref
    accepted_node_revision_refs[]
    accepted_relation_revision_refs[]
    projection_evaluated_at
  formation_basis
  change_summary
  created_by
  created_at
  previous_revision_ref?
  anchor_redirects[]
```

`scope_basis` 不是复制全部知识，而是证明这个 Overview revision 在什么知识状态上形成。

## 4.3 单一 canonical Overview

同一 `scope_ref + canonical_role` 只能有一个 active Overview。以下不产生第二个 active Overview：

- View before change；
- Archived snapshot；
- 分享 snapshot；
- AI preview；
- 另一个用户排序方式；
- 不同 Orientation / Change / Attention / Lifecycle 配置；
- 移动端与桌面布局。

它们分别是 Historical Revision、Snapshot、Proposal、View State 或 Presentation Profile。

---

# 5. Overview Block 类型

## 5.1 Editorial Block

保存 Overview 自己的、可版本化的表达：

- Boundary / Purpose；
- Orientation；
- Scope Synthesis；
- Reading Guidance；
- Transition；
- Change Interpretation；
- Historical Note。

Editorial Block 必须有 authorship、update policy、lock 和 support refs。

## 5.2 Projection Block

保存可重建规则与显示配置：

```text
ProjectionBlock
  projection_kind
  query_definition
  property_definition_refs[]
  accepted_assertions_only: true
  applicability_policy?
  missing_value_policy?
  scope_binding
  sort / group / limit
  display_mode
  empty_behavior
  last_evaluated_at
  evaluation_state
```

允许的核心 projection：

- Topic structure；
- Structure-derived readable entries（只作为无策展回退，不标为“代表知识”）；
- Key Relations；
- Related Groups；
- Conflicts / Unknowns；
- Important Questions；
- Coverage boundary；
- Recent high-impact changes；
- Continue Path；
- Source coverage；
- Group root content；
- Unplaced content in current Space。

Projection result 不成为 Overview revision 的重复正文。刷新 projection 不产生 Node、Placement、Relation 或 membership。

`Important Questions`只读取当前 Scope 内用户显式保存的 Question Knowledge，并按语义角色分组：

- **关键开放问题**：`unresolved / partially_resolved`且仍在追问，对理解当前范围重要；
- **暂时可用的回答**：`provisionally_resolved`，只在保留条件对当前 Overview 有解释价值时显示；
- **已形成的当前回答**：`resolved`，只有被 Editorial 引用或作为稳定入口时出现，不建立 FAQ 镜像正文；
- **需要复核**：`changes_available / review_due`，说明哪项依据变化，不自动写成结论失效；
- **停止追问 / 历史问题**：默认不进入 current Overview，只在 Editorial 明确保留、as-of 或 History 中出现。

Runtime Unknown 只属于本次 Answer，Persistent Gap Marker 只属于 owner 的局部缺口，Conflict 只说明不兼容主张；三者不能因数量、相关度或 AI confidence 被倾倒进 Overview。用户明确保存 / 提升后，才以 Question Knowledge identity 进入 projection。Question target、basis 与 Subquestion 只是展开内容，不作为 Overview 普通 Relation edge。

对时效、资格或高后果 Question，`需要复核`行必须同时给出：上次 adopted Resolution 的 `as_of`、发生变化的来源 / 条件、受影响 criterion 与 `查看变化`入口。若个人职业条件改变但其他标准不变，只突出该条件；禁止整条 Question 变红、把旧 Resolution 写成“错误”，或在 Overview 直接改写当前答案。

Group Overview 的 Relation Projection 必须按 standing 分层：

- **正式群关系**：只投影 maintained + current lifecycle + 当前 applicable Group Relations；review_due 保持可见并附一句变化说明；
- **跨群出口**：只投影少量当前 Scope 有解释价值的具体 Knowledge paths，文案表达“沿这条知识继续”，不画成 Group edge；
- **关系建议**：只有用户主动打开 Suggested 或当前正在比较 Group pair 时才上下文显示，不能进入稳定入口、代表关系或 Editorial prose；
- **共享核心知识观察**：只有用户主动打开 Shared Knowledge Lens、当前比较 Group pair，或该 observation 对“为何两群同时出现此知识”有直接解释价值时才显示；它列出同一 Knowledge identity 的两侧 Placements 与角色，不画成正式 Group edge、不写 Relation standing，也不进入 History；
- **观察信号**：Aggregation Signal、collapsed duplicate、fringe-only 与 exit-only 默认不显示；需要解释时进入 Candidate / relation assessment inspector；
- **历史关系**：ended / superseded / retracted / archived 只在 History 或明确 as-of context 中出现。

Projection 不按 raw path count、relation degree、AI confidence、recent 或 layout centrality排序关系。Group RelationCandidate 被采用后，下一次 Projection evaluation 才可读取新 Relation；采用前 Overview 不预演为已经成立的知识。Candidate dismissal 不删除原有 cross-group exits。共享核心 observation 随 Placement、Boundary role 和 Knowledge lifecycle 自动重算，但刷新 projection 不产生 Overview Revision，也不改变 resting Network layout。

Overview 的 Related Group row 可以提供两个分权动作：`打开知识群`改变 Reading Target；`比较`进入临时 Group Pair Comparison。后者必须携带 Overview origin、Anchor、scroll 与 focused control，不能把 Compare 做成新的 Overview Block 或在返回时回到页面顶部。

Structure / Source Projection 的 scope binding 必须保存 `direct_only | include_descendants | whole_group`。`include_descendants` 以 canonical Topic parent tree 递归求值，Knowledge 以 identity 去重但保留 exact Placement paths；Source coverage 以 Source Attachment paths 与 Evidence usage reasons 分层，不能从 Boundary 或 Binding 反推 Attachment。

Property-based Projection 必须按 stable Property / option IDs 引用 Accepted Assertions，并显示 Definition compatibility 与 index Coverage。`unknown`、`no_value`、`not_applicable`、`unset` 和 known false 不共用空白逻辑；migration / index partial 时不能把未评估对象写成“没有”。Property visibility 只改变 Overview 的当前呈现，不改 Assertions 或其他 Views。

Primary Kind / Facet / Group Profile 可以建议 projection kind 与显示顺序，但不自动生成 Editorial prose、空 Assertions 或完成度。Node-reference Property 不允许 Projection 画成正式 Relation；若系统发现可能的语义连接，只能生成 RelationCandidate；用户补全并提交后才产生 maintained Relation。

## 5.3 Reference Block

引用 Node / Anchor 时显式选择：

- Link；
- Live excerpt；
- Pinned excerpt；
- Explicit quote。

Overview 默认优先使用 Link 或短 Live excerpt；历史解释和 Decision rationale 可使用 Pinned；原话核验使用 Explicit quote。

## 5.4 Navigation Block

表达：

- 进入 Topic；
- 进入 Node / Anchor；
- 沿 Relation 探索；
- 开始 Saved Path；
- 在当前 Scope Ask。

Navigation Block 不把“常用入口”提升为知识关系。

持久化在 Overview revision 中的 Navigation Block 只允许三种策展角色：

```text
navigation_role:
  stable_start
  representative_entry
  recommended_path

target_ref
scope_ref
rationale?
created_by
```

`Continue Path / Resume` 与 `contextual next`可以显示在 Overview surface，但分别来自 Workspace state 与当前 Query / Explore run，不进入 canonical Overview content tree。最近访问、点击频率、更新时间、相似度或模型评分不能自动创建以上三种持久化角色。

## 5.5 Status Block

由系统投影：

- 当前有重要变化；
- 某些知识需要复核；
- 来源暂不可用；
- Overview 与当前结构有变化可用；
- 当前覆盖仅代表 Scope 的一部分。

Status Block 不持久化为一段永久正文；用户若要保留解释，应转为 Editorial Block 或 Historical Note。

---

# 6. 三个阅读语义区

## 6.1 Orientation

回答：

- 这是什么；
- 属于什么、不属于什么；
- 为什么值得进入；
- 当前最重要状态是什么。

默认由 1–3 个 Editorial Blocks、current Boundary Revision 的 projection 与一个可选 Status Block 组成。它不是另存的 `orientation` 字符串，也不由当前成员、最近材料或 AI Summary 反推。

## 6.2 Structure

回答：

- 由哪些 Topic / branches 构成；
- 哪些 Nodes 是用户策展的代表知识；没有策展时，哪些是按当前结构显示的可读入口；
- 主要横向关系在哪里；
- 从哪里开始读。

优先使用 Projection + Navigation，不让 AI 把动态结构写成长段落。

Group Scope 可分开显示`直接放在这个知识群`、主要 Topics 与`未归入知识群`入口；其中 root Placement 仍属于 Group，只有没有任何 active Placement 的 Knowledge 才是 Unplaced。Topic Scope 默认说`这个主题本身`，需要汇总时明确写`包含子主题`。

## 6.3 Synthesis

回答：

- 当前整体理解是什么；
- 哪些知识共同支持它；
- 哪些条件、争议和未知会改变判断；
- 最近发生了什么重要变化。

Synthesis 可以是 Editorial Blocks 与 Node References 的组合。可独立复用或证据化的 Claim 必须存在为 Node，不能只藏在 Synthesis prose。

## 6.4 三个语义区不是固定三栏

- P0 只显示 Orientation、主要 Structure 和一个继续入口；
- P1 展开代表知识、关系和范围状态；
- P2 在更新或编辑时显示 Support Map 与影响；
- P3 显示 revision basis、projection definitions、anchors 和完整 provenance。

窄屏可以单列，双镜可以把关系投影放入 Relation Lens；语义不随布局改变。

## 6.5 稳定策展、结构回退与会话引导

Overview 中的进入理由按以下优先级与标签解释：

1. 用户明确设置或接受 Diff 的 stable start / representative / recommended Path；
2. canonical Topic / Placement semantic order；
3. 没有策展时的确定性 Structure Projection fallback；
4. 当前 Workspace 的 Resume；
5. 当前 Query / Explore 的 contextual next。

前 1 项是长期策展，第 2 项是结构真相，第 3 项是可重建显示，第 4–5 项是短期语境。低一层不能反向覆盖高一层；只有用户动作或明确接受的 Diff 才能改变长期策展。没有策展时 Overview 仍完整可用，并写`按当前目录从这里开始`，不把回退伪装成用户推荐。

代表知识是 `scope + node + role + rationale` 的局部引用，不是 Node 的全局属性。取消代表角色只删除引用；Node identity、正文、Placements 与 Relations 保持不变。

---

# 7. Support Map 与“没有影子知识”

## 7.1 Overview Support

```text
OverviewSupport
  overview_anchor_ref
  support_refs[]
    node_anchor_ref?
    relation_ref?
    structure_projection_ref?
    boundary_ref?
    historical_overview_anchor_ref?
  support_role:
    summarizes
    explains_boundary
    derives_structure
    highlights_change
    identifies_unknown
    recommends_entry
  support_state:
    current
    changed
    missing
    intentionally_unlinked
```

Support Map 是 dependency / provenance，不是正式 Semantic Relation。

## 7.2 可以没有 Node support 的内容

以下可以标记 `intentionally_unlinked`：

- 用户写下的 Scope 目的；
- 主观阅读建议；
- “我为什么建立这个知识群”；
- 过渡句和解释性标题；
- 尚未形成知识的开放问题。

产品不能把“没有 Node support”一概显示成低置信。

## 7.3 不允许隐藏的 Claim

如果 Overview 一句话：

- 需要来源证据；
- 会被未来 Ask 当成结论；
- 有 Applicability；
- 可能被反驳；
- 会跨 Scope 复用；

则编辑器建议“保存为独立知识并在此引用”。用户可以暂时保留，但该段标记 `knowledge_candidate`，不会被 AI 当作已接受 Node truth。

## 7.4 Evidence 路径

```text
Overview Anchor
  → Node / Relation support
  → Evidence Connection
  → Evidence Fragment
  → Source Revision
```

这条路径允许用户从 Overview 一跳进入依据，同时保持 Evidence 的正式知识端点规则。

---

# 8. Authorship、Update Policy 与 Lock

## 8.1 Authorship

```text
authorship.origin:
  user_authored
  ai_drafted
  system_projected
  imported

authorship.last_editor:
  user | ai_assisted | system_projection
```

用户修改 AI draft 后，origin 仍可追溯，但 last editor 改变。

## 8.2 Update Policy

```text
update_policy:
  manual_only
  propose_diff
  live_reference
  auto_refresh_projection
```

- Editorial Block 默认 `manual_only` 或 `propose_diff`；
- Reference Block 根据模式选择 live / pinned；
- Projection Block 才能 `auto_refresh_projection`；
- AI 不得把普通 prose 改成 auto-refresh。

## 8.3 Lock

```text
lock_state:
  unlocked
  content_locked
  structure_locked
```

Lock 不改变 authorship，也不自动把 Block 变成 User-owned。

## 8.4 用户语言映射

| 内部组合 | 用户看到 |
|---|---|
| user_authored + manual_only | 你写的内容 |
| ai_drafted + propose_diff | AI 协助的内容 |
| system_projected + auto_refresh_projection | 根据当前知识显示 |
| any + content_locked | 已固定文字 |
| any + changes_available | 有变化可检查 |

默认阅读态不显示这些标签；编辑、Diff 与 History 时按需出现。

---

# 9. Revision、Alignment 与 Diff

## 9.1 Current / Draft / Proposed

```text
Current Overview Revision
  当前默认阅读的概览；用户直接编辑在本地保存后更新它

Draft Revision
  用户显式选择的长篇草稿，或冲突 / 恢复分支

Proposed Change
  AI 或系统根据输入变化形成的 Overview Diff

Historical Revision
  某次 Current Overview 的不可变快照
```

页面打开、Projection refresh 和 Ask 都不能把 Current 隐式换成 Proposed。AI / 系统 Diff 必须经用户确认；用户亲手编辑 Current Overview 不需要额外“采用自己的编辑”。

## 9.2 Alignment state

| 状态 | 含义 | 默认动作 |
|---|---|---|
| aligned | 依赖对象未出现需要解释的高影响变化 | 正常阅读 |
| changes_available | 有可选更新，不影响当前继续使用 | 查看变化 |
| review_due | 变化可能使重要叙事失准 | 检查受影响部分 |
| knowingly_diverged | 用户明确保留历史或不同表述 | 查看原因 / 恢复跟随 |

Alignment 不是 formation phase、freshness 或 epistemic state。

## 9.3 Overview Diff

Diff 按语义而不是纯文本排序：

1. Boundary changed；
2. Stable understanding changed；
3. Topic / Relation structure changed；
4. Conflict / Unknown changed；
5. Entry path changed；
6. Wording only；
7. Projection refresh only。

每项显示：

- 为什么变化；
- 支撑对象；
- 原文与建议；
- ownership / lock；
- 接受后影响；
- 拒绝或稍后会怎样。

## 9.4 Partial accept

用户可以逐 Block 接受、改写、拒绝或固定。接受一部分形成一个新的 Accepted revision，并记录 proposal lineage；未接受部分继续保持 proposal，不污染当前正文。

---

# 10. 输入变化的传播矩阵

| 输入变化 | Projection | Live Reference | Pinned / Quote | Editorial prose | Overview state |
|---|---|---|---|---|---|
| Topic move / rename | 自动刷新 | 不适用 | 保持 | 相关段落进入 Diff | changes_available / review_due |
| Node accepted revision | 结构候选可刷新；策展角色保持 | 跟随并标记变化 | 保持旧 revision | 有 support 的段落进入 Diff | 视影响决定 |
| Node split / merge | 重算结构候选；策展引用按 identity 处理 | 跟随 redirect | 保持历史目标 | 进入 identity-aware Diff | review_due |
| Curated target 离开 Scope / 归档 | 使用结构回退并保留旧目标去向 | 跟随 redirect，不自动换目标 | 保持历史目标 | 入口理由进入 Diff | review_due |
| Relation adopted / current Revision changed | 关系投影刷新 | 跟随 current revision 并标记变化 | 保持旧 relation_revision_id | 关系解释进入 block-level Diff | 视影响决定 |
| Relation review_due / open Challenge | 关系仍可投影并带一句说明 | 保持当前 target | 保持旧 revision | 只有重叠范围影响结论时 Diff | 可能 review_due |
| Relation ended | 当前投影退出；历史 projection 可见 | 若正文描述历史则保持 | 保持 | 写成当前判断的段落进入 Diff | 视语境决定 |
| Relation superseded / retracted | 当前投影切 successor / 退出 | 不静默换 target | 保持旧 revision | 当前解释必须 Diff | review_due |
| Relation archived | 默认投影排除 | 不自动改正文 | 保持 | 下次 refresh 默认排除 | 视影响决定 |
| Evidence / Source / Support Set changed | 通过 Binding / Support Set 投影 | 不直接改正文或 RelationRevision | 保持 | 只在结论受影响时 Diff | 可能 review_due |
| Source Attachment changed | Source coverage projection 刷新 | 不直接改正文 | 保持 | 只有材料进入理由影响叙事时 Diff | 视影响决定 |
| Group boundary changed | Scope projection 读取新 Boundary Revision | 保持 | 保持 | Orientation 必须 Diff | review_due；内容不自动迁移 |
| Orientation Profile changed | 改变编排权重 | 不变 | 不变 | 不改文字 | alignment 不变 |
| AI unavailable | 使用缓存结果 | 已保存内容可读 | 可读 | 可编辑 | 不改变 alignment |

## 10.1 低风险自动动作

允许自动发生：

- Projection re-evaluation；
- index / sort / count 刷新；
- redirect resolution；
- support state 从 current 标记为 changed；
- 显示“有变化可检查”。

不允许自动发生：

- 改写 accepted Editorial prose；
- 把新 Node 强行加入 curated “关键知识”；
- 改变 Boundary；
- 把 unknown 写成 conclusion；
- 删除用户选择的入口；
- 把一段 Overview Claim 当成 Node 保存。

---

# 11. Scope-specific Overview 合同

## 11.1 Space Overview

回答：

- 我的知识世界有哪些主要范围；
- 它们的边界与主要关系是什么；
- 哪些范围正在形成、变化或休眠；
- 从哪里进入。

默认以 Group projection 为主，editorial prose 极少。它不显示所有 Nodes、全部变化或个人生产力统计。

## 11.2 Group Overview

回答永久五问：

1. 这是什么；
2. 由什么组成；
3. 目前知道什么；
4. 哪里不确定或在变化；
5. 下一步去哪里。

Group Overview 是产品主轴，拥有最完整的 Boundary、Structure、Synthesis 与 Change contract。

它从 current Boundary Revision 解释“这个群想理解什么”，从 Placements / Topics 解释“现在包含什么”，从 Attachments / Bindings 解释“材料怎样进入并支撑它”，从 View / Ask 解释“此刻怎样观察”。四者可以暂时不一致，但必须能被分别理解。

## 11.3 Topic Overview

任意嵌套深度的 Topic 都使用同一 Overview 合同。显式 Open Topic 后，Topic Overview 作为 Topic Reading 的开头区域出现，随后在同一 scroll surface 中连续显示 direct children；它不是必须单独通过的一页。Topic Overview 只解释当前分支：

- 它在 Group 中承担什么；
- 直接子 Topic、direct Knowledge 与可选的 descendant Knowledge；
- 与同级分支的边界；
- 当前缺口和进入顺序；
- 后代 Nodes 已有的正式关系、跨分支桥接与跨群出口；
- 最值得继续打开的下一个 Topic、Node 或 Path。

它不复制 Group Orientation，也不把 Topic 变成独立 Group、Group Workspace、第五个 Sources Root 或 Relation endpoint。Topic 中 Source-only materials 通过 Attachment projection 作为`直接加入这个主题的来源`出现；默认 Projection 从 direct children 开始，`包含子主题`是显式 rollup 并标明后代路径。

Topic Opening 的 Presentation Density：

| density | 成立条件 | P0 | P1 |
|---|---|---|---|
| Bare | 无 accepted prose，或结构极少 | title、DepthTrail、真实 direct children、添加 / 继续动作 | direct Sources、空态解释 |
| Compact | 有一句局部 Orientation 或多个可辨认方向 | 1–3 句 Orientation、stable start / structure fallback、3–5 个 direct directions | representatives、descendant rollup、少量 gap / exit |
| Editorial | 有 accepted local synthesis、争议或长期阅读顺序 | Compact + 当前分支整体理解 | conditions、conflicts、Support Map、recommended Path |

没有足够 editorial synthesis 时，Structure Projection + 一句说明已经合法；空 Topic 不生成占位长文。密度从 accepted content 与 canonical structure 计算，不能因最近访问、AI confidence、formation phase 或视觉对称改变。用户直接编辑在本地持久化后更新当前 Overview revision；AI / 系统只提出 Diff。需要被独立引用、核验或建立 Relation 的 prose 必须提升为 Node。

祖先去重规则：当前 Orientation 必须能回答“这个分支相对父级新增什么”；若一段文字与父 / Group Overview 语义等价，界面使用 live reference 或建议删除重复，而不是维护两份 prose。深层 Topic 默认不显示 Group Boundary、父级主要结论、全部 relations / sources / changes；它们通过 DepthTrail、owner context 与按需 utility 可达。

Entry contract：Expand 只改变 tree state；Inspect 只改变 preview；Open Topic 把 Topic 设为 Primary Scope；Open child Knowledge / Search Anchor 直接进入目标；Up 进入结构父 Scope，Back 返回 caller，Resume 恢复 exact last-safe scene。Single-child Topic 不自动 redirect；只有通过可拒绝的 flatten Change Set 才改变结构。

## 11.4 Saved Path Overview

解释：

- 为什么按这个顺序理解；
- 路径形成时的 Scope、Revision basis 与真实 connector；
- formal relation、evidence、reference 与 manual step 为什么分别存在；
- 哪些步骤已变化；
- 怎样查看保存时版本或按当前知识重新整理。

Path steps 保持 Node / Relation identities；Overview 只保存 path-level rationale，不复制内容。current step、completed / skipped、scroll 与 Anchor 属于 PathProgress / ResumePoint；Overview 可以投影`继续第 3 步`，但该投影不会创建 Overview Revision，也不会把 Progress 写入 SavedPath identity。

Path 被 Scope 推荐时，Scope Overview 只保存 RecommendedPathReference、editorial reason 与 order；取消推荐不删除 Path、Path Overview 或任何人的 Progress。

## 11.5 Home 与 Overview 的组合

Home 可以读取：

- Space Overview Orientation；
- pinned / recent Groups；
- continue Paths；
- 一个可解释的 ResumePoint 及可选 PathProgress；
- high-impact changes；
- system status。

Home 的排序、最近和个性化状态不是 Space Overview revision 的一部分。
普通打开 Group 进入 Group Overview；只有显式`继续刚才的位置`才使用 ResumePoint。存在 active Progress 不允许动态推荐取代 stable start。

---

# 12. State Configuration 组合成一个 Overview Presentation

```text
OverviewPresentationProfile
  orientation_profile
  prioritized_roles[]
  collapsed_roles[]
  primary_action_policy
  relation_lens_weight

OverviewStateOverlay
  change_condition?
  attention_mode?
  lifecycle_state?
  boundary_condition?
  status_sentence_policy
```

Profile 与 Overlay 分开：前者依据 accepted content 选择真实信息顺序，后者只说明当前动作受什么影响。两者都不拥有第二份 Overview 正文。

## 12.1 Bare Profile

- Orientation：名称、可选 Boundary；
- Structure：已有真实内容，不用空态覆盖；
- 完全空白时主动作：`写下第一条知识`；`添加资料 / 建立主题`为安静替代；
- 禁止自动长文、空模板、空图谱和完整度。

## 12.2 Structuring Profile

- Boundary 与 coverage boundary 优先；
- 已接受结构与候选结构视觉分开；
- 少量建议进入 P2；
- 当前知识仍可直接阅读；
- deterministic structure fallback 不冒充用户策展的 stable start。

## 12.3 Oriented Profile

- Profile 本身退到背景，不显示“成熟”；
- Orientation、稳定 Structure、关键知识和 continue path 优先；
- changes / unknowns 只在相关时提升；
- 内容量、Relation 度数、访问频率与 AI confidence 不决定 Profile。

## 12.4 Change Overlay

- accepted stable Overview 保持主阅读；
- change interpretation、affected paths 与 View before change 一跳可达；
- 不要求先处理完所有 proposal；
- changes_available / review_due 只定位 affected owners，不把整个 Group 标成失效。

## 12.5 Paused Reorientation

- 最后 Current Overview Revision 与 last-safe position 优先；
- 暂停关注后的变化与内容 freshness 分开；
- 普通打开不自动把 Attention 恢复为 Normal；
- 不自动归档，不显示负面评分。

## 12.6 Archived Read-only State

- 只读 accepted revision；
- 显示归档原因、引用位置、历史 Scope 与 Restore；
- dynamic projections 默认固定到归档 snapshot，避免历史地形随当前知识漂移；
- Restore 回到同一 Overview identity，并基于 current truth 重新解析 Profile / overlays，而不是恢复旧 phase。

## 12.7 复合配置只显示一条必要说明

`oriented + review_due + paused + current + continuous` 不生成多套 Overview 或标签墙。用户看到最后稳定 Overview，以及一条合成句：

> 你曾暂停关注这个知识群；此后有一项变化会影响“担保条件”。

P0 状态说明最多一条；Lifecycle、identity transition、review_due、paused reorientation、empty bare 依次按是否改变当前动作仲裁。其余状态在 Impact / History 按需展开。

---

# 13. 创建与首次形成

## 13.1 Group creation

创建 Group 时立即创建空合法 Overview identity，但不生成正文。初始内容可以只有：

- Group name；
- optional Boundary sentence；
- three starting actions；
- empty-aware Structure projection。

## 13.2 Topic creation

Topic 创建不必立即创建长 Overview prose。第一次进入时可以显示：

- Topic title；
- current hierarchy；
- placed Nodes；
- “添加一句说明”。

用户写下说明或系统需要保存 scope-specific guidance 时，才形成 accepted Editorial Block。

首次 Open 使用 Bare density，不弹出“完善概览”向导。Topic 只有一个 child 时仍显示该 Topic 的 identity、父级作用与唯一进入动作；系统只有在它长期不承担独立 Orientation、兄弟边界或 Saved Path 作用时，才可以提出 flatten 建议，且不以内容数量单独触发。

## 13.3 Imported knowledge

导入不能按文件目录自动生成看似完整的 Overview。正确顺序：

```text
Map scopes and identities
  → save Sources / Nodes / Placements
  → evaluate structure projections
  → produce optional Overview Proposal
  → user accepts / edits
```

## 13.4 Zero-yield

来源 zero-yield 不触发 Overview prose 更新。Source coverage projection 可以反映“来源已保存但没有知识变化”，但不能以空白或失败惩罚用户。

---

# 14. Overview Editor

## 14.1 同一阅读面编辑

Overview Editor 使用同一 Knowledge Paper：

- 阅读态隐藏 Block handles；
- 编辑态显示 semantic role、authorship、update policy 与 lock；
- Projection Block 允许编辑规则和显示方式，不允许直接改投影结果；
- Reference Block 允许切换 Link / Live / Pinned / Quote；
- Status Block 只允许“查看原因”或“转为保留说明”。

## 14.2 编辑 Scope

标题明确：

```text
Editing: Overview of “AI Agent 产品设计”
```

Overview 编辑不会直接改 Node、Topic、Placement 或 Relation。若用户在 projection result 上执行结构动作，必须进入相应 Editor 与 Change Set。

## 14.3 从 prose 提升知识

选中一段 Overview prose 可：

- `保存为独立知识`；
- 选择 Node type；
- 建立 Node + Anchor；
- 在原位置保留 Link / Live / Pinned；
- 迁移 support refs；
- 预览 Placements、Relations 与 Answer impact。

这不是默认自动行为。

## 14.4 AI 协助

允许：

- 改写一个选中 Block；
- 根据指定 Nodes 形成 synthesis Proposal；
- 解释变化并生成 Diff；
- 建议缺失 support；
- 建议把独立 Claim 保存为 Node；
- 生成可编辑 reading guidance。

禁止：

- 一键重写整个 Overview 后直接替换；
- 使用 Working / rejected / external knowledge 而不说明；
- 因语言更流畅移除条件、unknown 或 conflict；
- 让引用和 support 在改写后静默丢失。

---

# 15. Ask、Search、Explore 与 Overview

## 15.1 Ask for Overview

用户问“概览一下这个知识群”时：

- 默认回答基于 Current Overview + Current Nodes / Relations；
- Query Run 分别保存用户请求的 Scope、系统实际采用的 Expansion 与真正支撑 Claims 的对象；
- 如果 Overview alignment 不是 aligned，回答说明“当前概览有变化可检查”；
- Answer Claim 仍回到 Node Anchor / Relation / Evidence，并使用 Overview 仅作 orientation；
- Overview Editorial prose 若没有独立 Node support，只能作为 Scope purpose / user statement，不得冒充 factual evidence；
- 回答不会自动成为 Overview revision。

保存动作分开：

- 保存回答快照；
- 保存为可编辑的综合 Knowledge Draft；
- 建议更新 Overview；
- 保存为 Path。

保存回答只创建 Saved Answer / Knowledge Snapshot，默认不参与未来当前事实查询；保存为 Synthesis 按 Claims 检查 identity、Applicability 与 support；建议更新 Overview 只产生 Semantic Diff。三者不能由一个 Save 按钮或整段 Accept all 合并。

## 15.2 Search

Search 命中 Overview 时显示：

```text
知识群概览 · AI Agent 产品设计
“……命中内容……”
位于：当前整体理解
```

打开后恢复 Overview + Anchor + Scope + reading position。结果不显示为普通 Knowledge Node。

## 15.3 Explore

Overview Structure 中的关系投影打开 Group Map / Local Graph，但不会因 Overview 中并列展示两个 Nodes 就创建边。

## 15.4 Query Route

AI Answer 可以经过 Overview 作为 scope orientation step，但 Overview prose 不能代替 Claim evidence。可靠 Route 继续指向 Nodes、Relations 与 Evidence；否则显示 Used Knowledge List。Query overlay 属于具体 Run，清除后不改变 Overview Projection、Support Map 或 canonical graph。

---

# 16. Scope transformation

## 16.1 Topic Promotion

Topic 成为 Group 时：

- 原 Topic Overview 保留在 Gateway history；
- 新 Group 建立新的 Overview identity；
- 可以从原 Topic accepted revision 派生 initial proposal；
- lineage 记录 `origin_scope_snapshot_ref`；
- Projection scope 重新绑定到新 Group；
- 用户 prose 不因复制而同时 live 编辑两处。

## 16.2 Group Split

不能把旧 Overview 按段落机械切成两份。预览：

- 新 boundaries；
- Topic / Placement mapping；
- 哪些 Editorial Blocks 仍适用；
- 哪些 Blocks 需要重写或固定为历史；
- Node / Relation support 分配；
- old Overview redirect / archive。

## 16.3 Group Merge

先选择 canonical Group identity，再处理 Overview：

- 两个 Current Overviews 并列比较；
- Boundary conflicts 优先；
- Structure projections 从 merged Placements 重建；
- 重复 prose 不自动合并；
- 支撑相同但表述不同可以保留为 proposal alternatives；
- 旧 Overview URLs 进入 historical redirect。

## 16.4 Absorb

被吸收 Group 的 Overview 固定为 historical snapshot；目标 Group Overview 只接收一个可编辑 proposal，不直接追加整篇历史正文。

## 16.5 Saved Path changed

Path step redirect 自动解析；路径 rationale 保持历史。若当前路径已无法复现，Overview 显示 changed steps 与可选 repair，不静默删除。

---

# 17. Failure、offline 与大规模

## 17.1 AI unavailable

- Current Overview 可读；
- manual editing 可用；
- Projection 使用本地 canonical store；
- Support Map 与 History 可查看；
- AI rewrite / synthesis / change explanation 延后；
- 不显示一篇空白或“稍后再来”的聊天壳。

## 17.2 Index unavailable

- cached Current content 与 hierarchy 可读；
- rule projections标记 incomplete；
- 不把 incomplete projection 当成“没有知识”；
- index rebuild 不改变 Overview revision。

## 17.3 Missing support

- Overview prose 保留；
- support state 变为 missing；
- 说明是 Node archived、Source unavailable、redirect failed 还是权限问题；
- 不因 support 暂不可用删除用户正文。

## 17.4 Large Group

10,000 Nodes 的 Group Overview 不尝试展示全部：

- Structure 以 Topic / curated representative Nodes 为主；
- Projection 有 limit + Show more + Search；
- 关键关系遵守 display budget；
- coverage 解释代表范围和缺口，不宣称全量总结；
- List Equivalent 与 keyboard navigation 可用。

## 17.5 No relations / no sources

- 没有关系时不显示空图；
- 没有外部 Source 的 user-authored Group 仍有合法 Overview；
- status 说明形成方式，不将用户综合标成证据不足的失败。

---

# 18. Import、export 与 backup

## 18.1 Import

导入映射至少区分：

- ordinary note → Node candidate；
- folder index / MOC → Overview candidate；
- database view / query → Projection / View candidate；
- copied summary → Editorial Block candidate；
- embedded note → Reference mode candidate。

系统不得把所有 index pages 自动认定为 canonical Overview。

## 18.2 Knowledge Package

完整导出包含：

```text
Overview identity and scope binding
accepted / working / historical revisions
content tree and anchors
canonical navigation roles, targets and rationale
block authorship / update policy / lock
projection definitions and last results
support map
scope basis and lineage
redirects
human-readable Markdown / HTML rendering
```

## 18.3 阅读导出

Markdown / HTML / PDF 可以物化当前 projection result 以便阅读，但必须标注生成时间和 Scope snapshot；这不是可恢复 Knowledge Package。

## 18.4 Restore

Restore 后验证：

- same overview_id；
- same scope_ref；
- accepted revision hash；
- projection definitions；
- stable start / representative / recommended Path roles and rationale；
- support refs；
- anchor resolution；
- historical redirects；
- readable fallback。

---

# 19. 产品指标与反指标

## 19.1 核心指标

- **Scope Orientation Success**：用户能否快速说清这个 Scope 是什么、不是什么；
- **Structure Findability**：能否从 Overview 在少量进入动作内到达目标 Topic / Node；
- **Overview-to-Evidence Continuity**：从概括能否回到支撑 Node 与 Evidence，并返回原位置；
- **Support Traceability**：重要 Synthesis Blocks 是否有可解释 support；
- **Change Comprehension**：用户能否说清什么变了、什么没变、是否需要决定；
- **Editorial Preservation**：用户正文和 locks 在 AI / structure updates 后是否保持；
- **Projection Fidelity**：动态结果是否与 canonical structure 一致；
- **Entry Provenance Comprehension**：用户能否区分稳定策展、结构回退、Resume 与 contextual recommendation；
- **Curation Preservation**：内容、结构或使用行为变化后，稳定入口是否只按合同演化而不被排名偷换；
- **Overview Recovery Success**：Paused / Archived / restored Scope 能否恢复最后稳定理解；
- **Shadow Knowledge Rate**：被 Ask 当作结论但不存在为 Node / Relation 的 Overview Claims 比例；
- **False Completeness Rate**：用户是否把部分覆盖误认为完整领域总结。

## 19.2 反指标

- Overview 越长越好；
- AI 每次进入都生成新摘要；
- 每个 Topic 都必须有长 Overview；
- Overview 引用越多越好；
- 结构变化后 prose 自动更新率；
- 知识完整度百分比；
- 用户接受 AI Diff 的比例本身；
- 所有 Scope 使用同一模板的比例。

---

# 20. 场景压力测试

## 20.1 Bare：空的“认知科学”

只有名称时 Overview 成立：显示边界可选项、写知识 / 建主题 / 加来源和已有零内容状态。AI 不生成认知科学长篇介绍。

## 20.2 Structuring：材料集中在记忆研究

Structure Projection 显示已出现的“记忆”分支；Coverage 说明目前不能代表整个认知科学。用户可以写 Boundary，不被完成度催促。

## 20.3 Oriented：“AI Agent 产品设计”

Orientation 是用户认可的产品范围；Structure 动态显示 Topics；Synthesis 引用已接受 Decisions / Principles；Ask 从概括回到 Nodes 和 Evidence。

## 20.4 Oriented + Change Overlay：产品方向从 Cognitive OS 收敛为知识库

旧 Current Overview 保留；新方向形成 Proposed Diff；Boundary、关键 Decision 和受影响 Paths 优先；用户可部分接受并查看变化前版本。

## 20.5 Oriented + Paused：“法国租房”

最后稳定 Overview 与上次焦点优先；休眠后来源变化显示为影响，不把整个 Overview 标成过期，也不要求先清 Review。

## 20.6 Topic Promotion：“长期记忆系统”

原 Topic Overview 进入 Gateway history；新 Group 使用新的 Overview identity 和派生 proposal；两处不保持 live prose 镜像。

## 20.7 Long Group / no relations

10,000 Nodes 但没有足够正式关系时，Overview 仍通过 Topic structure、representative Nodes、Search 和 List 成立；不生成假 Atlas。

## 20.8 User-authored only

没有 Source 的原创知识群仍可拥有 user-authored Overview；系统显示形成方式，不伪造 citations，也不把它整体归为 low confidence。

## 20.9 Curated entry changed

用户设置的代表 Node 离开当前 Topic 时，Overview 保留原入口历史与 redirect，回退到 canonical structure，并显示一处需要检查的入口变化。系统不能把最近最常打开或 embedding 最相似的 Node 自动补成新的代表知识。

## 20.10 Boundary 澄清但内容未调整

用户把`研究法国生活`澄清为`理解法国长期居住中的住房与行政规则`。Overview 立即读取新的 Boundary Revision，同时把尚未决定去向的旅行 Knowledge 标为可解释 boundary tension；它们保持原 Placement，不被静默删除、移动或排除。

## 20.11 Topic Source-only 与 descendant projection

深层 Topic 只有三份 directly attached Sources、没有 Knowledge。Topic Overview 仍以简短说明 + 来源入口成立；父 Topic 打开`包含子主题`后可以看到材料覆盖，但明确它来自后代路径，不把 Source 计作代表 Knowledge 或证据充分。

---

# 21. 可验证验收标准

## 21.1 单一正文真相

**Given** Overview 同时显示 Orientation、Structure 与 Synthesis  
**When** 用户编辑一个 Synthesis Block  
**Then**：

- 本地保存后只改变同一 Current Overview content tree；
- 不存在另一个 `synthesis` 字段需要同步；
- 按编辑会话形成新 Current revision，不要求额外提交；
- Anchor、support 与 History 保留；
- 其他语义区不被整篇重生成。

## 21.2 Projection 与 prose 分离

**Given** 一个 Topic 被移动  
**When** Group Overview 打开  
**Then**：

- Structure Projection 自动反映新位置；
- 用户写的边界与解释不被改写；
- 相关 prose 显示 changes available；
- Topic move 不产生新的 Overview revision，除非用户接受 prose Diff；
- Undo 后 projection 与 support 一起恢复。

## 21.3 三轴 governance

**Given** 用户锁定一段最初由 AI 起草的文字  
**When** 支撑 Nodes 变化  
**Then**：

- origin 仍是 ai_drafted；
- lock 仍是 content_locked；
- accepted text 不变；
- alignment 显示变化；
- 用户可以比较、解锁或保留不同表述。

## 21.4 Ask 不改 Overview

**Given** 用户请求“概览这个知识群”  
**When** AI 返回一个更流畅的新总结  
**Then**：

- Answer 是 Query Result；
- Current Overview 不变；
- 用户可以保存 Answer Snapshot、把选中 Claim 形成 Node、保存 Path 或建议更新 Overview；
- 只有最后一种进入 Overview Diff；
- 保存 Answer 默认不让其进入当前事实检索；
- 关闭 Answer 后没有知识写入。

## 21.5 没有影子 Claim

**Given** Overview prose 中出现一个需要独立 Evidence 的判断  
**When** 用户保存  
**Then**：

- 产品建议保存为 Node；
- 用户可以暂时保留并标记 knowledge candidate；
- Ask 不把未形成 Node 的句子伪装成 accepted Claim；
- Evidence 仍通过 Node / Relation endpoint；
- 未来可无损提升并在原处保留引用。

## 21.6 Orientation Profile 不复制 identity

**Given** Group 因 accepted Orientation 与有效 stable start 从 Structuring 重新解析为 Oriented  
**When** Overview 默认顺序变化  
**Then**：

- overview_id 不变；
- accepted revision 不因 Profile refresh 自动新增；
- 只改变 Presentation Profile；
- Selection、Anchors、Saved Path 与 Back 保留；
- 用户编辑仍在原 Blocks 上。

## 21.7 Change Overlay 保留稳定理解

**Given** 新知识影响 Group Boundary  
**When** Overview 进入 review_due  
**Then**：

- 当前 Current Overview 仍可阅读；
- Proposed Diff 与支撑对象可检查；
- View before change 一跳可达；
- 用户可部分接受；
- historical revision 永不改写。

## 21.8 Search 精确进入

**Given** Search 命中 Topic Overview 中部的 reading guidance  
**When** 用户打开并返回  
**Then**：

- 结果类型显示“主题概览”；
- 恢复 Overview + Anchor + Scope；
- 不创建 Node identity；
- Back 返回 Search；
- Anchor moved 后通过 redirect 或明确修复。

## 21.9 Topic Promotion

**Given** Topic 有 Current Overview Revision  
**When** 它成为 Group  
**Then**：

- 原 Topic Overview 进入 Gateway history；
- 新 Group 获得新 Overview identity；
- initial proposal 保留 provenance；
- 不形成两份 live prose；
- old URL、Saved Path 与 historical Ask 可解释。

## 21.10 AI unavailable

**Given** AI 与 semantic index 都不可用  
**When** 用户进入 Oriented Group  
**Then**：

- current Overview、cached structure、manual navigation 和 History 可用；
- incomplete projection 说明原因；
- 用户可以手工编辑 Current Overview；Edit Buffer 由 Recovery Checkpoint 保护，在 composition 结束且到达安全边界时以 Direct Edit Commit 更新 Current Overview Revision，不需要`完成并采用`；
- sync、index 与 Projection lag 不回滚 Editorial current；Projection 只能读取已提交 Revision，不能读取活跃 Buffer / Recovery；
- AI suggestions 延后但不阻塞；
- 不丢失 support 或 Anchors。

## 21.11 Export / restore

**Given** Overview 含 user prose、live projection、pinned reference 和 locks  
**When** Knowledge Package 导出并恢复  
**Then**：

- identity、scope、accepted revision、projection rule、support map 与 locks 等价；
- pinned revision 不被转成 live；
- human-readable export 可独立阅读；
- restore 后 Anchor 可解析；
- 校验失败不显示成功。

## 21.12 策展入口不被动态排名偷换

**Given** Scope 有一个 user-curated stable start，同时存在 Resume、结构回退与 AI contextual next  
**When** 最近访问、相似度或被策展对象的 Scope membership 发生变化  
**Then**：

- 每个入口能解释自己的来源；
- Resume 与 AI 建议不改变 canonical Navigation Block；
- curated target 离开 Scope 时保留 redirect 与历史理由；
- Overview 使用确定性 structure fallback 并进入 review_due；
- 系统不自动选择另一个“代表知识”。

## 21.13 Boundary revision 不迁移内容

**Given** Group 当前内容部分超出新 Boundary  
**When** 用户保存 Boundary clarification  
**Then** Overview Orientation 读取新 revision，内容保持原位并显示 bounded tension；任何 Placement / Topic / Attachment 变化都需要独立 Change Set。

## 21.14 Topic direct / descendants projection

**Given** Topic 有 direct Knowledge、两个 descendant branches 和一个跨分支重复 Knowledge  
**When** Overview 分别评估 direct 与 include-descendants projection  
**Then** 范围标签、计数与进入路径可解释；重复 identity 只呈现一次但保留 paths；ancestor 不获得镜像 Placement。

## 21.15 Source coverage role fidelity

**Given** Group 同时有 direct attached Source、used Source 与 shared-reference Source  
**When** Overview 显示来源覆盖  
**Then** 三种原因分层；Source-only 不被写成 Knowledge support，Evidence coverage 不因 Attachment 数量提高，打开可回到 exact Topic path 或 Binding target。

## 21.16 Expand、Inspect、Open 与 direct child open 分权

**Given** Tree 中一个 Topic 同时拥有 children、local Overview 与 direct Knowledge  
**When** 用户依次 disclosure Expand、keyboard Focus、Inspect、Enter Open Topic 与点击 Knowledge row  
**Then** 只有 Enter / explicit Open 改变 Primary Scope 并写 ReturnStack；Expand 只改变 tree state，Focus / Inspect 只改变 cue / preview，Knowledge row 直接进入 Knowledge，不先经过 Topic top。

## 21.17 Topic opening density 诚实退化

**Given** 同一 Topic 从 empty 逐渐形成多个 branches、accepted synthesis，之后又删除 editorial prose  
**When** 依次打开  
**Then** density 从 Bare → Compact → Editorial → Compact 自然变化；topic_id、overview_id、URL、DepthTrail 与 accepted History 不复制；空态不生成 AI prose，删除 synthesis 不删除结构或 Knowledge。

## 21.18 递归 Overview 不复制祖先

**Given** Group → Topic A → Topic B → Topic C 形成四层路径，且父级已经解释 Group Boundary 与整体判断  
**When** 打开 Topic C  
**Then** P0 只说明 C 在 B 中的作用、direct children 与下一入口；A / B / Group 保留在 DepthTrail 与按需 context；Boundary、父级 synthesis、全部 relations / sources / changes 不重复出现，screen reader reading order 也不朗读四份等价开场。

## 21.19 Deep target 与 single-child 不被错误重定向

**Given** Search 命中 single-child Topic 内某 Knowledge 的 Anchor，另有一个 active Resume 停在同 Topic 的关系 Inspector  
**When** 分别打开 Search result、普通 Open Topic 与 Resume  
**Then** Search 直达 Anchor，Topic Open 进入 Bare / Compact 开场，Resume 恢复 exact Inspector scene；三者不互相改写。Single-child 不自动 redirect；只有用户接受 flatten Change Set 才改变结构，并保留 lineage 与旧路径。

---

# 22. 研究依据与产品推论

## 22.1 Anytype：Query 与 Collection 必须分开

Anytype 官方文档明确区分：Query 是对整个 Graph 的动态过滤，不存储匹配 Objects；Collection 则由用户手工加入 Objects。[Queries](https://doc.anytype.io/anytype-docs/getting-started/sets) · [Collections](https://doc.anytype.io/anytype-docs/getting-started/sets/collections)

本产品据此把自动更新的 Structure / Coverage / Changes 放入 Projection Block，把用户决定的叙事和精选入口放入可版本化 Editorial / Reference Blocks。

## 22.2 Obsidian Bases：View 配置与 Markdown 内容分开

Obsidian Bases 从本地 Markdown 文件及 properties 读取数据，Base 保存视图配置；同一 Base 可以有不同 filter、sort、group 和 layout，并嵌入普通笔记。[Introduction to Bases](https://obsidian.md/help/bases) · [Views](https://obsidian.md/help/bases/views)

本产品据此不把 Projection result 复制为 Overview prose，也不让不同视觉布局产生不同知识 identity。

## 22.3 Capacities：规则视图与人工策展回答不同问题

Capacities 官方文档把 Query 定义为会随匹配内容自动更新的 saved filter，把 Collection 定义为人工决定 membership 的集合；Queries 还可以嵌入对象以形成 context-aware dashboard。[Queries](https://docs.capacities.io/reference/queries) · [Queries vs. Collections](https://docs.capacities.io/faq/editing/queries-vs-collections)

本产品据此要求 Projection、curated entry 和 Editorial narrative 显式分层，而不是把“自动推荐的关键知识”伪装成用户已经策展的入口。

## 22.4 Notion Wiki：Home 可编辑，内容验证有明确 owner 与过期

Notion Wiki 的 Home 允许用户添加普通 Blocks 和组织 Pages；Verified pages 则把 owner、验证状态和可选过期时间分开。[Wikis & verified pages](https://www.notion.com/help/wikis-and-verified-pages)

本产品不照搬团队 owner 流程，但吸收两个原则：Scope landing 可以同时包含编辑性内容与动态页面入口；“当前可依赖”必须有显式维护状态，不能只凭页面存在或 AI 最近生成。

## 22.5 Heptabase：结构、内容与快照不是同一版本

Heptabase 官方版本历史说明，恢复 whiteboard version 只恢复布局、sections、text elements、card positions 等，Card content 需要使用各自版本历史；其公开分享也区分 live link 与固定 snapshot。[Version history](https://support.heptabase.com/en/articles/10448124-how-to-restore-cards-and-whiteboards-from-version-history) · [Live link vs snapshot](https://support.heptabase.com/en/articles/12121546-how-do-i-publish-whiteboards-with-a-public-link)

本产品据此把 Overview layout / projection、Node content revision 与 historical Overview snapshot 分开，避免“恢复地图”意外回滚知识或“查看旧概览”展示当前动态结构。

## 22.6 Materialized view 的启发边界

PostgreSQL 官方文档说明 materialized view 会持久化查询结果，但数据不一定是最新的，需要显式 refresh。[Materialized Views](https://www.postgresql.org/docs/current/rules-materializedviews.html)

这不是技术选型依据，但清楚说明了产品语义：一个被保存的整体解释与一个实时查询结果不是同一件事。Overview Editorial Revision 可以稳定、可回看；Projection 可以刷新并标明评估时间。

## 22.7 Tana：任意层级节点可以成为当前焦点

Tana 官方说明任意 node 都可以 zoom 成 full page，breadcrumbs 持续显示其层级位置；expand / collapse 又可以只改变当前上下文，而不要求进入新的文档。[Outline editor](https://outliner.tana.inc/learn/features/outline-editor) · [Navigation](https://outliner.tana.inc/learn/features/navigation)

产品推论：Topic 可以是可打开的阅读 Scope，但 Expand 与 Open 必须分权；否则用户无法预测一次点击是整理树还是改变主阅读。

## 22.8 Docusaurus：介绍内容与直接子项索引可以共存

Docusaurus category link 可以引向介绍页面；generated index 投影 direct children，也可以嵌入普通文档页面。[Sidebar items](https://docusaurus.io/docs/sidebar/items)

产品推论：Topic 不必在纯目录与长文章之间二选一。Compact / Editorial 开场可以与真实 direct structure 连续存在；Projection 不需要复制成手写目录。

## 22.9 Wikipedia：开场应反映正文而不是创造影子内容

Wikipedia Lead guideline要求 lead 能独立提供简洁概览、按正文的重要性分配权重，重要内容不应只存在于 lead 而不在正文中。[Lead section](https://en.wikipedia.org/wiki/Wikipedia:Manual_of_Style/Lead_section)

产品推论：Editorial Topic Overview 可以提供局部方向，但独立 Claim 仍应提升为 Knowledge；概览不应成为另一个不可核验知识层。

## 22.10 Apple：Disclosure 是展开层级，不等于打开内容

Apple HIG 把 disclosure controls 用于逐步显示相关细节，把 outline view 的 disclosure triangle 用于展开 nested children；层级选择与内容呈现仍需要清楚反馈。[Disclosure controls](https://developer.apple.com/design/human-interface-guidelines/disclosure-controls) · [Outline views](https://developer.apple.com/design/human-interface-guidelines/outline-views)

产品推论：Topic row 必须有可预测的 Expand 与 Open 语法；使用单击区域、键盘 Enter 或明确动作都可以，但不能让同一 control 随内容状态随机改变后果。

## 22.11 推论边界

上述工具证明动态视图、人工策展、可版本化内容、验证状态、层级聚焦、category introduction 与 direct-child projection 是成熟产品中的真实分工问题；它们不证明本合同的具体 Overview 组成或 Bare / Compact / Editorial 密度已经通过个人知识工作者的真实使用测试。递归 Topic 是否仍显得重复、single-child flatten 触发是否克制、Support Map 可理解性、Diff 负担和 Shadow Claim 检测仍需要以后实证验证。

---

# 23. 对后续视觉设计的约束

本合同不授权开始原型。未来视觉设计必须证明：

1. Orientation、Structure、Synthesis 是连续阅读语义，不是三张平权卡片；
2. Editorial、Projection、Reference、Navigation 与 Status 在阅读态自然共存，编辑态又可区分；
3. Projection refresh 不被误解为 AI 修改用户文字；
4. Authorship、update policy、lock 和 alignment 不压成徽章墙；
5. Bare Overview 可以内容很少但仍完整，不用空图或 AI 长文装饰；
6. Oriented Overview 保持低噪声；Change Overlay 同时展示稳定理解与变化；
7. Search 命中 Overview Anchor 后，类型、Scope、正文位置和返回路径清楚；
8. Overview → Node / Relation → Evidence → Back 是可逆链路；
9. 一个需要独立知识 identity 的 Overview Claim 可以自然提升为 Node；
10. Topic Promotion、Group Split / Merge 的 Overview lineage 可判断；
11. AI unavailable、projection incomplete、missing support 和 knowingly diverged 有可恢复状态；
12. 方向 3 继续承担层级、连续阅读和 Overview 主轴，方向 2 只在相关时展示 Structure / Relation projection，不把 Overview 固定切成仪表盘。
13. Topic Expand、Inspect、Open、direct child open、deep link、Up、Back 与 Resume 使用可预测且不同的交互后果。
14. Bare、Compact 与 Editorial 在同一连续 Topic Reading 中自然退化，不形成三种页面模板或中转大厅。
15. 四层以上 Topic 路径不会逐层重复 Group Boundary、父级 synthesis、全部关系、来源和变化提示。
16. Overview 能区分关键 Question Knowledge、一次 Ask 的 Runtime Unknown、局部 Gap 与 Conflict，不形成待办清单。
17. `已有部分进展 / 暂时可用 / 已充分回答`与`正在 / 暂停 / 停止追问`能用一条组合人话呈现，不形成状态徽章墙。
18. 从 Overview Question → current Resolution → exact basis / Evidence → Back 可以恢复原 Overview Anchor、projection filter 与 focus。

---

# 结论

Overview 的价值不是“替用户把所有内容总结一遍”，而是让一个知识范围拥有稳定、可维护、可进入的整体方向。

它必须同时容纳两种不同时间语义：

> **Editorial Revision 保存用户当前认可的整体理解；Projection 保存根据当前知识实时重建的结构与状态。前者通过 Diff 演化，后者按规则刷新，两者通过 Support Map 相连，但绝不互相冒充。**

由此，Overview 不会成为第二份 Node 正文、不会成为动态查询的截图、不会成为 AI 打开即重写的摘要，也不会成为隐藏事实的影子数据库。它是从 Scope 进入知识网络的编辑性入口：先建立方向，再看见结构，再理解综合，最后回到 Nodes、Relations 与 Evidence。
