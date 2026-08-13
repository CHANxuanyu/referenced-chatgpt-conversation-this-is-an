# AI-native 个人知识库

## 问题知识、未知与求解生命周期合同 v1.0 — Question Knowledge, Unknown & Resolution Lifecycle

> 文档日期：2026-08-10  
> 文档性质：产品本体合同，不是任务系统、聊天界面、RAG 技术方案、数据库设计或原型授权  
> Canonical 产品定义：`AI-native-个人知识库-终局产品设计文档-v4.0.md`  
> 领域覆写：本合同对 Question Knowledge、运行时 Unknown、持久 Gap、Conflict、QuestionTargetReference、部分回答、暂时可用、充分回答、停止追问与重新打开拥有领域覆写权  
> 真实夹具验证：`AI-native-个人知识库-真实端到端使用样例与设计数据夹具-v1.0.md` 已用 2026 法国租房 / Visale / 住房补助主题验证 Question 的 Applicability、规则 / 个体推断 / 机构结果分层、变化复核与 Reopen；本文吸收其结构性修正，但不授权原型  
> 第二真实夹具验证：`AI-native-个人知识库-第二真实端到端夹具-概念学习、多语境复用与群关系-v1.0.md` 已用一条 decision-facing parent Question、四条 required Subquestions 与一条独立 context Question，验证 objective / retention horizon / assessment target、criterion rollup、`provisionally_resolved + active`及方法学 challenge 的局部复核；本文吸收其结构性修正，但不授权原型  
> 关系边界：`uncertain_about` 与 `reopens` 不属于 ordinary Knowledge Relation；完整类型边界见`AI-native-个人知识库-知识关系类型注册表与跨层语义合同-v1.0.md`  
> 当前阶段：继续定义产品本身；不授权制作、修改或发布原型  
> 核心问题：这个知识库怎样诚实保存“我还不知道什么”，又怎样让一次 AI 查询、后续研究与正式知识持续汇合，而不把聊天、任务或看似顺畅的回答冒充已经解决的问题

---

# 0. 执行结论

## 0.1 一句话定义

> **Question Knowledge 是用户决定长期保留、可以持续求解的一项“已知未知”：它拥有稳定身份、当前问题表述、适用范围、求解标准、目标、当前回答依据、剩余未知和完整历史。**

它仍然是 Knowledge，不是待办事项，也不是聊天线程。它能进入知识群、层级、搜索、关系探索和 AI 查询；但它的“关于什么”“回答到哪里”“是否还想继续追问”由专门的 Supporting Records 表达，不能塞进普通知识关系或一个含糊的 `open / closed` 状态。

## 0.2 本轮冻结的五十项产品决定

1. **未知本身可以成为知识。** 当用户认为某个未知值得长期保留时，它应成为 Question Knowledge，而不是消失在一次 Ask 的结尾。
2. **不是每个检索缺口都自动成为 Question Knowledge。** 运行时 Unknown、临时提示和低价值缺口默认随 Query Run 保存；只有用户显式保存或直接创作，才进入 Library。
3. **Question Knowledge 是 Primary Knowledge Resource。** 它具有稳定 `knowledge_id`、Current Revision、Placements、Sources、History 与可导出身份。
4. **Question 不是任务。** 它可以没有截止日、负责人、完成压力或下一行动；若用户需要行动管理，应链接到独立 Task / Decision 系统，而不是让知识库退化为 Inbox。
5. **Question 不是 Query Turn。** Query Turn 是一次提问行为；Question Knowledge 是可跨多次查询、阅读和修订持续存在的知识对象。
6. **Question 不是 Answer。** AI 输出、来源回答、用户笔记与既有 Knowledge 都只是候选或回答依据；它们不会因为“看起来回答了”而取得 Question 的当前求解状态。
7. **Question 不是 Conflict。** Conflict 保存相互不兼容的当前主张；只有当用户要持续调查冲突时，才创建或链接 Question Knowledge。
8. **Question 不是 Source Annotation。** 对某个片段的“质疑”可以先是 Annotation；只有显式提升后，才获得 Question identity。
9. **Question 不是普通 Relation。** “关于 X 不确定”使用 `QuestionTargetReference`；“重新打开”使用 `QuestionLifecycleEvent`，都不进入 ordinary relation registry。
10. **Question 可以同时拥有普通 Knowledge Relations。** 只有当两个 Knowledge 之间存在独立、稳定、可陈述的语义时才建立；“Q 关于 K”本身不满足该门槛。
11. **问题表述有版本。** 改写措辞、增加背景、收窄 Applicability、补充求解标准或目标，形成新的 Question revision，历史不可覆盖。
12. **问题身份由核心求知意图决定。** 只要核心未知、适用范围与判定标准仍可连续理解，就保留同一 identity。
13. **问题发生实质改变时建立 successor。** 若新表述需要另一套答案、另一组判定标准或改变决策后果，不能偷偷把旧 Question 改成新问题。
14. **复杂问题可以拆成 Subquestions。** 拆解顺序、必需性与汇总规则由 `QuestionSubquestionReference` 保存；它不是目录层级，也不自动成为正式 Relation。
15. **父问题不会因一个子问题回答而自动解决。** 只有全部 required criteria 满足、被明确豁免或不再适用，父问题才可标记充分回答。
16. **目标引用支持多对象、多角色。** Question 可以指向 Group、Topic、Knowledge、Anchor、Relation Revision、Property Assertion、Source / Fragment 或 Decision context。
17. **Question 可以暂时没有目标。** 一个独立问题可以未归类保存，之后再放入 Group / Topic 或增加 targets。
18. **目标状态与 Question 状态分开。** 某个 target 已处理、已移动或不可用，不等于 Question 已回答、已关闭或无效。
19. **求解程度使用独立轴。** 内部值为 `unresolved / partially_resolved / provisionally_resolved / resolved`。
20. **继续意愿使用独立轴。** 内部值为 `active / paused / concluded`；它回答“我现在还要不要追”，不回答“知识上是否已有答案”。
21. **变化提醒使用独立轴。** 内部值为 `no_material_change / changes_available / review_due`；它回答“已有依据后来是否发生值得复核的变化”。
22. **Library 存续状态继续独立。** `current / archived / trash` 不与求解程度、继续意愿或变化提醒混用。
23. **“已有部分进展”只表示部分必需标准有依据。** 一段长回答、很多引用或模型高置信度都不能替代 criterion-level 判断。
24. **“暂时可用”表示当前目的下可采用，但有明确保留条件。** 必须记录未完成验证、依赖、有效期或剩余未知；它不是模糊的低置信度标签。
25. **“已充分回答”是有范围的采用决定，不是永恒真理。** 它只对某一 Question revision、Applicability、resolution criteria 与所采用依据成立。
26. **“停止追问”不等于“已充分回答”。** 用户可以因为不再相关、问题无效、已有 successor、主动放弃或当前不可回答而结束追问。
27. **“已充分回答”也不强制停止追问。** 用户可以保留已采用的当前回答，同时继续寻找更强证据、替代解释或后续变化。
28. **结论理由必须显式。** `concluded + unresolved / partial / provisional` 必须带 closure reason；`duplicate_or_successor` 必须指向目标 Question。
29. **暂停与结束不同。** 等待资料、等待时间窗口或暂时无精力使用 `paused`；只有明确不再继续当前求解时使用 `concluded`。
30. **AI 永不自动把 Question 标为充分回答、结束追问或重新打开。** AI 可以提议状态、说明 criteria coverage 和变化影响，最终写入必须由用户确认。
31. **Answer Snapshot 只保存一次回答。** “保存回答”不会改变 Question resolution、pursuit、targets、Knowledge 或 Overview。
32. **链接既有 Knowledge 只增加回答依据。** 它可以形成 Resolution Proposal，但不会自动表示采用或充分回答。
33. **从 Answer 形成 Knowledge 与采纳当前回答是两个动作。** 前者写入长期 Knowledge；后者创建 `QuestionResolutionRevision`，不能用一个模糊按钮同时完成。
34. **“采纳为当前回答”与“结束追问”是两个原子后果。** 可以提供明确的组合动作，但必须在提交前展示两项后果并分别可撤销。
35. **当前回答由 Resolution Revision 固定，而不是复制一份影子正文。** 它引用精确 Knowledge revisions / anchors、Relation revisions、Evidence bindings、criteria 结果与剩余未知。
36. **Question 本身也可以承载工作回答。** 用户直接写在 Question 正文中的解释可以成为 answer basis，但 Resolution Revision 必须指向该 Question revision 的准确 Anchor。
37. **候选回答可以并存。** Suggested Answer、外部来源回答、用户假设和 AI synthesis 可以同时存在；只有显式 adopted resolution 是当前采用答案。
38. **采纳不等于事实认证。** Resolution 记录“用户在何种范围内采用哪套回答”，不会把所有引用内容升级为已证实事实。
39. **运行时 Unknown 使用原因分类。** 至少区分无相关知识、证据不足、范围过窄、适用条件缺失、来源不可用、索引不完整、历史缺口、外部资料关闭、未决冲突和需要用户判断。
40. **“不知道值是什么”与“知道不存在该值”必须分开。** Unknown、No Value、Not Applicable、Not Yet Known 与 Not Searched 不能共用空字段。
41. **Persistent Gap Marker 只是局部缺口标记。** 它可以贴在 Knowledge / Anchor / Property / Relation 上；当它已有完整问题、重要性和求解标准时，应提升为 Question Knowledge。
42. **目标或依据变化不会静默改写 Resolution。** 系统标记 `changes_available` 或 `review_due`，展示受影响 criteria；原 adopted resolution 与历史保持可读。
43. **依据过期不会直接删除当前回答。** 在复核前仍显示“曾被采用，但现在需要检查”，Ask 不得把它无警告地当作当前可靠结论。
44. **重新打开是生命周期事件。** 它保留前一次关闭理由、Resolution Revision 与当时依据，并记录本次重开原因。
45. **重开不必自动降级求解程度。** 若只是继续优化，resolved 可以保持；若某个 criterion 被新证据推翻，用户确认新的 Resolution Revision 后再改为 partial / provisional / unresolved。
46. **实质不同的问题使用 successor，而不是滥用 reopen。** Reopen 恢复同一求知意图；successor 建立新的求知意图并保持可追溯过渡。
47. **Overview 可以展示重要开放问题，但不能把运行时 Unknown 倾倒成维护清单。** 只展示用户保存、与当前范围相关且有解释价值的 Question Knowledge。
48. **Search 与 Library 必须能按真实问题状态找回。** 用户可以筛选正在追问、已暂停、已有部分进展、暂时可用、已充分回答、需要复核和停止追问。
49. **Network 中 Question 的“问题身份”和“目标引用”必须可辨。** Question 仍是 Knowledge node；target references 使用独立图层、完整文本标签和 List Equivalent，不冒充正式关系边。
50. **本合同不授权开始原型。** 下一轮视觉工作必须先证明这些状态、动作与返回语义，而不是先画一张好看的问题看板或聊天页。

## 0.3 真实端到端夹具补充的六项约束

1. **高后果 Resolution 的 Applicability 必须是快照，不是自由文本尾注。** 至少固定 `as_of`、地域 / 制度、决策时间、主体条件、依据规则、假设、排除项与是否仍待机构决定。
2. **个人情境输入默认不是普通 Knowledge。** 它可以只属于 Query Run 或 Question Applicability；跨问题复用必须来自用户显式保存、可修订的 Profile / Property Assertion。
3. **来源陈述、情境推断与操作结果分层。** “规则写了什么”“按给定条件可推断什么”“主管机构已经怎样决定”不能由一段 AI 口吻抹平成一个 standing。
4. **变化触发器是可检查对象。** 时间到达、来源语义变化、target / basis 变化、个人情境变化、Applicability 变化、依据不可访问和人工复核具有不同原因与影响范围。
5. **新 Source 或 Source Revision 只产生变化候选。** 它必须先检查 materiality 和受影响 criteria，不能自动重写 Knowledge、Resolution 或 pursuit。
6. **同一核心问题中的条件变化优先保留 identity。** 只有答案类别、核心时间 / 人群或判定标准已实质变化时才建立 successor；普通 Applicability 改变形成 Question revision + review。

## 0.4 第二真实夹具补充的五项约束

1. **Decision-facing Applicability 不只表达“适用于谁”。** 它还可表达 decision objective、desired outcome horizon、assessment / transfer target、material type 与 effort / time constraints；这些字段只在会改变答案时出现。
2. **Subquestion rollup 由 criterion mapping 决定。** required / optional / diagnostic 角色与 `evidence_only / criterion_contribution / blocking_requirement`共同决定父问题状态，禁止按已回答数量投票。
3. **`provisionally_resolved + active`是合法且重要的组合。** 当前回答可以足够指导一版策略，同时保留课程条件、实际结果或替代解释作为 remaining unknowns。
4. **方法学评论只复核真正受影响的 criterion。** Evidence challenge 不会因共用一个 Source、Topic 或关键词而把 parent 全部重开。
5. **目标结果实质变化可能建立 successor。** 从“八周后的闭卷保持与迁移”改成“下周开卷查找速度”时，答案类型和 criteria 已改变；不能只更新 Applicability 后继续冒用旧 Resolution。

---

# 1. 为什么“未知”必须有自己的产品位置

## 1.1 个人知识库不仅保存答案

成熟理解至少包含四种东西：

- 我目前采用什么；
- 我依据什么采用；
- 哪些解释互相冲突；
- 我仍然不知道什么，以及怎样才算知道。

如果产品只保存肯定句，用户就会被迫把问题写成假结论、放进聊天历史或记成任务。三种做法都会损失知识结构：假结论污染 Ask；聊天不可持续；任务只记录要做什么，无法表达问题怎样被逐步回答。

## 1.2 一次 Ask 失败不应制造无限债务

反过来，如果每次“未找到”都自动生成 Question，Library 很快会变成 AI 失败日志。产品必须区分：

1. 本次执行为什么没有回答；
2. 当前对象哪里存在一个局部缺口；
3. 用户是否认为这个未知值得成为长期知识。

只有第 3 项天然属于 Primary Knowledge。

## 1.3 问题的价值来自可持续求解

Question Knowledge 的价值不是一个问号图标，而是连续性：

- 下次 Ask 知道原问题、原范围和原 targets；
- 新资料知道自己填补了哪个 criterion；
- 用户能区分候选答案、当前采用答案与剩余未知；
- 目标或依据变化时，产品知道应提醒复核什么；
- 停止追问、重新打开或建立 successor 时，历史不丢失。

---

# 2. 对象边界：六种看起来像“问题”的东西

| 对象 | 它回答什么 | 是否进入 Library | 是否有稳定 identity | 默认生命周期 |
|---|---|---:|---:|---|
| Query Turn | 用户这一次问了什么 | 否 | 有 Supporting Record identity | 随 Ask history 保存 |
| Runtime Unknown | 这次 Run 为什么不能充分回答 | 否 | 属于 Run | 不自动产生工作债务 |
| Source Annotation: questioning | 用户在质疑哪个来源片段 | 否 | 有 Annotation identity | 随 Source / Target 保存 |
| Persistent Gap Marker | 某个对象的哪个局部信息仍缺 | 否 | 有 Supporting Record identity | 可解决、撤销或提升 |
| Conflict | 哪些当前主张相互不兼容 | 条件性；作为治理对象出现 | 有独立 identity | open / managed / retired |
| Question Knowledge | 哪个未知值得长期求解 | 是 | 有 Knowledge identity | 本合同的四轴状态 |

## 2.1 Query Turn

Query Turn 保存原始问题、解析后的 scope request、用户当时的焦点与后续分支。它可以被保存为 Question Knowledge，但保存前两者仍是不同对象：

- 同一个 Question 可以产生很多 Query Turns；
- 一个 Query Turn 可以临时询问而永不进入 Library；
- 保存时必须预览问题表述、Context、Placement 和 targets，不能只复制聊天文本。

## 2.2 Runtime Unknown

Runtime Unknown 是 Answer 的诚实组成部分：

```text
RuntimeUnknown
  query_run_ref
  affected_claim_ref?
  unknown_reason
  missing_scope_or_input?
  searched_scope_receipt
  consequence_for_answer
  possible_next_step?
```

它解释“这次为什么不知道”，不是“用户以后必须处理什么”。用户可以：

- 忽略；
- 改 Scope 后重试；
- 补充资料；
- 保存为 Question Knowledge；
- 附着为 Persistent Gap Marker。

## 2.3 Source Annotation: questioning

Annotation 适合表达“我质疑这一段”“这里需要核验”。它保持对精确 Source Fragment 的定位，但没有完整 Question frame。提升时创建 Question Knowledge，并保留 Annotation 作为 origin reference；两者不合并 identity。

## 2.4 Persistent Gap Marker

Gap Marker 是低负担的局部记号：

```text
PersistentGapMarker
  gap_id
  target_ref
  gap_kind
    unknown_value
    missing_explanation
    missing_evidence
    unresolved_conflict
    applicability_missing
    not_yet_investigated
  note?
  created_by
  created_at
  standing
    open
    addressed
    dismissed
    promoted_to_question
  successor_question_ref?
```

它没有独立 Overview、Placements 或 Resolution criteria。只要用户开始表达“究竟要回答什么、为什么重要、怎样算回答”，产品就应建议提升为 Question Knowledge。

## 2.5 Conflict

Conflict 是对 incompatibility 的治理，不是一个问句。它可以由多个 Knowledge claims、Relation revisions 或 Source statements 构成。Question 可以把 Conflict 作为 `investigates_conflict` target；Conflict 被消解不自动解决 Question，因为 Question 可能还要求解释原因、适用范围或决策后果。

## 2.6 Question Knowledge

Question Knowledge 与其他 Knowledge 共享：

- stable `knowledge_id`；
- Current Revision 与 History；
- Group / Topic Placements；
- readable content tree 与 Anchors；
- Sources、Evidence、Properties、Facets；
- Search、Ask、Overview 和 Network 可达性；
- local-first 存储、导出与恢复。

它额外拥有 Question-specific Supporting Records，但这些记录不会变成新的日常顶级对象。

---

# 3. Question Knowledge 的内容合同

## 3.1 用户看到的最小正文

一个 Question 首屏只需要四件事：

1. **问题**：当前要弄清什么；
2. **为什么重要 / 适用范围**：它对什么情境和目的成立；
3. **目前知道什么**：当前回答、候选解释或已有依据；
4. **还差什么**：剩余未知、求解标准与下一条可选路径。

目标、子问题、来源、回答历史、状态历史和机器细节按需展开。

## 3.2 QuestionFrameRevision

```text
QuestionFrameRevision
  frame_revision_id
  question_knowledge_ref
  knowledge_revision_ref
  interrogative_statement
  context
  why_it_matters?
  applicability
    decision_objective?
    desired_outcome_horizon?
    assessment_or_transfer_target?
    material_or_domain?
    effort_or_time_constraints?
  assumptions[]
  excluded_interpretations[]
  question_kind?
  created_by
  created_at
  predecessor_revision_ref?
```

`QuestionFrameRevision` 是 Question Knowledge revision 的语义投影，不是第二份正文。正文仍是 canonical content tree；frame 指向其中准确 Anchors 或保存结构化字段，用于 Ask、Search、Overview 和 Resolution 检查。

## 3.3 可选 question_kind

`question_kind` 只帮助写作与 criteria 建议，不创造不同对象类型：

- factual：某个事实或值是什么；
- explanatory：为什么、怎样发生；
- comparative：两个或多个对象怎样不同；
- evaluative：在明确标准下如何判断；
- procedural：怎样完成或复现；
- predictive：在什么假设下可能发生什么；
- decision-facing：为了一个决定需要知道什么；
- exploratory：当前仍在界定问题空间。

用户不必先选类型。AI 可以建议，但不能因类型预测改变 lifecycle。

## 3.4 问题写作质量

一个高质量 Question 不要求格式齐全，但产品应能逐渐补清：

- 问的是哪一个可辨别的未知；
- 适用于谁、什么场景、什么时间；
- 哪些词可能有歧义；
- 怎样的证据或解释才足够；
- 哪些内容明确不在本问题内；
- 回答后会改变哪种理解或决定。

AI 的作用是指出缺口和提供草稿，不是阻止用户先保存一个不完整问题。

---

# 4. 身份、修订、拆分与 successor

## 4.1 保留同一 identity 的变化

以下通常形成同一 Question 的新 revision：

- 更清楚地改写同一未知；
- 补充 Context、why it matters 或 Applicability；
- 增加、删除或修订 resolution criteria；
- 增加目标、来源、假设或 excluded interpretation；
- 把宽泛时间范围收窄到原问题可兼容的范围；
- 修正措辞，但旧答案仍能被解释为对同一问题的尝试。

## 4.2 必须新建 identity 的变化

出现任一条件，默认建立 successor Question：

- 新表述需要不同类别的答案；
- 原有 Resolution 无法合理映射到新 criteria；
- 决策对象、适用人群或核心时间范围发生改变；
- 问题从“是什么”变为“应不应该”，或反之；
- 旧问题仍可独立回答，新问题并未取代它；
- 合并两个 Questions 会隐藏各自不同的未决部分。

## 4.3 QuestionIdentityTransition

```text
QuestionIdentityTransition
  transition_id
  predecessor_question_refs[]
  successor_question_refs[]
  transition_kind
    reframed_as_successor
    split
    merged
    duplicate_of
    scope_fork
  rationale
  criterion_mapping[]
  target_mapping[]
  created_by
  created_at
```

这不是 `supersedes` ordinary Relation。旧 Question 保持可读，并说明当前应前往哪个 successor。

## 4.4 Subquestions

```text
QuestionSubquestionReferenceRevision
  parent_question_revision_ref
  child_question_ref
  role
    required
    optional
    alternative_path
    diagnostic
  order?
  parent_criterion_refs[]
  rollup_policy
    evidence_only
    criterion_contribution
    blocking_requirement
  standing
  created_at
```

Subquestion 可以放在不同 Topic，也可以独立被 Ask、解决或暂停。父问题页面只投影其状态，不复制正文。

---

# 5. QuestionTargetReference：问题“关于什么”

## 5.1 版本化对象

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

## 5.2 为什么它不是 Relation

普通 Knowledge Relation 回答“A 与 B 之间长期成立什么语义”；QuestionTargetReference 回答“这个问题当前把哪个对象的哪一部分当作求解对象”。后者随问题 frame、目标 revision 和求解状态变化，且不应该被 Network 的 ordinary relation filters、relation counts 或群级聚合读取。

## 5.3 多目标

一个 Question 可以同时：

- 以 Group 作为范围；
- 对某个 Knowledge Anchor 寻找解释；
- 质疑一条 Relation Revision；
- 寻找某项 Property Assertion 的证据；
- 为一条 Decision Knowledge 提供输入。

界面默认按 role 分组，而不是显示一串无差别链接。

## 5.4 目标变更

- Anchor redirected：Reference revision 跟随可解释重定位，保留旧指向；
- target successor：显示建议切换，用户确认后创建新 Reference revision；
- target archived：仍可读取，不自动结束；
- target trash / unavailable：显示历史与影响，不删除 Question；
- Relation retracted：标记 affected criterion 和 `changes_available`，不自动重开或降级。

---

# 6. Resolution Criteria：怎样才算回答

## 6.1 Criterion 模型

```text
QuestionResolutionCriterionRevision
  criterion_id
  question_revision_ref
  statement
  requiredness
    required
    optional
  evaluation_kind
    factual_value
    causal_explanation
    comparison_dimension
    evidence_threshold
    applicability_check
    reproducible_procedure
    decision_input
    user_judgment
  acceptance_condition
  allowed_uncertainty?
  validity_window?
  standing
  predecessor_revision_ref?
```

## 6.2 Criteria 不应变成表单负担

默认界面只显示自然语言的“怎样算回答”。简单事实问题可以只有一个 implicit criterion；高后果问题、比较问题或 decision-facing question 才逐步展开多个标准。用户可以直接标记充分回答，但系统必须先显示当前依据、适用范围和仍未满足的 required criteria。

## 6.3 Criterion result

每个 adopted Resolution 对每项 criterion 固定：

- `unmet`：没有可用依据；
- `partially_met`：只覆盖一部分；
- `provisionally_met`：当前可用，但有明确保留条件；
- `met`：在当前 Applicability 下满足；
- `waived`：用户明确不再要求，保留理由；
- `no_longer_applicable`：Question revision 改变后不再适用。

## 6.4 Partial 与 Provisional 的边界

| 状态 | 核心含义 | 必须展示 |
|---|---|---|
| partially_resolved | 还有 required criteria 没有达到当前可用程度 | 已覆盖部分、缺失标准、后果 |
| provisionally_resolved | required criteria 对当前目的已暂时可用，但存在验证、期限或依赖保留 | 保留条件、review trigger、剩余未知 |
| resolved | required criteria 在当前 Applicability 下被用户判断充分满足 | adopted basis、范围、采用时间 |

“不确定但先用”不是 partial；它是 provisional，必须说清为什么可以先用、什么变化会触发复核。

---

# 7. 四轴生命周期

## 7.1 求解程度 `resolution_state`

| 内部值 | 默认人话 | 含义 |
|---|---|---|
| unresolved | 尚未回答 | 没有 adopted resolution，或 required criteria 基本未满足 |
| partially_resolved | 已有部分进展 | 有 adopted resolution，但仍有 required criteria 未满足 |
| provisionally_resolved | 暂时可用 | 当前可采用，但有明确保留条件或复核点 |
| resolved | 已充分回答 | 在声明的范围与标准下已被用户采纳为充分 |

## 7.2 继续意愿 `pursuit_state`

| 内部值 | 默认人话 | 含义 |
|---|---|---|
| active | 正在追问 | 用户仍希望继续寻找、比较或复核 |
| paused | 暂停追问 | 以后可能继续；可带等待条件或复核日期 |
| concluded | 已停止追问 | 当前 Question pursuit 明确结束，必须保留理由 |

## 7.3 变化提醒 `change_state`

| 内部值 | 默认人话 | 含义 |
|---|---|---|
| no_material_change | 无需复核 | 当前未检测到影响 adopted basis 的变化 |
| changes_available | 依据有变化 | targets、Knowledge、Relations、Sources 或 criteria 出现相关新变化 |
| review_due | 需要复核 | 到达 validity / review trigger，或关键依据当前不可核验 |

## 7.4 Library 存续 `library_state`

| 内部值 | 默认人话 | 含义 |
|---|---|---|
| current | 当前知识 | 正常参与 Library 与默认找回 |
| archived | 已归档 | 保留但退出默认当前范围 |
| trash | 回收站 | 等待恢复或永久删除 |

## 7.5 允许组合

四轴不压成一个状态。以下组合都合法：

- `resolved + active`：已有当前答案，但继续寻找更强解释；
- `unresolved + concluded`：问题没有答案，但已不再追问；
- `provisionally_resolved + paused + review_due`：暂时可用，暂停到复核日期；
- `resolved + concluded + changes_available`：过去已回答并结束，但后来出现变化；
- `partially_resolved + active + archived`：历史 Question 被归档，但仍可通过显式范围继续研究。

系统只在必要处要求理由，不把合法现实压成单一路线。

## 7.6 conclusion reasons

`pursuit_state = concluded` 必须记录：

- `sufficiently_answered`；
- `no_longer_relevant`；
- `invalid_question`；
- `duplicate_or_successor`；
- `intentionally_abandoned`；
- `currently_unanswerable`。

若 reason 为 `sufficiently_answered`，必须存在 `resolved` Resolution Revision。其他 reason 不允许悄悄把 resolution_state 改为 resolved。

---

# 8. 候选回答、当前回答与采用记录

## 8.1 五层回答 standing

1. **Raw material**：Source、Fragment、用户输入；
2. **Answer candidate**：AI Answer Snapshot、他人答案、用户假设；
3. **Answer basis**：被链接到某个 criterion 的 Knowledge / Anchor / Relation / Evidence；
4. **Adopted resolution**：用户采纳的 current QuestionResolutionRevision；
5. **Historical resolution**：被后来 revision 取代，但仍可按当时范围回读。

任何层级都不能因“更靠后”而改变来源本身的 truth standing。

## 8.2 QuestionResolutionProposal

AI、用户链接或新来源可以形成 Proposal：

```text
QuestionResolutionProposal
  proposal_id
  question_revision_ref
  proposed_resolution_summary
  proposed_basis_refs[]
  criterion_assessments[]
  remaining_unknowns[]
  proposed_resolution_state
  proposed_review_trigger?
  origin
    query_run
    manual_link
    source_update
    knowledge_revision
  standing
    suggested
    inspected
    accepted
    dismissed
```

Proposal 不进入默认 Ask truth，不改变 Question header，也不触发 Overview “已回答”。

## 8.3 QuestionResolutionRevision

```text
QuestionResolutionRevision
  resolution_revision_id
  question_revision_ref
  resolution_summary
  resolution_anchor_ref?
  answer_basis_refs[]
    object_ref
    exact_revision_or_anchor_ref
    role
      direct_answer
      supporting_reason
      counterpoint
      applicability
      limitation
  relation_revision_refs[]
  evidence_binding_refs[]
  criterion_results[]
  remaining_unknowns[]
  resolution_state
  applicability_snapshot
    as_of
    jurisdiction?
    decision_period?
    subject_context_refs_or_inline_inputs[]
    governing_rule_refs[]
    assumptions[]
    exclusions[]
    operational_decision_pending
  validity_window?
  review_triggers[]
  adopted_by
  adopted_at
  predecessor_resolution_revision_ref?
```

Resolution Revision 是一份采用与依据记录，不是第二条 Answer Knowledge。用户打开 Question 时，系统将它投影成“当前回答”，并允许继续进入原 Knowledge、准确 Anchor 和 Evidence。

内联主体条件只在本 Question / Resolution 范围内有 standing；它不会因被保存进 Applicability Snapshot 就升级为全局个人 Knowledge。若引用 Profile / Property Assertion，必须固定 exact revision，后续 Profile 更新只触发 review，不反向改变旧 Snapshot。

## 8.4 ReviewTrigger

```text
ReviewTrigger
  trigger_id
  trigger_kind
    time_reached
    source_revision_material
    target_or_basis_changed
    subject_context_changed
    applicability_changed
    basis_unavailable
    manual_review_requested
  condition_or_ref
  affected_criterion_refs[]
  standing
    armed
    fired
    dismissed
    satisfied
  fired_at?
  rationale?
```

Trigger 只回答“为什么现在值得复核”。它不决定新旧答案谁正确，也不直接改变 `resolution_state` 或 `pursuit_state`。Source 页面排版、locator 或无语义内容变化只形成 Source Revision，不应触发 `source_revision_material`。

## 8.5 原子动作

| 用户动作 | 写入什么 | 不写入什么 |
|---|---|---|
| 保存这次回答 | Answer Snapshot | Question state、Knowledge、Relation |
| 链接为回答依据 | basis link / Proposal | adopted resolution |
| 从回答形成知识 | Knowledge Draft / Current Revision，取决于明确编辑合同 | Resolution、停止追问 |
| 采纳为当前回答 | QuestionResolutionRevision | pursuit_state |
| 标记已充分回答 | resolved Resolution Revision | pursuit_state，除非用户另选组合动作 |
| 暂停追问 | QuestionLifecycleEvent | resolution_state |
| 结束追问 | QuestionLifecycleEvent + reason | resolution_state，除非显式组合 |

按钮文案必须预告后果。禁止使用“完成”“保存”“接受”同时暗含多种写入。

---

# 9. Ask 与 Question-first 工作流

## 9.1 从空 Library 开始

空 Library 允许先问。系统必须说清“当前没有个人知识可供查询”，并提供：

- 保存为 Question；
- 加入资料；
- 写下已有理解；
- 本次允许外部资料；
- 返回 Library。

保存 Question 时原问题进入 QuestionFrame draft；用户可选 Group / Topic，也可暂时未归类。外部回答不会自动成为个人知识。

## 9.2 从 Question 打开 Ask

默认 Requested Context 包含：

- current Question revision；
- current targets；
- adopted resolution 与历史 basis 的状态；
- required criteria；
- 用户显式选择的 Group / Topic expansion；
- 允许的 Sources / external policy。

提交前用人话显示范围，例如：`正在查询这个问题、它指向的 3 条知识，以及“签证政策”知识群；外部资料关闭。`

## 9.3 Answer 的 Question-aware 结构

默认回答顺序：

1. 直接回答；
2. 当前能覆盖哪些 criteria；
3. 仍不知道什么；
4. 依据与适用范围；
5. 可选动作。

只有存在真实价值时才显示“更新当前回答”“形成知识”“增加目标”“拆成子问题”。不能每次都生成维护 CTA。

对于资格、规则、医疗、法律、财务或其他高后果 Question，Answer 还必须在需要时分清：

- `source_statement`：官方 / 原始来源明确声明什么；
- `contextual_inference`：结合当前 Applicability 输入可推断什么；
- `operational_outcome`：是否已有机构、系统或真实事件的决定；
- `remaining_verification`：仍需什么资料、模拟或正式处理。

这不是四个常驻卡片，而是 Claim standing 纪律。没有 operational outcome 时，禁止用“已获批”“已经不符合”“系统会接受”等完成态措辞。

## 9.4 Unknown 的提升

从 Runtime Unknown 保存为 Question 时，预览：

- 原问题与系统识别出的未知；
- 为什么这次没回答；
- 当前 Scope；
- 建议 targets；
- 是否与既有 Question 重复；
- 保存位置。

用户确认后创建 Question Knowledge；Runtime Unknown 仍保留在原 Run 作为 origin，不被搬走或删除。

## 9.5 追问

普通 follow-up 创建新 Query Turn / Run，不自动改变 Question revision。只有追问实质修订问题、criteria 或 targets 时，系统提出可检查的 Question Change Set。

## 9.6 外部研究

外部来源可以：

- 支撑本次 Answer Claim；
- 保存为 Source；
- 形成新的 Knowledge；
- 提议 Resolution basis。

它不能直接把 Question 变成 resolved。采纳时必须说明个人知识、外部来源与 AI inference 各自扮演什么角色。

---

# 10. 关闭、暂停、重新打开与复核

## 10.1 QuestionLifecycleEvent

```text
QuestionLifecycleEvent
  event_id
  question_ref
  event_type
    created
    pursuit_activated
    pursuit_paused
    pursuit_concluded
    reopened
    resolution_adopted
    resolution_revised
    applicability_context_changed
    changes_detected
    review_due
    successor_created
    archived
    restored
  from_state_snapshot
  to_state_snapshot
  reason
  affected_resolution_revision_ref?
  affected_criterion_refs[]
  actor
  occurred_at
```

## 10.2 结束追问

提交前显示：

- 当前 resolution_state；
- 结束理由；
- 是否保留已设置的 review trigger；
- 是否继续允许 Overview 展示；
- 是否有 successor / duplicate target；
- 对默认 Ask 的影响。

结束不会归档、删除或取消 Knowledge identity。

## 10.3 重新打开

重新打开需要一个简短 reason：

- 新证据；
- 旧依据失效；
- 适用范围改变；
- 决策重新出现；
- 希望继续优化；
- 误操作恢复。

Reopen 只把 pursuit_state 变为 active。若要改变 resolution_state，必须同时检查受影响 criteria 并形成新 Resolution Revision；历史 resolution 不覆盖。

## 10.4 changes_available 与 review_due

系统可以自动写入 change event，但不能自动判断新内容已推翻旧答案。Question 页面显示：

- 哪个 basis / target 变了；
- 哪些 criteria 可能受影响；
- 上次 adopted resolution 的范围和时间；
- `查看变化`、`暂不处理`、`开始复核`。

“开始复核”可以把 pursuit 切到 active，但必须由用户触发。

变化评估必须记录 trigger kind、旧 / 新 Applicability 差异、受影响 criteria 与 materiality。若只有一个主体条件改变，只标记真正依赖它的 criteria；其他 criteria 不因“整个问题有变化”被整体降级。旧 Resolution 继续按原 `as_of` 与 subject snapshot 解释。

## 10.5 successor

若变化实质产生新问题，使用“建立后续问题”：

- 新 Question 拥有新 identity；
- 旧 Question 可以 concluded，reason 为 `duplicate_or_successor` 或继续保留；
- criteria、targets 与 basis 只按可解释映射复制；
- History 显示过渡，不建立 `reopens` / `supersedes` ordinary edge。

---

# 11. 与产品表面的整合

## 11.1 Library

Question 与其他 Knowledge 混合存在，不建立第二个“问题中心”作为默认首页。用户可以建立动态视图：

- 正在追问；
- 已暂停；
- 已有部分进展；
- 暂时可用；
- 已充分回答；
- 需要复核；
- 已停止追问。

视图是 filter，不改变对象归属或 identity。

## 11.2 Group / Topic Overview

Overview 只在以下情况展示 Question：

- 用户显式置顶或纳入 Editorial Overview；
- 它是理解当前 Group / Topic 的关键开放问题；
- 当前阅读路径需要它解释边界、争议或下一层入口。

默认分为“关键问题”“当前回答”“仍未解决”，但不按未处理数量制造红点或完成率。

## 11.3 Search

Search index 至少包含：

- current / historical question statement；
- Context、Applicability、targets；
- current resolution summary；
- remaining unknowns；
- pursuit / resolution / change state；
- Group / Topic Placements。

命中 historical wording 时，结果必须说明“这是旧问题表述”，打开后落到 Current Question 并可查看命中 revision。

## 11.4 Explore / Network

Question 是可选择的 Knowledge node，显示问号 badge 与文字状态。选择后可展开：

- ordinary Knowledge Relations；
- Question Target layer；
- answer basis layer；
- subquestion layer。

四层不能混成一种 edge。List Equivalent 使用分组标题和完整关系句；关闭 layer 后 resting graph 恢复。

## 11.5 Knowledge Reader

Question Workspace 仍沿方向 3 的层级阅读：

1. 问题与 Context；
2. 当前回答；
3. criteria 与 remaining unknowns；
4. targets / subquestions；
5. answer basis / sources；
6. previous resolutions / lifecycle history。

右侧 Companion 使用方向 2 的关系空间，但默认只显示与当前段落或当前回答相关的少量连接。

## 11.6 History

History 以事件语言呈现：

- 问题表述怎样改变；
- 哪个回答在何时被采纳；
- 哪些 criteria 改变；
- 为什么暂停、停止或重开；
- 哪个依据后来发生变化；
- 是否建立 successor。

不能只显示 JSON diff，也不能把 AI 建议写成用户决定。

---

# 12. 语言与渐进披露

## 12.1 P0 日常语言

| 概念 | 默认文案 | 禁止默认文案 |
|---|---|---|
| unresolved | 尚未回答 | open state |
| partially_resolved | 已有部分进展 | 50% complete |
| provisionally_resolved | 暂时可用 | confidence 0.72 |
| resolved | 已充分回答 | truth verified |
| active | 正在追问 | active workflow |
| paused | 暂停追问 | snoozed ticket |
| concluded | 已停止追问 | closed / done |
| changes_available | 依据有变化 | stale object |
| review_due | 需要复核 | failed validation |
| target reference | 这个问题指向 | uncertain_about edge |

## 12.2 状态句必须组合表达

不要只显示一个“Closed”徽章。使用：

- `已充分回答 · 仍在继续研究`；
- `已有部分进展 · 暂停追问`；
- `尚未回答 · 已停止追问（目前不可回答）`；
- `暂时可用 · 需要在 9 月复核`；
- `已充分回答 · 依据后来有变化`。

P0 最多显示一个主状态句；其他轴在 Inspector 展开，但不可因此丢失语义。

## 12.3 禁止的诱导语言

- “AI 已解决”；
- “还有 7 个问题待完成”；
- “一键关闭全部”；
- “置信度达到阈值，自动完成”；
- “未找到，因此不存在”；
- “接受答案”但不说明写入 Question 还是 Knowledge；
- “重新打开关系”；
- “问题完成率”。

---

# 13. 失败、离线、同步与恢复

## 13.1 AI unavailable

用户仍可：

- 创建、编辑、放置与阅读 Question；
- 链接 targets、Knowledge 与 Sources；
- 手工写工作回答；
- 采纳 Resolution；
- 暂停、结束和重开；
- 搜索、导出和恢复。

只有生成、候选比较、自动 criteria 建议和变化影响摘要不可用。

## 13.2 Index partial

Question Ask 可以给 partial answer，但必须保留 Coverage receipt。`没有找到新依据`只能表示“在当前已覆盖范围未找到”，不能自动生成 `currently_unanswerable` closure。

## 13.3 同步冲突

若两台设备分别修改 Question frame、criteria 或 Resolution：

- body edit 走普通 Knowledge conflict 机制；
- Resolution adoption 不使用不可见 last-write-wins；
- 系统保留两个 proposal / revision，要求用户选择、合并或保留分支；
- pursuit state 的并发变化保留两个 events，并展示时间和 actor；
- 已成功本地提交的 Question 不因派生索引失败回滚。

## 13.4 删除与恢复

删除 Question 进入 Trash；其 Query Runs、Answer Snapshots、Targets、Resolution revisions 与 lifecycle history 保留可恢复 linkage。被其他 Knowledge 正式 Relation、Overview 或 Decision 引用时显示 Impact Preview，但不因引用存在禁止删除。

## 13.5 导出

可重建导出必须包含：

- Question Knowledge 与所有 revisions；
- QuestionFrame、Criteria、Targets、Subquestions；
- Proposals 与 Resolution revisions；
- lifecycle events 与四轴当前状态；
- linked Query Turns / Runs / Answer Snapshots；
- basis、Evidence、Sources、Relations 与 Anchors；
- identity transitions、Placements 与 returnable paths。

扁平 Markdown 可以作为阅读导出，但不能冒充可恢复备份。

---

# 14. 十八个场景压力测试

## 场景 1：空库问题

用户第一次打开产品直接问一个问题。系统明确个人知识为空，用户选择保存 Question，稍后加入资料；任何外部回答都不自动写成内部知识。

## 场景 2：一次性问题不保存

用户 Ask 后得到答案并关闭。Query history 可恢复，但 Library 没有新增 Question、Knowledge 或待处理事项。

## 场景 3：从 Unknown 提升

一次全库 Ask 因 index partial 无法回答。用户保存其中一个重要未知；新 Question 保留原 scope receipt 和 origin run，但状态仍是尚未回答。

## 场景 4：部分回答

比较问题有四项 required criteria，当前 Knowledge 只覆盖两项。用户采纳现有内容后显示“已有部分进展”，不是“已回答 50%”。

## 场景 5：暂时可用

政策问题在当前日期有足够资料，但官方细则待发布。用户采纳暂时答案，记录验证条件和复核日期；到期后变为“需要复核”，不自动变回尚未回答。

## 场景 6：有答案但继续研究

用户已经充分回答一个解释性问题，但仍想收集替代理论。状态是“已充分回答 · 正在追问”，不会被系统强制结束。

## 场景 7：无答案但停止追问

一个问题因已不相关被结束。它显示“尚未回答 · 已停止追问（不再相关）”，不会伪装成已解决。

## 场景 8：暂停等待资料

用户等待一份报告，把 pursuit 暂停并设置 review trigger。问题仍可被 Search、Overview 和显式 Ask 找到，没有逾期红点。

## 场景 9：候选回答并存

两个来源给出不同解释，AI 又生成综合。三者都作为 candidates / basis 可见，用户尚未采纳时 Question 仍是 unresolved。

## 场景 10：回答写回 Knowledge

用户从 Answer 选中两个 Claims，分别合并进既有 Knowledge 与创建新 Knowledge；Question 不因此自动更新 Resolution，用户随后独立采纳。

## 场景 11：Question 自身承载回答

用户直接在 Question 正文写工作结论，并以该段 Anchor 作为 Resolution basis。系统不要求再创建一条重复 Answer Knowledge。

## 场景 12：Conflict 触发调查

两条 current Knowledge 主张冲突。系统保留 Conflict；用户选择“作为问题调查”后创建 Question 并指向 Conflict，两个 identities 独立。

## 场景 13：Source Annotation 提升

用户质疑 PDF 的一段话。先保存 questioning Annotation；提升为 Question 后保留原 Fragment origin，Annotation 仍可独立处理。

## 场景 14：目标被修订

Question 指向的 Knowledge Anchor 被重写并 redirected。系统显示 target change 和受影响 criterion；不自动改变 adopted resolution 或 pursuit。

## 场景 15：依据失效后复核

一条 adopted Relation 被 retracted。Question 标记“依据有变化”；用户检查后创建新的 partial Resolution revision，再决定是否继续研究。

## 场景 16：真正重开

一个 concluded Question 因新证据重新激活。Reopen event 保存原因、旧 Resolution 和旧 closure；若核心问题未变则 identity 保持。

## 场景 17：建立 successor

问题从“这个方法是否有效”改变为“我是否应该在当前团队采用它”。系统建立 decision-facing successor，不用改写或 reopen 旧 factual / evaluative Question。

## 场景 18：Network 探索与返回

用户在 Local Graph 选择 Question，展开 target layer 和 answer basis，进入 Evidence 后 Back。系统恢复原 Question、layer、selected target、viewport 和 focused control；ordinary relation filters 未被 target references 污染。

---

# 15. 三十二条 Given / When / Then 验收合同

## 验收 1：Query Turn 不自动成为 Question

**Given** 用户完成一次普通 Ask  
**When** 保存 Answer 或关闭 Surface  
**Then** Library 不新增 Question；只有显式“保存为问题”才创建 Question Knowledge。

## 验收 2：空库保存问题

**Given** Requested Context 为空且没有内部 Knowledge  
**When** 用户保存原问题  
**Then** 创建可未归类的 Question Knowledge，保留 origin Query Turn；外部资料权限和 Answer 不被继承为知识。

## 验收 3：Runtime Unknown 有原因

**Given** Query Run 无法充分回答  
**When** 展开“仍不知道什么”  
**Then** 每项 Unknown 显示 reason、searched scope、对答案的影响和可选下一步，不写成“不存在”。

## 验收 4：Unknown 不制造 Inbox

**Given** 一次 Run 产生十项 Unknown  
**When** 用户不保存并离开  
**Then** 它们只属于该 Run，不产生十条 Question、红点、逾期或待整理计数。

## 验收 5：Unknown 与 No Value 分开

**Given** 一项属性分别处于值未知、确认无值、当前不适用和尚未检索  
**When** Search、Ask 与 Reader 展示  
**Then** 四种语义使用不同状态和人话，不共用空值或“未知”。

## 验收 6：Annotation 提升保留 origin

**Given** Source Fragment 有 questioning Annotation  
**When** 用户提升为 Question  
**Then** 创建新 Question identity 并引用原 Annotation / Fragment；Annotation 不被改造成 Question。

## 验收 7：Conflict 不自动成为 Question

**Given** 系统识别两条 current claims 冲突  
**When** 用户查看 Conflict  
**Then** Conflict 保持独立；只有显式“作为问题调查”才建立 QuestionTargetReference。

## 验收 8：同一 Question 的普通修订

**Given** 核心未知和 criteria 不变  
**When** 用户澄清 Context、Applicability 或措辞  
**Then** 形成同一 Question identity 的新 revision，旧问题和旧 Resolution 可按当时版本回读。

## 验收 9：实质改题建立 successor

**Given** 新表述需要不同答案类别或判定标准  
**When** 用户提交修改  
**Then** 系统预览 successor / split，不静默覆盖原 Question；criterion 与 target mapping 可检查。

## 验收 10：Question 可无 target

**Given** 用户只有一个值得保存的开放问题  
**When** 暂不选择 Group、Topic 或对象  
**Then** Question 仍可保存为 current / unplaced，之后可补 Placement 与 Target。

## 验收 11：多目标有角色

**Given** Question 同时指向 Group、Knowledge Anchor、Relation Revision 与 Decision  
**When** 打开 Targets  
**Then** 按 about scope、seeks explanation、challenges claim 与 informs decision 分组，而不是无差别链接列表。

## 验收 12：Target Reference 非 ordinary Relation

**Given** Q 指向 K 但没有独立稳定语义 Relation  
**When** 查看 Graph、Relation List、Group aggregation 与 Ask Route  
**Then** Q→K 只在 Question Target layer 出现，不计入 ordinary Relation、群级支撑或 relation filters。

## 验收 13：Subquestion 不自动解决父问题

**Given** 一个 required Subquestion 已 resolved，另一个 required criterion 未满足  
**When** 回到父 Question  
**Then** 父问题显示该项贡献与剩余缺口，不自动变为 resolved。

## 验收 14：Partial 有 criterion 依据

**Given** 只有部分 required criteria 有 adopted basis  
**When** 用户采纳当前回答  
**Then** Resolution 为 partially_resolved，并显示未满足 criteria；不使用百分比或模型 confidence 替代。

## 验收 15：Provisional 有保留条件

**Given** 当前回答可用于眼前目的但仍待官方确认  
**When** 用户采纳为暂时可用  
**Then** 必须保存 limitation、validity / review trigger 与 remaining unknown；到期只产生 review_due。

## 验收 16：Resolved 有范围

**Given** required criteria 在特定 Applicability 下均满足  
**When** 用户标记已充分回答  
**Then** Resolution 固定 Question revision、`as_of`、jurisdiction、decision period、subject snapshot、governing rules、assumptions、exclusions、operational decision standing、准确 basis revisions、criteria result、actor 与时间，不声明普遍真理。

## 验收 17：Resolved 与 Active 可并存

**Given** 用户已有充分答案但仍想继续找替代理论  
**When** 采纳 Resolution  
**Then** resolution_state 变为 resolved，pursuit_state 保持 active；页面显示组合状态。

## 验收 18：Unresolved 与 Concluded 可并存

**Given** 用户不再关心一个没有答案的问题  
**When** 以 no_longer_relevant 结束追问  
**Then** pursuit_state 为 concluded，resolution_state 仍 unresolved，History 保存理由。

## 验收 19：Paused 不等于 Concluded

**Given** 用户在等待新资料  
**When** 选择暂停并设置复核条件  
**Then** pursuit 为 paused；Question 仍可继续 Ask 和编辑，不显示已停止追问。

## 验收 20：保存 Answer 无生命周期后果

**Given** AI 生成 complete grounded Answer  
**When** 用户选择“保存这次回答”  
**Then** 只创建 Answer Snapshot；Question resolution、pursuit、Knowledge 与 Relations 不变。

## 验收 21：形成 Knowledge 与采纳分开

**Given** Answer 含两个可复用 Claims  
**When** 用户分别形成 / 合并 Knowledge  
**Then** Knowledge revisions 按编辑合同提交；Question 只出现可链接的新 basis，不自动采纳或结束。

## 验收 22：采纳与结束分开

**Given** 用户选择一个 current answer  
**When** 提交 adoption  
**Then** 创建 Resolution Revision；pursuit 不变。若使用“采纳并结束”，预览明确显示两个独立后果。

## 验收 23：AI 不能自动解决

**Given** AI 判断所有 criteria 似乎已满足  
**When** Answer 完成  
**Then** 只生成 Resolution Proposal；Question header 和 lifecycle 在用户确认前不变。

## 验收 24：依据变化不覆盖 Resolution

**Given** adopted basis 的 Knowledge 或 Relation 有新 revision / retraction  
**When** 系统检测到影响  
**Then** 按 time / source / target-basis / subject context / applicability / unavailable 区分 trigger，写 changes_available event，显示旧新快照与真正受影响 criteria；原 Resolution 仍按历史可读且不被静默整体降级。

## 验收 25：Review Due 不伪装当前可靠

**Given** provisional Resolution 已到复核日期  
**When** Ask 或 Overview 使用它  
**Then** 明确显示“曾被采用、现在需要复核”；回答限定使用，不无警告地当作 current reliable truth。

## 验收 26：Reopen 保留历史

**Given** Question 已 concluded 且有旧 Resolution  
**When** 用户因新证据重新打开  
**Then** 新 Lifecycle Event 保存 reason、from/to state 和旧 Resolution ref；旧 closure 不删除。

## 验收 27：Reopen 不必降级

**Given** resolved Question 只是继续优化  
**When** 用户 reopen  
**Then** pursuit 变 active，resolution 可保持 resolved；只有显式新 Resolution Revision 才改变求解程度。

## 验收 28：Target unavailable 仍可理解

**Given** Question target 被删除、归档或 Anchor orphaned  
**When** 打开 Question  
**Then** 显示历史 target、当前 standing、受影响 criteria 与修复路径；Question 不被删除或自动结束。

## 验收 29：Search 找回组合状态

**Given** Library 同时有 resolved+active、partial+paused、unresolved+concluded 与 provisional+review_due Questions  
**When** 按人话筛选  
**Then** 结果与四轴语义一致，旧表述命中可进入对应 historical revision。

## 验收 30：Overview 只展示重要问题

**Given** Group 内有 40 个 Runtime Unknown、8 个 Gap Markers 与 3 个用户保存的关键 Questions  
**When** 生成 Group Overview  
**Then** 默认只考虑 3 个 Question Knowledge；其他对象不被倾倒成待办清单。

## 验收 31：Graph 与 List 等价

**Given** selected Question 同时有 ordinary Relations、Targets、Basis 与 Subquestions  
**When** 切换 Graph / List 或关闭颜色  
**Then** 四层用分组、完整标签、方向和 programmatic state 区分；List 可完成相同 inspect、open、filter 与 return。

## 验收 32：Export / Restore 等价

**Given** Question 有多版 frame、criteria、target、Resolution、pause、close、reopen 与 successor history  
**When** 完整导出并恢复到新环境  
**Then** identity、Current standing、四轴状态、精确 basis、事件顺序、Placements、Ask lineage 与返回路径等价。

## 验收 33：决策目标与结果时点进入 Applicability

**Given** 同一“怎样学习”的问题分别面向明天的识别测验与八周后的闭卷迁移  
**When** 保存 QuestionFrame  
**Then** decision objective、outcome horizon、assessment target、material 与约束可检查；两种语境不会共用一份无条件 current answer。

## 验收 34：父问题按 criterion mapping 汇总

**Given** 四个 required Subquestions 中三个 sufficient、一个 partial，且该项映射到 blocking criterion  
**When** 生成 parent Resolution Proposal  
**Then** 不按 3/4 投票标记 resolved；显示该子问题贡献、阻塞项与可采用的 provisional 范围。

## 验收 35：暂时可用仍继续追问

**Given** 当前回答足够指导一版学习策略，但课程题型与实际延迟结果尚未知  
**When** 用户采纳当前回答  
**Then** resolution=`provisionally_resolved`、pursuit=`active`，并保留 review triggers；页面不显示完成、逾期或任务进度。

## 验收 36：局部 challenge 不整体重开

**Given** 新 technical comment 只挑战“概念图与提取练习比较”的方法与外推  
**When** impact analysis 完成  
**Then** 只有映射到概念图角色的 criterion 进入 review_due；其他 adopted criteria、parent identity 与 pursuit 不被自动改写。

---

# 16. 产品质量指标与反指标

## 16.1 应观察的质量指标

| 指标 | 问题 |
|---|---|
| Question Return Success | 用户能否从 Library / Group / Search / Answer 回到同一 Question 与现场 |
| State Comprehension | 用户能否说清“回答到哪里”和“是否还在追”是两件事 |
| Resolution Basis Reachability | 当前回答能否一到两步进入准确 Knowledge / Anchor / Evidence |
| Criterion Coverage Legibility | 用户能否解释为何是 partial、provisional 或 resolved |
| Unknown Promotion Precision | 被保存的问题是否真值得长期保留，而非 AI 失败垃圾 |
| Reopen Fidelity | 重开后能否看到旧 closure、Resolution 与新原因 |
| Change Review Comprehension | 依据变化时用户能否识别影响而不误以为答案已自动错误 |
| Successor Integrity | 改题后旧问题、criteria、targets 与 answer history 是否仍可理解 |
| Offline Question Completion | 无 AI 时能否创建、编辑、采用、暂停、结束、重开和导出 |

## 16.2 禁止优化的数字

- Question 数量；
- Unknown 转 Question 比率；
- 自动解决率；
- 平均关闭时间；
- 每日完成问题数；
- Answer 长度；
- 引用数量；
- 模型 confidence；
- reopen 越少越好。

一个高质量知识库可能保存很少但重要的问题，也可能多年保留一个尚未回答的问题。产品不应通过焦虑、红点或自动完成把“诚实未知”赶出系统。

---

# 17. 外部研究事实、产品推论与待验证假设

## 17.1 已核验的外部结构事实

1. W3C ActivityStreams 把 Question 表达为独立对象，允许表示回答选项、responses 与 result；其 `closed` 只表示不再接受回答，并没有把 closed 等同于已经得到正确答案。[W3C Activity Vocabulary — Question](https://www.w3.org/TR/activitystreams-vocabulary/#dfn-question) 与 [Representing Questions](https://www.w3.org/TR/activitystreams-vocabulary/#questions)
2. Schema.org 将 Question 与 suggested / accepted Answer 分开，且明确 accepted answer 的选择机制可能依赖社区意见或提问者判断；“被采纳”因此是 standing，不是来源自动证明的普遍真值。[Schema.org Question](https://schema.org/Question)
3. W3C Web Annotation 将 `questioning` 定义为对 Target 提问或质疑其真实性的 motivation，支持“问题指向准确目标”与“问题本体”分层。[Web Annotation Data Model — Motivation and Purpose](https://www.w3.org/TR/annotation-model/#motivation-and-purpose)
4. W3C PROV-O 将 revision 作为 derivation 的特例，并将 invalidation / expiry 与 revision 分开，支持保存“当时采用了什么”以及后来依据为何需要复核。[PROV-O — wasRevisionOf](https://www.w3.org/TR/prov-o/#wasRevisionOf) 与 [invalidatedAtTime](https://www.w3.org/TR/prov-o/#invalidatedAtTime)
5. Wikibase Data Model 明确区分“某个值存在但当前未知”与“确认没有该值”，并允许不同来源存在相互冲突的值；空值不能承担所有未知语义。[Wikibase Data Model — Snaks](https://www.mediawiki.org/wiki/Wikibase/DataModel#Snaks)
6. GitHub Issues 的关闭可以表示 completed 或 not planned，并且 reopen 是独立历史状态。这不是 Question 模型，但它提供了一个可验证的结构类比：结束处理与对象已经成功解决不能只靠 `closed` 一个词表达。[GitHub Docs — Closing an issue](https://docs.github.com/en/issues/tracking-your-work-with-issues/administering-issues/closing-an-issue)

## 17.2 本合同做出的产品推论

外部标准没有直接定义本产品的四轴状态、Resolution Criteria、Question Target roles 或默认语言。这些是针对个人知识库的产品决定：

- 将 Question 保留为 Knowledge，而把 Query、Unknown、Gap、Annotation 与 lifecycle events 放在 Supporting Records；
- 将 resolution、pursuit、change 与 library standing 正交；
- 用 criterion-level adopted Resolution 表达“当前回答”；
- 允许 resolved + active 与 unresolved + concluded；
- 让 AI 只能提出、不能自动采纳或关闭；
- 将方向 3 的层级阅读与方向 2 的关系空间用于同一 Question Workspace。

## 17.3 仍需真实任务验证的假设

- “已有部分进展 / 暂时可用 / 已充分回答”是否比“未解决 / 部分 / 临时 / 已解决”更易懂；
- 默认只展示一个组合状态句，是否足以让用户理解四轴；
- 用户是否愿意在高后果问题上显式写 resolution criteria；
- `采纳为当前回答` 与 `结束追问` 分开后，是否会被理解为清楚而不是繁琐；
- Network 中独立 Target layer 是否能在不制造图谱噪声的前提下帮助探索；
- Question 与普通 Knowledge 混合在 Library 是否优于单独的问题中心；
- Gap Marker 提升 Question 的判断门槛是否足够克制。
- 用户能否理解“规则层可推断”与“机构已决定”的差异，而不觉得产品在回避回答；
- `as_of` 与少量关键主体条件是否能在不造成表单负担的前提下，显著减少错误复用；
- 只突出一个 changed criterion 是否比整条 Question 变红更容易做出正确复核决定。

这些假设必须在后续真实任务设计与可用性测试中验证；当前文档不能把它们写成已经成功。

---

# 18. 对相邻合同与未来设计的覆盖要求

## 18.1 Canonical

Canonical 必须新增：

- Question Knowledge 的一句话定义；
- Query / Unknown / Gap / Conflict / Question 边界；
- 四轴状态与 adopted Resolution；
- AI 不自动解决、关闭或重开；
- 至少五条 canonical acceptance；
- 进入视觉设计前的独立 Gate。

## 18.2 AI 查询

AI 合同必须把 Runtime Unknown 与 persistent Question 分开，并把“保存回答、形成知识、链接依据、采纳回答、停止追问”拆成不同写入。

## 18.3 Knowledge 粒度

Knowledge 合同必须为 Question 提供从问题、Context、当前回答、criteria、remaining unknown 到 evidence 的阅读骨架，并写清改题 / successor identity boundary。

## 18.4 Relation registry

Relation 合同中的 QuestionTargetReference 必须升级为本合同的 versioned、multi-target、role-aware 模型；`uncertain_about / reopens` 继续保持 ordinary registry 之外。

## 18.5 Search、Overview、Language、Interaction 与 Flow

这些合同必须分别同步：组合状态筛选、重要问题而非 Unknown 倾倒、人话语言、Question Workspace / Resolution Inspector、事件与原子动作。

## 18.6 未来 Screen 2 / 3 设计证明

下一轮视觉设计只有同时证明以下内容才可计为完成：

1. Question 仍是可连续阅读的 Knowledge；
2. 当前回答、criteria 与 remaining unknown 可逐层深入；
3. resolution 与 pursuit 在一行人话中可区分；
4. target / basis / subquestion 与 ordinary Relation 不混边；
5. AI Answer 不自动关闭；
6. 从 Evidence / Ask / Network Back 后精确恢复 Question 现场；
7. Graph 与 List、desktop 与 narrow surface 语义等价。

当前 Ardot 七屏没有完整证明上述内容。本合同只冻结产品责任，不修改设计稿。

---

# 19. 结论

Question Knowledge 不是知识库边缘的一种卡片，而是这个产品能否诚实面对未知的试金石。

如果“问题”只存在于聊天里，AI 查询仍然是一次性消费；如果“关闭”就等于“回答”，系统会把放弃伪装成知识；如果有一段 Answer 就自动 resolved，AI 会接管用户最重要的判断；如果“关于什么”进入普通关系图，网络会被状态噪声污染。

本合同因此确定：

- Question 是长期 Knowledge；
- Unknown、Gap、Annotation、Conflict 与 Query 保持各自边界；
- 当前回答由带 criteria、范围与精确依据的 Resolution Revision 表达；
- 求解程度、继续意愿、变化提醒与 Library 存续正交；
- 采纳、停止追问、复核、重开与 successor 都保留历史；
- AI 可以帮助求解，但不能替用户宣布“这个问题已经解决”。

这使产品真正成为一个会保存答案、也会保存未知，并能让两者随时间共同演化的个人知识库。
