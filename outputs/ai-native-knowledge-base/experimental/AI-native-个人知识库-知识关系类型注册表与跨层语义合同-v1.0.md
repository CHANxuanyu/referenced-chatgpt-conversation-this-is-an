# AI-native 个人知识库

## 知识关系类型注册表与跨层语义合同 v1.0

> **权威状态（2026-08-10）：EXPERIMENTAL_APPENDIX。25-type registry 不冻结默认 UI 或 schema；只作为 v6 六类关系意图的研究候选。**  
> 日期：2026-08-10  
> 文档性质：终局产品本体、Knowledge-level Relation 类型、跨对象语义、迁移、语言与设计证明合同；不是数据库 enum、图数据库选型、OWL 实现、MVP 范围或原型授权  
> Canonical 产品定义：`AI-native-个人知识库-终局产品设计文档-v4.0.md`  
> 上游身份与粒度：`AI-native-个人知识库-产品对象层级与身份治理合同-v1.0.md`、`AI-native-个人知识库-知识节点粒度与内容组成合同-v1.0.md`  
> 上游生命周期：`AI-native-个人知识库-关系陈述生命周期与网络可信性合同-v1.0.md`；Relation、Revision、Candidate、Evidence、Challenge、Disposition 与 History 继续以该合同为准  
> 相邻群级合同：`AI-native-个人知识库-群级关系类型注册表与语义互斥合同-v1.0.md`；同名谓词不代表可以跨端点复用同一 TypeDefinition  
> 下游体验：`AI-native-个人知识库-知识深度与关系探索合同-v1.0.md`、`AI-native-个人知识库-AI查询与知识回答合同-v1.0.md`、`AI-native-个人知识库-产品语言与渐进披露规范-v1.0.md`  
> Question lifecycle 下游真相：`AI-native-个人知识库-问题知识、未知与求解生命周期合同-v1.0.md`对 QuestionTargetReference 的版本、目标类型、role、standing、Resolution 与 reopen 语义拥有覆写权；本合同只维护其与 ordinary Relation 的边界  
> 真实内容验证：`AI-native-个人知识库-真实端到端使用样例与设计数据夹具-v1.0.md` 已用一般住房补助规则、2026-07-01 特定人群条件与职业活动例外验证 `qualifies` / `contradicts`、Evidence / basis / target 分权和 cross-group exit 边界  
> 第二真实内容验证：`AI-native-个人知识库-第二真实端到端夹具-概念学习、多语境复用与群关系-v1.0.md` 已用 11 条 Knowledge Relations 验证 `provides_foundation_for / component_of / contributes_to / explains / supports / qualifies`的强度边界，并证明 technical comment 的 EvidenceBinding `challenges`不能冒充 `knowledge.contradicts`，研究条件收窄通常形成 Revision / qualifier 而不是撤回  
> 用户意图：产品仍然是知识库；纵向从 Overview 深入知识正文、主张与证据，横向沿少量有明确意义的关系探索  
> 当前边界：只定义完整产品；不修改 Ardot，不绘制新 Frame，不制作可点击原型

---

# 0. 执行结论

## 0.1 真正的问题不是“关系类型不够多”

现有设计已经区分结构、证据、引用、正式关系与检索跳转，但 Knowledge-level 词表仍然混入了四类不属于普通语义边的东西：

- **证据作用**：Evidence Binding 里的 `supports`，回答 Claim Support 里的 `supports`，与 Knowledge 对 Knowledge 的论证关系同名；
- **身份与版本变化**：`supersedes`、`retracts` 被放进关系词表，却实际改变当前有效版本或陈述处置；
- **问题生命周期**：`reopens`、`uncertain_about` 描述的是 Question 状态或目标，不是两个知识对象之间稳定的语义；
- **含糊兜底**：`blocks`、`overlaps_with` 容纳了彼此不兼容的意思，系统可以“选中一个词”却无法说明自己究竟承诺了什么。

如果不先解决这些混用，图谱即使视觉上漂亮，也会出现三种产品伤害：

1. 用户点击一条线，无法知道它是自己的判断、来源证据、AI 推断，还是旧版本的历史结果；
2. Ask 可以把“共同支持本次回答”误写成“两条知识互相支持”；
3. Network 可以把状态变化画成概念关系，使探索路径看似丰富、实际上不可验证。

因此本轮冻结的核心不是更多 edge，而是：

> **只有两个 Knowledge identities 之间、具有可回读陈述、明确端点角色、必要限定与独立真值的连接，才是 formal Knowledge Relation。证据作用、来源追溯、引用、结构、身份继承、处置动作、问题状态与一次检索路径各自拥有自己的对象。**

## 0.2 Canonical registry：五个家族、二十五种正式类型

Knowledge-level formal registry 冻结为二十五种：

### A. Classification & Composition / 分类与组成

1. `knowledge.subtype_of`；
2. `knowledge.instance_of`；
3. `knowledge.exemplifies`；
4. `knowledge.defines`；
5. `knowledge.component_of`。

### B. Explanation & Causal Structure / 解释与因果结构

6. `knowledge.explains`；
7. `knowledge.causes`；
8. `knowledge.contributes_to`；
9. `knowledge.enables`；
10. `knowledge.prevents`；
11. `knowledge.depends_on`；
12. `knowledge.provides_foundation_for`。

### C. Argument & Inference / 论证与推导

13. `knowledge.supports`；
14. `knowledge.contradicts`；
15. `knowledge.qualifies`；
16. `knowledge.assumes`；
17. `knowledge.derived_from`。

### D. Comparison & Application / 比较与应用

18. `knowledge.contrasts_with`；
19. `knowledge.similar_to`；
20. `knowledge.partially_overlaps_with`；
21. `knowledge.applies_to`；
22. `knowledge.implements`。

### E. Time & Evolution / 时间与演化

23. `knowledge.precedes`；
24. `knowledge.refines`；
25. `knowledge.evolved_from`。

命名空间 `knowledge.*` 是对象边界，不是工程装饰。同名的 `group.provides_foundation_for` 与 `knowledge.provides_foundation_for` 拥有不同 endpoint、充分性门槛、解释包和 TypeDefinitionRevision，不能因 UI 中文标签相同而共用一条 registry record。

## 0.3 七个旧类型的处理结论

| 旧类型 | 处理 | Canonical 落点 |
|---|---|---|
| `related_to` | 永久移出 formal registry | ReferenceLink、manual Path step 或 ambiguous RelationCandidate |
| `overlaps_with` | deprecated | `partially_overlaps_with`、identity resolution、`subtype_of`、`component_of` 或无正式关系 |
| `blocks` | deprecated | 因果阻止用 `prevents`；先决条件缺失用 `depends_on` |
| `uncertain_about` | 移出 formal registry | Question Knowledge + QuestionTargetReference；或 unresolved Challenge |
| `supersedes` | 移出 ordinary semantic registry | KnowledgeIdentityTransition / successor standing |
| `retracts` | 移出 formal registry | Relation / Knowledge disposition event + rationale |
| `reopens` | 移出 formal registry | Question lifecycle event |

`has_component`、`defined_by`、`builds_on` 继续可作为反向阅读标签，但不另存镜像 Relation。

## 0.4 本文件冻结的五十二项决定

1. **Knowledge Relation 是一条可拥有、可修订、可质疑的知识陈述。** 它不是图上的装饰线。
2. **Formal Relation 的端点必须是两个 Knowledge identities。** Anchor 只限定各端点参与的局部语义，不成为第三端点。
3. **每条 RelationRevision 固定一个 KnowledgeRelationTypeDefinitionRevision。** Registry 更新不静默重解释旧关系。
4. **类型键使用 `knowledge.*` namespace。** Group 与 Knowledge 的同名类型不共享定义。
5. **正式 registry 冻结为五个家族、二十五种类型。** Family 只服务选择、过滤与表达，不可保存为模糊关系。
6. **`related_to` 不进入 formal registry。** 无法说清意义时，产品必须允许“不创建关系”。
7. **结构连接、Evidence Binding、ReferenceLink、Semantic Relation 与 Retrieval Jump 必须保持五类。**
8. **Source provenance 与 `knowledge.derived_from` 分开。** 来源记录回答“材料来自哪里”，Relation 回答“知识怎样由另一知识推导”。
9. **Evidence Binding 的 support role 与 `knowledge.supports` 分开。** 前者是证据对陈述修订的作用，后者是知识前提对主张或决策的论证作用。
10. **Answer Claim Support 与 `knowledge.supports` 分开。** 两条知识共同支撑一次回答，不自动互相建立关系。
11. **所有正式类型都必须声明 canonical direction、inverse reading、symmetry、transitivity、endpoint kinds、required qualifiers 与相邻类型排除。**
12. **Directed type 只保存 canonical assertion。** 反向标签解析到同一个 `relation_id`。
13. **Symmetric type 按 endpoint identity 规范化。** 交换端点不创建第二条记录。
14. **所有类型默认 non-transitive。** 只有 `subtype_of` 等明确允许的 closure 形成 derived path，绝不自动物化 maintained Relation。
15. **所有 formal Knowledge Relations 禁止 self-edge。** Merge 后出现的 self-edge 只保留在历史与迁移报告。
16. **`subtype_of` 只连接 Concept → Concept。** 必须给出分类维度与区分标准。
17. **`instance_of` 连接具体 Entity / Event / Example → Concept 或 type Knowledge。** 它不传递为实例链。
18. **`exemplifies` 表达某对象具体展示了原则、方法、模式或主张。** 它不宣称对象属于一个分类。
19. **`defines` 必须包含定义范围与定义内容。** 提及、链接或引用一个词不构成定义。
20. **`component_of` 只表达语义组成。** Topic hierarchy、Block containment、Placement 与文件夹关系不由它替代。
21. **`explains` 需要 explanatory bridge。** “同时出现”或“相关”不构成解释。
22. **`causes` 需要机制、时间顺序与适用条件。** 它比 `contributes_to` 更强。
23. **`contributes_to` 表达非充分的促成因素。** 它不能用来掩盖不确定的因果主张。
24. **`enables` 表达使某事成为可能。** 它不表示结果已经发生，也不表示单独足以导致结果。
25. **`prevents` 取代含糊的 `blocks`。** 它要求明确的阻止对象与机制。
26. **`depends_on` canonical direction 是 dependent → prerequisite。** 必须说明依赖维度与缺失后果。
27. **`provides_foundation_for` 表达概念、理论、原则或证据框架的基础作用。** 它不是某一条主张的普通支持。
28. **`supports` 连接 premise / reason Knowledge → Claim / Decision Knowledge。** 必须说明 argument bridge 与重叠 Applicability。
29. **`contradicts` 是 symmetric Claim ↔ Claim。** 必须回答同一问题或维度，并且在重叠适用条件下不能同时成立。
30. **`qualifies` 表达收窄、限定、减弱或附加条件。** 它不等于反驳。
31. **`assumes` canonical direction 是 dependent claim / method / decision → assumption。** 必须说明假设承担什么作用。
32. **`derived_from` 需要可检查的推导或变换线索。** 文本引用、来源拷贝与版本修订分别走 Reference、Provenance、Revision。
33. **`contrasts_with` 是 symmetric comparison。** 必须有共同维度与 material difference，不判断谁更正确。
34. **`similar_to` 必须有明确相似维度与仍然重要的差异。** embedding similarity 只能发现 Candidate。
35. **Knowledge-level `overlaps_with` deprecated。** Canonical type 是 `partially_overlaps_with`。
36. **`partially_overlaps_with` 要求共享语义部分与双方各自独立的重要部分。** Same / near duplicate 进入 identity resolution。
37. **`applies_to` 表达潜在适用。** 它不声称目标已经采用或实现。
38. **新增 `implements` 表达实际实现、采用或落实。** 必须提供 implementation trace 或真实上下文。
39. **`precedes` 只表达时间先后。** 时间顺序不自动推出因果。
40. **`refines` 表达在保留核心命题的前提下提高精度、条件或解释力。** 同一 Knowledge identity 的文字修订不创建该关系。
41. **`evolved_from` 表达不同 Knowledge identities 之间的思想、方法或模型演化。** 相似、引用与版本继承不足以成立。
42. **`supersedes` 不是普通语义边。** 谁是当前 successor 由 KnowledgeIdentityTransition 与 standing 决定。
43. **`retracts` 是处置动作，不是 Relation type。** 撤回必须保留 actor、rationale、target revision 与时间。
44. **`reopens` 是 Question lifecycle event。** 它改变问题状态，不改变两个知识对象之间的语义。
45. **`uncertain_about` 改为 QuestionTargetReference 或 open challenge。** “不知道”本身是一种需要保留的知识状态。
46. **类型选择从自然语言意图开始。** 默认界面不展示二十五项长列表。
47. **AI 不确定类型时只产生 ambiguous RelationCandidate。** 不按概率最高的谓词偷偷保存。
48. **Type validation 只生成报告。** 它不自动改 Relation、Knowledge、Question 或 disposition。
49. **Type deprecation 先生成 Migration Review。** 用户可逐条保留 legacy、重分类、结束并建立 successor，或确认无正式关系。
50. **Network 只使用 family-level visual grammar。** 二十五种类型不能变成二十五种颜色或二十五种线型。
51. **Graph、List、Inspector、Overview、Ask 与 History 读取同一 TypeDefinitionRevision。** 任一表面不能自行缩写语义。
52. **本轮继续停留在产品定义阶段。** 视觉只定义必须证明的状态，不解除“不马上做原型”的约束。

---

# 1. 对象边界：先决定“这是不是 Relation”

## 1.1 七种连接对象

| 用户看到的联系 | Canonical 对象 | 它回答的问题 | 是否进入 formal graph |
|---|---|---|---|
| Topic / Group / Block 内的包含 | StructuralConnection / Placement | 它放在哪里、属于哪个阅读结构？ | 否 |
| 来源片段支持或挑战陈述 | EvidenceBinding | 哪段材料怎样影响哪条陈述修订？ | 否 |
| 文中提到、跳转或引用 | ReferenceLink | 我能从这里去哪里、上下文为何提到它？ | 否 |
| 两个 Knowledge 的稳定语义 | KnowledgeRelation | A 对 B 究竟意味着什么？ | 是 |
| 本次搜索或回答临时穿过 | RetrievalJump / QueryRouteStep | 这次检索怎样走到结果？ | 否 |
| 同一 identity 的版本变化 | KnowledgeRevision / Transition | 当前版本从哪个版本、哪个 identity 继承？ | 否 |
| Question 的开启、回答、重开 | QuestionLifecycleEvent | 这个未知现在处于什么状态？ | 否 |

## 1.2 三个 `supports` 必须在语言和数据上分开

### Knowledge semantic support

```text
Premise Knowledge --knowledge.supports--> Claim / Decision Knowledge
```

它是一条可维护的论证陈述，需要 argument bridge、Applicability、作者与 Revision。

### Evidence role

```text
SourceFragment --EvidenceBinding.supports--> RelationRevision / ClaimRevision
```

它说明某段来源怎样影响被绑定陈述，不建立 Fragment 与 Knowledge 的 semantic Relation。

### Answer support

```text
Knowledge / Evidence / Overview --ClaimSupport.supports--> AnswerClaim
```

它只解释一次 AnswerSnapshot 的组成。保存回答也不会自动把支持对象互相连边。

P0 UI 分别说：

- “这条知识支持该主张”；
- “这段来源支持该陈述”；
- “这条知识是本次回答的依据”。

禁止三个表面都只显示一个脱离对象的“支持”。

## 1.3 Relation 的最小资格

一个连接只有同时满足以下条件，才可以成为 formal Knowledge Relation：

1. 两个 endpoint 都解析到 canonical Knowledge identity；
2. 可以写成一条完整、可反向回读的人话陈述；
3. 类型 required qualifiers 齐全，或明确标为尚未齐全的 Candidate；
4. 它不是结构、证据、引用、来源、身份版本、生命周期或检索临时路径；
5. 交换方向或删除限定后，产品仍能判断语义是否改变；
6. 用户或系统可以指出形成依据；
7. 它拥有独立 revision、disposition 与 history。

只要第 2 或第 4 条失败，就不能用 `related_to` 修补。

---

# 2. Canonical 对象模型

## 2.1 KnowledgeRelationTypeDefinitionRevision

```text
KnowledgeRelationTypeDefinitionRevision
  type_definition_revision_id
  type_id: knowledge.*
  registry_revision_ref

  identity
    canonical_key
    family
    status: active | advanced | deprecated | retired
    endpoint_kind_constraints[]

  meaning
    definition
    canonical_statement_template
    inverse_statement_template?
    from_role
    to_role
    symmetry: directed | symmetric
    transitivity_policy: none | derived_closure_only
    self_policy: forbidden
    cycle_policy

  authoring
    availability: primary | contextual | advanced | migration_only
    intent_prompts[]
    required_qualifiers[]
    optional_qualifiers[]
    examples[]
    counterexamples[]

  validation
    meaning_tests[]
    endpoint_tests[]
    adjacent_type_checks[]
    incompatibility_rules[]
    duplicate_rules[]

  presentation
    zh_label
    zh_inverse_label?
    compact_sentence_template
    family_visual_token
    direction_cue

  compatibility
    deprecated_aliases[]
    migration_policy_ref?
    replacement_type_refs[]

  governance
    created_at
    supersedes_definition_revision_ref?
    rationale
```

TypeDefinitionRevision 是被版本化的产品语义，不是随代码更新覆盖的注释。

## 2.2 RelationRevision 绑定类型版本

```text
RelationRevision
  relation_revision_id
  relation_id
  relation_type_ref
  type_definition_revision_ref
  from_knowledge_ref
  to_knowledge_ref
  endpoint_anchor_refs[]
  statement
  applicability_ref
  required_qualifiers{}
  basis_summary
  confidence_posture
  authored_by
  created_at
```

更换同一主张的限定或措辞，可以形成新 RelationRevision。若改类型后已经在回答另一个问题，则结束旧 Relation 并建立 successor Relation，而不是假装“只是编辑了标签”。

## 2.3 TypeValidationReport

```text
KnowledgeRelationTypeValidationReport
  validation_report_id
  target_ref: RelationRevision | RelationCandidate
  type_definition_revision_ref
  evaluated_at
  checks[]
    check_id
    result: pass | fail | indeterminate | not_applicable
    explanation
    affected_fields[]
    adjacent_type_ref?
  overall_result
  suggested_actions[]
```

ValidationReport 是只读判断。它可以说“更像 depends_on”或“缺少共同适用条件”，但不能替用户改写事实。

## 2.4 TypeMigrationReview

```text
KnowledgeRelationTypeMigrationReview
  migration_review_id
  source_relation_revision_ref
  source_type_definition_revision_ref
  target_registry_revision_ref
  reason
  proposals[]
    keep_legacy
    revise_to_type
    replace_with_relation
    reclassify_as_reference
    reclassify_as_question_target
    end_with_successor
    retract
  impact
    network
    overview
    ask
    saved_paths
    history
  user_decision
```

Registry migration 是知识治理，不是后台 schema rewrite。

## 2.5 QuestionTargetReference

```text
QuestionTargetReferenceRevision
  target_reference_revision_id
  question_revision_ref
  target_ref
    object_kind
      group
      topic
      knowledge
      knowledge_anchor
      relation_revision
      property_assertion
      source
      source_fragment
      conflict
      decision_knowledge
    object_id
    revision_or_anchor_ref?
  target_role
    about_scope
    seeks_fact_about
    seeks_explanation_of
    tests_applicability_of
    challenges_claim
    seeks_evidence_for
    investigates_conflict
    informs_decision
  uncertainty_kind
    unknown_fact
    unresolved_explanation
    disputed_claim
    missing_evidence
    applicability_missing
    open_decision
  target_scope_note?
  standing
    current
    ended
    redirected
    target_unavailable
  predecessor_revision_ref?
  created_by
  created_at
```

Question 可以指向多个、不同类型和不同角色的 targets；“对 X 不确定”由 Question revision、Resolution criteria 与 target reference 表达，不需要 `uncertain_about` edge。Target 的 standing 与 Question 的 `resolution_state / pursuit_state / change_state / library_state`分开；target resolved、redirected、unavailable 或 Relation retracted 都不会自动把 Question 标成 resolved / concluded / reopened。

Question 在普通 Relation registry 中仍可作为 Knowledge endpoint，但只有当它与另一 Knowledge 存在独立、稳定、可陈述的二十五类语义时才成立。`about_scope / challenges_claim / seeks_evidence_for`等 target roles 永不映射为 ordinary edge、Group Relation support unit 或 classification closure。

## 2.6 KnowledgeIdentityTransition

```text
KnowledgeIdentityTransition
  transition_id
  predecessor_knowledge_refs[]
  successor_knowledge_refs[]
  transition_kind
    split
    merge
    replacement
    promotion
    identity_correction
  current_standing_effect
  rationale
  actor
  decided_at
  reversible_by_new_transition: true
```

`replacement` 可以在历史中读作“由……取代”，但它不是普通 Relation type。`refines` 与 `evolved_from` 只有在两个 identities 仍各自作为可引用知识成立时使用。

---

# 3. Registry 总表

| Type | UI 人话 | 方向 | 端点核心约束 | 必填限定 | 允许推导 |
|---|---|---|---|---|---|
| `subtype_of` | 是……的一类 | directed | Concept → Concept | 分类维度、区分标准 | closure path |
| `instance_of` | 是……的一个实例 | directed | Entity / Event / Example → Concept | 实例依据 | none |
| `exemplifies` | 具体展示了…… | directed | Example-like → Concept / Principle / Method / Claim | 展示方面、不可外推边界 | none |
| `defines` | 定义了…… | directed | Definition-like → Concept / term | 定义内容、范围 | none |
| `component_of` | 是……的组成部分 | directed | component → whole | 组成维度、完整性边界 | optional closure path |
| `explains` | 解释了为什么 / 如何…… | directed | explanans → explanandum | 解释桥 | none |
| `causes` | 导致…… | directed | cause → effect | 机制、时序、适用条件 | none |
| `contributes_to` | 促成…… | directed | factor → outcome | 作用机制、非充分说明 | none |
| `enables` | 使……成为可能 | directed | condition / capability → enabled outcome | 可行性机制 | none |
| `prevents` | 阻止……发生 | directed | blocker → prevented outcome | 阻止机制、条件 | none |
| `depends_on` | 依赖…… | directed | dependent → prerequisite | 依赖维度、缺失后果 | optional path |
| `provides_foundation_for` | 为……提供基础 | directed | basis → built knowledge | 基础类型、基础作用 | none |
| `supports` | 支持该主张 / 决策 | directed | premise / reason → Claim / Decision | 论证桥、共同适用条件 | none |
| `contradicts` | 与……相矛盾 | symmetric | Claim ↔ Claim | 同一问题、共同适用条件、不相容点 | none |
| `qualifies` | 限定了…… | directed | qualifier → Claim / Decision | 受影响方面、限定效果 | none |
| `assumes` | 以……为前提 | directed | dependent → assumption | 假设命题、承担作用 | none |
| `derived_from` | 由……推导而来 | directed | derivative → basis knowledge | 推导步骤或变换 | optional path |
| `contrasts_with` | 与……形成对照 | symmetric | comparable ↔ comparable | 共同维度、实质差异 | none |
| `similar_to` | 在……方面相似 | symmetric | comparable ↔ comparable | 相似维度、相似依据、重要差异 | none |
| `partially_overlaps_with` | 与……部分重叠 | symmetric | independent identities | 共享语义、双方独立部分 | none |
| `applies_to` | 适用于…… | directed | rule / method / principle → target | 目标情境、适用条件 | none |
| `implements` | 实际落实了…… | directed | realization → principle / method / spec | 采用痕迹、真实情境 | none |
| `precedes` | 先于…… | directed | temporal knowledge → temporal knowledge | 时间依据 | optional temporal path |
| `refines` | 更精确地细化了…… | directed | refined → base | 保留核心、精化维度 | none |
| `evolved_from` | 由……演化而来 | directed | descendant → ancestor | 演化线索、变化维度、directness | optional lineage path |

## 3.1 全局不变量

- `self_policy = forbidden`；
- symmetric types：`contradicts`、`contrasts_with`、`similar_to`、`partially_overlaps_with`；
- inverse label 不建立镜像 Relation；
- closure 只是一条带路径解释的 derived result；
- direct assertion 与 derived path 在图、列表和 Ask 中永远分开；
- endpoint kind 不满足时，不因自然语言“听起来合理”而绕过；
- Applicability 不相交时，`contradicts`、`supports`、`qualifies` 的判断必须失败或 indeterminate；
- AI 发现依据可以是 embedding、共现、共同来源或检索路径，但这些都不是采用后的 relation basis 本身；
- family visual token 不能替代 edge label；
- 同一 pair 可以有多条不同 Relation，但 broad / narrow duplicate 必须进入审查。

---

# 4. Intent-first 类型选择器

## 4.1 第一问不是“选哪个谓词”

创建流程先问用户想表达哪一种完整意思：

```text
它是什么、属于什么，或由什么组成？
它为什么发生、怎样发生，或依赖什么？
一条理解怎样支持、反驳或限定另一条？
两条知识怎样相似、不同、重叠或被应用？
它们在时间或思想演化上怎样相连？
```

进入 family 后最多展示 3–5 个候选完整句，不展示二十五项 enum 墙。

## 4.2 快速选择树

1. **是否在定义类别、实例、例子、定义或组成？** 进入 Classification & Composition。
2. **是否在解释机制、原因、条件、阻止或依赖？** 进入 Explanation & Causal Structure。
3. **是否在判断一个主张怎样作用于另一个主张？** 进入 Argument & Inference。
4. **是否在比较、说明适用或真实采用？** 进入 Comparison & Application。
5. **是否只表达先后、精化或思想演化？** 进入 Time & Evolution。
6. **仍说不清？** 保留 ReferenceLink、manual path、Question 或 ambiguous Candidate；不创建 formal Relation。

## 4.3 相邻类型的最小辨别问句

| 容易混淆 | 只问这一句 |
|---|---|
| subtype vs instance | A 是 B 的一种类型，还是 B 的一个具体成员？ |
| instance vs exemplifies | A 属于这个类别，还是只是具体展示了某项原则？ |
| component vs structure | A 是语义上的组成部分，还是只在阅读结构里放在 B 下面？ |
| explains vs causes | A 让 B 可理解，还是宣称 A 的发生导致 B？ |
| causes vs contributes | 没有其他因素时，A 是否仍被主张为足以产生 B？ |
| enables vs causes | A 只是让 B 成为可能，还是会使 B 发生？ |
| prevents vs depends | A 主动阻止 B，还是 B 因缺少 A 无法继续？ |
| supports vs foundation | A 支持一条具体主张，还是为一整套理解提供概念基础？ |
| supports vs evidence role | 端点是两个 Knowledge，还是某段来源绑定某条陈述？ |
| contradicts vs contrasts | 两者不能同时成立，还是只是在共同维度上不同？ |
| qualifies vs contradicts | A 让 B 在更窄条件下成立，还是使 B 不成立？ |
| derived vs provenance | B 经过推导得到 A，还是 B 只是来自某个 Source？ |
| similar vs overlap | 两者在某维度像，还是内容本身有可命名的共享部分？ |
| overlap vs identity | 双方是否仍各有重要独立内容；如果没有，应进入 identity resolution。 |
| applies vs implements | 只是适用，还是已经在真实对象中采用？ |
| refines vs revision | 两个 Knowledge identities 都需保留，还是同一 identity 的新文字版本？ |
| evolved vs derived | 是历史变形与传统延续，还是可检查的推导步骤？ |
| evolved vs successor | 前后两者都仍是知识对象，还是新对象取代旧对象的 current standing？ |

---

# 5. Classification & Composition 精确合同

## 5.1 `knowledge.subtype_of`

**陈述模板**：`A 是 B 在「分类维度」下的一类；它以「区分标准」区别于 B 的其他子类。`

**必须满足**：

- A、B 都是 Concept Knowledge；
- 分类维度一致且可命名；
- A 满足 B 的核心定义，并增加区分约束；
- 不产生 cycle；
- 只存 direct relation，祖先链为 derived path。

**不成立**：A 是 B 的实例、例子、组成部分、Topic 子项或文字更详细版本。

**反向阅读**：`B 以 A 作为一个子类型`，不另存 `supertype_of`。

## 5.2 `knowledge.instance_of`

**陈述模板**：`A 是 B 所定义类别的一个具体实例，因为「实例依据」。`

**必须满足**：A 是 Entity、Event、Example 或明确个体；B 是 Concept / type；实例资格可检查。

**不成立**：A 只是帮助理解 B、A 与 B 相似、A 是 B 的一个组成步骤。

**推导限制**：`A instance_of B` 与 `B subtype_of C` 可以形成“经 B 推得 A 属于 C”的 derived classification path，但不新建 maintained `A instance_of C`。

## 5.3 `knowledge.exemplifies`

**陈述模板**：`A 在「具体方面」展示了 B；这个例子不能被外推为「边界」。`

**必须满足**：展示方面、对应 Anchor 与不可外推边界。

**与 instance 的边界**：

- “这家公司是平台型企业” → `instance_of`；
- “这家公司展示了冷启动中的供需失衡” → `exemplifies`。

一个对象可以同时是某类实例并 exemplify 某原则，但必须是两条不同陈述。

## 5.4 `knowledge.defines`

**陈述模板**：`A 在「范围 / 版本」中把 B 定义为「定义内容」。`

**必须满足**：B 是 Concept 或明确术语；A 的 Anchor 包含真正定义；定义作用域可见。

**不成立**：A 只提到、引用、翻译、使用或链接 B。

**反向阅读**：`B 在该范围内由 A 定义`；`defined_by` 是阅读标签。

## 5.5 `knowledge.component_of`

**陈述模板**：`A 是 B 在「组成维度」上的一个组成部分；这里的整体边界是「说明」。`

**必须满足**：composition dimension、whole boundary、端点粒度相容。

**不成立**：

- Block 在 Knowledge Paper 中的排版包含；
- Knowledge Placement 位于某 Topic；
- 文件位于文件夹；
- A 是 B 的一种类型；
- A 只是 B 的先决条件。

**反向阅读**：`B 由 A 作为组成部分`；`has_component` 不另存镜像。

---

# 6. Explanation & Causal Structure 精确合同

## 6.1 `knowledge.explains`

**陈述模板**：`A 通过「解释桥」说明了 B 为什么 / 如何成立。`

必须指出机制、模型、定义或推理怎样连接到被解释对象。共同主题、共同来源、时间相邻或“读 A 有助于理解 B”都不足以成为正式 `explains`。

`explains` 不自动声称 A 导致 B。一个机制知识可以解释某事件，而不是产生该事件。

## 6.2 `knowledge.causes`

**陈述模板**：`在「适用条件」下，A 通过「机制」导致 B；时间顺序为「依据」。`

**必须满足**：

- mechanism；
- temporal ordering；
- applicability；
- alternative / confounding posture；
- claim strength 明确。

如果依据只支持相关、风险提高或局部贡献，必须改用更弱陈述或 `contributes_to`，不能靠 confidence 小数掩盖错误类型。

## 6.3 `knowledge.contributes_to`

**陈述模板**：`A 通过「作用机制」促成 B，但 A 单独不足以保证 B。`

它适合多因素结果、概率性影响与必要但不充分之外的促成作用。若真正含义是“没有 A 就无法发生”，应检查 `depends_on` 或 `enables`；若 A 被主张足以产生 B，应检查 `causes`。

## 6.4 `knowledge.enables`

**陈述模板**：`A 提供「能力 / 条件」，使 B 在「条件」下成为可能，但不保证 B 发生。`

`enables` 关注 possibility frontier。它不等于实际实施，不等于充分因果，也不等于依赖方向的简单反转。

## 6.5 `knowledge.prevents`

**陈述模板**：`在「条件」下，A 通过「阻止机制」使 B 不发生或不能完成。`

旧 `blocks` 逐条迁移：

- 主动抑制、排除或阻断结果 → `prevents`；
- B 缺少先决条件 A → `B depends_on A`；
- 流程界面暂不可点击 → UI state，不建 Relation；
- A 与 B 观点冲突 → `contradicts` 或 `challenges`，不是 `prevents`。

## 6.6 `knowledge.depends_on`

**陈述模板**：`A 在「依赖维度」上依赖 B；若 B 缺失，会产生「后果」。`

canonical direction 始终是 dependent → prerequisite。依赖可以是概念、数据、方法、决策或执行依赖，但必须命名；“经常一起出现”不构成依赖。

依赖链只作为 derived path 展示。A depends_on B、B depends_on C 不自动保存 A depends_on C。

## 6.7 `knowledge.provides_foundation_for`

**陈述模板**：`A 以「概念 / 理论 / 原则 / 证据框架」为 B 提供基础；缺少该基础会影响「核心理解」。`

它适合一种知识为另一知识提供解释坐标或理论底座。它不表达：

- 对某条 Claim 的具体论证 → `supports`；
- 真实采用某方法 → `implements`；
- 可行性条件 → `enables`；
- 来源出处 → provenance；
- 模糊影响 → 不创建或提出 Candidate。

反向阅读 `builds_on` 不另存镜像。

---

# 7. Argument & Inference 精确合同

## 7.1 `knowledge.supports`

**陈述模板**：`A 通过「论证桥」支持 B 在「共同适用条件」下成立。`

**端点约束**：from 是 premise / reason Knowledge；to 是 Claim 或 Decision Knowledge。Method、Concept 可以作为 premise，但必须指出其在论证中的角色。

**不成立**：

- SourceFragment 支持 B → EvidenceBinding；
- A 与 B 共同被本次回答使用 → 两条 ClaimSupport；
- A 为 B 提供理论坐标 → `provides_foundation_for`；
- A 只是引用 B → ReferenceLink；
- A 与 B 方向一致 → 仍需 argument bridge。

## 7.2 `knowledge.contradicts`

**陈述模板**：`A 与 B 回答同一问题 / 维度，并在「重叠适用条件」下不能同时成立，因为「不相容点」。`

它是 symmetric、non-transitive。以下不构成 contradiction：

- 适用于不同地区、时间或人群；
- 结论不同但问题不同；
- 只是方法不同；
- 证据强弱不同；
- 一条只是给另一条加条件。

Applicability 不完整时，系统显示“可能冲突，条件待核对”，只建立 Candidate。

## 7.3 `knowledge.qualifies`

**陈述模板**：`A 将 B 的「方面」收窄 / 附加条件 / 减弱为「效果」。`

必填 `qualification_effect`：`narrows_scope | adds_condition | weakens_strength | adds_exception | bounds_time`。

如果 A 使 B 在共同适用范围内完全不能成立，应使用 `contradicts`；如果 A 只是提供更多细节而保留核心命题，检查 `refines`。

## 7.4 `knowledge.assumes`

**陈述模板**：`A 以命题 B 为「必要 / 默认 / 简化 / 规范」前提。`

canonical direction 是 dependent → assumption。必须把假设写成可评估的 Knowledge，而不是一个隐藏字段。Assumption 被挑战时，系统可以解释哪些下游关系或结论受影响，但不能自动撤回它们。

## 7.5 `knowledge.derived_from`

**陈述模板**：`A 通过「推导 / 计算 / 转换步骤」由 B 得到。`

它要求 inference trace、transformation recipe 或可回读的推理摘要。必须与以下对象分开：

- 从一篇文章摘录 → SourceFragment / provenance；
- 文本重写或纠错 → KnowledgeRevision；
- 复制后变成新 identity → IdentityTransition；
- 历史思想演变 → `evolved_from`；
- 只是引用 → ReferenceLink。

多步推导可以显示 derived path，但不压缩成一条新的 direct Relation。

---

# 8. Comparison & Application 精确合同

## 8.1 `knowledge.contrasts_with`

**陈述模板**：`A 与 B 都讨论「共同维度」，但在「实质差异」上形成对照。`

它是 symmetric，不判断谁正确。若 A 明确削弱 B 的真值，应使用 `contradicts`；若是 Group 整体关系，使用独立的 `group.contrasts_with` 与群级充分性门槛。

## 8.2 `knowledge.similar_to`

**陈述模板**：`A 与 B 在「相似维度」上相似，依据是「说明」；它们仍在「重要差异」上不同。`

若没有重要差异，进入 same / near-duplicate identity resolution；若共享的是可指明的实际语义部分，检查 `partially_overlaps_with`；若只因向量相近，只能生成 Candidate discovery reason。

## 8.3 `knowledge.partially_overlaps_with`

**陈述模板**：`A 与 B 共享「语义部分」，但 A 独有「部分」，B 独有「部分」。`

它是 symmetric、irreflexive、non-transitive。必须同时证明 shared facet 与 bilateral distinct contribution。

旧 `overlaps_with` 不能批量改名：

- 近重复或同一命题 → identity resolution / merge；
- A 是 B 的一种类型 → `subtype_of`；
- A 是 B 的组成部分 → `component_of`；
- 只在某维度相似 → `similar_to`；
- 确有部分共享且双方独立 → `partially_overlaps_with`；
- 说不清 → Reference 或结束旧 Relation。

## 8.4 `knowledge.applies_to`

**陈述模板**：`A 在「适用条件」下适用于目标 B 的「情境 / 问题 / 对象」。`

它表达 potential applicability。目标尚未采用、实施或验证该知识仍可成立。必须保存 target context 与 exclusion conditions。

## 8.5 `knowledge.implements`

**陈述模板**：`A 在「真实情境」中实际落实了 B 的「原则 / 方法 / 规范」，依据是「采用痕迹」。`

canonical direction 是 implementation / realization → implemented knowledge。它适合：

- 某个 Decision 实际采用某原则；
- 某个 Method 具体实现一份规范；
- 某个 Entity / Example 显示真实部署的做法。

只有“可以应用”时用 `applies_to`；只有“展示了一个概念”时用 `exemplifies`；只有“提供步骤”而尚未采用时，不用 `implements`。

---

# 9. Time & Evolution 精确合同

## 9.1 `knowledge.precedes`

**陈述模板**：`A 在「时间依据」上先于 B。`

它只承诺时序。A precedes B 不推出 A causes B、B derived_from A 或 B evolved_from A。多步时间链可作为 derived path；对不确定时间只保存范围与置信姿态。

## 9.2 `knowledge.refines`

**陈述模板**：`A 保留了 B 的「核心命题」，并在「精化维度」上增加精度、条件、边界或解释力。`

两个端点必须是不同但都值得保留的 Knowledge identities。以下情况不建 `refines`：

- 同一 Knowledge 的改字、补证据或版本更新 → Revision；
- A 否定 B → `contradicts`；
- A 只是给 B 附加一个局部条件 → 可能是 `qualifies`；
- B 被 A 取代且不再 current → IdentityTransition / successor standing。

## 9.3 `knowledge.evolved_from`

**陈述模板**：`A 由 B 经「演化线索」发展而来，并在「变化维度」上发生改变；lineage 为 direct / indirect。`

它表达思想、模型、方法或术语传统的 transformation lineage。必须有历史连续性，不得由引用次数、相似度或“受启发”单独推断。

默认 Local Graph 只显示 direct lineage。Indirect lineage 作为可展开 Path，不维护跨代镜像 edge。

---

# 10. 互斥、共存与重复规则

## 10.1 互斥不是“同 pair 只能一条边”

同一对 Knowledge 可以有多条 Relation，只要每条回答不同问题。例如：

- 一个理论 `provides_foundation_for` 一种方法；
- 同时该理论中的某条 Claim `supports` 方法背后的决策；
- 方法的实际项目案例 `implements` 该方法；
- 另一案例 `contrasts_with` 它。

系统要阻止的是同一语义被宽窄两条边重复保存。

## 10.2 强制相邻检查矩阵

| 当前候选 | 必须排除 | 失败后的合法落点 |
|---|---|---|
| `subtype_of` | instance、component、Topic structure | 改型或结构连接 |
| `instance_of` | exemplifies、similar | 改型或 Candidate |
| `component_of` | structure、dependency | Placement / Structure 或 `depends_on` |
| `causes` | contributes、enables、precedes | 更弱类型或 Candidate |
| `prevents` | depends、contradicts、UI state | 改型或不建 Relation |
| `supports` | EvidenceBinding、Answer support、foundation | 对应专属对象或改型 |
| `contradicts` | different Applicability、contrast、qualification | 并列显示、改型或 Candidate |
| `derived_from` | provenance、revision、evolution | 对应专属对象或改型 |
| `similar_to` | duplicate、partial overlap | identity resolution 或改型 |
| `partially_overlaps_with` | identity、subtype、component | identity / 改型 |
| `applies_to` | implements | 保留潜在适用或改为实际采用 |
| `refines` | revision、qualifies、successor | 对应专属对象或改型 |
| `evolved_from` | successor、derived、similar | Transition、改型或 Candidate |

## 10.3 Broad / narrow duplicate

若同一 endpoint pair、Applicability 与 basis 下，两个类型只是同一主张的一宽一窄表达，则只保留更准确的一条：

- `causes` 不再另存 `contributes_to`；
- `implements` 不再为同一采用事实另存 `applies_to`；
- `partially_overlaps_with` 不再另存 `similar_to` 来表达同一 shared facet；
- `supports` 不再另存 `provides_foundation_for` 来表达同一 argument bridge。

如果两条陈述的作用层面不同，则可以共存，但 Inspector 必须解释差异。

## 10.4 Applicability-first 冲突判断

任何 contradiction、cause、support、qualification、application 判断都先读取：

```text
subject / target
population / entity class
location
time interval
conditions
version / jurisdiction
exceptions
```

Applicability 不相交时，系统默认不判 contradiction。部分相交时，只在交集范围内陈述关系，不把局部冲突提升为全局冲突。

---

# 11. 生命周期、迁移与历史

## 11.1 Type revision 不重写已有意义

每条 RelationRevision 固定其 type definition revision。新 registry 可以：

- 提示旧定义过宽；
- 生成只读 ValidationReport；
- 建立 MigrationReview；
- 在 Network 中标注 legacy；
- 让用户新建 successor Relation。

它不能在后台把历史 `overlaps_with` 直接变成 `partially_overlaps_with`。

## 11.2 七类旧数据的迁移

### `related_to`

逐条显示原 statement 与用户用途：

- 只为跳转 → ReferenceLink；
- 只为记录探索路线 → SavedPath manual step；
- 有清楚语义 → 选择精确 type 并建立 successor；
- 仍不清楚 → ambiguous Candidate 或结束。

### `overlaps_with`

必须经过 identity、taxonomy、composition 与 partial-overlap 四项检查；禁止批量字符串替换。

### `blocks`

先问“主动阻止”还是“缺少先决条件”。前者 `prevents`，后者反向建立 `depends_on`。

### `uncertain_about`

建立或复用 Question Knowledge，保存 QuestionTargetReference；旧 edge 在历史中标注 `reclassified_as_question_state`。

### `supersedes`

如果新 Knowledge 成为 current replacement，建立 KnowledgeIdentityTransition；如果两者都 current 且只是更精细，检查 `refines`。

### `retracts`

转成 disposition event。旧 target、actor、rationale、time 必须保留；被撤回对象仍可从 History 回读。

### `reopens`

转成 QuestionLifecycleEvent。重开原因、前一次 Resolution 与新的 `pursuit_state = active`必须可见；`resolution_state`是否改变由新的 QuestionResolutionRevision 决定，不由 reopen 自动降级。

## 11.3 Relation 改类型的三种结果

1. **同一主张，更精确的类型定义**：新 RelationRevision；
2. **主张已经改变**：结束旧 Relation，新建 successor Relation；
3. **原来就不是 Relation**：reclassify 为 Reference、Question state、Transition 或 disposition event，历史保留迁移说明。

## 11.4 Merge、Split 与 endpoint 重定向

Knowledge identity 发生 merge / split 时：

- 系统先生成 impact preview；
- self-edge 不进入 current graph；
- symmetric duplicate 不自动保留两条；
- endpoint kind 失效的 Relation 进入 review；
- 旧 RelationRevision 仍按旧 identities 回读；
- SavedPath 与 AnswerSnapshot 固定历史引用，不被悄悄改成新路径。

---

# 12. Ask、Search、Explore 与 Overview 怎样使用关系类型

## 12.1 Search：关系用于定位，不成为额外答案

Search 可以按关系 family、type、方向和 endpoint 过滤。结果行必须区分：

- 直接 Relation；
- derived path；
- Reference；
- Question target；
- AI Candidate。

搜索命中“支持”时，用户能选择“知识关系”“来源支持”“回答依据”，避免三个对象混成一列。

## 12.2 Ask：Relation 是可引用依据，不是自动真理

Ask 使用 Relation 时必须保留：

- relation_id 与 exact revision；
- type definition revision；
- statement 与 Applicability；
- disposition；
- supporting / challenging Evidence coverage；
- direct 或 derived；
- 使用它支撑了哪条 Answer Claim。

“A supports B”可以支撑回答对 B 的解释，但不能让系统把 A 的全部内容视为 B 的证据，也不能把 relation confidence 变成答案真值概率。

## 12.3 Query Route：只画真实连接类别

若两条 Knowledge 只是共同用于回答 Claim C：

```text
A --ClaimSupport--> C
B --ClaimSupport--> C
```

不得生成 `A supports B`、`A related_to B` 或“共同依据” formal edge。

若 Route 穿过 derived path，必须可展开每一条 direct Relation；若中间一步只是 retrieval jump，视觉和语言都要说明“本次检索跳转”。

## 12.4 Explore：先显示意义，再扩大半径

Local Graph 默认按 family 提供有限 filters：

- 分类与组成；
- 解释与因果；
- 论证与推导；
- 比较与应用；
- 时间与演化。

选择 edge 后 Inspector 显示完整 statement、限定、basis、revision 与相邻类型解释。用户先理解“为什么相连”，再决定 Open、Compare、Follow path 或返回。

## 12.5 Overview：关系只在有阅读价值时进入正文

Overview 不罗列所有 edge。只有满足以下任一条件才进入当前 synthesis：

- 解释核心概念结构；
- 构成阅读主干；
- 解释关键因果或依赖；
- 揭示仍未解决的冲突；
- 是跨领域继续探索的主要出口。

每个 Overview relation sentence 仍引用 exact RelationRevision。Relation 变化时先标记受影响 Anchor，再由 Overview 更新合同决定是否修订正文。

---

# 13. 产品语言与渐进披露

## 13.1 P0 只出现自然句

默认阅读层不显示：

- `knowledge.partially_overlaps_with`；
- `type_definition_revision_id`；
- `symmetry = symmetric`；
- `derived_closure_only`。

它显示：

- “注意力恢复是认知负荷管理的一种具体策略”；
- “这项机制解释了为什么切换任务会留下残余注意”；
- “这两个主张只在同一时间范围内相互冲突”；
- “这套流程可以用于审批设计，但这个案例尚未实际采用”；
- “该项目实际落实了双人确认原则”。

## 13.2 P1 Inspector 给出判断材料

P1 显示：

- 关系家族与清晰类型名；
- 方向和反向阅读；
- 必填限定；
- 形成依据；
- 当前 / challenged / ended / legacy；
- “为什么不是相邻类型”；
- direct / derived；
- change impact。

## 13.3 P2 才暴露本体与迁移细节

P2 可以显示内部 key、definition revision、validation checks、migration review、endpoint kind constraints 与 registry history。

## 13.4 中文标签

| Internal type | P0 / P1 中文 |
|---|---|
| `subtype_of` | 是……的一类 |
| `instance_of` | 是……的实例 |
| `exemplifies` | 具体展示了…… |
| `defines` | 定义了…… |
| `component_of` | 是……的组成部分 |
| `explains` | 解释了…… |
| `causes` | 导致…… |
| `contributes_to` | 促成…… |
| `enables` | 使……成为可能 |
| `prevents` | 阻止…… |
| `depends_on` | 依赖…… |
| `provides_foundation_for` | 为……提供基础 |
| `supports` | 支持该主张 / 决策 |
| `contradicts` | 与……相矛盾 |
| `qualifies` | 限定了…… |
| `assumes` | 以……为前提 |
| `derived_from` | 由……推导而来 |
| `contrasts_with` | 与……形成对照 |
| `similar_to` | 在……方面相似 |
| `partially_overlaps_with` | 与……部分重叠 |
| `applies_to` | 适用于…… |
| `implements` | 实际落实了…… |
| `precedes` | 先于…… |
| `refines` | 更精确地细化了…… |
| `evolved_from` | 由……演化而来 |

---

# 14. Screen 2 + Screen 3 的设计证明要求

这不是原型说明，而是未来视觉方案必须证明的产品状态。

## 14.1 Screen 2：Layered Reading Workspace

至少必须同时证明：

1. 用户从 Group Overview 进入一条 Knowledge Paper；
2. 正文中某个 Claim Anchor 可展开来源与相关关系；
3. `supports` 的三种对象在措辞和位置上不混淆；
4. 用户能从正文打开 Relation Inspector，但阅读位置不丢失；
5. 一条 `applies_to` 明确说“适用但尚未采用”；
6. 一条 `implements` 明确显示真实采用痕迹；
7. Question target 与 Relation 不画成同一种边；
8. 返回正文时保留 Anchor、阅读深度与 relation focus。

## 14.2 Screen 3：Relation Space

至少必须同时证明：

1. 默认图只使用五个 family visual tokens；
2. edge label 是意义主载体，不靠颜色猜；
3. direct edge 与 derived path 可见区分；
4. semantic relation、reference、retrieval jump、evidence connection 不混线；
5. Focus 后显示完整人话 statement 与 required qualifiers；
6. symmetric relation 不出现两条镜像边；
7. 多条不同关系可形成可展开 bundle，但不合并语义；
8. legacy / challenged / ended 通过状态层表达，不伪装成新的 relation type；
9. 列表模式与图模式能访问同样信息和操作；
10. Compare / Open / Return 不把一次探索自动写成新关系。

## 14.3 禁止的视觉捷径

- 二十五种颜色；
- 只靠箭头区分所有方向；
- 把 ReferenceLink 画成浅色 Relation 而不标类别；
- 用线宽代表 truth；
- 把 AI confidence 画成“更可靠”的边；
- hover 才能看到基本意义；
- 同一 `supports` 图标同时表示证据、回答依据与知识关系；
- 把 `supersedes`、`reopens` 继续放进 ordinary relation filter；
- 将 graph density 当作知识质量。

---

# 15. 十八个场景压力测试

## 场景 1：类型与实例

“Transformer 是神经网络架构的一类”和“GPT-4 是 Transformer 的一个实例”必须分别保存 `subtype_of` 与 `instance_of`，不能因都叫“属于”而使用同一边。

## 场景 2：例子不是实例分类

“一次失败上线展示了审批缺失风险”保存 `exemplifies`；它不宣称“失败上线”是“审批缺失风险”的实例类型。

## 场景 3：语义组成与 Topic 结构

“检索是 RAG 的组成部分”可以是 `component_of`；把一篇检索笔记放到“RAG / 检索”Topic 只产生 Placement。

## 场景 4：解释不等于因果

“认知负荷理论解释切换成本”可保存 `explains`；除非有因果陈述与机制证据，否则不保存 `causes`。

## 场景 5：多因素结果

“睡眠不足促成判断失误”在现有理解只支持概率性贡献时使用 `contributes_to`，不夸大为 `causes`。

## 场景 6：使可能不等于导致

“向量索引使语义检索成为可能”使用 `enables`；它不宣称部署索引就必然产生高质量答案。

## 场景 7：阻止与依赖

“权限策略阻止未授权导出”使用 `prevents`；“导出流程依赖审批结果”使用 `depends_on`。

## 场景 8：理论基础与论证支持

“认知负荷理论为界面复杂度原则提供基础”使用 `provides_foundation_for`；具体实验结论支持某一条主张时使用 `supports`。

## 场景 9：来源支持不是知识支持

一段论文片段支持 Claim B，只建立 EvidenceBinding；如果论文中的独立 premise Knowledge A 通过论证桥支持 B，才建立 `knowledge.supports`。

## 场景 10：伪冲突

“住房补助取决于一般住房、家庭与资源条件”和“2026-07-01 后特定非欧盟学生增加奖学金条件”结论粒度不同；若时间、人群与身份 Applicability 可以同时成立，保存 `qualifies`，不保存 `contradicts`。职业活动例外再以另一条 `qualifies` 收窄新条件；Source Evidence 与 Question basis 仍不是 semantic edge。

## 场景 11：限定而非反驳

“该建议只适用于低风险操作”用 `qualifies` 限定“应自动执行”；不把它画成完全反驳自动执行。

## 场景 12：推导与出处

一条计算结论由数据表和公式推导，Knowledge 对 Knowledge 保存 `derived_from`；数据表文件本身仍通过 Source provenance 追溯。

## 场景 13：相似、重叠与重复

两条方法在“先探索后收敛”上相似但步骤不同，用 `similar_to`；共享同一子过程且各有独立部分，用 `partially_overlaps_with`；实为同一方法的改写则进入 merge review。

## 场景 14：适用与落实

“双人确认适用于高风险自动化”保存 `applies_to`；某审批流程已经使用双人确认并有配置记录，保存 `implements`。

## 场景 15：先后不是因果

“政策发布先于租金变化”只保存 `precedes`；没有机制和适用条件时不自动生成 `causes`。

## 场景 16：精化与文字版本

新的独立模型保留旧模型核心并增加边界条件，可以 `refines`；同一 Knowledge Paper 修改措辞与补来源只形成 Revision。

## 场景 17：演化与取代

一种方法由旧方法长期演变且两者仍值得比较，使用 `evolved_from`；新 identity 成为旧 identity 的 current replacement，使用 KnowledgeIdentityTransition。

## 场景 18：回答共同依据不制造边

Ask 同时使用 A、B 回答 C，只建立 A→C、B→C 的 ClaimSupport。用户明确审查并采用前，不创建 A 与 B 的任何 formal Relation。

---

# 16. 三十二项 Given / When / Then 验收合同

## 验收 1：连接类别分离

**Given** 一个 SourceFragment、两个 Knowledge 与一个 Answer Claim  
**When** 三者都出现“支持”作用  
**Then** 系统分别创建 EvidenceBinding、KnowledgeRelation、ClaimSupport，且三者拥有不同对象标签与 Inspector。

## 验收 2：无含糊兜底

**Given** 用户只说“A 与 B 有关”  
**When** 无法补齐关系意义  
**Then** 系统允许 Reference 或 ambiguous Candidate，不创建 `related_to` formal Relation。

## 验收 3：类型版本固定

**Given** Relation R 使用 registry revision T1  
**When** T2 修改该类型定义  
**Then** R 的历史 Revision 仍按 T1 回读，系统只生成 validation / migration 提示。

## 验收 4：跨层命名空间

**Given** Knowledge 与 Group 都存在 `provides_foundation_for`  
**When** 用户检查其定义  
**Then** 两者显示不同 endpoints、充分性与 TypeDefinitionRevision，不共享一条类型记录。

## 验收 5：subtype 端点

**Given** A 不是 Concept Knowledge  
**When** 用户选择 `subtype_of`  
**Then** 系统阻止直接保存并建议 instance、example、component 或结构连接检查。

## 验收 6：subtype cycle

**Given** A 已通过 direct subtype path 指向 B  
**When** 用户尝试建立 B subtype_of A  
**Then** 系统阻止 cycle，并显示造成循环的 direct path。

## 验收 7：instance 不传递保存

**Given** x instance_of A 且 A subtype_of B  
**When** 用户展开分类  
**Then** 系统可显示 derived path“x 也属于 B”，但不自动创建 x instance_of B。

## 验收 8：example 边界

**Given** 一个案例展示某原则  
**When** 用户保存 `exemplifies`  
**Then** 必须填写展示方面与不可外推边界。

## 验收 9：definition 非提及

**Given** A 只在正文中提到术语 B  
**When** AI 发现两者共现  
**Then** 只能建议 Reference，不生成 `defines` Candidate。

## 验收 10：component 非结构

**Given** A 只是被放在 B 的 Topic 下  
**When** 系统评估 `component_of`  
**Then** 评估失败，保留 Placement，不制造语义组成。

## 验收 11：解释非因果

**Given** A 能解释 B 但没有因果承诺  
**When** 创建 Relation  
**Then** 可用 `explains`，不得因语言中的“为什么”自动升级为 `causes`。

## 验收 12：因果强度

**Given** 依据只说明 A 是多个促成因素之一  
**When** 用户选择 `causes`  
**Then** validation 指出强度过高，并建议 `contributes_to` 或保留 Candidate。

## 验收 13：enable 非发生

**Given** A 只让 B 成为可能  
**When** Relation 出现在 Ask  
**Then** 回答不得改写成“A 导致了 B”或“B 已经发生”。

## 验收 14：blocks 迁移

**Given** 一条旧 `blocks` Relation  
**When** 进入 MigrationReview  
**Then** 用户必须在 `prevents`、反向 `depends_on`、其他对象或保留 legacy 中选择，系统不批量替换。

## 验收 15：依赖方向

**Given** A 需要 B 才能成立  
**When** 从任一端创建  
**Then** canonical 保存 A depends_on B，B 端只显示 inverse reading，不创建镜像 Relation。

## 验收 16：foundation 与 support

**Given** A 为 B 提供理论框架，同时 A 中某前提支持 B 的一条 Claim  
**When** 用户检查两条连接  
**Then** 系统允许两条不同 Relation，并解释 foundation 与 argument bridge 的差异。

## 验收 17：Knowledge support 与 Evidence support

**Given** SourceFragment F 支持 Knowledge Claim B  
**When** 用户打开 Local Graph  
**Then** F 不作为 `knowledge.supports` endpoint；Evidence 在 B 或相关 Relation 的依据层展开。

## 验收 18：contradiction applicability

**Given** 两条 Claim 结论相反但适用时间不重叠  
**When** AI 评估冲突  
**Then** 不创建 `contradicts`，并解释时间条件不同。

## 验收 19：qualification effect

**Given** A 只收窄 B 的范围  
**When** 保存 `qualifies`  
**Then** 必须记录 affected aspect 与 effect，B 不被自动标为 false。

## 验收 20：assumption 可追踪

**Given** A assumes B 且 B 受到挑战  
**When** 用户查看影响  
**Then** 系统显示 A 可能受影响的路径，但不自动撤回 A。

## 验收 21：derivation 与 provenance

**Given** A 由 B 的公式推导，B 又来自 Source S  
**When** 查看溯源  
**Then** A derived_from B 与 B→S provenance 分两层呈现，可分别核验。

## 验收 22：similarity 发现限制

**Given** embedding 认为 A 与 B 高度相似  
**When** AI 提示关系  
**Then** 只能生成带 discovery reason 的 Candidate；未补相似维度与重要差异前不能采用。

## 验收 23：partial overlap 双侧独立

**Given** A 与 B 共享一段语义  
**When** 任一方没有重要独立内容  
**Then** 系统转入 identity / containment review，不保存 `partially_overlaps_with`。

## 验收 24：applies 与 implements

**Given** 原则 P 适合项目 X，但 X 尚未采用  
**When** 用户保存关系  
**Then** 只允许 P applies_to X；存在真实采用痕迹后才可另建 X implements P。

## 验收 25：precedes 非 cause

**Given** A 的时间早于 B  
**When** 图谱展开路径  
**Then** 只显示时序，系统不因相邻或先后自动生成 cause Candidate。

## 验收 26：refine 与 revision

**Given** 用户只修改同一 Knowledge 的文字和来源  
**When** 保存  
**Then** 形成 KnowledgeRevision，不创建 self 或 cross-identity `refines`。

## 验收 27：successor 非 relation

**Given** 新 Knowledge 取代旧 Knowledge 成为 current  
**When** 用户确认替换  
**Then** 创建 KnowledgeIdentityTransition，并从普通 Relation filter 中排除 `supersedes`。

## 验收 28：Question state 非 relation

**Given** 已回答问题因新证据重开  
**When** 用户执行“重新打开问题”  
**Then** 创建 QuestionLifecycleEvent，目标通过 QuestionTargetReference 保留，不创建 `reopens` edge。

## 验收 29：direct 与 derived

**Given** A subtype_of B、B subtype_of C  
**When** 用户查看 A→C  
**Then** UI 标注 derived path 并可展开两条 direct Relations，不显示为第三条 maintained edge。

## 验收 30：图与列表等价

**Given** 用户无法或不愿使用 graph  
**When** 切换到 Relation List  
**Then** 可访问相同 statement、方向、限定、basis、history、open 与 compare 操作。

## 验收 31：共同回答不造边

**Given** Ask 同时使用 A 与 B 支撑 Claim C  
**When** 回答完成或被保存  
**Then** 只固化 ClaimSupport；除非用户另行审查采用，不创建 A↔B Relation。

## 验收 32：类型迁移可逆且可解释

**Given** 旧 Relation 被建议迁移  
**When** 用户接受新类型  
**Then** 系统保留旧 Revision、决策理由与影响预览，并可通过新的 successor decision 恢复或改判，而不是覆盖历史。

---

# 17. 指标与反指标

## 17.1 产品质量指标

- **Typed comprehension**：用户能否用一句话复述选中关系；
- **Adjacent-type correction rate**：validation 发现宽窄误用后被正确修订的比例；
- **Unsupported relation rate**：缺少 required qualifiers 或 basis 的 current Relations 比例；
- **Cross-object confusion rate**：用户把 Evidence、Reference、Question state 误认成 Relation 的任务比例；
- **Route fidelity**：Ask Route 中每条正式边能否解析到 exact RelationRevision；
- **Migration completeness**：deprecated types 的逐条处置覆盖，而不是字符串替换进度；
- **Return continuity**：从 Inspector / Graph 返回阅读 Anchor 成功率；
- **Negative honesty**：没有精确关系时，系统是否能稳定呈现“当前没有正式关系”。

## 17.2 禁止优化的数字

- Relations 总数；
- 每个 Knowledge 的平均边数；
- Network density；
- AI Candidate 采用率；
- 图上颜色数量；
- 自动补全关系数量；
- 因为“看起来更丰富”而增加的路径长度。

知识库的质量来自可理解、可核验、可回返，而不是连线密度。

---

# 18. 研究依据、产品判断与待验证假设

## 18.1 已核验的外部结构事实

- W3C SKOS 把 hierarchical relations、associative `related` 与 transitive closure 分开，并明确 associative relation 与 broader transitive hierarchy 的边界；这支持本产品把 hierarchy、association 和 derived path 分开。
- W3C OWL 2 将 classes、properties、individuals、axioms 与 annotations 分开，并为 property direction、inverse、domain、range、symmetry、transitivity 与 disjointness提供独立结构；这支持每个 relation type 明确端点与逻辑特征，而不是只保存一个 label。
- W3C PROV-O 将 derivation、revision、primary source、quotation、invalidation 与 qualified relation 分开；这支持本产品把来源追溯、知识推导、版本修订与撤回动作拆成不同对象。
- W3C Web Annotation Data Model 将 Body、Target、Motivation 与具体 segment / state 分开；这支持 Anchor、Reference、Evidence Annotation 不冒充 Knowledge Relation。
- Wikibase conceptual data model 区分 Statement、Property、Value、qualifier-like additional snaks、rank 与 ReferenceRecord，并强调表达能力与复杂度 / 可用性的平衡；这支持“少量精确类型 + 必要限定 + 独立来源”的产品取舍。
- CiTO 展示了 citation intent 可以细分为 supports、uses method、disagrees、qualifies 等，同时 citation metadata 与作品本体分离；这支持来源引用作用与 Knowledge semantic relation 分开，而不是把引用类型直接复制成知识本体。

## 18.2 本文做出的产品判断

- 不复制完整 OWL、Wikibase 或 CiTO 词表；个人知识库需要意图优先、可读、有限且可治理的 registry。
- `implements` 是实际采用语义的必要补位；只有 `applies_to` 会让“适用”和“已采用”混淆。
- `uncertain_about`、`supersedes`、`retracts`、`reopens` 应从 ordinary relation registry 移出。
- Knowledge-level overlap 也应收紧为 `partially_overlaps_with`，但必须逐条迁移，不能沿用群级结论做批量改名。
- 二十五种类型是终局本体边界，不是默认 UI 菜单；默认体验只暴露五个 family 与少量候选句。

## 18.3 仍需以后用真实任务验证的假设

- 五个 family 是否足以让非本体专家完成大多数关系创建；
- `supports` 与 `provides_foundation_for` 的中文辨别句是否自然；
- `similar_to` 与 `partially_overlaps_with` 是否需要在 P0 合并成一次“比较”入口；
- `implements` 的方向“实现对象 → 被实现知识”是否比反向更符合用户阅读；
- 二十五种类型在长期知识库中是否有极低频项应降到 advanced，而不是删除；
- Relation List 是否比 graph 更常成为可信核验入口。

这些是待研究假设，不反向改写本文已经冻结的对象边界。

## 18.4 参考资料

- W3C, *SKOS Simple Knowledge Organization System Reference*: https://www.w3.org/TR/skos-reference/
- W3C, *OWL 2 Web Ontology Language Structural Specification and Functional-Style Syntax*: https://www.w3.org/TR/owl2-syntax/
- W3C, *PROV-O: The PROV Ontology*: https://www.w3.org/TR/prov-o/
- W3C, *Web Annotation Data Model*: https://www.w3.org/TR/annotation-model/
- Wikimedia, *Wikibase DataModel*: https://www.mediawiki.org/wiki/Wikibase/DataModel
- SPAR Ontologies, *CiTO — Citation Typing Ontology*: https://sparontologies.github.io/cito/current/cito.html

---

# 19. 与现有文档的覆盖关系

本文件发布后：

1. `AI-native-个人知识库-终局产品设计文档-v4.0.md` 的 Knowledge-level relation family 与类型清单，以本文为精确解释；
2. `AI-native-个人知识库-知识深度与关系探索合同-v1.0.md` §7 中旧 28-type list 被本文替代；
3. `AI-native-个人知识库-关系陈述生命周期与网络可信性合同-v1.0.md` 继续拥有生命周期，但 `supersedes / retracts / reopens / uncertain_about` 不再是 ordinary Knowledge Relation types；
4. `AI-native-个人知识库-AI查询与知识回答合同-v1.0.md` 中 Answer Claim support 继续存在，但不得与 `knowledge.supports` 共用对象；
5. Group Relation registry 不被本文替代；跨层同名类型必须保留 namespace 与独立 definition revision；
6. 任何未来原型、Ardot Frame、技术方案或验收 rubric 必须通过本文三十二项验收，不得把已降级类型重新画回主图。

发生冲突时，对 Knowledge-level relation type、跨对象语义与旧类型迁移，以本文为准；对 Relation lifecycle 仍以生命周期合同为准；对 Group endpoints 以群级 registry 为准。

---

# 20. 结论

这个产品不需要一个“什么都能连”的知识图谱。它需要的是：用户在 Overview 与深层正文中遇到一条重要联系时，可以知道它究竟是什么、为什么成立、适用于哪里、来自谁、当前是否仍有效，并且能沿它继续探索后准确返回。

二十五种 Knowledge Relation 并不是二十五种视觉装饰，而是五类可理解问题的精确答案。更重要的是，本文明确了哪些东西永远不该画成普通关系：来源支持、回答依据、引用、结构、检索跳转、版本继承、撤回动作与问题重开。

只有把这些边界守住，Screen 3 的 Relation Space 才不是一张“聪明的网”；它才会成为 Screen 2 的 Layered Reading 真正可信的横向延伸。
