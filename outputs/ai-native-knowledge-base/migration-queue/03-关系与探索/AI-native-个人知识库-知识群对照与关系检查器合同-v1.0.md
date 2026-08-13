# AI-native 个人知识库

## 知识群对照与关系检查器合同 v1.0 — Group Pair Comparison、Relation Inspector 与安全写回

> 文档日期：2026-08-10  
> 文档性质：终局产品本体与交互责任合同；不是页面线框、视觉稿、原型、开发排期或 MVP 说明  
> 上位真相源：`AI-native-个人知识库-终局产品设计文档-v4.0.md`  
> 类型真相源：`AI-native-个人知识库-群级关系类型注册表与语义互斥合同-v1.0.md`  
> 底层路径类型真相源：`AI-native-个人知识库-知识关系类型注册表与跨层语义合同-v1.0.md`；Paths 中 Knowledge connectors 必须解析到其 25-type definition revision，并把 Evidence / Reference / Answer / Transition / Question state 排除在 formal Relation 之外  
> 聚合资格：`AI-native-个人知识库-群级关系聚合门槛与支撑充分性合同-v1.0.md`  
> 生命周期：`AI-native-个人知识库-关系陈述生命周期与网络可信性合同-v1.0.md`  
> 边界真相：`AI-native-个人知识库-知识群边界与跨群架构合同-v1.0.md`  
> 查询真相：`AI-native-个人知识库-AI查询与知识回答合同-v1.0.md`  
> 表面与返回：`AI-native-个人知识库-交互架构与设计系统-v1.0.md`、`AI-native-个人知识库-知识群工作区与双镜连续性合同-v1.0.md`  
> 视觉方向：方向 3 的层级阅读 + 方向 2 的按需关系空间；本文只冻结产品责任，不授权制作原型  
> 第二真实夹具证明：`AI-native-个人知识库-第二真实端到端夹具-概念学习、多语境复用与群关系-v1.0.md`已冻结一个 complete pair：2 条 same-pair Current Relations（foundation + method）、3 条 Shared Knowledge observations、4 条去重 Paths、1 条 rejected complements Candidate、research challenge、History 与 Knowledge Anchor exact return。未来 Pair 设计必须完整承载这组真实长内容，不能只画“两张卡 + 一条边”  

---

# 0. 执行结论

类型注册表解决“两个知识群究竟以什么方式相连”，但用户仍需要一个具体、连续、可信的地方回答：

1. 这两个知识群分别想理解什么；
2. 它们当前有哪些正式关系；
3. 为什么这些关系成立；
4. 是否只是共享同一知识、存在具体跨群路径，或尚未形成群关系；
5. 两者在什么范围内互补、对照、挑战、限制或演化；
6. 如果关系不准确，怎样修改而不破坏历史；
7. 如果还没有正式关系，怎样继续探索或提出一条完整建议；
8. 看完以后怎样回到原来的知识、图谱位置或问题。

本合同冻结四十六项产品决定。

1. **Group Pair Comparison 是显式 Compare 行为，不是普通 Group open。**
2. **它是 Workspace State，不是第十五类 Primary Product Resource。**
3. **比较对象固定为两个 Groups。** 多于两个 Groups 使用 Ask compare、Saved View 或逐对比较，不把 surface 扩展成矩阵产品。
4. **Pair identity 与方向分开。** Pair 使用规范化 unordered key；每条 directed Relation 保留自己的 from / to。
5. **进入比较不会创建 Relation、Candidate、Observation、Saved Answer 或 Path。**
6. **比较默认使用最新 current Group Boundary Revision。** 用户可显式切换 as-of / historical comparison。
7. **两个 Group 的 Overview、Boundary 与当前内容覆盖必须分开。** 不能拿现有内容自动替代 Boundary。
8. **Current formal Relations 是第一层事实。** 只读取 maintained + lifecycle current + applicable Group Relations。
9. **同 pair 可有多条不同正式关系。** Bundle 只折叠呈现，不合并 identity、statement、type、Revision 或 lifecycle。
10. **Shared Knowledge 是派生观察。** 它不进入 Current / Suggested / History，也不拥有 Adopt / End / Retract。
11. **Cross-group exits 是可走路径，不是群级边。**
12. **Aggregation Signals 默认隐藏。** 只有解释 Candidate 资格或用户主动查看“为什么尚未形成关系”时出现。
13. **Suggested 与 Current 分层。** Candidate 不能因处于 Compare surface 而显得已经成立。
14. **History 默认不与 Current 混排。** 只有 relation impact、as-of 或用户主动打开时出现。
15. **用户先看到完整中文关系句。** enum、revision ID、gate、unit 与 policy 进入更深披露。
16. **类型选择意图优先。** 先选择范围、作用、协同、比较、限制或演化，再处理相邻类型。
17. **TypeValidationReport 不写入。** 它只能解释缺失字段、不一致和 alternatives。
18. **`influences`不是快捷兜底。** 缺少机制、受影响维度或更窄类型排除理由时不能提交。
19. **`challenges`不等于谁是错的。** 它保存挑战方向、对象、机制与适用范围，不改变被挑战对象 lifecycle。
20. **`partially_overlaps_with`不等于共享几条知识。** 必须比较两个 Boundary 是否部分相交且互不包含。
21. **`scope_within`不形成 Subgroup。** 它只表达 scope containment，不改变 ownership、Placement 或删除行为。
22. **`evolved_from`区分 direct / indirect。** indirect 默认展开为 lineage path，不伪装成直接邻接。
23. **Ask in Pair 使用两个 Groups 作为 Requested Scope。** 实际覆盖、排除、索引缺口与使用对象必须可检查。
24. **AI 回答不建立关系。** “建立关系建议”是显式独立动作。
25. **从回答保存 Candidate 必须复用本次比较的 type / direction / Applicability / support 解释。** 不重新生成另一套含义。
26. **从 Current Relation 修改语义时产生 RelationRevision 或 successor。** 不原地改历史。
27. **仅更换 Evidence / Support 不制造语义 Revision。**
28. **Registry definition 更新只产生 Migration Review。** 不静默批量改型。
29. **比较内容有一致性快照。** 一次阅读不会因后台刷新把左、右、关系和 observation 更新到不同时间。
30. **新变化先显示“比较内容已变化”。** 用户可以刷新、保持当前快照或查看差异。
31. **保存 Comparison Snapshot 是可选支持记录。** 只有用户明确保存或导出时产生，不成为新知识。
32. **普通关闭丢弃临时筛选与排序，但不丢原现场。**
33. **Back 恢复 exact origin。** 包括 Graph viewport、selected edge、Reading Anchor、Ask Claim 或 List filter。
34. **Pair Compare 不写 Recent 两次。** 它记录一次 compare event；只有真正 Open endpoint 才记录对应对象 open。
35. **桌面可以呈现双镜，但只有一个 Primary。** 默认是可读的 Pair Comparison，Relation Space 是按需 Companion。
36. **窄屏使用顺序表达，不删责任。** 两群、关系、共同知识、路径、建议、依据与返回全部可达。
37. **Graph 与 List 共用同一 inventory。** 不允许图上有关系、列表没有，或反之。
38. **视觉不为十一种类型创建十一种颜色。** 精确语义由完整句、方向、标签与 Inspector 承担。
39. **Shared Knowledge Lens 不改变 resting layout。** 开关前后 Group / Relation positions 保持稳定。
40. **Comparison 允许没有关系。** 合法结果可以是“没有正式关系，但有两条可探索路径”，或“当前没有可确认联系”。
41. **Partial index 不冒充无关系。** 明确哪些 Group / Knowledge / Source 尚未评估。
42. **AI unavailable 不阻止人工比较。** Boundary、Overview、Current Relations、Shared Knowledge identity、exits 与 History 仍可读。
43. **Graph unavailable 自动退到 List，不中断比较。**
44. **离线使用本地 current snapshot。** 不把缺少远端更新写成没有关系。
45. **键盘、屏幕阅读器与 200% zoom 是同一产品。** 必须完成选关系、看依据、换端点、建 Candidate 与返回。
46. **本文不授权原型。** 只有产品本体继续收敛并经用户确认后，才进入视觉探索。

---

# 1. 当前规格留下的九个产品缺口

## 1.1 Compare 只有动作名，没有 owner

现有文档区分 Focus、Inspect、Open 与 Compare，却没有决定 Compare 属于哪个 surface、保存什么状态、怎样返回。实现很容易把它做成：

- 一次性弹窗；
- 两张 Overview 卡片；
- 一张只高亮两群的图；
- 一次 AI 回答；
- 或永久新页面。

这些答案不等价。

## 1.2 “它们有什么关系”可能混合六种 standing

同一句问题可能返回：

- Current formal Relation；
- shared-core observation；
- cross-group exit；
- Aggregation Signal；
- RelationCandidate；
- historical Relation。

如果同屏没有责任顺序，用户会把“看得到”理解成“已经建立”。

## 1.3 两群并排可能制造虚假对称

`contrasts_with`与`complements`是对称语义；`provides_foundation_for`、`applies_to`、`challenges`、`constrains`与`evolved_from`有方向。左右布局只是空间位置，不能替代 relation direction。

## 1.4 Group Boundary 与当前内容可能不一致

只比较两群现有 Nodes 会把内容缺口误写成范围差异，也会把共享 Knowledge 误写成 Boundary overlap。

## 1.5 Relation Bundle 可能合并语义

一个 pair 可以同时互补、对照，并在某个范围内存在挑战。若图上只保留一条粗线或一个“3 条关系”气泡，用户无法知道每条陈述的方向、限定和 lifecycle。

## 1.6 AI Compare 可能偷偷成为类型判断器

AI 可以帮助生成候选陈述，却不能因为回答流畅就跳过类型必填项、资格门或用户检查。

## 1.7 Shared Knowledge Lens 可能变成关系捷径

如果“共同知识”画成 edge，产品会重新引入已经废弃的 `shares_core_knowledge_with`，并在 Placement 变化时制造自动消失的假历史。

## 1.8 后台刷新可能产生时间撕裂

左侧 Boundary、右侧 Overview、Current Relations 和 shared observation 若各自实时更新，用户可能在同一判断中看到四个不同时间点。

## 1.9 返回链不清楚

从 Network edge、Group Overview、Ask Claim、cross-group exit 或 Search result 进入 Compare 后，关闭应回到不同 origin。统一回到 Library 顶部会破坏探索连续性。

---

# 2. 产品目标与非目标

## 2.1 产品目标

Group Pair Comparison 必须让用户在一次连续任务里：

1. 定位两个知识范围；
2. 阅读双方 Boundary 与主要方向；
3. 区分 formal、derived、path、suggested 与 historical；
4. 理解每条正式关系的完整 statement、方向、限定和依据；
5. 看见共同知识的真实 identity / Placements；
6. 沿具体 exits 深入；
7. 对候选进行精确类型判断；
8. 修订、结束、替代或撤回已有关系；
9. 对当前 pair 提问；
10. 无损返回进入前现场。

## 2.2 非目标

本表面不负责：

- 把所有 Groups 做成 N×N 对比矩阵；
- 自动给所有 Group pairs 打分；
- 生成相似度排行榜；
- 把共同标签、共同来源或 embedding 当关系；
- 代替完整 Group Overview；
- 代替 Knowledge reading / Evidence reader；
- 批量维护整个 Registry；
- 自动消除所有类型歧义；
- 因比较而创建新的 Group、Topic、Knowledge 或 Collection；
- 成为第二套聊天产品。

---

# 3. 对象模型：Comparison 是工作现场，不是新知识资源

## 3.1 GroupPairKey

```text
GroupPairKey
  space_id
  group_id_low
  group_id_high
```

`GroupPairKey`只用于查找同一 pair 的 inventory。它不定义 relation direction，也不拥有 title、Overview、membership 或 lifecycle。

## 3.2 GroupPairComparisonState

```text
GroupPairComparisonState
  comparison_id
  pair_key
  left_group_id
  right_group_id
  entry_context
  base_snapshot_id
  active_section
  active_relation_id?
  active_candidate_id?
  active_knowledge_id?
  standing_filter[]
  relation_family_filter[]
  applicability_filter?
  time_context
  shared_knowledge_lens: off | on
  presentation: reading | balanced | relation
  graph_or_list
  return_envelope
  dirty_comparison_draft?
```

左右顺序是用户的当前阅读偏好；交换左右不改变 pair identity 或 directed relation meaning。

## 3.3 PairComparisonSnapshot

```text
PairComparisonSnapshot
  snapshot_id
  pair_key
  created_at
  left_group_boundary_revision_id
  right_group_boundary_revision_id
  left_overview_revision_id?
  right_overview_revision_id?
  relation_revision_ids[]
  candidate_assessment_revision_ids[]
  placement_revision_basis
  knowledge_identity_basis
  index_coverage_receipt
  registry_revision_id
  query_run_id?
```

默认 snapshot 是临时一致性基线。只有用户选择保存、导出或作为 Decision basis 时，才保留 supporting record。

## 3.4 PairConnectionInventory

```text
PairConnectionInventory
  current_relations[]
  shared_knowledge_observations[]
  cross_group_exits[]
  eligible_candidates[]
  suppressed_candidates[]
  aggregation_assessments[]
  historical_relations[]
  unresolved_type_reports[]
  coverage_state
  evaluated_at
```

它是可重建 projection，不是知识真相。删除缓存后从 Groups、Boundaries、Relations、Candidates、Placements、Knowledge identity、Support Sets 与 History 重建。

## 3.5 PairComparisonDraft

用户正在撰写关系 statement、调整类型或限定时，内容先进入 draft：

```text
PairComparisonDraft
  draft_id
  source: direct_create | candidate_edit | relation_revision | migration_review
  endpoints
  intended_family
  proposed_type
  statement
  direction
  applicability
  qualifiers
  mechanism?
  affected_dimension?
  challenged_object?
  lineage_directness?
  support_refs[]
  type_validation_report_id?
  base_revision_id?
  save_state
```

Draft 不进入 Current / Suggested / Ask truth。关闭时若有未保存内容，保留本地恢复或明确放弃，不能静默丢失。

## 3.6 Relation 与 Observation 的身份边界

| 对象 | 稳定 identity | 用户采用 | lifecycle | History | 自动刷新 |
|---|---:|---:|---:|---:|---:|
| Group Relation | 是 | 直接提交或采用 Candidate | 是 | 是 | 否 |
| RelationCandidate | 是 | 待判断 | candidate lifecycle | formation / decision history | assessment 可重评 |
| Shared Knowledge Observation | 否，按 pair + Knowledge identity 求值 | 否 | 否 | 否 | 是 |
| Cross-group exit | 来自真实 Knowledge / Relation path | 否 | 跟随底层对象 | 底层历史 | projection 重算 |
| Comparison Snapshot | supporting identity | 显式保存 | snapshot retention | 是 | 否 |

---

# 4. 进入、退出与返回合同

## 4.1 合法入口

1. Network 中选择 Group pair 或 Relation Bundle 后点击`比较两个知识群`；
2. Group Overview 的 Related Group 点击`比较`；
3. Relation Inspector 点击`查看两个知识群的完整关系`；
4. Ask 回答中的 pair Claim 点击`在知识库中比较`；
5. Cross-group exit 点击目标 Group 后选择`先比较`；
6. Search / Command 中明确选择两个 Groups；
7. Migration Review 从受影响 Relation 进入 pair context。

Hover、单击 Group、普通 Open、Query 共现与自动聚合不能进入 Compare。

## 4.2 进入摘要

进入前必须能预测：

```text
比较“认知科学”和“AI Agent 产品设计”
查看它们各自的范围、当前关系、共同知识与可探索路径。
不会建立或修改关系。
```

如果入口来自 directed relation，摘要继续说明：

```text
当前选择：“认知科学”为“AI Agent 产品设计”提供理论基础。
```

## 4.3 ReturnEnvelope

```text
PairComparisonReturnEnvelope
  origin_surface
  origin_owner_id
  origin_selection_layer
  origin_relation_id?
  origin_candidate_id?
  origin_query_claim_id?
  origin_anchor?
  origin_scroll?
  origin_graph_viewport?
  origin_filters?
  origin_focus_target
```

Close 返回 transient origin；Back 回到 caller；Open endpoint 会建立新的 ReturnStack entry；Up 不适用于 pair，因为 pair 不是结构父级。

## 4.4 交换左右

`交换左右`只改变阅读排列：

- directional relation 继续保持原 from / to；
- inverse sentence 更新为对应读法；
- selected relation identity 不变；
- filters、snapshot、Ask context 与 History 不变；
- 不创建 revision 或 recent event。

## 4.5 退出与未保存 Draft

无 Draft 时立即退出。存在 Draft 时提供：

- `继续编辑`；
- `保留未完成内容`；
- `放弃这次修改`。

不能用模糊“保存更改？”隐藏保存对象。若是 RelationCandidate edit，必须明确保存的是建议；若是 Relation revision，必须明确会推进 current statement。

---

# 5. Pair Comparison 的阅读结构

## 5.1 固定责任顺序

主阅读面按以下顺序组织，但不强制为七个 tabs：

1. **Pair Orientation**：双方分别是什么；
2. **Current Relations**：当前采用了哪些群关系；
3. **Shared Knowledge**：同一知识目前怎样出现在两群；
4. **Paths Between**：可以沿哪些具体知识走过去；
5. **Suggestions / Unknown**：可能值得建立什么，为什么尚不能判断；
6. **Evidence & Limits**：支撑、反例、适用条件与覆盖；
7. **History / Change**：过去怎样理解，什么发生了变化。

P0 默认展开前两项；其余按真实存在与当前意图渐进出现。没有内容的区段不显示空卡片。

## 5.2 Pair Header

Header 只显示：

- 两个 Group 名称；
- 当前 time context；
- 一句 coverage / freshness 事实；
- 一个主动作；
- overflow。

主动作按当前情境只能是：

- 有 Current：`查看选中关系`；
- 无 Current、有 Candidate：`检查关系建议`；
- 无 Candidate、有 exits：`沿路径探索`；
- 完全无联系：`在这两个知识群中提问`；
- 用户已明确开始建边：`检查并提交`。

Ask、Create、Swap、History、Export、Shared Lens 不同时常驻抢占。

## 5.3 Pair Orientation

每侧显示同构但不强制等高的信息：

- Boundary 一句话；
- 主要 Topics / stable start；
- representative Knowledge；
- 当前 Boundary tension / partial index；
- `打开知识群`。

双方信息都绑定具体 Boundary Revision。内容数量、活跃度或图中大小不能代替范围说明。

## 5.4 Current Relations

每条 row 首先是完整句：

```text
“认知科学”为“AI Agent 产品设计”提供理论基础。
```

下一层显示：

- 为什么重要；
- 适用范围 / 时间 / exceptions；
- `为什么是这种关系`；
- 主要 support summary；
- review / Challenge / lifecycle 事实；
- `查看关系`、`沿支撑路径探索`。

同 pair 多条关系按 family 分组、按用户固定顺序或稳定 type order 呈现；不按 confidence、path count、degree 或最近点击排序。

## 5.5 Shared Knowledge

默认只显示一句：

```text
目前有 2 条同一知识同时出现在两个知识群。
```

展开后每条显示：

- 一个 canonical Knowledge title；
- 左侧 exact Placement / role；
- 右侧 exact Placement / role；
- current Knowledge revision；
- 为什么它被计入或未计入 core observation；
- `打开这条知识`。

这里没有`采用关系`、`结束关系`、`撤回`、`关系历史`。可选动作是：

- 查看共同知识；
- 比较两侧语境；
- 沿这条知识探索；
- 基于更完整语义建立 Candidate。

最后一个动作必须重新进入类型与资格流程，不能把 observation 一键升级。

## 5.6 Paths Between

Cross-group exits 按可读 path 显示：

```text
认知科学 / 记忆 / 检索线索
  → provides_foundation_for
AI Agent 产品设计 / 记忆系统 / 上下文恢复
```

必须区分：

- formal Knowledge Relation；
- structural Placement step；
- Evidence step；
- reference / mention；
-本次 retrieval jump。

只有真实 connector 可成为 Saved Path step。纯 retrieval jump 退出 Answer 后消失；用户保留时必须写手工理由。

## 5.7 Suggestions / Unknown

Candidate 先显示完整 proposed statement、standing 与一句资格说明：

```text
可能值得建立：
“认知科学”与“人机交互”在注意分配问题上互相补充。
采用前不会出现在当前知识网络。
```

Unknown 使用具体落点：

- 只有 fringe exits；
- shared Knowledge 但 Boundary 不重叠；
- type ambiguous；
- direction split；
- Applicability 不一致；
- core CounterSignal；
- insufficient independent support；
- index partial；
- Boundary 尚不完整。

不写“关系强度 42%”或“没有发现价值”。

## 5.8 Evidence & Limits

证据区围绕当前选中 Relation / Candidate，而不是汇总两群所有 Sources。固定顺序：

1. statement；
2. supporting Knowledge paths；
3. Evidence Bindings / Support Set；
4. CounterSignals / Challenges；
5. Applicability / exceptions；
6. coverage / collapse / removal result；
7. change impact。

## 5.9 History / Change

History 以可读陈述为单位：

- 当时的 statement；
- type definition revision；
- endpoints / Boundary revisions；
- disposition；
- successor；
- 当时 support；
- 变化原因。

历史 Relation 不重新加入 Current inventory。as-of comparison 使用当时 snapshot，不把当前 Boundary 倒灌进旧判断。

---

# 6. Relation Bundle 与单条 Inspector

## 6.1 Bundle 只解决密度

Bundle 可以显示：

```text
当前有 3 条正式关系
基础 · 互补 · 对照
```

但内部始终是三个 relation IDs。Bundle 不拥有自己的 statement、type、support、lifecycle 或 edit action。

## 6.2 Bundle 展开顺序

1. 用户当前选择；
2. pinned relation；
3. relation family stable order；
4. 其余按完整标签展开。

不使用算法强度决定“主关系”。若用户固定一条为 pair 的 primary explanation，这是一项 curation ref，不改变其他 Relation truth。

## 6.3 GroupRelationInspector

Inspector 固定顺序：

1. 完整 statement；
2. type 与 inverse reading；
3. 为什么是这种类型；
4. why it matters；
5. Applicability / exceptions / time；
6. supporting Knowledge paths；
7. Support Set / Evidence / Challenges；
8. assertion disposition / change condition / lifecycle；
9. Type Definition Revision；
10. affected Overview / Paths / Answers；
11. History / successor；
12. continue exploring。

P0 不显示全部十二项。首屏只显示 1、4、5 的必要部分和一个主动作；其余一跳可达。

## 6.4 Inspector 动作

合法动作按对象状态变化：

| 状态 | 主动作 | 其他动作 |
|---|---|---|
| maintained current | 继续探索 | Revise、End、Supersede、Retract、Archive、History |
| review_due | 检查变化 | Maintain、换支撑、收窄、Supersede、End、Retract、Defer |
| ended | 查看当时依据 | 建立 current successor、History |
| superseded | 打开 successor | 查看旧依据 |
| retracted | 查看撤回原因 | 建立独立新 Relation |
| archived | 恢复到原 standing | History |

`恢复`只改变 lifecycle，不自动改变 disposition。

## 6.5 图与列表同步

选择一条 bundled edge 后：

- 图只高亮该 relation；
- 列表滚动并选中同一 relation；
- Inspector 打开同一 revision；
- Pair Orientation 不重排；
- Back 恢复 bundle 选择；
- screen reader 获得 statement、direction、standing 与 actions。

---

# 7. Candidate Inspector 与类型选择

## 7.1 建立入口

可以从：

- Pair header overflow；
- Current Relations 下方；
- Shared Knowledge / exit 的“建立更精确关系建议”；
- Ask Claim；
- Migration Review；
- 用户在 Network 中显式拖线后选择`说明它们如何相连`。

系统不能因 shared observation、similarity、共现、共同 Source 或 raw paths 自动打开 editor。

## 7.2 意图第一步

第一问固定为：

```text
你想表达哪一种联系？
范围 · 作用 · 协同 · 比较 · 限制 · 演化
```

第二步只显示相关 2–4 种中文类型，并即时回读完整句。

## 7.3 相邻类型问题

- 范围：一方完整属于另一方，还是只有一部分交叉？
- 作用：提供理解基础、可执行方法，还是说明适用对象？
- 协同 / 比较：共同补足、并列差异，还是一方在削弱另一方？
- 限制：减少成立条件 / 选择空间，还是只能说明其他明确影响？
- 演化：直接沿革，还是通过中间对象演化？

## 7.4 Candidate Inspector 固定顺序

1. proposed statement；
2. type / direction / inverse；
3. why this type；
4. alternatives considered；
5. Applicability / time / exceptions；
6. Boundary coverage；
7. Effective Support Units；
8. collapsed / excluded signals；
9. CounterSignals / Challenges；
10. strongest-unit removal；
11. adoption effects；
12. Adopt / Edit / Dismiss / Defer / Explore。

## 7.5 Direct Relation 与 Candidate

- 用户从自己的明确表达开始，并补全 statement / type / direction / Applicability / support，可直接提交 maintained Relation；
- AI、来源抽取、导入语义映射与路径聚合只能创建 Candidate；
- 用户在 Candidate Inspector 中采用后原子创建 Relation、first RelationRevision 与 Support Set Revision；
- 采用失败时 Candidate 保留，Current 不出现半条边。

## 7.6 TypeValidationReport

报告可以返回：

- valid；
- missing required meaning；
- adjacent type likely；
- direction inconsistent；
- symmetric duplicate；
- broad / narrow duplicate；
- incompatible Applicability；
- deprecated type；
- lineage insufficient；
- boundary evidence insufficient。

报告不自动修改。用户可以采用建议、保持原选择并补充解释、缩小范围、保存未完成 Candidate 或取消。

---

# 8. Shared Knowledge Observation 的 Compare 合同

## 8.1 计算条件

Observation 读取：

- canonical Knowledge identity；
- active Placements；
- current Placement roles；
- current Group Boundary Revisions；
- Knowledge lifecycle；
- index coverage。

它不读取相似 embedding、相同标题、复制文本、共同 Source 或 Query 共现。

## 8.2 三种呈现层级

| 层级 | 内容 | 影响布局 |
|---|---|---|
| Summary | `目前有 2 条共同知识` | 无 |
| Lens | 高亮同一 identities 与两侧 Placements | 不重排 |
| Context Compare | 并排显示同一 Knowledge 在两群的 contextual role | 进入明确 Compare，不建边 |

## 8.3 Observation 变化

Placement / role / Boundary / lifecycle 改变后：

- 新 inventory 自动重算；
- 当前 snapshot 显示`共同知识的当前结果有变化`；
- 用户选择刷新或保持 snapshot；
- 不创建 Relation history；
- 已保存 Comparison Snapshot 保留当时计算 basis；
- 若它曾支撑 Candidate，只触发 Assessment refresh。

## 8.4 从 Observation 到正式 Candidate

产品必须重新询问：

1. 共享知识说明的是范围部分交叉、基础、方法、应用、互补、对照、挑战、限制、影响还是沿革？
2. 是否触及两侧 Boundary，而非仅是多位置复用？
3. 是否有独立支撑、方向与 Applicability？
4. 是否存在反例？

只有通过完整类型与聚合合同后，才产生 Candidate。没有“一键升级为关系”。

---

# 9. Pair Ask 合同

## 9.1 默认 Scope

Pair Ask 的 Requested Scope 是：

```text
Group A current Boundary + included Knowledge
Group B current Boundary + included Knowledge
Current applicable Relations between A and B
```

Shared observations、cross-group exits、Candidates 与 History 是否加入，必须由问题意图或显式 selector 决定。

## 9.2 典型问题

- `它们有什么关系？`
- `它们在哪些问题上互补？`
- `A 对 B 提供的是基础还是方法？`
- `两者共享哪些核心知识？`
- `为什么系统还没有建议群关系？`
- `这条挑战关系在哪些条件下成立？`
- `过去为什么把它们看成重叠？`

## 9.3 回答结构

1. 直接答案；
2. 当前正式关系；
3. shared observation；
4. concrete paths；
5. Candidate / Unknown；
6. conflict / Applicability；
7. coverage；
8. explore / save actions。

没有对应内容的层不显示。AI 不为了填满结构而创造关系。

## 9.4 Pair Ask 写回

回答后的独立动作：

- 保存回答；
- 保存所选 Claim 为 Knowledge Draft；
- 保存一条探索路线；
- 建立 RelationCandidate；
- 打开 Relation Revision editor；
- 保存 Comparison Snapshot。

一个`保存`按钮不得同时完成多种写入。

---

# 10. Snapshot、刷新与时间一致性

## 10.1 默认一致性

打开 Compare 时创建临时 base snapshot。当前显示的：

- 两侧 Boundary；
- Overview refs；
- Relation revisions；
- type registry revision；
- shared observations；
- candidates / assessments；
- coverage receipt

必须属于同一 evaluation boundary。

## 10.2 背景变化

后台变化不直接替换当前阅读。Header 显示一条：

```text
比较内容有更新：一条共同知识的位置发生变化。
查看变化 · 刷新比较
```

Registry、Boundary、Relation statement 与 index coverage 变化分开说明。

## 10.3 刷新

刷新创建新的 temporary snapshot，并保留：

- active section；
- selection if resolvable；
- scroll / focus；
- graph viewport；
- draft base warning。

若 Relation / Candidate 已变化，Draft 进入 stale compare，不自动 rebase。

## 10.4 Historical compare

用户选择 as-of 时间后：

- 两侧读取当时可解析 Boundary / Overview / Placement / Relation snapshots；
- shared observation 按历史可用 basis 重建，缺失时明确不可重建；
- Current label 改为`当时采用的关系`；
- 建立新 Relation 仍回到 current context，不写进过去。

---

# 11. 方向 3 + 方向 2 的产品级组合

## 11.1 默认不是固定 50/50

明确进入 Compare 后，桌面可以使用：

- **Reading dominant**：Pair Orientation + Relation statements 为主，Network cue 为辅；
- **Balanced**：双方范围 / statement 与 Relation Companion 并列；
- **Relation dominant**：用户显式进入 map exploration 后，图为 Primary，Pair reading 变 Preview。

ordinary Group open 仍回到单 Group Reading，不恢复 Compare。

## 11.2 Warm Reading 的责任

温暖阅读面承载：

- 两群各自范围；
- 完整关系句；
- 对照维度；
- 限定、反例与变化；
- 共同 Knowledge 的语境差异；
- Ask answer。

它不能退化成两张摘要卡、指标表或 AI 自动结论墙。

## 11.3 Relation Night 的责任

深色关系面承载：

- pair 与 selected relation；
- supporting paths；
- shared Knowledge Lens；
- Current / Suggested / History layer；
- direction 与 endpoint；
- cross-group navigation。

它不能用星点、光线、大小或颜色替代真实 identities、labels、selection 与 Inspector。

## 11.4 视觉家族

正式类型只使用有限 family-level grammar：

- Scope；
- Directional Contribution；
- Symmetric Comparison / Cooperation；
- Directional Effect；
- Lineage。

精确 type 由可读 label、arrow / endpoint、完整 sentence 与 List Equivalent 承担。Current / Suggested / History 属于 standing，不与 type family 混用颜色通道。

## 11.5 Pair Map 起始预算

- 2 个 Group anchors；
- 当前选中 relation；
- 0–4 条其他 Current relations；
- 0–6 个 supporting Knowledge nodes；
- Candidate 只有显式 Suggested layer 才出现；
- Shared Knowledge 只有 Lens on 才高亮；
- History 只有显式 historical context 才出现。

预算只限制初始表达，不删数据。全部关系通过 List Equivalent 可见。

## 11.6 Screen 2 / Screen 3 的证明要求

未来设计必须用同一真实 fixture 证明：

1. Screen 2 的正文侧能比较两个真实 Group Boundaries，而不是展示一篇孤立文章；
2. 右侧 graph 使用与左侧相同 relation IDs；
3. 同 pair 的 complement、contrast 与 challenge 不被一条金线合并；
4. shared Knowledge Lens 开关不改变 layout；
5. Current / Suggested / History 可见但不形成三张独立图；
6. selected relation 的 Inspector 与 List row 同义；
7. Ask Claim 可以回到具体 pair statement / support；
8. Close / Back 恢复原 Anchor 与 viewport；
9. 0 relation 仍有诚实且可探索的 surface；
10. narrow / mobile 使用顺序表达完成同一任务。

---

# 12. 状态、失败与退化

## 12.1 状态矩阵

| 状态 | 正确表达 | 保留能力 | 禁止 |
|---|---|---|---|
| 0 Current / 0 exits | 当前没有可确认联系 | Ask、打开两群、建明确 Relation | 生成装饰边 |
| 0 Current / exits | 有具体路径，尚未形成群关系 | 沿 path、Ask why、保存 Path | 写成“已连接” |
| Current only | 当前采用 N 条关系 | Inspect、Explore、Revise | 为了建议重排 Current |
| Candidate only | 可能值得建立 | Review、Edit、Dismiss、Defer | 进入 Current / Overview |
| Shared only | 有共同 Knowledge | Compare context、Open Knowledge | 创建 lifecycle edge |
| Review due | 主要依据有变化 | Maintain、Revise、End 等 | 自动删边 / 改型 |
| Boundary incomplete | 一侧范围仍在形成 | 比较已有范围、补 Boundary | 用内容反推完整 Boundary |
| Partial index | 一部分尚未评估 | 已知 Current、exact paths | 宣称无关系 |
| AI unavailable | AI 暂不可用 | 人工阅读、Current、History | 阻止 Compare |
| Graph unavailable | 图暂不可用 | 完整 List Equivalent | 空白错误页 |
| Offline | 使用本地快照 | 读、改、本地提交、History | 冒充已同步最新 |
| Registry unavailable | 使用 Relation pinned definition | 读现有 statement / History | 猜测 current enum 意义 |
| Stale draft | 底层已变化 | Compare diff、rebase、保留 | 静默覆盖 |

## 12.2 Group deleted / archived / redirected

- archived Group 可以在 History / explicit compare 中打开，默认不进入 current Network；
- trash Group 只显示恢复或历史影响，不能建立新 Current Relation；
- redirect 必须解析 identity continuity；
- split / merge transition pending 时显示具体 RelationTransitionCases；
- 无法解析 endpoint 时保持历史 snapshot，不挂到近似 Group。

## 12.3 Source degraded

Source 不可用只影响 Evidence re-verification。Relation statement、Knowledge、Support Set snapshot 与 Historical Compare 仍保留，并说明哪些依据当前不能重新核验。

## 12.4 保存失败

Relation / Candidate / Snapshot 保存失败时：

- Current 不变化；
- Draft 留在本地；
- 显示失败对象与范围；
- 提供重试、复制 statement、导出 draft；
- 不显示 success toast 或半条 edge。

---

# 13. Responsive、键盘与辅助技术

## 13.1 Desktop

Primary + one Companion + Rail。Pair reading 拥有主标题和默认快捷键；Relation Companion 可以 follow selected relation 或 pinned，但必须显示 target。

## 13.2 Compact / tablet

Pair Orientation 先顺序显示两侧 Boundary；Relation inventory 使用可展开列表；Graph 是可切换 surface，不压缩成不可读缩略图。

## 13.3 Mobile

顺序固定为：

1. Pair Header；
2. Group A / Group B orientation；
3. Current Relations；
4. Shared / Paths / Suggested；
5. selected Inspector Sheet；
6. Evidence；
7. Back。

左右交换变为“先看 A / 先看 B”，不依赖拖动分隔线。

## 13.4 Keyboard

- Tab 进入 section landmarks；
- 方向键在 Relation List 内移动；
- Enter Inspect；
- 明确 action Open endpoint；
- Escape 关闭 Inspector 并恢复触发 row；
- Compare / Swap / Graph-List switch 均有可读名称；
- focus 与 selected relation 分开。

## 13.5 Screen reader

每条 relation 至少朗读：

```text
当前关系。认知科学为 AI Agent 产品设计提供理论基础。
方向：认知科学到 AI Agent 产品设计。
适用范围：记忆机制与注意资源。
需要检查：主要依据发生变化。
```

Observation 朗读`共同知识观察，不是正式关系`；Candidate 朗读`建议，尚未采用`。

## 13.6 200% zoom 与 reflow

双栏转单栏，内容无需二维滚动才能阅读。只有真正的数据 grid 可在自己的容器内横向滚动；关系句、Boundary、Inspector actions 与返回不依赖横向滚动。

---

# 14. 代表场景

## 14.1 Foundation + Complement 同时成立

“认知科学”为“AI Agent 产品设计”提供理论基础，同时两者在“人类记忆机制 vs 系统记忆工程”上互相补充。两条 Relation 分开显示，Bundle 不合并 statement。

## 14.2 Contrast + Challenge 同时存在

两群在同一评价维度上形成对照，其中一群的证据又定向挑战另一群的一项主张。Contrast 是 symmetric，Challenge 是 directed；挑战不撤回整个 Group。

## 14.3 只共享同一 Knowledge

同一“工作记忆负担”Knowledge 出现在两个 Groups。Pair 显示 shared observation 与 exact Placements，Current Relation count 保持 0。

## 14.4 一条 fringe exit

用户可以沿路径走到另一群，但 Boundary coverage 不足。产品说明“可以沿这里继续”，不出现 Candidate。

## 14.5 Qualified Candidate

Candidate 通过九道门。Inspector 解释完整 statement、两侧 coverage、独立 units、collapsed origins、CounterSignals 与 removal result，用户采用后才进入 Current。

## 14.6 Type ambiguous

系统无法判断是 foundation 还是 method。Pair 显示两个自然语言 alternatives；用户未决定前不画边。

## 14.7 Broad influence blocked

用户选择“以其他方式影响”，但没有说明机制。产品要求补 mechanism / affected dimension / why not narrower，不允许提交。

## 14.8 Partial overlap vs scope within

A 完全落在 B Boundary 内。系统建议 scope containment，而非 partial overlap；左右交换不改变 canonical direction。

## 14.9 Shared observation changes

一个 Placement role 从 representative 改为 reference。临时 snapshot 提示结果变化；刷新后 observation 数减少，不创建 Relation History。

## 14.10 Relation review due

主要支撑被 supersede。Current Relation 保留，Pair 显示需要检查；用户可以 Maintain、换支撑、收窄或 Supersede。

## 14.11 Registry migration

旧 Group-level `overlaps_with`固定旧定义版本。Migration Review 比较 partial overlap、scope containment 与其他精确关系，用户决定前不改 Current。

## 14.12 Historical compare

用户查看 2025 年两个 Groups 的关系。当时 Boundary / Relation / support 可重建；当前 successor 独立显示，不能覆盖历史。

## 14.13 Ask then save Candidate

AI 回答“两群可能在某维度互补”。用户选择建立建议，系统复用 Claim support 与 comparison snapshot，但仍要求类型、范围和资格检查。

## 14.14 Graph unavailable

图布局失败。List Equivalent 完整显示 relations、observations、paths、Candidates 与 actions，用户可以完成任务并返回。

## 14.15 Partial index

一侧 30% Knowledge 尚未评估。Current formal Relations 仍显示；derived / negative conclusions 标明 coverage，不能说“没有其他联系”。

## 14.16 Mobile relation edit

用户在手机上从 Pair List 打开 Candidate、补充 Challenge mechanism、检查影响并采用，再 Back 回到原 row。能力不因没有双栏缩水。

## 14.17 Compare from Ask Claim

从 Answer Claim 进入 Pair，查看 relation support 后返回，恢复原 Claim、Run、Answer scroll 与 Query highlight。

## 14.18 Compare with zero relation

两个刚建立的 Groups 没有 Current、Candidate、shared observation 或 exit。产品仍提供双方 Boundary、打开 Group 与 Ask，不生成“尚未完成连接”的债务。

---

# 15. Given / When / Then 验收合同

## 15.1 Compare 不创建对象

**Given** 用户选择两个 Groups  
**When** 进入并关闭 Pair Comparison  
**Then** 不创建 Relation、Candidate、Observation history、Saved Answer、Path、Group 或 Knowledge；原 ReturnEnvelope 恢复。

## 15.2 Pair key 与方向分开

**Given** A provides_foundation_for B  
**When** 用户交换左右  
**Then** pair inventory 不重复；Relation 仍是 A→B；界面使用正确 inverse reading。

## 15.3 Boundary 与内容分开

**Given** A 当前内容只覆盖 Boundary 一小部分  
**When** 与 B 比较  
**Then** 产品分别显示 A Boundary 与 current coverage，不把缺内容解释成 scope exclusion。

## 15.4 多条 Current 不合并语义

**Given** 同 pair 有 complement、contrast 与 challenge  
**When** Graph 折叠为 Bundle  
**Then** List / Inspector 仍能逐条访问各自 identity、direction、statement、support、Revision 与 lifecycle。

## 15.5 Observation 不是 Relation

**Given** 两群共享 canonical Knowledge  
**When** 开启 Shared Lens  
**Then** observation 显示 exact Placements；Relation count、Current / Suggested / History、layout 与 lifecycle 均不变化。

## 15.6 Exit 不升级

**Given** 只有一条 fringe cross-group exit  
**When** 打开 Pair  
**Then** 显示可走路径和不足原因，不创建 Candidate 或 edge。

## 15.7 Candidate standing

**Given** 一个 qualified Candidate  
**When** 与 Current Relations 同屏  
**Then** Candidate 明确写“尚未采用”，位于 Suggested responsibility，不进入 Overview stable projection 或默认 Ask truth。

## 15.8 Intent-first type choice

**Given** 用户建立关系  
**When** 打开 editor  
**Then** 先选择六类意图，再看到相关中文类型与完整句；不先展示十一项 enum。

## 15.9 Type ambiguity

**Given** foundation / method 无法确定  
**When** validation 运行  
**Then** 报告 alternatives 与缺失 meaning，不自动选数量更多的 path，也不默认 influences。

## 15.10 Influence required meaning

**Given** 用户选择 influences  
**When** 缺少 mechanism、affected dimension 或 narrow-type exclusion  
**Then** 不能提交 Current Relation，可保存未完成 Candidate 或继续编辑。

## 15.11 Challenge direction

**Given** A challenges B  
**When** 左右交换或切 Graph / List  
**Then** challenge direction、challenged object、mechanism 与 Applicability 不变；B 不被自动 retract。

## 15.12 Partial overlap

**Given** A 完全属于 B，或只共享几条 Knowledge  
**When** 类型判断  
**Then** 两者均不使用 partial overlap；只有 Boundaries 部分相交且互不包含时通过。

## 15.13 Direct / indirect lineage

**Given** A 经 C 演化自 B  
**When** Pair 显示 evolved_from  
**Then** indirect 明示并可展开 A←C←B path，不画成 direct adjacency。

## 15.14 Ask 不写关系

**Given** Pair Ask 生成关系解释  
**When** Answer 完成  
**Then** Current / Suggested 不变化；只有显式建立 Candidate 或提交 direct Relation 才写入。

## 15.15 Ask 保存复用 basis

**Given** 用户从 Answer Claim 建立 Candidate  
**When** 进入 review  
**Then** 复用 query run、comparison snapshot、support 与 type alternatives；不生成另一套不可追溯理由。

## 15.16 Relation revision

**Given** 用户把 influences 收窄为 provides_method_for  
**When** 语义角色连续  
**Then** 创建新 RelationRevision 并保留旧 statement；若主张已变则创建 successor，不原地覆盖。

## 15.17 Support-only change

**Given** statement / type / direction / Applicability 未变，仅替换支撑  
**When** 提交 review  
**Then** 创建 Support Set Revision，不制造 RelationRevision。

## 15.18 Registry migration

**Given** Type Definition Revision 更新  
**When** 打开旧 Relation  
**Then** 仍按 pinned old definition 读取；Migration Review 可用；用户决定前不改型或改方向。

## 15.19 Snapshot consistency

**Given** 比较期间 Placement 与 Boundary 更新  
**When** 当前 snapshot 尚未刷新  
**Then** 所有区段继续使用同一 basis，并提示更新；不会一半旧、一半新。

## 15.20 Refresh preserves context

**Given** 用户选中某 Relation 并滚动到 Evidence  
**When** 刷新 comparison  
**Then** selection、section、scroll、focus 与 viewport 尽量恢复；无法解析时给出明确 fallback。

## 15.21 Back returns exact origin

**Given** 从 Ask Claim、Network edge 或 Knowledge Anchor 进入  
**When** Back  
**Then** 分别恢复原 Claim / scroll、edge / viewport、Knowledge / Anchor，不统一回 Library 顶部。

## 15.22 Graph / List equivalence

**Given** 图不可用或用户使用 screen reader  
**When** 切换 List  
**Then** 能完成选择 relation、查看 support、打开 endpoint、检查 Candidate、切 History 与返回。

## 15.23 Partial index

**Given** 一侧索引覆盖不完整  
**When** Pair 显示 0 Candidate  
**Then** 不宣称无潜在联系；明确 eligible / evaluated / unavailable 范围。

## 15.24 Offline

**Given** 网络与 AI 均不可用  
**When** 打开 Pair  
**Then** 本地 Boundary、Overview、Current Relations、shared identity、exact paths、History 与人工编辑可用；状态不冒充已同步。

## 15.25 Save failure

**Given** Relation adoption 本地写入失败  
**When** 提交  
**Then** Current 不出现 edge；Candidate / Draft 保留；用户可重试、复制或导出。

## 15.26 Observation refresh

**Given** shared Knowledge 的 Placement role 变化  
**When** 刷新 Pair  
**Then** observation 自动更新；不创建 RelationRevision、History 或 migration item。

## 15.27 Historical compare

**Given** 用户查看过去时间点  
**When** current successor 已存在  
**Then** 当时 statement / Boundary / support 与 current successor 分层；历史不被当前定义覆盖。

## 15.28 Bundle primary curation

**Given** 用户把一条 relation 固定为 pair primary explanation  
**When** 再打开 Pair  
**Then** 它优先呈现，但其他 Relations 的 identity、检索、Ask truth 与 importance 不改变。

## 15.29 200% reflow

**Given** desktop 放大到 200%  
**When** 双栏无法并列  
**Then** 转为单栏顺序；relation statement、Boundary、actions、Evidence 与 Back 无二维页面滚动仍可使用。

## 15.30 Keyboard focus

**Given** 用户只用键盘  
**When** 在 list → inspector → endpoint → Back 之间操作  
**Then** focus、selection 与 open state 分开，返回原 row，所有主动作有名称。

## 15.31 No relation is valid

**Given** 两群没有任何 current / candidate / observation / exit  
**When** 打开 Pair  
**Then** 显示双方范围与诚实空结果，提供 Ask / Open Group；不生成连接债务或建议数量。

## 15.32 Screen 2 / 3 不冒充证明

**Given** 当前 Ardot 只有文章 + 星图图片和概念星图  
**When** 评估 Pair Comparison 完整性  
**Then** 因缺少真实 pair identity、standing、statement、Inspector、List、return、failure 与 responsive states，覆盖仍为未证明。

---

# 16. 指标、诊断与反指标

## 16.1 结果指标

- 用户能正确区分 Current Relation、Candidate、Observation 与 exit；
- 用户能用自己的话复述 selected relation 的方向与限定；
- 从 Pair 到 supporting Knowledge / Evidence 再返回成功率；
- type ambiguity 经用户判断后的精确类型选择率；
- relation revision / support-only change 分流正确率；
- zero-relation 场景中继续探索成功率；
- Graph / List task equivalence；
- Back exact-origin restore 成功率。

## 16.2 诊断指标

- Shared Lens 被误当 Relation 的理解错误率；
- broad influences selection / later narrowing rate；
- Candidate adoption 后立即 undo / retract rate；
- Bundle 展开率与误读率；
- partial index 下错误 negative conclusion rate；
- Registry migration defer / accept / manual rewrite distribution；
- stale snapshot refresh failure；
- mobile relation editing completion。

## 16.3 反指标

不得优化：

- 平均 pair 关系数量；
- 图谱边密度；
- Candidate 生成量；
- Relation adoption rate；
- Shared Knowledge observation 数；
- Ask 后建边转化率；
- 使用 `influences` 的便利性；
- 通过更亮、更粗、更近中心获得的“重要感”；
- 用户停留时长本身。

---

# 17. 研究事实、产品推论与证据边界

## 17.1 WAI-ARIA Grid：focus、selection 与 action 必须分开

WAI-ARIA Authoring Practices 的 Grid pattern 区分 composite focus movement 与内部交互，并要求可预测键盘行为。

**产品推论：** Pair Relation List 可以使用 grid / list 语义，但 focus row、selected relation、Inspect 与 Open endpoint 不能由一个裸 selection 状态驱动。该标准不决定本产品的 Pair surface 结构。

[WAI-ARIA Grid Pattern](https://www.w3.org/WAI/ARIA/apg/patterns/grid/)

## 17.2 WCAG Reflow：双栏不能成为能力前提

WCAG 2.2 Reflow 要求内容在放大与窄视口下重排，避免为了阅读文本进行二维滚动。

**产品推论：** 方向 3 + 2 可以在宽屏形成双镜，但 Pair Orientation、Relation statement、Evidence 与 actions 必须拥有单栏等价序列。该标准不决定具体断点或比例。

[WCAG 2.2 — Reflow](https://www.w3.org/WAI/WCAG22/Understanding/reflow.html)

## 17.3 Capacities：side panel 应保存主内容上下文

Capacities 官方 Navigation 文档把 full-page、preview modal、side panel 与 tabs 分开，side panel 用于在保留主内容时查看 supporting context。

**产品推论：** Relation Inspector / Companion 可以支撑 Pair Reading，但不能创建第二 owner 或在关闭后丢失 origin。Capacities 不证明本产品一个 Companion 上限或 Group Pair 模型。

[Capacities Navigation](https://docs.capacities.io/reference/navigation)

## 17.4 Anytype：Graph 是对象的一种视图，不是唯一目录

Anytype 官方 Graph 功能把对象和链接可视化，并与其他浏览 / 查询入口并存。

**产品推论：** Pair graph 必须有 List Equivalent，且 visual layout 不拥有关系真相。Anytype 不证明本产品的 formal type registry 或 standing layers。

[Anytype Graph](https://doc.anytype.io/anytype-docs/advanced/feature-list-by-platform/graph)

## 17.5 既有语义标准继续适用

SKOS 对 hierarchy 与 symmetric associative relation 的区分、OWL 2 对 inverse / symmetric / transitive characteristics 的显式定义、PROV-O 对 broad influence 与更具体 derivation / revision 的分层、SHACL 对 validation report 与数据写入的分离，继续支撑 Registry 与 Inspector 的可解释性边界。

这些标准不证明：

- Pair Comparison 应当只支持两个 Groups；
- Current / Shared / Paths / Suggested / History 的具体顺序；
- 双镜是最优默认构图；
- Relation Bundle 的信息密度；
- 用户能理解 observation 与 formal relation；
- 四十六项决定已通过真实可用性测试。

这些仍是产品决定和待验证假设。

[SKOS Reference](https://www.w3.org/TR/skos-reference/) · [OWL 2 Structural Specification](https://www.w3.org/TR/owl-syntax/) · [PROV-O](https://www.w3.org/TR/prov-o/) · [SHACL](https://www.w3.org/TR/shacl/)

---

# 18. 对文档体系与未来设计的同步要求

## 18.1 Canonical

必须增加：

- GroupPairComparisonState / Snapshot / Inventory；
- Compare 不是新 Primary Resource；
- Pair Ask Scope；
- Current / Shared / Paths / Suggested / History 顺序；
- snapshot consistency 与 exact return；
- 新验收合同。

## 18.2 Interaction / Flow

必须增加：

- pair compare entry / close / swap / refresh；
- shared lens；
- relation bundle selection；
- Candidate / Relation / Migration handoff；
- Graph / List / mobile / keyboard states；
- `group_pair.comparison_opened`、`group_pair.snapshot_refreshed`、`group_pair.returned`事件。

## 18.3 Ask / Overview / Network

- Ask 在 pair context 中显示两侧范围与实际 coverage；
- Overview 只提供进入 Compare 的链接，不内嵌完整比较系统；
- Network Bundle 打开 Pair 或单 Relation Inspector，动作必须可区分；
- Shared Lens 关闭后不影响 stable layout；
- History / Migration 不进入 default Overview。

## 18.4 未来视觉 Gate

进入 Pair Comparison 视觉探索前必须具备真实 fixtures：

1. 0 Relation + 0 exit；
2. exit-only；
3. shared-only；
4. multiple Current Relations；
5. Current + Candidate；
6. complement / contrast / challenge 同 pair；
7. ambiguous type；
8. review_due；
9. Registry migration；
10. partial index；
11. graph unavailable；
12. desktop / 200% / mobile / keyboard；
13. Ask Claim → Pair → Evidence → Back；
14. Shared Lens on / off layout comparison。

当前 Ardot Screen 2 / 3 尚未证明以上状态，继续作为视觉气质与构图方向输入，不作为产品完成证据。

---

# 结论

Group Pair Comparison 不是“两张知识群卡片 + 中间几条线”，也不是让 AI 临时总结“它们很相关”。它是用户核验知识网络的关键阅读行为：先理解两个范围，再分清当前关系、共同知识、具体路径、建议与历史，最后才决定是否建立、修订或结束一条长期陈述。

这也是方向 3 与方向 2 真正结合的地方：温暖阅读面负责让关系可读、可比较、可限定；深色关系面负责让路径、方向和网络位置可探索。两者共享同一 pair、同一 relation identity、同一 snapshot 与同一返回现场，不制造第二份知识真相。

本文继续停留在产品定义阶段，不授权制作原型。
