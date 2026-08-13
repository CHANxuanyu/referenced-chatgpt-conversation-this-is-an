# AI-native 个人知识库

## 产品对象层级与身份治理合同 v1.0 — Primary Resources、Supporting Records、Projection 与 Workspace State

> 日期：2026-08-06  
> 文档性质：终局产品本体、身份层级与真相边界合同；不是数据库表设计、MVP 范围、视觉稿或原型  
> Canonical 产品定义：`AI-native-个人知识库-终局产品设计文档-v4.0.md`；本合同只证明本体与身份不变量，不得反向改写 v4.0  
> v4.0 Knowledge identity 覆写：Knowledge identity、Content Revision、Section / Content Block 与 Anchor 分层；后三者不因可深链、可检索或可导出而自动成为 Primary Resource，Claim Knowledge 只能由明确 Promotion 产生  
> v4.0 Relation identity 覆写：Relation 是独立 Primary Resource；inverse label、symmetric view、derived path、cross-group exit 与 Relation Bundle 都解析到既有 truth 或 Presentation，不创建镜像、聚合或临时 Relation identity  
> v4.0 Query identity 覆写：Query Session / Turn / Run / Context Snapshot / Answer Claim 是 Supporting Records；未保存 Answer 只是 Workspace state，Saved Answer 复用 Knowledge Snapshot；任何对象都不因可搜索、可深链或可导出而自动成为 Knowledge  
> v4.0 Scope identity 覆写：Group Boundary Revision、Knowledge Placement、Source Attachment 与 Topic Transformation Lineage 都是 Supporting / Governance identities；它们分别保存范围意图、知识出现位置、材料进入语境与结构变化历史，任何一项都不是新的 Knowledge 或 Source identity  
> v4.0 探索连续性覆写：Saved Path 仍是 Primary Resource；SavedPathRevision 是 Supporting identity，PathStep 是 Embedded record；ExplorationSession / Trail、ReturnStack、ResumePoint 与 PathProgress 属于 Supporting / Workspace continuity，且 `last_position` 不属于 Saved Path identity  
> 2026-08-07 直接写作身份冻结：Current Revision、Explicit Draft、Proposal、Recovery Checkpoint、Direct Edit Commit、Edit Buffer / Session、Sync State 与 Projection State 分层；普通写作不创建 Working-first 审批对象  
> 2026-08-08 Group Formation 身份冻结：GroupCandidate 是临时 Formation State，不是 Primary Resource 或 Supporting knowledge record；它没有 group_id / Overview / Relation / History，不进入 Search、Network、Ask 或 canonical export，Accept 才创建 Group 与 Change Set  
> 2026-08-10 Relation Lifecycle 身份冻结：RelationCandidate 不是 Relation；RelationRevision、EvidenceBinding、RelationChallenge、RelationReviewCase、RelationDecisionEvent、GroupRelationSupportSetRevision 与 RelationTransitionCase 分属不同 supporting responsibilities，并全部回到 owner Relation / endpoint。完整合同见`AI-native-个人知识库-关系陈述生命周期与网络可信性合同-v1.0.md`  
> 2026-08-10 Knowledge Relation Type 身份冻结：KnowledgeRelationTypeDefinitionRevision、TypeValidationReport、TypeMigrationReview、KnowledgeIdentityTransition 与 QuestionTargetReference 是不同 Supporting / Governance identities；`supersedes / retracts / reopens / uncertain_about`不通过 ordinary Relation identity 表达。完整合同见`AI-native-个人知识库-知识关系类型注册表与跨层语义合同-v1.0.md`  
> 历史深层模型：`AI-native-个人知识库-产品定义-v3.0.md`  
> 交互基线：`AI-native-个人知识库-交互架构与设计系统-v1.0.md`  
> 产品语言：`AI-native-个人知识库-产品语言与渐进披露规范-v1.0.md`  
> 流程与状态：`AI-native-个人知识库-产品流程板与组件状态图-v1.0.md`  
> 知识群边界：`AI-native-个人知识库-知识群边界与跨群架构合同-v1.0.md`  
> 知识节点：`AI-native-个人知识库-知识节点粒度与内容组成合同-v1.0.md`  
> 关系陈述生命周期：`AI-native-个人知识库-关系陈述生命周期与网络可信性合同-v1.0.md`  
> Overview：`AI-native-个人知识库-Overview形成编辑与更新合同-v1.0.md`  
> AI 查询：`AI-native-个人知识库-AI查询与知识回答合同-v1.0.md`  
> Library 与 View：`AI-native-个人知识库-Library浏览与动态视图合同-v1.0.md`  
> 来源与证据：`AI-native-个人知识库-来源证据与可追溯性合同-v1.0.md`  
> 直接创作与历史：`AI-native-个人知识库-直接创作编辑与版本历史合同-v1.0.md`  
> 属性与适用条件：`AI-native-个人知识库-属性Facet与适用条件合同-v1.0.md`
> 探索路径、回返与继续：`AI-native-个人知识库-探索路径、回返与继续合同-v1.0.md`

---

# 0. 执行决定

现有规格反复使用“十四个正式对象”“第十五个对象”“内部记录”“Projection”“Workspace State”等说法，却没有统一说明：一个东西有稳定 ID，是否就应该进入 Library、Atlas、Search、Relation、一级导航、完整导出和日常语言。

本合同冻结五十二项决定：

1. **稳定 identity 不等于主要产品对象。** Revision、Binding、Query Run、Property Definition 等可以长期存在、可引用、可导出，但不因此进入日常知识目录。
2. **十四个对象改称十四类 Primary Product Resources / 主要产品资源。** 这是产品行为合同，不是系统全部持久记录的穷举，也不是十四张页面。
3. **五个日常核心名词保持不变。** 默认界面仍只要求用户理解知识群、主题、知识、关系、来源；对象分层属于内部严谨性，不增加学习门槛。
4. **主要资源与知识真相不是同义词。** Source、Change Set、Proposal、View 都是主要产品资源，但分别属于来源、治理或观察，不冒充 Current Knowledge。
5. **系统使用六个内部平面。** Knowledge、Source & Provenance、Structure & Curation、Governance & History、Definition & Policy、Projection & Workspace 各自拥有不同写入与显示规则。
6. **对象类别与 Truth Role 分开。** 同一类别中的记录仍要明确它保存的是 Knowledge Truth、Source Truth、Decision History、Definition Truth、Derived Result 还是 Session State。
7. **Primary Resource 必须通过准入测试。** 它应对应独立用户意图、稳定地址、独立生命周期、可解释历史和不可由其他真相完整重建的责任。
8. **有 ID 不是准入理由。** 为并发、缓存、引用、审计或实现便利生成的 ID，不使记录成为主要资源。
9. **有独立页面也不是准入理由。** History Inspector、Relation Inspector、Evidence Reader 可以打开支持记录，但打开能力不等于顶层对象地位。
10. **Primary Resource 不自动进入一级导航。** 一级导航只表达一个 Knowledge Library；Groups / Network 是同一 Library 的观察，Sources / Knowledge Decision 由 utility 或受影响 owner / event 按需进入。
11. **Primary Resource 不自动进入 Library Root。** Library 默认收纳用户长期拥有和主动找回的知识身份、路径、回答与 View，不变成内部对象浏览器。
12. **Search 默认返回用户要找的 identity。** Revision、Anchor、Fragment、Binding 与 Assertion 只作为命中位置、解释或限定；不与 Node、Group、Source 并列制造结果噪声。
13. **正式 Semantic Relation 端点仍只允许 Node↔Node 或 Group↔Group。** 稳定 ID、可点击或出现在同一图中都不能绕过端点合同。
14. **Provenance Graph 与 Semantic Graph 分开。** Source、Revision、Fragment、Binding、Activity 的连接可被检查，但不冒充知识关系。
15. **Structure Graph 与 Semantic Graph 分开。** Topic parent、Placement、Overview Navigation 与 Saved Path step 不重复存成正式 Relation。
16. **Projection 是可重建观察，不是第二份真相。** View Evaluation、Overview Projection、Search result set、Graph cluster、status summary 和推荐列表都从 canonical inputs 重算。
17. **可缓存不等于可编辑。** Materialized projection 可以持久化以支持离线与性能，但用户不能直接修改缓存结果来改变知识。
18. **Projection 必须保存 basis 与 coverage。** 用户能检查它基于哪些 revisions、规则、时间和索引范围生成，过期或部分覆盖时不得装作当前全量事实。
19. **Workspace State 只保存工作现场。** Selection、scroll、pane、graph viewport、temporary filter、cursor 和 disclosure state 可恢复，但不改变对象、结构或知识权威。
20. **Session State 不进入 canonical export 的知识层。** 它可以进入可选的 Continuity 包；恢复失败不能损坏知识主体。
21. **Content Revision 是不可变支持记录。** 它拥有稳定身份和历史价值，但默认只通过对象 History 进入，不在 Library 与 Atlas 独立出现。
22. **Explicit Draft 是用户主动保留的支持身份。** 它可以在 Draft Search 以“草稿”找到，但不成为 Current Knowledge、Overview Projection 或正式 Atlas 节点；Recovery Checkpoint 不进入 Search。
23. **Edit Buffer / Session 是短期 Workspace State。** 它可以恢复光标、IME 与撤销栈，不作为知识版本、审计历史或长期引用目标；只有 Direct Edit Commit 能推进 Current Revision。
24. **Source Revision 与 Representation 属于 Source Truth。** 它们可被 Citation 精确引用和导出，但用户日常仍进入 Source identity，再选择版本与形态。
25. **Evidence Fragment 与 Evidence Binding 分工。** Fragment 是十四类主要资源之一并保存精确片段；Binding 是支持记录，保存该片段对具体 Target 的作用。
26. **Source Annotation 是阅读记录。** 它可以有稳定 ID、版本和提升结果，但不默认进入 Knowledge Search、Atlas、Overview 或 Review。
27. **Query Turn、Query Run 与 Answer Snapshot 是运行与历史记录。** 它们不会因为可回看而成为知识；Saved Answer 通过既有 Knowledge Snapshot 获得主要资源身份。
28. **Property Definition 与 Property Profile 是 Definition & Policy identities。** 它们可版本化、迁移和归档，但不进入知识网络或成为 Relation endpoint。
29. **Property Assertion 是目标对象的结构化事实记录。** 它随 target、origin、Applicability、Evidence 和 revision 被检查，不作为独立 Library row。
30. **View Definition 是主要资源，View Evaluation 不是。** 用户保存和命名的是观察规则；某次结果只是带 basis 与 coverage 的求值。
31. **Proposal 是决策资源，raw candidate 不是。** 只有已聚合为用户能判断、能延期、能接受或拒绝的 Decision Bundle 才获得 Proposal identity。
32. **Change Set 保存一次有用户意义的多对象变化。** 底层每个索引更新、缓存刷新或 telemetry event 不成为 Change Set。
33. **Knowledge Snapshot 保存历史理解边界。** 它可以包含 Answer Snapshot、used revisions 和 Query Context，但不把当时生成文本自动升级为当前知识。
34. **Configuration change 与 Knowledge change 分开。** 修改 Relation type、Property Definition、AI policy 或 import mapping 先改变 Definition / Policy，只有明确迁移或提交才改变知识对象。
35. **系统不提供“全部内部对象”通用后台。** 高级检查从当前对象进入相应 History、Evidence、Definition 或 Diagnostic context。
36. **Deep link 记录对象类别与进入语境。** 打开 Fragment、Revision、Assertion 或 Run 时，界面同时显示其所属主要资源和返回路径，避免孤立技术页面。
37. **删除语义由 ownership 与 derivability 决定。** 删除 Projection 只删缓存；删除 View Definition 不删结果；删除 Binding 不删 Fragment；删除 Source 不自动删 Node。
38. **Archive 与 tombstone 保留身份连续性。** 任何被其他稳定记录引用的 identity 都不能因 UI 隐藏而被静默复用或彻底消失。
39. **级联删除默认禁止跨平面发生。** 影响必须预览；能保留引用、快照、tombstone 或 orphan state 时，不通过级联抹掉历史。
40. **完整 Knowledge Package 分层导出。** 主要资源、支持记录、Definition / Policy、provenance、历史、派生索引和可选 Workspace Continuity 使用不同 manifest 区段。
41. **Canonical restore 不依赖 Projection cache。** 删除全部索引、View Evaluation、Overview Projection result 与 graph layout 后，仍能从主要资源和支持记录重建产品。
42. **Round-trip 必须保留引用可达性。** Group → Placement → Node、Source Revision → Fragment → Binding → Target、View → Definition refs、Snapshot → used revisions 均可验证。
43. **AI 可以读取多个平面，但必须按 Truth Role 标注。** 模型不能把 Query Run、Annotation、Proposal、Recovery、Projection result 或 stale cache 当作 Current Knowledge。
44. **AI 写入必须选择目标平面。** 生成回答、提出 Proposal、创建 Working Patch、更新 Projection 与提交 Knowledge Change 是五种不同后果。
45. **对象数量不是产品完整性指标。** 新增实体、表、ID、组件或页面不能被当作产品成熟度；用户能否形成、理解、使用、维护和带走知识才是标准。
46. **对象分层不授权全量 Event Sourcing。** 仅对需要历史、恢复、并发或影响解释的边界保留不可变 revisions / activities；简单偏好和可重建缓存保持简单。
47. **终局模型先于工程切片。** 本合同定义完整产品语义，不使用 MVP、P0/P1 裁剪来重新定义长期对象边界。
48. **本合同不授权原型。** 在主要资源、支持记录、Projection、Workspace 与用户表面边界获得确认前，不用对象浏览器或漂亮图谱掩盖产品本体混淆。
49. **Group Boundary Revision 是 Definition / Governance supporting identity。** 它保存“这个群想理解什么”的历史，不保存成员清单；更新 Boundary 不自动移动 Topic、Placement、Attachment 或 View result。
50. **Placement 与 Source Attachment 是不同的 Structure identities。** Placement 记录 Knowledge 在 Group root / Topic 的出现位置；Attachment 记录 Source 进入 Group / Topic 的材料语境，二者不能互相推导。
51. **Topic transformation lineage 必须长期存在。** rename / move 通常保留 identity；merge / split / cross-group transfer 通过 redirect、successor 与 Change Set 解释旧链接、Paths、Placements 与 Attachments 的新去向。
52. **结构支持身份不进入日常对象表面。** P0 / P1 只说`这个知识群想理解`、`直接放在这里`、`包含子主题`、`这份来源加入了…`与`结构已经变化`；内部 record 只在影响预览、历史或恢复中展开。

---

# 1. 当前规格中的十六个结构缺口

## 1.1 “十四个正式对象”被误读为完整数据模型

合同随后又引入 Query Run、Revision、Binding、Assertion、Selector、Activity 等稳定记录。若“正式对象”意味着全部持久实体，十四显然不完整；若意味着日常概念，十四又过多。

## 1.2 “不是第十五个对象”成为逐条补丁

Block、Anchor、Property Definition、Query Run、Annotation、View Evaluation 都各自被声明“不是新对象”，但没有统一准入规则，无法约束未来新增。

## 1.3 稳定身份与可见对象混为一体

为了引用和恢复，很多记录必须有 ID；若设计按“有 ID 就有卡片”实现，产品会变成治理后台。

## 1.4 可点击与可搜索混为一体

Citation 可以打开 Fragment，History 可以打开 Revision，但这不代表它们应在全局 Search 与 Library 中独立竞争。

## 1.5 主要资源与 Knowledge Truth 混为一体

Source、Proposal、Change Set、View 都是重要产品对象，却不应被 Ask 当作当前事实或在 Atlas 中画成语义节点。

## 1.6 三张图缺少统一对象准入表

Structural、Semantic、Provenance Graph 已被区分，但每一类 record 是否可进入哪张图仍散落在多份合同中。

## 1.7 Projection 有时被写成 Block，有时被写成结果

Projection definition、evaluation、cached result 与 rendered block 若不拆开，用户可能直接编辑派生结果，系统也无法说明何时过期。

## 1.8 Workspace State 的持久性边界不清

Return Stack、Selection、temporary filter、graph layout 和 Edit Session 都能恢复，但哪些属于知识资产、哪些只是工作现场没有统一出口。

## 1.9 History 被多个相似对象重复表达

Content Revision、Change Set、Knowledge Snapshot、Query Run、Recovery Checkpoint 与 Activity 都保存“过去”，但回答的问题不同。

## 1.10 Definition identities 处于夹层

Property Definition、Profile、Relation type、AI policy 与 import mapping 都会影响长期行为，却既不是知识，也不能作为随时丢弃的配置字符串。

## 1.11 删除影响缺少跨平面规则

删除 View、Projection cache、Binding、Fragment、Source、Node 或 Definition 的级联后果完全不同；没有统一规则时实现容易过删。

## 1.12 Export 可能只保留“十四对象”

若导出只按主要资源清单打包，会丢失 Revision、Binding、Selector、Definition、Query basis 与 Migration history，恢复后表面存在但语义断裂。

## 1.13 AI 检索容易跨层误用

模型看见 Annotation、Proposal、历史 Answer、stale Projection、Explicit Draft 或 Recovery 后，可能把它们与 Current Knowledge 混成一个语料池。

## 1.14 Search 容易退化为内部记录列表

高亮片段、版本、属性值、命中块和回答 Claim 若都以独立结果出现，用户找不到真正想进入的知识 identity。

## 1.15 复杂模型没有新对象准入门槛

未来任何新能力都可能新增 Collection、Card、Thread、Agent Memory、Insight、Digest 或 Workspace，形成第二套知识真相。

## 1.16 视觉设计可能暴露错误层级

如果所有 record 都拥有卡片、图标、徽章和导航位置，方向 2 + 3 会变成对象星云；若全部隐藏，版本、证据和影响又无法核验。

---

# 2. 产品目标、非目标与证据边界

## 2.1 终局目标

1. 让每个长期存在的记录拥有唯一、可解释的产品责任；
2. 让“能引用、能恢复、能导出”与“日常要管理”同时成立；
3. 让 Search、Library、Atlas、Ask 和 Export 使用同一对象层级；
4. 让复杂内部模型服务低负担阅读，而不是暴露为知识治理后台；
5. 为未来新增对象提供一致准入、删除、迁移和显示规则。

## 2.2 永久非目标

- 不把本合同变成数据库 ERD 或具体存储选型；
- 不要求所有对象使用 event sourcing；
- 不把所有 ID 都暴露为 URL、页面或卡片；
- 不提供通用内部对象浏览器；
- 不让 Primary Resource 数量成为产品 KPI；
- 不允许视图、缓存、AI 输出或运行日志获得第二份 Knowledge Truth。

## 2.3 证据边界

- **[用户确认]**：产品是个人知识库；核心为知识群、关系、层级、AI 查询和网络探索；当前不做原型。
- **[研究事实]**：外部标准与官方架构模式证明 domain resource、statement / qualifier / reference、provenance record、annotation、projection 与 workspace state 可以使用不同模型责任。
- **[产品决定]**：六平面、十四主要资源、准入门槛、表面规则和导出分层是本产品的选择。
- **[待验证假设]**：用户能否在不学习内部对象名的情况下理解 History、Evidence、View basis 和影响预览，仍需后续真实任务验证。

---

# 3. 核心术语

## 3.1 Primary Product Resource / 主要产品资源

一个承担独立用户意图、拥有稳定地址与生命周期、不能由其他真相完整重建、需要独立影响与导出语义的产品资源。

它不必拥有一级导航、独立全屏页面或日常名词，也不必成为 Knowledge Truth 或 Semantic Relation endpoint。

## 3.2 Supporting Identity / 支持身份

为了版本、引用、并发、迁移、证据或审计而持久存在的 identity，例如 Content Revision、Source Revision、Evidence Binding、Query Run、Property Definition。

它可被深链和检查，但默认通过所属 Primary Resource 进入。

## 3.3 Embedded Record / 内嵌记录

只有在所属 identity 语境中才有完整意义的记录，例如 Property Assertion、Content Anchor、Path Step、Answer Claim Support。

它可以拥有稳定局部 key，不应独立进入 Library 或 Atlas。

## 3.4 Governance Record / 治理记录

保存一次决定、变化、迁移或恢复依据的长期记录，例如 Change Set item、Schema Migration、Conflict Resolution、Provenance Activity。

治理记录回答“发生了什么、为什么、影响什么”，不回答“当前知识是什么”。

## 3.5 Projection / 投影

由 canonical inputs + definition + evaluation basis 计算出的读取结果。Projection 可以缓存、离线使用或被快照，但缓存本身不接受直接知识写入。

## 3.6 Workspace State / 工作现场

帮助用户连续完成任务的状态，例如 Selection、pane、scroll、temporary filters、graph viewport、cursor 和 disclosure。它可以持久恢复，但不进入 Knowledge Truth。

## 3.7 Truth Role / 真相角色

记录在产品中承担哪种权威：

```text
knowledge_truth
source_truth
definition_truth
decision_history
derived_observation
workspace_continuity
```

一个记录必须有主 Truth Role；它可以引用其他角色，但不能用一个通用 `object` 或 `state` 字段模糊处理。

---

# 4. 六个内部平面

## 4.1 Knowledge Plane / 知识平面

保存用户当前认可、可以阅读、连接、查询和维护的个人知识结构。

主要包含：

- Knowledge Space boundary；
- Knowledge Group boundary；
- Topic structure；
- Knowledge Node current content；
- Semantic Relation statement；
- Overview accepted editorial truth。

它不包含：来源原文、AI 运行日志、View results、临时 selection 或未接受 Proposal。

## 4.2 Source & Provenance Plane / 来源与可追溯平面

保存材料当时是什么、怎样转换、哪一段被使用、对哪条 Claim 起什么作用。

主要包含：

- Source identity；
- immutable Source Revision；
- Representation；
- Selector Bundle；
- Evidence Fragment；
- Evidence Binding；
- Source Annotation；
- Provenance Activity。

它提供核验，不自动决定 Knowledge Truth。

## 4.3 Structure & Curation Plane / 结构与策展平面

保存知识怎样被组织、进入和重新观察，而不复制正文。

主要包含：

- Placement；
- Topic parent 与 semantic order；
- Saved Path 与 Path Step；
- View Definition；
- Pin；
- Navigation references。

Topic 本身同时是 Knowledge Plane 的可理解 Scope 与本平面的结构 identity；这是一项明确多角色，不代表重复存储。

## 4.4 Governance & History Plane / 治理与历史平面

保存输入何时被采用、发生了什么变化、谁作出决定、如何恢复与重评。

主要包含：

- Proposal / Decision Bundle；
- Change Set；
- Content Revision；
- Explicit Draft / Proposal Branch；
- Direct Edit Commit；
- Knowledge Snapshot；
- Query Turn / Run / Answer Snapshot；
- Migration Plan / Result；
- Recovery Checkpoint；
- Conflict Resolution。

它解释知识演化，不与 current pointer 竞争。Recovery Checkpoint 只承担近期保护，Direct Edit Commit 记录 pointer 何时被用户普通写作推进；二者不能合并为同一 record。

## 4.5 Definition & Policy Plane / 定义与策略平面

保存可被多个对象稳定引用、需要版本和迁移的语义配置。

主要包含：

- Property Definition；
- Property Profile；
- Facet / Primary Kind Definition；
- Relation Type Definition；
- View Definition dependency；
- AI Policy；
- Source mapping policy；
- Import / export mapping；
- presentation preference definition。

Definition 改变后先产生 compatibility 与 impact，不直接重写使用它的知识。

## 4.6 Projection & Workspace Plane / 投影与工作现场平面

保存当前怎样看、当前算出了什么、当前进行到哪里。

主要包含：

- Overview Projection Evaluation；
- View Evaluation；
- Search Result Set；
- index documents / embeddings；
- Graph layout / cluster；
- recommendation candidate ranking；
- Selection State；
- Return Stack；
- Library Workspace State；
- Edit Buffer；
- Edit Session；
- Sync State；
- pane / scroll / cursor / disclosure。

该平面全部可以失效、重算或重置，而不改变 Knowledge / Source Truth。

---

# 5. 身份等级与真相角色是两个正交维度

## 5.1 身份等级

| Identity Class | 说明 | 示例 |
|---|---|---|
| Primary Resource | 独立用户意图与生命周期 | Node、Source、View、Change Set |
| Supporting Identity | 需要稳定引用与历史 | Content Revision、Query Run、Property Definition |
| Embedded Record | 只在父对象内成立 | Assertion、Anchor、Path Step |
| Derived Evaluation | 可重建观察 | View Evaluation、Search Result Set |
| Workspace State | 连续任务状态 | Selection、scroll、temporary filter |

## 5.2 真相角色

| Truth Role | 写入权威 | 可否由其他层重建 |
|---|---|---|
| Knowledge Truth | 用户提交或明确有限规则 | 否 |
| Source Truth | 原始 bytes / snapshot / immutable revision | 否 |
| Definition Truth | definition revision + migration | 否 |
| Decision History | immutable activity / decision record | 否，但可归档 |
| Derived Observation | canonical inputs + evaluation basis | 是 |
| Workspace Continuity | interaction state | 是或可丢失 |

## 5.3 组合示例

- View 是 `Primary Resource + Structure / Definition`；View Evaluation 是 `Derived Evaluation + Derived Observation`。
- Source 是 `Primary Resource + Source Truth`；Source Revision 是 `Supporting Identity + Source Truth`。
- Knowledge Snapshot 是 `Primary Resource + Decision History`；Answer Snapshot 是 `Supporting Identity + Decision History`。
- Property Definition 是 `Supporting Identity + Definition Truth`；Property Assertion 是 `Embedded Record + Knowledge Truth`。
- Edit Session / Buffer 是 `Workspace State + Workspace Continuity`；Explicit Draft 是 `Supporting Identity + Decision History / not-current content`；Recovery Checkpoint 是 `Supporting Recovery / not truth`。

---

# 6. 十四类主要产品资源的精确含义

“主要”表示产品行为不可由其他资源替代，不表示默认可见程度。

| Primary Resource | 主平面 | 用户意图 | 默认入口 | Semantic Relation endpoint |
|---|---|---|---|---|
| Knowledge Space | Knowledge | 我的全部知识边界 | 隐式 App Root | 否 |
| Knowledge Group | Knowledge | 独立理解一个知识范围 | Library Groups / Network | 是，Group↔Group |
| Topic | Knowledge + Structure | 进入群内稳定分支 | Group hierarchy | 否 |
| Knowledge Node | Knowledge | 阅读、编辑和复用一条知识 | Library / Search / Group | 是，Node↔Node |
| Placement | Structure | 理解同一知识在这里的位置 | Topic row / Context Rail | 否 |
| Relation | Knowledge | 理解两端为什么相连 | Atlas / Local Graph / Inspector | 自身是陈述，不作普通端点 |
| Overview | Knowledge | 从整体进入当前 Scope | Space / Group / Topic / Path | 否 |
| Source | Source | 阅读和管理一份材料 | Sources / Citation | 否 |
| Evidence Fragment | Source | 精确核验被使用的片段 | Evidence / Citation | 否，使用 Evidence Binding |
| Saved Path | Structure | 保存一段有顺序的理解路线 | Library / Explore | 否 |
| Knowledge Snapshot | Governance | 保留当时的问题、范围与理解 | Paths & Answers / History | 否 |
| Change Set | Governance | 检查一次变化与影响 | History / Impact | 否 |
| Proposal | Governance | 对一个高价值变化作决定 | Review / inline suggestion | 否 |
| View | Structure + Definition | 保存一种动态观察规则 | Library / saved surface | 否 |

## 6.1 Primary Resource 不是页面清单

- Placement 通常以 row context、rail 或 impact item 出现；
- Evidence Fragment 通常在 Source Reader 中打开；
- Relation 通常由 edge、statement 与 Inspector 表示；
- Change Set 通常是影响预览与 History；
- Proposal 通常以内联 Decision Bundle 表示；
- Knowledge Space 默认只有一个，不显示 Space 管理主页。

## 6.2 Primary Resource 不是全局 Search 清单

默认 Global Search 的顶层结果单位：Group、Topic、Node、Source、Saved Path、Knowledge Snapshot、View。Relation 在明确关系搜索或 endpoint context 中出现；Overview 作为 Scope entrance 合并到所属 Scope；Placement、Fragment、Change Set、Proposal 作为深层命中或专用模式出现。

## 6.3 Primary Resource 不是 Atlas 节点清单

Atlas 默认只显示 Groups 与正式 Group Relations；Group Map / Local Graph 按 contract 显示 Topic structure、Nodes、正式 Node Relations 与有限辅助连接。Source、Fragment、Snapshot、Change Set、Proposal、View 不进入 canonical semantic layer。

---

# 7. 支持身份与内嵌记录目录

## 7.1 Knowledge content records

| Record | Identity class | 所属资源 | 责任 |
|---|---|---|---|
| Content Revision | Supporting | Node / Overview | 不可变 current / historical content |
| Explicit Draft Branch | Supporting | Node / Overview | 用户主动保留、默认不用于知识读取的草稿 |
| Proposal Branch | Supporting | Node / Overview | AI / system 提议差异 |
| Direct Edit Commit | Supporting / Governance | Node / Overview | 普通用户写作如何原子推进 current pointer |
| Recovery Checkpoint | Supporting / Recovery | Edit Session / Draft | 设备级近期保护；不是真值或普通历史 |
| Content Block | Embedded | Content Revision / Draft | 连续正文写作单元 |
| Content Anchor | Embedded | Content Revision | 精确定位与 redirect |
| Edit Buffer | Workspace | Edit Session | dirty content、IME composition、validation state |
| Edit Session | Workspace | Node / Overview / Draft | cursor、selection、IME、session undo |
| Sync State | Workspace / Supporting | Current Revision | queued、synced、conflict；不决定 current |

## 7.2 Relation records

| Record | Identity class | 所属资源 | 责任 |
|---|---|---|---|
| Relation Revision | Supporting | Relation | 一次不可变的 endpoints / type / statement / qualifiers / Applicability 意义 |
| Relation Candidate | Supporting / Proposal | Candidate owner context | 待判断建议；采用后才物化 Relation，不拥有 graph truth |
| Relation Challenge | Supporting | Relation Revision | 具体反命题、Applicability overlap、basis 与 resolution |
| Relation Review Case | Supporting / Governance | Relation | 一次有依据的语义影响判断；不拥有新 truth |
| Relation Decision Event | Supporting / Governance | Relation | Create / Maintain / Revise / End / Supersede / Retract / Archive 等历史 |
| Group Relation Support Set Revision | Supporting | Group Relation Revision | 某时刻的 supporting paths、roles、removal impact 与 exclusions |
| Relation Transition Case | Supporting / Governance | Relation + endpoint identity change | Split / Merge / successor 后逐边判断，不静默 retarget |
| Relation Bundle | Derived / Presentation | endpoint pair + current scope | 折叠显示多条 Relations；不拥有 standing 或 Evidence |
| Candidate Suppression | Workspace / Supporting preference | endpoint pair + basis fingerprint | 防止无新依据时重复建议；不进入知识图 |

## 7.3 Source and evidence records

| Record | Identity class | 所属资源 | 责任 |
|---|---|---|---|
| Source Revision | Supporting | Source | 一次不可变材料状态 |
| Representation | Supporting | Source Revision | PDF / HTML / OCR / transcript 等形态 |
| Selector Bundle | Supporting | Evidence Fragment | 多策略 locator |
| Evidence Binding | Supporting | Fragment + Target | support / challenge / qualify 等作用 |
| Source Attachment | Supporting | Source + Group / Topic | 保存材料进入某个知识范围的语境；不等于成员或证据 |
| Source Annotation | Supporting | Source Revision | highlight / comment / bookmark |
| Provenance Activity | Supporting | Source / Representation / Binding | 保存 transform、creation、revision、invalidation 的 Decision History |

## 7.4 Query and answer records

| Record | Identity class | 所属资源 | 责任 |
|---|---|---|---|
| Query Turn | Supporting | Query Session / Snapshot | 用户问题与意图 |
| Query Run | Supporting | Query Turn | 实际执行与 Effective / Used Context |
| Answer Snapshot | Supporting | Run / Knowledge Snapshot | 一次不可变回答结果 |
| Answer Claim | Embedded | Answer Snapshot | 可核验结论单位 |
| Claim Support | Embedded | Answer Claim | basis、support、route、limits |
| Query Overlay | Derived | Query Run | 当前图谱高亮，不写入 canonical graph |

## 7.5 Property and definition records

| Record | Identity class | 所属资源 | 责任 |
|---|---|---|---|
| Property Definition | Supporting | Definition Registry | 稳定语义、type、cardinality |
| Property Assertion | Embedded | target identity / revision / Placement / Source | 结构化事实值 |
| Property Profile | Supporting | Group kind / Facet | 按需建议与显示 |
| Facet Definition | Supporting | Definition Registry | 附加结构角色 |
| Relation Type Definition | Supporting | Definition Registry | 关系语义与约束 |
| Schema Migration | Supporting | Definition change | 保存 impact、conversion、legacy、rollback 的治理历史 |

## 7.6 Structure and view records

| Record | Identity class | 所属资源 | 责任 |
|---|---|---|---|
| Topic Parent Ref | Embedded | Topic | 单一直接父级 |
| Knowledge Placement | Supporting | Node + Group root / Topic | 同一 Knowledge 的可复用出现位置 |
| Group Boundary Revision | Supporting | Group | 范围意图、理由、时间与 revision lineage |
| Topic Transformation Lineage | Governance | Topic + Change Set | merge / split / transfer 的 redirect、successor 与恢复依据 |
| Saved Path Revision | Supporting | Saved Path | ordered steps、purpose change 与 revision basis；不保存进度 |
| Path Step | Embedded | Saved Path Revision | target、placement context、真实 connector、rationale 与保存时 revision |
| Pin | Embedded | user preferences | convenience record；快捷入口，不改变真相 |
| Recent Event | Embedded | object history | convenience record；访问、编辑、更新分别记录 |
| View Evaluation | Derived | View | 某次成员与 coverage |
| Library Workspace State | Workspace | View / Library surface | tree、sort、scroll、selection |

## 7.6 Exploration continuity records

| Record | Identity class | 所属资源 / 现场 | 责任 |
|---|---|---|---|
| DepthTrail | Derived | current target + placement | 当前结构位置；不保存访问顺序 |
| ReturnStack / ReturnEnvelope | Workspace | window / tab | 恢复 place、owner、anchor、viewport、scroll 与 focus |
| ExplorationSession | Workspace / Supporting | current exploration | 一次探索的 origin、active branch 与生命周期 |
| ExplorationTrail / TrailStep | Workspace / Embedded | ExplorationSession | 有意义的 Open 顺序；不记录 hover、inspect 或 scene operation |
| TrailBranch | Embedded | ExplorationSession | Back 后新 Open 形成的轻量分支 |
| PathProgress | Supporting / Workspace continuity | user + SavedPathRevision | current / completed / skipped steps；可清除，不改 Path |
| ResumePoint | Workspace | workspace instance | last-safe ReturnEnvelope 与可选 PathProgress reference |
| RecommendedPathReference | Supporting curation | Scope + Saved Path | 将既有 Path 推荐到 Scope，不复制 Path 或 Progress |

这些 records 即使拥有稳定 ID，也不因此进入 Library、Atlas 或 formal Relation endpoint。PathProgress、ResumePoint 和 ReturnStack 的删除后果只限工作连续性；Saved Path、Knowledge、Relation 与历史 Revision 保持不变。

---

# 8. Projection、Snapshot 与 Cache 的边界

## 8.1 Projection Definition

保存“如何观察”的规则，例如：

```text
definition_id
owner
base_scope
criteria
sort / grouping / layout
property_refs
revision
created_at / updated_at
```

View Definition 是 Primary Resource；Overview Projection Block 是 Overview 内嵌 definition。二者都不能保存一份静默成员真相。

## 8.2 Evaluation Basis

每次重要求值保存：

```text
definition_revision_ref
input_revision_vector
evaluated_at
coverage
index_state
source_availability
result_digest
stale_reason?
```

结果可以缓存；basis 不完整时必须显示 partial / indeterminate，而不是空列表。

## 8.3 Snapshot

Snapshot 是用户明确保留的历史边界。它冻结某次 evaluation、answer 或 path context，并保留所用 revisions；它不把派生结果转换为当前 accepted truth。

## 8.4 Cache

Cache 只服务性能与离线：

- 可以丢弃；
- 可以重建；
- 不能直接编辑；
- 不能成为唯一 export；
- 不能在 stale 时无标记显示；
- rebuild 失败保留上一份可用结果并说明 basis。

---

# 9. 新对象准入测试

任何新增 `Insight`、`Collection`、`Digest`、`Thread`、`Memory`、`Board`、`Card`、`Agent Run` 或其他名词，必须逐项回答：

1. 用户是否有独立、可复述的长期意图？
2. 它是否拥有不可由现有 canonical objects 完整重建的真相？
3. 它是否有独立 lifecycle，而不是父对象的一段内容或一次 evaluation？
4. 用户是否需要稳定 deep link、历史、导出与恢复？
5. 删除它是否有独立且可解释的后果？
6. 它是否不能由 Node、Group、Topic、View、Path、Snapshot、Proposal 或 Change Set 表达？
7. 它进入 Search、Library、Atlas、Ask 和 Relation 时各是什么单位？
8. 它的日常语言是否不增加新的强制心智模型？
9. 它属于哪个平面和 Truth Role？
10. 若不成为 Primary Resource，作为 Supporting、Embedded、Derived 或 Workspace 是否已经足够？

只有 1–8 都有强答案，且第 10 项不能满足时，才可修改十四类清单。新增数据库表、API object 或组件不触发准入。

---

# 10. Search、Library、Atlas 与 Deep Link 规则

## 10.1 Search

Search 使用两阶段表达：

```text
match record
  → aggregate to user-intended identity
  → show decisive match reason / anchor
```

例如：

- 命中 Content Block → 返回 Node，并打开 Anchor；
- 命中 Property Assertion → 返回 target identity，并显示属性原因；
- 命中 Evidence Fragment → 在 Evidence mode 返回 Source / Target context；
- 命中 Revision → 在 History mode 返回所属对象版本；
- 命中 Answer Claim → 在 Saved Answer mode 返回 Knowledge Snapshot。

## 10.2 Library

Library 不出现 `All Records`。专用入口分别承担：

- 全部知识：Node identities；
- 群层级：Placements；
- 路线与回答：Saved Path / Knowledge Snapshot；
- Views：View Definitions；
- Archived：按 Primary Resource kind 分组。

Revision、Binding、Assertion、Run、Evaluation 与 Workspace State 只能从所属资源或专用高级模式进入。

## 10.3 Atlas

Canonical Atlas 只读取 Accepted Knowledge Plane。Proposal、Working、Query Overlay、similarity、shared tags、View membership 和 Source co-occurrence 使用独立 layer，并在关闭后不留边。

## 10.4 Deep Link

支持记录 deep link 使用：

```text
owner_primary_ref
record_ref
entry_context
revision_or_snapshot_ref?
return_target
```

若 owner 被 archived / trashed，打开只读恢复态；若 record 已 tombstoned，显示历史摘要、影响与可恢复路径，不把链接重定向到无关当前对象。

---

# 11. 写入、采用与提交边界

## 11.1 写入目标必须明确

一次动作只能明确落到以下之一：

- Workspace State：只改变当前工作现场；
- Projection Definition：改变观察规则；
- Explicit Draft：保存用户主动选择暂不进入 current 的内容；
- Recovery Checkpoint：保存近期异常恢复保护，不进入事实读取；
- Proposal：保存待决定变化；
- Definition / Policy：改变可复用语义规则；
- Knowledge Commit：移动 accepted pointer 或创建正式结构 / Relation；
- Source Commit：保存材料 truth；
- Governance Record：保存变化与依据。

界面不能用一个通用 Save 同时完成多个后果。

## 11.2 派生结果的正确编辑入口

- 改 View result → 编辑 View Definition 或 target object；
- 改 Overview Projection row → 编辑 projection rule 或 underlying knowledge；
- 改 Search result → 编辑对象，不编辑 index hit；
- 改 Graph cluster → 调整 layout / filter，不改 Relation truth；
- 改 AI Answer → 保存为 Working knowledge 或重新运行，不覆盖 Answer Snapshot；
- 改 Property summary → 编辑 Assertions，不编辑聚合值。

## 11.3 Definition change

Definition revision 先执行：

```text
impact preview
  → compatibility scan
  → migration plan
  → partial / full commit
  → dependent projections refresh
  → history + rollback
```

没有 migration commit 时，不改既有 Assertion、Relation 或 View semantics。

---

# 12. 生命周期、删除与级联

## 12.1 Derivable first

若对象完全可重建，删除动作默认只清除派生数据：

- Search index；
- embeddings；
- graph cluster；
- View Evaluation；
- Overview Projection result；
- recommendation ranking；
- disposable cache。

清除失败或重建失败不改变 canonical truth。

## 12.2 Supporting record deletion

- 删除 Annotation：不删已提升 Fragment / Binding；
- 删除 Binding：不删 Fragment、Source 或 Target；
- archive Property Definition：保留 Assertions、Views、Migration history；
- discard Explicit Draft：不删 Current Revision；
- delete Query Session convenience：保留已显式保存的 Knowledge Snapshot；
- remove Workspace State：不改 View Definition 或知识。

## 12.3 Primary Resource deletion

必须区分 Remove、Archive、Trash、Permanent Delete。跨平面引用进入 impact preview：

```text
direct dependents
historical dependents
derived dependents
external / exported references
restorable vs irreversible effects
```

优先保留 tombstone、snapshot 或 orphan state；Permanent Delete 只在 Trash 发起，并逐层说明无法重建的 truth。

## 12.4 ID 不复用

任何被导出、引用、同步或写入历史的稳定 ID 永不重新分配给新对象。Merge 使用 redirect / successor；Split 使用 lineage；删除使用 tombstone。

---

# 13. AI 读取与写入合同

## 13.1 默认可用层

| Plane | 默认 Ask 使用 | 条件 |
|---|---|---|
| Accepted Knowledge | 是 | 当前 Scope / policy |
| Source Truth | 按需 | 可引用、在来源策略内 |
| Structure & Curation | 是 | 只用于 scope / route，不伪装事实 |
| Governance & History | 否 | 用户询问历史、变化或显式包含 |
| Definition & Policy | 是 | 用于解释属性、类型、适用和规则 |
| Projection & Workspace | 只作导航 | 不作为 Claim factual basis |

## 13.2 非默认内容

Explicit Draft、Proposal、Recovery、Annotation、旧 Answer、Query Run output、stale cache 与 rejected candidate 默认不进入事实回答。用户显式包含 Draft 或临时 Buffer 时，Answer 必须分层标明；Recovery 不可作为直接 Query Basis。

## 13.3 AI 输出的五种后果

1. **Answer Snapshot**：回答本次问题；
2. **Projection Evaluation**：生成当前观察；
3. **Proposal**：提出可判断变化；
4. **Working Patch**：写入未采用分支；
5. **Knowledge Change Set**：经用户或明确有限规则提交正式变化。

五者不可共用“已保存”或“AI 已整理”状态。

## 13.4 Retrieval 不改变对象层级

模型检索到 Block、Assertion、Fragment、Binding、Revision 或 Run 时，Answer Claim 仍回到 owner identity + exact locator；检索颗粒度不制造新 Knowledge Node。

---

# 14. 用户表面与渐进披露

## 14.1 P0 Calm

默认只显示：

- 当前 Scope 与对象；
- 连续知识内容；
- 一个主要动作；
- 必要的一句状态；
- 返回、深入、沿关系探索或查看来源的自然入口。

不显示 plane、identity class、record kind、revision ID 或 cache basis。

## 14.2 P1 Focused

选中对象时可见：

- 它出现在哪里；
- 关键关系；
- 来源与版本摘要；
- 当前是否有未完成修改、变化或覆盖限制。

## 14.3 P2 Decision

编辑、接受、删除、迁移或恢复时可见：

- 正在改变哪个 truth；
- 会影响哪些 Primary Resources；
- 哪些 supporting records 被保留；
- 哪些 projections 会刷新；
- 能否撤销或恢复。

## 14.4 P3 Forensic

主动检查时可见：

- stable IDs；
- revision / activity lineage；
- Binding、Selector、Run basis；
- Definition compatibility；
- evaluation coverage；
- manifest 与 round-trip checks。

## 14.5 禁止对象徽章墙

同一表面最多显示一个影响当前行动的状态说明。`Node · Accepted · Fresh · Available · Indexed · Local · Synced · No conflict` 这类内部轴列举不进入默认 UI。

---

# 15. 导出、恢复与可移植性

## 15.1 Knowledge Package manifest

```text
package
  primary_resources/
  knowledge_records/
  source_truth/
  provenance/
  definitions_and_policies/
  governance_and_history/
  projections_optional/
  workspace_continuity_optional/
  attachments/
  redirects_and_tombstones/
  integrity_manifest
```

## 15.2 必须保留

- Primary Resource identities 与 lifecycle；
- accepted pointers、Content Revisions、Branches 与 Anchors；
- Relation identities、all Relation Revisions、assertion dispositions、successor graph、Candidates adoption lineage、Challenges、Review Cases、Decision Events、Support Set Revisions 与 Endpoint Transition Cases；
- Source Revision、Representation、Selector、Fragment、Binding 与 Source Attachments；
- Definition IDs、revisions、Assertions 与 migration history；
- Change Set、Proposal decisions、Knowledge Snapshots 与 used revisions；
- Placements、Group Boundary Revisions、Topic parents、Topic transformation lineage、Path steps、View definitions；
- redirects、successors、tombstones；
- bytes / digests / counts / referential integrity。

## 15.3 可选或可重建

- Search index；
- embeddings；
- graph clusters；
- View Evaluations；
- Overview Projection cached results；
- recommendation rankings；
- temporary filters；
- cursor / scroll / pane state。

## 15.4 Restore 完成条件

Restore 不是“文件解压成功”。至少验证：

1. Primary IDs 数量与 digest；
2. accepted pointers 可达；
3. Group → Placement → Node 路径；
4. Source → Revision → Representation；
5. Source → Attachment → Group / Topic exact path；
6. Fragment → Binding → Target；
7. Group Boundary Revision 与 Topic transformation lineage 可达；
8. View / Projection definitions 引用有效；
9. Property / Relation definitions 可解析；
10. Snapshots 能回到 used revisions；
11. redirects / tombstones 行为；
12. 删除全部 optional projections 后可以重建并读写。

---

# 16. 事件、日志与 Event Sourcing 边界

## 16.1 需要不可变活动的地方

- current / historical content revision；
- Source revision / transform activity；
- high-impact Change Set；
- Proposal decision；
- Definition migration；
- destructive lifecycle action；
- Answer / Snapshot history；
- sync conflict resolution。

## 16.2 不需要事件流成为真相的地方

- pane width；
- hover / focus；
- temporary filters；
- recommendation cache；
- graph physics steps；
- derived counts；
- ordinary preferences that can be stored as current value。

## 16.3 产品决定

本合同只冻结不可变历史语义，不决定采用 Event Store、关系数据库、文档存储或混合架构。工程不得以“事件溯源”为由把每次键击、hover、cache refresh 和 model token 都升级为长期产品对象。

---

# 17. 质量指标与反指标

## 17.1 质量指标

- **Object Responsibility Accuracy**：用户动作是否落到正确 resource / record；
- **Surface Simplicity**：普通任务无需理解 supporting identities；
- **Truth Separation**：Projection、History、Recovery、Source 与 Current Knowledge 不互相冒充；
- **Deep-link Recovery**：内部 record deep link 能回到 owner 与上下文；
- **Deletion Safety**：跨平面依赖不被静默级联删除；
- **Rebuildability**：清除派生层后产品可完整重建；
- **Round-trip Integrity**：导出恢复后身份、引用与历史可达；
- **AI Layer Fidelity**：回答能区分 accepted、source、working、proposal、history 与 inference。

## 17.2 反指标

- 数据表、entity、API object 或 event 数量；
- 内部对象页面数量；
- graph node 数量；
- badge / state 数量；
- 导出文件数量；
- 用户打开 P3 诊断的频率；
- 缓存命中被包装成知识质量。

---

# 18. 十六个代表场景

## 18.1 正文命中

用户搜索到一个长 Node 第四段。结果仍以 Node identity 出现，并在打开后定位 Anchor；不生成 Block 卡片。

## 18.2 属性命中

用户搜索“适用于法国、租金低于 900 欧元”。结果返回符合条件的 Node / Group，并解释 Property Assertion 与 Applicability；Assertion 不独立成行。

## 18.3 历史版本命中

用户显式切换“包括历史版本”。结果显示所属 Node、版本时间和变化原因；默认搜索不让旧 Revision 与当前 Node 竞争。

## 18.4 Evidence deep link

用户打开旧 Citation。系统进入 Source identity 的确定 Revision 与 Fragment，上方说明它支撑哪条 Node Claim，并保留返回答案路径。

## 18.5 删除 Annotation

用户删除已经提升过的 highlight。Annotation 消失，Fragment / Binding / Node 仍保留，并说明提升后的证据不受影响。

## 18.6 删除 View

用户删除“法国租房条件”View。规则与其历史被归档或删除，Node、Placements、Assertions 与当前知识均不改变。

## 18.7 View partial index

View 依赖尚未完成迁移的 Property。旧 evaluation 可继续查看但标记 stale / partial；系统不把未评估对象写成“不符合”。

## 18.8 Overview Projection refresh

Topic 新增 Placement 后，Structure Projection 重算；Overview editorial prose 与 revision 不改变。

## 18.9 Ask 显式包含 Draft

用户明确要求“也参考这份草稿”。Answer 把 Current 与 Draft 分层引用；下一次普通 Ask 恢复默认排除 Draft。若用户从 Editor 发起 Ask 且 commit 失败，未提交 Buffer 只能成为本次临时 basis，Recovery Checkpoint 不能被查询。

## 18.10 Re-evaluate Saved Answer

旧 Knowledge Snapshot 保留 Original Answer 与 used revisions；新 Run 创建新的 Answer Snapshot 与 diff，不覆盖历史。

## 18.11 Relation from property reference

一个 Node-reference Assertion 指向另一个 Node。UI 提供导航，但 Local Graph 不画正式边；只能产生独立 RelationCandidate，用户检查 statement、direction 与 Applicability 并采用后才物化 Relation。

## 18.12 Source permanent delete

用户从 Trash 永久删除 Source bytes。系统保留 tombstone、受影响 Bindings 与 Knowledge Nodes，并明确哪些 Citation 只能查看 snapshot、哪些不可核验。

## 18.13 Clear all caches

用户执行安全索引重建。View results、Search index、Graph layout 与 projection cache 被重建；Current Knowledge、Sources、History 与 Definitions 不变。

## 18.14 Import unknown object type

旧库导入一个无法映射的 `collection`。系统保留原始 payload，要求映射为 Group、Topic、View、Path 或 unsupported archive，不静默创建第十五种容器。

## 18.15 Proposal candidate flood

AI 检测到 200 个候选。系统聚合为少量 Decision Bundles；raw candidates 只有内部 record，不在 Review 生成 200 个主要资源。

## 18.16 Complete round-trip

导出包不含任何可选 projection cache。恢复后仍能浏览 Groups、读取 Nodes、打开 Sources、核验证据、查询历史、重建 Views 与 Search，并恢复稳定 IDs。

---

# 19. 关键状态矩阵

| Record | Default Ask | Global Search default | Library | Atlas | Canonical export |
|---|---:|---:|---:|---:|---:|
| Node Current Revision | 是 | 是 | 是 | 是 | 是 |
| Node Explicit Draft | 否 | 仅 Draft scope | 草稿 View | 否 | 是 |
| Recovery Checkpoint | 否 | 否 | 仅恢复入口 | 否 | Continuity / recovery 可选 |
| Content Revision historical | 否 | 仅历史模式 | 通过 History | 否 | 是 |
| Source current / historical Revision | 按策略 | Source 模式 | Sources | 否 | 是 |
| Evidence Fragment | 作为 Claim support | Evidence 模式 | 通过 Source / Target | Provenance only | 是 |
| Source Attachment | 否 | 聚合到 Source / Scope owner | 通过 Group / Topic / Source | 否 | 是 |
| Source Annotation | 否 | Annotation 模式 | 通过 Source | 否 | 是 |
| Proposal | 否 | Review 模式 | 否 | suggested layer only | 是 |
| Query Run / old Answer | 否 | Answer history mode | 通过 Snapshot | query overlay only | 已保存时是 |
| Property Assertion | 随 target | 聚合到 target | 随 target | 只作 filter | 是 |
| View Evaluation | 否 | 否 | 通过 View | 否 | 可选 |
| Workspace State | 否 | 否 | 只恢复现场 | 只恢复布局 | 可选 |

---

# 20. Given / When / Then 验收

## 20.1 Block 命中聚合

**Given** Search 命中一个 Node 内部 Block  
**When** 用户查看结果  
**Then** 只显示一个 Node identity、命中原因和 Anchor preview；打开定位原段落，返回恢复原 Result Set。

## 20.2 Revision 不竞争当前知识

**Given** Node 有五个历史 Revisions  
**When** 用户执行默认 Search / Ask  
**Then** 只使用 current Accepted；只有显式历史模式才展示旧版本，并始终附 owner Node。

## 20.3 View result 不可直接改真相

**Given** View 显示十条知识  
**When** 用户尝试删除其中一行  
**Then** 系统区分“从当前结果隐藏 / 修改 View rule / 归档知识”；删除 View row 不成为含糊的知识删除。

## 20.4 Projection 可重建

**Given** 所有 View Evaluation、Search index 和 graph cache 被清除  
**When** 系统重建  
**Then** Primary Resources、current content、Definitions 与 History 不变，重建结果带新 basis 与 coverage。

## 20.5 Annotation 删除不级联

**Given** Annotation 已提升为 Fragment + Binding  
**When** 删除 Annotation  
**Then** Fragment、Binding、Target 与 Citation 保留；界面明确“只删除阅读标记”。

## 20.6 Binding 删除不级联

**Given** Fragment 支撑两个 Targets  
**When** 删除其中一个 Binding  
**Then** 只移除该作用；Fragment、另一个 Binding、Source 与两个 Targets 均不被删除。

## 20.7 Query history 不污染

**Given** 用户有一条包含错误的旧 Answer Snapshot  
**When** 发起普通 Follow-up 或新 Ask  
**Then** 旧 Answer 不作为事实 basis；若引用历史，必须标为 previous answer 并回到其 supports。

## 20.8 Draft 显式包含

**Given** Node 有 Current Revision 与 Explicit Draft  
**When** 用户显式要求包含 Draft  
**Then** Answer 分层显示差异和非当前状态；不会移动 current pointer 或刷新 canonical Atlas。

## 20.9 Definition change 不静默迁移

**Given** Property type 从 Text 改为 Date  
**When** 保存 Definition change  
**Then** 先生成 Migration Preview；不可转换值保留 legacy；Views 标明 compatibility / coverage；没有 commit 不改变 Assertions。

## 20.10 Relation endpoint 守门

**Given** Topic、Source、Fragment、Assertion 和 Query Run 都有 stable IDs  
**When** 用户或 AI 尝试建立正式 Relation  
**Then** 只有 Node↔Node 或 Group↔Group 可提交；其他连接路由到 Placement、Evidence、Reference、History 或 Query overlay。

## 20.11 Primary Resource 准入

**Given** 团队提出新的 `Insight Card` 对象  
**When** 运行十项准入测试  
**Then** 若它可由 Node + View / Proposal 表达，拒绝新增 Primary Resource，并记录正确 supporting / projection 归属。

## 20.12 Deep link 恢复语境

**Given** 用户打开一个 Evidence Binding 或 Query Run deep link  
**When** record 仍有效  
**Then** 页面显示 owner Primary Resource、record role、历史 basis 与返回目标，不呈现孤立数据库详情页。

## 20.13 Source permanent delete impact

**Given** Source 被多个 Fragments、Bindings、Nodes 与 Answers 使用  
**When** 用户发起 Permanent Delete  
**Then** Preview 分层列出 bytes、snapshots、locators、Bindings、knowledge 与 history 后果；不级联删除 Nodes。

## 20.14 Workspace reset 安全

**Given** 用户重置布局与工作现场  
**When** Selection、pane、scroll、temporary filters 和 graph viewport 被清除  
**Then** View Definitions、Saved Paths、Placements、Relations 与 content 均不改变。

## 20.15 AI 写入目标明确

**Given** AI 生成一段综合与三条结构建议  
**When** 用户选择保存  
**Then** 系统分别提供 Answer Snapshot、Working Patch、Proposal 与 Knowledge Change；不使用一个 Save 自动完成全部后果。

## 20.16 Export Round-trip

**Given** Knowledge Package 排除所有 optional projections 与 Workspace State  
**When** 在新环境恢复并重建  
**Then** IDs、accepted pointers、结构、Relations、Sources、Fragments、Bindings、Definitions、Snapshots、redirects 与 tombstones 可达；Search / Views / Graph 可重建。

## 20.17 Boundary 与 membership 分离

**Given** Group Boundary 被澄清，但原有 Topics、Placements、Attachments 与 Views 仍有效  
**When** 保存 Boundary Revision  
**Then** 只更新 Group 的 current boundary pointer 和历史；内容保持原位，boundary tension 可被检查；系统不静默迁移或删除结构记录。

## 20.18 Placement 与 Attachment 分离

**Given** 一份 Source attached 到 Topic A，同时一个由它支撑的 Knowledge placed 到 Topics A 与 B  
**When** 用户 detach Source from A  
**Then** Source identity、Knowledge Placements、Fragment、Binding 与 B 的路径均保持；只有当前 Source Attachment 生命周期改变。

## 20.19 Topic transformation lineage

**Given** Topic A 被 merge、Topic B 被 split、Topic C 被 transfer  
**When** 旧 deep link、Saved Path、Placement 与 Source Attachment 被打开  
**Then** rename / move 继续解析同一 identity；merge / split / transfer 根据 Change Set 进入唯一 successor、候选选择或历史只读态，不复用旧 ID，也不生成伪 Relation。

---

# 21. 官方研究依据与产品推论

## 21.1 W3C PROV-O

W3C PROV-O 把 provenance 的起点分为 Entity、Activity、Agent，并进一步定义 Revision、Quotation、Primary Source、Generation、Invalidation 与 qualified influence。它说明：为了追溯而持久存在的实体与活动可以拥有正式语义，但不必与领域知识对象使用同一用户表面。

产品推论：Source Revision、Representation、Binding 与 Activity 应被完整保存和检查，但属于 provenance plane，不进入 canonical Semantic Graph。

[W3C PROV-O](https://www.w3.org/TR/prov-o/)

## 21.2 W3C Web Annotation Data Model

Web Annotation 将 Annotation、Body、Target、SpecificResource、Selector 与 State 分开；同一个 target 的特定片段和状态可以有独立身份与约束。该模型证明“可以精确引用”与“成为顶层知识对象”是两件事。

产品推论：Annotation、Fragment、Selector 与 Binding 分层；支持 deep link 与历史核验，但不为每条 highlight 创建 Knowledge Node。

[W3C Web Annotation Data Model](https://www.w3.org/TR/annotation-model/)

## 21.3 Wikidata Data Model

Wikidata 区分 Item、Statement、Property、Value、Qualifier、Reference 与 Rank；restrictive qualifier 会改变 statement 的适用范围，reference 则说明依据。它说明一个知识系统可以拥有丰富、可寻址的内部陈述结构，而不把 qualifier 和 reference 提升为与 Item 相同的浏览单位。

产品推论：Property Assertion、Applicability、Evidence 与 Node identity 分工；Search 和 Library 聚合到用户想找的对象，同时保留 statement-level 精度。

[Wikidata Data Model](https://www.wikidata.org/wiki/Wikidata:Data_model)、[Wikidata Statements](https://www.wikidata.org/wiki/Help:Statements/en-gb)

## 21.4 CQRS 与 Materialized View

Microsoft Azure Architecture Center 将 write model 与 read model / projection 分开，并明确 materialized view 可由源数据重建、不能由应用直接修改。它同时提醒 read model 可能滞后，必须处理 coverage 与 eventual consistency。

产品推论：View Evaluation、Search index、Overview Projection 与 Graph cluster 属于可重建读取层；用户编辑 definition 或 canonical input，而不是改缓存结果。

[CQRS Pattern](https://learn.microsoft.com/en-us/azure/architecture/patterns/cqrs)、[Materialized View Pattern](https://learn.microsoft.com/en-us/azure/architecture/patterns/materialized-view)

## 21.5 Event Sourcing 的限制

Azure 官方 Event Sourcing 指南强调 append-only history 的审计与重建价值，也明确指出它引入 schema、并发、查询和迁移复杂度，通常不应全系统无差别采用。

产品推论：Current / Historical Revision、Source change、Change Set 与 Definition migration 保留不可变历史；hover、layout、cache refresh 与普通 preference 不被升级为事件真相。

[Event Sourcing Pattern](https://learn.microsoft.com/en-us/azure/architecture/patterns/event-sourcing)

## 21.6 研究不证明什么

上述标准和模式证明分层方法存在且具有清晰语义，不证明本产品的十四资源清单、六平面命名、默认 Search 单位、P0–P3 披露和删除文案已被真实用户验证。后者仍是产品决定与待验证假设。

---

# 22. 对相邻合同的同步要求

## 22.1 产品定义

- 把“十四个产品对象”统一改为“十四类主要产品资源”；
- 增加六平面与 identity / truth role 正交模型；
- 已冻结决定新增 stable identity ≠ primary resource、Projection 可重建、Workspace 不写知识、分层导出。

## 22.2 交互架构

- 基础决定新增对象层级；
- Search、Library、Atlas 与 deep link 使用 owner-first presentation；
- 增加 PrimaryResourceContext、RecordRoleSummary、EvaluationBasis、OwnerBacklink、RebuildStatus 等组件合同；
- 验收覆盖 record deep link、projection rebuild、workspace reset、AI layer fidelity。

## 22.3 流程板

- PB-00 保存 workspace continuity 但不写知识；
- PB-04 聚合检索命中到 owner identity；
- PB-06 / PB-07 分开 Knowledge change 与 provenance activity；
- PB-08 验证 projection rebuild；
- PB-10 分层 export / restore。

## 22.4 产品语言

- “对象”在用户界面只用于普通指代，不显示 Primary / Supporting / Embedded；
- supporting record 页面必须先说“这是谁的什么记录”；
- Projection / cache / workspace reset 使用“重新生成结果”“重置当前布局”，不使用删除知识语言。

## 22.5 完整性审计

新增完成门槛：系统失去全部派生层仍可恢复；任何 supporting record 可回到 owner；新增 object 必须通过准入测试；十四主要资源不再被误解为全部数据模型。

---

# 23. 结论

本产品需要深模型，但深模型不能被压成一张无差别对象图，也不能为了界面简洁而丢失历史、证据和身份。

> **十四类主要产品资源定义用户长期拥有并需要独立理解的产品责任；支持身份保存版本、证据、运行和定义；Projection 负责可重建观察；Workspace State 负责连续工作。稳定 ID 不制造新知识对象，漂亮页面也不能改变真相角色。**

这条边界让产品可以同时具备知识库的完整性、AI 系统的可追溯性和日常阅读的安静表面，也防止未来每增加一种能力就增加一套新的对象、卡片与导航。
