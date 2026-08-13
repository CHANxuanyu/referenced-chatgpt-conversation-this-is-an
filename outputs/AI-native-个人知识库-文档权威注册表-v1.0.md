# AI-native 个人知识库

## 文档权威注册表 v1.0

> 日期：2026-08-10  
> 目的：给每份产品文档唯一、可机器读取的权威状态，停止使用“顶部覆写但正文仍保留旧模型”的隐含规则  
> Canonical：`ai-native-knowledge-base/canonical/AI-native-个人知识库-终局产品设计文档-v6.0.md`  

---

# 0. 状态定义

| Status | 权力 | 使用规则 |
|---|---|---|
| **CANONICAL** | 定义当前产品真相 | 发生冲突时仅低于用户最新明确意图 |
| **ACTIVE_APPENDIX** | 深化 Canonical 指定领域的现行合同 | 必须有 Canonical pointer、AC 映射和 fixture 对齐；冲突时服从 Canonical |
| **DECISION_COMPANION** | 帮助用户反对或确认推荐默认 | 不新增产品真相；冲突时服从 Canonical |
| **EVIDENCE** | 记录真实截图、审计结论或形成过程 | 证明问题与来源，不能反向定义产品 |
| **FIXTURE** | 提供真实内容和验收数据 | 约束设计真实性，不新增导航或对象类型 |
| **MIGRATION_QUEUE** | 含有可复用深层规则，但尚未逐段迁移到 v6 | 当前非规范；只能作为候选参考 |
| **EXPERIMENTAL_APPENDIX** | 未验证的精确 taxonomy / state model | 不能进入默认界面、日常语言或不可逆 schema |
| **HISTORICAL** | 被替代的历史产品定义或旧设计结构 | 只用于理解演化，不可指导新设计 |

只有完成逐段冲突检查、Canonical pointer、术语映射和 AC-01–AC-32 对应后，`MIGRATION_QUEUE` 才能升级为 `ACTIVE_APPENDIX`。旧专项合同没有任何一份被自动升级；当前 Active Appendix 仅限注册表显式列出的新合同。

---

# 1. 当前产品权威

| 文件 | Status | 责任 |
|---|---|---|
| `ai-native-knowledge-base/canonical/AI-native-个人知识库-终局产品设计文档-v6.0.md` | **CANONICAL** | 产品本体、心智模型、资源、场景、旅程、状态和核心验收 |
| `ai-native-knowledge-base/contracts/AI-native-个人知识库-知识群层级、目录规模与结构演化合同-v1.0.md` | **ACTIVE_APPENDIX** | 深化 Group、Topic、Catalog、Placement、规模和结构演化；Overview / Topic Opening 的阅读正文由连续阅读合同拥有；以 v6 为上位权威 |
| `ai-native-knowledge-base/contracts/AI-native-个人知识库-AI查询、知识探索与返回连续性合同-v1.0.md` | **ACTIVE_APPENDIX** | 深化 Search、Ask、Answer、Question、Claim support、Query history、Answer ↔ Explore 与 exact return；以 v6 为上位权威 |
| `ai-native-knowledge-base/contracts/AI-native-个人知识库-知识进入、来源保存与知识形成合同-v1.0.md` | **ACTIVE_APPENDIX** | 深化 Add、Direct Current、Source save、Annotation、Evidence Binding、AI Proposal、import、partial success 与 formation return；以 v6 为上位权威 |
| `ai-native-knowledge-base/contracts/AI-native-个人知识库-关系、群级网络与探索连续性合同-v1.0.md` | **ACTIVE_APPENDIX** | 深化 Relation statement、Candidate / Current / History、Group Relation qualification、Pair、Graph / List、Relation Scene、规模与 exact return；以 v6 为上位权威 |
| `ai-native-knowledge-base/contracts/AI-native-个人知识库-Overview、连续阅读与知识正文合同-v1.0.md` | **ACTIVE_APPENDIX** | 深化 Overview / Topic Opening / Knowledge Paper、正文深度、Anchor、direct edit、History、Recovery 与阅读 exact return；以 v6 为上位权威 |
| `ai-native-knowledge-base/contracts/AI-native-个人知识库-Library入口、目录浏览与继续阅读合同-v1.0.md` | **ACTIVE_APPENDIX** | 深化 cold start、daily return、All Groups / All Knowledge、Resume / Pin / Recent / Saved View / Saved Path / Recovery 分权、Open / Continue 与 Library degradation；以 v6 为上位权威 |
| `ai-native-knowledge-base/contracts/AI-native-个人知识库-表面架构、场景家族与完整设计证明合同-v1.0.md` | **ACTIVE_APPENDIX** | 深化统一 App Shell、五个 Scene families、Surface roles、Search / Ask / Add transitions、Return Envelope、state / responsive / accessibility equivalence 与 DPB-01–18；以 v6 为上位权威 |
| `ai-native-knowledge-base/contracts/AI-native-个人知识库-用户可见信息架构、产品语言与复杂度披露合同-v1.0.md` | **ACTIVE_APPENDIX** | 深化一个`知识库`、五个日常内容概念、三个全局动作、用户结果与错误文案、复杂度披露、accessible naming、LPX-01–18 与 LAC-01–32；以 v6 为上位权威 |

任何文件若与 v6 冲突，以 v6 为准；更长、更早或更精确的旧表格不拥有更高权力。

---

# 2. 当前决策、证据与夹具

| 文件 | Status | 责任 |
|---|---|---|
| `ai-native-knowledge-base/decisions/AI-native-个人知识库-关键产品决策审阅稿-v1.0.md` | **DECISION_COMPANION** | 让用户集中确认十一项高影响推荐默认 |
| `ai-native-knowledge-base/evidence/AI-native-个人知识库-v5结构收敛与文档债审计-v1.0.md` | **EVIDENCE** | 解释为什么 v5 被 v6 取代、哪些内部对象和 taxonomy 被降级 |
| `ai-native-knowledge-base/evidence/AI-native-个人知识库-v6需求、旅程、验收与设计证据追踪矩阵-v1.0.md` | **EVIDENCE** | 追踪用户意图、十一条旅程、AC-01–AC-32、三份夹具与当前 Ardot 证据；不新增产品真相 |
| `ai-native-knowledge-base/evidence/AI-native-个人知识库-v6用户可见语言迁移审计-v1.0.md` | **EVIDENCE** | 审计旧语言规范、现行 Active contracts 与当前 Ardot 的用户可见术语冲突，记录迁入新语言 Active Appendix 的依据与排除项；不新增产品真相 |
| `ai-native-knowledge-base/evidence/AI-native-个人知识库-关键产品决定对抗性审计-v1.0.md` | **EVIDENCE** | 用竞品模式、反例和三份夹具挑战独立知识、Group / Topic、Overview、Relation 与 AI 写回；不新增产品真相 |
| `design-audit-ardot/Ardot-v5产品决策错位审计-v1.0.md` | **EVIDENCE** | 当前 Ardot 七屏相对产品定义的逐屏错位证据 |
| `design-audit-ardot/Ardot-设计审查与全量设计蓝图-v1.0.md` | **EVIDENCE** | 历史设计证据、覆盖缺口和视觉迁移记录；不再是产品定义 |
| `design-audit-ardot/群级关系升级门槛与视觉证明缺口审计-v1.0.md` | **EVIDENCE** | Screen 2 / 3 群关系真实性缺口 |
| `design-audit-ardot/探索连续性设计证明增补-v1.0.md` | **EVIDENCE** | 探索、返回与路径的设计缺口 |
| `design-audit-ardot/直接写作与当前知识提交设计证明增补-v1.0.md` | **EVIDENCE** | 普通写作、Current 与 Proposal 分权缺口 |
| `design-audit-ardot/library-definition-round-2026-08-10/Ardot-Library与核心表面产品错位审计-v1.0.md` | **EVIDENCE** | 以本轮 Screen 1、Screen 2、Screen 3 与七屏总览截图审计 Page list / Surface Architecture、Library、Reading、Relation 与完整设计证明缺口 |
| `design-audit-ardot/library-definition-round-2026-08-10/02-current-screen-1-library.png` 等本轮截图 | **EVIDENCE** | 2026-08-10 当前 Ardot 的逐屏可见证据；只证明已观察到的视觉与状态，不证明交互行为 |
| `visual-directions/README.md` | **EVIDENCE** | 方向 3 + 2 的历史视觉选择与限制 |
| `ai-native-knowledge-base/fixtures/AI-native-个人知识库-真实端到端使用样例与设计数据夹具-v1.0.md` | **FIXTURE** | 时效、资格、条件、来源变化与跨群任务 |
| `ai-native-knowledge-base/fixtures/AI-native-个人知识库-第二真实端到端夹具-概念学习、多语境复用与群关系-v1.0.md` | **FIXTURE** | 稳定概念、丰富层级、多 Placement、Question 与关系任务 |
| `ai-native-knowledge-base/fixtures/AI-native-个人知识库-基础可用性夹具-空库直接写作搜索与恢复-v1.0.md` | **FIXTURE** | 空库、直接写作、Search、Source partial、离线与语义恢复 |

---

# 3. 迁移队列：可复用，但当前不具规范权威

## 3.1 核心体验与结构

| 文件 | Status | 迁移时只保留 |
|---|---|---|
| `ai-native-knowledge-base/migration-queue/01-核心体验与结构/AI-native-个人知识库-核心心智模型与连续探索合同-v1.0.md` | **MIGRATION_QUEUE** | 一个 Library、纵向阅读、按需关系、连续返回 |
| `ai-native-knowledge-base/migration-queue/01-核心体验与结构/AI-native-个人知识库-核心体验与知识群生命周期-v1.0.md` | **MIGRATION_QUEUE** | Group 从 Bare 到长期演化的用户体验 |
| `ai-native-knowledge-base/migration-queue/01-核心体验与结构/AI-native-个人知识库-核心导航与复杂度收敛合同-v1.0.md` | **MIGRATION_QUEUE** | stable Catalog、Resume 与 global action 的有效规则已迁入 Library Active Appendix；仅保留尚未核验的稀有复杂度边界参考 |
| `ai-native-knowledge-base/migration-queue/01-核心体验与结构/AI-native-个人知识库-首日到日常核心旅程合同-v1.0.md` | **MIGRATION_QUEUE** | 第一条可返回知识、Bare Group、daily return 与非 AI 路径已迁入 Formation / Library Active Appendices；旧 Places / stage 模型非规范 |
| `ai-native-knowledge-base/migration-queue/01-核心体验与结构/AI-native-个人知识库-规模化知识空间与长期可浏览性合同-v1.0.md` | **MIGRATION_QUEUE** | F1 / F10 / F100 / F10K 同一骨架与 anchor required |

迁移时删除旧 Home / Atlas / four Places / stage scoring；统一映射到 v6 Library、Reading、Relation Space 与 Supporting Utilities。

## 3.2 Group、Topic、Knowledge 与 Overview

| 文件 | Status | 迁移时只保留 |
|---|---|---|
| `ai-native-knowledge-base/migration-queue/02-对象结构与概览/AI-native-个人知识库-知识群边界与跨群架构合同-v1.0.md` | **MIGRATION_QUEUE** | Boundary、membership、Topic promotion、split / merge 后果 |
| `ai-native-knowledge-base/migration-queue/02-对象结构与概览/AI-native-个人知识库-知识群状态演化与身份连续性合同-v1.0.md` | **MIGRATION_QUEUE** | 正交状态和 identity continuity |
| `ai-native-knowledge-base/migration-queue/02-对象结构与概览/AI-native-个人知识库-知识节点粒度与内容组成合同-v1.0.md` | **MIGRATION_QUEUE** | 已迁移连续正文、Anchor、Split / Merge、Block 非对象化；只保留未迁移的稀有边界参考，旧 Node 术语非规范 |
| `ai-native-knowledge-base/migration-queue/02-对象结构与概览/AI-native-个人知识库-Overview形成编辑与更新合同-v1.0.md` | **MIGRATION_QUEUE** | 已迁移 Editorial prose / structure projection / Reference / local Diff；旧 Primary Resource 与过细治理模型非规范 |
| `ai-native-knowledge-base/migration-queue/02-对象结构与概览/AI-native-个人知识库-直接创作编辑与版本历史合同-v1.0.md` | **MIGRATION_QUEUE** | 已迁移 direct Current、recovery、session history、restore forward；旧对象和表面命名非规范 |
| `ai-native-knowledge-base/migration-queue/02-对象结构与概览/AI-native-个人知识库-属性Facet与适用条件合同-v1.0.md` | **MIGRATION_QUEUE** | 属性按需、Applicability、不把 schema 变写作门槛 |

Topic、Overview、Placement、Proposal、Change Set、Question state 不得在迁移后重新提升为平级 Primary Resources。

## 3.3 Relation 与探索

| 文件 | Status | 迁移时只保留 |
|---|---|---|
| `ai-native-knowledge-base/migration-queue/03-关系与探索/AI-native-个人知识库-知识深度与关系探索合同-v1.0.md` | **MIGRATION_QUEUE** | D / R 正交、Graph / List、exact return |
| `ai-native-knowledge-base/migration-queue/03-关系与探索/AI-native-个人知识库-关系陈述生命周期与网络可信性合同-v1.0.md` | **MIGRATION_QUEUE** | statement、qualifier、basis、standing、revision |
| `ai-native-knowledge-base/migration-queue/03-关系与探索/AI-native-个人知识库-群级关系聚合门槛与支撑充分性合同-v1.0.md` | **MIGRATION_QUEUE** | exit → signal → candidate → adoption；无关系合法 |
| `ai-native-knowledge-base/migration-queue/03-关系与探索/AI-native-个人知识库-知识群对照与关系检查器合同-v1.0.md` | **MIGRATION_QUEUE** | Pair comparison、shared lens、snapshot、return |
| `ai-native-knowledge-base/migration-queue/03-关系与探索/AI-native-个人知识库-探索路径、回返与继续合同-v1.0.md` | **MIGRATION_QUEUE** | Trail / Saved Path / Resume 分权已迁入 Relation / Library Active Appendices；旧 Workspace / Place 命名非规范 |
| `ai-native-knowledge-base/migration-queue/03-关系与探索/AI-native-个人知识库-知识群工作区与双镜连续性合同-v1.0.md` | **MIGRATION_QUEUE** | Quiet → Peek → Companion → Explore |

## 3.4 Search、Ask、Question、Source 与形成

| 文件 | Status | 迁移时只保留 |
|---|---|---|
| `ai-native-knowledge-base/migration-queue/04-搜索问答与来源/AI-native-个人知识库-搜索定位与知识找回合同-v1.0.md` | **MIGRATION_QUEUE** | exact Anchor、coverage、ambiguous / redirected / unavailable |
| `ai-native-knowledge-base/migration-queue/04-搜索问答与来源/AI-native-个人知识库-AI查询与知识回答合同-v1.0.md` | **MIGRATION_QUEUE** | Scope、Basis、Coverage、Claim citation、atomic write-back |
| `ai-native-knowledge-base/migration-queue/04-搜索问答与来源/AI-native-个人知识库-问题知识、未知与求解生命周期合同-v1.0.md` | **MIGRATION_QUEUE** | complex Question 的 criteria、unknown、reopen / successor |
| `ai-native-knowledge-base/migration-queue/04-搜索问答与来源/AI-native-个人知识库-来源证据与可追溯性合同-v1.0.md` | **MIGRATION_QUEUE** | Source identity、revision、fragment、binding、unavailable |
| `ai-native-knowledge-base/migration-queue/04-搜索问答与来源/AI-native-个人知识库-知识形成与维护循环-v1.0.md` | **MIGRATION_QUEUE** | Source Commit / Knowledge Commit、zero-yield、local Proposal |
| `ai-native-knowledge-base/migration-queue/04-搜索问答与来源/AI-native-个人知识库-Library浏览与动态视图合同-v1.0.md` | **MIGRATION_QUEUE** | stable Catalog、dynamic View 与入口 Lens 的有效规则已迁入 Hierarchy / Library Active Appendices；旧 Home / Working / Review 表面非规范 |

## 3.5 表面、流程、身份与语言

| 文件 | Status | 迁移时只保留 |
|---|---|---|
| `ai-native-knowledge-base/migration-queue/05-表面流程与语言/AI-native-个人知识库-产品语言与渐进披露规范-v1.0.md` | **MIGRATION_QUEUE** | Deep model / simple surface、Calm / Focused / Decision / Forensic、动作后果、AI / Source / Knowledge 声音与 truthful failure 已迁入新语言 Active Appendix；旧 14 resources、Home、Command、未归类、81-screen 与 Places / Surface 模型非规范 |
| `ai-native-knowledge-base/migration-queue/05-表面流程与语言/AI-native-个人知识库-产品对象层级与身份治理合同-v1.0.md` | **MIGRATION_QUEUE** | owner、truth role、stable identity 准入测试 |
| `ai-native-knowledge-base/migration-queue/05-表面流程与语言/AI-native-个人知识库-地点编排信息归属与跨地点连续性合同-v1.0.md` | **MIGRATION_QUEUE** | Return context、surface owner、event primary destination |
| `ai-native-knowledge-base/migration-queue/05-表面流程与语言/AI-native-个人知识库-交互架构与设计系统-v1.0.md` | **MIGRATION_QUEUE** | Shared Shell、selection、focus / inspect / open 的有效责任已迁入 Surface Active Appendix；旧 Place、layout 与 token 方案非规范 |
| `ai-native-knowledge-base/migration-queue/05-表面流程与语言/AI-native-个人知识库-产品流程板与组件状态图-v1.0.md` | **MIGRATION_QUEUE** | journey continuity、state responsibility 与 evidence bundle 的有效规则已迁入 Surface Active Appendix；旧 screen / component inventory 非规范 |
| `ai-native-knowledge-base/migration-queue/05-表面流程与语言/AI-native-个人知识库-产品表面架构与完整设计证明合同-v1.0.md` | **MIGRATION_QUEUE** | surface admission 与 responsive / accessibility proof 的有效规则已迁入新 `表面架构、场景家族与完整设计证明合同`；旧 four Places / 81-surface 模型非规范 |
| `ai-native-knowledge-base/migration-queue/05-表面流程与语言/AI-native-个人知识库-场景压力测试与产品修订-v1.0.md` | **MIGRATION_QUEUE** | failure / scale / real fixture regression cases |
| `ai-native-knowledge-base/migration-queue/05-表面流程与语言/AI-native-个人知识库-完整性审计与产品修订-v1.1.md` | **MIGRATION_QUEUE** | 遗漏检查方法；不得恢复旧对象和 Places |

以上文档正文仍包含旧编号、旧导航或过度对象化内容。完成迁移前不得把其中单句当现行需求发给设计或工程。

---

# 4. 实验性语义附录

| 文件 | Status | 当前边界 |
|---|---|---|
| `ai-native-knowledge-base/experimental/AI-native-个人知识库-知识关系类型注册表与跨层语义合同-v1.0.md` | **EXPERIMENTAL_APPENDIX** | 25-type registry 仅作研究材料；默认 UI 与 schema 不冻结 |
| `ai-native-knowledge-base/experimental/AI-native-个人知识库-群级关系类型注册表与语义互斥合同-v1.0.md` | **EXPERIMENTAL_APPENDIX** | 11-type registry 仅作研究材料；先验证 v6 六类意图与真实表达 |

只有当真实 fixture 和用户测试证明相邻类型可稳定辨认、确实改变行为，并且迁移成本合理，具体类型才可进入 Active Appendix。

---

# 5. 历史文档

| 文件 | Status | 被什么取代 |
|---|---|---|
| `ai-native-knowledge-base/history/AI-native-个人知识库-终局产品设计文档-v5.0.md` | **HISTORICAL** | v6.0 |
| `ai-native-knowledge-base/history/AI-native-个人知识库-终局产品设计文档-v4.0.md` | **HISTORICAL** | v5.0，现由 v6.0 取代 |
| `ai-native-knowledge-base/history/AI-native-个人知识库-产品定义-v3.0.md` | **HISTORICAL** | v4.0，现由 v6.0 取代 |
| `personal-cognitive-os/Personal-Cognitive-OS-Product-Design.md` | **HISTORICAL** | 产品中心已从 Cognitive OS 回到 Knowledge Library |
| `personal-cognitive-os/Personal-Cognitive-OS-产品设计文档-v1.0.md` | **HISTORICAL** | 同上 |
| `personal-cognitive-os/Personal-Cognitive-OS-产品设计文档-v2.1.md` | **HISTORICAL** | 同上 |
| `project-continuity/Project-Continuity-最终产品需求文档.md` | **HISTORICAL** | Project Continuity 不再是产品中心 |

历史文档可以解释为什么产品曾经漂移，但不能提供现行导航、对象、首页或视觉需求。

---

# 6. 维护规则

1. 新产品决定先修改 v6，再判断是否需要专项附录；
2. 新文档必须在首屏声明唯一 Status；
3. `MIGRATION_QUEUE` 迁移后创建新版本，不继续叠加覆写说明；
4. 每个 Active Appendix 必须列出它深化的 v6 sections 和 AC IDs；
5. Fixture 与 Evidence 不得被改写成产品决定；
6. 设计文件只读取 v6、确认过的 Decision Companion、Fixtures 和当前 Evidence；
7. 任何新对象先判断能否由四类 canonical truth families、Topic 结构身份与 supporting identity 表达；
8. 任何新 Place 必须证明 Library / Reading / Relation / Answer / Source / Utility 无法承担；
9. 每轮产品修订都检查是否恢复了 Home feed、Atlas product center、Review Inbox、全局节点云或 AI 自动推进；
10. 注册表随 Canonical version 一起更新。
