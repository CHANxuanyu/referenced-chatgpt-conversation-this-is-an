# AI-native 个人知识库

## 群级关系类型注册表与语义互斥合同 v1.0

> **权威状态（2026-08-10）：EXPERIMENTAL_APPENDIX。11-type registry 不冻结默认 UI 或 schema；先通过真实 Group pair 验证用户是否能稳定辨认。**  
> 日期：2026-08-10  
> 文档性质：终局产品本体、关系语义、类型选择、迁移、语言与设计证明合同；不是数据库 enum、OWL 实现、图布局算法、MVP 范围或原型授权  
> Canonical 产品定义：`AI-native-个人知识库-终局产品设计文档-v4.0.md`  
> 第二真实夹具证明：`AI-native-个人知识库-第二真实端到端夹具-概念学习、多语境复用与群关系-v1.0.md`用同一 Group pair 验证 `provides_foundation_for + provides_method_for`可以作为两个独立 Current statements 共存；前者回答概念 / 证据依赖，后者要求目标群 current actual use。3 条 Shared Knowledge observations 不成为第三种 Relation，冗余 `complements`不因共同目标自动成立  
> 上游资格合同：`AI-native-个人知识库-群级关系聚合门槛与支撑充分性合同-v1.0.md`；本文决定“候选究竟是哪一种关系”，上游继续决定“系统有没有资格提出”  
> 上游生命周期：`AI-native-个人知识库-关系陈述生命周期与网络可信性合同-v1.0.md`；Relation、Revision、Candidate、Evidence、Challenge、Disposition、Lifecycle 与 History 继续以该合同为准  
> 下游 Pair Comparison：`AI-native-个人知识库-知识群对照与关系检查器合同-v1.0.md`；它决定同一 pair 怎样读取 Current / Shared / Paths / Suggested / History、保持 snapshot 与安全写回  
> 相邻合同：`AI-native-个人知识库-知识群边界与跨群架构合同-v1.0.md`、`AI-native-个人知识库-知识深度与关系探索合同-v1.0.md`、`AI-native-个人知识库-AI查询与知识回答合同-v1.0.md`、`AI-native-个人知识库-Overview形成编辑与更新合同-v1.0.md`  
> 用户意图：产品仍然是知识库；纵向由 Overview → Detail 提供理解主干，横向由少量有明确意义的群级关系提供可信探索  
> 当前边界：只定义完整产品，不修改 Ardot，不绘制新 Frame，不制作可点击原型

---

# 0. 执行结论

## 0.1 这轮为什么不能只补十个定义

上一轮已经冻结：Group Relation 不是底层线条的自动聚合，系统必须先通过九道资格门。但如果 relation type 本身含糊，严格聚合仍会产生含糊知识：

- `overlaps_with` 同时可能被理解为部分交集、包含关系或只是共享对象；
- `provides_foundation_for`、`provides_method_for`、`applies_to` 与 `influences` 很容易互相替代；
- `contrasts_with` 不能表达一方真正削弱另一方；
- 两个范围相互补足与相互重叠并不是一回事；
- `evolved_from` 容易把思想影响伪装成 identity lineage；
- `shares_core_knowledge_with` 完全由当前 Placements 与策展角色决定，却被误建模成需要用户长期维护的 Relation；
- 类型名称、方向、inverse reading、transitivity 与视觉箭头还没有形成同一套合同。

因此本轮不保留“现有十种类型默认正确”的前提，而重新冻结：

> **一条群级关系类型，必须让用户知道两个知识范围在什么层面相连、谁对谁做了什么、什么情况下成立、相邻类型为什么不准确，以及它是否是一条被拥有的陈述还是当前结构的派生观察。**

## 0.2 本轮最重要的三项修订

### 修订一：`overlaps_with` 收紧为 `partially_overlaps_with`

本产品需要表达的是：

> 两个独立 Group 的 Boundary 在明确语义范围内部分相交，但任何一方都不完全包含另一方。

因此 Group-level canonical type 改为 `partially_overlaps_with`。旧 `overlaps_with` 成为 deprecated alias。本合同本身不自动改写 Knowledge-level 数据；随后发布的`AI-native-个人知识库-知识关系类型注册表与跨层语义合同-v1.0.md`已独立收紧 Knowledge overlap，并要求逐条迁移，两个层级仍不共享 TypeDefinition。

### 修订二：`shares_core_knowledge_with` 移出正式 Relation registry

“共享核心知识”是由以下当前事实计算出的结构观察：

- 同一 canonical Knowledge identity；
- 两侧 current Placements；
- 两侧 core / representative curation roles；
- 当前 Boundary Revisions。

这些输入变化时，观察理应实时变化。它不需要用户采用，也不应拥有独立 assertion disposition。因此它改为：

```text
GroupConnectionObservation.kind = shared_core_knowledge
```

它进入可选 Shared Knowledge Lens、Group pair comparison 与 Ask explanation；不进入 Current / Suggested / History Relation layers，不增加 Relation count，也不影响 resting layout。它可以支撑 `partially_overlaps_with`、`provides_foundation_for` 等 Candidate，但不能替代它们。

### 修订三：新增 `complements` 与 `challenges`

- `complements` 表达两个知识范围围绕同一目标提供不同且非冗余的贡献；它不是 overlap，也不是“没有冲突”；
- `challenges` 表达 A 在重叠 Applicability 内削弱、质疑或暴露 B 的假设、方法或结论问题；它有方向，不等于 symmetric contrast，也不自动撤回 B。

## 0.3 Canonical 关系组合

正式 Group Relation registry 冻结为十一种：

1. `scope_within`；
2. `partially_overlaps_with`；
3. `provides_foundation_for`；
4. `provides_method_for`；
5. `applies_to`；
6. `complements`；
7. `contrasts_with`；
8. `challenges`；
9. `constrains`；
10. `influences`；
11. `evolved_from`。

其中 `influences` 是 advanced fallback，只有无法使用更精确的 foundation / method / applies / constrains / challenges 且影响机制明确时才可保存。`related_to` 永远不是正式类型。

## 0.4 本文件冻结的四十八项决定

1. **Group Relation type 是 statement meaning 的一部分。** 改类型通常创建新 RelationRevision；若已经变成不同主张则新建 Relation。
2. **类型不是颜色分类。** 每个类型必须声明 direction、inverse、symmetry、qualifiers、integrity rules 与降级落点。
3. **正式 registry 有十一种 Group-level types。** Knowledge-level registry 不被本合同整体替换。
4. **`related_to` 不进入正式 registry。** 无法定型时保留 exit、Reference、Saved Path 或 ambiguous Candidate。
5. **Group-level `overlaps_with` deprecated。** 新 canonical type 是 `partially_overlaps_with`。
6. **Partial overlap 与 scope containment 在同一 Boundary / Applicability 下互斥。**
7. **`shares_core_knowledge_with` 不再是 formal Group Relation type。**
8. **共享核心知识是 derived GroupConnectionObservation。** 它不需要采用，不拥有 Relation lifecycle。
9. **Derived observation 不进入 Current / Suggested / History Relation layers。**
10. **Shared Knowledge Lens 不影响 resting Network layout。**
11. **`complements` 新增为 symmetric formal type。**
12. **`challenges` 新增为 directed formal type。**
13. **`scope_within` 只表达 Boundary containment。** 它不产生 Subgroup、membership、ownership 或级联删除。
14. **`scope_within` canonical direction 是 narrower → broader。** `contains_scope` 只是 inverse reading。
15. **`scope_within` 只保存 direct assertions。** Closure 是 derived path，不进入 Current direct edge count。
16. **`partially_overlaps_with` 是 symmetric、irreflexive、non-transitive。**
17. **`provides_foundation_for` 表达概念、理论、原则或证据框架的基础作用。**
18. **`provides_method_for` 表达可重复方法在目标范围内被实际采用。**
19. **`applies_to` 表达某项模型、原则、规则或方法适用于明确目标语境。** 它不等于 B 实际采用。
20. **`complements` 需要共同目标和非冗余贡献。** 共享标签或无冲突不足以成立。
21. **`contrasts_with` 需要共同问题 / 比较维度与 material difference。** 它不判断谁更正确。
22. **`challenges` 需要 overlapping Applicability 与明确被削弱对象。** 它有方向。
23. **`challenges` 不自动改变被挑战 Relation / Group 的 disposition。** 它只形成 Challenge signal 或正式群级陈述。
24. **`constrains` 表达 A 减少 B 的可行选择空间。** 它不是一般影响或认识冲突。
25. **`influences` 必须保存 mechanism 与 affected dimension。**
26. **存在更窄类型时不使用 `influences`。** 同一机制不能同时保存 broad influence 与其 narrow duplicate。
27. **系统生成的 `influences` Candidate 默认只按需出现。** 不进入 ambient Suggested。
28. **`evolved_from` 只表达 identity、tradition 或 scope lineage。** 相似、引用与基础作用不构成演化。
29. **`evolved_from` 必须声明 direct / indirect lineage distance。**
30. **只有 direct lineage 进入默认 Current 邻接。** Indirect lineage 作为 Path / History 展开。
31. **所有类型默认 non-transitive。** 只有 registry 明确声明的 closure 产生 derived path。
32. **任何 derived closure 都不自动物化 maintained Relation。**
33. **Directed type 只保存一个 canonical assertion。** inverse label 不创建镜像边。
34. **Symmetric type 按 endpoint identities 规范化。** 交换端点不创建第二条 Relation。
35. **所有正式 Group Relations 禁止 self-edge。** Merge 产生的 self-edge 只保留历史。
36. **同 pair 可以有多条类型。** 但每条必须表达不同主张，不能只是宽窄重复。
37. **类型选择从用户意图开始，不从十一项 enum 开始。**
38. **用户必须能看到“为什么不是相邻类型”。** 复杂边界进入 P1，而非默认术语墙。
39. **系统不确定类型时不得投票选最常见谓词。**
40. **Type validation 只生成 report。** 不直接改 Relation、Candidate 或 Boundary。
41. **RelationRevision 固定 registry revision。** Registry 更新不静默重解释历史。
42. **Type deprecation 先生成 Migration Review。** 不批量改边。
43. **旧 `overlaps_with` 需要逐条确认是否为 partial overlap、scope containment、shared-core observation 或无正式关系。**
44. **旧 `shares_core_knowledge_with` 需要逐条迁移预览。** 用户拥有的历史陈述不被静默删除。
45. **Network 只使用 family-level visual grammar。** 十一种类型不能变成十一种只靠颜色区分的线。
46. **Edge label / List statement 是主要意义载体。** Arrow、颜色、线型与动效只辅助。
47. **Graph、List、Ask、Overview 与 Inspector 读取同一 TypeDefinitionRevision。**
48. **当前继续停留在产品定义阶段。** 本文不解除“不马上做原型”的约束。

---


# 1. 为什么 Group-level registry 必须独立

## 1.1 Knowledge Relation 与 Group Relation 不是同一粒度

Knowledge Relation 可以精确表达：

- 某条 Claim supports 另一条 Claim；
- 某个 Method applies to 某个 Task；
- 某个 Event precedes 另一 Event；
- 某条 Rule constrains 某个 Decision。

Group Relation 则把两个有 Boundary 的知识范围作为端点。它必须防止把一条成员事实外推成整体，也必须提供对两侧核心理解真正有用的陈述。因此 Group registry 可以复用部分词汇，却需要更严格的 required qualifiers、Boundary coverage 和 cross-level semantics。

## 1.2 Registry 的任务不是列词表

Registry 必须同时回答：

1. 这是什么关系；
2. 它不是什么关系；
3. canonical direction 是什么；
4. 从另一端怎么读；
5. 是否 symmetric / transitive；
6. 必须补哪些限定；
7. 什么 basis 可以直接建立或聚合；
8. 哪些相邻类型容易混淆；
9. 不满足时保留成什么；
10. Network、Ask、Overview 与 History 怎样读取。

## 1.3 类型家族只服务选择与表达

十一种类型分为五个 family：

| Family | 回答的问题 | Types |
|---|---|---|
| Scope | 两个知识范围怎样相交 | `scope_within`、`partially_overlaps_with` |
| Contribution | A 为 B 提供什么 | `provides_foundation_for`、`provides_method_for`、`applies_to` |
| Comparison | 两者怎样共同、不同或互相质疑 | `complements`、`contrasts_with`、`challenges` |
| Directional Effect | A 怎样限制或影响 B | `constrains`、`influences` |
| Lineage | 一个范围如何由另一个演变 | `evolved_from` |

Family 不是可保存的模糊 type，也不产生 family edge。它只用于创建流程、过滤、Bundle 分组与视觉语法。

---


# 2. Canonical 对象模型

## 2.1 GroupRelationTypeDefinitionRevision

```text
GroupRelationTypeDefinitionRevision
  type_definition_revision_id
  type_id
  registry_revision_ref

  identity
    canonical_key
    status: active | advanced | deprecated | retired
    family
    endpoint_kinds: [Group, Group]

  meaning
    definition
    canonical_statement_template
    inverse_statement_template?
    from_role
    to_role
    symmetry: directed | symmetric
    directness_policy
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
    integrity_constraints[]
    adjacent_type_checks[]
    duplicate_rules[]
    incompatibility_rules[]

  formation
    direct_policy
    aggregation_policy_ref
    default_candidate_visibility
    insufficient_outcomes[]

  presentation
    zh_label
    zh_inverse_label?
    compact_verb_phrase
    family_visual_token
    direction_cue
    list_sentence_template

  compatibility
    deprecated_aliases[]
    migration_policy_ref?
    replacement_type_refs[]

  governance
    created_at
    supersedes_definition_revision_ref?
    rationale
```

TypeDefinitionRevision 是可版本化产品语义，不是随代码发布覆盖的 enum 注释。

## 2.2 RelationRevision 绑定 type revision

```text
RelationRevision
  relation_revision_id
  relation_type_ref
  type_definition_revision_ref
  from_group_ref
  to_group_ref
  statement
  inverse_reading
  applicability
  type_specific_qualifiers{}
  why_it_matters
```

旧 Relation 永远可以按当时的 TypeDefinitionRevision 回读。Registry 新版本可以提出 Migration Review，但不能改变历史 statement 的意义。

## 2.3 TypeValidationReport

```text
TypeValidationReport
  validation_report_id
  target_ref: RelationRevision | RelationCandidate
  type_definition_revision_ref
  checked_at
  checks[]
    check_id
    result: pass | fail | indeterminate | not_applicable
    explanation
    affected_fields[]
    adjacent_type_ref?
  overall_result
  suggested_actions[]
```

Validation Report 不写入或改写 Relation。用户主动采用 Candidate、修改 Revision 或接受 Migration 时才产生 Change Set。

## 2.4 GroupConnectionObservation

```text
GroupConnectionObservation
  observation_id
  kind:
    shared_core_knowledge
  group_pair_ref
  boundary_revision_refs[]
  evaluated_at
  evaluation_coverage
  basis
    shared_knowledge_refs[]
    placement_refs[]
    curation_role_refs[]
  current_result
    shared_core_count
    representative_count
    named_subscopes[]
  relation_candidate_refs[]
  expires_when[]
```

Observation 是可重建 projection。它没有 assertion disposition、adoption、RelationRevision 或 Relation History。为了重建历史 Ask，可把当时 Observation snapshot 固定进 AnswerSnapshot，但不因此变成 Relation。

## 2.5 GroupRelationTypeMigrationReview

```text
GroupRelationTypeMigrationReview
  migration_review_id
  source_relation_revision_ref
  source_type_definition_revision_ref
  target_registry_revision_ref
  reason
  proposals[]
    keep_legacy
    revise_to_type
    replace_with_relation
    reclassify_as_observation
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

Migration Review 是高影响 Decision，不是后台 schema migration。

---


# 3. Registry 总表

| Type | Family | 方向 | 默认创建入口 | 系统聚合 | 必需限定 | 默认呈现 |
|---|---|---|---|---|---|---|
| `scope_within` | Scope | directed | contextual | forbidden | Boundary containment | Scope Lens / statement |
| `partially_overlaps_with` | Scope | symmetric | contextual | strict | overlap dimensions + boundary differences | Current / Suggested |
| `provides_foundation_for` | Contribution | directed | primary | strict | foundation kind + target dependency | Current / Suggested |
| `provides_method_for` | Contribution | directed | primary | strict | method + actual use | Current / Suggested |
| `applies_to` | Contribution | directed | primary | strict | applicable content + target context + conditions | Current / Suggested |
| `complements` | Comparison | symmetric | primary | strict | shared goal + non-redundant contributions | Current / Suggested |
| `contrasts_with` | Comparison | symmetric | primary | strict | comparison dimension + material difference | Current / Suggested |
| `challenges` | Comparison | directed | contextual | strict | challenged object + challenge mechanism | Current / Suggested |
| `constrains` | Directional Effect | directed | contextual | strict | constraint + reduced option space | Current / Suggested |
| `influences` | Directional Effect | directed | advanced | on-demand only | mechanism + affected dimension | Current / on-demand Suggested |
| `evolved_from` | Lineage | directed | contextual | forbidden | lineage basis + directness + time | Current direct / History path |

## 3.1 全局不变量

- `self_policy = forbidden`；
- inverse reading 不创建第二条 Relation；
- symmetric relation endpoint pair 规范化；
- 默认 non-transitive；
- 任何 closure 只形成 derived path；
- Candidate 不确定类型时保持 `ambiguous_type`，不写 `related_to`；
- 同一 pair 同时存在多条 Relations 时，Bundle 不合并语义；
- 同一 statement 的 broad + narrow type duplicate 不并存；
- `Applicability` 不相交的两条关系不因 label 相同自动判冲突；
- type validation 与 Relation truth 分开。

## 3.2 Quick create 不展示十一项列表

Quick create 先让用户回答一个自然问题：

```text
它们的范围怎样相交？
A 为 B 提供了什么？
它们怎样共同解释或解决一个问题？
它们在哪里不同，或谁在质疑谁？
A 怎样限制或影响 B？
一个是否由另一个演变而来？
```

第二步才显示 2–4 个相关类型，并用完整句子即时回读。Advanced `influences` 默认不出现，只有用户选择“其他明确影响”或 AI 无法用窄类型表达时进入。

---


# 4. 类型选择树

## 4.1 第一问：这是 lineage、Boundary，还是语义作用

1. 两个 Groups 是否表达同一 scope / tradition / project identity 的前后演变？  
   - 是 → `evolved_from`；
   - 否 → 继续。
2. 是否可以只通过两侧 Boundary Revisions 判断？  
   - 一侧完整落在另一侧 → `scope_within`；
   - 双方部分相交、互不包含 → `partially_overlaps_with`；
   - 只是共享 Knowledge → Shared Knowledge Observation；
   - 否 → 继续。
3. 是否在表达 A 对 B 的贡献？  
   - 理论 / 概念 / 原则基础 → `provides_foundation_for`；
   - 可重复方法且 B 实际使用 → `provides_method_for`；
   - A 的内容适合 B 的明确语境，但未必实际采用 → `applies_to`；
   - 否 → 继续。
4. 是否围绕共同问题比较两侧？  
   - 不同且非冗余贡献共同完成目标 → `complements`；
   - 同一维度存在 material difference → `contrasts_with`；
   - A 削弱、质疑或暴露 B 的问题 → `challenges`；
   - 否 → 继续。
5. 是否表达 A 对 B 的定向作用？  
   - 减少 B 的可行选择空间 → `constrains`；
   - 有明确机制但没有更窄类型 → advanced `influences`；
   - 否 → 不创建正式 Group Relation。

## 4.2 无法通过选择树不是产品失败

合法落点包括：

- cross-group exit；
- Knowledge-level Relation；
- Reference Link；
- Saved Path；
- Shared Knowledge Lens observation；
- comparison view；
- ambiguous RelationCandidate；
- 当前没有群级关系。

系统不能为了“帮助用户完成”把最后一步改成 `related_to`。

## 4.3 相邻类型的最小辨别问题

| 容易混淆 | 只问这一句 |
|---|---|
| foundation vs method | B 依赖的是 A 的概念框架，还是实际使用 A 的可重复步骤？ |
| method vs applies | B 已实际采用，还是只说明在这些条件下适用？ |
| foundation vs influence | 没有 A，B 的核心解释是否失去基础；还是 A 只是改变了 B 的部分选择？ |
| constraint vs challenge | A 限制的是 B 能做什么，还是质疑 B 为什么成立？ |
| contrast vs challenge | 只是不同，还是 A 明确削弱 B？ |
| complement vs overlap | 两者共同完成同一目标，还是 Boundary 本身相交？ |
| partial overlap vs shared core | Boundary 是否部分相交，还是只是当前共享几个核心 Knowledge identities？ |
| evolved_from vs foundation | 是同一 tradition / scope 的历史连续性，还是 B 借用了 A 的思想基础？ |

---


# 5. 十一种类型的精确定义

## 5.1 `scope_within`

### 定义

Narrower Group 的完整 Boundary 在当前 Applicability 下属于 Broader Group 的 Boundary，同时 Narrower 仍拥有独立 governing question、Overview、identity 与进入价值。

```text
Narrower Group --scope_within--> Broader Group
Broader Group --contains_scope--> Narrower Group
```

### 必须满足

- 两侧 Boundary Revisions current 且可读；
- containment 是 scope truth，不是 contents percentage；
- Narrower 不是 Broader 内应当降为 Topic 的普通目录分支；
- 关系有明确 Applicability；
- 不存在 cycle；
- 同一 Boundary scope 下不同时保存 `partially_overlaps_with`。

### 不成立

- A 的多数 Knowledge 恰好也能放入 B；
- A 与 B 共享标签或来源；
- 用户只是想在 Library 中把 B 显示在 A 下面；
- A 是 B 的一个项目阶段；
- A 与 B 只有一个重叠 Topic。

### Formation 与呈现

- System aggregation：forbidden；
- Direct：用户明确建立或接受 Boundary comparison；
- Transitivity：只产生 derived closure；
- Default Network：只显示 direct containment；
- Scope Lens 可以聚合展示 closure，但必须标明“通过哪些直接范围关系”。

## 5.2 `partially_overlaps_with`

### 定义

两个独立 Group 的 Boundary 在明确的 shared questions、concepts、methods 或 applicability 中部分相交，但双方都保留重要的非重叠范围，且任何一方都不完整包含另一方。

### 必须满足

- symmetric、irreflexive、non-transitive；
- 至少一个 named overlap scope；
- 至少各自一个 material boundary difference；
- bilateral-core 或明确 named-subscope coverage；
- 与当前 `scope_within` containment check 不冲突；
- shared-core observation 可以成为 evidence，但不是充分条件。

### 不成立

- 只有一个共享 Knowledge；
- 只有 embedding similarity；
- 一侧完整包含另一侧；
- 两者只为同一目标贡献不同内容；
- 两者观点不同但 Boundary 不相交。

### Formation 与迁移

- System aggregation：strict；
- Old alias：`overlaps_with` deprecated；
- 旧 Relation 必须逐条检查 containment、proper overlap、shared-core-only 或 false positive；
- 新 UI 只显示“部分重叠”，不显示笼统“重叠”。

## 5.3 `provides_foundation_for`

### 定义

Source Group 中的理论、概念框架、原则或证据体系，为 Target Group 的核心理解、判断或组织提供基础；移除这项基础会让 Target 的部分核心解释失去理由或结构。

```text
Foundation Group --provides_foundation_for--> Target Group
Target Group --builds_on--> Foundation Group
```

### Required qualifiers

```text
foundation_kind:
  theory | conceptual_framework | principle | evidence_base
foundation_scope
target_dependency
applicability
```

### 不成立

- 只引用 A；
- B 使用 A 的一个方法但不依赖其理论；
- A 只是历史上影响 B；
- A 与 B 部分重叠；
- B 可完全独立成立，只是与 A 相似。

### Formation

- Aggregation：strict，bilateral-core 或 anchor-and-spread；
- Direct：用户完整陈述；
- Transitivity：none；A→B→C 只形成 Path；
- Removal：若只剩唯一 source anchor，最多 on-demand Candidate。

## 5.4 `provides_method_for`

### 定义

Source Group 提供一个可重复的 procedure、framework 或 practice，并且 Target Group 的任务、判断或产出实际采用它。

```text
Method Group --provides_method_for--> Using Group
Using Group --uses_method_from--> Method Group
```

### Required qualifiers

```text
method_ref_or_scope
target_use_scope
use_state: current | experimental | historical
adoption_evidence
```

### 不成立

- Target 只提到或解释该方法；
- 方法理论为 Target 提供基础，但没有实际使用；
- 方法可能适用，但尚未采用；
- 一次 Ask 使用了方法描述；
- Target 只复制了术语。

### Formation

- Aggregation：strict，anchor-and-spread 或 named-subscope；
- Candidate 必须指向实际 use anchors；
- Historical use 必须写 valid time，不能冒充 current method relation。

## 5.5 `applies_to`

### 定义

Source Group 中明确命名的 model、principle、rule、method 或 finding，在给定条件下适用于 Target Group 中的任务、对象、人群、地区、时间或情境；它不声明 Target 已经采用。

```text
Source Group --applies_to--> Target Context Group
Target Group --is_application_context_for--> Source Group
```

### Required qualifiers

```text
applicable_content
target_context
conditions
exceptions
valid_time?
```

### 不成立

- 不能填写“什么适用于什么”；
- 只存在一般相似；
- Target 已实际采用一个方法且重点是使用事实；
- 只适用于一条边缘 Knowledge，却把整群作为 target；
- 条件完全不同。

### Formation

- Aggregation：strict，anchor-and-spread 或 named-subscope；
- Group endpoints 不变，但 type qualifiers 必须保存内部 scope anchors；
- 不允许从 A applies B、B applies C 自动推出 A applies C。

## 5.6 `complements`

### 定义

两个独立 Group 围绕同一 goal、question 或 decision 提供不同、非冗余且可组合的贡献；一起使用能形成单独任何一侧都不能提供的更完整理解或行动能力。

### Required qualifiers

```text
shared_goal_or_question
A_contribution
B_contribution
combined_value
non_substitution_reason
```

### 不成立

- 只是没有冲突；
- 只是 Boundary 重叠；
- 一方完整包含另一方；
- 两侧重复同一内容；
- 一侧为另一侧提供基础或方法；
- 用户习惯一起打开。

### Formation

- Symmetric、non-transitive；
- Aggregation：strict，bilateral contributions；
- Strongest-unit removal 必须仍能证明两个不同 contribution roles；
- 如果一方实际依赖另一方，优先 directional type。

## 5.7 `contrasts_with`

### 定义

两个独立 Group 对同一问题、维度或任务，在重叠 Applicability 内具有 material difference；关系只说明差异具有理解价值，不声明任何一侧错误。

### Required qualifiers

```text
shared_question
comparison_dimension
overlapping_applicability
A_position_or_approach
B_position_or_approach
material_difference
```

### 不成立

- 两者讨论不同问题；
- 差异只来自时间、人群或地点不同；
- A 明确削弱 B 的有效性；
- 只是不同但对理解没有影响；
- AI 从词向量差异生成。

### Formation

- Symmetric、non-transitive；
- Aggregation：strict，bilateral-core；
- 若差异来自 Applicability，优先 qualifier / comparison view；
- 用户从任一端读取同一 statement identity。

## 5.8 `challenges`

### 定义

Challenger Group 在重叠 Applicability 内，通过证据、反例、方法批评或假设揭示，削弱、质疑或限制 Challenged Group 的一个明确核心主张、前提或方法。

```text
Challenger Group --challenges--> Challenged Group
Challenged Group --is_challenged_by--> Challenger Group
```

### Required qualifiers

```text
challenged_object
challenge_kind:
  counterevidence | counterexample | assumption_critique | method_critique | scope_limit
challenge_mechanism
overlapping_applicability
effect:
  limits | weakens | exposes_gap | contradicts_in_scope
```

### 不成立

- 只是观点不同；
- Applicability 不重叠；
- A 限制 B 的行动选择，而不是认识基础；
- 两者只是互补；
- 一个来源对 B 有负面措辞但没有明确对象。

### Formation 与后果

- Directed、non-transitive；
- Aggregation：strict，必须包含 explicit challenge paths 与 core coverage；
- Candidate 默认 contextual，不因情绪词 ambient 出现；
- 采用 Group Relation 不自动 retract 被挑战的 Group 或其 Relations；
- 具体受影响 Relation / Claim 另建 RelationChallenge，不能只靠群级边替代。

## 5.9 `constrains`

### 定义

Constraint Group 中的规则、资源、制度、物理限制或边界条件，实际减少 Target Group 在明确任务中的可行选择空间。

```text
Constraint Group --constrains--> Target Group
Target Group --is_constrained_by--> Constraint Group
```

### Required qualifiers

```text
constraint_source
target_decision_space
mechanism
affected_options
applicability
```

### 不成立

- A 只是影响 B 的偏好；
- A 质疑 B 的结论；
- A 为 B 提供原则基础；
- A 与 B 经常共同出现；
- Target 的选择并未实际减少。

### Formation

- Directed、non-transitive；
- Aggregation：strict，anchor-and-spread；
- 规则只约束 named Topic 时必须收窄 Applicability；
- 不从法规来源数量或引用次数推断 constraint。

## 5.10 `influences`

### 定义

Source Group 通过明确机制改变 Target Group 的 framing、priority、choice、practice 或 development，但该作用不满足更窄的 foundation、method、applies、challenge 或 constraint 定义。

### Required qualifiers

```text
influence_mechanism
affected_dimension
observable_effect_or_trace
applicability
why_no_narrower_type_fits
```

### 不成立

- 只有先后顺序；
- 只有引用、共同 Source 或相似；
- 可以准确表达为更窄类型；
- 方向不清；
- 只有“互相影响”的空泛陈述。

### Formation 与显著性

- Directed、non-transitive；
- Authoring availability：advanced；
- System aggregation：只可 on-demand Candidate；
- reciprocal influence 保存两条不同 directional statements，不能画一条无说明双箭头；
- 后续能收窄类型时，使用 Revision / successor review，不静默改 type。

## 5.11 `evolved_from`

### 定义

Successor Group 是 Predecessor Group 的 identity、tradition、project scope 或 coherent body of thought 的后续形态；两者之间存在可追溯历史连续性，而不只是借鉴或影响。

```text
Successor Group --evolved_from--> Predecessor Group
Predecessor Group --evolved_into--> Successor Group
```

### Required qualifiers

```text
lineage_basis:
  identity_successor | scope_transformation | tradition_lineage | project_lineage
lineage_directness: direct | indirect
transition_or_intermediate_refs[]
valid_time
continuity_explanation
material_change
```

### 不成立

- 标题、内容或 embedding 相似；
- B 只借用 A 的理论；
- A 对 B 有历史影响；
- 两个 Group 被用户合并但没有 successor identity；
- 只是时间先后。

### Formation 与呈现

- System aggregation：forbidden；只接受 lineage / transition basis；
- Direct lineage 进入当前邻接；
- Indirect lineage 进入 History / Path，不与 direct edge 同等显著；
- Closure 可用于查询，但不物化 Relation；
- timeline view 可以从 predecessor → successor 阅读 inverse label，但 canonical identity 仍保持同一 assertion。

---

# 6. Shared Core Knowledge：从正式边改为派生观察

## 6.1 为什么它不是 Relation

`shared_core_knowledge` 回答的是：

> 当前有哪些相同的 canonical Knowledge identities，在两个 Group 中都承担核心或代表角色？

它的 truth 完全来自当前结构，不需要独立 assertion：

```text
Knowledge identity
  × current Placements in A / B
  × current curation roles
  × current Boundary Revisions
  → GroupConnectionObservation
```

如果用户把一个 Knowledge 从 B 的 representative 改为 background，观察就应自动更新；让它像正式 Relation 一样等待 Review，会让结构投影变成维护债务。

## 6.2 Shared Knowledge Lens

Library Network 与 Group Map 提供按需 Lens：

- 默认关闭，不影响 Current relation layout；
- 选中一个 Group pair 或主动打开`共同核心知识`时出现；
- 显示共享 identity 数量、双方角色、所在路径与 Boundary revision；
- 一个 identity 的多个 Placements 只显示一次，可展开语境；
- shared count 为 0 是合法结果；
- partial index 时写`当前只检查了…`，不显示确定 0；
- List Equivalent 与 Graph 使用同一 Observation result。

P0 语言示例：

> 这两个知识群当前共享 3 条核心知识；这是一项根据当前组织方式显示的观察，不是你已经建立的群关系。

## 6.3 它怎样帮助形成正式 Relation

Observation 可以：

- 触发 pair comparison；
- 成为 `partially_overlaps_with` Candidate 的一部分 basis；
- 说明 `provides_foundation_for` 为什么有双侧核心覆盖；
- 在 Ask 中解释具体连接；
- 帮助用户发现 Placement / Boundary tension。

但它不能：

- 独自生成 Candidate；
- 进入 Relation count；
- 被 adopted；
- 拥有 assertion disposition；
- 被标为 ended / retracted；
- 自动建议 Merge；
- 让没有共享 identity 的两个 Groups 被判定无关系。

## 6.4 旧 `shares_core_knowledge_with` 的迁移

每条旧 Relation 进入 Migration Review：

1. **只是在陈述当前共享对象事实** → 提议 reclassify 为 Observation，并让旧 Relation ended / archived；需要用户确认；
2. **实际表达 Boundary 部分重叠** → 提议新建 `partially_overlaps_with` RelationCandidate；
3. **实际表达基础、方法或应用依赖** → 提议更精确 directional Candidate；
4. **用户希望保留原历史陈述** → keep legacy；新建入口不再提供该 type；
5. **依据已不成立** → 用户选择 End / Retract / Archive，不自动处理。

迁移不会删除 supporting paths、Saved Paths、Answers 或旧 Revision。

---


# 7. Type-specific formation、互斥与重复合同

## 7.1 聚合策略矩阵

| Type | Aggregation standing | Coverage | 关键 pattern | 默认 Candidate prominence |
|---|---|---|---|---|
| `scope_within` | forbidden | direct Boundary | complete containment | Boundary comparison only |
| `partially_overlaps_with` | strict | bilateral-core / named-subscope | proper Boundary intersection | ambient eligible |
| `provides_foundation_for` | strict | bilateral-core / anchor-and-spread | conceptual dependency | ambient / on-demand |
| `provides_method_for` | strict | anchor-and-spread | actual method use | ambient eligible |
| `applies_to` | strict | anchor-and-spread / named-subscope | applicability, not adoption | ambient / on-demand |
| `complements` | strict | bilateral contributions | shared goal + nonredundant roles | ambient eligible |
| `contrasts_with` | strict | bilateral-core | common comparison dimension | ambient eligible |
| `challenges` | strict | bilateral-core / named-subscope | explicit challenge + overlap | contextual by default |
| `constrains` | strict | anchor-and-spread | reduced feasible options | ambient / contextual |
| `influences` | on-demand only | typed directional | mechanism + trace | never ambient by default |
| `evolved_from` | forbidden | lineage | identity / tradition continuity | direct current / history |

通过聚合门槛不表示一定 ambient 出现。类型本身的 default prominence 与 G9 attention budget 共同决定 Candidate 是 ambient、on-demand 还是 suppressed。

## 7.2 同一 statement 的 broad / narrow duplicate

以下不能作为两条独立 Current Relations：

```text
A influences B through method M
A provides_method_for B using method M
```

如果 Applicability、mechanism 与 effect 相同，第二条是更窄表达，应取代 broad `influences`。产品提供：

- revise current Relation type；或
- 创建 narrow successor，并将 broad Relation superseded；
- 保留两者只有在 statements 确实表达两个不同机制时。

同样适用于：

- influence vs foundation；
- influence vs constrains；
- influence vs challenges；
- applies_to vs provides_method_for；
- partial overlap vs scope containment。

## 7.3 可以共存的类型

同一 Group pair 可以同时存在：

- `partially_overlaps_with` + `contrasts_with`：范围部分相交，同时在一个维度上不同；
- `provides_foundation_for` + `provides_method_for`：A 同时提供理论基础和实际方法；
- `complements` + `contrasts_with`：两者观点不同，但共同完成一个更完整解释；
- `challenges` + `partially_overlaps_with`：重叠范围内存在方向性挑战；
- `scope_within` + `constrains`：较窄范围位于较广范围内，广范围中的规则同时约束它；
- `evolved_from` + `provides_foundation_for`：仅当 lineage 与当前概念依赖是两个独立 statements。

Bundle 必须显示为什么不是重复；不能只列两个 type labels。

## 7.4 Applicability 先于互斥

同一 pair 的 A `scope_within` B 与 A `partially_overlaps_with` B 看似冲突，但若分别适用于不同时间或明确子范围，不一定逻辑冲突。Validation 顺序：

1. 比较 Boundary Revision；
2. 比较 valid time；
3. 比较 Applicability；
4. 比较 statement target；
5. 只有重叠后才运行互斥 / duplicate check。

## 7.5 方向不由英文词序猜测

每个 directed type 固定 endpoint roles：

| Type | From role | To role |
|---|---|---|
| `scope_within` | narrower scope | broader scope |
| `provides_foundation_for` | foundation source | dependent target |
| `provides_method_for` | method source | using target |
| `applies_to` | applicable source | target context |
| `challenges` | challenger | challenged target |
| `constrains` | constraint source | constrained target |
| `influences` | influencer | affected target |
| `evolved_from` | successor | predecessor |

UI 创建时始终用完整句子回读，并允许`交换方向`。交换后重新运行 required qualifier validation；不能只转箭头。

## 7.6 Transitivity registry

| Type | Direct Relation transitive? | Derived path |
|---|---|---|
| `scope_within` | no | containment closure allowed |
| `evolved_from` | no | indirect lineage path allowed |
| 其余九种 | no | only generic multi-step path |

`A provides_foundation_for B` + `B provides_foundation_for C` 不会自动推出 A 为 C 提供基础。系统可以回答“存在一条两步基础链”，但不能压成新 RelationCandidate，除非另有直接支撑重新通过聚合门槛。

## 7.7 Type validation outcomes

```text
valid_for_selected_type
missing_required_qualifier
adjacent_type_more_precise
ambiguous_between_types
duplicate_of_narrower_relation
incompatible_same_scope
unsupported_direction
invalid_lineage
derived_observation_only
no_formal_relation_needed
```

这些 outcomes 是解释和动作建议，不是 Relation disposition。

---


# 8. 创建、编辑、迁移与长期维护

## 8.1 用户直接创建

用户从 Group pair、Network、Ask 或正文路径进入`建立群关系`：

1. 先看到当前已有 Relations、exits 与 derived observations；
2. 选择自然意图，而非英文 enum；
3. 产品推荐 1–3 个 types，并解释差异；
4. 用户用完整句子回读 from / to；
5. 只填写该 type 真正必要的 qualifiers；
6. 检查 duplicate、incompatibility 与 Boundary；
7. 预览 Network / Overview / Ask 影响；
8. 本地原子保存 Relation + Revision；
9. Receipt 提供 Inspect、Undo 与沿关系探索。

用户直接表达不需要系统聚合门槛，也不需要外部 Evidence；但 type contract 与完整 statement 仍必须成立。

## 8.2 AI / Source / Import Candidate

系统必须保存：

- proposed type + TypeDefinitionRevision；
- statement 与 inverse reading；
- type-specific qualifiers；
- alternative types considered；
- why alternatives were rejected；
- aggregation Assessment；
- evidence / path basis；
- existing Relations / Observations comparison；
- Candidate prominence reason。

如果两个 types 仍无法区分，Candidate 保持 `ambiguous_between_types`，只能在用户主动比较时出现；不能先创建两条 competing edges。

## 8.3 修改 type

修改 type 有三种不同后果：

### Same assertion refinement

`influences` 收窄为 `constrains`，statement 主要角色和机制连续。可以创建同一 Relation 的新 Revision，但必须显示历史 type change。

### New assertion

`partially_overlaps_with` 改为 `provides_foundation_for`，意义、direction 与 why_it_matters 已不同。创建新 Relation；旧 Relation End / Supersede / Retract 由用户决定。

### Presentation alias

`provides_foundation_for` 从另一端显示 `builds_on`，不创建 Revision。

产品在提交前根据 semantic diff 解释会发生哪一种。

## 8.4 Registry revision

Registry 发布新 revision 时：

- 新建 Candidate 使用最新 active TypeDefinitionRevision；
- 旧 Relations 按原 revision 继续可读；
- breaking semantic change 不原地覆盖；
- deprecated type 不再出现在普通创建入口；
- affected current Relations 生成一条 scope-bounded Migration summary；
- 每条高影响迁移由用户逐项或按同类规则确认；
- Reject migration 不改变 Relation truth；
- offline 时旧 registry snapshot 仍可回读。

## 8.5 `overlaps_with` migration

旧 relation 逐项运行：

```text
if complete containment:
  propose scope_within
else if proper partial boundary overlap:
  propose partially_overlaps_with
else if only shared core identities:
  propose shared_core_knowledge observation
else if only semantic similarity:
  propose end / retract / keep legacy
else:
  needs manual review
```

系统不能把所有旧 `overlaps_with` 文本批量换 key，因为旧 statement 可能没有足够 Boundary evidence。

## 8.6 Relation review

Type-specific review trigger 包括：

- Boundary change 让 partial overlap 变为 containment 或分离；
- method use 从 current 变 historical；
- application conditions 改变；
- complementary contribution 被删除或变得冗余；
- contrast 的 comparison dimension 不再共同；
- challenge 的 Applicability 不再重叠；
- constraint 不再减少选择；
- influence mechanism 被更窄 type 取代；
- lineage 新增 intermediate successor；
- registry definition deprecated。

Review 不自动改变 assertion disposition。

---


# 9. Network、Ask、Overview 与 Search

## 9.1 Library Network

Current layer 只显示 maintained + lifecycle=current + applicable Relations。Type registry 决定：

- label；
- direction / symmetry；
- family；
- direct / derived；
- filter behavior；
- type-specific status explanation。

Derived Shared Knowledge Observation 只在 Shared Knowledge Lens 中出现。Scope closure、indirect lineage 与 multi-step chains 只在明确 Expand / Path / History 中出现。

## 9.2 Group pair inspector

选择两个 Groups 后，Inspector 顺序固定：

1. Current Relations，按独立 statements；
2. derived shared Knowledge observations；
3. concrete cross-group exits；
4. open Candidates / unresolved type；
5. historical Relations；
6. 当前没有关系时的诚实说明。

它不先显示`共有 12 条连接`，因为这会把不同 standing 混成数量。

完整 Pair Orientation、snapshot consistency、Ask Scope、Relation Bundle、Graph / List / mobile 等价与 exact return 以`AI-native-个人知识库-知识群对照与关系检查器合同-v1.0.md`为准。

## 9.3 Ask

问“这两个知识群是什么关系”时，Answer：

1. 用自然句列出 current Relations；
2. 若同 pair 多关系，按 family 组织但不合并；
3. 说明 shared-core observation 是当前结构观察；
4. 没有 formal Relation 时列具体 exits，不说“它们没有任何联系”；
5. possible Candidate 必须说明 proposed type 与相邻类型差异；
6. `influences` 若机制不明，回答`目前只能看到若干具体联系，无法确认群级影响`；
7. 不因回答创建、迁移或重新分类 Relation。

## 9.4 Overview

Group Overview 的 formal relation projection 只显示：

- 少量 current Relations 的完整人话；
- review_due 的一句变化说明；
- direction 从当前 Group 视角自然回读；
- type-specific Applicability。

Shared core 只能作为动态 Projection Block：

> 与“AI Agent 产品设计”当前共享 3 条核心知识。

它不能被静默写进 Editorial prose；用户若希望形成长期解释，应建立更具体 Relation 或手工写 Editorial statement 并绑定 Support Map。

## 9.5 Search

Search 可以：

- 按用户语言搜索 type 和 inverse label；
- 搜索完整 relation statement；
- filter by family / direction / current standing；
- 搜索 deprecated legacy label 并显示 current mapping；
- 查找 Shared Knowledge observations，但结果明确为动态观察；
- direct Relation 与 derived path 分层。

Search ranking 不因某 type 更“高级”而提高对象重要性。

## 9.6 Saved Path 与历史 Answer

Saved Path step 固定 relation_revision_id 与当时 type revision。未来 type migration 后：

- 路线仍显示原句；
- 提示 current successor / revised type；
- 用户可以继续历史路线或更新 Path；
- Shared Knowledge observation 作为 observation snapshot step，不能冒充 formal Relation；
- as-of Ask 使用当时 registry revision 回读。

---


# 10. 产品语言与渐进披露

## 10.1 P0：用户只读一句关系

| Type | P0 示例 |
|---|---|
| `scope_within` | “长期记忆系统”是“认知科学”内一个独立知识范围 |
| `partially_overlaps_with` | “认知科学”和“个人知识管理”在记忆与学习策略上部分重叠，但各自范围不同 |
| `provides_foundation_for` | “认知科学”为“AI Agent 产品设计”的记忆机制提供理论基础 |
| `provides_method_for` | “用户研究方法”为“AI Agent 产品设计”的任务分析提供方法 |
| `applies_to` | “认知负荷理论”中的分段原则适用于“AI Agent 产品设计”的首次使用流程 |
| `complements` | “定性研究”和“行为数据分析”从原因与行为规模两个侧面共同支持产品判断 |
| `contrasts_with` | “本地优先”和“云端协作”在所有权与共享效率上采取不同取舍 |
| `challenges` | “生态效度研究”质疑“实验室记忆研究”在真实工作场景中的适用性 |
| `constrains` | “法国租房法规”限制“住房选择”中可以采用的担保方案 |
| `influences` | “认知科学”通过注意资源模型影响“AI Agent 产品设计”的交互优先级 |
| `evolved_from` | “Personal Knowledge Library”由早期“Personal Cognitive OS”产品范围演变而来 |

## 10.2 P1：为什么是这一种

P1 只回答最可能的相邻混淆：

- `这是理论基础，不是实际采用的方法`；
- `这是可能适用，不表示目标知识群已经采用`；
- `这是双方部分重叠，不是一方包含另一方`；
- `这是从不同侧面共同完成目标，不表示它们内容重叠`；
- `这项关系明确质疑另一方，不只是不同观点`；
- `这项限制减少了可选方案，不只是一般影响`；
- `这是历史连续性，不只是思想借鉴`。

## 10.3 P2：核验类型合同

显示：

- canonical / inverse labels；
- endpoint roles；
- required qualifiers；
- Boundary / Applicability；
- type validation report；
- adjacent type comparison；
- aggregation policy；
- registry revision；
- migration status。

## 10.4 P3：Forensic

显示 machine keys、definition revision diff、constraint IDs、policy revision、origin records、migration decision history 与 export representation。

## 10.5 禁用语言

- `强关系 / 弱关系`；
- `关联度 87%`；
- `因为有 5 条边，所以是基础关系`；
- `相关领域`作为正式 type；
- `自动升级为重叠关系`；
- `共享核心知识关系已失效`；
- `AI 判断它们互相影响`但没有 mechanism；
- `所有关系`把 observation、exit、candidate 与 current 混在一起。

---


# 11. 对 Screen 2 / Screen 3 的设计证明要求

## 11.1 这轮冻结语义，不冻结视觉答案

当前已接受的 Ardot 证据与逐屏审查继续见：

- `design-audit-ardot/group-relation-round-2026-08-10/accepted/01-current-network-concept.png`；
- `design-audit-ardot/group-relation-round-2026-08-10/accepted/02-current-dual-mirror.png`；
- `design-audit-ardot/群级关系升级门槛与视觉证明缺口审计-v1.0.md`。

本文件不新增截图审计结论，只把 Type Registry 转换为未来设计必须证明的责任。

## 11.2 Screen 2 — Relation Companion

未来双镜关系面至少必须证明：

1. 选中一条 edge 后首先显示完整 statement，不先显示 type key；
2. Directed relation 的 endpoint roles 和 inverse reading 可以理解；
3. Symmetric relation 不出现误导箭头；
4. `scope_within` 不让 Group 看起来变成文件夹 / Subgroup；
5. `evolved_from` 的时间方向与 canonical assertion 不冲突；
6. `complements`、`contrasts_with`、`challenges` 在同 pair 出现时不会靠三种颜色猜意义；
7. `influences` 显示 mechanism，不能只有“影响”；
8. Shared Knowledge Observation 明确是当前结构观察；
9. Open endpoint、Inspect relation、Compare pair 与 Back 保持不同后果；
10. 窄窗口一次显示一个 pane 时仍能回到原 Reading Anchor。

## 11.3 Screen 3 — Library Network

未来关系空间至少必须证明：

- Current / Suggested / History / Shared Knowledge Lens 四者不互相冒充；
- Scope、Contribution、Comparison、Directional Effect、Lineage 使用 family-level grammar；
- 十一种 exact types 主要靠 label / sentence，不靠十一种颜色；
- directed / symmetric / derived path 可以用文字、箭头与结构共同判断；
- same-pair Bundle 能展开多条独立 statements；
- deprecated / migration relation 不混入默认 current；
- 0 relation、1 relation、dense relations 都有合法表达；
- Graph / List 选择、filter、standing 与动作完全同义；
- Shared Knowledge Lens 开关前后 Current nodes 与 edges 不重排；
- indirect scope / lineage closure 只有明确 Expand 后出现；
- partial index、layout unavailable 与 AI unavailable 有可靠退化。

## 11.4 Family-level visual grammar

本合同只冻结可区分责任，不指定最终颜色或线型：

| Family | 必须被感知的差异 |
|---|---|
| Scope | 范围关系，不是语义因果；containment 与 partial overlap 分开 |
| Contribution | 有 from → to，说明提供的具体内容 |
| Comparison | symmetric 或 directional challenge 必须可辨 |
| Directional Effect | mechanism 与 target dimension 清楚 |
| Lineage | 时间 / predecessor / successor 清楚 |
| Observation | derived、可刷新、不是 formal Relation |

允许 family 共用 token，但 exact type 必须由可读 label 与 Inspector 证明。颜色从不承担唯一意义。

## 11.5 Edge label budget

Graph resting state：

- 一条边至少显示能区分 type 的中文 verb phrase；
- 选中后显示完整 statement；
- dense state 先折叠 Bundle 或要求 anchor，不截成`相关`；
- inverse reading 从当前选中 Group 视角自然表达；
- qualifier 影响结论时显示短限定，如`仅限首次使用`；
- review_due 用一句变化说明，不以断线暗示错误；
- observation 使用`当前共享 3 条核心知识`，不使用 edge type label。

## 11.6 必备 visual fixtures

下一轮视觉探索前，真实 fixture 至少包含：

- one `scope_within` + derived closure；
- one `partially_overlaps_with` + shared-core observation；
- foundation vs method adjacent-type comparison；
- applies_to with named conditions；
- complements + contrasts same pair；
- challenges directional + affected Claim / Relation；
- constrains vs influences；
- direct + indirect evolved_from；
- deprecated overlaps migration；
- shared core changes after Placement role edit；
- ambiguous Candidate；
- 0 Relation but several exits；
- Graph / List / mobile / keyboard states。

---


# 12. 代表场景

## 12.1 完整包含但仍是独立 Group

“AI Agent 长期记忆”完整落在“AI Agent 产品设计”当前 Boundary 内，但拥有独立 governing question 和长期入口。用户建立 `scope_within`；Library 不把它变成 Topic，删除上位 Group也不级联删除。

## 12.2 真正的部分重叠

“认知科学”与“个人知识管理”在记忆、学习和信息组织上相交，但前者还研究知觉 / 决策，后者还研究工具 / 工作流。Candidate 使用 `partially_overlaps_with`，同时说明 overlap 与 boundary differences。

## 12.3 只共享核心知识

两个 Groups 共享三条 representative Knowledge，但 governing questions 没有充分 Boundary intersection。Shared Knowledge Lens 显示观察；系统不创建 formal Relation 或 Candidate。

## 12.4 Foundation 不是 Method

认知负荷理论为 onboarding 判断提供理论基础，但目标团队没有采用认知科学中的实验方法。类型是 `provides_foundation_for`，不是 `provides_method_for`。

## 12.5 Applies 不表示已采用

间隔效应原则适用于学习型 Agent 的提醒设计，但产品尚未实施。保存 `applies_to`；实施后可以另建 `provides_method_for` 或更具体 Knowledge Relation，不原地偷换意义。

## 12.6 Complement 不是 Overlap

访谈研究解释“为什么”，行为数据说明“多少人、在哪一步”；两者围绕同一产品判断贡献不同信息。它们 `complements`，即使 Boundary 交集很少。

## 12.7 Contrast 不是 Challenge

本地优先与云协作在所有权 / 共享效率上取舍不同，是 `contrasts_with`。只有当一方的证据明确削弱另一方在同范围的假设时，才是 `challenges`。

## 12.8 Challenge 不自动撤回

真实工作场景研究挑战实验室记忆结论的外部效度。Group Relation 被采用，但被挑战的具体 Claims 只进入 open Challenge / review；系统不把整个实验研究 Group 标错或撤回。

## 12.9 Constraint 不是一般影响

法国租房法规排除了若干担保方案，直接减少住房选择空间，使用 `constrains`。法规让用户更谨慎但没有减少选项时，只可能是 `influences`，且需机制。

## 12.10 Broad influence 被窄类型取代

已有“A influences B through task analysis method”，后来语义被明确为实际方法采用。系统建议将同一 Relation Revision 收窄为 `provides_method_for` 或创建 narrow successor；不会保留两条重复 Current edges。

## 12.11 Lineage 不是 Foundation

Personal Knowledge Library 由早期 Personal Cognitive OS 产品范围连续演变，使用 `evolved_from`。认知科学为它提供理论基础则是另一条 Relation；两个 statements 可以并存。

## 12.12 Scope cycle

A scope_within B、B scope_within C，用户尝试 C scope_within A。Validation Report 阻止提交并解释 cycle；已有 Relations 不被修改。

## 12.13 Boundary 变化改变类型

A 与 B 原本部分重叠；B 收窄后完整落在 A 中。旧 partial-overlap Relation进入 review_due；系统提出 `scope_within` Candidate / migration，但不自动改 type。

## 12.14 Deprecated overlap migration

旧 `overlaps_with` statement 只写“二者共享三个核心概念”。Migration Review 判断证据只支持 Shared Knowledge Observation；用户可以保留 legacy、转 Observation，或补 Boundary statement 建立 partial overlap。

## 12.15 Shared observation 自动变化

用户将一条 Knowledge 在 B 的 role 从 representative 改为 background。Observation count 从 3 变 2；不会创建 Relation Revision、Review Case 或维护提醒。

## 12.16 同 pair 多条关系

A 为 B 提供理论基础，同时 A 与 B 在方法选择上形成 contrast。Bundle 展示两条完整 statements；它们不合并为 related，也不因共用 endpoints 被去重。

## 12.17 AI 无法定型

系统发现 A 与 B 多次互引，但无法判断是 foundation、influence 还是只是 Reference。只保留 exits / ambiguous Candidate；用户主动比较时解释缺什么，不制造三条 competing suggestions。

## 12.18 离线恢复

离线打开关系，local registry snapshot 能回读 statement、inverse、qualifiers 与 History；在线 type suggestion 与 migration summary暂不可用，但 Current Network truth 不变。

---


# 13. Given / When / Then 验收合同

## 13.1 不允许 `related_to`

**Given** 用户或 AI 只能说明两个 Groups“有关”  
**When** 创建 Group Relation  
**Then** 产品要求选择更明确意图，或保留 exit / Reference / ambiguous Candidate；正式 registry 不保存 `related_to`。

## 13.2 Type revision 固定

**Given** Relation 在 registry v1 下创建  
**When** registry v2 修改同 type 定义  
**Then** 历史 Revision 继续引用 v1 回读；v2 只影响新建和显式 Migration，不静默重解释。

## 13.3 Directed inverse 不重复

**Given** A provides foundation for B  
**When** 从 B 端打开  
**Then** 读取 B builds on A，仍是同一 relation_id，不创建镜像边。

## 13.4 Symmetric normalization

**Given** A complements B 已存在  
**When** 用户从 B 建立 complements A  
**Then** 产品定位同一 Relation，允许补充 / 修订，不创建 duplicate。

## 13.5 Scope direct 与 closure 分开

**Given** A scope_within B，B scope_within C  
**When** 查看 A 与 C  
**Then** 显示 derived containment path；不创建 A→C direct Relation，不计入 direct edge count。

## 13.6 Scope cycle

**Given** A→B→C scope chain  
**When** 提交 C scope_within A  
**Then** Validation Report 失败并解释 cycle；三个现有 Groups / Relations 均不改变。

## 13.7 Partial overlap 排除 containment

**Given** B Boundary 完整包含 A  
**When** 系统评估 A partially_overlaps_with B  
**Then** outcome 指向 `scope_within` comparison；不能因为共享多个 core Nodes 通过 partial overlap。

## 13.8 Old overlap migration

**Given** legacy overlaps_with Relation  
**When** registry migration 运行  
**Then** 分别评估 containment、partial overlap、shared-core-only 与 insufficient；不批量字符串改名。

## 13.9 Shared core 不增加 Relation count

**Given** 两个 Groups 共享三个 current representative Knowledge identities  
**When** 打开 Shared Knowledge Lens  
**Then** 显示 Observation；Current / Suggested / History relation counts 和 resting layout 不变化。

## 13.10 Observation 自动更新

**Given** shared-core Observation 当前为 3  
**When** 一个 Placement role 改为 background  
**Then** evaluation 更新为 2；不创建 RelationRevision、Candidate、Review Case 或 History edge。

## 13.11 Foundation required meaning

**Given** A 被 B 多次引用但没有 target dependency  
**When** 评估 provides_foundation_for  
**Then** 不通过；保持 exits，不能以 citation count 替代 foundation role。

## 13.12 Method requires use

**Given** B 解释 A 的方法但未采用  
**When** 评估 provides_method_for  
**Then** 不通过；若条件完整可考虑 applies_to，否则保留 Knowledge path。

## 13.13 Applies 不声明 adoption

**Given** A 的原则适用于 B，但 B 未采用  
**When** 创建 applies_to  
**Then** statement 显示 applicable content、target context 与条件，不显示`B 使用 A 的方法`。

## 13.14 Complement requires nonredundant roles

**Given** A、B 都支持同一目标，但内容完全重复  
**When** 评估 complements  
**Then** 不通过；必须说明不同 contribution 与 combined value。

## 13.15 Contrast requires common dimension

**Given** A、B 结论不同但研究对象 / 时间不重叠  
**When** 评估 contrasts_with  
**Then** 优先说明 Applicability 差异；不创建群级 contrast。

## 13.16 Challenge has direction

**Given** A 的证据削弱 B 的一个核心假设  
**When** 创建 Group Relation  
**Then** 保存 A challenges B，包含 challenged object、mechanism 与 overlap；从 B 端读取 is challenged by A。

## 13.17 Challenge 不决定 disposition

**Given** A challenges B 已采用  
**When** 当前 Network / Ask 使用 B  
**Then** B 仍正常存在；受影响 Claims / Relations 按具体 Challenge 和 Applicability进入 review，不全局撤回。

## 13.18 Constraint reduces options

**Given** A 只改变 B 的偏好但不减少可行选项  
**When** 评估 constrains  
**Then** 不通过；需要 influence mechanism 或更具体 relation。

## 13.19 Influence advanced fallback

**Given** narrower type 无法表达，但 A 对 B 有明确机制与效果  
**When** 用户选择`其他明确影响`  
**Then** 可创建 influences，必须填写 mechanism、affected dimension 与为什么窄类型不适合。

## 13.20 Influence 不 ambient

**Given** 系统聚合出 influences Candidate  
**When** 用户没有主动比较该 pair  
**Then** Candidate 默认不进入 ambient Suggested；Current 不变化。

## 13.21 Narrow type replaces duplicate broad type

**Given** A influences B 与 A provides_method_for B 表达同一 method / Applicability  
**When** duplicate check 运行  
**Then** 建议保留 narrow statement，并通过 Revision 或 successor 处理 broad Relation，不显示两条 Current edges。

## 13.22 Evolved direct / indirect

**Given** A evolved_from B，B evolved_from C  
**When** 查看 A lineage  
**Then** A→B 是 direct current adjacency，A→C 是 indirect derived path；不自动创建 Relation。

## 13.23 Similarity 不构成 lineage

**Given** 两个 Group 标题与内容高度相似但没有 continuity  
**When** 评估 evolved_from  
**Then** invalid_lineage；系统不以 embedding 或 creation time 推断。

## 13.24 Intent-first create

**Given** 用户选择两个 Groups 建立关系  
**When** 打开创建流程  
**Then** 先回答自然问题并看到 1–3 个相关 types；不先面对十一项英文 enum。

## 13.25 Ambiguous type 不产生 edge

**Given** foundation、influence 与 shared reference 无法区分  
**When** AI 完成评估  
**Then** outcome=ambiguous_between_types；只按需显示解释，不创建多条 Suggested edges。

## 13.26 用户直接提交

**Given** 用户完成完整 statement、direction 与 required qualifiers  
**When** 本地写入成功  
**Then** 原子创建 maintained current Relation；不要求通过系统 aggregation gate 或再次采用。

## 13.27 Candidate 解释 alternatives

**Given** AI 提议 provides_foundation_for  
**When** 打开 Candidate Inspector  
**Then** 显示为什么不是 method / applies / influence，以及改变 type 会要求哪些 qualifiers。

## 13.28 Type change 区分 revision 与 new relation

**Given** 用户把 influences 改为 constrains，或把 partial overlap 改为 foundation  
**When** 提交  
**Then** 前者若机制连续可形成同 Relation Revision；后者默认创建新 Relation并处理旧 disposition；提交前解释差异。

## 13.29 Graph / List 同义

**Given** 同一 Scope 有 directed、symmetric、observation 与 derived lineage  
**When** 在 Graph / List 切换  
**Then** identity、statement、direction、family、standing、qualifiers、selection 与 actions完全一致。

## 13.30 Ask 不写入

**Given** 用户问 A 与 B 是什么关系  
**When** Answer 比较 current Relations、exits、Candidates 与 Observations  
**Then** 不创建、迁移、采用或修改任何 Relation；保存动作另行明确选择对象。

## 13.31 Overview 分离 formal 与 observation

**Given** A 与 B 没有 formal Relation，但共享三个 core Knowledge  
**When** 打开 A Overview  
**Then** 只在动态 Projection / explicit lens 显示共享观察；不写进正式关系区或 Editorial prose。

## 13.32 Restore without current registry service

**Given** 本地包含 Relations、TypeDefinitionRevisions 与 history，但 AI / registry update service不可用  
**When** 恢复  
**Then** Current / History statements、inverse readings、filters 与 List 可重建；新建议和 migration 暂停但不损坏 truth。

---


# 14. 指标与反指标

## 14.1 结果指标

- **Type Explanation Success**：用户能否用一句话解释为什么是该 type；
- **Adjacent-type Correction Rate**：用户采纳前主动改成相邻更准确 type 的比例；
- **Formal / Observation Distinction**：用户能否区分正式 Relation 与 shared-core observation；
- **Direction Readback Accuracy**：从两端读取仍能判断同一 assertion 的比例；
- **No-relation Confidence**：只有 exits / observations 时，用户是否仍认为系统诚实而完整；
- **Migration Decision Quality**：用户能否理解 keep / revise / reclassify / end 的后果；
- **Graph / List Semantic Parity**：两种表面完成同一类型判断的成功率；
- **Return Fidelity**：关系创建 / migration / inspect 后返回原现场的正确率。

## 14.2 诊断指标

- Candidate ambiguous-type rate；
- broad `influences` selection rate；
- broad → narrow revision rate；
- duplicate relation prevention rate；
- shared-core-only proposals correctly downgraded；
- partial-overlap vs containment correction rate；
- missing qualifier rate by type；
- registry migration defer / reject rate；
- relation statement truncated / expanded frequency；
- mobile List completion rate。

## 14.3 反指标

不得以以下数字证明 registry 成功：

- relation types 总数；
- 每个 Group 平均类型覆盖；
- Network edge 数；
- `related_to` 被替换的数量本身；
- Candidate acceptance rate 越高越好；
- shared-core observation 转正式 Relation 的比例；
- 用户选择 type 的速度越快越好；
- AI 推荐与用户最终 type 一致率；
- 图中每个 family 的颜色均匀度；
- 所有 pair 都有一种关系。

---


# 15. 官方研究事实、产品推论与证据边界

## 15.1 SKOS：hierarchical 与 associative relation 分开

W3C SKOS 将 broader / narrower hierarchy 与 symmetric `related` 分开，并规定 `related` 与 broaderTransitive 不相容；hierarchical 与 associative semantics 不能只用一条泛关联互换。[SKOS Reference](https://www.w3.org/TR/skos-reference/)

**产品推论：** Scope family 与其他 semantic families 必须分开；`related_to`不能掩盖 containment、comparison 或 contribution。SKOS 没有定义本产品的十一种 Group types。

## 15.2 OWL 2：inverse、symmetric 与 transitive 是显式特征

OWL 2 将 inverse property expression、SymmetricObjectProperty 与 TransitiveObjectProperty 作为不同、显式声明的语义能力；一个动词看起来像可反向或可传递，不代表系统可以自行推断。[OWL 2 Structural Specification](https://www.w3.org/TR/owl-syntax/)

**产品推论：** 每个 TypeDefinitionRevision 显式保存 direction、inverse、symmetry 与 transitivity policy；inverse label 不创建镜像，closure 不物化 direct Relation。

## 15.3 OBO RO：overlap 的形式含义可能包含 part-of

OBO Relation Ontology 的过程关系说明中，`overlaps` 表示至少共享一个 part，并把 part-of、has-part 与 proper overlap 都包含在广义 overlap 下。[OBO Relation Ontology — Process Relations](https://oborel.github.io/obo-relations/process-relations/)

**产品推论：** 为避免产品用户把 containment 与 partial intersection 混淆，Group-level type 明确命名为 `partially_overlaps_with`。这不是采用 OBO 的 domain ontology，也不声称知识群是物理部件。

## 15.4 OBO RO：direct 与 indirect relation 需要区分

OBO Relation Ontology 说明 direct form 可以是 transitive relation 的 non-transitive subproperty，并以 develops-from / directly-develops-from 展示直接 succession 与 closure 的区别。[OBO Relation Ontology — Direct and Indirect Relations](https://oborel.github.io/obo-relations/direct-and-indirect-relations/)

**产品推论：** `evolved_from` 保存 lineage directness；直接邻接与间接 path 不以同一显著性出现。具体 lineage 类型仍是本产品决定。

## 15.5 PROV-O：Influence 是宽泛 superproperty，Revision 是更具体 derivation

W3C PROV-O 把 `wasInfluencedBy`定义为对 Entity、Activity 或 Agent 特征产生影响的广义 superproperty，同时把 `wasRevisionOf`作为 `wasDerivedFrom` 的更具体关系。[PROV-O](https://www.w3.org/TR/prov-o/)

**产品推论：** `influences`不应成为首选万能关系；存在更窄且准确的 foundation、method、constraint、challenge 或 lineage 时应使用窄类型。PROV-O 没有证明这些产品类型之间的具体边界。

## 15.6 SHACL：验证报告与数据写入分开

W3C SHACL 将 validation 结果表达为独立 Validation Report，并要求验证期间 data graph 与 shapes graph 保持不变。[SHACL](https://www.w3.org/TR/shacl/)

**产品推论：** TypeValidationReport 只说明 pass / fail / ambiguous 与建议动作，不直接修改 Relation 或 Candidate。

## 15.7 OBO Foundry：不要为相同意义重复造 relation

OBO Foundry 的 relation principle 要求在已有关系意义适用时复用，而不是声明意义相同的新关系。[OBO Foundry Relation Principle](https://obofoundry.org/principles/fp-007-relations.html)

**产品推论：** 同一 mechanism 的 broad `influences` 与 narrow type 不能同时成为两条 Current Relations；Registry 需要 duplicate 与 migration contract。产品并不直接复用生物医学 RO identifiers。

## 15.8 研究没有证明什么

上述来源没有证明：

- 本产品应该有十一种 Group Relation types；
- `complements` 与 `challenges`一定是必要首批类型；
- `shares_core_knowledge_with`一定应该成为 Observation；
- `partially_overlaps_with`是唯一正确命名；
- `influences`默认只按需出现；
- direct lineage 应进入默认 Network；
- family-level visual grammar 一定比 type-level color 更易理解；
- 用户能理解 Relation 与 Observation 的区别；
- Quick create 的六个自然问题足够。

这些是为了减少模糊边、保护知识所有权、保持网络可读所做的产品决定，仍需真实任务和设计证明验证。

---


# 16. 对文档体系的覆写与同步要求

## 16.1 立即覆写的旧语义

任何有效文档出现以下语义时，以本文为准：

- Group-level `overlaps_with` → deprecated；新建使用 `partially_overlaps_with`；
- `shares_core_knowledge_with` formal Relation → derived `shared_core_knowledge` Observation；
- `influences` 是普通可选类型 → advanced fallback；
- `contrasts_with` 足以表达方向性挑战 → 新增 `challenges`；
- overlap / contrast 已覆盖共同完成目标 → 新增 `complements`；
- evolved_from 不需要 directness → 必须保存 direct / indirect；
- 类型只是 enum / label → 必须固定 TypeDefinitionRevision；
- registry update 批量改旧边 → 必须 Migration Review；
- 十一种类型各用一种颜色 → family-level grammar + label first；
- Shared core count 进入 Relation count → 禁止。

## 16.2 Canonical 必须同步

Canonical 至少需要同步：

- 十一类 formal types 与五个 families；
- `partially_overlaps_with` rename；
- Shared Knowledge Observation；
- `complements` / `challenges`；
- `influences` advanced fallback；
- intent-first selection tree；
- TypeDefinitionRevision / ValidationReport / MigrationReview；
- direct / inverse / symmetric / derived contracts；
- Ask、Overview、Network、Search 与 History行为；
- 新 journey / acceptance / visual Gate。

## 16.3 进入原型前的新 Gate

在既有 Gate 之外还必须满足：

1. 用户能区分 Relation 与 Shared Knowledge Observation；
2. 用户能区分 partial overlap 与 scope containment；
3. foundation / method / applies / influence 的选择可理解；
4. complement / contrast / challenge 的选择可理解；
5. constraint 与 epistemic challenge 不混淆；
6. direct / inverse / symmetric / derived 在 Graph 与 List 同义；
7. deprecated types 有迁移 fixture；
8. same-pair multi-type Bundle 可完整选择；
9. family-level visual grammar 不依赖颜色；
10. Screen 2 / 3 使用真实 statements 和 qualifiers，而不是关系词云。

当前仍处于产品定义阶段；本文没有授权原型。

---


# 结论

知识网络的产品品味，不来自边的数量，而来自对语言的克制。`相关`、`重叠`和`影响`都很容易让图变得丰富，却把真正需要用户拥有的判断藏起来。

这份 registry 把群级关系收敛成十一种正式陈述，同时主动移除一类不该被拥有的边：共享核心知识回到 derived observation。这样，结构事实可以自动更新，语义陈述仍由用户拥有；系统可以帮助发现，却不能靠模糊动词占据 Network。

方向 2 的关系空间只有做到这一点，才真正与方向 3 的层级阅读等价：纵向每一级都知道自己在解释什么，横向每一条边也知道自己为什么存在。
