# AI-native 个人知识库

## 知识节点粒度与内容组成合同 v1.0 — Node、Content Block、Anchor 与 Transclusion

> 文档日期：2026-08-06  
> 文档性质：产品本体合同，不是编辑器技术选型、视觉稿或原型规格  
> Canonical 产品定义：`AI-native-个人知识库-终局产品设计文档-v4.0.md`；本合同只证明知识粒度与内容责任，不得反向改写 v4.0  
> 2026-08-07 写入冻结：用户直接编辑经安全 Direct Edit Commit 成为 Current Revision；Edit Buffer、Recovery Checkpoint、Explicit Draft、Proposal、Sync 与 Projection 分开，普通路径没有 Working / 完成并采用  
> v4.0 Knowledge Paper 覆写：Knowledge 是围绕一个主要理解任务的稳定 identity；Knowledge Paper 是它当前 Revision 的连续正文。Section、Block、内联 Claim 与 Anchor 默认都不是独立 Knowledge；只有需要独立理解、适用、证据、关系、复用或修订时才 Promotion  
> v4.0 Relation Anchor 覆写：Relation endpoint 仍是 Knowledge；`from_anchor_ref / to_anchor_ref` 只解释正文哪一处参与关系。Anchor ambiguous / orphaned 触发 review_due；需要独立 Relation neighborhood 的局部主张先 Promotion  
> 2026-08-10 Relation Lifecycle 覆写：Anchor relocation 只更新定位解析；Anchor ambiguous / orphaned 进入 endpoint resolution 与 review，不静默重定向 Relation。RelationCandidate、Revision、EvidenceBinding、Challenge 与 Split / Merge transition 以`AI-native-个人知识库-关系陈述生命周期与网络可信性合同-v1.0.md`为准  
> 2026-08-10 Question Knowledge 覆写：Question 仍是围绕一个主要求知任务的 Knowledge Paper；frame、targets、criteria、Resolution 与 lifecycle 是 Supporting Records / projections，不产生第二份正文。完整合同见`AI-native-个人知识库-问题知识、未知与求解生命周期合同-v1.0.md`  
> 历史深层模型：`AI-native-个人知识库-产品定义-v3.0.md`  
> 相邻合同：`AI-native-个人知识库-知识深度与关系探索合同-v1.0.md`、`AI-native-个人知识库-知识形成与维护循环-v1.0.md`、`AI-native-个人知识库-知识群边界与跨群架构合同-v1.0.md`、`AI-native-个人知识库-Overview形成编辑与更新合同-v1.0.md`、`AI-native-个人知识库-AI查询与知识回答合同-v1.0.md`、`AI-native-个人知识库-来源证据与可追溯性合同-v1.0.md`、`AI-native-个人知识库-直接创作编辑与版本历史合同-v1.0.md`、`AI-native-个人知识库-属性Facet与适用条件合同-v1.0.md`、`AI-native-个人知识库-产品对象层级与身份治理合同-v1.0.md`  
> 核心问题：一条知识应该多大；长内容如何从 Orientation 深入到 Evidence；段落如何被引用、复用、拆分、合并和持续定位，而不制造卡片碎片或文档孤岛

---

# 0. 执行决定

这一轮冻结二十八项产品决定。

1. **Knowledge Node 是最小可独立理解、维护和复用的知识 identity，不是最小文本块。** 一句话、一个段落或一篇长文都不能仅凭长度决定是否成为 Node。
2. **Node 只承担一个主要理解任务，但可以拥有完整论证。** “原子化”不等于删去上下文、条件、例子和反例。
3. **Content Block 是 Embedded Record，不是新增 Primary Resource 或知识对象。** 它没有全局知识 identity，也不能直接成为 Group member 或正式 Relation endpoint。
4. **Node Content Anchor 是 Node 内部的稳定 locator / Embedded Record，不是独立知识对象。** 它让 Evidence、引用、评论、AI Answer 与 Saved Path 精确指向 Node 的某一部分。
5. **Node identity、Current Revision、Edit Buffer / Recovery 与显式 Draft / Proposal 分开。** Node 保持稳定；用户正常直接编辑在 safe Direct Edit Commit 后更新 current，用户可见历史按连续编辑会话分组；Recovery 只保护现场，只有显式 Draft、AI / 系统建议、冲突和高影响变更才使用独立 staging。
6. **Node 的正文只有一份 canonical content tree。** `concise_definition`、`overview`、`examples`、`caveats` 不再同时作为与正文重复的独立真相。
7. **阅读骨架由 Content Block 的 semantic role 投影。** Orientation、Core、Conditions、Connections、Evidence 与 History 是阅读语义，不要求六份重复字段或六张卡。
8. **长 Node 合法。** 只要其章节共同回答同一个主要理解任务，并共享大体一致的 identity、Applicability 与修订节奏，就不因长度被强制拆分。
9. **短 Node 也合法。** 一个关键定义、决定或主张即使只有数句，只要可独立引用、判断和修订，就可以拥有 Node identity。
10. **AI 不按段落、标题、chunk 或 token 数自动制造 Nodes。** 解析片段、检索 chunk、摘要和高亮都不是 Node 候选的充分条件。
11. **Section → Node Promotion 必须基于知识独立性。** 可独立命名、跨语境复用、单独成立或被反驳、具有独立适用条件或修订节奏时，才建议提升。
12. **Node 内部层级服务阅读，不承担知识世界的 canonical hierarchy。** Group / Topic / Placement 决定外部结构；Node 内 heading / block tree 决定正文展开。
13. **一个 Node 引用另一个 Node 默认形成 Reference Link，不形成 Placement 或正式 Relation。** 被引用 Node 不因出现在正文里自动属于当前 Group。
14. **复用默认引用 identity，不复制正文。** 用户可以选择 link、live excerpt、pinned excerpt 或 explicit quote；四者的更新与历史语义不同。
15. **Live excerpt 的编辑必须进入原 Node。** 若用户希望局部独立修改，需要明确“转为本地引用”或“创建独立知识”，不能静默断开同步。
16. **Evidence 可以精确支撑 Node 的 Content Anchor，也可以支撑整个 Node 或一条 Relation。** Evidence Fragment 仍指向 Source；Node Anchor 只说明它支持正文哪里。
17. **正式 Relation endpoint 仍只有 Node↔Node 或 Group↔Group。** Anchor 可以作为 endpoint 的解释定位，但不能取代 Node identity；真正需要独立关系的段落应提升为 Node。
18. **位置 offset 不能单独承担稳定引用。** Anchor 同时使用 stable block id、revision、text quote / prefix / suffix 等可重定位信息，编辑后允许 redirected 或 orphaned 状态。
19. **Node Split 是 identity 变换，不是剪切粘贴。** 它需要处理 Blocks、Anchors、Placements、Relations、Evidence、Backlinks、Overviews、Answers、Paths 与 redirects。
20. **Node Merge 不是简单拼接正文。** 必须选择 canonical identity，比较定义、Applicability、类型、状态和内容结构，并把自关系、重复 Placement 与冲突单独处理。
21. **Node 类型修正不自动改变 identity。** 只要“这条知识是什么”没有改变，Concept → Principle 等重分类可以成为 revision；如果一个正文实际混入多个 identity，则建议 Split。
22. **Search 与 Ask 可以在 Block 粒度检索，但结果必须回到 Node + Anchor + Placement。** 内部 chunk 永远不直接出现在用户知识世界里。
23. **AI 保存到已有 Node 默认产生 block-level patch。** 它说明新增、替换、限定或补证哪一部分，不整篇重写。
24. **Overview 与 Node 复用 Block / Anchor 基础能力，但不共享正文身份。** Overview 可以引用 Nodes 与 Anchors；引用不会复制知识，也不会自动建立 Group membership 或 Relation。
25. **产品质量不以 Node 越小、Block 越多或链接越密衡量。** 能否连续理解、准确引用、稳定复用和安全演化才是质量。
26. **Question Knowledge 共享同一 Knowledge 粒度规则。** 一个复杂问题可以用连续正文保留 Context、工作解释、候选答案与限制，不因 criteria、targets 或 subquestions 被拆成卡片堆。
27. **Question 的当前回答是 Resolution projection，不是影子正文。** Resolution 只能引用 Question 自身或其他 Knowledge 的准确 Revision / Anchor；用户直接写在 Question 中的回答无需复制成第二条 Answer Knowledge。
28. **改写问题也受 identity 边界约束。** 同一核心未知与判定标准形成 revision；答案类别、Applicability 或决策后果实质改变时创建 successor / split，而不是覆盖旧 Question。

这些决定解决现有规格中的五个结构缺口：

- `KnowledgeNode.content` 同时保存 definition、overview、body、examples 与 caveats，可能形成多份正文真相；
- Node schema 内仍出现 `group_memberships / hierarchy_placements`，与 Placement 单一归属合同冲突；
- L4 Deep Detail 被定义为显示层，但没有正文内部结构和稳定定位合同；
- Evidence 只能指向整个 Node 时，长内容中的多条主张会被同一证据含混覆盖；
- Node Split / Merge、正文复用和 AI Merge learning 被列为能力，却没有精确影响与历史语义。

---

# 1. Node 不在“卡片”和“文档”之间二选一

## 1.1 两种失败极端

### Card soup / 卡片碎片

- 每句话成为 Node；
- 定义、条件、例子和反例被拆散；
- 用户必须不断跳转才能理解一件事；
- AI 生成大量标题相似的卡片；
- 图谱边数增长，但知识无法连续阅读。

### Document island / 文档孤岛

- 一个 Node 承载一个领域的所有内容；
- 具体主张无法单独引用、复用或反驳；
- Evidence 只能挂到整篇文章；
- 更新一部分时整篇进入 Diff；
- Group、Relation 与 Ask 只能把长文当黑箱。

本产品拒绝用统一字数阈值解决这两个极端。

## 1.2 Node 的一句定义

> **Knowledge Node 是一个拥有稳定身份、围绕一个主要理解任务组织、可以独立进入并持续修订的知识单元。**

“主要理解任务”示例：

- 解释一个概念；
- 陈述并限定一个主张；
- 记录一个决定及其理由；
- 说明一个方法及其适用条件；
- 追踪一个事件；
- 保留一个仍待回答的问题。

一个 Node 可以包含多段论证，因为论证共同服务同一个任务；它不应同时回答数个只因来源相同而被放在一起的独立问题。

## 1.3 长度不是 identity

以下都可能是合法 Node：

- 80 字的产品原则；
- 500 字的带条件主张；
- 2,000 字的方法说明；
- 8,000 字的概念综述；
- 一条持续更新的公司 Entity；
- 一次复杂决策的完整 rationale。

判断标准是知识职责，不是字符数、Block 数或阅读时间。

---

# 2. 四层内容模型

## 2.1 Node Identity

稳定回答“这是哪一条知识”。它承载：

- `node_id`；
- 类型与标题；
- aliases；
- origin 与作者；
- 当前 Accepted revision；
- 正交知识状态；
- Node 整体的默认 Applicability reference（若适用）；
- identity-level Property Assertion references；
- lineage 与 redirects。

Node identity 可以跨 Group / Topic Placements 复用。

## 2.2 Node Content Revision

回答“这条知识在某次版本中具体写了什么”。它包含：

- 标题快照；
- Orientation；
- Content Block tree；
- Block semantic roles；
- 当前引用与本地引用语境；
- revision message / change basis；
- content-revision-level Property Assertion references；
- author / created_at；
- previous revision；
- 接受动作、接受时间与 lineage。

Content Revision 是版本记录，不是新的日常知识对象。

## 2.3 Content Block

回答“正文由哪些可编辑部分组成”。典型 kind：

- paragraph；
- heading；
- list / list item；
- quote；
- callout；
- table；
- code；
- media；
- node reference；
- evidence citation；
- divider。

Block 有稳定 `block_id`、父级和顺序，可在 Node 内移动；它不是全局可复用知识 identity。

## 2.4 Content Anchor

回答“正文中的哪一处”。它可以指向：

- 整个 Block；
- Heading 下的 section；
- Block 内的 text range；
- 一组连续 Blocks；
- 某个历史 revision 中的位置。

Anchor 是 locator value。它可以被 Evidence Connection、Reference Link、Answer Claim、Saved Path、Comment 或 Change Set 使用，但不出现在 Library、Atlas 或 Group membership 中。

## 2.5 为什么 Block 与 Anchor 不成为 Primary Resource

Content Block 与 Anchor 属于 Node / Overview 的内部内容基底，类似 Source 的 exact locator：

- 它们随父对象导出；
- 不能独立出现在 Atlas；
- 没有独立 lifecycle / epistemic state；
- 不接受 Placement；
- 不作为 Semantic Relation endpoint；
- 如果需要这些能力，应 Promotion 为 Node。

---

# 3. 修订后的 Knowledge Node 模型

```text
KnowledgeNode
  identity
    node_id
    node_type
    title
    aliases[]

  content
    accepted_revision_ref
    working_revision_ref?
    preferred_orientation_anchor_ref?

  epistemics
    lifecycle_state
    epistemic_state
    freshness_state
    availability_state
    default_applicability_ref?
    assumption_refs[]
    conflict_refs[]

  structured_facts
    identity_assertion_refs[]

  authorship
    origin:
      user_authored
      source_derived
      user_synthesis
      system_inference
    author_ref
    created_at

  lineage
    previous_node_refs[]
    successor_node_refs[]
    split_from_ref?
    merged_into_ref?
    redirect_refs[]
    revision_history
```

明确删除：

- `group_memberships`：由 active Placements 推导；
- `hierarchy_placements`：Placement 自身是 canonical truth；
- 与正文重复的 `concise_definition / overview / examples / caveats` 独立字段；
- 含混的 `source_support`：由 Evidence Connections 推导；
- 作为关系替代品的自由 `tags`；Facet / View metadata 与正式知识关系分开。

## 3.1 Content Revision

```text
NodeContentRevision
  revision_id
  node_id
  title_snapshot
  orientation_block_ref?
  content_root_refs[]
  block_records[]
  anchor_redirects[]
  change_summary
  formation_basis
  created_by
  created_at
  previous_revision_ref?
  content_assertion_refs[]
```

Content Revision 一经创建即不可变；`historical` 只是“是否仍被 current pointer 指向”的派生视角，不是可变 revision state。普通编辑先进入 Edit Buffer，并可被 Recovery Checkpoint 保护：

```text
NodeEditBuffer
  session_id
  node_id
  base_revision_ref?
  dirty_content_tree
  composition_state
  validation_errors[]

NodeRecoveryCheckpoint
  checkpoint_id
  session_ref
  base_revision_ref?
  protected_content_tree
  latest_local_checkpoint_ref
  device_ref

NodeExplicitDraft
  draft_id
  node_id
  base_revision_ref?
  draft_content_tree
  draft_kind: user_explicit | conflict | restore
```

普通直接编辑可以频繁写 Recovery Checkpoint；只有 composition 结束、内容合法且到达 idle / blur / navigation / explicit save / normal close / pre-read flush 等安全边界后，Direct Edit Commit 才原子更新 Current Revision。底层 commits 可高频，用户可见 History 按可理解编辑会话分组。Explicit Draft 只在用户主动选择、冲突或历史恢复时存在；AI / 系统建议保持 Proposal。Recovery、Draft、Proposal、Sync 与 Projection 都不能自行移动 current pointer。

### 3.1.1 Property Assertion 的归属

Node 不保存无结构的 `properties{}` 或自由 `tags[]`。所有结构化事实引用 stable Property Definition，并按语义保存到不同位置：

| 事实 | Assertion location | 例子 |
|---|---|---|
| 即使正文修订也仍描述同一对象 | Node identity | 人物出生日期、产品官网 |
| 它是该版正文形成的结论 | Current Content Revision | 当前比较结论、有效状态 |
| 只在某个 Group / Topic 出现语境成立 | Placement | 本群优先级、局部角色 |
| 描述原始材料本身 | Source | 文件作者、网页发布日期 |
| 只限定一次 Ask | Query Context，不写 Node | 法国、学生、2026 |

Property Definition 和 Assertion 均不是 Content Block；它们不进入正文 Block tree，也不成为正式 Relation endpoint。Context Rail 把 identity、content revision、Placement、Source、Derived 与 Working / Proposed 分层显示，日常阅读默认退让。

Node-reference Assertion 只表达原子特征和导航。若需要说明两个 Nodes 如何相连，用户必须补全类型、方向、statement、Applicability 与依据并提交 maintained Relation；AI 发现只产生 RelationCandidate。`unset`、known false、`unknown`、`no_value` 与 `not_applicable` 分别保存，不由空字段推断。

## 3.2 Content Block

```text
NodeContentBlock
  block_id
  parent_block_id?
  order_key
  block_kind
  semantic_role?
  payload
  ownership:
    user_owned
    ai_assisted
    generated
  source_anchor_refs[]
  created_at / updated_at
```

`block_id` 在 Node identity 内稳定。Block 被移动、改变样式或在同一 Node 内重排时不换 ID；Block 被复制到另一 Node 时得到新 ID，并保留 derivation link。

## 3.3 Content Anchor

```text
NodeContentAnchor
  node_id
  anchor_id
  revision_basis_ref
  selector
    block_ref?
    heading_path?
    text_position?
    text_quote?
    prefix?
    suffix?
  anchor_state:
    resolved
    redirected
    ambiguous
    orphaned
  redirect_anchor_ref?
```

默认优先级：stable block id → text quote + context → revision position。offset 只作为重定位线索，不作为唯一真相。

---

# 4. 粒度判断合同

## 4.1 一个内容应保持在同一 Node 的条件

通常同时满足：

1. 围绕同一个主要问题或知识 identity；
2. 各段落共享大体一致的 Applicability；
3. 更新时通常需要一起理解；
4. 单独拿出某一段会失去必要上下文；
5. 关系主要指向整体，而不是内部每一段；
6. 用户进入时希望连续阅读，而不是跳到另一条独立知识。

例如“情境依赖检索”可以在一个 Node 中包含定义、机制、实验范式、适用条件、限制和例子。

## 4.2 应拆成独立 Node 的信号

满足任一强信号，或多个弱信号：

- 可以独立命名和解释；
- 可以独立为真、为假、被限定或被替代；
- 拥有不同 Applicability；
- 拥有独立 Evidence 集合；
- 在多个 Groups / Topics 中复用；
- 需要自己的正式 Relations；
- 更新节奏明显不同；
- 用户频繁直接 Search / Ask / link；
- 一段内容膨胀到遮蔽父 Node 的主要任务；
- 合并在一起导致标题无法准确命名正文。

## 4.3 应保持为 Section / Block 的信号

- 只是定义的解释、例子或反例；
- 只是方法中的一步，脱离方法无法使用；
- 只是版式结构；
- 只为当前 Node 提供过渡；
- 没有独立 Applicability、Evidence、关系或使用入口；
- 用户只需精确引用，不需要独立维护。

## 4.4 不使用硬阈值

系统可以把以下作为提示信号，但不能单独决定 Split：

- 字数；
- Heading 数；
- Block 数；
- 引用数；
- 阅读时长；
- embedding cluster；
- AI “主题数”。

## 4.5 用户随时可以覆盖建议

用户可以：

- 保持长 Node；
- 将选中 Section 提升为 Node；
- 将短 Node 合并；
- 拒绝 AI 粒度建议；
- 固定“不要再建议拆分 / 合并”。

系统只有在 identity、证据、适用条件或下游影响需要判断时，才让粒度建议进入 Review。

---

# 5. Semantic Role：同一正文，不重复存储

## 5.1 通用 role

Block 可以可选地拥有：

- `orientation`：一句定义、结论或作用；
- `core_explanation`：核心解释；
- `mechanism`：如何发生；
- `rationale`：为什么；
- `condition`：成立条件；
- `exception`：例外；
- `example`；
- `counterexample`；
- `procedure_step`；
- `comparison`；
- `unknown`；
- `history_note`；
- `other`。

Role 服务阅读投影、Ask 与可访问性，不强迫用户填表。

## 5.2 Role 不是复制内容

错误：

```text
concise_definition = A
overview = A 的改写
first paragraph = A 的第三种改写
```

正确：

```text
orientation_block_ref = block-17
block-17.semantic_role = orientation
```

界面在 D0 使用同一 Block 的简洁呈现，在 D2 回到其完整上下文。

## 5.3 缺失不是空模板

若一个 Method 没有限制：

- 阅读态不显示空的“限制”卡；
- 系统可以在 P1 显示“尚未记录限制”；
- 用户或 AI 可以建议补充；
- 缺失本身可以成为 knowledge gap，但不是表单错误。

## 5.4 类型适配

### Concept

优先：orientation、core explanation、boundaries、examples、confusions。

### Claim

优先：claim statement、Applicability、rationale、counterevidence、status。

### Principle

优先：principle statement、rationale、Applicability、exceptions、applications。

### Method

优先：purpose、preconditions、steps、failure modes、examples。

### Decision

优先：decision statement、context、options、rationale、consequences、supersession。

### Entity / Event

优先：identity / what happened、timeline、claims、relations、sources。

### Question / Inquiry

优先：

1. question statement、Context、why it matters 与 Applicability；
2. current adopted answer，若尚无则显示候选解释，不生成空答案卡；
3. `怎样算回答`的 Resolution Criteria；
4. available basis / evidence 与准确 Anchors；
5. remaining unknowns、limitations 与 review trigger；
6. targets、required / optional Subquestions 与 next resolution paths；
7. previous resolutions、pause / conclude / reopen 与 successor history。

QuestionFrame 与 QuestionResolutionRevision 都从同一 Knowledge Paper 投影或指向其准确 Anchors；不得再保存一份会与正文漂移的 `question_body` 或 `final_answer`。问题只是在同一核心求知意图下补清 Context、criteria、targets 或措辞时保留 identity；新表述需要另一类答案或另一套 criteria 时建立 successor Question。

类型只改变推荐结构和阅读优先级，不生成空字段墙。

## 5.5 三种 Claim 不共用 identity

| 名称 | 所属 | 是否是 Knowledge Node | 写入规则 |
|---|---|---|---|
| Inline Claim | 一个 Node 的 Content Revision + Anchor | 否 | 随父 Node 直接编辑；可有 Evidence Binding |
| Claim Node | 独立 Knowledge identity，type = Claim | 是 | 独立适用条件、证据、状态、关系、复用与历史 |
| Answer Claim | 一次 Query Run / Answer Snapshot | 否 | 保存回答也不自动进入 current Knowledge |

Inline Claim 与父 Node 共享主要理解任务、Applicability 和修订节奏。只有它需要独立成立或被反驳、独立 Evidence / state、正式 Relation endpoint、跨语境复用或不同修订节奏时，才执行 Promotion。仅仅被 AI 抽取、被搜索命中或拥有 Anchor，不授予 Knowledge identity。

---

# 6. Reading Depth 与正文内部结构

## 6.1 D0 Orientation

显示：

- title；
- Node type；
- 当前 Placement 语境；
- orientation block 或明确的“尚未写下简短说明”；
- 一句最重要状态。

D0 不另存一份 AI 摘要。如果 orientation 是 Generated projection，必须标明且可回到依据 Blocks。

## 6.2 D1 Synthesis

显示：

- orientation；
- section outline；
- 2–5 个关键 Blocks / conclusions；
- Conditions & Limits 摘要；
- 主要关系和证据入口。

D1 可以由当前 Accepted revision 派生，也可以由用户拥有的 Synthesis Blocks 组成。

## 6.3 D2 Explanation

显示连续 Knowledge Paper：

- 完整 Content Block tree；
- inline Node references；
- evidence markers；
- section folding；
- Context Rail；
- 当前 anchor 与阅读位置。

默认不把每个 Block 画成独立卡片。Block handles 只在 edit / selection mode 出现。

## 6.4 D3 Evidence

从当前 Node Anchor 进入：

- 哪个 Source Fragment 支撑、限定或反驳这一部分；
- exact Source locator 与上下文；
- Node revision 与 Anchor 状态；
- 证据对整个 Node 还是局部内容生效；
- Back 后恢复相同 anchor、scroll、Placement 与 Relation Radius。

## 6.5 L3 / L4 不产生两个对象

L3 Node 与 L4 Deep Detail 使用同一个 Node identity：

- L3 改变的是 Scope；
- D0–D2 改变的是同一 Scope 内的 Reading Depth；
- heading / section 不自动成为 L4 子页面；
- Search 可以直接落到一个深 Anchor，但 Up 仍返回 Node / Topic，而不是虚构 Section 层级。

---

# 7. Reference、Embed 与 Transclusion

## 7.1 四种复用方式

| 方式 | 显示 | 更新语义 | 是否复制正文 |
|---|---|---|---:|
| Link | 标题或自定义文本 | 打开当前 Accepted Node | 否 |
| Live excerpt | 显示目标 Node 的当前指定 Anchor | 原 Node 更新后同步，并显示影响 | 否 |
| Pinned excerpt | 显示目标 Node 某个历史 revision / Anchor | 保持当时内容，可提示已有新版本 | 否 |
| Explicit quote | 本地保存一段引用文本并记录 Node revision | 不同步；明确是引用快照 | 是，但不是另一条 canonical knowledge |

## 7.2 Reference Block

```text
NodeReferenceBlock
  source_node_ref
  source_anchor_ref?
  display_mode:
    link
    live_excerpt
    pinned_excerpt
    explicit_quote
  pinned_revision_ref?
  local_context_text?
  reference_state
```

Reference Block 形成 backlink / Reference Link，不自动生成正式 Relation。

## 7.3 引用不产生 Group membership

若 Group A 中的 Node X 引用 Node Y：

- Y 不因此自动属于 Group A；
- Atlas 不新增群关系；
- Group Overview 不把 Y 计入 active member coverage；
- 用户可以单独选择“也放入这个知识群”，此时创建 Placement；
- 多个核心引用可以成为 Group RelationCandidate 的依据，但采用后仍需物化独立 Group Relation 与首个 Revision。

## 7.4 编辑 Live excerpt

默认动作：

- `打开原知识`；
- `编辑原知识`；
- `固定当前版本`；
- `改为本地引用`；
- `创建独立知识`。

不能让用户在嵌入位置直接修改，随后才发现所有引用都变了。

## 7.5 来源 Node 变化

- current revision 更新：live excerpt 更新，并在高影响时显示 change marker；
- anchor redirected：自动跟随并可查看旧位置；
- anchor ambiguous：显示“内容已变化，当前无法唯一确定对应位置”；
- anchor orphaned：保留最后可用 excerpt 与修复入口；
- Node superseded：显示 successor，用户选择跟随或继续固定；
- Node archived：仍可显示并说明状态；
- Node permanently deleted：高影响操作前必须列出引用；删除后保留不可恢复说明，不伪造空内容。

---

# 8. Anchor 与精确 Evidence

## 8.1 两段定位链

```text
Node / Relation
  → Node Content Anchor（知识中的哪一部分）
  → Evidence Fragment（来源中的哪一部分）
  → Source Revision + exact locator
```

Node Anchor 与 Evidence Fragment 不是同一个 locator：前者定位用户知识，后者定位原始来源。

## 8.2 Evidence Fragment 与 Binding Target

```text
EvidenceBinding
  evidence_fragment_ref
  knowledge_target
    node_ref | relation_ref
    node_anchor_ref?
  target_revision_ref
  support_role:
    supports
    challenges
    qualifies
    defines
    exemplifies
    provides_context
  applicability_alignment?
  created_by
  revision_history
```

Evidence Fragment 永久绑定 Source Revision、Representation、Selector Bundle 与内容快照；它不拥有全局 support role。如果 `node_anchor_ref` 为空，Binding 对整个 Node 生效；对长 Node 的具体主张应尽量精确指向 Anchor。同一 Fragment 可通过多个 Bindings 对不同 targets 表达不同作用。完整 provenance 见 `AI-native-个人知识库-来源证据与可追溯性合同-v1.0.md`。

## 8.3 Anchor 重定位

Accepted revision 后执行：

1. 优先匹配 stable block id；
2. Block 被拆分或移动时使用 anchor redirect；
3. 匹配 text quote + prefix / suffix；
4. 使用历史 revision position 辅助；
5. 匹配到多个候选或只能模糊猜测时标记 ambiguous，等待用户确认；
6. 内容确已删除时标记 orphaned，并保留旧 revision 查看入口。

系统不能把“还能找到相似句子”自动等同于同一语义位置。

## 8.4 Anchor 状态的人话

- resolved：`依据已指向当前内容`；
- redirected：`这段内容已移动到新位置`；
- ambiguous：`内容已变化，请确认现在对应哪一段`；
- orphaned：`原来引用的内容已被删除；可查看历史版本`。

## 8.5 Relation 与 Anchor

Relation schema 可以拥有：

```text
meaning
  from_anchor_ref?
  to_anchor_ref?
```

这些 Anchor 帮助解释“Node 的哪一部分参与关系”，但 endpoints 仍是 Nodes。若一条关系只对某段独立主张成立，且该主张需要自己的状态与 Evidence，应先将该段 Promotion 为 Claim Node。

---

# 9. 写作与编辑合同

## 9.1 连续写作优先

Node Editor 默认是连续正文：

- 光标直接进入内容；
- Block handles 在 hover、selection 或 keyboard command 时出现；
- Node type、Applicability、Relations 与 Evidence 进入 Context Rail；
- 不要求用户先填写属性表；
- 按键级可保护 recovery checkpoint；safe Direct Edit Commit 成功后，普通用户编辑默认更新 Current Revision；
- 正式历史按连续编辑会话合并，不为每个字符生成 Revision；
- 只有用户显式选择“作为草稿继续”、发生写入失败或冲突、应用 AI / 系统建议、或执行高影响变更时，Close 才保留 Draft / Proposal 而不更新 current pointer。

## 9.2 Edit Scope

用户需要区分：

- `修改这条知识`：编辑 canonical Node Content；
- `只修改它在这里的说明`：编辑 Placement contextual summary；
- `编辑引用的原知识`：从 live excerpt 进入 source Node；
- `把这一段变成独立知识`：Section → Node Promotion；
- `固定当前版本`：live → pinned；
- `转为本地引用`：live → explicit quote。

## 9.3 Block move

同一 Node 内移动 Block：

- block id 保持；
- anchors 随 block 移动；
- section path 更新；
- 外部引用不失效；
- reading position 尽量恢复。

跨 Node 移动 Block：

- 进入 Node Split / Promote flow；
- 不能作为普通 drag-and-drop 静默完成；
- 新 Node 中生成新 block id；
- 旧 anchor 建 redirect；
- 预览 Evidence、Reference 与 Answer impact。

## 9.4 删除 Block

删除前按影响分级：

- 无任何引用 / Evidence：普通 undoable edit；
- 有内部 reference：显示局部影响；
- 有外部 Anchor、Evidence、Relation、Overview、Saved Answer 或 Path：打开 Change Set Preview；
- user-owned / locked Block：AI 不可删除，只能提出 Diff；
- 历史 revision 永远保留原内容。

## 9.5 并发

后台 AI、来源重编译和多设备同步可能同时改变 Node。冲突最小单位是 Block / Anchor：

- 不使用 whole-document last-write-wins；
- 无冲突 Blocks 自动合并；
- 同一 Block 冲突并列比较；
- Block 移动与正文修改分别处理；
- Accept 后形成一个 Change Set 与新 revision。

---

# 10. Section → Node Promotion

## 10.1 入口

- 选中 Heading / Blocks：`成为独立知识`；
- AI 建议：`这一部分已经可以独立维护`；
- Evidence / Relation 创建时发现目标过于局部；
- Search / Ask 高频直达同一 Anchor。

## 10.2 Promotion 预览

用户确认：

1. 新 Node 标题与类型；
2. 哪些 Blocks 进入新 Node；
3. 原位置保留 link、live excerpt、pinned excerpt 还是简短过渡；
4. 新 Node 放到哪些 Placements；
5. 哪些 Evidence / Relations 应重绑定；
6. 是否保留原 Node 的 Applicability 或单独限定。

## 10.3 变换

```text
Section S in Node A
  → snapshot source revision and anchors
  → create Node B with new node_id
  → move selected semantic content into B
  → replace S in A with chosen Reference Block
  → redirect external anchors from A/S to B
  → rebind clearly local Evidence
  → review Relations, Overviews, Answers and Paths
  → commit one reversible Change Set
```

## 10.4 默认不自动重绑定

- Evidence 精确支撑被移动内容：可预选跟随 B；
- Relation 明确只针对被移动主张：建议改为 B endpoint；
- Relation 同时依赖 A 的其他内容：保持 A 或建议新 relation；
- Placement：B 默认只继承当前语境，其他 Groups 逐项选择；
- Overview / Answer：标记 affected，不能直接替换文字；
- 历史 Saved Answer 继续指向 A 的旧 revision anchor。

## 10.5 Promotion 不是复制

原位置默认使用 Reference Block，不保留两份可独立编辑的相同正文。用户选择 explicit quote 时，界面明确它是历史引用，不是同步知识。

---

# 11. Node Split / Merge

## 11.1 Split Node

适用于一个 Node 实际包含多个 identity。

流程：

1. 标出每个新 Node 的主要理解任务；
2. 映射 Blocks；
3. 为共享上下文选择 duplicate-as-quote、reference 或重新写过渡；
4. 分配 Applicability 与状态；
5. 分配 Evidence Connections；
6. 分配 Placements；
7. 检查 Relations 与 backlinks；
8. 预览 Overview、Answers、Paths；
9. 保留原 Node 为 redirect / historical container，或保留其中一个 canonical identity；
10. 提交可撤销 Change Set。

## 11.2 Merge Nodes

先选择 canonical Node identity。系统显示：

- definition / orientation diff；
- node type；
- Applicability；
- lifecycle / epistemic / freshness；
- Content Block mapping；
- Evidence overlap / conflict；
- Placements 与 contextual summaries；
- Relations、backlinks、References；
- Overview、Answer、Path impact；
- aliases 与 redirect plan。

## 11.3 不能默认做的事

- 直接把 B 正文粘到 A 底部；
- 以标题或 embedding 相似判定同一 identity；
- 用“保留较长版本”决定 canonical；
- 删除冲突段落；
- 把不同 Applicability 的 Claims 合并；
- 自动继承所有 Placements；
- 把 A→B Relation 变成自关系并继续显示；
- 改写 historical snapshots。

## 11.4 Merge 后

- 非 canonical Node 保留 redirect；
- anchor redirects 指向 canonical Node / revision；
- 等价 Placements 可以合并，语境不同的 Placements 保留；
- duplicate Relations 去重；
- endpoint collapse 产生的 self-relation 进入 archived historical relation；
- Evidence 不丢失原 target history；
- 旧 URL、Saved Path 与 Answer 可解释。

## 11.5 Undo

Undo 恢复：

- Node identities；
- Content revisions；
- Blocks 与 Anchors；
- Placements；
- Relations；
- Evidence targets；
- redirects；
- Overview / Answer impact markers。

Merge 后新增的内容不能被历史 Undo 静默删除；出现后续 revision 时进入三方预览。

---

# 12. AI 的内容边界

## 12.1 AI 可以自动准备

- Block semantic roles；
- section outline；
- D0 / D1 未保存 preview；
- anchor re-location candidates；
- possible duplicate / split signals；
- Evidence-to-anchor suggestions；
- inline citation formatting；
- retrieval chunks。

这些属于 A0 / A1，不改变 Knowledge Truth。

## 12.2 AI 必须以 Proposal 进入

- 新 Node；
- Section → Node Promotion；
- Node Split / Merge；
- Accepted Node 的 block-level patch；
- Applicability 改变；
- Evidence rebind；
- user-owned Block 改写；
- live reference 转为本地副本。

## 12.3 Block-level patch

AI 建议必须说明：

```text
Target Node + Anchor
Change kind:
  append
  replace
  qualify
  retract
  add evidence
  restructure
Why this change
Source / Evidence
Applicability
Affected objects
Undo scope
```

默认不使用“用最新资料重写整篇”。

## 12.4 AI 不能以 chunk 为产品真相

- chunk id 只用于检索；
- chunk 边界不决定 Node；
- overlap chunk 不生成重复知识；
- chunk summary 不成为 canonical orientation；
- 用户永远看到 Node title、Anchor context 与 Placement，不看到“片段 17”。

## 12.5 粒度建议必须解释

系统只能说：

> 这一部分已经在三个知识群中被单独引用，并拥有不同适用条件；把它变成独立知识可以减少重复修改。

不能只说：

> 这段太长，建议拆分。Confidence 92%。

---

# 13. Search、Ask 与保存

## 13.1 检索粒度

内部可以索引：

- Node title / aliases；
- Orientation；
- Blocks；
- Anchors；
- Placements / contextual summaries；
- Relations；
- Evidence；
- Sources。

结果统一为：

```text
Node identity
  + matched Anchor
  + current Placement context
  + why matched
  + status / evidence summary when relevant
```

## 13.2 搜索结果

搜索命中深段落时：

- 结果标题仍是 Node；
- snippet 来自 matched Anchor；
- 打开后滚动并高亮 Anchor；
- Up 返回 Topic / Group；
- Back 返回 Search；
- 用户可以“查看整条知识”取消 anchor focus。

## 13.3 Ask 引用

每个 Answer Claim 保存：

- basis kind：accepted knowledge、source statement、current user input、cited external source、reasoned derivation 或显式 historical answer reference；
- supporting Node refs + exact Anchor + actual revision；
- supporting Relations + applicability；
- Evidence Fragment refs + Source locator / snapshot；
- support role 与 Retrieval reason；
- conflicts、unknowns 与 locator availability。

因此用户可以从一句回答回到正文的确切部分，再进入 Source。Node + Anchor citation 只证明“来自你的知识”，不自动证明存在外部 Evidence；Source locator 只证明“来源原文”，不自动把它升级成 Accepted Node。

## 13.4 保存 AI Answer

用户选择：

- 保存为 Saved Answer / Knowledge Snapshot；
- 新建综合 Knowledge Draft；
- 保存为 Inquiry；
- 合并到已有 Node 的某个 Anchor；
- 追加 Evidence；
- 保存 Path；
- 建议 Relation；
- 建议更新 Overview；
- 保存外部 Source。

`合并到已有知识` 打开 block-level patch，只允许选择已经能说明 basis 与 Applicability 的 Claims；不把整段 Answer 直接粘入正文，也不把 Answer Claim 自动当成 Accepted Claim。Saved Answer 默认不参与 current factual Ask；它的 Node Anchor refs 只在查看 Original / historical scope 时解析。

## 13.5 Node 变化后的 Answer

- historical Answer 保留原 Node revision + Anchor；
- current re-evaluate 使用最新 Accepted revision；
- re-evaluate 创建新 Query Run / Answer Snapshot，不改变旧 Claim Support；
- anchor redirected 时旧 Answer 仍可回到旧位置并提供当前入口；
- anchor orphaned 时显示“原回答引用的内容已被删除”；
- 新回答不覆盖旧回答。

---

# 14. Overview 与 Node Content 的关系

完整 Overview identity、版本、Block types、Support Map、治理、alignment 与变换合同见 `AI-native-个人知识库-Overview形成编辑与更新合同-v1.0.md`；本章只冻结它与 Node Content 的接缝。

## 14.1 Overview 不是 Node 拼贴

Overview 可以包含：

- Editorial Blocks：用户或经接受的 AI-assisted prose；
- Projection Blocks：Group / Topic structure、代表知识、关系与变化等规则结果；
- Reference Blocks：Link、Live、Pinned 或 Quote；
- Navigation Blocks：进入 Topic、Node、Path 或 Relation Lens 的入口；
- Status Blocks：边界、覆盖、变化与核验状态。

它不能把若干 Node orientations 机械拼接成一篇文章。

## 14.2 Overview 引用语义

- link reference：只保留 Node 入口，不复制正文；
- live Node reference：按最新 Node revision 显示，更新结果与 Editorial prose 分开；
- pinned reference：保留某次边界或历史解释；
- explicit quote：保留确切文字、来源 revision 与 Anchor；
- local synthesis：Overview 自己的 Editorial 表述，通过 Support Map 回到支撑 Nodes / Relations；
- AI preview：仍是 working proposal，接受前不是 Overview truth。

## 14.3 Node Split / Merge 影响

- Split：Overview reference 保留原历史，current projection 建议指向新 Nodes；
- Merge：旧 references 通过 redirect 到 canonical Node；
- accepted Editorial prose 无论 authorship 都不自动改写；
- 需要改变的 prose 形成 Overview Semantic Diff；
- Projection 根据 redirects 与 canonical structure 刷新；
- locked Blocks 保持原文，alignment 可同时进入 changes_available、review_due 或 knowingly_diverged。

## 14.4 Overview Anchor

Overview 使用同一 Content Block / Anchor substrate，允许：

- Answer 回到 Overview 的某段；
- Diff 精确定位；
- Support Map 从局部指向 Node Anchor、Relation、Structure Projection、Boundary 或 Historical Overview；
- Saved Path 恢复阅读位置。

它仍是 Overview 对象，不因此变成 Node，也不成为 Evidence endpoint。若 Overview 段落需要独立 Evidence、Applicability、Relation 或跨群复用，应执行 Claim Promotion：创建 Node，迁移支撑与历史，Overview 保留 Reference 与 Anchor continuity。

---

# 15. 状态与生命周期

## 15.1 Node state 与 Block state 分开

Node 拥有 lifecycle、epistemic、freshness、availability。Block 不复制四轴状态；局部差异通过：

- semantic role；
- ownership；
- Evidence target；
- Change Diff；
- Anchor state；
- Applicability-specific child Claim Node；
- local warning projection。

如果正文内部不同主张需要长期独立 epistemic state，应拆成 Claim Nodes，而不是给每段建立一套迷你状态机。

## 15.2 Buffer、Recovery、Explicit Draft 与 Proposal

- Edit Buffer 是普通写作的短期现场；Recovery Checkpoint 高频保护它，但默认 Search / Ask / Overview / Graph 不使用；
- 普通直接编辑在 Direct Edit Commit 后形成 Current Revision，因此默认 Ask 使用它；
- 显式 Draft 可以包含未完成 Blocks，默认 Ask 不使用，除非 Query Context 明确包含该 Draft；
- Draft / Recovery checkpoint 不改变 current pointer；
- Proposal 在 review 前不改变 current；Inline accept 进入 Buffer，Structured Patch confirm 可直接 commit；
- Draft Anchor 可用于当前编辑会话与恢复，但不能成为稳定公共引用；设为当前时系统把可重定位 Anchor 映射进新 Current Revision。

## 15.3 Supersede

Node 被 supersede 时：

- identity 保留；
- successor 明确；
- historical references 不改写；
- live references 默认显示状态并可选择跟随 successor；
- pinned references 保持原 revision；
- Placement 可以继续存在用于历史语境，或迁移到 successor。

## 15.4 Archive / Trash / Delete

- Archive Node：Content、Anchors、references 与 history 可读；
- Trash Node：默认不参与 Search / Ask，但 Impact Preview 可见；
- Permanent Delete：列出所有 Reference Blocks、Anchors、Evidence、Relations、Placements、Overviews、Answers 与 Paths；
- 删除一个 Block 不等于删除 Node；
- 删除 Node 不删除它引用的其他 Nodes；
- explicit quotes 保留自身文本与原引用不可用说明。

---

# 16. 规模与退化规则

## 16.1 10,000 Blocks 的 Node

产品不尝试一次渲染全部：

- outline + virtualized content；
- section search；
- anchor direct open；
- collapse / expand；
- current section evidence；
- AI 可以建议 Split，但不能仅因 Block 数执行。

## 16.2 1,000 外部 Anchors

- Impact Preview 聚合到使用对象；
- 默认显示高影响 references；
- 完整列表可筛选；
- anchor re-location 后批量报告 resolved / redirected / ambiguous / orphaned；
- 不因引用多禁止编辑，但高影响删除需要明确确认。

## 16.3 AI unavailable

- Node / Block 编辑可用；
- Anchor 与引用解析可用；
- Search 使用本地索引；
- Evidence 可打开；
- AI synthesis、split suggestion、semantic role suggestion 暂停；
- 已保存结构和历史不降级。

## 16.4 Index corrupted

- canonical content tree 与 stable IDs 不受影响；
- Search / Ask 命中降级；
- links / anchors 仍按直接 ID 打开；
- 重建 index 不创建 Nodes 或改写 content；
- 完整备份不把派生 chunk 当成唯一内容。

## 16.5 Export

完整 Knowledge Package 保存：

- Node identities；
- accepted / historical revisions；
- Block tree 与 stable IDs；
- Anchor selectors / redirects / states；
- Reference modes；
- Evidence targets；
- Placements、Relations、Overviews 与 history。

阅读导出提供：

- 可读 Markdown / HTML；
- heading / HTML anchor fallback；
- Node / revision manifest；
- tool-specific block reference 不作为唯一可恢复格式。

---

# 17. 代表性场景

## 17.1 长 Concept Node

“情境依赖检索”包含定义、机制、实验范式、现实限制和应用。

预期：

- 保持一个 Concept Node；
- D0 先显示定义，D2 连续阅读；
- 每个实验主张可有 Anchor + Evidence；
- 一个独立的“编码特异性原则”若跨群复用，则 Promotion 为 Principle Node；
- 不按每个 Heading 自动拆 Node。

## 17.2 短 Decision Node

“Atlas 默认只显示 Groups”只有一段结论和 rationale。

预期：

- 独立 Decision Node；
- 具有 Applicability、alternatives、consequences；
- 可与设计原则、性能限制建立 Relations；
- 短不等于应该并入长产品文档。

## 17.3 同一知识在三篇 Node 中复用

“Evidence adjacent to knowledge”被方法、原则和设计决定引用。

预期：

- 一个 canonical Principle Node；
- 三个 Reference Blocks 或 Nodes Relations；
- 修改 Principle 一次，live excerpts 同步；
- 只有 Placement 才改变 Group membership；
- explicit quote 保留历史语境并明确不自动更新。

## 17.4 Evidence 精确支撑一段

一篇 Method Node 中只有“默认 3–7 个 Decision Bundles”由某次研究支持。

预期：

- Evidence Connection 指向该 Anchor；
- 不把整篇 Method 标为“被此证据支持”；
- 删除或改写该段时出现 Evidence impact；
- Source locator 与 Node anchor 分开核验。

## 17.5 Section Promotion

“Identity Resolution”最初是 Compiler Node 的一节，后来拥有独立流程、状态和跨群引用。

预期：

- 建议“成为独立知识”；
- 新建 Method Node；
- 原位置变成 live excerpt / link；
- Evidence 跟随明确 Anchors；
- Relations 逐项检查；
- 旧 Saved Answer 仍可打开原 revision。

## 17.6 Node Merge

“Knowledge Group”和“知识群”被确认是同一 Concept Node。

预期：

- 选择 canonical identity；
- alias 合并；
- 内容按 semantic role 对照，不直接拼接；
- Placements 与 contextual summaries 保留；
- A→B self-relation 归档；
- 旧 URL 和 Anchors redirect；
- 不同 Applicability 时阻止错误 Merge。

## 17.7 Ask 命中深 Anchor

用户问“为什么 Retrieval Jump 不应该变成 Relation”。

预期：

- 检索命中“连接类型”Node 内一段；
- Answer 引用 Node + Anchor + Evidence；
- 点击直接到该段；
- Up / Back / Placement 完整；
- 内部 chunk 不作为用户可见对象。

---

# 18. 产品质量指标

## 18.1 核心指标

- **Node Orientation Success**：用户能否在短时间说清该 Node 的主要任务；
- **Continuous Understanding Success**：阅读一个完整问题是否无需在碎片间过度跳转；
- **Independent Reuse Success**：需要跨语境复用的知识是否拥有稳定 Node identity；
- **Evidence Target Precision**：Evidence 是否指向正确 Node Anchor；
- **Anchor Survival Rate**：Accepted revisions 后外部 Anchors 保持 resolved / redirected 的比例；
- **Anchor Repair Success**：ambiguous / orphaned 是否可理解并修复；
- **Split Reversal Rate**：Section Promotion / Split 后短期撤销比例；
- **Merge Error Rate**：错误 identity Merge 后重新拆分比例；
- **Reference Mode Comprehension**：用户能否预测 live、pinned 与 quote 的更新差异；
- **Block Patch Acceptance Quality**：用户是否能准确解释 AI patch 改了哪里及为什么；
- **Deep Search Continuity**：从命中 Anchor 打开、阅读、返回时上下文是否保持。

## 18.2 反指标

- Node 数越多越好；
- 平均 Node 越短越好；
- Block 数越多越灵活；
- 每段都有链接；
- 所有 Anchor 永不 orphan；
- AI Split 接受率；
- 文档被拆成卡片的比例；
- 引用同步次数。

---

# 19. 验收标准

## 19.1 粒度判断

- 长 Concept 可以保持一个 Node；
- 独立短 Decision 可以成为 Node；
- chunk、Heading、Block 与 highlight 不自动成为 Node；
- 用户能说清 Section 和独立 Node 的区别；
- 拒绝粒度建议不会损失内容或产生 Review Debt。

## 19.2 单一正文真相

- Orientation、Examples 与 Caveats 来自同一 Content Revision / Blocks；
- Node schema 不保存 Group membership 或 hierarchy placements；
- `source_support` 可由 Evidence Connections 重建；
- Edit Buffer、Recovery、Explicit Draft、Proposal 与 Current Revision 不混淆；
- reading projections 不产生不可编辑的影子正文。

## 19.3 Anchor

- Search 可直接打开 Node Anchor；
- Evidence 可精确指向 Anchor；
- Block move 后 Anchor 不失效；
- Split 后旧 Anchor redirect 到新 Node；
- 无法可靠定位时明确 ambiguous / orphaned；
- historical revision 可恢复原位置。

## 19.4 Reference / Embed

- Link、live excerpt、pinned excerpt 与 quote 更新语义不同；
- live excerpt 编辑进入 source Node；
- 引用不自动创建 Placement 或 Relation；
- 来源 Node 变化时影响可理解；
- offline 时已保存引用仍可用。

## 19.5 Split / Merge

- Split 预览 Blocks、Anchors、Evidence、Placements、Relations 与 downstream impact；
- Merge 先选择 canonical identity 并比较 Applicability；
- self-relation 不残留为正式边；
- old URL / Anchor / Saved Path / Answer 可解释；
- Undo 不删除变换后新增的独立内容。

## 19.6 Ask / AI

- 检索 chunk 不暴露为知识对象；
- Answer Claim 能回到 Node Anchor 与 Evidence；
- Merge learning 形成 block-level patch；
- AI 不整篇覆盖 user-owned content；
- Anchor re-location 不以相似度静默定案。
- Answer Claim 是 Run 内陈述，不因引用 Anchor 就获得 Node identity；Promotion 前不进入 Library、Placement 或正式 Relation。

## 19.7 退化

- AI unavailable 时正文、引用、Evidence 与历史可用；
- index corrupted 时 canonical Blocks 与 Anchors 不丢；
- 10,000 Blocks 仍可通过 outline、search 与 anchor 定位；
- 完整导出可以重建 content tree 和 anchor semantics；
- 阅读导出在其他工具中仍可读，不依赖专有 block ref 才成立。

## 19.8 Overview / Node 边界

- Overview 与 Node 可以共享 Block / Anchor 基础设施，但 `overview_id`、`node_id`、content revision 与正文分别存在；
- Overview Reference 的 Link / Live / Pinned / Quote 与 Node 间复用语义一致；
- Projection refresh 不创建 Node 或 Overview prose revision；
- Overview Support Map 可以落到 Node Anchor，但 Evidence endpoint 仍是 Node / Relation；
- 需要独立支撑、关系、状态或复用的 Overview Claim 可以无损提升为 Node，原 Anchor、Reference 与 History 可追溯。

## 19.9 Question Knowledge 正文与身份

- Question 的问题、Context、工作回答、criteria、remaining unknowns 与 history 可以连续阅读，不被强制拆成多张对象卡；
- QuestionResolutionRevision 只引用 exact Question / Knowledge Revision 与 Anchor，不复制 substantive answer；
- 用户在 Question 正文写下的回答可直接成为 basis，无需创建重复 Knowledge；
- Runtime Unknown、Gap Marker、Conflict、Annotation 与 Question Knowledge 不共用 identity；
- 同一核心未知的澄清形成 revision，实质改题形成 successor / split；
- Resolution、pause、conclude、reopen 与 target changes 不覆盖 canonical content history。

---

# 20. 研究依据与产品推论

## 20.1 W3C Selectors and States

W3C 的 Selectors and States 模型区分资源本身与对资源局部的 Selector；Text Quote Selector 使用 exact text 与前后文，Text Position Selector 使用 start / end，并明确单独依赖位置在资源变化后很脆弱，建议结合 State。模型还允许 selector refinement。[Selectors and States](https://www.w3.org/TR/selectors-states/)

本产品据此采用：

- Node identity 与 Node Anchor 分开；
- stable block id、text quote / context、revision position 组合定位；
- resolved / redirected / ambiguous / orphaned 状态；
- 历史 revision 帮助重定位，但不把“相似文本”冒充原位置。

## 20.2 Obsidian

Obsidian 官方帮助支持链接到 Note、Heading 与 Block，也支持嵌入具体 Heading / Block；同时明确 Block references 不是标准 Markdown，离开 Obsidian 不具有同等互操作性。[Internal links](https://obsidian.md/help/links) · [Embed files](https://obsidian.md/help/embeds)

本产品据此采用：

- Node 内部需要稳定局部引用；
- Heading / Block direct open 是真实使用需求；
- 完整导出必须包含可恢复 manifest 与标准 HTML / Markdown fallback；
- 专有 block reference 不能成为唯一可迁出语义。

## 20.3 Anytype

Anytype 官方文档把 Object 描述为最小可链接单位，同时允许一个 Object 由多个 Blocks 组成，并支持把选中的 Block 转成 Object。[Objects](https://doc.anytype.io/anytype-docs/getting-started/object-editor) · [Blocks](https://doc.anytype.io/anytype-docs/getting-started/object-editor/blocks)

本产品吸收两层分离：

- Node 是可链接、可维护的知识 identity；
- Block 是对象内部编辑结构；
- Section → Node Promotion 是显式知识身份变换；
- 每个 Block 都可移动，不等于每个 Block 都应成为知识节点。

## 20.4 Notion

Notion 官方资料说明 Synced Blocks 可以让同一内容在多个页面出现，并在一个位置修改后同步到其他位置；取消同步后副本独立。其设计文章把 Block 描述为可移动、转换或链接的基本内容单元。[Synced blocks](https://www.notion.com/help/synced-blocks) · [Designing Synced Blocks](https://www.notion.com/blog/designing-synced-blocks)

本产品不照搬 Synced Block，但吸收：

- 复用必须明确“同一内容”还是“独立副本”；
- 编辑同步内容时必须能看见其他使用位置；
- unsync / detach 是高语义动作；
- 删除原内容的下游影响必须预览。

## 20.5 产品推论边界

上述资料证明“对象与内部内容单元分开、局部引用、内容复用和显式提升”是成熟知识工具中的实际问题，不证明本合同的具体粒度规则已经通过用户验证。Node 判断、Anchor 修复和 Reference mode 仍需要真实任务测试。

---

# 21. 对后续视觉设计的约束

本合同不授权开始原型。未来视觉设计必须证明：

1. 长 Node 仍是连续文章，不退化为卡片墙；
2. D0 → D2 是同一正文逐步显露，不是三份摘要；
3. Block handles 只在编辑语境出现；
4. Search 命中深 Anchor 后能直接定位、取消高亮并返回；
5. Evidence 可以显示“支撑哪一段”，且一跳到 Source；
6. Link、live、pinned 与 quote 的更新语义可理解；
7. live excerpt 编辑不会让用户误改所有位置；
8. Section → Node Promotion 有内容、引用、Placement 与影响预览；
9. Node Merge 不是正文拼接，Applicability 与 identity compare 位于主判断路径；
10. Anchor redirected / ambiguous / orphaned 使用文字和恢复动作，不只用颜色；
11. 10,000 Blocks、1,000 references 与 AI unavailable 有真实可用状态；
12. 方向 3 的层级阅读承载连续正文与 section outline，方向 2 的关系空间只显示 Node / Group identities 与真实连接，不把每个 Block 画成图节点。
13. Overview 编辑态能够辨认 Editorial、Projection 与 Reference，但阅读态仍是一篇连续内容，不与 Node 知识卡片混淆。
14. Claim Promotion 显示 Node identity、Evidence / Applicability 迁移、原 Overview Reference 与 Anchor continuity。

---

# 结论

一个优秀知识库既不能把每句话拆成卡片，也不能把整篇文档当成无法引用的黑箱。

它需要四层清楚分工：

> **Node 保存可独立维护的知识 identity；Content Revision 保存这条知识在某次版本中的完整表达；Block 支持连续写作与内部结构；Anchor 让任意一处内容可以被精确引用、核验和演化。**

这使“从 Overview 深入到细节”真正成立：用户先进入一个稳定 Node，再按需展开完整论证，最后从某一段回到原始 Evidence；与此同时，同一知识可以被多处引用而不复制，AI 可以提出局部变化而不整篇重写，Split / Merge 也能保留历史而不破坏整个网络。
