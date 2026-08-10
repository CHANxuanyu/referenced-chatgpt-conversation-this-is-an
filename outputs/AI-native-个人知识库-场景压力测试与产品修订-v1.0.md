# AI-native 个人知识库

## 场景压力测试与产品修订 v1.0

> 日期：2026-08-06  
> 文档性质：产品定义验证、对象模型压力测试与修订决策；不是用户研究结论，不是视觉稿，不是原型  
> Canonical 产品定义：`AI-native-个人知识库-终局产品设计文档-v4.0.md`；本文档只保留压力测试与修订证据，不得反向改写 v4.0  
> 2026-08-07 历史边界：本文所有 Working-first、Accepted Revision、`current_accepted_revision_ref`与“完成并采用”直接写作场景均为已被推翻的历史测试模型；当前结果以 Buffer / Recovery / Current / Draft / Proposal / Sync / Projection 与 Direct Edit Commit 合同为准  
> 2026-08-09 Group State 历史边界：本文 Seed → Forming → Established → Evolving → Dormant 的线性场景是已被推翻的历史测试模型；当前应读作 Bare / Structuring / Oriented Presentation 与 Change / Attention / Lifecycle / Boundary overlays 的组合回归，完整规则见`AI-native-个人知识库-知识群状态演化与身份连续性合同-v1.0.md`  
> 2026-08-10 Relation Lifecycle 历史边界：本文把 Contested、Stale、Proposal 与 Relation lifecycle 混排的场景仅保留为缺口证据；当前回归必须分别验证 Candidate、Revision、Evidence、Challenge、Disposition、Change Condition、Lifecycle、Current / Suggested / History 与 Endpoint Transition。完整合同见`AI-native-个人知识库-关系陈述生命周期与网络可信性合同-v1.0.md`  
> 2026-08-10 认知科学场景深层覆写：本文的`认知科学与长期记忆`场景只保留为早期浅层压力测试；当前对象计数、真实论文条件、15 条 Knowledge、双 Placement、父子 Question、same-pair foundation / method 关系、research challenge 与 27 步回归以`AI-native-个人知识库-第二真实端到端夹具-概念学习、多语境复用与群关系-v1.0.md`为准；该新夹具仍不授权原型  
> 历史深层模型：`AI-native-个人知识库-产品定义-v3.0.md`  
> 交互基线：`AI-native-个人知识库-交互架构与设计系统-v1.0.md`
> 下游流程编排：`AI-native-个人知识库-产品流程板与组件状态图-v1.0.md`
> 后续核心体验复核：`AI-native-个人知识库-核心体验与知识群生命周期-v1.0.md`
> 后续知识深度与关系复核：`AI-native-个人知识库-知识深度与关系探索合同-v1.0.md`
> 后续知识群边界与跨群架构复核：`AI-native-个人知识库-知识群边界与跨群架构合同-v1.0.md`
> 后续知识节点粒度与内容组成复核：`AI-native-个人知识库-知识节点粒度与内容组成合同-v1.0.md`
> 后续 Overview 形成、编辑与更新复核：`AI-native-个人知识库-Overview形成编辑与更新合同-v1.0.md`
> 后续 AI 查询与知识回答复核：`AI-native-个人知识库-AI查询与知识回答合同-v1.0.md`
> 后续来源、证据与可追溯性复核：`AI-native-个人知识库-来源证据与可追溯性合同-v1.0.md`
> 后续直接创作、编辑与版本历史复核：`AI-native-个人知识库-直接创作编辑与版本历史合同-v1.0.md`
> 后续属性、Facet 与适用条件复核：`AI-native-个人知识库-属性Facet与适用条件合同-v1.0.md`
> 后续产品对象层级与身份治理复核：`AI-native-个人知识库-产品对象层级与身份治理合同-v1.0.md`

---

# 0. 为什么需要这轮压力测试

产品文档已经能够描述一个理想知识库，但“概念完整”不等于“遇到真实知识仍然成立”。本轮不增加功能清单，而是把同一套对象与流程放进三类差异很大的知识情境：

1. **学习研究型知识**：概念层级深、证据与争议重要、知识变化相对慢；
2. **产品实践型知识**：决策频繁变化、旧方向会被推翻、文档与设计必须同步；
3. **生活决策型知识**：来源权威不同、适用条件复杂、内容会过期，错误回答有实际代价。

如果产品只能服务其中一种，它就不是完整的个人知识库。

## 0.1 证据边界

本文使用以下标记：

- **[场景夹具]**：为验证产品模型构造的代表性资料，不是真实用户研究，也不证明具体事实；
- **[当前证据]**：来自本工作区现有产品文档、设计审查和本次真实产品方向变化；
- **[规格内通过]**：现有定义已经给出无明显矛盾的产品行为；
- **[规格缺口]**：现有定义无法唯一决定正确行为，或不同章节给出冲突答案；
- **[修订决定]**：本轮据此冻结的产品定义；
- **[待原型验证]**：行为已经定义，但必须以后用真实交互和内容验证可理解性。

生活决策场景中的机构、材料和规则只用于表现“来源、版本、条件、冲突”的数据形态，不构成法律、行政或租房建议。

## 0.2 通过门槛

每个场景必须同时通过：

1. 来源可以先安全进入，不被迫立即生成正式知识；
2. 系统能形成边界清楚的 Knowledge Group；
3. 用户可从 L1 Overview 经 L2 Topic、L3 Node、L4 Detail 到 L5 Evidence；
4. 同一 Node 在不同 Group 中不会被复制成相互漂移的版本；
5. Relation 有类型、方向、依据和适用条件；
6. Ask 能说明作用域、使用路径、证据、冲突与未知；
7. 新来源不会静默覆盖旧知识；
8. 过时、争议和证据不足不会被混为一种“低置信”；
9. 用户可以理解一次变化影响了哪些 Overview、Answer 和关系；
10. AI 不可用时，核心知识仍可浏览、搜索、编辑和核验。
11. Overview 只有一个 identity 和一棵正文树，结构刷新、AI 建议与阶段变化不会产生平行摘要。
12. Ask 区分问题与执行、Requested / Effective / Used Context、Claim basis、Coverage 和历史重评；回答与 Saved Answer 不递归成为当前事实。

---

# 1. 场景 A：认知科学与长期记忆

## 1.1 场景目标

用户持续学习记忆科学，希望理解“情境依赖检索、提取练习、间隔学习、遗忘与提示线索”之间的结构，并把其中一些原则连接到“AI Agent 长期记忆设计”。

这个场景检验：

- 深层概念层级；
- 主张与证据的对应；
- 学术争议与适用限制；
- 跨群复用；
- 从 Overview 到原始证据的连续性。

## 1.2 输入资料 [场景夹具]

| Source | 形态 | 主要内容 | 可信与版本特征 |
|---|---|---|---|
| A-S1 | 教科书章节 | 记忆编码、存储与提取的整体框架 | 适合 Overview，但不是每个具体结论的最新证据 |
| A-S2 | 实验论文 | 特定条件下的情境依赖检索效应 | 直接证据，样本与实验条件有限 |
| A-S3 | 综述论文 | 多类提取练习研究的综合 | 覆盖广，需要区分纳入标准与发表时间 |
| A-S4 | 课程笔记 | 用户自己的理解、类比和问题 | 是用户知识来源，但不能冒充原论文结论 |
| A-S5 | 新增反方研究 | 某种情境效应在另一条件下未复现 | 不自动推翻 A-S2，需要比较条件 |

## 1.3 期望知识结构

```text
Knowledge Group: 认知科学
  Topic: 记忆
    Topic: 编码与线索
      Node: 编码特异性原则 [Concept]
      Node: 情境依赖检索 [Concept]
      Node: 环境线索可提高特定条件下的回忆 [Claim]
    Topic: 学习策略
      Node: 提取练习 [Method]
      Node: 间隔学习 [Method]
    Topic: 争议与边界
      Node: 实验室效应能否稳定迁移到真实学习 [Question]
```

`Topic` 在这里承担的是当前知识群中的阅读结构；`Node` 承担可跨群复用、引用、修订和建立关系的知识身份。

## 1.4 L0–L5 走查

### L0 Atlas

“认知科学”显示为一个知识群，并与“AI Agent 产品设计”存在一条经过确认的 `provides_foundation_for` 群关系。关系解释不是“两个群内容相似”，而是存在多个被实际使用的桥接 Node，例如“检索线索”“工作记忆负担”“情境恢复”。

**结果：** [规格内通过] 当前定义已禁止用向量相似度直接产生正式群关系。

### L1 Group Overview

Overview 需要说明：群边界、主要主题、已经较稳定的知识、正在争议的结论和进入路径。A-S5 进入后，Overview 的“情境效应”段落应出现更新建议，而不是整篇重新生成。

**结果：** [规格内通过] Overview Diff 与用户锁定段落已有定义。

### L2 Topic Structure

用户进入“记忆 / 编码与线索”，看到父级、同级、子主题、代表 Node 和当前缺口。

**结果：** [规格缺口] 交互规格使用 `Topic`，Selection State 也有 `topic_id`，但产品顶层对象模型没有定义 Topic；无法回答它是否有身份、版本、Overview、关系和历史。

### L3 Knowledge Node

打开“情境依赖检索”，看到定义、当前群语境、关键主张、关系、其他出现位置和证据预览。

**结果：** [规格内通过] Canonical Node + Placement 能保持跨群身份。

### L4 Deep Detail

用户深入理解机制、实验条件、反例和真实应用限制。

**结果：** [规格缺口] `KnowledgeNode.epistemics` 只有 status、confidence、support 和 conflicts，不能结构化表达“这条主张仅对哪些参与者、任务、环境和时间成立”。

### L5 Evidence

用户打开 A-S2 的具体实验段落，同时看到方法上下文；A-S4 用户笔记被明确标为二次解释。

**结果：** [规格内通过] Source Reader 已要求区分原文、OCR、转写与翻译，但需要新增“证据角色”以区分直接证据、二次综合和用户解释。

## 1.5 Ask 压力测试

用户问：

> “换一个环境复习，一定会降低记忆效果吗？”

合格回答必须：

- 不把某个实验条件外推为普遍规律；
- 显示 Query Scope 为“认知科学 / 记忆”；
- 使用 Concept、Claim、A-S2、A-S3 与 A-S5；
- 把“适用条件不同”与“来源互相矛盾”区分开；
- 允许进入“实验室效应能否迁移”这个 Question Node；
- 提供 A-S2 和 A-S5 的条件对照，而不是只按来源数量投票。

**结果：** [规格缺口] Query Scope 目前只有知识范围，没有时间、知识状态、适用条件和来源政策，无法稳定产生上述回答。

## 1.6 跨群探索

“情境依赖检索”在两个位置出现：

```text
认知科学 / 记忆 / 编码与线索
AI Agent 产品设计 / 长期记忆 / Context Reconstruction
```

用户从认知科学切换到产品设计时：

- canonical content 不变；
- contextual summary 改为“为什么 Agent 恢复上下文需要有效检索线索”；
- 关系邻居从实验概念切换为 Resume Brief、Working Set 与 Retrieval Policy；
- 返回时恢复原研究阅读位置。

**结果：** [规格内通过] 当前 Placement 与 Selection State 能表达，但需要把 Topic 正式纳入对象模型。

## 1.7 新来源影响

A-S5 不应直接将原 Claim 标为错误。系统先比较：

- 研究对象；
- 任务类型；
- 实验环境；
- 干预方式；
- 测量指标；
- 有效时间与版本。

如果条件不同，系统建立 `qualifies` 或生成更窄的新 Claim；只有相同条件下结论不兼容，才进入 `Contested` 认识状态。

**结果：** [修订决定] Claim 与 Relation 必须支持结构化 Applicability，而不是只拥有自由文本 scope。

---

# 2. 场景 B：AI Agent 产品设计方向演化

## 2.1 场景目标

用户曾讨论 Personal Cognitive OS、Project Continuity 和 Resume Brief，随后明确修正方向：产品本质上应是一个具有知识群、丰富层级、关系、AI 查询与网络探索的个人知识库。

这是当前工作区已经真实发生的产品方向变化，用于检验：

- Decision 的 supersede 与历史保留；
- 多版本文档之间的 Source Truth；
- 最新用户意图的权威优先级；
- 产品定义与设计稿双向同步；
- 保存回答能否区分“当时正确”与“现在仍正确”。

## 2.2 输入资料 [当前证据]

| Source | 内容角色 | 预期处理 |
|---|---|---|
| Personal-Cognitive-OS 旧文档 | 旧产品方向与完整系统设想 | 保留为历史 Source，不作为当前默认方向 |
| Project Continuity PRD | 某一使用场景的完整定义 | 降级为项目型知识群或派生 View |
| 用户最新方向表达 | 当前产品意图 | 高权威 Decision Source |
| AI-native 个人知识库产品定义 v3.0 | 当前 Knowledge Truth | canonical 产品定义 |
| Ardot 七张设计探索 | 视觉概念证据 | 保留方向气质，不代表完整流程 |
| 交互架构与设计系统 v1.0 | 当前交互定义 | 设计与产品同步基线 |

## 2.3 期望知识结构

```text
Knowledge Group: AI-native 个人知识库产品设计
  Topic: 产品方向
    Decision: 产品本质是个人知识库 [Accepted, current]
    Decision: Project Continuity 定义整个产品 [Superseded]
  Topic: 产品本体
    Node: Knowledge Group [Concept]
    Node: Semantic Zoom [Principle]
    Node: Source Truth / Knowledge Truth [Principle]
  Topic: 核心交互
    Node: Selection State [Concept]
    Node: Dual Lens [Principle]
    Node: Ask enters the network [Principle]
  Topic: 设计证据
    Source: Ardot Screen 1–7
    Finding: 当前只是概念册，不是完整产品设计 [Claim]
```

## 2.4 方向纠正走查

当最新用户意图进入时，系统不能：

- 删除旧文档；
- 把旧文档里的全部细节判为错误；
- 继续把 Project Continuity 当作产品北极星；
- 创建两个互不相干、同名的产品节点；
- 让旧 Ask 结果看起来仍是当前结论。

系统应：

1. 创建新的 Decision revision；
2. 将旧方向标为 `superseded`，并保留“为何当时产生”；
3. 将仍有价值的能力重挂到项目型知识群或派生 View；
4. 对产品 Overview 生成局部 Diff；
5. 标记七张设计图中受方向变化影响的结构；
6. 对引用旧方向的保存 Answer 标记“基于旧知识版本”；
7. 允许用户查看当时答案，或按当前知识重新评估。

**结果：** [规格缺口] 当前文档定义了 supersede 和 correction propagation，但没有定义 Saved Answer 的冻结版本与动态重算模式。

## 2.5 文档—设计同步走查

当一级导航由六个入口收敛为五个地点后：

- 产品定义 §15 必须改变；
- App Shell 与导航组件必须改变；
- 81 项覆盖中的入口路径必须检查，尤其包含直接创作、迁移与恢复；
- 旧 Ardot Screen 里的导航不能继续作为真实产品结构；
- 验收流程必须从 Home、Library 或 Atlas 重新起步。

**结果：** [规格内通过] Coverage Matrix 已经建立，但仍缺少“变更影响对象”的可执行记录格式。

## 2.6 Ask 压力测试

用户问：

> “为什么这个产品最终不是 Project Continuity 工具？”

合格回答至少包含：

- 当前结论；
- 方向变化的时间顺序；
- 最新用户意图与旧文档的权威区别；
- 被保留的 Project Continuity 能力；
- 当前产品定义与设计审查证据；
- “截至当前知识”标签。

如果用户把时间范围切换为“方向修正之前”，系统应能给出当时的答案，而不是把历史视角当作事实错误。

**结果：** [修订决定] Query 必须支持 `as_of`，Saved Answer 必须保存 Knowledge Snapshot，并允许显式 Re-evaluate。

## 2.7 Group 类型压力

“AI Agent 产品设计”同时具有 Domain、Practice、Project 特征。旧模型只有一个 `group_kind`，可能迫使用户在错误抽屉中三选一。

**结果：** [修订决定] Group 使用一个 `primary_kind` 决定默认 Overview 模板，同时允许多个 `facets` 表达其附加性质。类型服务默认体验，不成为本体限制。

---

# 3. 场景 C：法国租房与入住房手续

## 3.1 场景目标

用户需要组织住所合同、担保材料、保险、付款、机构网页、邮件和个人清单，并在某个具体日期回答“我现在还缺什么”“这份要求是否适用于这个住所”。

这个场景检验：

- 来源权威和版本；
- 有效时间与适用对象；
- 同名实体消歧；
- 条件差异造成的伪冲突；
- 来源失效后的知识状态；
- AI 不应把通用资料覆盖具体合同。

## 3.2 输入资料 [场景夹具]

| Source | 形态 | 例示内容 | 风险 |
|---|---|---|---|
| C-S1 | 某机构官方指南快照 | 通用办理条件 | 网页以后可能更新 |
| C-S2 | 某住所合同 PDF | 该住所的具体义务 | 对当前合同更具体，但只适用于该住所 |
| C-S3 | 住所运营方邮件 | 某次入住要求与截止时间 | 可能晚于合同附件，需保留发送时间 |
| C-S4 | 用户付款记录 | 已完成的实际动作 | 不等于机构已确认收到 |
| C-S5 | 旧年度清单 | 过去一次办理经验 | 容易被误当成当前规则 |
| C-S6 | 新版官方指南 | 修改后的通用要求 | 应触发影响分析而非静默替换 |

## 3.3 期望知识结构

```text
Knowledge Group: 法国租房与入住房手续
  Topic: 当前住所
    Entity: Residence A
    Event: 入住日期
    Claim: Residence A 要求在日期 D 前提供材料 X
    Event: 材料 X 已发送
    Question: 运营方是否已确认接收
  Topic: 担保与资格
    Entity: Guarantee Service A
    Claim: 条件 Y 适用于申请人类别 Z 与有效期 T
  Topic: 保险与付款
    Entity: Insurance Contract B
    Event: 首笔费用已支付
  Topic: 历史记录
    Source: 旧年度清单
```

## 3.4 适用条件走查

以下两句话可能同时成立：

- 通用指南说材料 X 在某类申请中可选；
- Residence A 的合同说该住所入住前必须提供材料 X。

如果系统只有 Claim 文本和 `confidence`，它可能把二者判为冲突或给出错误的统一答案。正确模型需要保存：

```text
Applicability
  jurisdiction?
  organization?
  subject_type?
  subject_ref?
  location?
  conditions[]
  valid_from?
  valid_to?
  observed_at
  source_precedence_reason?
```

**结果：** [规格缺口] 现有 Node 和 Relation 尚无这套限定结构。

## 3.5 Ask 压力测试

用户问：

> “入住前还需要准备什么？”

系统必须先明确或继承：

- 哪个住所；
- 哪个入住日期；
- 针对哪个申请人；
- 是否只查询已接受的当前知识；
- 是否包括尚未确认的邮件要求；
- 是否允许使用过期历史经验。

回答结构应区分：

1. 已明确需要；
2. 可能需要但条件未确认；
3. 已完成但未被对方确认；
4. 来源存在冲突或版本变化；
5. 当前知识库仍缺什么材料。

**结果：** [修订决定] Query Context 不能只有范围，必须同时保存 focus、as-of、status filter、applicability bindings 与 source policy。

## 3.6 来源变化与过期

C-S6 进入后：

- C-S1 仍保留为历史版本；
- 由 C-S1 派生的 Claim 标为“需要复核”，不是自动删除；
- 若 C-S2 对当前住所仍然有效，具体合同要求不会被通用指南覆盖；
- Overview 只更新受影响的“通用条件”部分；
- 已保存的旧办理清单显示当时知识版本；
- 当前 Ask 默认使用 C-S6 和仍有效的 C-S2/C-S3。

**结果：** [规格缺口] 当前 Node 把 `Contested`、`Superseded`、`Stale` 与 `Low evidence` 放在同一状态列表，无法表达“内容仍被接受，但因为来源更新而需要复核”。

## 3.7 Source 丢失

若 C-S3 邮件权限丢失：

- 邮件来源显示 unavailable；
- 由它支持的 Claim 不被删除；
- Evidence 状态变为不可复核；
- Ask 默认降低该 Claim 的证据说明；
- 用户可以补充快照或替代来源；
- 之后恢复权限时重新校验定位和版本。

**结果：** [规格内通过] 当前 Source Reader 与 local knowledge store 已支持保留知识并降低可核验状态，但需要把这种影响映射到正交状态轴。

## 3.8 Capture 压力测试

用户可能只想先保存一份合同，暂时不希望 AI 拆解或提出几十个节点。

当前五步 Capture 容易被理解为必须完成 Knowledge Proposal 才能提交。

**结果：** [修订决定] Source 可以独立 Commit。用户可选择“仅保存来源并索引”“稍后生成提案”或“现在审查知识提案”；来源进入不以知识编译完成为前提。

---

# 4. 跨群 Atlas 压力测试

## 4.1 代表性群

```text
认知科学
AI-native 个人知识库产品设计
法国租房与入住房手续
```

它们不应因为都包含“证据”“时间”或“记忆”几个词就被全部连起来。

## 4.2 合格的群关系

### 认知科学 → AI 产品设计

```text
provides_foundation_for
```

依据：多个桥接 Node 和已保存路径共同表明，检索线索、认知负担与情境恢复被实际用于产品原则。

### AI 产品设计 → 法国租房知识群

不默认创建产品领域关系。只有当用户把“来源版本与适用条件”作为跨场景方法复用，并形成正式 Method Node 时，才可以显示：

```text
Method: 条件化证据判断
  applies_to → AI 知识维护
  applies_to → 行政与合同要求判断
```

这更适合表现为共享方法带来的桥接，而不是声称两个知识群在主题上相关。

## 4.3 群关系生成门槛 [修订决定]

正式群关系至少需要满足一项：

1. 用户明确创建或固定；
2. 存在被实际使用的 typed cross-group path；
3. 多个高价值 canonical Nodes 在两个群中承担明确角色；
4. 一个群的 Overview、Decision 或 Method 明确引用另一个群；
5. 可靠来源直接表达群级依赖。

以下不足以生成正式群关系：

- 单一共享标签；
- 单一低价值共享 Node；
- embedding 相似；
- 同一来源偶然提到两个主题；
- 用户一次性从一个群跳到另一个群。

Atlas 默认显示的是“可解释的知识地形”，不是统计相关网络。

---

# 5. 五条核心产品流程复核

## 5.1 建立知识

```text
Capture Source
  → Source Commit
  → Parse / Index
  → Optional Knowledge Proposal
  → User or rule-based acceptance
  → Group / Topic / Node / Relation updates
  → Overview Diff
```

关键修订：Source Commit 与 Knowledge Commit 解耦；解析失败不应阻止来源保存。

## 5.2 从 Overview 深入证据

```text
L0 Group
  → L1 Scope Overview
  → L2 Topic
  → L3 Canonical Node in current Placement
  → L4 Deep Detail
  → L5 Evidence Fragment in Source version
```

关键修订：Topic 成为有稳定身份和历史的结构对象；Overview 可以属于 Group 或 Topic，而不是只属于 Group。

## 5.3 沿关系跨群探索

```text
Current Node
  → typed Relation
  → bridge Node / target Node
  → choose target Placement
  → switch Group context
  → preserve return stack
```

关键修订：跨群关系需要解释桥接依据；选择目标 Node 后不能自动替用户决定进入哪个群语境。

## 5.4 AI 查询知识

```text
Question
  + Knowledge Scope
  + Focus
  + As-of
  + Status Filter
  + Applicability Bindings
  + Source Policy
  → Retrieval Route
  → Direct Answer
  → Evidence / Conflict / Unknown
  → Explore or Save
```

关键修订：Scope 不再等同于完整 Query Context。

## 5.5 新来源改变旧知识

```text
New Source Version
  → compare validity and applicability
  → affected Claim / Relation set
  → state-axis changes
  → Overview Diff
  → Saved Answer impact
  → Review only when judgment is needed
  → commit / undo
```

关键修订：先比较条件，再判断冲突；保存的回答保留当时快照，并可按当前知识重新评估。

---

# 6. 本轮发现的结构缺口

| ID | 缺口 | 后果 | 严重度 |
|---|---|---|---|
| G-01 | Topic 在交互中存在、对象模型中缺席 | L2 无身份、版本、Overview 和历史定义 | P0 |
| G-02 | Overview 默认绑定 Group | Topic 级导航只能变成目录，无法提供局部地形 | P0 |
| G-03 | Claim / Relation 缺少 Applicability | 条件不同的结论被误判为冲突或被错误泛化 | P0 |
| G-04 | Query 只有知识范围，没有完整 Context | 时效、对象、来源政策无法稳定控制回答 | P0 |
| G-05 | Node 状态混合多个维度 | 无法区分被替代、证据不足、有争议和过时 | P0 |
| G-06 | Saved Answer 只有生成时间和引用 | 无法解释旧答案为何变化，也无法可靠重算 | P0 |
| G-07 | Capture 暗示必须走完 Proposal | “先收进来，之后整理”的核心低负担承诺被破坏 | P0 |
| G-08 | Group 只有一个 kind | 跨 Domain / Practice / Project 的群被迫错误归类 | P1 |
| G-09 | 群关系缺少形成门槛 | Atlas 很快退化成相似度 hairball | P0 |
| G-10 | Evidence 角色不明确 | 用户笔记、综述与直接证据可能被等同处理 | P1 |
| G-11 | 文档—设计同步只有原则，没有影响记录对象 | 变更容易只改一个页面或一份文档 | P1 |
| G-12 | Subgroup 被引用但没有对象与生命周期 | 群内层级、独立范围和群关系互相混淆 | P0 |
| G-13 | Group Membership、member refs 与 Placement 重复表达归属 | 移动或删除后可能产生多份冲突真相 | P0 |
| G-14 | Topic 同时维护 parent 与 child refs | 深层移动后可能残留错误祖先结构 | P0 |
| G-15 | Topic Promotion 与 Group Merge 缺少 identity / redirect 合同 | 旧路径、Saved Path、Overview 和关系失去解释 | P0 |

---

# 7. 冻结的产品修订

## 7.1 Topic / Knowledge Branch 成为用户可理解对象

Topic 是某个 Group 内的稳定结构对象：

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

规则：

- Topic 组织 Placements，不拥有 canonical Node 正文；
- 同一 Node 可以出现在多个 Topic；
- 删除 Topic 只移除结构位置，不删除 canonical Node；
- Topic 可以改名、移动、拆分、合并并保留历史；
- Topic 可以有局部 Overview、Question 和知识缺口；
- Topic 默认只在所属 Group 内有意义，不自动成为全局语义节点。
- Topic 只保存一个直接父级，children、ancestors 与 breadcrumb 由系统推导；
- Topic 不采用多父 DAG，同一 Node 的多重语境由 Placements 表达；
- Topic 成为独立 Group 后保留 Gateway、旧路径和历史，不复制 Node、Evidence 或 Source。

## 7.2 Overview 改为 Scope Overview

```text
Overview
  overview_id
  scope_ref: Space | Group | Topic | Saved Path
  orientation
  structure
  synthesis
  coverage
  conflicts
  unknowns
  source_snapshot
  revision_history
  locked_fragments[]
```

L0 的 Space Overview、L1 的 Group Overview、L2 的 Topic Overview 共享一套维护逻辑，但信息密度和表达不同。

## 7.3 Applicability 成为 Claim 与 Relation 的组成部分

```text
Applicability
  subject_type?
  subject_refs[]
  organization_refs[]
  location?
  jurisdiction?
  conditions[]
  valid_from?
  valid_to?
  observed_at
  exceptions[]
```

系统在声明“冲突”前必须比较 Applicability；条件不同的主张优先形成 `qualifies`、更窄 Claim 或并列适用分支。

## 7.4 对象、版本、编辑与知识状态改为正交轴

第一轮已经确认认识状态、时效与来源可用性不能压成一个 `low confidence`；后续直接创作复核进一步确认，`draft / accepted / superseded / archived` 本身也混合了对象 lifecycle、identity standing、current Accepted pointer 与尚未完成的编辑。修订模型为：

```text
NodeState
  object_lifecycle: active | archived | trashed | tombstoned
  identity_standing: canonical | redirected | merged | split_lineage
  current_accepted_revision_ref?: RevisionRef
  working_state: none | local_only | sync_queued | synced | conflicted
  proposal_state: none | proposed | partially_applied | stale | rejected
  epistemic: supported | evidence_limited | contested | unknown
  freshness: current | review_due | stale
  availability: available | source_degraded | source_unavailable
```

一个 active Node 可以同时有 Accepted Revision 7、已保存到本机但尚未采用的 Working Branch、`supported`、`review_due` 与 `source_degraded`。这比 `accepted + supported + review_due + source_degraded` 更进一步：它还能解释用户当前读到哪一版、未完成修改是否安全、是否已经同步，以及哪个动作才会改变当前知识。

## 7.5 Query Context 扩展

```text
QueryContextSnapshot
  requested
    scope_anchors[]
    expansion_policy
    current_focus?
    knowledge_as_of?
    valid_at?
    status_filter
    applicability_bindings{}
    source_policy
    external_knowledge_policy
    excluded_refs[]
  effective
    resolved_scope_refs[]
    resolved_applicability{}
  used
    node_revision_refs[]
    relation_revision_refs[]
    evidence_fragment_refs[]
    source_revision_refs[]
  coverage
    index_state
    unavailable_refs[]
```

回答前显示 Requested，回答后可检查 Effective 与 Used Context；如果缺少决定性条件，应先提一个必要问题或给出分支答案，不能假设用户身份、地点或日期。

## 7.6 Saved Answer 双模式

每个保存回答包含：

```text
SavedAnswer
  query_turn_ref
  query_run_ref
  requested_context
  effective_context
  answer_snapshot_ref
  knowledge_revision_set
  route_snapshot
  evidence_snapshot
  generated_at
  impact_state
```

用户可以：

- **View original**：查看当时答案与当时依据；
- **Re-evaluate now**：使用当前知识重新生成，并展示与原答案的差异；
- **Pin as historical**：明确作为当时决策或研究记录保存；
- **Merge learning**：把稳定的新理解提交为 Node，而不是让 Answer 本身成为事实。

Saved Answer 默认不进入当前事实检索；Re-evaluate 创建新 Query Run 与 Answer Snapshot，并比较 Claims、support、unknown、coverage 与 Context，不覆盖 Original。

## 7.7 Capture 双提交

Capture 必须区分：

1. **Source Commit**：安全保存来源、元数据、版本与索引状态；
2. **Knowledge Commit**：接受 Node、Relation、Placement 与 Overview 变更。

用户可以只完成第一步。Knowledge Proposal 可以现在生成、后台生成或永不生成。

## 7.8 Group 类型使用 primary kind + facets

```text
GroupClassification
  primary_kind_ref
  facet_refs[]
  property_profile_ref?
```

Primary Kind 决定默认 Overview 和建议结构；Facets 支持一个群同时具有 Domain、Practice、Project、Entity 或 Inquiry 特征。三者都引用稳定 Definition identity；Property Profile 只提出按需属性建议，不制造必填 schema，也不因为 Facet 被移除而删除既有值。

## 7.9 Evidence 五轴与 Binding

Evidence Fragment 只保存 Source Revision、Representation、Selector Bundle、内容 / 上下文快照和 provenance，不拥有全局“支持 / 反驳”角色。片段与具体 Node Anchor、Relation statement、Overview / Answer Claim 的作用由 Evidence Binding 保存。

五个正交维度分别回答：

1. Material Origin：谁产生材料；
2. Derivation Distance：primary record、quote、transformed、secondary、synthesis 或 inference；
3. Support Role：supports、challenges、qualifies、defines、exemplifies、provides method / context 等；
4. Extraction Fidelity：native、OCR、transcript、translation、summary 或 inference；
5. Verification State：当前能否从 original / snapshot 精确核验。

这些轴都不是质量分数。系统仍需结合具体 Claim、方法、适用条件、版本、反证和用户判断解释证据强度。完整合同见 `AI-native-个人知识库-来源证据与可追溯性合同-v1.0.md`。

## 7.10 Change Set

产品和知识结构中的每次批量变化都形成 Change Set：

```text
ChangeSet
  trigger
  changed_objects[]
  affected_overviews[]
  affected_saved_answers[]
  affected_views[]
  review_items[]
  committed_by
  committed_at
  undo_lineage
```

它既服务知识维护，也为产品文档与设计文件的同步提供同一种“影响范围”思维。

## 7.11 知识形成不是强制产出

来源、用户原创 Working content、AI Query Result 与 Accepted knowledge 保持不同落点；Placement 独立表达归类。一份 Source 完整解析后可以零 Node 成功；用户快速输入可以成为无 Placement、无 Accepted Revision 的 Working Node；AI Candidate 必须经过 identity、Applicability、knowledge difference 与 Proposal Bundling，不能按片段直接进入 Review。

一次默认只呈现 3–7 个高价值决策包。大型导入的成功标准是来源安全、重复受控、映射可信和当前知识可继续使用，不是一次性把全部材料“知识化”。完整合同见 `AI-native-个人知识库-知识形成与维护循环-v1.0.md`。

## 7.12 Node 粒度与内部定位不能含糊

三类场景共同暴露四个此前没有充分冻结的结构风险：

1. **[规格缺口] 重复正文真相**：如果 Node 同时保存 definition、summary、overview、detail 与 body，产品无法决定新证据应该修改哪一份；
2. **[规格缺口] 碎片化**：如果每个段落、Heading 或 AI chunk 都自动成为 Node，研究论证、产品 rationale 和办事条件都会退化为卡片堆；
3. **[规格缺口] 无精确落点**：如果 Search、Ask 与 Evidence 只能打开整条 Node，长知识无法证明一句结论的依据，也无法在返回时恢复位置；
4. **[规格缺口] 复用语义混合**：如果 Link、同步内容、固定版本和原文引用都叫 Embed，更新会静默改变历史语境。

**[修订决定]** Node 是最小可独立理解、维护与复用的知识身份；Block 是同一 Content Revision 内的写作单元；Anchor 是稳定局部 locator。D0–D2 从同一内容树投影，Evidence 可指向 Node Anchor，跨 Node 复用必须显式选择 Link / Live / Pinned / Quote。完整合同见 `AI-native-个人知识库-知识节点粒度与内容组成合同-v1.0.md`。

## 7.13 Overview 不能重新制造第二套知识真相

三类场景进一步暴露四个风险：

1. **[规格缺口] 重复概览字段**：Orientation、Structure、Synthesis、summary 与 AI preview 如果分别保存文字，会在来源变化后互相矛盾；
2. **[规格缺口] 动态内容和正文混合**：Topic 数、代表 Nodes、最近变化与编辑性判断混在一篇 generated prose 中时，系统只能整篇重写；
3. **[规格缺口] 治理维度合并**：`user-owned / AI-owned / locked` 不能同时回答谁写的、怎样更新、能否编辑和当前是否仍一致；
4. **[规格缺口] 影子 Claim**：如果 Overview 中的独立结论可以被 Answer 当作 Evidence，却没有 Node identity、Applicability、历史和来源，就会形成无法核验的第二知识层。

**[修订决定]** 每个 Space / Group / Topic / Saved Path 至多有一个 canonical Overview identity 和一棵连续 content tree。Editorial、Projection、Reference、Navigation、Status 是 Block 类型；Orientation、Structure、Synthesis 只是阅读语义区。Projection 根据当前知识刷新，accepted Editorial prose 只经 Semantic Diff 修改。authorship、update policy、lock 与 alignment 正交；Overview Anchor 使用 Support Map 解释依据，但正式 Evidence endpoint 仍是 Node / Relation。可独立核验、引用、建立关系或复用的 Claim 必须“保存为独立知识”。完整合同见 `AI-native-个人知识库-Overview形成编辑与更新合同-v1.0.md`。

## 7.14 AI Query 不能成为第二知识库

三类场景继续暴露七个风险：

1. **[规格缺口] 问题与执行混合**：同一问题重试、追问或按当前知识重评时，旧答案会被覆盖；
2. **[规格缺口] 范围事实混合**：用户要求、系统扩大和最终实际使用对象只有一个 Scope 标签；
3. **[规格缺口] 回答只有统一引用**：无法判断每条结论来自用户知识、来源原文、外部资料还是推论；
4. **[规格缺口] 负面回答越界**：当前 Group 未命中、索引不完整和全库不存在可能被写成同一句话；
5. **[规格缺口] 追问递归污染**：上一条 AI Answer 进入下一轮 Context，错误绕开 Knowledge Commit 被反复强化；
6. **[规格缺口] Saved Answer 回流**：历史生成文本可能默认与当前 accepted Nodes 竞争；
7. **[规格缺口] Save 后果混合**：回答、Node、Relation、Overview 和 Source 被一个 Save 动作处理。

**[修订决定]** Query Session、Turn、Run、Context Snapshot、Answer Snapshot 与 Knowledge Snapshot 分开；Requested / Effective / Used Context 分开；每个主要 Answer Claim 映射 basis、support role 和精确 locator；Coverage 单独表达；Follow-up 显示 Context Delta 且重新回到原始 Knowledge / Evidence；Saved Answer 默认不参与当前事实查询；Re-evaluate 新建 Run 和 Answer Snapshot；八类 Transform 具有不同对象后果。完整合同见 `AI-native-个人知识库-AI查询与知识回答合同-v1.0.md`。

---

# 8. 规格回归验收

## 8.1 Topic 回归

**Given** 同一 Node 出现在两个 Group、三个 Topic  
**When** 用户移动、重命名或删除其中一个 Topic  
**Then** canonical Node 与其他 Placements 不改变，Topic 历史可追溯，Group Overview 只更新受影响结构。

## 8.2 条件化 Claim 回归

**Given** 两条结论文本不同但 Applicability 不同  
**When** 新来源进入  
**Then** 系统不会直接标为冲突，先显示条件对照并建议限定或拆分 Claim。

## 8.3 状态轴回归

**Given** 一个 Accepted Claim 的唯一 Source 暂时失效  
**When** 用户打开 Node 或 Ask  
**Then** lifecycle 仍为 accepted，availability 变为 source_unavailable，epistemic 反映证据影响，并提供补充来源入口。

## 8.4 Historical Ask 回归

**Given** 一个保存回答引用的 Decision 已被 supersede  
**When** 用户打开旧回答  
**Then** 显示原始快照、知识变化提示和 Re-evaluate now；不会静默把旧正文替换为新答案。

## 8.5 Source-only Capture 回归

**Given** 用户添加一份大型 PDF  
**When** 用户选择“仅保存来源”  
**Then** Source 立即进入 Registry，解析可后台继续，不创建 Working Nodes 或 Accepted knowledge，不产生 Review Debt，稍后可从 Source Detail 启动 Knowledge Proposal。

## 8.6 Atlas 关系回归

**Given** 两个 Group 仅共享一个低价值标签  
**When** Atlas 生成默认群关系  
**Then** 不显示正式边；用户查看候选时可以看到共享依据不足。

## 8.7 Topic Overview 回归

**Given** 一个 Group 有五层 Topic 结构  
**When** 用户进入第三层 Topic  
**Then** 显示该 Scope 的 Orientation、Structure 与知识缺口，同时保留父级路径和代表 Nodes；不重复生成一篇与 Group Overview 相同的长摘要。

## 8.8 Knowledge Route 忠实度回归

**Given** 法国租房 Ask 同时使用两个没有 formal Relation 的 Nodes  
**When** Answer 显示使用路径  
**Then** 两个 Nodes 分别支撑对应结论，retrieval jump 标明“本次回答中一起使用”；不创建 `related_to`，关闭 Answer 后长期图无新增正式边。

## 8.9 三维深入回归

**Given** 用户在“情境依赖检索”Node 阅读机制说明，并查看直接关系  
**When** 展开一条跨群 Path  
**Then** Scope 仍是当前 Node，正文深度和滚动位置不变，只扩展 Relation Radius；Back 恢复原邻接集合。

## 8.10 无归属快速记录回归

**Given** 用户当前不在任何 Group  
**When** 全局写下一条自己的想法  
**Then** 建立没有 Accepted Revision 的 user-authored Working Node，不要求 Source 或 Placement；durable local Working Checkpoint 同时可从 Library 的“未完成”和“未归类”两个独立 View 找回，且不会产生 Review Debt。只有“完成并采用”才创建 current Accepted Revision。

## 8.11 Zero-yield 回归

**Given** 一份来源已经完整解析但没有值得改变现有知识的内容  
**When** Compiler 完成  
**Then** 显示“没有发现值得形成知识的变化”；Source 仍可读、可搜，不创建空 Node、Topic、Relation 或 Review Item，并与 parse incomplete 状态区分。

## 8.12 Identity Resolution 回归

**Given** 新材料与既有 Node 名称相同但适用条件不同  
**When** 系统比较 identity  
**Then** 用户可以选择补证、更新、增加 Placement、创建独立 Node 或只保留 Source；界面显示定义、条件与影响，不用单一置信度直接合并。

## 8.13 大型导入回归

**Given** 用户导入 300 份来源  
**When** 样本解析与候选分组完成  
**Then** Source Commit 逐项保留，默认只出现 3–7 个 Decision Bundles，其余候选可解释地归并，批次部分失败和 Apply to similar 均可预览并撤销。

## 8.14 用户纠正传播回归

**Given** 用户纠正 AI-assisted Node 解释  
**When** 新 revision 保存  
**Then** 下游 Overview Projection 按规则刷新，accepted Editorial prose 只形成 Semantic Diff / alignment notice，Saved Answer original 保持不变，且相同错误无新依据不再生成。

## 8.15 “知识模型”保持 Topic

**Given** “知识模型”在“AI Agent 产品设计”中拥有大量 Nodes，但边界、使用意图和主要问题仍依赖父 Group  
**When** 系统评估结构  
**Then** 保持 Topic，不因数量或 embedding 聚类建议独立成 Group；它可有深层子 Topic、局部 Overview 与跨群 Node Placements。

## 8.16 “长期记忆系统”提升为 Group

**Given** “长期记忆系统”形成独立边界、多条主要分支、独立来源范围与反复单独 Ask  
**When** 用户接受“成为独立知识群”并选择 Placements share  
**Then** 创建新 Group，原 Topic 成为 Gateway，Node identity 与 Evidence 不复制，旧 Saved Path 可继续打开，并建立准确的 `scope_within` / `applies_to` 群关系。

## 8.17 同一 Node 三个 Placements

**Given** “情境依赖检索”分别在“认知科学”“长期记忆系统”“AI Agent 产品设计”承担理论、机制和产品应用角色  
**When** 用户从 Search 和不同 Group 打开它  
**Then** 始终是一个 canonical Node；三个 Placements 显示不同 contextual summaries；canonical edit 影响全部，contextual edit 只影响当前位置。

## 8.18 法国租房深层 Topic

**Given** “法国租房 / 资格与文件 / 担保 / Visale”形成四层路径  
**When** 用户从 Search 直接进入 Visale 下的 Node  
**Then** Topic 只保存直接 parent，DepthTrail 完整恢复；层级深度本身不触发强制拆 Group。

## 8.19 Group Merge 与 identity 分离

**Given** “Agent 产品设计”和“AI Agent 产品”被确认是同一 Group  
**When** 用户选择 canonical Group 并预览 Merge  
**Then** 两棵 Topic roots 先并列保留，boundary / Overview / Relations 做 diff，旧 Group 建 redirect；疑似重复 Nodes 进入独立 Identity Resolution，不被批量自动合并。

## 8.20 共享标签不形成群关系

**Given** “认知科学”和“法国租房”都包含 Evidence 类型的 Nodes  
**When** Atlas 构建 Group Relation  
**Then** 不因共享对象类型、标签或来源格式画边；只有存在可解释的 typed bridge paths 时才提出 Proposal，接受前不进入默认 Atlas。

## 8.21 长 Concept 与短 Decision 回归

**Given** “情境依赖检索”包含多节机制与限制，而“全局只展示知识群”只有一句被接受的决定  
**When** 两者进入阅读、编辑与引用  
**Then** 都只有一个 Node identity 与一个 content tree；长 Concept 不被按 Heading 自动拆卡，短 Decision 不被迫补空章节，D0–D2 只改变投影深度。

## 8.22 Search / Ask Anchor 回归

**Given** 用户检索到“情境依赖检索”中部的反例，并从 Answer Claim 点击同一段  
**When** Node 已经经过一次段落移动  
**Then** 两个入口都恢复 Node + Anchor + Placement；Anchor 通过 redirect 定位新位置，Back 分别返回 Search 与 Answer，不能创建临时片段 Node。

## 8.23 Evidence 精确支撑回归

**Given** A-S2 只支撑 Node 中“实验室条件下成立”的限定段落  
**When** 用户查看 Evidence  
**Then** Source Reader 高亮原始位置和上下文，Evidence target 是该 Node Anchor；Relation 可引用此 Anchor 解释依据，但正式 endpoint 仍是 Node。

## 8.24 四种内容复用回归

**Given** 产品 Decision 引用研究 Method 的一段解释  
**When** 原 Method Node 更新  
**Then** Link 打开最新 Node，Live excerpt 同步并标出更新，Pinned excerpt 保持原 revision 并提示新版，Explicit quote 保持原话和出处；四者都不自动创建 Placement 或 Relation。

## 8.25 Section Promotion 与 Node Split 回归

**Given** “适用条件”Section 已有独立 Evidence、跨群引用和更新节奏  
**When** 用户让它成为独立知识并随后拆分两个条件不同的 Claims  
**Then** 两步都预览 blocks、Anchors、Evidence、Placements、Relations 与原处引用方式；旧链接通过 redirects 工作，历史与 Undo 保留。

## 8.26 Node Merge 与 AI Patch 回归

**Given** 两条标题近似但 Applicability 不同的 Nodes，且 AI 提议补充其中一条  
**When** 用户进入 Merge / Edit  
**Then** Merge 先判断 identity 而非文字相似度；若不合并，AI 只提供可选择的 block-level patch，不整篇覆盖用户 accepted content。

## 8.27 Topic 移动与 Overview Projection 回归

**Given** 一个 Topic 在 Group 内被移动并重命名，Editorial prose 中没有依赖旧路径的表述  
**When** Change Set 提交  
**Then** Structure Projection 自动刷新并保留同一个 `overview_id`；Editorial revision 不改变，也不出现 AI 重写确认。

## 8.28 Accepted AI prose 与 Lock 回归

**Given** 用户已经接受一段 AI 协助的 Overview 文字，并锁定编辑  
**When** 新 Node 让这段文字可能不再完整  
**Then** 内容保持不变，同时显示 `current overview may need review`；authorship、lock 与 alignment 分别可查，系统不得把 locked 等同于 aligned。

## 8.29 Ask for Overview 不写入回归

**Given** 用户在 Group 范围内问“概览一下现在的关键观点”  
**When** AI 返回一个 Query Result  
**Then** canonical Overview 不创建 revision；用户可保存回答、明确请求“建议更新概览”或把一项 Claim 保存为独立知识，三个动作后果不同。

## 8.30 Overview Claim 提升回归

**Given** 用户在 Overview 中写下一个带条件、需要证据且会跨群复用的判断  
**When** 选择“保存为独立知识”  
**Then** 创建 Node 与 Evidence / Applicability / Placement，原 Overview 保留 Reference 与 Support Map；旧 Overview Anchor 可继续定位，Overview 本身不成为 Evidence endpoint。

## 8.31 Formation phase 身份连续性回归

**Given** 一个 Group 从 Seed 进入 Forming、Established、Evolving，再进入 Dormant  
**When** 每次阶段变化发生  
**Then** 只更新 Presentation Profile 与默认内容权重；不复制 `overview_id`、不自动创建 Editorial revision，也不把成熟阶段分数写入知识正文。

## 8.32 Group Merge 的 Overview lineage 回归

**Given** 两个 Group 被确认是同一边界，但各自有已编辑 Overview 与独立历史  
**When** 用户选择 canonical Group 并执行 Merge  
**Then** 系统提供 Overview Semantic Diff、保留来源 Overview 的 historical lineage 与 redirect；Projection 重新计算，未接受的文字不静默进入 canonical Overview。

## 8.33 Query Turn / Run 回归

**Given** 用户对“为什么产品不是 Project Continuity”先正常提问、Retry，再停止第三次回答  
**When** 查看历史  
**Then** 只有一个原始问题身份，三次 Run 的 Context、policy、Answer 与 complete / cancelled 状态分别保留；任何 Run 都不覆盖另一个。

## 8.34 Requested / Effective / Used 回归

**Given** 用户只选择“法国租房 / 入住”，系统需要沿正式 Relation 读取“法国行政手续”中的一条知识  
**When** Answer 完成  
**Then** Requested 保留原选择，Effective 说明允许沿哪条 Relation 扩展，Used 只列真正支撑 Claims 的对象；Current Focus 不被误写成全局 Scope。

## 8.35 Claim basis 回归

**Given** 一个回答同时使用用户原创产品 Principle、政策 Source statement、用户明确开启的外部网页和系统比较推论  
**When** 展开四个主要 Claims  
**Then** 分别显示“来自你的知识 / 来源原文 / 外部资料 / 基于这些知识可以推断”，每项进入精确 locator；原创知识不伪造 Source，Source statement 不自动成为 Accepted knowledge。

## 8.36 Coverage 与负面回答回归

**Given** 当前 Group 无命中，全局有候选 Node，一份相关来源索引未完成  
**When** 用户问“还有其他手续吗”  
**Then** 回答限定当前选择和已完成索引，Coverage 为 partial，提供显式扩大范围；不能写“你的知识库里没有其他手续”。

## 8.37 Follow-up Context Delta 回归

**Given** 上一 Run 的条件是“法国、2026、学生”  
**When** 用户追问“那非学生呢”  
**Then** 新 Turn 只改变适用对象，继承项与变化项可检查；上一 AI Answer 不作为事实依据，Nodes、Evidence 和 valid time 重新核验。

## 8.38 Saved Answer 默认排除回归

**Given** 旧 Saved Answer 曾总结 Project Continuity 为产品本体，后来相关 Decision 已 supersede  
**When** 用户在默认当前知识范围重新问产品本质  
**Then** 旧 Answer 不进入 factual support；显式选择历史回答或比较旧新时才进入，并清楚标为 Historical Answer basis。

## 8.39 Re-evaluate lineage 回归

**Given** Saved Answer 的 Nodes、Relation 与 Source availability 均发生变化  
**When** 用户选择“根据当前知识重新回答”  
**Then** 新 Run 复用原 Requested Context、解析新的 Effective / Used Context，并显示 Claim / support / unknown / coverage diff；Original 永不改写，impact 不自动宣判旧答案错误。

## 8.40 Streaming 与 Transform 回归

**Given** 回答在两个 Claims grounded 后被停止，另有一个未核对段落  
**When** 用户尝试保存  
**Then** 页面显示 incomplete，不允许把整段保存为普通 Saved Answer 或 Accepted knowledge；用户可以保留未完成文本、重新执行，或只把已核验 Claim 送入独立 Working / Proposal Preview。

---

# 9. 对视觉设计的约束

这轮仍不制作原型，但后续视觉设计必须能证明：

1. Topic 与 Node 的视觉语法不同，用户不会把目录标题误认为知识正文；
2. lifecycle、epistemic、freshness、availability 不会压成一排难懂徽章；
3. Ask Composer 能表达必要 Query Context，又不会变成数据库筛选器；
4. Saved Answer 的 Original / Re-evaluate 差异清楚；
5. Source-only Capture 是一条轻路径，而不是“跳过 AI”的隐蔽次要动作；
6. Applicability 对照能用人话说明“对谁、何时、在什么条件下”；
7. Atlas 不用大量候选边制造知识丰富的假象；
8. Overview Diff 能显示受影响范围而不是文本 diff 噪声；
9. Source 丢失不会让 Node 看起来被删除；
10. 所有状态都具有文字、图标和可访问的解释，不只依赖颜色。
11. 同一 Group Overview 能分别承载 Seed、Established、Evolving 与 Dormant，而不生成四套导航或成熟度评分。
12. Scope、Reading Depth 与 Relation Radius 可以分别改变；五类连接与 Relation 四维状态不会压成一种线。
13. Ask 无可靠 Route 时显示 Used Knowledge List，不为了画面完整制造关系。
14. Capture 能区分来源已保存、本地已保存但尚未采用、未归入知识群、整理建议与已作为当前知识采用。
15. Zero-yield、Partial 与 Failed 使用不同完成语义。
16. Proposal 首屏围绕 3–7 个用户决定，不呈现 AI 卡片瀑布流。
17. Identity Resolution 显示多种合法结果，不依赖 High / Medium / Low 置信标签。
18. Review 不承载新来源、普通 Working content 或低风险自动动作。
19. Library 不出现 Subgroup；Group、Topic、Node 与 View 使用不同结构和动作语法。
20. Topic Promotion 以 Gateway 保留旧父级语境，Group Absorb / Split / Merge 显示 redirect 与影响预览。
21. Group membership 能完全由 Placements 还原，界面不同时维护第二份成员列表。
22. Atlas 群边能展开 statement、why it matters、supporting paths、Evidence 与 limits。
23. 长 Node 保持连续 Knowledge Paper，短 Node 不被空模板膨胀，Block handle 只在相关动作时出现。
24. Search / Ask / Evidence 能精确进入 Node Anchor，并覆盖 redirected、ambiguous 与 orphaned。
25. Link、Live、Pinned 与 Quote 的更新后果可见，Section Promotion 与 Node Split / Merge 有身份影响预览。
26. Overview 阅读态是一篇连续内容，不是 Editorial、Projection、Reference、Navigation、Status 五种卡片的拼盘。
27. Projection refresh、Semantic Diff、Support Inspector、Claim Promotion 与四种 alignment 状态均有设计证据。
28. “已锁定编辑”能与“有变化可更新 / 需要检查 / 选择保留当前表述”同时成立；状态不被一个 AI 徽章代替。
29. Ask 生成 Overview-like Answer、显式建议更新 canonical Overview、保存 Claim 为 Node 三条路径在动作和结果上不可混淆。
30. Quick Ask 与 Full Answer 展开同一 Turn / Run / Claim Support，不重新生成一套答案。
31. “你让我查的范围 / 系统实际采用 / 这次真正用到”可检查，但不会成为 chips 和日志墙。
32. 每个主要 Claim 的四类 basis 能一跳核验，默认 Direct Answer 仍先于依据展开。
33. No relevant knowledge、Scope too narrow、Index partial、Source unavailable、Conflict、AI unavailable 与 cancelled 不共享一个空状态。
34. Follow-up 显示 Context Delta，Rephrase、Retry、Branch、Resume 与 Re-evaluate 的历史关系能被理解。
35. Saved Answer Original、Impact、Re-evaluation 与 Answer Diff 可比较，历史回答默认排除状态可以被检查。
36. Answer、Node、Merge、Question、Path、Relation、Overview 与 Source 八种 Transform 的长期后果在动作前可预测。

---

# 10. 结论

三类场景说明，产品方向本身成立：知识群、语义层级、关系网络、AI 查询与证据可以组成同一个长期个人知识库。

但原有模型在“静态、无条件、只有当前版本”的知识上更完整；一旦进入真实世界的多语境、有效时间、来源变化和历史回答，就会出现结构缺口。

本轮最关键的修订是：

> **Group 负责独立知识边界，Topic 负责群内结构，Placement 负责唯一归属真相，Node 负责可复用知识身份，Group Relation 负责解释范围为什么相连；Applicability、状态轴、Query Context、Snapshot 与 Change Set 则让这些知识在条件、时间和变化中保持可解释。**

这些不是附加功能，而是让“知识库”在真实复杂度下仍然可信、可理解、可演化的产品本体。

本轮三个内容场景已经被进一步映射到流程板；第二轮完整性审计又加入直接创作、迁移与恢复三个所有权场景，当前基线为十一块流程板和 81 项唯一主归属，见 `AI-native-个人知识库-产品流程板与组件状态图-v1.0.md` 与 `AI-native-个人知识库-完整性审计与产品修订-v1.1.md`。第三轮核心体验复核进一步让“认知科学”走过 Seed → Forming → Established、“AI Agent 产品设计”证明用户原创与 AI 知识共存、“法国租房”证明 Established → Evolving 并保留历史。第五轮知识形成复核增加无归属快速记录、zero-yield、300 来源导入、身份解析与纠正传播回归，见 `AI-native-个人知识库-知识形成与维护循环-v1.0.md`。第六轮知识群架构复核加入 Topic / Group 边界、Promotion Gateway、Placement 单一归属、Group Merge 和群关系解释回归，见 `AI-native-个人知识库-知识群边界与跨群架构合同-v1.0.md`。第七轮 Node 粒度复核增加长短 Node、Search / Ask Anchor、精确 Evidence、四种复用、Section Promotion、Split / Merge 与 AI block patch 回归，见 `AI-native-个人知识库-知识节点粒度与内容组成合同-v1.0.md`。第八轮 Overview 复核冻结单一 identity 与 content tree、Editorial / Projection 分离、正交治理、Support Map、Claim Promotion、Ask 不写入与阶段身份连续性，见 `AI-native-个人知识库-Overview形成编辑与更新合同-v1.0.md`。第九轮 AI 查询复核冻结 Turn / Run、Requested / Effective / Used Context、Claim Support、Coverage、Follow-up Delta、Saved Answer exclusion 与 Re-evaluate lineage，见 `AI-native-个人知识库-AI查询与知识回答合同-v1.0.md`。后续设计应持续使用这些场景做回归，而不是用理想化占位数据代替。
