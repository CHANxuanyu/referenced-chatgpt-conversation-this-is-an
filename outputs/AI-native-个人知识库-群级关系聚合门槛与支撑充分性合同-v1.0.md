# AI-native 个人知识库

## 群级关系聚合门槛与支撑充分性合同 v1.0

> 日期：2026-08-10  
> 文档性质：终局产品本体、推断边界、交互行为与设计证明合同；不是图算法方案、评分模型、数据库实现、MVP 范围或原型授权  
> Canonical 产品定义：`AI-native-个人知识库-终局产品设计文档-v4.0.md`；本文只细化 Aggregated Group Relation 的资格、充分性与降级责任，不得反向新增产品中心  
> 上游关系生命周期：`AI-native-个人知识库-关系陈述生命周期与网络可信性合同-v1.0.md`；Candidate、Revision、Evidence、Challenge、Disposition、Lifecycle 与 Transition 继续以该合同为准  
> 下游类型注册表：`AI-native-个人知识库-群级关系类型注册表与语义互斥合同-v1.0.md`；它决定十一种 formal types、Shared Knowledge Observation、相邻类型区分与 Registry migration；本文类型示例与其冲突时以后者为准  
> 相邻合同：`AI-native-个人知识库-知识群边界与跨群架构合同-v1.0.md`、`AI-native-个人知识库-知识深度与关系探索合同-v1.0.md`、`AI-native-个人知识库-规模化知识空间与长期可浏览性合同-v1.0.md`、`AI-native-个人知识库-Overview形成编辑与更新合同-v1.0.md`、`AI-native-个人知识库-AI查询与知识回答合同-v1.0.md`  
> 用户意图：产品仍然是知识库；一个个知识群具有丰富纵向层级，并可通过真实、可解释的群间关系进入知识网络探索；方向 3 是阅读主干，方向 2 是按需关系空间  
> 当前阶段：先定义完整产品；本文不授权修改 Ardot、绘制高保真 Frame 或制作可点击原型  
> 第二真实夹具证明：`AI-native-个人知识库-第二真实端到端夹具-概念学习、多语境复用与群关系-v1.0.md`已验证同一 pair 可同时通过 `provides_foundation_for`与`provides_method_for`，但两者必须分别通过 conceptual dependency 与 actual-use gate；同一 Knowledge 的多 Placements 及同一 Source lineage 必须 collapse，宽泛 `complements`可因无新增语义而被拒  

---

# 0. 执行结论

## 0.1 这轮审计发现了什么

现有文档已经冻结：单条跨群 Knowledge Relation、共享 Knowledge、Gateway、Saved Path、共同来源、一次 Ask 共现与 embedding similarity 都不能自动形成 Group Relation；系统只能根据“多条正式 paths”提出 RelationCandidate。

但“多条”仍然不是产品合同。它留下九个会直接污染 Library Network 的缺口：

1. **没有有效支撑单位。** 三条路径可能只是同一条事实的 inverse reading、同一 Source 的三次摘录，或同一 Knowledge 的三个 Placements；按条数计算会产生伪多样性。
2. **没有跨层外推门槛。** 两个成员对象相连，不代表两个知识范围整体相连；局部事实被直接外推到 Group level，会把 fringe Knowledge 冒充群级主干。
3. **没有 Boundary relevance。** 现有 `core / bridge` 只是角色词，没有说明它如何相对 Group Boundary、governing question、representative Knowledge 与 Overview 成立。
4. **没有 relation-type-specific 规则。** `partially_overlaps_with`、`provides_foundation_for`、`scope_within`、`contrasts_with`、`challenges` 与 `evolved_from` 需要完全不同的支撑形状，不能共用一个“路径数 ≥ N”。
5. **没有方向合法性。** A 中的一个方法被 B 引用，不一定足以推出“A 为 B 提供方法”；反向读法、作用对象和 Applicability 必须同时成立。
6. **没有反例扫描。** 系统只收集支持路径而不检查同范围的限制、冲突或例外，会把选择性证据包装成稳定群关系。
7. **没有移除测试。** Candidate 可能完全依赖唯一核心路径；这类关系与拥有多个独立支撑的关系不应以同样显著性出现。
8. **没有失败后的诚实落点。** 未达到群级门槛的真实连接不能消失，也不能继续作为 Proposal 催促用户；它应保留为可走的 cross-group exits。
9. **没有视觉证明标准。** 当前 Ardot 全局星图把所有连线画成同一种空间装饰；双镜关系面也没有证明一条边如何从出口、Candidate、Current 到 History。

因此，本轮不设一个看似精确的“关系强度分数”，而是冻结：

> **Group Relation 的系统建议资格 = 明确群级陈述 × 合法类型规则 × 去重后的有效支撑 × 对两侧 Boundary 的充分覆盖 × 方向与适用条件一致 × 反例已检查 × 可解释的移除影响。**

任何一项缺失，都不能用更多同类连线补足。

## 0.2 本文件冻结的四十二项决定

1. **Group Relation 是跨层知识陈述，不是底层边的视觉聚类。**
2. **Cross-group exit、Aggregation Signal、RelationCandidate 与 maintained Group Relation 是四个不同 standing。**
3. **系统永远不能把 Signal 直接画进 Current Network。**
4. **用户直接建立完整群级陈述时，不需要满足系统聚合门槛。** 它按 user-asserted Relation 保存，并诚实显示依据状况。
5. **AI、Source extraction、路径聚合和 trusted import preview 都先创建 Candidate。** 它们不能以“Direct”名义绕过采用。
6. **系统主动提出 Aggregated Candidate 时，默认至少需要两个去重后的 Effective Support Units。** 原始 path count 不作为门槛。
7. **两个 Effective Support Units 必须不是同一 assertion、同一 content lineage 或同一 traversal 的重复呈现。**
8. **同一 Source lineage 的多个摘录只提供一个 provenance origin。** 它们可以补充细节，不能伪装成多份独立依据。
9. **同一 canonical Knowledge 的多个 Placements 只算一个 Knowledge identity。**
10. **Relation inverse label、对称镜像与 duplicate Relation 只算一个 assertion lineage。**
11. **Query Route、Saved Path 与可视化中的多次经过不形成新的支持单位。**
12. **每个系统聚合策略都必须绑定具体 Group Relation type。** 不存在通用 `related_to` 聚合器。
13. **`scope_within` 不能由成员路径聚合。** 它必须来自 Boundary contract 或用户明确断言。
14. **`evolved_from` 不能由相似路径聚合。** 它必须来自可追溯的 identity / transformation lineage 或明确历史陈述。
15. **`provides_foundation_for` 允许 bilateral-core 或 anchor-and-spread 两种支撑形状。**
16. **`provides_method_for` 必须证明方法被应用，而不只是被提到。**
17. **`applies_to` 必须说明 Group A 的什么适用于 Group B 的哪个明确范围。** 整群外推不能隐藏在 predicate 中。
18. **`contrasts_with` 必须具有共同比较维度与重叠 Applicability。** 不同问题的不同答案不是对照。
19. **`partially_overlaps_with` 必须具有双侧 Boundary overlap 与差异。** Shared core 只形成 Observation；一个共享 Node 不足以成立 formal Relation。
20. **`influences`、`constrains` 等因果 / 约束型关系需要明确 typed path 或直接群级陈述。** 引用、共现和相似度不能支撑。
21. **Boundary coverage 使用可解释 footprint，不使用百分比幻觉。**
22. **Coverage 至少区分 `bilateral_core / anchor_and_spread / named_subscope / fringe_only / unknown`。**
23. **`fringe_only` 与 `unknown` 永远不能进入系统主动 Suggested layer。**
24. **支持路径必须绑定 source / target Group Boundary Revision。** Group 变界后不能继续沿用旧覆盖判断。
25. **系统必须先扫描 CounterSignals 和 exceptions，再决定 Candidate standing。**
26. **不同 Applicability 的反向结果优先形成 qualifier / parallel scope，不制造伪冲突。**
27. **同一 Applicability 下的核心反向路径使 Candidate 进入 `conflicting`，不能继续按多数票建议。**
28. **系统不使用“多数路径赞成”作为群级真值。**
29. **每个 Candidate 必须显示 strongest-unit removal test。**
30. **移除最强 unit 后仍成立的 Candidate 可以进入 ambient Suggested；完全失去依据的 Candidate 只在用户主动询问时显示为 anchor-dependent。**
31. **Candidate eligibility 与展示显著性分开。** 通过资格不等于必须出现。
32. **同一 Group pair + relation family + Applicability fingerprint 同时最多一个未决 Candidate bundle。**
33. **被拒绝 Candidate 按语义 fingerprint 抑制；增加相同来源、相同路径或布局变化不能重提。**
34. **无法确定 relation type 时保留 exits，不创建 generic Candidate。**
35. **达到门槛只允许“提出建议”，不允许自动采用。**
36. **采用确认的是群级 statement，不是底层每一条 path 的永久正确。**
37. **Support Set 保存纳入、折叠、排除、反例与移除影响，而不只保存支持列表。**
38. **Ask 可以综合解释两个 Groups 的可能联系，而不创建 Candidate 或 Relation。**
39. **Search 与 Group Map 可以找回 exits；Library Network Current 只显示 maintained current Group Relations。**
40. **Suggested layer 必须解释“为什么够资格上升”，而不只显示路径数量或 confidence。**
41. **Graph 与 List 必须能表达相同的 eligibility、coverage、type fit、counter-signal 与 action。**
42. **未来视觉设计必须同时证明 exit-only、qualified Candidate、anchor-dependent、conflicting、Current 与 History，才能声称 Group Relation 设计完整。**

---


# 1. 产品心智模型

## 1.1 一句话定义

> **群级关系不是“两个群里有东西相连”，而是“基于当前两个知识群的边界，我们愿意把它们整体之间的某种关系作为一条独立知识来维护”。**

这句话包含三个跃迁：

1. 从具体 Knowledge paths 跃迁到 Group-level proposition；
2. 从系统观察跃迁到待判断 Candidate；
3. 从 Candidate 跃迁到用户当前采用的 Relation。

三个跃迁都不能由图布局代替。

## 1.2 四级 standing

| 层级 | 用户看到什么 | 是否群级陈述 | 是否进入 Current Network | 典型动作 |
|---|---|---:|---:|---|
| **Cross-group Exit** | `通过这条知识可以去另一个群` | 否 | 否 | 沿路径进入、查看来源 |
| **Aggregation Signal** | `两个群之间出现了可能值得判断的重复模式` | 尚未形成 | 否 | 后台折叠、等待更多依据 |
| **Group RelationCandidate** | 一句完整群关系及其资格说明 | 是，待判断 | 仅 Suggested | 检查、收窄、采用、拒绝 |
| **Group Relation** | 当前采用的正式群级关系 | 是 | maintained + current 时进入 | 探索、修订、Review、End |

Signal 是系统内部 Derived Evaluation，不是用户待办。只有它达到主动建议资格，才物化 RelationCandidate。

## 1.3 为什么不是“至少三条边”

以下三组数据都有三条可见路径，但意义完全不同：

```text
案例 A：同一 Knowledge 在三个 Topics 的 Placements
案例 B：同一报告的三个摘录支持同一 Relation
案例 C：三个不同 Knowledge assertions，来自两类来源，覆盖两个群的核心问题
```

A 只有一个 Knowledge identity；B 只有一个 assertion / provenance origin；只有 C 可能构成多个 Effective Support Units。产品若按线条数判断，会把内容重复、结构复用和来源重复奖励成“更可信”。

## 1.4 Direct 与 Aggregated

`Direct / Aggregated`只说明形成依据，不形成两套 truth standing：

- **User Direct**：用户直接写出完整 Group Relation 并提交，立即成为 maintained current Relation；
- **Source-explicit Candidate**：来源明确陈述两个领域 / 项目 / 主题整体之间的关系，系统抽取后形成 Candidate；
- **Typed Import Candidate**：导入数据已有群级 predicate，仍通过 Import Preview / adoption；
- **Aggregated Candidate**：系统从多个 Effective Support Units 形成新的群级综合陈述。

“来源明确说过”不等于系统可以自动采用；“用户亲手写下”也不等于外部证据充分。两者在 lifecycle 上一致，在 formation basis 上可追溯。

## 1.5 用户可以越过系统聚合门槛，但不能越过语义完整性

系统聚合门槛限制的是**系统何时有资格打扰用户**，不是限制用户表达自己的理解。

用户可以在只有一条或没有外部 supporting path 时直接建立 Group Relation，但必须完成：

- 两个 Groups；
- relation type 与方向；
- 可读 statement；
- Applicability / 时间 / 限制；
- why it matters；
- 可选 Evidence；
- 回读确认。

保存后界面可以写`你的判断；目前只有一条具体路径`或`你的判断；暂无外部依据`，不能阻止创建，也不能伪称“证据充分”。

---


# 2. Canonical 对象与记录

## 2.1 对象总览

| 对象 | 责任 | 身份层级 | 是否长期存在 |
|---|---|---|---:|
| `GroupRelationAggregationPolicy` | 定义某 relation type 是否允许聚合及需要什么支撑形状 | Definition & Policy | 是，版本化 |
| `AggregationSignal` | 保存后台观察到的未达 Candidate 模式 | Derived Evaluation | 可重建，低成本 |
| `EffectiveSupportUnit` | 把重复 paths 折叠为一个有效语义支撑单位 | Supporting Record | 随 Assessment 保存 |
| `SupportOriginCluster` | 解释多个路径是否来自同一 assertion / content / source / traversal | Derived + Supporting | 随 Assessment 保存 |
| `BoundaryCoverageFootprint` | 解释支撑触及两侧 Group Boundary 的程度与位置 | Supporting Record | 绑定 Boundary Revision |
| `GroupRelationAggregationAssessment` | 保存一次 Candidate 资格判断及失败原因 | Derived Evaluation + Decision basis | 是，可审计 |
| `GroupRelationCandidate` | 待用户判断的完整群级陈述 | Proposal Identity | 是，直到采用 / 拒绝 / 过期 |
| `GroupRelationSupportSetRevision` | 正式 Group Relation 某时刻的有效支撑快照 | Supporting Identity | 是，版本化 |

这些对象不新增一级页面。用户默认只看到可读 statement、资格原因、supporting routes、limits 与动作。

## 2.2 GroupRelationAggregationPolicy

```text
GroupRelationAggregationPolicy
  policy_id
  policy_revision_id
  group_relation_type_ref
  aggregation_permission:
    forbidden
    strict
    allowed

  accepted_support_shapes[]
  allowed_path_patterns[]
  disallowed_path_patterns[]
  endpoint_role_requirements[]
  direction_projection_rule
  applicability_merge_rule
  boundary_coverage_requirement
  independence_requirement
  counter_signal_rule
  removal_robustness_rule

  user_visible_reason_template
  active_from
  supersedes_policy_revision_ref?
```

Policy 是系统定义，不是每个 Group 的可调“高级设置”。否则用户会被迫管理一套本体工程工具。未来若允许专业用户自定义，必须进入独立 Definition surface，并且不能改变既有 Relation history。

## 2.3 AggregationSignal

```text
AggregationSignal
  signal_id
  group_pair_ref
  observed_relation_family?
  raw_path_refs[]
  first_observed_at
  last_observed_at
  signal_state:
    accumulating
    eligible_for_assessment
    collapsed_as_duplicate
    exit_only
    suppressed
  non_eligibility_reason_refs[]
  rebuild_basis
```

Signal 不进入 Library、Search 普通结果、Decision Inbox 或 Relation count。它可以被清除并从 canonical paths 重建。

## 2.4 EffectiveSupportUnit

```text
EffectiveSupportUnit
  support_unit_id
  assessment_ref

  semantic_path
    source_group_boundary_revision_ref
    source_knowledge_revision_refs[]
    relation_revision_refs[]
    target_knowledge_revision_refs[]
    target_group_boundary_revision_ref

  support_role:
    core
    corroborating
    boundary
    exception
    counter

  origin_clusters
    assertion_cluster_ref
    content_cluster_ref
    provenance_cluster_refs[]
    traversal_cluster_ref?

  applicability_projection
  direction_projection
  type_projection
  endpoint_role_projection
  current_resolvability
  inclusion_result:
    included
    folded_into_unit
    excluded
    counter_signal
  inclusion_reason
```

Effective Support Unit 不是“独立来源”的同义词。两个不同来源可以重复同一 assertion；一个来源也可能包含两个真正不同的 assertions。系统分别保留 assertion、content、provenance 与 traversal 四类 lineage，不把它们压成一枚 independence score。

## 2.5 SupportOriginCluster

```text
SupportOriginCluster
  cluster_id
  cluster_kind:
    assertion_lineage
    content_lineage
    source_lineage
    traversal_lineage
  member_refs[]
  canonical_member_ref
  collapse_reason
  preserved_differences[]
```

折叠不删除成员。Inspector 可以展开查看“这三条摘录来自同一份报告”，但资格判断只把它们作为一个 provenance origin。

## 2.6 BoundaryCoverageFootprint

```text
BoundaryCoverageFootprint
  footprint_id
  assessment_ref
  source_group_boundary_revision_ref
  target_group_boundary_revision_ref

  source_coverage:
    core
    named_subscope
    fringe
    unknown
  target_coverage:
    core
    named_subscope
    fringe
    unknown

  support_shape:
    bilateral_core
    anchor_and_spread
    named_subscope_only
    fringe_only
    unresolved

  source_anchor_refs[]
  target_anchor_refs[]
  representative_knowledge_refs[]
  overview_statement_refs[]
  boundary_fit_explanation
```

Coverage 不计算“覆盖了 37% 的知识”。Group 中 Knowledge 数量、文字长度与关系度数都不能代表 governing purpose。判断依据优先级是：

1. 当前 Boundary Revision；
2. 用户策展的 stable start / representative Knowledge；
3. 当前 Overview 中明确的主要方向；
4. Knowledge 的 Placement role；
5. Topic path 与内容语义；
6. 数量和频率只能作为诊断线索。

## 2.7 GroupRelationAggregationAssessment

```text
GroupRelationAggregationAssessment
  assessment_id
  assessment_version
  candidate_fingerprint
  group_pair_ref
  boundary_revision_refs[]
  policy_revision_ref
  assessed_at
  assessed_by:
    system
    user_invoked_ai
    import
    manual_review

  proposed_statement
  proposed_type
  proposed_direction
  proposed_applicability

  raw_path_refs[]
  effective_support_unit_refs[]
  origin_cluster_refs[]
  boundary_coverage_footprint_ref
  counter_signal_refs[]
  exclusion_records[]
  strongest_unit_removal_result

  gate_results{}
  outcome:
    eligible_ambient_candidate
    eligible_on_demand_candidate
    exit_only
    needs_more_support
    ambiguous_type
    conflicting
    invalid
    suppressed
  outcome_explanation
```

Assessment 保存为什么系统提了或没有提。它不是 Relation truth；Policy 或 Boundary 更新后可以重新评估，但旧 Assessment 仍保留当时依据。

## 2.8 Candidate Fingerprint

Candidate fingerprint 至少包含：

```text
normalized_group_pair
relation_family
direction
normalized_applicability
boundary_revision_family
effective_support_semantic_fingerprint
```

它用于：

- 同 pair 候选去重；
- dismissed suppression；
- 判断新证据是否真的改变建议；
- 避免一个 Relation family 因不同 wording 产生五张卡；
- 在 Boundary 重大变化后允许合法重评。

---


# 3. 九道资格门

系统主动创建 Aggregated Group RelationCandidate 前，必须逐项通过九道门。任何门失败都返回明确 outcome，不用总分抵消。

## G0. Endpoint 与 Boundary 可解析

必须满足：

- 两个端点都是 current、可解析的 Group identities；
- 不是 Topic、View、Saved Path、Query result 或临时 cluster；
- 两侧都有可读取的 Boundary Revision；
- Group 正处于 Split / Merge transition 时使用 transition-aware assessment；
- 同一 Group 的 self relation 默认不允许。

失败结果：`invalid`或`needs_more_support`；保留具体 exits。

## G1. 可以写成群级陈述

系统必须生成一句不依赖“有很多连线”才能成立的完整陈述：

> Group A 在什么范围内，以什么方式，改变、支持、限定、应用或对照 Group B。

如果 statement 只能写成：

- `A 与 B 有联系`；
- `A 和 B 经常一起出现`；
- `A 与 B 相似度较高`；
- `A 有三条边连向 B`；
- `A 和 B 都包含某标签`；

则失败为 `ambiguous_type`或`exit_only`，不能用 `related_to` 占位。

## G2. Relation type 允许该聚合方式

Assessment 必须绑定当前 Policy Revision：

- `forbidden`：只能 Direct / lineage 创建；
- `strict`：只允许特定 typed patterns；
- `allowed`：仍需通过其余所有门。

Path 中 relation families 必须能合法投影到 group-level type。类型不一致不能靠多数票选一个最常见 predicate。

## G3. 底层 paths 当前有效且适用范围可合并

可成为 `core / corroborating` 的 path 必须：

- 使用 maintained current RelationRevision；
- endpoints 与 Placements 可解析；
- 不来自 RelationCandidate、Reference Link、Query Jump、embedding edge 或 derived path；
- Applicability 与 proposed Group Relation 有非空、可解释交集；
- 不是只在历史时点成立，除非 Candidate 明确是 historical relation；
- supporting Knowledge 当前仍与相应 Group 有 Placement 或明确 Boundary role。

review_due path 可以进入，但必须显示变化；open Challenge 与 source unavailable 不自动排除，却会影响 counter / limitation 说明。

## G4. 原始 paths 完成去重与依赖折叠

至少执行四类 collapse：

1. **Assertion collapse**：inverse label、symmetric mirror、duplicate Relation、同一 Revision 的多次引用；
2. **Content collapse**：同一 Knowledge identity、transclusion、pinned excerpt、多个 Placements；
3. **Provenance collapse**：同一 Source Revision、同一 study / original record 的多个 reports、同一 import batch 的复制；
4. **Traversal collapse**：同一 Query Route、Saved Path、session 或 visualization traversal 的多次出现。

折叠后少于两个 Effective Support Units 的聚合 Signal，默认不能进入 ambient Suggested。

## G5. 支撑触及 Group Boundary，而不是 fringe

Assessment 必须形成 BoundaryCoverageFootprint，并满足 type policy 规定的 shape：

- `bilateral_core`：两侧都有多个核心或代表性知识参与；
- `anchor_and_spread`：一侧有明确 curated core anchor，另一侧有多个独立应用 / 影响 paths；
- `named_subscope_only`：只支撑两个群中明确命名的子范围，Candidate 必须把该子范围写入 Applicability；
- `fringe_only`：只碰到边缘 Knowledge，不能提升；
- `unresolved`：Boundary 不足以判断，不能提升。

一个高连接 fringe Node 不会因 degree 高而成为 Group core。Recent、点击、文档长度和 AI relevance 也不能自动升级 coverage。

## G6. 方向与端点角色一致

对有方向关系，系统必须回答：

- A 提供的到底是什么；
- B 在哪里使用、依赖或受到限制；
- inverse reading 是否仍是同一 assertion；
- 支撑 paths 是否都指向同一方向；
- 反向 paths 是 reciprocal relation、例外，还是方向判断错误。

如果一半 paths 表示 A→B，另一半表示 B→A，系统不能选数量更多的一侧。它应形成两个更窄 Candidates、一个 symmetric type，或 `ambiguous_type`。

## G7. CounterSignals 与 exceptions 已检查

Counter scan 至少覆盖：

- 同 pair、同 relation family、同 Applicability 的反向正式 Relations；
- 两侧 Overview / representative Knowledge 中明确限制；
- excluded Knowledge 中会直接改变群级 statement 的例外；
- open Challenges；
- Boundary exclusions；
- same-source contradiction。

处理顺序：

1. Applicability 不重叠 → qualifier / parallel scope；
2. 只限制部分范围 → exceptions / narrower Candidate；
3. 同范围核心冲突 → `conflicting`；
4. 只有“缺少依据” → `needs_more_support`，不伪造 Challenge。

## G8. Strongest-unit removal test

系统暂时移除对 Candidate 贡献最大的 Effective Support Unit，并重新检查 G3–G7：

| 结果 | Candidate standing |
|---|---|
| 仍满足 type 与 coverage | `eligible_ambient_candidate` |
| statement 仍可能成立，但 coverage 退化 | `eligible_on_demand_candidate`，标明依赖单一核心锚点 |
| 只剩 fringe / duplicate / vague paths | `needs_more_support`或`exit_only` |
| 方向或类型改变 | 原 Candidate invalid；重新形成不同 Candidate |

Removal test 不要求正式 Relation 永远拥有冗余。它只约束系统主动建议的显著性，并为未来 Support Set review 提供基准。

## G9. Attention 与重复建议预算

通过前八道门仍不等于必须出现。Ambient Suggested 还必须满足：

- 当前没有语义等价的 maintained Group Relation；
- 当前没有同 fingerprint 的 open / dismissed Candidate；
- 相比上次评估出现了新的 assertion、Boundary change 或新 Applicability，不只是更多重复 excerpts；
- 对当前 Group / Network scope 有解释价值；
- 同一 Group pair + relation family 不制造候选卡墙；
- Library 默认不显示候选数量 badge。

未通过 attention budget 的 eligible Signal 可以在用户主动打开 Suggested layer 或询问两个 Groups 的关系时出现，但不形成常驻提醒。

---

# 4. 支撑充分性：不做总分，做支撑形状

## 4.1 为什么不使用 confidence score

`关系强度 82%`无法回答：

- 82% 来自三条独立判断，还是三次复制；
- 支撑的是群的核心问题，还是边缘对象；
- 表达的是 overlap，还是 directional dependency；
- 是否存在同一范围的反例；
- Group Boundary 改变后是否仍成立；
- 用户接受后到底承担什么维护责任。

因此内部可以使用相似度、频率或模型置信度帮助发现，但资格输出只能是逐门结果、支撑形状和人话解释。任何数值不得成为 Current / Suggested / History 的视觉 standing。

## 4.2 两个 Effective Support Units 是下限，不是充分条件

系统主动形成 Aggregated Candidate 的默认下限为两个 Effective Support Units，原因不是“二比一可靠”，而是至少要证明它不是单一局部事件。

但以下都说明“两条仍不够”：

- 两条都只触及 fringe Knowledge；
- 两条来自同一 assertion lineage；
- 两条 Applicability 不可合并；
- 两条支持不同 relation types；
- 两条方向相反；
- 两条都依赖同一被挑战的 core anchor；
- 类型 Policy 要求 bilateral core，但两条都只在一侧展开。

相反，一份来源直接写出群级陈述时，它不是 Aggregated Candidate，而是 Source-explicit Candidate；它不需要假造第二条 path，但仍等待用户采用。

## 4.3 Bilateral Core

适用于：

- `partially_overlaps_with`；
- `contrasts_with`；
- `complements`；
- 某些 `challenges`。

必须同时满足：

- A 侧至少一个 current representative / core Knowledge anchor；
- B 侧至少一个 current representative / core Knowledge anchor；
- 至少两个 Effective Support Units；
- units 不全部收敛到同一个 canonical Knowledge；
- relation statement 能解释两个 governing purposes 的连接，而非仅列举共享名词；
- 若是 `contrasts_with`，所有核心 units 使用同一 comparison dimension。

系统不要求固定“每侧两条”。一个 curated core anchor 可以代表一侧，但另一条 unit 必须提供不同 assertion 或不同语义维度；否则是 anchor-dependent on-demand Candidate。

## 4.4 Anchor and Spread

适用于：

- `provides_foundation_for`；
- `provides_method_for`；
- `applies_to`；
- 某些 `constrains`。

形状是：

```text
A 的明确核心知识 / 方法 / 原则
  → 在 B 的两个或更多独立核心、bridge 或 named subscope 中被使用
```

要求：

- anchor 是用户策展的 representative、Overview 明确主张或可解释的 core Placement，不由 degree 自动选出；
- spread paths 不是同一 Knowledge 的多个 Placements；
- B 侧至少形成两个去重的使用 / 依赖 / 限制 assertions，或一个明确 Overview-level adoption + 一个独立具体 path；
- Candidate 的 statement 只覆盖实际 spread scope；
- 如果 spread 只落在 B 的一个 fringe Topic，保持 cross-group exit。

## 4.5 Named Subscope

支持只覆盖两群中的明确子范围时，合法产品结果不是“拒绝所有聚合”，而是收窄陈述：

```text
错误：认知科学为 AI Agent 产品设计提供基础
准确：认知科学中的工作记忆研究，为 AI Agent 产品设计中的长任务状态呈现提供基础
```

Named Subscope Candidate 必须：

- Applicability 明确列出 source subscope 与 target subscope；
- UI 在 P0 关系句中保留该限定，不能藏进 Inspector；
- Network resting label 仍可读，不缩写成无条件关系；
- Ask 沿它扩展时只能进入限定范围；
- 若用户希望更宽 statement，需要额外支撑，而不是删掉 qualifier。

## 4.6 Fringe-only

以下任一成立即为 fringe-only：

- 所有 paths 都来自非代表性、临时、低关联 Placement；
- 连接对象被 Group Boundary 明确排除；
- 支撑只来自一次 Capture / Query 产生的未整理对象；
- relation statement 删除具体 Knowledge 名称后无法说明群整体含义；
- 用户从 Overview / Catalog 无法自然到达这些 Knowledge；
- 高 degree 只由引用、标签或来源复用造成。

Fringe-only 仍然是可走路径；产品显示 exit，不写`还差一条就可以升级`，避免把正常局部连接制造成整理任务。

## 4.7 Independence Matrix

Assessment 在 Inspector 中不显示一个“独立性分数”，而显示四行事实：

| 维度 | 用户语言 | 通过示例 | 未通过示例 |
|---|---|---|---|
| Assertion | `是否是不同判断` | 两种不同机制共同支撑 | 同一 Relation 的 inverse / duplicate |
| Content | `是否来自不同知识` | 两篇独立 Knowledge | 同一 Knowledge 三个 Placements |
| Provenance | `是否来自不同来源脉络` | 用户判断 + 独立研究 | 同一报告三个摘录 |
| Role | `是否从不同位置触及群的核心` | core anchor + bridge application | 三条都落在同一 fringe Topic |

不同 provenance 不是硬门槛：个人知识可以主要来自用户自己的综合。但当界面写“多份依据”或“相互印证”时，必须至少有两个 provenance clusters。

## 4.8 Exclusion Record

每次 Assessment 还必须保存未被计入的 paths：

```text
ExclusionRecord
  path_ref
  reason:
    duplicate_assertion
    same_content_lineage
    same_source_lineage
    query_or_traversal_only
    candidate_not_current
    derived_not_asserted
    applicability_mismatch
    fringe_only
    endpoint_unresolved
    historical_only
    counter_signal
  explanation
```

用户无需默认阅读全部排除项，但可以检查`为什么显示 2 组有效路径，而不是图上的 7 条线`。

---


# 5. Relation type 专属聚合策略

## 5.1 类型矩阵

| Group Relation type | 聚合许可 | 最低支撑形状 | 必须证明 | 不足时落点 |
|---|---|---|---|---|
| `scope_within` | forbidden | Direct only | Boundary containment，不是内容相似 | Boundary suggestion / exit |
| `evolved_from` | forbidden | Lineage only | successor / transformation history | historical path |
| `provides_foundation_for` | strict | bilateral core 或 anchor-and-spread | A 的原则 / 理论实际承担 B 的基础角色 | exits / on-demand Candidate |
| `provides_method_for` | strict | anchor-and-spread | A 的方法在 B 中被实际使用 | exits |
| `applies_to` | strict | anchor-and-spread 或 named subscope | A 的何物适用于 B 的何范围 | scoped exit / narrower Candidate |
| `contrasts_with` | strict | bilateral core | 共同比较维度、重叠 Applicability、不同结论 / 方法 | comparison Path |
| `complements` | strict | bilateral contributions | 共同目标、不同且非冗余贡献、combined value | comparison view |
| `challenges` | strict | bilateral core / named subscope | overlapping Applicability、被挑战对象与 challenge mechanism | comparison / review path |
| `partially_overlaps_with` | strict | bilateral core / named subscope | Boundary 部分相交、双方都有非重叠范围 | exits / shared Knowledge Lens |
| `influences` | strict | typed directional paths | 影响机制与方向，不是引用次数 | exits / ambiguous type |
| `constrains` | strict | anchor-and-spread | A 的规则 / 限制实际约束 B 的选择空间 | exits |

Policy registry 可以扩展类型，但每个新类型必须先写出：合法 path pattern、方向投影、coverage shape、冲突类型、反例规则与不满足时的降级。

## 5.2 scope_within

`scope_within`表达两个独立 Group boundaries 的范围包含，不是 Topic nesting，也不是“多数 Knowledge 可以放进去”。

合法 basis：

- 用户明确建立；
- Boundary Revision 直接引用更广 governing purpose；
- trusted structured import 经用户 Preview；
- 可追溯组织 / 标准定义明确给出范围关系。

多个共享 Knowledge、相似 Topic 名或路径方向不能聚合出 scope containment。若 A、B 实际不是独立 Group，应走 Group merge / Topic promotion 判断，不用 relation 掩盖 identity 问题。

## 5.3 evolved_from

`evolved_from`需要历史连续性：

- Group successor；
- split / merge lineage；
- 明确的项目 / 学科演化陈述；
- 用户建立并提供时间范围。

embedding similarity、复用多数 Knowledge 或标题相近都不能构成演化。若只有内容来源关系，使用 `provides_foundation_for`或具体 Knowledge Relation。

## 5.4 provides_foundation_for

合法 path patterns：

```text
A.core Knowledge --provides_foundation_for--> B.core / bridge Knowledge
A.core principle --supports / explains--> B 的多个主要设计判断
A Overview 明确定位 --被 B Overview / representative Knowledge 采用--> B
```

必须排除：

- 只有引用，没有基础角色；
- B 只在一条边缘注释中提到 A；
- A、B 相互引用但方向不明；
- 只有一次 Ask route 把二者同时取回；
- B 使用 A 的一个案例，但不依赖 A 的理论 / 原则。

## 5.5 provides_method_for

必须区分：

- `提到一种方法`；
- `解释一种方法`；
- `在目标群的任务中实际采用该方法`。

只有第三种能形成 core path。若方法只用于一个 named target Topic，Candidate 必须限定该 Topic scope，不能把整个 B 写成“由 A 提供方法”。

## 5.6 applies_to

`applies_to`最容易被滥用为泛化关系。Candidate 必须回读：

> A 中的 {principle / model / rule / method} 适用于 B 中的 {task / population / condition / time}。

如果无法填写两个花括号，保持具体 Knowledge Relation。Group-level statement 的 from / to 仍是 Groups，但 Applicability 必须携带内部 role anchors。

## 5.7 Comparison family：contrasts / complements / challenges

`contrasts_with` 必须拥有 Comparison Contract：

```text
comparison_dimension
shared_question
overlapping_applicability
A_position / approach
B_position / approach
material_difference
```

两个 Groups 讨论不同问题、时间或人群，不构成 contrasts。若表面冲突来自 Applicability 不同，优先生成 comparison view 或 `qualifies` paths，而不是群级对照边。

`complements` 必须同时证明共同 goal / question、A / B 不同 contribution roles、nonredundancy 与 combined value。共同出现、没有冲突或 Boundary overlap 都不足以成立。

`challenges` 必须证明 challenger → challenged direction、被挑战 assertion / assumption / method、overlapping Applicability、challenge mechanism 与 effect。采用 Candidate 不自动改变被挑战 Group 或 Relation disposition；具体对象继续通过 RelationChallenge / Claim review 处理。

## 5.8 partially_overlaps_with

`partially_overlaps_with`表达两个独立范围在重要语义维度上部分相交，但互不包含且仍有各自 material Boundary。Group-level `overlaps_with` deprecated。

至少证明：

- 两个 Effective Support Units；
- overlap scope 与双方 boundary differences；
- units 不只是同一共享 Knowledge 的复制；
- 支撑触及两侧核心或 named subscopes；
- Inspector 能说明重叠在哪里、边界仍在哪里不同；
- overlap 不被误写成 merge suggestion。

## 5.9 shared_core_knowledge Observation

`shares_core_knowledge_with` 不再是 formal type。只有 canonical Knowledge 在两侧都承担 core / representative role 时，才进入 `shared_core_knowledge` GroupConnectionObservation。一个 Knowledge 在 A 为 core、在 B 只是 background reference，不满足双侧核心观察。

默认需要：

- 至少两个不同 canonical Knowledge identities；或
- 一个被用户明确策展为两侧 stable start / representative 的 Knowledge，加一条独立 core assertion；
- 两侧 Placements 都是 current；
- 删除其中任一 Placement 的影响可解释。

Observation 自动刷新，不创建 Candidate、RelationRevision 或 Review Case，不进入 Relation count 与 Current / Suggested / History。它可以作为 partial overlap、foundation 或其他 Candidate 的 basis，但永远不是充分条件。

## 5.10 influences / constrains

这两类关系不能由 citation count 或 temporal order 推出：

- `influences`需要明确机制或多条一致的 directional typed Relations；
- `constrains`需要 A 的规则、资源、限制或边界实际减少 B 的可行选择；
- 若 foundation、method、applies、challenges 或 constrains 已准确表达同一 mechanism，不再保存 broad `influences` duplicate；
- system-generated `influences` Candidate 默认 on-demand only；
- “先出现”不等于 influence；
- “经常被提到”不等于 constrain；
- reciprocal influence 应保留两条 directional Relations 或使用明确 symmetric type，不把双向箭头当装饰。

---


# 6. Candidate 形成、呈现与采用

## 6.1 三种触发方式

### Ambient discovery

后台发现稳定模式，只有 outcome=`eligible_ambient_candidate`且通过 attention budget 时，才在用户进入相关 Group / Suggested layer 时提供一条安静 Cue。

### User-invoked comparison

用户选择两个 Groups 并问`它们有什么关系`。系统可以展示：

- 当前正式 Group Relations；
- 可走的 cross-group exits；
- eligible_on_demand Candidate；
- 为什么当前不足以形成 Group Relation。

它不因用户提问自动创建 Candidate identity，除非用户选择`保存为关系建议`。

### Import / source-explicit

带类型数据或来源明确群级陈述进入 Candidate Preview，保存 original predicate、source statement 与 mapping；它不冒充 Aggregated，也不自动进入 Current。

## 6.2 Candidate Card 的 P0 内容

默认卡片只显示：

1. 完整群级关系句；
2. `为什么可能成立`的一句解释；
3. Boundary coverage：`覆盖两个群的核心`、`一个核心向另一群多个方向展开`或`只适用于指定子范围`；
4. `通过 N 组有效路径相连`，其中 N 是去重后的 units，不是原始边数；
5. 最重要 limitation / counter-signal；
6. `检查`、`稍后`、`不再建议`。

卡片不显示：

- 置信度百分比；
- 图算法 edge weight；
- embedding distance；
- `AI 认为很相关`；
- 原始 path count 冒充充分性；
- Accept all。

## 6.3 Candidate Inspector 的阅读顺序

1. **建议的关系是什么**：statement、type、direction、Applicability；
2. **为什么是群级而非局部路径**：BoundaryCoverageFootprint；
3. **通过哪些独立知识相连**：Effective Support Units；
4. **哪些线被折叠或排除**：origin clusters / exclusions；
5. **是否存在限制或反例**：CounterSignals；
6. **去掉最强依据会怎样**：removal test；
7. **采用后改变什么**：Current Network、Ask expansion、Overview projection；
8. **动作**：修改、采用、保存稍后、拒绝。

## 6.4 修改 Candidate

用户可以：

- 改 relation type；
- 改 direction；
- 重写 statement；
- 收窄 Applicability；
- 排除不相关 path；
- 补充自己的 rationale / Evidence；
- 将一条 counter path 改为 exception；
- 把群级 Candidate 降回 Saved Path / comparison view。

任何会改变 semantic fingerprint 的修改都重新运行 type、coverage、direction 与 counter gates。用户仍可选择 Direct Commit，但界面必须说明它已经从“系统聚合建议”变成“你的群级判断”。

## 6.5 采用

采用后：

- 创建独立 Group Relation identity；
- 创建首个 RelationRevision；
- 创建首个 GroupRelationSupportSetRevision；
- 保存 Candidate adoption event；
- 保存 Boundary Revision refs 与 Assessment；
- Candidate 从 Suggested layer 退出；
- Relation 以 maintained + lifecycle=current 进入 Current Network；
- 下游 Overview / Ask / Search 只在各自规则下使用，不自动改写正文。

采用不执行：

- 合并底层 Knowledge；
- 锁死 Placements；
- 把 supporting paths 改成 Evidence ownership；
- 删除 exits；
- 自动提升 Network 显著性；
- 将 Candidate 的模型置信度保存为 truth。

## 6.6 稍后与拒绝

- `稍后`：Candidate 保留但不产生常驻 badge；只在 Suggested / pair Inspector 中出现；
- `不再建议`：保存 fingerprint suppression；
- `不是群关系，只是路径`：Candidate dismissed，并保留 exits；
- `类型不对`：可以只抑制当前 type fingerprint，允许新语义 Candidate；
- `这两个群本来就该合并`：进入 Group identity / merge assessment，不创建 Relation。

拒绝必须零 Current 副作用；它不删除底层 Knowledge Relations 或路径。

## 6.7 Candidate 过期与重评

以下变化可以使 Candidate 过期或要求重评：

- 任一 Group Boundary 重大变化；
- core / representative curation 改变；
- supporting Relation ended / superseded / retracted；
- Applicability 不再重叠；
- Policy Revision 改变；
- endpoint split / merge；
- 新 CounterSignal 改变类型或方向。

过期 Candidate 不转成 retracted Relation，因为它从未是 Relation。系统保留 Assessment history，并重新回到 Signal / exit-only / new Candidate。

---


# 7. Support Set 与正式关系的长期维护

## 7.1 Support Set 必须保存什么

在原 `GroupRelationSupportSetRevision` 基础上补充：

```text
GroupRelationSupportSetRevision
  support_set_revision_id
  group_relation_ref
  target_relation_revision_ref
  previous_support_set_revision_ref?

  included_effective_support_units[]
  origin_clusters[]
  boundary_coverage_footprint_ref
  counter_signal_refs[]
  exclusion_records[]
  strongest_unit_removal_result
  policy_revision_ref

  assessed_by
  assessed_at
  change_reason
```

Support Set 不是一袋 IDs。它保存当时怎样从 paths 得到群级判断，并允许未来解释：为什么同样七条可见线，系统只算成两组有效支撑。

## 7.2 变化传播矩阵

| 变化 | Support Set | RelationRevision | Relation standing |
|---|---|---|---|
| 新增同源重复 excerpt | 记录折叠；可不创建新 Revision | 不变 | no_material_change |
| 新增独立 corroborating unit | 新 SupportSetRevision | 不变 | changes_available 或无提示 |
| core unit 有等价 successor | 新 SupportSetRevision | statement 不变则不改 | review_due |
| strongest unit 被撤回，仍满足 gates | 新 SupportSetRevision | 不变 | review_due，可 Maintain |
| removal 后退化为 anchor-dependent | 新 SupportSetRevision | 可能收窄 Applicability | review_due |
| 只剩 fringe / duplicate | 新 SupportSetRevision | 不自动改 | review_due，要求 End / Revise / Retract 判断 |
| Boundary 收窄，named subscope 仍成立 | 新 footprint | 新 RelationRevision | maintained |
| Boundary 改变导致方向 / type 变化 | 新 assessment | 创建 successor Relation | old superseded / retracted |
| 新 CounterSignal 同范围冲突 | 新 SupportSetRevision + Challenge | 不自动改 | review_due |

## 7.3 Maintained 不要求永远满足“主动建议门槛”

系统建议门槛约束 Candidate creation；用户已经采用的 Relation 是独立知识陈述。后来支撑减少时：

- 不静默撤回；
- 不因为少于两个 units 立即消失；
- 不自动降回 Candidate；
- 显示“当前主要依赖一组路径”或“当前支撑只覆盖指定子范围”；
- 用户可以 Maintain、收窄、换支撑、End、Supersede、Retract 或 Archive。

这避免系统用变化中的算法重新决定用户“是否曾经拥有”一条关系。

## 7.4 Boundary Change

任一 Group Boundary Revision 变化后：

1. 旧 Support Set 与 footprint 保持历史；
2. 新 Assessment 使用新 Boundary Revision；
3. 若只影响显著性，不改变 statement，更新 Support Set；
4. 若使 statement 只适用于 named subscope，创建 RelationRevision；
5. 若 governing purpose 不连续，进入 RelationTransitionCase；
6. Current Network 在 unresolved transition 时不静默 retarget。

## 7.5 Policy Change

聚合 Policy 更新不能批量撤回既有 Relations。它可以：

- 对新 Signals 使用新规则；
- 将既有 Aggregated Relations标为 changes_available；
- 生成批量影响摘要；
- 允许用户逐项 / 按同类模式 review；
- 保留采用时 Policy Revision 与 Assessment。

产品不得因模型升级让整张 Network 一夜重排而没有解释。

---


# 8. Library Network、Group Map 与 Inspector

## 8.1 Group Map 负责 exits，Library Network 负责群级真相

Group Map / Topic Reading 可以持续显示真实 cross-group exits：

```text
当前 Knowledge
  → maintained Knowledge Relation / Reference / Saved Path step
  → 目标 Knowledge / Placement
  → 目标 Group
```

它不需要等 Group Relation 才可探索。这样产品不会为了让跨群路径可见而放松群级门槛。

Library Network 则只承载：

- Groups；
- maintained current Direct / adopted Aggregated Group Relations；
- 用户显式打开的 Suggested layer；
- 用户显式打开的 History layer；
- 当前 Query Highlight overlay。

## 8.2 没有群关系不是缺陷状态

两个 Groups 之间有 12 条 exits，但没有任何 Candidate 通过资格门时：

- Group Map 仍可沿具体知识探索；
- Library Network 不画正式边；
- List Equivalent 可以写`当前没有群级关系；存在 12 条具体跨群路径`；
- 用户可以查看路径、主动比较或直接建立自己的 Group Relation；
- 产品不显示警告、完整度、孤立分数或`还差 1 条`。

## 8.3 Suggested layer

Suggested 是用户明确打开的图层，不是 Current edge 的虚线变体。

每条 Candidate 必须在图上同时表达：

- `建议`文字；
- relation statement；
- coverage shape；
- strongest limitation；
- Inspect action；
- 关闭 Suggested 后完全退出布局影响。

Candidate 不参与：

- Group degree；
- resting layout；
- default neighbour count；
- Ask current truth；
- Overview formal relation projection；
- Network completeness metric。

## 8.4 Current layer

Current edge 只说明用户当前采用了 Group Relation，不说明：

- Evidence 一定充分；
- Support Set 一定 robust；
- 没有 Challenge；
- relation 一定由 aggregation 形成；
- edge 一定高重要性。

review_due Current edge继续可见，并用一句话说明`主要依据发生变化，需要检查`。如果当前 scope 排除了其 Applicability，它不出现；这不是 Relation 被删除。

## 8.5 History layer

History 可以显示：

- ended；
- superseded + successor；
- retracted；
- archived；
- old RelationRevision；
- old SupportSetRevision；
- 当时采用所依据的 Assessment。

History edge 必须显著区别于 Current，并且不能参与默认 shortest path、neighbour count 或 current Ask expansion。

## 8.6 Group Relation Inspector 增补

Inspector 固定顺序：

1. 完整 relation statement；
2. `为什么这是一条群级关系`；
3. 当前 Boundary scope；
4. Effective Support Units；
5. 原始 paths 中哪些被折叠 / 排除；
6. CounterSignals / exceptions；
7. strongest-unit removal；
8. formation basis 与 adoption event；
9. current disposition / change / lifecycle；
10. affected Overview / Ask / Paths；
11. History / successor；
12. 继续探索。

正式 Relation Inspector 不需要把九道 gate 持续显示成审核表。它们在`为什么这条群关系成立`与 Advanced / History 中渐进披露。

## 8.7 Relation Bundle

同一 Group pair 可以同时拥有：

- `provides_foundation_for`；
- `contrasts_with`；
- 一个 named-subscope `applies_to`；
- 一个 Candidate；
- 两条 historical Relations。

Bundle 只负责折叠呈现：

- Current members 与 Suggested / History 分区；
- 每个 Current member 独立 statement；
- 不把五条不同关系合成`强关系`；
- 不把 path count 加总为 edge weight；
- 默认展示 pinned 或当前任务相关 member，并写`另有 N 条当前关系`。

## 8.8 Graph / List 等价

List Equivalent 必须可完成：

- 区分 exit / Candidate / Current / History；
- 阅读完整 statement 与 direction；
- 查看 coverage shape；
- 展开 Effective Support Units；
- 查看折叠 / 排除原因；
- 检查 CounterSignals；
- 修改 / 采用 / 拒绝 Candidate；
- 进入 endpoint Group / supporting Knowledge；
- 恢复 Back / filter / selection。

若图能表达“哪条边更亮”，列表必须用文字说明“为什么现在显示”。

---


# 9. Ask、Search、Overview 与 Saved Path

## 9.1 Ask：问“这两个群有什么关系”

回答结构固定为：

1. **当前正式关系**：maintained current Group Relations；
2. **具体连接路径**：cross-group Knowledge exits；
3. **可能的群级关系**：仅在允许展示 Candidate 时单独列出；
4. **限制与未知**：Boundary、partial index、CounterSignals、Source availability；
5. **动作**：进入 Group、沿具体 path 探索、检查 Candidate。

没有正式关系时，回答应说：

> 当前没有你已采用的群级关系；我找到了三组具体知识路径，其中两组支持一个可能的限定关系。

它不能写成`这两个群没有关系`，也不能把本次综合直接保存为 Relation。

## 9.2 Ask expansion

正式 Group Relation 可以作为 scope expansion route，但必须：

- 读取 RelationRevision 的 Applicability；
- 保留 expansion reason；
- 再进入具体 supporting Knowledge，而不是把群级 edge 当事实来源；
- review_due / Challenge 在相关 Claim 中说明；
- historical Relation 只有 as-of / history query 使用。

Candidate 不进入默认 Ask truth。用户显式选择`也考虑建议关系`时，Answer Basis 标为 `Candidate`，不能写成`来自你的当前知识`。

## 9.3 Search

Search 可以找回：

- current Group Relation statement；
- Candidate statement；
- supporting Knowledge；
- historical Relation；
- exact Group pair；
- `为什么被折叠`等 Inspector metadata 的 owner-first result。

普通结果默认 current-first。Candidate、History、exit-only 分别过滤；原始 path 命中聚合到 owner，不让同一支撑复制十条结果。

## 9.4 Overview

Group Overview 的正式关系 projection 只使用 maintained current Group Relations。它可以显示：

- `与哪些知识群真正相连`；
- 一句 relation statement；
- named subscope 限定；
- 进入 Group / Inspector / supporting path。

Candidate 只能在 contextual suggestion 中出现，不写进 Editorial prose。Cross-group exit 可以在相关 Knowledge / Topic 区块写`通向另一个知识群`，不能冒充群级关系。

Support Set 变化时：

- statement 未变 → Overview prose 不自动改；
- review_due → 相关 projection 显示一句 notice；
- Applicability 收窄 → 生成 Overview Semantic Diff；
- superseded / retracted → current projection 退出或切 successor，但旧 Overview revision 保留引用。

## 9.5 Saved Path

Saved Path 可以保存：

- 具体 cross-group exits；
- current Group RelationRevision；
- Query overlay 中的 manually chosen step；

它不能因路线跨过两个 Groups 自动创建 AggregationSignal 的用户待办。若保存时经过 Candidate，step 必须写 `candidate_ref + saved_statement`；Candidate 后来 dismissed 时，Path 仍保留当时路线但说明 current standing。

## 9.6 Export / Restore

完整本地包至少保存：

- GroupRelationAggregationPolicy revisions；
- Candidate / suppression fingerprints；
- adopted Assessments；
- Effective Support Units 与 origin clusters；
- BoundaryCoverageFootprints；
- exclusions / CounterSignals；
- SupportSetRevisions；
- Relation / Revision / Decision / Transition history。

纯 Derived AggregationSignals 与计算缓存可以选择不导出，只要能从 canonical paths、Boundaries 和 Policies 重建。Restore 后不得因为重新计算顺序不同而自动新增 Current Relations。

---


# 10. 产品语言与渐进披露

## 10.1 P0 用户语言

推荐：

- `通向另一个知识群`：cross-group exit；
- `可能是群之间的关系`：Candidate；
- `为什么可以上升为群关系`：eligibility explanation；
- `通过 2 组独立知识相连`：Effective Support Units；
- `其中 4 条线来自同一知识 / 来源`：collapse explanation；
- `只适用于两个群中的这个范围`：named subscope；
- `主要依赖一组核心知识`：anchor-dependent；
- `当前存在相反依据`：conflicting；
- `群之间的关系`：maintained current Relation。

避免：

- `关系强度 82%`；
- `边权 0.82`；
- `AI 置信度高`；
- `检测到 7 条关联，因此已建立群关系`；
- `弱关系 / 强关系`；
- `孤立群`；
- `关系缺失`；
- `接受全部`。

## 10.2 P1 资格说明

资格说明使用三句话预算：

```text
为什么像一条群关系：A 的核心原则在 B 的三个主要设计判断中被实际使用。
为什么不是重复计数：六条可见路径折叠为三组不同判断，来自两个来源脉络。
最重要限制：当前只覆盖 B 的长任务状态设计，不适用于全部 Agent 产品问题。
```

## 10.3 P2 Inspector

显示 support shape、origin clusters、exclusions、CounterSignals、removal result、Boundary Revision、Policy Revision 与 adoption impact。

## 10.4 P3 Forensic

显示完整 IDs、semantic fingerprints、path revisions、collapse events、Assessment diff、policy migration、actor、timestamp 与 export form。普通用户不需要先理解这些词。

---


# 11. 代表场景

## 11.1 七条线其实只有一个事实

`AI Agent 产品设计`与`认知科学`之间可见七条 paths：三个来自同一 Knowledge 的 Placements，两个是同一 Relation 的 inverse reading，两个引用同一报告。系统折叠为一个 Effective Support Unit，不提出 Candidate；Group Map 仍显示可走 exits。

## 11.2 两个独立基础机制

认知科学中的`工作记忆限制`与`线索依赖回忆`分别支撑 Agent 产品设计中的`长任务状态呈现`和`Resume cue`。它们来自不同 Knowledge assertions，触及 source Group core 与 target Group 两个核心方向。系统提出 named-subscope `provides_foundation_for` Candidate。

## 11.3 一个核心方法，多处实际应用

`用户研究方法`中的任务分析框架，在`AI Agent 产品设计`的 onboarding、long-running task 和 recovery 三个核心 Knowledge 中被实际使用。形成 anchor-and-spread `provides_method_for` Candidate。若三处只是引用方法名而没有采用记录，则保持 exits。

## 11.4 相似但不是 partial overlap

两个 Groups 都含`记忆`标签，但一个讨论人类记忆，一个讨论存储硬件。embedding 很近，Boundary 与 comparison dimension 不一致。Signal outcome=`exit_only / ambiguous_type`，系统不建议 partial overlap。

## 11.5 一条共享核心 Knowledge

同一 canonical Knowledge 在两个 Groups 都是 representative。它是强信号，但仍只有一个 content identity。若没有第二个独立 assertion，Candidate 仅在用户主动比较时显示为 anchor-dependent；不进入 ambient Suggested。

按新 Type Registry，它同时形成一项`当前共享 1 条核心知识`的 derived Observation；Observation 不需要 Candidate 门槛，也不进入 formal Relation layer。

## 11.6 同一报告的多篇转述

五篇笔记引用同一原始研究。系统将五个 Sources 折叠到一个 study / source lineage，保留各笔记的不同解读，但不写`五份独立证据`。

## 11.7 方向相反

A→B 有两条 paths，B→A 有两条 paths。系统不按数量平局创建双向箭头；它检查是否为 reciprocal influence、两个不同 Applicability，或 type ambiguous。必要时形成两条独立 Candidates。

## 11.8 核心反例

三个 paths 支持 A provides_method_for B，但 B Overview 明确说明该方法只用于历史方案、当前已弃用。若时间范围不同，Candidate 收窄为 historical；若同范围冲突，outcome=`conflicting`。

## 11.9 用户坚持建立

系统 Assessment 认为只有 fringe support，用户仍明确写出群级 Relation。产品允许 Direct Commit，显示`你的判断；当前支撑主要来自一个局部范围`，并保留系统 Assessment 作为 context，不与用户争夺所有权。

## 11.10 Boundary 收窄

B 从“AI Agent 产品设计”收窄为“企业 Agent 的可逆任务体验”。旧 foundation Relation仍可能成立，但 CoverageFootprint 与 Applicability 必须重评；若只影响 scope，创建 RelationRevision，不新建 edge identity。

## 11.11 Group Split

B split 为 B1、B2。旧 Support Set 显示两组 units 只落在 B1，一组无法判断。系统只为 B1 创建 successor Candidate；B2 无边；旧 Relation进入 TransitionCase，历史仍可解释。

## 11.12 Policy 更新

新 policy 禁止用 citation paths 支撑 `influences`。既有 Relation不被批量撤回；系统显示受影响摘要，把 citation-only units 标为 excluded，Relations进入 changes_available / review_due。

## 11.13 没有关系的高价值探索

用户从 A 沿三条具体 exits 到 B，保存一条跨群 Path，但不认为两群整体有稳定关系。产品完整保存路线和返回现场，不要求建立 Group Relation。

## 11.14 AI 不可用

用户仍能查看 current Group Relations、Support Set、exits、History，并直接建立或修改 Relation。后台不产生新 Assessment；已有 Candidate 明确标记`当前无法重新评估`。

---


# 12. 极端状态与失败恢复

## 12.1 10,000 条 raw paths

系统先按 group pair、assertion/content/source/traversal lineage 分区；UI 不加载全部路径。Candidate Inspector默认显示 Effective Units、每个 cluster 的折叠数量与最强 exclusions；用户按需进入原始 paths。

## 12.2 1,000 个 Signals

Signals 不形成 inbox。只有用户当前 scope 内通过 G0–G9 的少量 Candidates出现；其余可重建。没有`待建立 1,000 条关系`。

## 12.3 一个 Group pair 有 30 种 possible types

系统按 relation family 与 Applicability 折叠；类型无法明确时不生成 30 张 Candidate cards。用户主动比较时先显示当前 formal Relations、主要 exits 与`尚不足以形成明确群级类型`。

## 12.4 Partial Index

Assessment 标记 coverage incomplete，不得写`没有反例`或`已覆盖两个群`。既有 Current Relations保持；新 ambient Candidate 暂缓，user-invoked结果明确`仅检查了当前已索引范围`。

## 12.5 Source unavailable

本地 snapshot 可核验时继续计入 provenance cluster；仅远程引用不可用时标记 availability。它不自动增加或减少 Effective Unit 数，只影响核验说明与 review。

## 12.6 Concurrent Boundary edits

Assessment 在 Boundary Revision N 上完成，用户在采用前将 Group 改到 N+1。提交前必须 rebase coverage；若结果改变，显示 diff，不以旧 Assessment 创建 Relation。

## 12.7 Offline

本地已有 policies、Boundaries、Relations 与 indexes 时可以运行有限 Assessment；需要远程 Source / AI 的部分标记 unknown。Offline 不自动降低门槛或用 embedding shortcut 补齐。

## 12.8 Failed adoption

Relation identity、Revision、Support Set 与 adoption event 必须事务化。任一失败：

- Candidate 保持 open；
- Current Network不出现半条边；
- retry 使用同一 idempotency key；
- exits、paths 与用户修改不丢失；
- 错误不写成`关系未通过`。

---


# 13. Given / When / Then 验收合同

## 13.1 同一 Knowledge 多 Placements 不重复计数

**Given** 同一 canonical Knowledge 在 Group A 有两个 Placements、在 Group B 有一个 Placement，并形成三条可见路径  
**When** 系统评估 Group Relation eligibility  
**Then** 三条路径折叠为一个 content lineage 与至多一个 Effective Support Unit；不因 Placement 数提出 Candidate。

## 13.2 Inverse relation 不重复计数

**Given** A Knowledge `provides_foundation_for` B Knowledge，从 B 侧显示 inverse `builds_on`  
**When** 两种读法同时出现在 paths 中  
**Then** assertion cluster 只计一个 unit；Inspector 可以从两侧回读，但不显示“两条独立依据”。

## 13.3 同一来源多报告不双计

**Given** 三篇笔记和两个网页都转述同一原始研究  
**When** Candidate 资格依赖这些材料  
**Then** 系统保留五个 records，但折叠为一个 provenance cluster；若没有其他独立 assertion，不能写`多份独立依据`。

## 13.4 Query 共现不升级

**Given** Ask 连续五次同时使用 Group A 与 B  
**When** 系统观察跨群路径  
**Then** Query Routes只形成 traversal signal；不创建 Effective Support Unit、Candidate、Group Relation 或 attention badge。

## 13.5 至少两个 units 仍不等于通过

**Given** 两个独立 units 都来自 Group B 的 fringe Topic  
**When** 数量达到默认下限  
**Then** G5 失败，outcome=`exit_only`；Group Map保留 exits，Suggested layer不出现 Candidate。

## 13.6 Bilateral partial overlap

**Given** 两侧各有 representative Knowledge，且两个独立语义维度重叠  
**When** Policy 允许 `partially_overlaps_with` aggregation  
**Then** Candidate 显示 bilateral-core coverage、重叠范围、双方 Boundary differences 与 containment check；不建议 merge，也不使用 generic related_to。

## 13.7 单共享 Node 只形成结构线索

**Given** 一个 canonical Knowledge在两侧都出现并承担 core role  
**When** 没有第二个独立 assertion 或 curated bilateral anchor 证据  
**Then** 形成`当前共享 1 条核心知识`的 derived Observation，但不形成 partial-overlap Candidate；多个 Placements 不重复计数，Current Network 不新增 formal edge。

## 13.8 Anchor-and-spread foundation

**Given** A 的一条 curated core principle分别支撑 B 的三个独立主要判断  
**When** paths 在方向、Applicability 与实际使用上都一致  
**Then** 系统可提出 `provides_foundation_for` Candidate；显示一个 source anchor、三个去重 target uses 与 removal result。

## 13.9 提到方法不等于使用方法

**Given** B 的三篇 Knowledge都引用 A 的方法名，但没有应用记录  
**When** 系统评估 `provides_method_for`  
**Then** type-fit gate失败；保持 references / exits，不把引用次数解释为方法提供关系。

## 13.10 scope_within 禁止聚合

**Given** A 中多数 Knowledge也能放入 B  
**When** 系统检测成员重叠  
**Then** 不创建 `scope_within` Candidate；只能提出 Boundary comparison或由用户明确建立范围关系。

## 13.11 evolved_from 需要 lineage

**Given** A、B 标题相近且共享大量 Knowledge，但没有 successor / transformation history  
**When** 系统评估 `evolved_from`  
**Then** Policy forbidden；不创建演化关系，必要时建议 identity duplicate / merge review。

## 13.12 contrasts 需要共同比较维度

**Given** A、B 得出不同结论，但回答的问题与人群不同  
**When** 系统尝试形成 `contrasts_with`  
**Then** Applicability / comparison gate失败；产品生成 comparison view或并列 scope，不创建群级对照边。

## 13.13 方向分裂

**Given** 两个 units 支持 A→B，两个 units 支持 B→A  
**When** relation type不是 symmetric  
**Then** 系统不按数量选择方向；形成两个更窄 Assessments或返回 ambiguous_type，并说明 reciprocal possibility。

## 13.14 核心 CounterSignal

**Given** 三个 supporting units 与一个同 Applicability core counter unit  
**When** Counter scan 完成  
**Then** outcome=`conflicting`；不能以三比一通过，Candidate Inspector显示双方 statement与来源。

## 13.15 不同 Applicability 不制造冲突

**Given** support适用于新用户，counter只适用于长期用户  
**When** 比较范围  
**Then** 系统生成 qualifiers / parallel scopes；可以形成限定 Candidate，不写`存在相反依据`的全局警告。

## 13.16 Strongest-unit removal 仍成立

**Given** Candidate 有三个 Effective Support Units  
**When** 移除贡献最大的 core unit后仍满足 type与bilateral coverage  
**Then** outcome可为 eligible_ambient_candidate；UI说明仍有两组独立支撑，不显示置信度分数。

## 13.17 Strongest-unit removal 后失效

**Given** Candidate 有一个 core unit和两个同范围 corroborating units  
**When** 移除 core unit后只剩 fringe coverage  
**Then** Candidate只能 on-demand显示为 anchor-dependent；ambient Suggested不出现。

## 13.18 User Direct 不受聚合门槛阻止

**Given** 用户在两个 Groups 上完成完整 statement、type、direction、Applicability与why it matters，但只有一个 path  
**When** 本地提交成功  
**Then** 创建 maintained current user-asserted Relation；界面说明支撑有限，不要求虚构第二条路径或额外 Accept。

## 13.19 Source-explicit 仍是 Candidate

**Given** 一份来源直接声称 Field A 为 Field B 提供理论基础  
**When** 系统抽取该群级陈述  
**Then** 创建 source-explicit RelationCandidate；不当作 Aggregated，也不因来源可靠自动进入 Current。

## 13.20 Candidate adoption 原子提交

**Given** 用户修改 Candidate 的scope并采用  
**When** Relation、Revision、SupportSet或DecisionEvent任一步写入失败  
**Then** Current Network不出现半条边；Candidate与用户修改保留，可用同一幂等键重试。

## 13.21 Candidate dismissal 保留 exits

**Given** 用户选择`不是群关系，只是具体路径`  
**When** Candidate dismissed  
**Then** suppression保存，Candidate退出Suggested；底层Relations、Knowledge、exits和Saved Paths都不删除。

## 13.22 新重复证据不重提

**Given** 用户已拒绝某 fingerprint  
**When** 新增三个同来源摘录和一次新的图布局  
**Then** Candidate不重提；只有新 assertion、Boundary或Applicability产生实质差异时才允许新评估。

## 13.23 Boundary Revision rebase

**Given** Candidate assessment基于Boundary Revision 4，用户采用前目标Group已到Revision 5  
**When** 点击采用  
**Then** 系统重新评估coverage并显示diff；不能用旧footprint直接物化Relation。

## 13.24 Maintained Relation 失去门槛

**Given** 已采用Aggregated Relation后来只剩一个有效unit  
**When** Support Set重评  
**Then** Relation保持独立knowledge identity并进入review_due；不自动撤回、消失或降回Candidate。

## 13.25 Ask 不制造关系

**Given** 用户问`这两个群有什么关系`，当前没有formal relation但有多个exits  
**When** Answer生成  
**Then** 分开写当前关系、具体路径、可能Candidate与未知；关闭Answer后Current / Suggested均不新增对象，除非用户显式保存。

## 13.26 Suggested 不影响 Current layout

**Given** 同一scope有20个eligible Candidates  
**When** 用户关闭Suggested layer  
**Then** Network恢复只由Current Relations决定的位置、degree、neighbour count与filters；Candidates不留下虚线或空洞。

## 13.27 Graph / List 等价

**Given** 一个Candidate为named-subscope、anchor-dependent并有CounterSignal  
**When** 用户在Graph、List、mobile和keyboard-only模式检查  
**Then** 四种表面都能读取完整statement、coverage、限制、有效units、采用 / 拒绝动作与返回目标；信息不只靠颜色和线型。

## 13.28 无缓存恢复

**Given** graph cache、Signals与ranking全部删除  
**When** 从本地Knowledge Package恢复  
**Then** Current Group Relations、Revisions、SupportSets、adopted Assessments、Boundary refs与suppression可重建；系统不会自动采用新Candidate。

---


# 14. 指标与反指标

## 14.1 核心结果指标

| 指标 | 定义 | 验证什么 |
|---|---|---|
| Group-level Statement Comprehension | 用户能否复述边表达的是两个群整体的什么关系 | 边是否超越视觉关联 |
| Cross-level Elevation Precision | adopted Aggregated Relations 中满足type、coverage与support规则的比例 | 局部路径是否被误升 |
| Exit–Relation Distinction | 用户能否区分可走路径与群级陈述 | Group Map / Network分工是否成立 |
| Effective Support Traceability | 用户能否从“N组支撑”进入具体units并理解折叠 | 去重是否可解释 |
| Boundary Coverage Comprehension | 用户能否说清关系覆盖整群、核心锚点还是named subscope | qualifier是否可见 |
| Candidate Reversal Rate | 采用后短期内因“并非群关系”而撤回的比例 | 建议门槛是否准确 |
| Missed Important Relation Rate | 用户主动建立的高价值Group Relation中，系统长期只有exit而未能合理suggest的比例 | 门槛是否过度保守 |
| Support Review Resolution | 支撑变化后能否通过Maintain / Revise / End等结束review | lifecycle是否可维护 |
| Suggestion Attention Cost | 每次真正采用或高价值检查所需忽略的Candidates数量 | Suggested是否制造噪声 |

## 14.2 诊断指标

- raw path → Effective Unit collapse ratio；
- source lineage duplicate ratio；
- fringe-only signal rate；
- ambiguous type rate；
- strongest-unit dependency rate；
- Candidate dismissed as exit-only；
- Candidate scope narrowed before adoption；
- CounterSignal discovered after adoption；
- Boundary change rebase rate；
- Graph / List action parity；
- Ask-created-object zero-side-effect rate。

这些指标用于发现问题，不成为用户评分或自动 truth threshold。

## 14.3 反指标

产品不优化：

- Group Relation总数；
- Candidate总数；
- Candidate接受率；
- Network密度；
- 平均degree；
- 每日新增边；
- 自动聚合覆盖率；
- path count；
- 视觉连通率；
- `孤立Group减少量`。

一个只有少量群关系但每条都可解释、可维护的Library，比一张高度连通的相似度图更成功。

---


# 15. 官方研究事实、产品推论与证据边界

## 15.1 SKOS：路径组合默认不产生新关系

W3C SKOS 明确区分 exact、close、broad、narrow 与 related mapping。除 `exactMatch` 外，`closeMatch`、`broadMatch` 与 `relatedMatch`都没有自动 transitive entailment；规范甚至给出 A broadMatch B、B broadMatch C 不推出 A broadMatch C 的 non-entailment 示例。[SKOS Reference](https://www.w3.org/TR/skos-reference/)

**产品推论：** 多条成员级关系不会仅因为形成路径就自动推出新的群级 Relation。若某 path pattern有资格产生 Candidate，必须在 relation-type Policy中明确声明，而不是交给通用图遍历。

## 15.2 OWL 2：Property Chain 需要显式规则

OWL 2 支持 property-chain axiom：只有明确声明一组 property chain 是另一个 property 的 sub-property，链式事实才按该语义规则产生新 entailment。[OWL 2 Structural Specification](https://www.w3.org/TR/owl-syntax/)

**产品推论：** 本产品的 `GroupRelationAggregationPolicy`类似“允许哪些 typed paths 支撑哪一种群级 Candidate”的产品规则；它不是自动 truth，也不意味着用户界面或存储必须使用 OWL。

## 15.3 PROV-O：Collection membership 与 derivation 可分别追踪

W3C PROV-O 使用 `hadMember`表达 collection membership，并将 derivation、revision、primary source等关系分开；它允许集合、成员和派生历史分别保留 provenance。[PROV-O](https://www.w3.org/TR/prov-o/)

**产品推论：** Group membership / Placement 不能本身推出 Group Relation；Aggregated Relation 的 Support Set应保留成员 paths、来源与 Assessment history，但它仍是独立 assertion。

## 15.4 SHACL：验证条件与推断写入是不同责任

W3C SHACL Core用于描述和验证图数据是否满足一组 constraints，验证过程产生独立 Validation Report，并要求验证期间数据图保持不变；SHACL Advanced Features则把新增 inferred triples作为独立 rules-engine能力。[SHACL](https://www.w3.org/TR/shacl/) · [SHACL Advanced Features](https://www.w3.org/TR/shacl-af/)

**产品推论：** 九道资格门首先产生 Assessment，不直接写 Relation。通过 shape / eligibility与真正创建 Candidate、采用Relation是不同事件。

## 15.5 Cochrane：多个报告不等于多个独立研究

Cochrane Handbook要求把同一study的多个reports关联并合并，以study而不是report作为分析单位；把多个reports当作多个studies会产生重复计数和偏差。[Cochrane Handbook Chapter 4](https://training.cochrane.org/handbook/current/chapter-04)

**产品推论：** 多个Source records可能只是一个origin。本产品折叠source lineage，同时保留各report提供的不同细节；这是一种防止伪多样性的产品类比，不把Cochrane的方法学门槛直接移植到所有个人知识。

## 15.6 跨层推断需要谨慎

统计研究长期记录了个体层与群体层关系可能不同，跨层外推会受aggregation bias、ecological / atomistic fallacy与Simpson’s paradox影响。[Spatial Aggregation and the Ecological Fallacy](https://pmc.ncbi.nlm.nih.gov/articles/PMC4209486/)

**产品推论：** Knowledge-level Relation与Group-level Relation是不同层级命题。本文借用“跨层外推必须有额外合同”的原则，不声称知识图谱关系等同统计相关。

## 15.7 Provenance graph summarization

研究工作表明，provenance graph可以通过类型和路径约束形成summary，同时保持从summary回到原始provenance结构的解释能力。[Aggregation by Provenance Types](https://eprints.soton.ac.uk/364726/16/gam15.pdf)

**产品推论：** Network可以显示聚合后的Group Relation，但必须通过Support Set、Effective Units与exclusions回到原始paths；具体九道门、类型矩阵和用户采用仍是本产品决定。

## 15.8 研究没有证明什么

上述来源没有证明：

- 两个Effective Support Units是普适真理；
- 本文九道gate是最佳数量；
- bilateral-core与anchor-and-spread覆盖所有知识关系；
- 用户愿意阅读origin cluster；
- ambient Candidate应该出现多少；
- relation type registry已经完备；
- removal test一定能预测未来稳定性；
- Candidate adoption一定需要本文的信息顺序；
- 群级关系能自动提升个人知识库留存。

这些都是为了克制系统建议、保护用户知识所有权和保持Network可解释所做的产品决定，必须用真实知识库与持续任务验证。

---


# 16. 当前 Ardot 证据与未来设计证明

## 16.1 本轮当前截图

- `design-audit-ardot/group-relation-round-2026-08-10/accepted/01-current-network-concept.png`
- `design-audit-ardot/group-relation-round-2026-08-10/accepted/02-current-dual-mirror.png`

两张截图均在2026-08-10从用户给出的Ardot文件当前可见画板重新捕获并检查；它们只证明静态视觉状态，不能证明交互、键盘、响应式或数据真实性。

## 16.2 Screen 3 — IA 概念星图

可保留的视觉价值：

- 深色关系空间具有明确气质；
- Group-like clusters与跨域探索感直观；
- L0–L5条带表达了从全局到证据的纵向概念；
- 与温暖阅读面形成足够强的模式切换。

当前未证明：

- 图中什么是Group、Knowledge、Topic或装饰星点；
- 哪条线是cross-group exit、Group Relation、Reference或Query Highlight；
- relation statement、type、direction、Applicability；
- Current / Suggested / History；
- Group Relation为何够资格从成员paths上升；
- source / content / assertion重复怎样折叠；
- CounterSignal、named subscope与anchor-dependent；
- Selection、Inspect、Open、Back、filter与List Equivalent。

结论：它仍然是**关系空间的艺术方向与概念海报**，不是Group Relation产品设计证明。

## 16.3 Screen 2 — 双镜工作区

可保留的视觉价值：

- Warm Paper + Relation Night准确表达方向3与方向2结合；
- 正文仍是Primary，关系面可以作为Companion；
- `可逆行动 / 最小权限 / 可观察轨迹 / HITL边界`提供真实内容fixture雏形。

当前未证明：

- 右侧是否为可交互graph，而不是背景图片；
- 节点和边的identity；
- 群内Knowledge Relation与群级Group Relation的区别；
- 一个具体exit如何进入Candidate；
- Candidate资格、折叠与反例；
- relation Inspector与supporting paths；
- 312条关系的scope、standing与可读性；
- close / back后怎样恢复正文Anchor和viewport。

结论：双镜方向正确，但当前关系面仍是**氛围层**，尚未成为可判断、可维护的知识表面。

## 16.4 未来视觉必须证明的六段升级链

未来设计不需要把六段画成六张固定页面，但必须在同一产品中证明：

1. **Exit only**：一条具体Knowledge path通向另一个Group，没有群级edge；
2. **Signal hidden**：系统观察到重复模式，但不打扰、不显示badge；
3. **Qualified Candidate**：Suggested layer显示群级statement、coverage与有效units；
4. **Candidate Inspector**：解释折叠、排除、CounterSignal与removal test；
5. **Current Relation**：采用后进入Current Network，并可回到具体paths；
6. **Review / History**：支撑变化、scope收窄、supersede / retract后仍可解释。

## 16.5 必须设计的关键状态

- 7条raw paths折叠为1个unit；
- 3条independent paths但fringe-only；
- bilateral-core Candidate；
- anchor-and-spread Candidate；
- named-subscope Candidate；
- anchor-dependent on-demand Candidate；
- ambiguous type；
- core CounterSignal；
- Candidate dismissed as exit-only；
- adopted Relation；
- Support Set changed / review_due；
- Boundary Revision changed；
- partial index；
- AI unavailable；
- Graph / List / mobile / keyboard等价。

## 16.6 视觉语法不能提前冻结

本合同只冻结语义责任，不决定：

- Candidate是虚线、halo还是单独列表；
- coverage使用何种图形；
- Inspector宽度；
- relation bundle的具体形态；
- cosmic background是否保留；
- 深色模式的色值、字体、半径或动效。

视觉探索开始后，必须以真实fixture绘制，再从三种视觉方向中选择。不得用颜色深浅替代standing，不得用生成式星图图片冒充产品数据。

---


# 17. 对文档体系的覆写与同步要求

## 17.1 立即覆写的旧语义

任何有效文档出现以下语义时，以本文为准：

- `多个正式paths即可提出Group Relation` → 必须通过九道资格门；
- `至少N条边` → 原始path count无效，使用Effective Support Units；
- `多个core / bridge Placements` → 必须绑定Boundary Revision与CoverageFootprint；
- `可靠来源直接陈述可成为Direct Relation` → 系统抽取仍先形成source-explicit Candidate；
- `一个Group pair的多条底层关系先聚合为一条群关系` → 只有type-specific Assessment通过后才可聚合；
- `accepted / active Group Relations` → 当前投影使用maintained + lifecycle=current；
- `关系强度 / 边权` → 不作为truth或standing；
- `Candidate依路径数量排序` → 使用eligibility、attention budget与current task relevance；
- `支撑列表` → Support Set必须包含折叠、排除、counter与removal impact；
- `没有Group Relation = 未连接 / 异常` → 合法状态，保留exits。

## 17.2 Canonical 必须同步

Canonical至少需要新增：

- Group Relation四级standing；
- Effective Support Unit与origin collapse；
- 九道资格门；
- type-specific policy；
- bilateral-core / anchor-and-spread / named-subscope；
- ambient vs on-demand Candidate；
- current Network / Ask / Overview行为；
- 新journey与acceptance contracts；
- Current Ardot证据结论；
- visual design Gate。

## 17.3 进入原型前的新Gate

在既有Gate之外，还必须满足：

1. 用户能理解exit不等于Group Relation；
2. 系统建议门槛不依赖raw path count；
3. relation type policies覆盖首批canonical types；
4. Candidate可解释Boundary coverage与independence；
5. 没有关系不会被呈现成缺陷；
6. Current / Suggested / History在Graph与List中同义；
7. 至少一个真实fixture完整走通exit → Candidate → adoption → review；
8. 当前Ardot星图降为视觉参考，不被继续直接补按钮冒充完整设计。

当前状态仍是产品定义阶段；本文没有解除“不马上做原型”的约束。

---


# 结论

群级关系是这个产品最容易“看起来聪明、实际上不可信”的地方。AI很容易发现相似、共现和多条路径，视觉也很容易把它们画成漂亮的星座；真正困难的是决定何时可以把局部连接上升为两个知识范围整体之间的一条可维护陈述。

本合同把答案冻结为九道不能互相抵消的资格门，并把原始线条折叠成可解释的Effective Support Units。它允许系统保持克制：不够资格的连接仍然可以探索，只是不冒充群级知识；够资格的也只成为Candidate，直到用户采用；采用后的Relation则成为用户真正拥有的独立知识，不会因为算法或支撑数量变化被静默抹去。

这样，方向2的关系空间才有资格与方向3的层级阅读并列：一边负责深入理解，一边负责可信地跨越知识范围。两者都服务知识本身，而不是服务一张更密、更炫的图。
