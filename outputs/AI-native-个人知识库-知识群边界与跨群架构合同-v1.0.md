# AI-native 个人知识库

## 知识群边界与跨群架构合同 v1.0 — Group、Topic、Placement 与 Group Relation

> 文档日期：2026-08-08  
> 文档性质：产品本体合同，不是视觉稿、数据库实现或原型规格  
> Canonical 产品定义：`AI-native-个人知识库-终局产品设计文档-v4.0.md`；本合同只证明群边界与跨群责任，不得反向改写 v4.0  
> v4.0 Group 覆写：名称即可创建合法 Bare Group；无 Topic、无 Source、无 Relation、唯一或长期孤立都不影响成立，Relation 是价值增强而不是准入条件  
> v4.0 Topic 覆写：Topic 是可递归打开和查询的局部知识范围，可拥有局部 Overview；它不因此获得 Group boundary、群级全局身份、Library Network 节点身份或正式 Relation endpoint  
> v4.0 策展覆写：Topic / Placement semantic order 是结构真相；Scope representative / stable start 是局部策展角色；Recent、View sort 与 AI relevance 不得写回两者  
> v4.0 Relation 覆写：跨群 Knowledge Relation、共享 Knowledge、Gateway、Saved Path 与 Query Route 只能形成 cross-group exit / supporting path；只有 Direct 或用户接受的 Aggregated Group Relation 才进入 Library Network。一个 Group pair 可保留多条独立 Relations，并用 Bundle 呈现  
> v4.0 Boundary 覆写：Group Boundary、Knowledge Placement、Source Attachment 与 View / Query result 是四种不同真相；内容不会自动改写边界，边界修订也不会自动移动或删除内容  
> v4.0 Topic Scope 覆写：Topic 默认范围包含 direct Placements 与 descendant Topics，但祖先不生成镜像 Placements；Group root Placement 合法且不等于 unplaced；Source-only 通过指向 Group / Topic 的 Source Attachment 保留语境  
> 2026-08-08 Group Formation 覆写：Group 可从空白、Knowledge selection、Source bundle、Topic promotion、View snapshot 或 imported hierarchy 建立；AI cluster 只产生可丢弃的 Group Candidate，不能静默成为 Group  
> 2026-08-09 Group State 覆写：`formation_phase` 已被 Orientation、Change、Attention、Lifecycle 与 Boundary continuity 取代；successor / split / merge 重新解析每个新 Scope 的状态，不继承“成熟阶段”。完整合同见`AI-native-个人知识库-知识群状态演化与身份连续性合同-v1.0.md`  
> 2026-08-10 Relation Lifecycle 覆写：RelationCandidate、RelationRevision、Evidence / Challenge、Assertion Disposition、Change Condition 与 Lifecycle 分离；Group Split / Merge 对每条边创建 RelationTransitionCase，新 scope 不继承 maintained edge。完整合同见`AI-native-个人知识库-关系陈述生命周期与网络可信性合同-v1.0.md`  
> 2026-08-10 Group Relation Aggregation 覆写：多条 paths、多个 core / bridge Placements 或来源直接陈述都不自动取得 Candidate 资格；系统必须先执行 Effective Support Unit collapse、Boundary coverage、type-specific policy、CounterSignal 与 strongest-unit removal。完整合同见`AI-native-个人知识库-群级关系聚合门槛与支撑充分性合同-v1.0.md`  
> 2026-08-10 Group Relation Type Registry 覆写：正式 registry 使用十一种 types；Group-level `overlaps_with` deprecated 为 `partially_overlaps_with`，`shares_core_knowledge_with` 改为 derived Shared Knowledge Observation，并新增 `complements / challenges`。完整合同见`AI-native-个人知识库-群级关系类型注册表与语义互斥合同-v1.0.md`  
> 2026-08-10 多语境复用夹具覆写：`AI-native-个人知识库-第二真实端到端夹具-概念学习、多语境复用与群关系-v1.0.md`用`提取练习 / 间隔学习 / 学习与表现`三条 canonical Knowledge 的双 Placement 验证：identity、正文、Revision 与 Evidence 不复制；每个 Placement 可拥有不同 contextual summary、role、neighbor priority 与 Return Envelope。Shared Knowledge 只形成 observation，词面 / embedding 相似不形成 identity merge  
> 术语兼容：本文早期使用的 `Node` 均按 v4.0 的 `Knowledge` 理解，不新增第二种日常知识对象  
> 历史深层模型：`AI-native-个人知识库-产品定义-v3.0.md`  
> 相邻 Node 合同：`AI-native-个人知识库-知识节点粒度与内容组成合同-v1.0.md`  
> 相邻 Overview 合同：`AI-native-个人知识库-Overview形成编辑与更新合同-v1.0.md`  
> 相邻 AI 查询合同：`AI-native-个人知识库-AI查询与知识回答合同-v1.0.md`  
> 相邻直接创作合同：`AI-native-个人知识库-直接创作编辑与版本历史合同-v1.0.md`  
> 相邻属性与适用条件合同：`AI-native-个人知识库-属性Facet与适用条件合同-v1.0.md`  
> 相邻关系陈述生命周期合同：`AI-native-个人知识库-关系陈述生命周期与网络可信性合同-v1.0.md`  
> 相邻产品对象层级与身份治理合同：`AI-native-个人知识库-产品对象层级与身份治理合同-v1.0.md`  
> 适用范围：Knowledge Group、Topic、Placement、Overview、Group Relation、Library Network、跨群探索  
> 核心问题：什么应该成为知识群，什么只是群内主题；同一知识如何跨群复用；群之间的关系如何成立且可解释

---

# 0. 执行决定

这一轮冻结三十七项产品决定。

1. **Knowledge Group 是可独立进入、理解、查询和维护的知识范围。** 它不是文件夹、标签、白板或相似内容簇。
2. **Topic 是单个 Group 内的有序结构分支。** 它帮助理解一个群内部“由什么组成”，但不拥有独立的全局知识身份。
3. **Knowledge Node 是可跨群复用的知识身份。** Topic 不拥有 Node 正文，同一 Node 不因出现在多个 Group 而复制。
4. **Placement 是 Node 出现在某个 Group / Topic 语境中的正式位置。** Group Membership 不再作为独立真相或独立对象存在。
5. **一个 Node 是否属于某 Group，由 active Placement 推导。** `member_node_refs` 只能是索引，不是第二份 canonical membership。
6. **产品不设 Subgroup 对象。** 一个范围要么仍是 Topic，要么成为完整 Group；Group 之间用可解释的 scope relation 连接，不用未定义的容器层。
7. **知识的丰富层级主要发生在 Group 内。** Library → Group → Topic tree → Knowledge → Explanation → Evidence；不能用无限嵌套 Group 替代 Topic 设计。
8. **Topic 树只保存直接父级。** 祖先、后代和导航路径由系统推导，避免同时维护 `parent` 与 `child` 两套真相。
9. **Topic 在一个 Group 内只有一个直接父级。** 多重语境由 Node Placements、Saved Paths 与 Group Relations 表达，不把 Topic 结构变成难以解释的 DAG。
10. **Node 可以在同一 Group 中拥有多个 Placement，但必须承担不同语境角色。** 纯重复位置应合并或保留一个默认入口。
11. **手工创建 Group 永远不被门槛阻止。** 系统只有在边界独立、使用意图独立且结构信号充分时，才建议把 Topic 提升为 Group。
12. **Topic → Group 是身份保持的拓扑变换。** 原 Topic 默认成为通往新 Group 的 Gateway，旧路径、Saved Path 和历史 Overview 继续可解释。
13. **不提供轻率的“一键把 Group 降级成 Topic”。** 需要时执行高影响的 Absorb into Group 操作，保留原 Group identity、历史和 redirect。
14. **Group Split / Merge 不负责 Node identity 合并。** 群结构变化与知识身份判断是两类不同 Change Set。
15. **正式 Semantic Relation 的端点只允许 Node↔Node 或 Group↔Group。** Topic、Placement、Source 和 Evidence 使用自己的结构、引用或证据连接，不混入正式语义关系层。
16. **Group Relation 是关于两个知识范围如何互相改变理解的陈述。** 它不是共享标签、共同来源或 embedding 相似度。
17. **Group Relation 分为用户直接断言与底层路径聚合。** 聚合 Signal 通过资格门后才成为 RelationCandidate；用户采用后才物化 Relation。底层依据变化时进入 review_due，不静默消失。
18. **Library Network 只显示已接受且当前有解释价值的 Group Relations。** 候选关系属于单独 Suggested layer，检索共用属于 Query Route。
19. **View、Facet 与 Group 分开。** “最近更新”“未归类”“所有 PDF”“法国相关”可以是动态 View；Facet 只表达附加结构角色并组合 Property Profile；只有具有独立知识边界与 Overview 的范围才是 Group。
20. **Group 的质量不以数量、深度或连线多少衡量。** 边界可逐渐理解、进入后能定位、Node 不重复，已存在的跨群关系可解释，才是产品质量；无 Relation 的第一个、唯一或孤立 Group 同样完整合法。
21. **Scope transformation 必须显式处理 Overview identity 与 lineage。** Topic Promotion 建立新的 Group Overview；Group Merge 选择 canonical Overview；Split 不机械切 prose；Absorb 只提出可编辑 Diff。
22. **Projection 重新绑定与 Editorial prose 迁移分开。** 结构变换可以重建 Projection；旧文字只有在 scope 仍适用并经预览接受时进入新 Overview。
23. **Query Scope 不创造结构归属。** 一个 Ask 可以同时读取多个 Groups、Topics、Nodes 或 Views，但 Requested / Effective / Used refs 和 retrieval jumps 只属于 Query Run；它们不创建 Placement、Group membership、scope relation 或正式群边。
24. **Group Boundary 与 Current Contents 是两种真相。** Boundary 保存 governing question、includes、excludes 与 Applicability；Contents 由 Topics、Placements 与 Source Attachments组成。两者可以暂时不完全一致，但差异必须可解释。
25. **Boundary Revision 不执行内容迁移。** 扩大、收窄或澄清 Boundary 只改变范围意图，并对 Overview、Ask、Relations 与策展产生影响；Knowledge / Source 去向必须通过独立结构动作决定。
26. **Topic Scope 必须区分 direct 与 descendant。** 当前 Topic 的查询范围可以包含后代，但每个 Knowledge 只保存真实直接 Placements；同一 identity 在多条后代路径出现时去重并保留路径。
27. **Group root Placement 是合法结构。** 它表示 Knowledge 已属于 Group 但不依赖某个 Topic；没有任何 active Placement 才是 unplaced，产品不得把 Bare Group 的 root content 制造成整理债务。
28. **Source Attachment 保存材料进入语境。** Source 可以直接 attached 到 Group 或 Topic，即使尚未形成 Knowledge / Evidence；Attachment 不是 Placement、Binding 或 Source 副本，移除它不删除材料和下游证据。
29. **Topic 自己拥有完整结构生命周期。** Rename / move / merge / split / archive / delete / cross-group transfer 分别处理 parent、children、Placements、Source Attachments、Overview、stable entries、Paths、Ask history 与 redirects。
30. **Group identity continuity 由 governing purpose 决定。** 改名、alias 与边界澄清通常保持 identity；核心问题和长期用途被替换时使用 successor / split / merge，不能用同一个 group_id 静默换范围。
31. **Group 只有六种合法形成起点。** 空白、已有 Knowledge selection、Source bundle、Topic promotion、View / Search 当前结果与 imported hierarchy 最终都建立同一种 Group identity，不能产生六类 Group。
32. **View 转 Group 必须冻结一次显式选择。** View criteria 与未来命中继续动态；只有用户在创建时选中的 identities 才形成 Placements，规则本身不变成 membership。
33. **Source bundle 转 Group 先建立 Source Attachments。** 解析、摘要或聚类失败仍可成功；没有用户确认时不自动创建 Knowledge、Topics 或 Relations。
34. **Imported hierarchy 需要映射预览。** 外部 folder / heading / tag 可以映射到 Group、Topic、Source 或保持原路径，但文件夹数量和层级不能自动定义知识边界。
35. **AI cluster 只能形成 Group Candidate。** Candidate 是临时、可丢弃的结构建议，不进入 Search、Library Network、Ask 默认范围、Overview 或导出真相；只有用户接受才产生 Group 与 Change Set。
36. **100+ Groups 仍不用第二层容器。** 定位依赖稳定 Group catalog、Pins、Saved Group Views、Search 与 manual order；暂不新增 Shelf / Collection / Workspace 来承载“群的群”。
37. **Group identity 与长期状态配置分开。** Orientation、Change、Attention、Lifecycle 与 Boundary continuity 各自回答一个问题；Pause、Archive、内容增减和高影响变化不改 `group_id`，只有 governing purpose 不连续时进入 successor / split / merge。

这些决定共同消除当前文档中的三个结构冲突：

- `subgroup_refs` 被使用，却没有 Subgroup 对象、交互或生命周期；
- `Group Membership`、`member_node_refs` 与 `Placement` 同时表达“属于”，可能产生三份不同真相；
- Topic 提升、Group 降级、拆分和合并被列为动作，却没有身份、重定向和下游影响合同；
- Boundary、Contents 与 View 都被宽泛写成“范围”，内容加入或查询扩张可能静默改变群边界；
- Topic 的 direct / descendant membership 未分开，祖先可能产生镜像归属；
- Source-only 进入深层 Topic 后没有正式 Attachment，未形成知识时会失去原语境；
- Topic merge / split / cross-group transfer 缺少独立的 identity 与影响合同。

---

# 1. 四种容易混淆的组织单位

## 1.1 Knowledge Group：独立知识范围

一个 Group 回答：

- 这是关于什么的完整知识范围；
- 为什么值得独立进入；
- 包含什么、不包含什么；
- 当前整体理解是什么；
- 由哪些主要主题组成；
- 与其他知识范围为什么相连；
- 在这个范围内提问时，默认应该使用哪些知识。

例如：

- 认知科学；
- AI Agent 产品设计；
- 法国租房；
- 个人财务；
- 某项长期研究计划。

## 1.2 Topic：群内理解分支

Topic 回答：

- 在这个 Group 内，我们从哪个角度组织一部分知识；
- 它在父级结构中承担什么作用；
- 有哪些子主题和代表知识；
- 当前分支有哪些缺口。

打开 Topic 时，这些责任以可维护的局部 Overview 呈现；继续进入子 Topic 时重复同一合同。Topic 因而是可阅读的范围，而不是只可展开的文件夹，但仍依赖所属 Group 才能完整解释。

例如，在“AI Agent 产品设计”中：

- 知识模型；
- 查询与检索；
- 人机确认；
- 失败与恢复。

离开“AI Agent 产品设计”后，“失败与恢复”可能含义过宽，不能仅凭名字成为独立 Group。

## 1.3 Knowledge Node：可独立理解的知识

Node 回答一个具体、可复用的认知单元：

- 什么是 Knowledge Group；
- 为什么 Retrieval Jump 不能成为 Relation；
- 法国租房担保的当前规则；
- 一个产品决定及其理由。

Node 有稳定 identity、canonical body、版本、状态、关系和来源。它可以在多个 Group / Topic 中出现，但仍是同一条知识。

## 1.4 View：同一批知识的一种观察方式

View 是筛选、排序、聚合或布局，不声称形成新的知识范围：

- 最近更新；
- 未归入知识群；
- 所有 Evidence-limited Claims；
- 过去一个月添加的 Sources；
- 按国家筛选的生活知识；
- 当前 Query 使用的 Nodes。

View 不自动拥有独立 Overview、边界、来源政策或 Group Relations。

---

# 2. Group / Topic / Node / View 的判断合同

## 2.1 快速判断表

| 问题 | Group | Topic | Node | View |
|---|---:|---:|---:|---:|
| 能否独立写出“包含与不包含什么” | 必须 | 依赖父 Group | 不适用 | 否 |
| 能否独立进入并获得 Overview | 必须 | 局部 Overview | Node Orientation | 否或派生摘要 |
| 能否成为 Ask 的稳定默认 Scope | 是 | 是，但继承 Group | 可作为焦点 | 临时过滤 |
| 是否拥有全局可复用知识正文 | 否 | 否 | 是 | 否 |
| 是否组织多个知识对象 | 是 | 是 | 否 | 是，但只表示结果集 |
| 是否具有独立 Relation neighborhood | 是 | 否 | 是 | 否 |
| 是否在多个 Group 中复用 | Group 自身存在于 Library Network | 否 | 是 | 可复用规则，不是知识身份 |
| 删除是否可能改变知识世界边界 | 是 | 只改变群内结构 | 改变知识身份 | 只删除观察方式 |

Ask 选择 Group / Topic / Node / View 时保存的是 Scope Anchor，不是 membership copy。是否沿 descendants、正式 Relations、Saved Path 或 Evidence 扩展由独立 Expansion Policy 决定。Current Focus 只保持用户位置；它不能让“当前 Node”暗中变成“整个 Group”或“全部知识”。跨群 Used Context 只在本次 Answer 的 Actual Context 和 Query overlay 中高亮，关闭后 Library Network 返回 maintained current Group Relations。

## 2.2 产品中的一句判断

> **如果离开父语境后，它仍值得被单独进入、提问、维护边界并与其他知识范围建立关系，它可以是 Group；如果它主要负责在当前 Group 内安排一组知识，它是 Topic；如果它本身是一条可理解和复用的内容，它是 Node；如果它只是筛选结果，它是 View。**

## 2.3 不按大小判断

- 很大的 Topic 仍可能只是 Topic，因为它离开父 Group 后没有独立语义；
- 很小的 Bare Group 仍可以是 Group，因为用户明确要建立一个独立知识范围；
- 一个包含很多 Nodes 的查询结果仍只是 View；
- 一条很长的文章仍可能只是一个 Source，而不是 Group。

对象类型由认知职责决定，不由数量阈值决定。

---

# 3. Knowledge Group 的边界合同

## 3.1 Boundary 不是一句营销描述

一个可维护的 Group boundary 至少包含：

```text
GroupBoundary
  purpose_or_governing_question
  includes[]
  excludes[]
  key_perspectives[]
  default_applicability?
  source_scope_policy?
  neighboring_groups[]
  boundary_revision_history
```

P0 只显示一句自然语言边界；P2 编辑时才展开 includes / excludes；P3 才显示版本和来源策略。

## 3.2 边界句的质量标准

合格：

> 研究 AI Agent 产品如何组织、查询、解释和维护长期知识；不覆盖通用模型训练、算力基础设施或所有办公自动化。

不合格：

- “关于 AI 的所有内容”；
- “我感兴趣的东西”；
- “一些产品资料”；
- 自动拼接五个关键词。

边界可以暂时不完整，尤其是 Bare / Structuring Group；系统必须显示“边界仍在形成”，而不是用模型常识填满。

## 3.3 Group 独立性的五个信号

系统判断一个范围是否值得独立成 Group 时，检查：

1. **Boundary independence**：能否独立说明包含与排除；
2. **Orientation independence**：进入后能否形成自己的 Orientation / Overview；
3. **Retrieval independence**：用户是否会反复把它作为 Search / Ask Scope；
4. **Structural independence**：是否形成不依赖父 Topic 的主要分支；
5. **Relational independence**：是否拥有自己与其他 Groups 的关系邻域。

这些是建议依据，不是阻止用户创建 Group 的门槛。

## 3.4 Boundary Revision 与 identity continuity

Boundary 是可版本化的 Scope truth：

```text
GroupBoundaryRevision
  boundary_revision_id
  group_id
  predecessor_ref?
  purpose_or_governing_question
  includes[]
  excludes[]
  key_perspectives[]
  default_applicability_ref?
  source_scope_policy_ref?
  authored_by
  accepted_at
  change_reason?
```

以下变化通常保持同一 Group identity：

- rename、alias 与措辞改善；
- includes / excludes 更精确；
- Applicability 被限定；
- 已存在 governing question 的自然扩展或收窄；
- 当前 Boundary 与真实使用之间的纠偏。

以下变化需要 successor / split / merge，而不是普通 Boundary edit：

- governing question 被另一个问题替换；
- 主要长期用途、受众语境或 Applicability 已不连续；
- 原范围只剩历史壳，新范围无法解释旧 Overview 与 Ask；
- 一个 Group 实际上已经分成多个可独立进入的知识世界；
- 两个 Groups 被确认是同一 identity。

历史 Boundary Revision 必须随 Saved Answer Scope、Overview basis、Group Relation Applicability 与 export 一起保留。改标题不能使旧 deep link 失效；旧标题可作为 alias 或历史显示。

## 3.5 Boundary tension：允许暂时不一致，但不能静默

一条 Placement / Attachment 可能超出当前 Boundary。这不是立即阻止写入的错误，也不能被系统自动吸收到边界。产品只在差异会影响理解时显示一次 tension：

```text
这条知识目前位于本群，但超出“通用模型训练不在本范围”的边界。
```

合法动作：

- 保留为 context / example / bridge / reference；
- 移动当前 Placement；
- 在另一个 Group 增加 Placement；
- 修订 Boundary；
- 创建 successor / split；
- 暂时保留，不形成待办红点。

Boundary tension 是范围解释，不是 Knowledge quality、冲突或错误状态；拒绝系统建议后，没有新依据不重复催促。

---

# 4. Knowledge Group 数据模型修订

## 4.1 Canonical Group

```text
KnowledgeGroup
  identity
    group_id
    title
    aliases[]

  boundary
    current_boundary_revision_ref
    purpose_or_governing_question
    includes[]
    excludes[]
    default_applicability_ref?
    source_scope_policy?

  organization
    primary_kind_ref
    facet_refs[]
    property_profile_ref?
    overview_ref

  state_configuration
    orientation_profile_ref
    change_condition_ref
    attention_mode
    lifecycle_state
    boundary_condition_ref

  object_facts
    freshness_state
    unresolved_question_refs[]
    conflict_refs[]

  ownership
    curation_mode
    created_by
    created_at
    updated_at

  lineage
    origin_topic_snapshot_ref?
    previous_group_refs[]
    successor_group_refs[]
    redirect_refs[]
    revision_history
```

`purpose_or_governing_question` 等字段在上表中是 current revision 的可读投影；canonical truth 是 `current_boundary_revision_ref`。成员、Source Attachment、View result 与 Query Context 不写进 Boundary Revision。

`orientation_profile_ref`、`change_condition_ref` 与 `boundary_condition_ref` 是带 evaluated basis 的可重建 Projection；`attention_mode` 与 `lifecycle_state` 是显式用户决定。Freshness、conflict、Evidence availability 与 Overview alignment 保持对象事实，不压缩成 Group health 或 maturity。完整状态语义由`AI-native-个人知识库-知识群状态演化与身份连续性合同-v1.0.md`定义。

## 4.2 Primary Kind、Facet 与 Property Profile

Primary Kind 回答“这个 Group 默认用什么骨架帮助理解”，一个 Group 同时只有一个；Facet 回答“它还具有哪些附加结构角色”，可以多个。二者均引用稳定 Definition identity，不是自由 `tags[]`。

它们只影响：

- Overview 的默认 Presentation Profile；
- 推荐的 Topic / content roles；
- Context Rail 中建议显示的 Property Definitions；
- 比较与 Saved View 的建议维度；
- Group 创建时可选的结构提示。

它们不影响：

- Group identity 或 Boundary truth；
- Node membership / Placements；
- 现有 Property Assertions；
- Relation truth；
- Direct Authoring 与 Accepted Commit；
- 是否允许空 Group 长期存在。

Property Profile 组合 Primary Kind、Facets 与 Group override，只保存推荐字段、显示顺序和显著性。添加 Profile 不生成空 Assertions，改变默认值不回写既有对象，移除 Facet 不删除现有值。Group-local 需要不同语义时创建新的 canonical Property Definition，而不是复制同名 field；同名不等于同义。

Source Tag、User Facet、System Marker、Alias 与普通关键词分别保存。共享任意一种都不能形成 Group membership 或 Group Relation；Node-reference Property 也不能因为跨群指向对象而生成 Library Network edge。

## 4.3 明确删除的字段

- 删除 canonical `subgroup_refs`：产品没有 Subgroup 对象；
- 删除 canonical `member_node_refs`：成员由 Placements 推导；
- 删除同时维护的 `child_topic_refs`：子级由 `parent_topic_id` 反向索引；
- 删除 canonical `root_topic_refs`、`root_placement_refs` 与 `group_relation_refs`：根对象和直接群关系均可从各自 canonical 对象反向推导；
- 删除 canonical `source_refs` / `topic_source_refs`：直接语境由 Source Attachments 表达，Evidence 使用由 Bindings 推导；
- 不用 `contains / belongs_to_group` Relation 重复表达 Placement。

为了性能，系统可以物化以下 derived indexes：

```text
DerivedGroupIndex
  active_member_node_refs[]
  root_topic_refs[]
  root_placement_refs[]
  descendant_topic_refs[]
  source_coverage_summary
  direct_source_attachment_refs[]
  direct_group_relation_refs[]
  bridge_node_refs[]
```

Derived index 可以重建，不能成为用户导出中唯一的结构真相。

---

# 5. Topic hierarchy：丰富但不含混

## 5.1 Topic 的最小模型

```text
Topic
  topic_id
  group_id
  title
  parent_topic_id?
  overview_ref?
  order_key
  knowledge_gap_refs[]
  lifecycle_state
  promoted_group_ref?
  redirect_ref?
  revision_history
```

Topic 的 children、descendants 与 breadcrumb 由 `parent_topic_id` 推导。

## 5.2 层级不使用两套真相

系统只持久化直接父级：

```text
Topic B.parent = Topic A
Topic C.parent = Topic B
```

系统可以推导 A 是 C 的 ancestor，但不会额外写一条 A contains C。这样可以：

- 保留直接结构；
- 避免移动 Topic 后产生残留祖先边；
- 支持查询整个后代树；
- 让可视化准确区分“直接子级”与“更深后代”。

## 5.3 单父级，不等于单语境

Topic 在一个 Group 内只拥有一个直接父 Topic。这让 Outline、Up、Back、Move 和删除影响可预测。

如果同一知识需要出现在多个分支：

- 为同一 Node 建立多个 Placements；
- 使用 Reference Link；
- 保存跨分支 Path；
- 在真正具有语义意义时建立 Node Relation。

不通过让 Topic 同时拥有多个父级制造结构 DAG。

## 5.4 层级深度不设硬上限

产品不以“最多三级目录”限制真实知识。但界面采用 Focus + Context：

- 当前 Topic 展示父级、同级、一级子级和代表 Nodes；
- 更深后代按需展开；
- DepthTrail 保留完整路径；
- 搜索和 Ask 可以直接进入深层；
- 每一级 Topic 可打开局部 Overview，DepthTrail 保留全部祖先 Scope；
- 层级过深本身不触发强制拆分；
- 只有边界和使用意图独立时，才建议提升为 Group。

`order_key` 只表达同一父级下的 canonical semantic order。按标题、更新时间、最近打开、属性或 AI relevance 排序属于 View / session state，不得回写 `order_key`。Scope 将某个 Topic 或 Node 设为 stable start / representative 时，保存的是 Overview curation reference，不改变其父级、placement 或全局重要性。

## 5.5 Rename 与同群 Move

- Rename 保持 topic_id，旧标题进入 alias / historical label；
- 同一 Group 内 Move 保持 topic_id，只修改直接 `parent_topic_id` 与 `order_key`；
- Move 禁止形成 cycle；
- descendants 随 parent path 变化，不逐项改 ancestor refs；
- Placements 与 Source Attachments 继续指向同一 Topic；
- DepthTrail、Search path 与 current Overview Projection 刷新；
- Editorial prose、stable entry、Saved Path 与 historical Answer Scope 只有语义受影响时进入 impact / redirect。

普通拖动只有在目标仍属于同一 Group 时可以直接提交。跨 Group 拖动不使用这一合同。

## 5.6 Merge Topics

Merge 先选择 canonical Topic identity：

1. 并列比较两个 Topic boundaries / local roles 与 Overviews；
2. 映射 child Topics，不自动按同名合并；
3. 迁移 Placements；相同 Knowledge + 相同 role + 相同 contextual meaning 可合并入口，否则保留多个；
4. 迁移 Source Attachments，不复制 Source；
5. 选择 canonical Overview identity，另一份进入 historical redirect；
6. stable starts、representatives 与 recommended Paths 分别检查；
7. 被吸收 Topic 保存 redirect、old parent path 与 lineage；
8. Query / Saved Answer 保留当时 Topic ref 和可解析的 current target。

Merge Topics 不合并 Knowledge identities，也不把两篇 Overview prose 直接拼接。

## 5.7 Split Topic

Split 创建两个或多个新 Topic identities，原 Topic 由用户选择：继续作为父级 hub、保留为 Gateway-like structural entry，或归档并 redirect。

Preview 必须逐项处理：

- child Topics；
- direct Knowledge Placements；
- Source Attachments；
- Overview Editorial Blocks / Projections；
- stable start / representatives / Paths；
- current Reading targets、deep links 与 Ask scopes。

Knowledge 可以 move 或在多个新 Topics 中建立 roles 不同的 Placements；正文不复制。未决定内容继续留在原 Topic，不因 Split 进入悬空状态。

## 5.8 Topic Transfer across Groups

跨 Group 迁移 Topic subtree 是 Scope Transformation，不是普通 Move：

```text
Transfer Topic T from Group A to Group B
  → snapshot T subtree and source attachments
  → validate B boundary and destination parent
  → keep topic_id with transfer lineage or create successor when semantics change
  → re-resolve all descendant Placements to Group B
  → move / share selected bridge Placements back to A
  → transfer direct Source Attachments; Source identity stays global
  → rebind Topic Overview scope and projections
  → review A / B Overview prose, curation, Group Relations, exits and source policies
  → preserve old path redirect and historical Query scopes
```

若 Topic 离开 A 后仍值得在 A 保留入口，使用 Reference / Gateway 或少量 bridge Placements；不复制一棵同步 Topic subtree。若 Topic 已能独立存在，应优先使用 Topic Promotion，而不是把它塞入另一个父 Group。

---

# 6. Placement 与 Group Membership

## 6.1 Placement 是唯一结构归属真相

```text
Placement
  placement_id
  node_id
  container_ref
    kind: group_root | topic
    id
  placement_role:
    core
    supporting
    example
    bridge
    reference
  contextual_summary?
  local_order_key?
  user_pinned
  lifecycle_state
  created_by
  revision_history
```

`container_ref` 只有一个 canonical 目标：直接放在 Group 时指向 `group_root`，放在某个 Topic 时指向该 Topic。`resolved_group_id` 由 container 推导，不再同时持久化 `group_id + topic_id` 两套可漂移路径。

## 6.2 Membership 的推导规则

```text
Node belongs to Group
  iff there is at least one active Placement
  where Placement.node_id = Node.id
  and resolve_group(Placement.container_ref) = Group.id
```

因此：

- Remove Placement 可能让 Node 不再属于该 Group；
- 删除 Topic 会处理其中 Placements，但不删除 Node；
- 一个 Node 在 Group 内多个 Topics 出现，仍只有一个 Node identity；
- 没有 active Placement 的 Node 没有 Group Membership；无论它已有 Current Revision、Explicit Draft 或 Recovery-only content；
- Search 可以找到没有 Group 的 Node。

## 6.3 同一 Group 中的多个 Placement

允许，但需要满足至少一项：

- 在两个 Topic 中承担不同角色；
- contextual summary 明显不同；
- 一个是 core，另一个是 example / bridge / reference；
- 用户明确希望保留两个入口。

系统发现完全相同的重复 Placement 时，应建议合并入口，而不是认为 Node 重复。

## 6.4 默认进入语境

Node 可以拥有一个 `preferred_entry_placement_ref` 作为用户偏好，但不能删除其他 Placements。打开 Node 时：

1. 从 Group / Topic 进入，保留实际 Placement；
2. 从 Search 进入，优先最近使用或 preferred Placement，并显示可切换路径；
3. 从 Ask 进入，使用支撑当前 Answer Claim 的 Placement；
4. 没有 Placement 时进入 canonical Node，并明确“未归入知识群”。

## 6.5 Topic direct scope、descendant scope 与去重

一个 Topic 同时有两种可读范围：

```text
DirectScope(T)
  = active Placements whose container_ref = T

DescendantScope(T)
  = DirectScope(T)
    + active Placements under every descendant Topic
```

产品规则：

- Topic Overview 的 Structure 先显示 direct children 与 direct Placements；
- Search / Ask 默认可包含 DescendantScope，但 Scope Summary 必须写`包含子主题`；
- 祖先 Topic 不为 descendant content 新建 Placement；
- 同一 Knowledge 在多个 descendant paths 出现时，scope result 按 identity 去重，并保留每个 Placement path / role；
- 用户切换`只看直接内容`只改变 View / Query policy，不改 canonical structure；
- 删除或移动某个 descendant Placement 只改变那条 path，不删除其他语境。

这样可以同时保证“主题代表整个分支”与“知识究竟直接放在哪里”都可回答。

## 6.6 Group root Placement 与 unplaced

`container_ref.kind = group_root` 是合法结构：

- Bare Group 可以不先建 Topic；
- 横跨多个 Topics 的基础 Knowledge 可以直接位于 Group；
- 用户尚未需要更细结构时，不制造分类义务；
- Group root Placement 参与 Group Overview、Search、Ask 与 Sources coverage；
- 它在 Contents 中与 root Topics 同级显示，但不冒充 Topic。

只有没有任何 active Placement 的 Knowledge 才进入全局`未归类` View。把 Group root content 标为 unplaced 会破坏用户已经作出的群边界判断。

## 6.7 Source Attachment：Source-only 的 Scope 归属

```text
SourceAttachment
  attachment_id
  source_id
  target_scope_ref
    kind: group | topic
    id
  attachment_role: primary_material | reference | example | background
  note?
  created_by
  created_at
  lifecycle_state
  revision_history
```

Attachment 只声明“这份材料被直接加入这个范围”：

- Source identity 与 Revision 仍属于全局 Sources；
- Attachment 不让 Source 成为 Knowledge、Group member 或 Semantic Relation endpoint；
- Topic Attachment 自动解析到 Group Sources，但保留 exact Topic path；
- Source 支撑 Knowledge 时另建 Evidence Binding；Binding 不反向创建 Attachment；
- 同一 Source 可以 attached 到多个 Groups / Topics，不复制 bytes；
- detach 不删除 Source、Representation、Annotation、Fragment、Binding 或其他 Attachment；
- Topic move / merge / split / transfer 必须处理 Attachment target；
- Source-only 可以永久只拥有 Attachment 而不形成 Knowledge Proposal。

---

# 7. Group 的合法形成与 Topic 提升

## 7.1 用户创建不受限制，系统建议必须克制

用户可以随时把一个 Topic 提升为 Group。系统只有同时满足以下三个必要条件，才主动建议：

1. **边界独立**：离开父 Group 后仍可清楚说明它是什么；
2. **使用独立**：它已经或很可能被单独浏览、提问、固定或引用；
3. **结构独立**：它包含多个有意义分支、稳定知识集合或独立来源范围。

并至少满足一个增强信号：

- 出现多个跨群关系；
- Topic Overview 已经接近独立 Group Overview；
- 用户反复从其他 Group 进入该 Topic；
- 父 Group Overview 因该 Topic 过重而失去方向感；
- 该 Topic 拥有与父 Group 不同的 primary kind 或 Applicability。

Nodes 数量、文本长度或 embedding 聚类不能单独触发建议。

## 7.2 提升前的问题

用户只需回答三个产品问题：

1. `这个新知识群包含什么？`
2. `原知识群中还要保留一个入口吗？`
3. `这些知识只移动到新群，还是同时保留在两个群？`

内部再生成完整 Change Set。

## 7.3 Topic → Group 变换

```text
Topic T in Group A
  → Snapshot T subtree
  → Create Group B with stable new group_id
  → Record B.origin_topic_snapshot_ref
  → T children become B root topics
  → T placements move or become shared according to user choice
  → T becomes Gateway with promoted_group_ref = B
  → Preview a Group Relation only if the resulting boundaries support one
  → Preserve T Overview in Gateway history
  → Create B overview_id with origin_scope_snapshot_ref
  → Rebind B projections and propose applicable Editorial Blocks
  → Refresh A projection; propose A prose changes only when needed
  → Rebuild Library Network, Search and Saved Path impact
```

默认策略：

- 保留原 Topic row，显示“已成为独立知识群”；
- 点击进入 Group B；
- 原 Topic URL 与历史 snapshot 继续可用；
- Node identity、Evidence 与 Sources 不复制；
- Topic subtree 的结构 identity 迁入 B，并为原 A 路径建立 redirect；不会在 A / B 各维护一棵同步 Topic tree；
- `move` 把原 Placement container 迁到 B 的对应 Topic；`keep in both` 仍迁移 B 的主 Placement，同时在 A 的 Gateway 或用户指定 Topic 新建一个 role 明确的 bridge / reference / core Placement；
- Gateway 默认只保留用户选择的少量代表 Placements，不能因“share all”重新长成一棵影子内容树；
- Saved Path 记录当时经过 Topic T，同时提供当前 Group B 入口；
- 若 B 的新边界仍完全位于 A 内，Change Set 建议 `B scope_within A`；若边界扩大，则按事实建议 `partially_overlaps_with`、`provides_foundation_for / builds_on` 或不建立正式群关系；
- Promotion lineage 由 `origin_topic_snapshot_ref` 保留，不能为了证明来源而强造一条不准确的 Group Relation；
- 原 Topic Overview 保留为 Gateway history；新 Group 使用新的 Overview identity，用户 prose 不变成两处 live 编辑；
- 父 Group 的 Projection 可以刷新，Editorial prose 只有在明确依赖旧 Topic scope 时才产生 Semantic Diff。

## 7.4 Gateway 是 Topic 状态，不是新资源类型

Gateway 是 Topic 的一个状态：

```text
Topic.lifecycle_state = promoted
Topic.promoted_group_ref = Group B
```

它只保留父级语境中的一句说明、少量代表 Nodes 和进入动作，不继续拥有一套与 Group B 分叉的完整内容树。

## 7.5 六种形成路径，共用一种 Group

| 形成路径 | 用户最少决定 | 提交结果 | 不能偷做的事 |
|---|---|---|---|
| Blank | 名称；边界可稍后补 | Bare Group | 自动编造 Topics / Overview / Relations |
| Knowledge selection | 选中 identities；每个现有位置 move / keep both / reference | Group + Placements | 复制 Knowledge body 或合并同名 identity |
| Source bundle | 选中 Sources；Group 名称；Attachment target | Group + Source Attachments | 每个 Source 自动变 Knowledge |
| Topic promotion | 新边界；原处是否保留 Gateway；Placements 处理 | Group + lineage + Gateway | 同步维护两棵 Topic tree |
| View / Search conversion | 选中当前结果；是否保留当前顺序 | Group + 当前选择的 Placements | 保存 criteria 为 membership 或自动吸收未来结果 |
| Imported hierarchy | 外部路径到 Group / Topic / Source 的映射 | Group + Topics / Attachments / Placements + import lineage | 文件夹一对一自动生成 Groups |

Blank Group 在输入名称后立即成立。其他路径只在存在跨 identity、跨位置或外部结构影响时显示预览；简单选择不需要重型向导，高影响移动 / 拆分 / 合并才进入完整 Change Set。

## 7.6 Group Candidate 是临时形成方案

```text
GroupCandidate
  candidate_id
  trigger: selection | source_bundle | topic_promotion | view_conversion | import | ai_suggestion
  proposed_boundary
  included_identity_refs[]
  excluded_identity_refs[]
  placement_plan[]
  source_attachment_plan[]
  initial_topic_plan[]
  relation_impacts[]
  explanation
  evidence_signature
```

Candidate 不拥有 Group identity、Overview、Relations、History 或稳定 URL；也不出现在 Library catalog、Network、Search、Ask scope 与 Knowledge Package 的 canonical graph。它可以保存在短期 Formation State 以便继续检查，但不是 Primary Resource。

接受 Candidate 时，系统把当时的 identities、Sources 与计划冻结为原子 Change Set，再建立 Group。拒绝或丢弃时不创建空壳、Placement、Topic 或 Relation；同一 `evidence_signature` 不重复提示，除非用户主动重新打开建议或出现新证据。

## 7.7 AI 建议 Group 的门槛

系统只有同时满足四个必要条件才主动提出 Candidate：

1. **边界独立**：能用一句话说明理解范围，并能解释至少一类排除项；
2. **进入独立**：用户已经或很可能把它作为整体重复进入、查询或引用；
3. **结构独立**：存在多个连贯方向，或一组稳定 Knowledge / Sources；
4. **解释充分**：每个主要纳入 / 排除决定有可追溯依据。

并至少有一个增强信号：独立 Source 范围、跨群出口、重复从不同入口进入、父 Group 已因该范围过重而失去方向。数量、文件夹名、tag、一次 Search、共同 Source、共现或 embedding similarity 都只能成为发现信号，不能单独越过门槛。

## 7.8 View / Search 转 Group 的快照语义

转换时界面固定显示：`当前结果 N 条；已选择 M 条；未来匹配不会自动加入`。用户可选择全部当前结果或其中一部分，系统按 identity 去重并为每条显示现有 Placements。View Definition、Search Session 和 Group 彼此独立：

- View 继续按原 criteria 动态更新；
- Group 只由接受时创建的 active Placements 推导当前内容；
- View 后续新增 / 移除结果不改变 Group；
- 删除 View 不删除 Group 或 Knowledge；
- 若用户真正需要规则集合，只保存 View，不建议创建 Group。

---

# 8. Group 不做轻率“降级”

## 8.1 为什么不能一键 Group → Topic

Group 可能已经拥有：

- 稳定 URL 和 identity；
- 独立 Overview；
- Group Relations；
- Query Scope 历史；
- Saved Paths；
- Source scope policy；
- 形成阶段与历史版本。

把它改成 Topic 会让这些对象失去合法归属。因此产品不提供普通菜单中的“降级为主题”。

## 8.2 Absorb into Group

需要合并范围时，使用高影响操作：

```text
Absorb Group B into Group A
  → choose or create destination Topic T
  → map B root topics under T
  → move or share Placements
  → review B Group Relations
  → preserve B Overview as historical snapshot
  → propose applicable B Editorial Blocks to A; never append whole prose
  → refresh A projections from canonical structure
  → archive B identity
  → redirect B to T with historical access
```

Group Relations 不自动改写成 Topic Relations。用户逐项选择：

- 将关系提升为 A 的 Group Relation；
- 由具体 Node Relations 承担；
- 保留为历史 B Relation；
- 归档。

---

# 9. Group Split / Merge 合同

## 9.1 Split Group

Group Split 默认从一个或多个 Topic subtrees 开始：

1. 选择新 Group 的边界；
2. 选择哪些 Topics 迁入；
3. 对每个 Placement 选择 move / share / keep；
4. Node identity 与 Evidence 保持不变；
5. Source scope 默认共享引用，不复制原文件；
6. 预览两侧 Overview；
7. 预览每条 incoming / outgoing Group Relation、它使用的 Revision / endpoint snapshot、Evidence、Saved Paths 与对各 successor 的适用判断；
8. 提交一个可撤销 Change Set。

Overview 不能按 Topic subtree 对旧正文做机械切片。每个新 Group 建立新的 `overview_id`，继承 `origin_scope_snapshot_ref`；用户逐段判断哪些 Editorial Blocks 仍适用，Projection 则按新 scope 规则重新计算。

共享 Node 可以同时保留在两个 Groups。Split 不强迫复制或重新命名 Node。

Split 也不复制 Relations。原 Group 的每条 Relation逐边进入 `RelationTransitionCase`：只适用于一个 successor 时提出一条 successor RelationCandidate；分别适用于多个 successors 时提出多条独立 Candidates；只适用于旧整体时旧 Relation ended；无法判断时保持 transition_pending，Current Network 不把旧边挂到任一新 Group。

## 9.2 Merge Groups

Merge 先选择 canonical Group identity。系统不得为了“干净”自动把两个 Topic trees 扁平合并。

默认提供：

- 保留两棵 Topic roots，分别标明来源 Group；
- 手工映射真正等价 Topics；
- 合并重复 Placements，但不自动合并 Nodes；
- 对 boundary、primary kind 与 source policy 做 diff；
- 两个 accepted Overviews 并列比较，选择 canonical Overview identity；
- 从 merged Placements 重建 Structure Projection，重复或冲突 prose 作为 alternatives 而非自动拼接；
- 对每条 Group Relation 分类为 identity-continuous、scope-expanded、external duplicate 或 internal self-edge；
- 为被吸收 Group 创建 redirect；
- 非 canonical Group Overview 固定为 historical snapshot 并建立 redirect；保留历史 Query Scope。

Node identity 冲突进入独立 Identity Resolution，不与 Group Merge 同一个“全部应用”按钮绑定。

Merge 不自动合并或 retarget Relations：只有 canonical Group identity 与 Relation statement 对合并后 scope 都连续时才安全解析；scope 扩大时保留旧历史并提出带限定的 successor Candidate；对外近似重复保持两条 identities 直到 Relation Merge 审查；A↔B 在合并后形成的 self-edge 只保留为 ended / merge lineage，不改造成其他 relation type。

## 9.3 Undo

Undo Group Split / Merge 必须恢复：

- Group identities；
- Topic parent paths；
- Placement positions and roles；
- Group Relations、RelationTransitionCases、dispositions、Support Set revisions 与 endpoint snapshots；
- Overview identities、revisions、lineage、Projection rules 与 redirects；
- Saved Path redirects；
- Library Network layout anchors。

之后新增的用户知识不能被一次历史 Undo 静默删除；存在后续修改时进入三方影响预览。

---

# 10. Formal Relation 的端点合同

## 10.1 Endpoint matrix

| From → To | 正式 Semantic Relation | 使用的其他连接 |
|---|---:|---|
| Node → Node | 允许 | Reference、Evidence、Retrieval 仍分开 |
| Group → Group | 允许，使用 Group Relation types | Scope / aggregate explanation |
| Topic → Topic | 不允许 | parent-child、compare View、Saved Path |
| Topic → Node | 不允许 | Placement |
| Node → Group | 不允许 | Placement 或由 Node paths 聚合成 Group Relation |
| Node / Relation → Evidence | 不作为 Semantic Relation | Evidence Connection |
| Evidence → Source | 不作为 Semantic Relation | exact locator / provenance |
| Query Result → Node | 不作为长期 Relation | Answer Claim support / Save Proposal |

这一限制不是削弱图谱，而是保证每条正式边都可以被同一种语义模型解释。

## 10.2 为什么 Topic 不做 Relation endpoint

Topic 是一个可重组的结构集合。它移动、改名或提升为 Group 时，不应导致大量知识关系失效。

若用户认为两个 Topic 有重要语义关系，系统提供三个选择：

- 建立代表 Nodes 之间的 Relation；
- 保存一个跨 Topic Path；
- 若两者本身是独立知识范围，将其提升为 Groups 后建立 Group Relation。

---

# 11. Group Relation 的精确模型

## 11.1 Group Relation 类型

Group↔Group 使用受限类型：

### 范围关系

- `scope_within`：B 的知识边界真实落在 A 的范围内，但 B 仍是独立 Group；`contains_scope` 只是从反方向阅读同一条关系，不另存第二条边；
- `partially_overlaps_with`：边界部分相交，任何一方都不完全包含另一方，并能说明双方仍有哪些 material differences。

### 基础与应用

- `provides_foundation_for`，inverse reading：`builds_on`；
- `applies_to`，inverse reading：`is_application_context_for`；
- `provides_method_for`，inverse reading：`uses_method_from`。

### 共同、对照与影响

- `complements`：围绕同一目标提供不同、非冗余且可组合的贡献；
- `contrasts_with`；
- `challenges`，inverse reading：`is_challenged_by`；
- `influences`，inverse reading：`is_influenced_by`；
- `constrains`，inverse reading：`is_constrained_by`。

### 演化

- `evolved_from`，inverse reading：`evolved_into`。

`related_to` 不进入正式 Group Relation 类型。`influences` 是 advanced fallback：必须有 mechanism 与 affected dimension，且 foundation / method / applies / challenge / constraint 等更窄类型都不准确时才使用。

`shares_core_knowledge_with` 不再是 Relation type。同一 canonical Knowledge 在两个 Groups 都承担 core / representative role 时，产品形成 derived `shared_core_knowledge` GroupConnectionObservation；它可以在 Shared Knowledge Lens 中自动刷新，也可以支撑 Candidate，但不需要采用、不拥有 Relation lifecycle、不进入 Relation count 或 resting Network。

范围关系只保存直接陈述。`scope_within` 的 transitive closure 可推导但不显示成“直接关系”；其图允许一个 Group 处于多个真实上位范围内，但禁止 cycle。`partially_overlaps_with`、`complements` 与 `contrasts_with` 语义对称，只保存一份 normalized edge；其余类型保留方向。`evolved_from` 必须保存 direct / indirect lineage distance，只有 direct lineage 进入默认邻接。任何 inverse label 都由同一 Relation 派生，不建立镜像记录。

## 11.2 Group Relation schema

Group Relation 复用正式 Relation 对象，但增加 scope-level 约束：

```text
Relation
  identity
    relation_id
    current_revision_ref

  continuity
    assertion_disposition: maintained | ended | superseded | retracted
    successor_relation_refs[]

  maintenance
    change_condition: no_material_change | changes_available | review_due | transition_in_progress
    open_review_case_refs[]
    open_challenge_refs[]

  lifecycle
    lifecycle_state: current | archived | trash

  lineage
    formation_basis
    derivation_method?: aggregated_paths
    adopted_by?
    revision_history

RelationRevision
  relation_revision_id
  endpoints
    from_ref: Group
    to_ref: Group
    from_role
    to_role
  meaning
    relation_type: GroupRelationType
    relation_statement
    inverse_reading_label?
    why_it_matters
    applicability?
    qualifiers[]
    valid_from? / valid_to?
    exceptions_or_limits[]

GroupRelationSupportSetRevision
  target_relation_revision_ref
  supporting_paths[]
  supporting_node_refs[]
  supporting_relation_revision_refs[]
  evidence_binding_refs[]
  exclusions[]
  assessed_at

RelationCandidate
  proposed Group endpoints / statement / type / applicability
  why_suggested
  basis_refs[]
  candidate_state: open | adopted | dismissed | expired
```

Qualifier / Applicability 属于 RelationRevision 的意义；Evidence 与 supporting paths 属于 Binding / Support Set。支撑集合变化默认不创建语义 Revision，也不直接改变 assertion disposition。

## 11.3 Cross-group exit 不是 Group Relation

以下都可以成为真实、可进入的跨群路径，但单独出现时不创建 Library Network edge：

- 两个位于不同 Groups 的 Nodes 之间存在 maintained current Relation；
- 同一个 canonical Node 在两个 Groups 有 Placements；
- Topic Promotion 后原位置留下 Gateway；
- 用户保存一条跨群 Path；
- Group Overview 引用另一个 Group 中的 Node；
- 一次 Ask 同时使用两个 Groups。

Group Map / Topic Overview 可以显示：

```text
当前 Node / Placement
  → maintained current Node Relation / Reference / manual Path step
  → 目标 Node / Placement
  → 目标 Group
```

这叫 cross-group exit。它说明“可以从这里走过去”，不说明“两个知识范围整体上是什么关系”。只有独立 Direct Group Relation，或通过完整审查后 accepted 的 Aggregated Group Relation，才进入 Library Network truth。

## 11.4 直接断言与聚合断言

### Direct Group Relation

来源：

- 用户明确选择 Groups，完成 statement、type、direction 与 Applicability，并亲自提交。

它可以没有外部 Evidence；产品仍保存 user-asserted basis、当前依据与限制。可靠来源直接陈述、带类型导入和 AI 抽取都可能选错 endpoints、direction 或 Applicability，因此先形成 source-explicit / import RelationCandidate，不以 Direct 名义绕过用户采用。

### Aggregated Group Relation

发现信号可以来自：

- 多条已接受的跨群 Node Relations；
- 多个 core / bridge Placements；
- 一个 Group Overview 对另一个 Group 的明确依赖；
- 稳定、重复使用的 typed cross-group paths。

这些输入先形成 Aggregation Signal，不直接成为 RelationCandidate。系统主动提出 Candidate 前必须逐项通过：

1. endpoints 与两侧 Boundary Revisions 可解析；
2. 能写成明确、可限定的群级 statement；
3. proposed relation type 明确允许这种聚合；
4. 底层 Relations 当前、正式且 Applicability 可合并；
5. assertion、content、provenance 与 traversal 重复已折叠；
6. 支撑形成 bilateral-core、anchor-and-spread 或 named-subscope，不是 fringe-only；
7. 方向与 endpoint roles 一致；
8. CounterSignals 与 exceptions 已检查；
9. strongest-unit removal 后仍有与显著性相符的 standing，并满足 attention / suppression budget。

同一 canonical Knowledge 的多个 Placements、同一 Relation 的 inverse / mirror、同一 Source lineage 的多个报告或摘录、同一 Query / Saved Path 的重复经过，都只产生一个相应 lineage，不按线条计数。系统默认至少需要两个 Effective Support Units，但这只是下限；任一 gate 失败都不能被数量抵消。

通过后形成的 RelationCandidate 必须显示：

- statement、direction、Applicability 与 why it matters；
- 两侧 Boundary coverage 与去重后的 Effective Support Units；
- 哪些 signals 被折叠、排除或只保留为 exits；
- CounterSignals、exceptions 与 strongest-unit removal result；
- 接受后 Library Network 会如何变化。

没有通过时，真实 paths 继续作为 cross-group exits。产品不显示“关系缺失”、不积累整理债务，也不以 `related_to`、edge strength 或 confidence score 填补空白。

## 11.5 Review trigger

Group Relation 在以下情况创建 Review Case，并在不改变 maintained disposition 的前提下进入 review_due：

- 主要 supporting path 被 supersede、retract 或删除；
- supporting core Nodes 不再属于任一 Group；
- Group boundary 发生重大变化；
- Applicability 改变；
- 用户拆分或合并其中一个 Group；
- 新证据使关系类型或方向不再准确。

底层变化先创建新的 Support Set Revision，不会让关系静默消失，也不会自动改成另一个类型。用户可以 Maintain、Revise、End、Supersede、Retract 或 Defer；Supersede 必须指向 successor。

---

# 12. Library Network 与 Group Relation Inspector

## 12.1 Library Network resting state

默认只显示：

- Groups；
- maintained、lifecycle=current、当前 Applicability 有解释价值的 Group Relations；
- 当前 Selection / Query 使用的高亮路径；
- 固定或最近进入的 Groups。

不显示：

- Topics；
- 所有 Nodes；
- embedding 相似边；
- 共享一个标签的边；
- 未接受 Proposal；
- 本次 Retrieval Jump。

## 12.2 选择一个 Group

选中 Group 后：

- 保持 Group 位置稳定；
- 显示约 3–7 条当前最重要直接关系；
- 其他 Groups 降低视觉权重但不全部消失；
- 右侧显示 Group boundary、主要 Topics 和关系摘要；
- 用户可进入 Group 或选择一条 Relation。

## 12.3 Relation Inspector 的阅读顺序

1. `它们为什么相连`：一句 relation statement；
2. `为什么重要`：理解 A 如何改变 B；
3. `通过哪些知识相连`：bridge Nodes 与 supporting paths；
4. `依据和限制`：Evidence、Applicability、exceptions；
5. `当前状态`：谁建立、是否已接受、是否需要复核；
6. `继续探索`：进入 A、B 或一条具体 path。

默认不显示图算法分数、边权、共现次数或 embedding distance。

## 12.4 List Equivalent

列表至少显示：

- From Group；
- relation statement；
- direction；
- To Group；
- formation basis；
- current state；
- why now visible。

用户可以完成选择、过滤、检查依据、打开 endpoint、保存 Path 和返回，不能只是无障碍附录。

## 12.5 同一 Group pair 的 Relation Bundle

两个 Groups 可以同时存在 `provides_foundation_for`、`contrasts_with` 和 `complements` 等不同陈述。Library Network 不把它们合并为 `related_to`，也不叠画成几条难以选择的线；Shared Knowledge Observation另行进入可选 Lens，不成为 Bundle member。

`Relation Bundle` 只是 presentation record：

- members 是独立 `relation_id` 列表；
- 默认 statement 来自用户固定或当前任务中最有解释价值的 accepted Relation；
- 显示 `另有 N 条关系` 并可完整展开；
- 每条 Relation 保留 direction、inverse label、Applicability、support、state 与 history；
- Bundle sort、collapse、Query Highlight 和布局位置都不修改 Relation truth；
- 其中一条 review_due / superseded 不污染同 pair 的其他 Relations。

---

# 13. Group Overview 如何承载边界与跨群关系

本章规定 Overview 应表达哪些 Group 语义；identity、Block types、Support Map、alignment、更新与 scope transformation 的完整行为遵守 `AI-native-个人知识库-Overview形成编辑与更新合同-v1.0.md`。

所有 Group Overview 使用相同五问：

1. 这是什么；
2. 由什么组成；
3. 当前知道什么；
4. 哪里不确定或在变化；
5. 下一步去哪里。

本合同增加两个约束：

## 13.1 边界先于内容数量

Bare Group 即使没有 Nodes，也可以用用户命名与原始边界成立。系统不因为内容少就生成泛化摘要。

## 13.2 Related Groups 不是推荐 Feed

Related Groups 只显示：

- 已接受 Group Relations；
- 当前 Query 使用的临时 Group path，并明确临时性；
- 少量可解释 Proposal，位于 P1 / P2 而非默认正文。

每个入口说明关系，不写“你可能还喜欢”。

## 13.3 Topic Overview 不复制 Group Overview

Topic Overview 只解释：

- 当前分支在 Group 中的位置；
- 代表 Nodes；
- 子主题；
- 当前缺口；
- 跨分支 / 跨群出口。

它不重复整个 Group 的边界、所有重要结论和全部 Related Groups。

Topic Overview 与 Group Overview 是绑定不同 scope 的两个 identity。Topic Promotion 时，旧 Topic Overview 保留在 Gateway history，新 Group 创建新的 Overview；二者不建立双向 live prose。结构与代表知识使用 Projection 重新绑定，Editorial prose 只通过可检查 proposal 迁移。

---

# 14. AI 建议边界

## 14.1 AI 可以提出

- 新 Group boundary Working content；
- Topic hierarchy 改进；
- Placement role 和 contextual summary；
- Topic → Group Promotion；
- Group Split / Merge；
- Group RelationCandidate；
- 可能重复的 Group identity。
- 从 Unplaced Knowledge、Sources、View 或重复路径形成的 Group Candidate；

## 14.2 AI 必须解释

每项建议至少显示：

- 当前结构中的问题；
- 建议后的认知收益；
- 使用了哪些 Nodes、Sources、Paths 或用户行为；
- 会移动、共享或保持哪些 Placements；
- 受影响的 Overview、Relations、Saved Paths 与 Answers；
- 不接受建议是否有实际后果。
- 为什么它应是 Group，而不是 Topic、View、Saved Path 或相似度簇；
- 哪些候选被明确排除，以及排除理由。

## 14.3 AI 不能静默执行

- Topic Promotion；
- Group Split / Merge / Absorb；
- Group Relation accept；
- boundary 大幅改写；
- Node 在多个 Groups 之间批量移动；
- Group identity 合并；
- 旧 Group redirect。
- Group Candidate accept，及其批量 Placements / Attachments / Topics 提交。

这些都是 A3 正式变更，必须通过 Change Set。

---

# 15. 规模与退化规则

## 15.1 100+ Groups

产品使用：

- Search；
- pinned / recent；
- primary kind / facet filters；
- scope_within relation 的可选聚合 View；
- stable Group catalog 与 manual order；
- user-created Saved Group Views。

不通过恢复未定义的 Subgroup、Shelf、Collection 或 Workspace 容器，也不把所有 Groups 压成小字解决。若 30–50 Groups 的真实任务证明还需要命名分区，只能先验证为不改变 Boundary、Placement、Ask scope 与 Relation truth 的纯 Library layout；在验证前不新增本体名词。

## 15.2 大 Group

当一个 Group 有数千 Nodes：

- 默认只显示 Topic structure 和 representative Nodes；
- Node list 使用筛选、搜索和分页 / 虚拟化；
- Overview 不尝试总结每个对象；
- Group Map 不加载全部 Node；
- AI 可以建议 Promotion / Split，但不能仅因数量自动执行。

## 15.3 未连接 Group

未连接不等于错误：

- Library Network 显示它存在但不伪造关系；
- Group Overview 仍可完整使用；
- Ask / Search 可检索；
- 系统只有找到可解释依据时才提出 RelationCandidate；Candidate 仍不进入 Current 图层。

## 15.4 边界重叠

两个 Group 大量共享 Nodes 时，系统依次判断：

1. 是否是同一 Group identity；
2. 是否只是不同 Applicability；
3. 是否应 Merge；
4. 是否是合法 `partially_overlaps_with`，还是只有 shared-core observation；
5. 是否一个应 Promotion / Absorb；
6. 是否保留两个 Groups 但减少重复 Placements。

不能只显示“相似度 86%”。

---

# 16. 代表性场景

## 16.1 “知识模型”应该是 Topic

在“AI Agent 产品设计”中，“知识模型”主要组织 Node、Relation、Applicability、Evidence 等知识，含义依赖父 Group。

预期：

- 保持 Topic；
- 拥有局部 Overview；
- Node 可跨到“认知科学”；
- 不因为内容多自动变成 Group。

## 16.2 “长期记忆系统”可以成为 Group

若它已经拥有独立边界、多个 Topics、自己的来源与反复独立 Ask，且与“认知科学”“AI Agent 产品设计”分别有基础与应用关系：

预期：

- 系统可提出 Promotion；
- 原 Topic 保留 Gateway；
- 相关 Nodes 按用户选择 move / share；
- 建立 `scope_within` 或 `applies_to` 等准确 Group Relation；
- 旧 Saved Paths 可继续打开。

## 16.3 同一 Node 跨三个 Groups

“情境依赖检索”出现在“认知科学”“长期记忆系统”“AI Agent 产品设计”。

预期：

- 一个 canonical Node；
- 三个 Placements；
- contextual summaries 分别解释理论、系统机制与产品应用；
- Search 打开时可选语境；
- canonical edit 影响全部，contextual edit 只影响一个 Placement。

## 16.4 法国租房的多层 Topic

```text
法国租房
  资格与文件
    身份与居留
    收入证明
    担保
      Visale
      私人担保人
  签约
  入住
```

预期：

- 深层 Topic 合法；
- 只持久化直接 parent；
- Search 可直接打开 Visale 下的 Node；
- DepthTrail 恢复完整路径；
- “担保”只有形成独立跨国 / 跨项目知识范围时才建议成为 Group。

## 16.5 Group Merge

用户发现“Agent 产品设计”和“AI Agent 产品”实为同一 Group。

预期：

- 选择 canonical Group；
- 两个 Topic trees 先并列保留；
- Group boundary / Overview 做 diff；
- Node duplicates 进入单独 identity review；
- 旧 Group URL redirect；
- 历史 Answer Scope 保持可解释。

## 16.6 共享标签不形成群关系

“认知科学”和“法国租房”都包含 Evidence Nodes。

预期：

- Library Network 不显示 Relation；
- shared tag / object type 只支持筛选；
- 如果二者都使用同一具体 Method Node，才可能形成可解释的桥接路径；
- 单次 Ask 同时使用仍只是 Retrieval Jump。

## 16.7 Source-only 进入深层 Topic

用户在“法国租房 / 担保 / Visale”添加 PDF，但没有形成 Knowledge。

预期：

- Source 在全局 Sources 只有一个 identity；
- Source Attachment 指向 Visale Topic；
- Topic 与 Group Sources 都能找回，并说明 exact path；
- 后续 Evidence Binding 与 Attachment 并存，各自回答不同问题；
- detach 不删除 Source 或 Evidence；
- Topic transfer 时 Attachment 进入同一影响预览。

## 16.8 Boundary 收窄但内容暂留

Group Boundary 新增 excludes“通用模型训练”，已有两条相关 Knowledge。

预期：

- 创建 Boundary Revision；
- 两条 Knowledge 不自动移动或归档；
- 以 reference / bridge role 显示 boundary tension；
- 用户可分别保留、move Placement、share 到另一 Group 或再次修订 Boundary；
- Overview、Ask default 与 Group Relations 显示影响；
- 无红点倒计时或重复催促。

## 16.9 Topic Merge 与跨群 Transfer

“查询与检索”与“AI 回答”合并为“知识调用”，其中“失败与恢复”随后迁到另一个 Group。

预期：

- Merge 选择 canonical Topic，另一个 Topic redirect；
- child Topics、Placements、Attachments、Overviews 与 Paths 分别映射；
- duplicate Placement 可合并，duplicate Knowledge identity 另行判断；
- Transfer 不是普通 drag，重新检查 Boundary、Overview、source policy、Ask history 与 exits；
- 后续 Undo 不删除 transfer 后新增知识。

---

# 17. 内部产品质量指标

## 17.1 核心指标

- **Group Orientation Success**：用户能否快速说清 Group 边界和主要 Topics；
- **Boundary–Contents Comprehension**：用户能否区分 Boundary intent、Placements / Attachments 与动态 View；
- **Boundary Tension Resolution**：超出边界的内容能否被合理保留、移动或促成 Revision，而非误删；
- **Boundary Correction Rate**：AI 建议边界被用户大幅重写的比例；
- **Direct / Descendant Scope Comprehension**：Topic 查询与 Overview 是否让用户知道内容直接位于哪里；
- **Root Placement Clarity**：Group root content 是否被正确理解为已归入 Group；
- **Source Context Retention**：Source-only 是否能从原 Group / Topic 重新进入；
- **Topic Transformation Continuity**：merge / split / transfer 后旧路径、Overview、Attachments 与 history 的可解释比例；
- **Topic Promotion Reversal**：Promotion 后短期撤销或重新吸收的比例；
- **Duplicate Group Rate**：后续被确认同一 identity 的 Groups 比例；
- **Node Reuse Fidelity**：跨群使用时复用 canonical Node 而非复制的比例；
- **Placement Role Clarity**：用户能否解释同一 Node 为什么在多个位置；
- **Group Relation Explanation Success**：用户能否说清 Library Network 边为何存在；
- **Cross-group Continuity**：跨群后 Back、Placement 和 Path 是否恢复；
- **Structure Change Recovery**：Split / Merge / Promotion 后旧链接与历史路径可解释比例。

## 17.2 反指标

- Group 数量增长；
- Topic 深度；
- 每个 Node 的 Placement 数；
- Library Network 边数量；
- AI Promotion 建议接受率；
- “孤立 Group”清零率；
- 所有内容必须归类的完成率。

---

# 18. 验收标准

## 18.1 对象边界

- 用户能判断代表案例是 Group、Topic、Node 还是 View；
- Group 不因内容少被迫降为 Topic；
- Topic 不因内容多自动变成 Group；
- View 不自动获得知识边界和 Relation；
- 产品中不存在未定义 Subgroup 对象。

## 18.2 结构一致性

- Group Membership 可以从 Placements 完整重建；
- `member_node_refs` 和 Topic children 只作为 derived index；
- Topic parent 不可跨 Group；
- Topic hierarchy 不产生 cycle；
- Remove Placement 不删除 Node；
- 同一 Node 的多个 Placement 不复制 canonical body。

## 18.3 Promotion / Split / Merge

- Topic Promotion 保留旧 Topic Gateway 和历史路径；
- Promotion 不复制 Node、Evidence 或 Source；
- Group Absorb 不静默删除 Group identity；
- Merge 不自动合并 Node identities；
- Split 中每个 Placement 可以 move / share / keep；
- 所有变化提交前可查看 Overview、Relation、Answer 和 Saved Path impact。
- Topic Promotion 创建新的 Group `overview_id`，原 Topic Overview 保留 Gateway history 与 lineage；
- Split 不按 Topic 或段落机械切 Overview prose，每个新 scope 独立决定 Editorial Blocks 并重建 Projection；
- Merge 明确选择 canonical Overview，非 canonical Overview 进入 historical redirect，重复 prose 不自动拼接；
- Absorb 只向目标 Overview 提出 Semantic Diff，不把被吸收 Group 的整篇正文追加进去。

## 18.4 Group Relations

- 单一标签、共同来源或相似度不形成正式 Group Relation；
- 单条跨群 Node Relation、共享 Node、Gateway、Saved Path 或 Query Route 只形成 cross-group exit / supporting path，不自动进入 Library Network；
- 每条 Library Network 边有 relation statement、why it matters 和 supporting paths；
- 聚合关系在接受前是 RelationCandidate，采用后才物化为 Relation；
- 多条 raw paths 必须先折叠为 Effective Support Units；两个 units 只是下限，仍需通过九道资格门；
- 支撑必须触及 Boundary：bilateral-core、anchor-and-spread 或 named-subscope 合法，fringe-only 只保留 exits；
- relation type 使用专属 policy；`scope_within` 不可聚合，`evolved_from` 需要 lineage，因果 / 约束关系不能由共现与相似度产生；
- CounterSignals、exceptions 与 strongest-unit removal 进入 Assessment，不用 confidence / edge weight 代替；
- 底层 path 变化先创建 Support Set Revision 与 Review Case，只触发 review_due，不静默删除或改类型；
- 同一 Group pair 的多条 Relations 保持独立 identities；Bundle 只折叠呈现，不合并语义或状态；
- 有方向 Relation 的 inverse label 解析到同一 relation_id，不保存镜像边；
- Topic / Placement / Evidence 不进入正式 Semantic Relation endpoint；
- Group Split / Merge 对每条边建立 RelationTransitionCase；successor 只获得 Candidate，近似重复不自动 merge，self-edge 只保留历史；
- Ended、Superseded、Retracted 与 Archived 分开，Superseded 必须指向 successor；
- Library Network 和 List Equivalent 表达相同关系真相。

## 18.5 规模与降级

- 100+ Groups 仍可通过 Search、filter 和稳定选择定位；
- 大 Group 默认不显示全部 Nodes；
- 深层 Topic 可直接进入并恢复完整 DepthTrail；
- 未连接 Group 不显示伪边；
- AI unavailable 时结构、Placements、Group Relations 与历史仍可使用。

## 18.6 Boundary、Topic Scope 与 root content

- Boundary Revision 与 Contents / View 分离；
- Boundary change 不自动增加、移动或删除 Knowledge / Source；
- governing purpose 被替换时必须使用 successor / split / merge；
- Topic direct / descendant scope 可分别查询；
- descendant content 不在每个 ancestor 生成 Placement；
- 同一 Knowledge 在 descendant scope 中按 identity 去重并保留所有 paths；
- Group root Placement 参与 Group Scope，且不进入 unplaced View；
- boundary tension 不成为知识质量分数或必须清零的任务。

## 18.7 Source Attachment 与 Topic lifecycle

- Source-only 可以 attached 到 Group / Topic 并长期找回；
- Attachment、Placement、Evidence Binding 与 Source identity 不混淆；
- detach 不删除 Source / Evidence / other Attachments；
- Topic rename / move 保持 identity 与 attachment targets；
- Topic merge 选择 canonical identity，Split 为新范围建立新 identities；
- cross-group Topic Transfer 有 Boundary、Overview、Attachment、Ask history 与 exit impact；
- Topic delete 默认不删除 Knowledge 或 Source；
- 所有 transformation 保留 redirects、lineage 与可撤销 Change Set。

## 18.8 Group formation 与 Candidate

- 六种形成路径最终生成同一种 Group identity；
- Blank Group 只需名称，非空白路径显示与影响相称的纳入 / 排除、Placement / Attachment 与 Topic 预览；
- View / Search conversion 只冻结当前显式选择，future matches 不进入 Group；
- Source bundle 可以永久停在 Source Attachments，不制造占位 Knowledge；
- Imported hierarchy 不把每个 folder 自动变成 Group；
- Group Candidate 不进入 canonical Library、Network、Search、Ask、Overview 或导出；
- Reject / discard 不创建任何结构，并按 evidence signature 抑制重复提示；
- similarity、count、tag、共同 Source 或一次 Query 不能单独触发 Group creation。

---

# 19. 研究依据与产品推论

## 19.1 W3C SKOS

SKOS 将 Concept、Concept Scheme 与 Collection 分开；Collection 可以是有序集合，但不等同于 Concept，也不应直接使用概念语义关系。SKOS 还区分直接 broader / narrower 与由其推导的 transitive closure，并为不同 scheme 之间的 mapping 保留独立语义和 provenance。[SKOS Reference](https://www.w3.org/TR/skos-reference/)

本产品不是 SKOS 实现，但吸收三个重要结构原则：

- Node、Topic collection 与 Group scope 不应是同一种对象；
- 只保存直接 Topic parent，祖先路径由系统推导；
- Group 间映射和 Group 内结构必须分开，并保留形成依据。

## 19.2 Capacities

Capacities 官方文档强调一个对象可以出现在多个页面和 collections 中，而不被单一文件夹拥有；它也区分 tags、collections 与 objects，并明确“链接越多不一定越有帮助”。[Networked note-taking](https://docs.capacities.io/tutorials/networked-note-taking) · [Tags vs. Collections](https://docs.capacities.io/tutorials/tags-vs-collections)

本产品据此坚持：

- canonical Node 与多个 Placements 分开；
- Topic / View / Group 不因都能“收集内容”就合并；
- Library Network 只保留有解释价值的关系。

## 19.3 Anytype

Anytype 官方文档把 Object 视为最小可链接单位；Collections 手工收纳多种对象，Queries 只是从 Graph 中按条件返回结果；Properties 可以表达对象连接，Graph 显示方向。[Objects](https://doc.anytype.io/anytype-docs/getting-started/object-editor) · [Collections](https://doc.anytype.io/anytype-docs/getting-started/sets/collections) · [Queries](https://doc.anytype.io/anytype-docs/getting-started/sets) · [Properties](https://doc.anytype.io/anytype-docs/getting-started/types/relations)

本产品进一步收敛：View 不拥有成员，Group 不是动态 Query，结构归属与正式语义 Relation 使用不同对象。

## 19.4 Heptabase

Heptabase 官方资料显示，同一 Card 可以被放到 Whiteboard 组织；Whiteboard 布局和 Card 内容拥有不同版本语义，删除 whiteboard instance 也不等于删除 card identity。其性能文档还建议在单板过密时拆分 sub-whiteboards。[MCP and whiteboard context](https://support.heptabase.com/en/articles/12679581-how-to-use-heptabase-mcp) · [Collaboration and card instances](https://support.heptabase.com/en/articles/10510497-collaboration-q-a) · [Version history](https://support.heptabase.com/en/articles/10448124-how-to-restore-cards-and-whiteboards-from-version-history) · [Performance](https://support.heptabase.com/en/articles/11430704-troubleshooting-performance-and-lag-issues-in-heptabase)

本产品吸收“内容 identity 与出现位置分开”，但不把自由布局设为 canonical hierarchy；Group 和 Topic 的结构需要可预测的 parent、Placement、redirect 与 Change Set。

## 19.5 Zotero 与 direct / descendant collection scope

Zotero 官方 Collections 模型允许同一 item 进入多个 collections 而不复制；删除 collection 或从 collection 移除 item 默认不删除 item；`Show Items from Subcollections` 又把直接成员与后代范围作为独立显示选择。[Collections and Tags](https://www.zotero.org/support/collections_and_tags)

本产品据此强化三项边界：

- Source identity 与 Source Attachment 分开，detach 只取消当前语境；
- Topic direct scope 与 descendant scope 分开，后代不会在祖先生成镜像 Attachment / Placement；
- Source-only 可以直接保存到 Group / Topic，而不被迫先形成 Knowledge。

Zotero 的 collection 是材料组织工具，不等于本产品的 Knowledge Group Boundary、Topic Overview 或 Knowledge truth；这些仍是本产品决定。

## 19.6 Capacities / Anytype 的 curated membership 与 dynamic query

Capacities 官方把 Collection 描述为人工决定 membership 的范围，把 Query 描述为按规则自动更新的 saved filter；同一内容可进入多个 Collections。Anytype 同样把手工添加对象的 Collection 与从整个 Graph 动态获取对象的 Query 分开。[Capacities Queries vs. Collections](https://docs.capacities.io/faq/editing/queries-vs-collections) · [Capacities Tags vs. Collections](https://docs.capacities.io/tutorials/tags-vs-collections) · [Anytype Collections](https://doc.anytype.io/anytype-docs/getting-started/sets/collections)

本产品据此不让 View result、Ask Used Context 或 similarity cluster 改写 Group Membership；它进一步把 Group Boundary 与 curated Placement 也分开，因为“这个范围打算理解什么”与“当前放了哪些知识”仍不是同一判断。

## 19.7 Tana Workspace：系统边界不等于知识群

Tana 官方把 Workspace 定义为顶层容器，拥有 members、Home、daily notes、schema、library、settings、trash、publishing / export 与 access boundaries。[Tana Workspaces](https://outliner.tana.inc/learn/features/workspaces)

产品推论：Knowledge Group 不应复制 Workspace 责任。它没有独立权限、schema、settings、trash 或隔离导出边界；这些属于一个本地 Knowledge Library 的系统层。否则“一个个知识群”会退化为多个彼此割裂的小应用。

## 19.8 Tana Search Nodes、Obsidian Bases 与 Notion Wiki：查询、视图和方向面不同于范围

Tana Search Node 保存条件并实时返回原节点 references；修改结果会修改原对象。Obsidian Bases 让多个 Views 在同一份 notes / properties 上保存独立 filters、sort、group 与 layouts。Notion Wiki 又把可策展 Home、穷尽的 All pages 与按 owner 形成的 Views 分开。[Tana Search Nodes](https://outliner.tana.inc/learn/features/search-nodes) · [Obsidian Bases](https://obsidian.md/help/bases) · [Notion Wikis](https://www.notion.com/help/wikis-and-verified-pages)

产品推论：动态 Query / View、Library 方向面与 Knowledge Group 是三种责任。View 可以成为发现 Group Candidate 的入口，但规则和 future matches 不能成为 membership；Library Resume 可以提供方向，却不创建第二个 Home 或第二套知识真相。

---

# 20. 对后续视觉设计的约束

本合同不授权开始原型。未来视觉设计必须证明：

1. Group、Topic、Node 和 View 在视觉与动作上可区分；
2. Library 不显示未定义的 Subgroup 容器；
3. Topic tree 移动、Promotion 与 Group Split / Merge 有真实影响预览；
4. 同一 Node 的多个 Placements 显示不同语境，但正文 identity 明确唯一；
5. Topic Gateway 能说明“已成为独立知识群”，不会复制两套内容；
6. Library Network 边选择后能展开 relation statement、supporting paths 和 Evidence；
7. 候选 Group Relation 与正式 Relation 不在同一默认图层；
8. `scope_within` 可以帮助聚合浏览，但不把 Group 变成可级联删除的文件夹；
9. 100+ Groups、深层 Topic 与未连接 Group 都有真实状态；
10. “方向 3 的层级阅读 + 方向 2 的关系空间”共享同一 Group / Topic / Placement truth，而不是两套各自生成的结构。
11. Promotion、Split、Merge 与 Absorb 的 Overview identity、lineage、Projection rebind、Editorial alternatives 和 historical redirect 都有可检查设计证据。
12. Boundary、当前内容与 View / Query 结果不会被一个含混的“此群包含”视觉混在一起；
13. Topic 的`直接放在这里 / 包含子主题`可被理解，但不重复展示同一 Knowledge；
14. Group root content 与 unplaced Knowledge 有不同进入语言，不把空白 Group 变成整理 Inbox；
15. Source-only attached 到深层 Topic 后可从 Topic 与 Group Sources 找回，且 Attachment 与 Evidence 不混淆；
16. Topic rename / move / merge / split / transfer 的后果与 redirect 可检查，普通 drag 不掩盖跨群 Scope 变化。
17. Blank、Knowledge selection、Source bundle、Topic promotion、View snapshot 与 imported hierarchy 看起来是六个入口，但最终对象、Overview 与阅读体验完全一致；
18. View 转 Group 明确显示`当前选择`与`未来匹配不会自动加入`，且能逐条检查 existing Placements；
19. AI cluster 只进入可拒绝的 Candidate 预览；正式 Library 与 Network 不出现半成立群；
20. 100+ Groups 通过 catalog、Saved Group Views、Pins、Search 与 manual order 定位，不引入第二层 Shelf / Collection 容器。

---

# 结论

这个知识库的核心并不是把一切都变成图，也不是让用户在 Group、Topic、Tag、Folder、Collection 和 Page 之间做分类考试。

它需要一套稳定而克制的结构：

> **Group 定义一个可以独立居住的知识范围；Topic 组织这个范围内部的理解顺序；Node 保存可跨范围复用的知识；Placement 说明同一知识此刻在哪里、承担什么角色；Group Relation 解释两个知识范围为什么真正相连。**

当这五者的职责清楚后，丰富层级不会变成目录迷宫，跨群复用不会复制知识，Library Network 也不会用相似度制造一张看似丰富但不可相信的网络。
