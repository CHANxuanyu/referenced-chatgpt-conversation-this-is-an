# AI-native 个人知识库

## 探索路径、回返与继续合同 v1.0 — Wayfinding、Trail、Saved Path、Progress 与 Resume

> 日期：2026-08-06  
> 文档性质：产品定义补充；冻结网络探索中的方向感、回返、分支、保存路线与继续现场，不是视觉稿、原型或研发排期  
> Canonical 产品定义：`AI-native-个人知识库-终局产品设计文档-v4.0.md`；发生冲突时以 v4.0 与用户最新明确意图为准  
> 相关合同：`AI-native-个人知识库-知识深度与关系探索合同-v1.0.md`、`AI-native-个人知识库-知识群工作区与双镜连续性合同-v1.0.md`、`AI-native-个人知识库-地点编排信息归属与跨地点连续性合同-v1.0.md`、`AI-native-个人知识库-关系陈述生命周期与网络可信性合同-v1.0.md`  
> 2026-08-08 Library Resume 覆写：旧 `Home Resume` 统一读取为 Library Groups catalog 顶部的一条显式恢复入口；普通启动、新窗口与 unsafe restore 不自动打开 deep Reading Workspace，普通 Group open 始终进入 canonical Overview  
> 2026-08-10 Relation Lifecycle 覆写：formal relation connector 必须固定 relation_revision_id 与保存时 statement；ended、superseded、retracted、transition_pending 与 archived 分别处理，Re-evaluate 不覆盖原 Path。  
> 阶段边界：只定义产品本身与未来设计必须证明的状态；**不授权开始原型，也不修改当前 Ardot 设计**

---

# 0. 执行判断

用户要的不是一个只会显示关系的图，而是一个能够真正进入、逐步理解并在之后继续的知识网络。现有规格已经回答“有哪些对象”“关系为什么成立”“图和列表怎样等价”，但还没有完整回答一次真实探索最常见的五个问题：

1. 我现在在知识结构的哪里？
2. 我刚才从哪里来到这里？
3. 我这一轮沿着什么理解线索走到了这里？
4. 哪些步骤值得保存为以后可复用的路线？
5. 我关闭产品后，下次到底从哪里继续？

如果这五项仍用一个 `path` 或 `history` 表达，产品会产生四类严重错误：

- breadcrumb 同时承担层级、访问历史和学习进度，用户无法预测 `Back` 与 `Up`；
- 鼠标 hover、图谱展开和正文滚动污染访问历史，返回变得不可信；
- Saved Path 保存原始点击流水而不是理解顺序，最终成为不可维护的浏览日志；
- `last_position` 写进 Saved Path，使同一条路线在用户继续阅读时不断被改写，无法被推荐、比较、版本化或共享。

本合同把这些责任拆成五种状态，并冻结它们的写入与生命周期。

## 0.1 本文件冻结的三十项决定

1. **Location is not Journey。** 结构位置、临时回返、当前探索轨迹、长期保存路线和继续位置是五种不同责任。
2. `DepthTrail` 只表达结构位置，不记录访问顺序。
3. `ReturnStack` 只恢复交互现场，不自动形成长期知识资产。
4. `ExplorationSession` 表达一次有边界的探索活动；`ExplorationTrail` 是其中有意义的打开步骤。
5. `SavedPath` 是用户主动选择、带目的的长期理解路线，不是浏览历史。
6. `PathProgress` 单独保存某个用户对某条 Saved Path 的完成位置；它不属于 Saved Path identity。
7. `ResumePoint` 保存一个安全、可解释的工作现场；它不是 Saved Path，也不是最近列表。
8. `QueryRoute` 属于一次 Answer Run；它不等于 Exploration Trail 或 Saved Path。
9. `RecommendedPathReference` 只把既有 Saved Path 策展进某个 Scope；它不复制 Path，也不改变 Topic order。
10. Hover 和 keyboard focus 只用于定位，不写 ReturnStack、Trail、Recent 或 Progress。
11. Inspect 只打开局部语境，不改变 durable Reading Target，也不写 Trail。
12. Open 才改变主要目标，并写入 ReturnStack；满足语义步条件时才写入 Trail。
13. Compare 是临时、有界集合，不因并排显示自动成为 Path。
14. Expand、collapse、filter、dismiss、group、pan、zoom 与 viewport 是场景操作，不是知识或路线步骤。
15. `Up` 沿结构位置返回父范围；`Back / Forward` 沿时间现场返回；`Close` 关闭当前 overlay / inspector；`Resume` 恢复安全现场。四者不得混用。
16. Back 后打开新目标会形成探索分支；系统不默认显示复杂树，但允许恢复“刚才的另一条分支”。
17. 浏览器式 Forward 可以在新分支产生后失效；当前 Exploration Session 仍保留轻量分支记录。
18. 保存路线只保存用户选择的有意义步骤；允许删除、补充、重排和写理由。
19. Path 中没有正式 Relation 的相邻步骤必须标为 `manual`，不能生成假边。
20. Path step 可以固定 placement context，但不复制 target identity。
21. Saved Path 保存 revision basis；默认打开当前对象，同时允许查看保存时的版本与变化。
22. Path 受影响时显示 current、redirected、changed、historical-only 或 unavailable，不静默改写步骤。
23. Re-evaluate Path 只提出 successor / draft revision，不覆盖原路线。
24. Continue Path 只更新 PathProgress 和 ResumePoint，不创建 Saved Path revision。
25. Library Groups catalog 最多突出一个可解释的 Resume；Recent、Pinned、Saved Paths 与 Attention 保持不同排序语义。
26. 多窗口分别维护 ReturnStack、ExplorationSession 与 ResumePoint；Saved Path identity 可跨窗口共用，PathProgress 按用户和运行语境隔离。
27. 图、关系列表、层级树、搜索结果与 Answer Route 使用同一套 Open / Return / Save semantics。
28. 本合同是待真实任务验证的终局产品决定，不以竞品行为或当前七张概念图证明成立。
29. 普通启动恢复上次稳定 Library catalog state，不自动恢复 deep Reading；只有显式`继续`才打开 ResumePoint。
30. First use、new window、needs_repair、target unavailable 与 AI / Index offline 均以 Stable Library 或 nearest safe reading fallback 收敛；不复制 live scene，不重放副作用。

---

# 1. 产品目标、非目标与用户结果

## 1.1 产品目标

探索连续性必须让用户做到：

- 从 Overview、Topic、Knowledge、Relation、Answer 或 Source 任一入口开始探索；
- 在不离开当前阅读的情况下先查看局部语境；
- 真正进入另一个对象时，准确知道来源、关系和目标所在范围；
- 随时返回刚才的现场，而不是只回到页面顶部；
- 在 Back 后走向另一条线索，并能找回刚才放下的分支；
- 从一次杂乱探索中挑出一条值得复用的理解路线；
- 关闭应用后从可信位置继续，但不把临时噪声固化成知识；
- 当知识、关系或位置变化时，理解保存路线哪些仍成立、哪些需要重评。

## 1.2 非目标

本产品不追求：

- 记录每次点击、hover、滚动和缩放的完整行为监控；
- 用访问次数自动判断知识重要性；
- 把所有探索轨迹永久保存并展示为时间线；
- 用无限推荐流替代用户的主动选择；
- 把 Saved Path 变成课程管理、任务计划或强制完成机制；
- 因保存一条路径而自动创建 Relation、Placement、Topic 或新 Knowledge；
- 用复杂的分支树和进度仪表盘制造维护压力。

## 1.3 核心用户结果

> **用户可以自由走，但不会失去位置；可以回来，但不会被历史拖累；可以保存理解，却不会把临时点击误当知识。**

---

# 2. 五种连续性状态

## 2.1 总览

| 状态 | 回答的问题 | 主要写入时机 | 生命周期 | 是否是长期知识资产 |
|---|---|---|---|---|
| `DepthTrail` | 我在结构的哪里 | 结构 / placement 解析 | 随当前 target 计算 | 否 |
| `ReturnStack` | 我刚才从哪个现场来 | Open / handoff | 当前窗口或标签页 | 否 |
| `ExplorationTrail` | 这一轮沿什么线索走过 | 有意义的 Open | 当前探索会话 | 否，除非显式选存 |
| `SavedPath` | 哪个理解顺序值得以后复用 | 用户保存与编辑 | 长期、可版本化 | 是，主要产品资源 |
| `PathProgress / ResumePoint` | 我下次从哪里继续 | 安全 checkpoint | 可清除的个人现场 | 否 |

这五项可以互相引用，但不能共享同一个记录或删除后果。

## 2.2 DepthTrail / 结构位置

DepthTrail 是系统根据当前 owner、scope 和 placement 计算出的可读路径：

```text
个人知识空间
  > AI Agent 产品设计
  > 记忆与上下文
  > 长期记忆架构
  > 适用条件
```

它可以包含：

- Space；
- Knowledge Group；
- Topic 与递归 Subtopic；
- Knowledge；
- Section / Anchor；
- Source / Fragment 的核验位置。

DepthTrail 不包含：

- 上一个访问对象；
- 图谱中刚展开过的邻居；
- Query Route 中检索过但未打开的对象；
- 同一 Knowledge 的其他 placements；
- “完成到第几步”。

一个 Knowledge 有多个 Placements 时，DepthTrail 必须使用当前 placement context；若 deep link 无法确定，先显示可理解的默认 context，并允许用户选择`按另一个位置查看`。

## 2.3 ReturnStack / 临时回返

ReturnStack 保存可恢复的 `ReturnEnvelope`，不是 URL 清单：

```text
ReturnEnvelope
  place
  surface_owner_ref
  primary_target_ref
  placement_context_ref?
  origin_kind
  root_or_lens
  reading_depth
  anchor_ref?
  relation_radius
  selected_identity_ref?
  inspect_target_ref?
  filters
  graph_viewport
  reading_scroll
  focus_return_ref
  working_state_ref?
  safe_at
```

写入条件：

- Open 新的 primary target；
- 从 Group Map 进入另一个 Group / Placement；
- 从 Answer 进入 Knowledge / Evidence；
- 从 scoped Lens 显式进入 global Place；
- 打开需要独立 owner 的 History、Decision 或 Source Workspace。

不写入条件：

- hover、focus、inspect；
- 同一对象内滚动；
- 图谱 pan / zoom / expand / filter；
- Companion follow 更新；
- 打开或关闭无 owner 变化的 tooltip；
- streaming Answer 的局部更新。

## 2.4 ExplorationSession / 当前探索活动

ExplorationSession 在用户明确开始关系探索，或连续发生两个有语义连接的 Open 时建立。它包含：

```text
ExplorationSession
  session_id
  origin_ref
  origin_context
  started_at
  active_cursor
  active_branch_id
  branch_summaries[]
  transient_scene_state?
  status = active | suspended | ended | discarded
```

会话结束条件：

- 用户显式结束探索；
- 用户切到与当前探索无关的任务并确认不保留；
- 应用安全关闭后只保留 ResumePoint，而不永久保存全部 Trail；
- 超过合理空闲期后归档为可清除的 suspended state。

## 2.5 ExplorationTrail / 有意义的访问轨迹

Trail step 只记录改变理解目标的动作：

```text
TrailStep
  step_id
  target_ref
  placement_context_ref?
  entered_via = structure | formal_relation | evidence | reference | query_route | manual
  connector_ref?
  origin_step_id?
  opened_at
  semantic_reason?
```

不会成为 Trail step 的行为：

- 只是看了一眼 Preview；
- 在图上展开更多邻居；
- 切换 relation family filter；
- 放大、缩小、拖动画布；
- 在同一正文折叠 Section；
- 仅移动键盘 focus；
- 从 Answer 高亮到一个未打开的 Claim。

## 2.6 SavedPath / 长期理解路线

SavedPath 是有目的、可命名、可版本化的长期资源：

```text
SavedPath
  path_id
  title
  purpose
  owner_space_ref
  start_scope_ref?
  visibility = private
  current_revision_ref
  lifecycle = active | archived | trashed
  created_by
  created_at

SavedPathRevision
  revision_id
  path_id
  ordered_steps[]
  revision_basis
  change_note?
  created_at

SavedPathStep
  step_id
  target_ref
  placement_context_ref?
  connector_kind = structural | formal_relation | evidence | reference | manual
  connector_ref?
  connector_revision_ref?
  saved_connector_statement?
  saved_endpoint_snapshots[]
  step_rationale?
  target_revision_ref?
  anchor_ref?
```

**SavedPath 不包含 `last_position`、completed steps、scroll、viewport 或当前 cursor。** 这些全部属于 PathProgress / ResumePoint。

## 2.7 PathProgress / 路线进度

```text
PathProgress
  progress_id
  path_ref
  path_revision_ref
  user_ref
  workspace_instance_ref?
  current_step_id
  completed_step_ids[]
  skipped_step_ids[]
  current_anchor_ref?
  last_safe_at
  status = not_started | active | paused | completed
```

产品默认只显示：`继续第 3 步：长期记忆架构`，而不是完整进度后台。清除 Progress 不删除 Path；修改 Path 不自动把 Progress 迁移为“已完成”，而是先计算兼容性。

## 2.8 ResumePoint / 安全继续位置

ResumePoint 是某个 Workspace 的单一安全 checkpoint：

```text
ResumePoint
  resume_id
  workspace_instance_ref
  owner_ref
  return_envelope
  related_path_progress_ref?
  reason = explicit_continue | ordinary_close | app_restart | safe_suspend
  safety_state = safe | needs_repair | unavailable
  updated_at
```

ResumePoint 不重放：

- 提交、删除、导入、AI 运行或外部请求；
- 未确认的高影响 Decision；
- 已失效的临时权限；
- 不安全的编辑器组合输入状态。

## 2.9 QueryRoute / 回答使用路线

QueryRoute 解释本次 Answer 为什么使用这些对象。它的步骤可以是结构跳转、正式 Relation、Evidence connection 或明确标注的 runtime retrieval jump。

它不会自动：

- 进入 ExplorationTrail；
- 成为 SavedPath；
- 建立 formal Relation；
- 改变 PathProgress；
- 改写 Overview 推荐入口。

只有用户选择`把这条回答路线整理成探索路线`，系统才打开一个可编辑 SavedPath draft，并让用户删除纯检索步骤、补目的与步骤理由。

## 2.10 RecommendedPathReference / 范围策展引用

```text
RecommendedPathReference
  scope_ref
  path_ref
  path_revision_policy = current | pinned
  editorial_reason
  semantic_order
  status
```

它回答“这个 Scope 为什么推荐这条路线”，不回答“用户走到第几步”。取消推荐只删除 reference，不删除 SavedPath 或任何人的 Progress。

---

# 3. 动词与副作用合同

## 3.1 核心动作矩阵

| 动作 | 改 primary target | 写 ReturnStack | 写 Trail | 写 Recent | 写 PathProgress | 改知识真相 |
|---|---:|---:|---:|---:|---:|---:|
| Hover | 否 | 否 | 否 | 否 | 否 | 否 |
| Focus | 否 | 否 | 否 | 否 | 否 | 否 |
| Inspect | 否 | 否 | 否 | 否 | 否 | 否 |
| Open | 是 | 是 | 条件成立时 | 是 | 若正沿 Path | 否 |
| Compare | 否 | 否 | 否 | 否 | 否 | 否 |
| Expand / filter / pan / zoom | 否 | 否 | 否 | 否 | 否 | 否 |
| Back / Forward | 恢复 | 移动 cursor | 移动 trail cursor | 否 | 否 | 否 |
| Up | 是 | 是 | 仅主动探索时 | 是 | 视 Path step | 否 |
| Save Path | 否 | 否 | 读取并筛选 | 否 | 新建可选 | 新建 Path 资源 |
| Continue Path | 是 | 是 | 是 | 是 | 是 | 否 |

## 3.2 Hover 与 Focus

- hover 只做即时高亮或 tooltip；移开即消失；
- focus 只表示键盘当前位置；
- 两者不能改变 Ask Scope、Reading Target、Companion pinned target、History 或 graph layout；
- tooltip 内需要操作时必须可进入 focus，并在关闭后返回触发点。

## 3.3 Inspect

Inspect 用于回答“这个是什么，为什么与当前对象有关”。它可以显示：

- Orientation；
- relation statement、direction、status 与依据；
- target 的 Group / Topic context；
- 一小段 Preview；
- `打开完整知识`、`在另一个位置打开`、`加入比较`。

Inspect 不改变 primary target；关闭后主阅读、Trail cursor 与 ReturnStack 完全不变。

## 3.4 Open

Open 表示用户决定让目标成为主要理解对象。它必须：

1. 捕获当前 safe ReturnEnvelope；
2. 解析目标 identity 与 placement context；
3. 更新 primary target；
4. 形成 Recent open event；
5. 若发生在 active ExplorationSession，写入一个 TrailStep；
6. 若正在沿 Saved Path，更新 PathProgress；
7. 保持来源关系可解释。

## 3.5 Compare

Compare 默认最多两个对象。添加第三个前明确提示替换或退出当前比较。Compare 退出后不保留为 SavedPath；用户可以显式`把比较对象保存为路线草稿`，但必须补顺序和目的。

## 3.6 Scene operations

图谱的 expand、dismiss、filter、group、undo / redo、fit selection、pan 与 zoom 只改变当前 scene state。它们可以被局部撤销和恢复，但：

- 不创建 Knowledge、Relation、Placement 或 PathStep；
- 不写 Recently Opened；
- 不改变 Saved Path revision；
- 不因两个节点同时出现在 scene 就产生“相关”真值。

---

# 4. Back、Forward、Up、Close 与 Resume

## 4.1 语义总表

| 动作 | 用户问题 | 目标来源 |
|---|---|---|
| Back | 我刚才从哪个现场来 | ReturnStack 上一 envelope |
| Forward | 我返回前还去过哪里 | ReturnStack 下一 envelope |
| Up | 当前对象的结构父级是什么 | DepthTrail parent |
| Close | 当前临时层关闭后回到哪里 | overlay / inspector trigger |
| Resume | 上次安全停在什么现场 | ResumePoint / PathProgress |

## 4.2 Back

Back 恢复的不只是 target，还包括足以维持方向感的：

- Active Place 与 owner；
- Root / lens；
- placement context；
- reading anchor 与 scroll；
- graph viewport、radius、filter 与 selected identity；
- focus return；
- 非破坏性的 working state reference。

若某个字段已失效，恢复最近安全状态并明确说明“原位置已变化”，不能悄悄回到 Library root 或页面顶部。

## 4.3 Forward 与新分支

用户 Back 后又 Open 新目标：

- ReturnStack 的 browser-like Forward 路线失效；
- active ExplorationSession 保留一个轻量 alternate branch；
- 默认界面只显示`刚才的另一条分支`，不展示复杂树；
- 用户可以恢复该分支，也可以把当前或另一分支选存为 Path。

## 4.4 Up

Up 沿 DepthTrail 返回最近结构父级：Anchor → Knowledge、Knowledge → Topic / Group root、Topic → parent Topic / Group、Group → Space。它不会返回 Search、Answer 或 Atlas；这些属于 Back。

## 4.5 Close

Close 只移除最上层 Overlay、Inspector、Preview、Answer quick view 或 Compare surface，并把 focus 还给触发点。若关闭的是 full owner Workspace，才使用 ReturnEnvelope 或系统窗口行为。

## 4.6 Resume

Resume 必须显示人话摘要，例如：

> 继续“AI Agent 产品设计”中的“长期记忆架构”，上次停在“适用条件”；正在沿“从认知限制到产品机制”第 3 步。

用户在进入前应理解：恢复哪个 Scope、哪个 Knowledge、是否属于 Saved Path、现场最后保存时间。需要 repair 时先预览替代位置。

---

# 5. 分支探索

## 5.1 为什么分支是一等责任

网络探索不是线性阅读。用户经常因为一条关系进入 A，返回后再沿另一条关系进入 B。若新选择直接覆盖旧路线，用户会害怕自由探索；若产品把全部路径展开成复杂树，又会让日常界面失控。

## 5.2 轻量分支模型

```text
TrailBranch
  branch_id
  parent_step_id
  ordered_step_ids[]
  last_target_ref
  last_active_at
  summary
```

产品默认只显示：

- 当前路线；
- 一个最近 alternate branch；
- 必要时`查看本次探索的其他分支`。

## 5.3 分支保存

保存时用户可以：

- 保存当前分支；
- 从本次探索中勾选步骤；
- 插入未实际访问但值得加入的知识；
- 删除弯路；
- 重排顺序；
- 为手工跳转补充理由；
- 把两条分支组合成一条新路线。

系统不得把原始轨迹直接永久化并假装它已经是策展结果。

---

# 6. Saved Path 的形成与编辑

## 6.1 合法起点

Saved Path 可以从以下起点形成：

- 当前 ExplorationTrail；
- 用户从多个 Knowledge / Topic / Relation 中手工建立；
- QueryRoute 转换后的 draft；
- Compare 结果；
- 既有 Path 的 duplicate / successor；
- Overview 编辑器中的`添加推荐路线`。

## 6.2 保存编辑器的最小责任

保存前必须让用户完成：

1. 写标题或接受可编辑建议；
2. 说明用途，例如“先理解限制，再看产品机制”；
3. 选择实际保留的步骤；
4. 检查每步之间的连接类型；
5. 对 manual step 补理由或接受明确的“手工顺序”；
6. 决定是否固定保存时版本；
7. 决定是否立即作为某个 Scope 的推荐路线。

## 6.3 不允许的隐式写入

保存 Path 不会：

- 把步骤相邻关系写成 Relation；
- 把对象加入同一个 Group；
- 改变 Topic semantic order；
- 采用 AI RelationCandidate，物化正式 Relation 与首个 RelationRevision；
- 将 Query retrieval jump 变成正式知识；
- 自动 Pin 每个对象；
- 自动开始或重置 Progress。

## 6.4 Path revision

以下行为创建新 Path revision：

- 增删或重排步骤；
- 改变 path purpose；
- 改变 connector kind / ref；
- 把某一步固定到不同历史 revision；
- 改变 manual rationale 的实质意义。

只更新阅读进度、scroll、当前步骤、最后打开时间不会创建 revision。

## 6.5 Path lifecycle

- `active`：可打开、推荐、继续；
- `archived`：保留历史和引用，默认不推荐新用户进入；
- `trashed`：等待永久删除；
- permanent delete 前显示受影响的 Recommended references、Progress 和 historical Answers。

---

# 7. 路线变化、历史与重评

## 7.1 Step impact states

| 状态 | 含义 | 默认动作 |
|---|---|---|
| current | 当前对象与保存时兼容 | 正常打开 |
| redirected | identity 仍连续，位置或 successor 已重定向 | 打开新位置并说明 |
| changed | 当前 Revision 与保存时有实质差异 | 默认当前，可比较历史 |
| historical-only | 原对象只存在历史 | 进入历史视图 |
| unavailable | 内容或权限不可用 | 保留占位与修复入口 |

## 7.2 上游变化矩阵

| 上游变化 | Path 后果 |
|---|---|
| Topic rename / move | 更新可读位置；identity 不变 |
| Topic merge / split | 通过 redirect / successor 修复 placement context |
| Knowledge revision | 标记 changed；不改 step identity |
| Knowledge merge / split | 提供 successor 选择；不静默替换多个步骤 |
| Relation ended | connector 标记 historical-only；保留有效时间与保存时 statement |
| Relation superseded | connector 标记 changed；保留保存时 statement，并提供 successor |
| Relation retracted | connector 标记 historical-only；说明当前不再采纳与撤回原因 |
| Relation archived | 原 connector 可重建；当前路线默认不沿用，显式历史模式可打开 |
| Relation transition_pending | 保留旧 endpoint snapshots，不静默指向 split / merge successor |
| Relation trash / deleted tombstone | step 仍可 manual historical continuation，或选择已确认 successor relation |
| Source unavailable | Evidence step 不可核验；其他步骤保留 |
| Group archived | 支持 historical mode；推荐引用进入 review |
| Boundary revision | 重新检查推荐语境，不移动 Path steps |

## 7.3 Re-evaluate Path

Re-evaluate 输出：

- 哪些步骤仍有效；
- 哪些步骤已变化；
- 建议替换、插入或移除什么；
- 建议的当前路线与原路线的 diff；
- 是否需要新的 purpose 或 scope。

用户接受后创建 successor Path revision 或新 Path；原版本仍可打开。

## 7.4 当前与历史打开策略

默认打开当前身份与最新可用正文，同时在受影响步骤显示`这一步自保存后已变化`。用户可以选择：

- 查看保存时版本；
- 按当前知识继续；
- 重新整理这条路线；
- 暂时跳过；
- 从路线中移除并创建 revision。

---

# 8. Continue 与 Library Resume

## 8.1 Continue 的优先级

显式 deep link > ReturnEnvelope > explicit Continue Path > ordinary Group open。普通打开 Group 仍进入 Overview，不因存在 Progress 就强行继续。

## 8.2 Library 的呈现预算

Groups catalog 保持页面主体，顶部最多突出一个 Resume card，内容包括：

- 正在继续的 Group / Knowledge；
- exact position；
- 若有关联，Path title 与当前 step；
- 最后安全保存时间；
- `继续`与`从概览进入`两个不同后果。

Saved Paths 列表、Recent、Pinned 与 Attention 不与 Resume 合并成一个“最近内容”流。

| 进入条件 | 默认落点 | Resume 后果 |
|---|---|---|
| ordinary launch + safe checkpoint | last stable Library catalog | 显式点击后恢复 exact target / Anchor / scroll / companion |
| no checkpoint | stable Groups catalog | 不显示，不以 Recent 填充 |
| first use / empty | Empty Library | 不显示；提供三条真实起点 |
| new window | independent Stable Library state | 可引用同一 safe Resume，不复制 live scene |
| needs_repair | Stable Library 或 nearest safe reading fallback | 解释原因，提供 draft / permission / redirect repair |
| target unavailable | nearest explainable owner / historical destination | 不猜测相似对象 |
| AI / Index offline | local Stable Library | 本地 Resume 可用，AI-dependent hints 隐藏 |

Resume 排名只考虑 safety、尚未结束的明确用户意图与 recency，不考虑 AI relevance、点击频率或内容权威性。多窗口分别拥有 ReturnStack 与 live scene；默认只突出全局最近一个 safe Resume，其他现场按需展开为`其他最近位置`。

## 8.3 进度兼容

Path revision 变化后：

- unchanged steps 保留完成状态；
- redirected step 迁移并说明；
- removed step 保留 historical completion，但不算当前完成；
- inserted step 默认未完成；
- ambiguous split 要求用户选择；
- Progress 永远不反向改写 Path revision。

## 8.4 完成不是强制目标

Saved Path 可以被读完、跳读、暂停或只用作参考。产品不显示 streak、逾期、完成率排名或红色欠账。`完成`只表示用户走完当前 Path revision，不表示相关知识已经学会或通过验证。

---

# 9. 跨 Place、跨镜头与跨设备连续性

## 9.1 层级树、阅读与图谱

- Tree focus 不写历史；Enter Open 才写；
- Reading 中打开 Local Graph 只改变 Companion / lens；
- Inspect graph node 不离开 Reading；
- Open graph node 写 ReturnEnvelope，并保留 relation connector；
- `在图谱中打开`是显式 Place handoff，Back 可回到原 Reading anchor。

## 9.2 Search 与 Ask

- Search open 写 ReturnEnvelope，Back 回到 query、scope、scroll 和 selected result；
- Answer citation open 回到 exact Node / Evidence，Back 回到原 Claim；
- QueryRoute 进入 Explore 时创建新的 ExplorationSession origin，不复制 Answer；
- 保存 QueryRoute 为 Path 时先进入筛选编辑器。

## 9.3 Sources

Evidence → Source exact locator → Back 必须恢复原 Knowledge / Claim anchor。沿 Source reference 打开另一个 Knowledge 时，connector kind 是 `reference` 或 `evidence`，不是 formal Relation。

## 9.4 多窗口

- 每个 window / tab 有独立 ReturnStack、scene state、Trail cursor 与 ResumePoint；
- 同一 Saved Path 可以在多个窗口打开；
- Progress 默认按用户 + Path revision 汇总，但保存每个窗口的 last-safe envelope；
- 并发更新 Progress 使用最新明确 step，不覆盖 Path revision；
- 一个窗口清除现场不影响其他窗口或 canonical Path。

## 9.5 离线与同步

离线时仍可：

- 使用 DepthTrail、Back / Forward、Saved Path 和本地 Progress；
- 保存当前 Trail 为 Path；
- 查看已有历史版本；
- 在来源不可用时保留不可核验 step。

同步冲突只针对 Path revision 或同一 Progress 的并发变更；不能因此回滚 Knowledge、Relation 或 Workspace。

---

# 10. 失败与恢复

## 10.1 Return target changed

若原 anchor、placement 或 scene element 已变化：

1. 先尝试 same identity + repaired anchor；
2. 再尝试 successor / redirect；
3. 再回到最近可解释父范围；
4. 显示`原位置已变化`与恢复依据；
5. 永不无提示地回到 Library root 或页面顶部。

## 10.2 Resume unsafe

编辑器处于未完成 IME、文件写入中、权限已撤回或高影响 Decision 未提交时，ResumePoint 标为 needs_repair。恢复先进入安全阅读态，并提供恢复草稿或重新授权入口。

## 10.3 Trail corruption

Trail 损坏只丢弃当前 session 的衍生轨迹；ReturnStack、Saved Paths、Knowledge truth 与 Progress 不被删除。若有未保存 Path draft，使用单独 recovery record。

## 10.4 Path target unavailable

保留 step title、保存时 context、revision ref 与前后理由。用户可以跳过、替换、查看历史或修复引用，不能让数组自动收缩导致顺序含义变化。

## 10.5 Index / AI unavailable

AI 或索引不可用不影响沿现有结构、Relations、Saved Paths 与 Progress 继续。只关闭推荐和 Re-evaluate；不能把路线显示成不可用。

---

# 11. 语言与渐进披露

## 11.1 P0 用户语言

默认使用：

- `回到上一处`
- `回到上一级`
- `继续刚才的位置`
- `保存这条探索路线`
- `刚才的另一条分支`
- `这条路线已经变化`
- `查看保存时的路线`
- `按当前知识重新整理`
- `打开完整知识`
- `从概览进入`

## 11.2 不默认暴露的内部词

`DepthTrail`、`ReturnStack`、`ReturnEnvelope`、`ExplorationSession`、`TrailStep`、`PathProgress`、`ResumePoint`、`connector_kind`、`revision_basis` 只用于产品和工程合同。

## 11.3 不使用的误导文案

- `自动记住一切`
- `AI 已为你整理好路径`
- `完成度 87%`（除非明确指路线步骤）
- `相关内容`（没有说明相关原因）
- `返回`（无法判断是 Back、Up 还是 Close）
- `保存历史`（未说明保存 Trail 还是 Path）

---

# 12. 响应式、键盘与列表等价

## 12.1 Desktop wide

Reading 与 Map 可以主从并列；Back / Up 保持稳定位置；Trail 只在用户需要时以轻量路径带显示，不能占满第三栏。

## 12.2 Compact / mobile

- Map 与 Reading 顺序切换，但共用 primary target；
- Inspect 使用 Sheet，关闭恢复触发点；
- `查看`与`打开`必须是两个明确动作；
- Trail / Path editor 使用可重排列表，不依赖空间图；
- Resume 保留 exact target 与 step，不简化成只开 Group 首页。

## 12.3 Keyboard

- `Alt/Command + Left/Right`：Back / Forward；
- 层级导航的 Up 使用明确命令，不劫持 Tree 方向键；
- Escape 关闭最上层 transient surface；
- Enter 激活 Open；Space 可 Inspect / select，具体组件遵循其 pattern；
- focus restoration 使用 trigger ref；
- 图谱必须有同义关系列表，可完成分支、打开和保存路线。

## 12.4 Screen reader

每个步骤读出：目标、所属范围、连接类型、当前 / 历史状态、是否为当前 Progress step。颜色、线型或空间位置不能是唯一信息。

---

# 13. 指标与反指标

## 13.1 核心结果指标

| 指标 | 定义 | 方向 |
|---|---|---|
| Return Fidelity | Back 后 target、anchor、scope、viewport 与 focus 恢复正确率 | 越高越好 |
| Wayfinding Comprehension | 用户能否区分“上一处”与“上一级” | 越高越好 |
| Trail Signal Ratio | Trail steps 中真正改变理解目标的比例 | 越高越好 |
| Branch Recoverability | Back 后新分支产生时找回另一分支的成功率 | 越高越好 |
| Saved Path Fidelity | 保存结果与用户想保留的理解顺序一致率 | 越高越好 |
| Resume Confidence | 用户在点击 Continue 前能否预测恢复现场 | 越高越好 |
| Progress Independence | Continue / reset progress 不产生 Path revision 的正确率 | 100% |
| Impact Explainability | 路线变化时用户能否判断当前与历史差异 | 越高越好 |

## 13.2 诊断指标

- Inspect 后立即 Back 的异常比例；
- Return 只恢复到页面顶部的比例；
- Trail 被 hover / filter 污染的步数；
- Save Path 后大量删除自动步骤的比例；
- 用户误认为 manual step 是 Relation 的比例；
- Path revision 仅由 progress 更新触发的次数；
- Resume 后立即退出或回到 Overview 的比例；
- unavailable step 无解释丢失的次数。

## 13.3 反指标

不能把以下指标当产品成功：

- 平均每次探索点击更多节点；
- 平均图谱停留更久；
- 自动保存路径数量；
- Path 平均步骤数；
- 推荐点击率；
- 每日连续使用天数；
- 关系连线数量。

---

# 14. 十八条 Given / When / Then 验收

## 14.1 Location 与 History 分开

**Given** 用户从 Search 打开深层 Knowledge Anchor  
**When** 分别执行 Up 与 Back  
**Then** Up 进入结构父级 Topic，Back 回到原 Search query、selection 与 scroll；两者不互换。

## 14.2 Inspect 不污染历史

**Given** 用户在 Local Graph 依次 inspect 三个节点  
**When** 关闭 Inspector 并执行 Back  
**Then** 主阅读仍未变化，Back 返回打开主阅读前的现场，而不是穿过三个 Preview。

## 14.3 Scene operation 不成为路线

**Given** 用户 expand 十次、filter 两次并 dismiss 三个节点  
**When** 保存当前探索路线  
**Then** 编辑器只列出实际 Open 的语义步骤；scene 操作可以撤销，但不进入 Path。

## 14.4 Open 写入可恢复现场

**Given** 用户从 Relation statement 打开跨群目标 Knowledge  
**When** 执行 Back  
**Then** 恢复原 Group、Relation Inspector、selected edge、viewport 与 focus；目标的 placement context 不丢失。

## 14.5 Back 后形成分支

**Given** Trail 为 A → B → C  
**When** Back 到 B 后打开 D  
**Then** 当前分支为 A → B → D；Forward 不再指向 C，但`刚才的另一条分支`可恢复 A → B → C。

## 14.6 保存路线是选择性策展

**Given** 用户探索中走过 12 个对象，其中 5 个是弯路  
**When** 保存 Path  
**Then** 用户可以只保留 7 步、重排、补理由；原始 click log 不被自动固化。

## 14.7 Manual step 不制造 Relation

**Given** Path 中 A 与 B 没有 formal Relation  
**When** 用户保留 A → B  
**Then** connector 标为 manual 并显示理由；Atlas、Group Map 与 Local Graph 不新增边。

## 14.8 Progress 与 Path identity 分开

**Given** 用户沿同一 Path 从第 2 步读到第 5 步  
**When** 关闭并继续  
**Then** 只更新 PathProgress / ResumePoint；Path revision id、ordered steps 与推荐引用不变。

## 14.9 Reset progress 不删除 Path

**Given** 一条已推荐 Path 有完成进度  
**When** 用户选择`重新开始这条路线`  
**Then** 清除或新建 Progress；Path、Revision、Overview reference 与历史不变。

## 14.10 QueryRoute 显式转换

**Given** Answer Route 包含两条 runtime retrieval jumps  
**When** 用户选择保存为探索路线  
**Then** 先打开 draft editor，runtime steps 明确标注并可删除；保存后不创建 Relations，也不把 Answer 变成 Knowledge。

## 14.11 Resume 可预测

**Given** 用户上次停在 Path 第 3 步的某个 Anchor  
**When** Library 显示 Continue  
**Then** 进入前说明 Group、Knowledge、Anchor、Path 与 step；进入后现场一致。

## 14.12 Ordinary open 不强制 Continue

**Given** Group 中存在 active Progress  
**When** 用户从 Library 普通打开 Group  
**Then** 进入 Group Overview；只有显式 Continue 才恢复 Path position。

## 14.13 Path target changed

**Given** 一步 Knowledge 已有新 Revision，Relation 已 superseded  
**When** 打开 Path  
**Then** 显示 changed、保存时 statement、当前 successor 与可比较入口；不静默替换原 Revision basis。

## 14.13.1 Relation ended / retracted / transition pending

**Given** 三个 Path connectors 分别指向 ended、retracted 和 endpoint transition_pending Relations  
**When** 用户继续或 Re-evaluate Path  
**Then** ended 保留历史有效时间，retracted 明示当前不再采纳，transition_pending 保留旧 endpoints 且不猜 successor；新建议路线进入 Path draft，原 SavedPathRevision 与 relation revisions 均不被覆盖。

## 14.14 Topic split repair

**Given** Path step 的 placement 所在 Topic 被 split  
**When** 继续 Path  
**Then** identity 仍可打开；若有多个 successor placement，先让用户选择语境；Progress 不因此改写 Path。

## 14.15 Source unavailable

**Given** 一步指向 Evidence Fragment，而 Source 暂不可用  
**When** 继续路线  
**Then** 保留步骤、上下文与不可核验说明；允许跳过或修复，不删除相邻步骤。

## 14.16 多窗口隔离

**Given** 两个窗口打开同一 Group 和同一 Path 的不同步骤  
**When** 一个窗口 Back、另一个窗口继续  
**Then** ReturnStack、Trail cursor 与 viewport 不串线；共享 Progress 的更新可解释，Path identity 不变。

## 14.17 图与列表等价

**Given** 用户不能或不愿使用空间图  
**When** 在 Relation List 中完成 inspect、open、back、branch 与 save  
**Then** connector、Trail、Path、Progress 与 impact states 与图谱完全一致。

## 14.18 不安全恢复

**Given** 上次关闭时 AI run 未完成且编辑器有未提交 IME  
**When** 重启  
**Then** 恢复最近安全阅读现场，分别提供 run status 与 draft recovery；不重放 AI、提交或丢弃知识。

---

# 15. 官方研究事实与产品推论

## 15.1 W3C Breadcrumb：位置不是历史

WAI-ARIA Breadcrumb Pattern 将 breadcrumb 定义为当前页面在层级中的位置路径；它不是访问历史。[Breadcrumb Pattern](https://www.w3.org/WAI/ARIA/apg/patterns/breadcrumb/)

产品推论：DepthTrail 只承担结构位置；Back / Forward 必须由独立 ReturnStack 负责。

## 15.2 W3C Tree View：Focus、Selection 与 Activation 分开

WAI-ARIA Tree View 与 Navigation Tree 示例区分 focus、selection、activation，并要求明确键盘行为与焦点恢复。[Tree View Pattern](https://www.w3.org/WAI/ARIA/apg/patterns/treeview/) · [Navigation Tree Example](https://www.w3.org/WAI/ARIA/apg/patterns/treeview/examples/treeview-navigation/) · [Keyboard Interface](https://www.w3.org/WAI/ARIA/apg/practices/keyboard-interface/)

产品推论：Focus / Inspect / Open 不得共享副作用；只有 Open 改变主要目标和返回历史。

## 15.3 Obsidian：Global Graph、Local Graph 与 Preview 分工

Obsidian 官方将 Graph 与 Local Graph 分开，后者围绕 active note 显示可调深度的连接；Page Preview 允许 hover 查看链接内容而不离开当前 note；Backlinks 又提供围绕当前对象的列表语境。[Graph View](https://obsidian.md/help/plugins/graph) · [Page Preview](https://obsidian.md/help/plugins/page-preview) · [Backlinks](https://obsidian.md/help/plugins/backlinks)

产品推论：Preview 不应制造 navigation step；全局、群级与局部探索范围需要分开；列表不是图谱的残缺降级。

## 15.4 Neo4j：场景操作不是知识真值

Neo4j Bloom / Explore 官方文档把 expand、dismiss、clear scene、undo / redo、fit selection、过滤、分组和关系方向选择定义为对当前 scene 的交互；Card list 又让 selection 与 scene 同步并检查邻居。[Bloom Search and Actions](https://neo4j.com/docs/bloom-user-guide/current/bloom-visual-tour/search-bar/) · [Bloom Card List](https://neo4j.com/docs/bloom-user-guide/current/bloom-visual-tour/card-list/) · [Explore Scene Interactions](https://neo4j.com/docs/aura/explore/explore-visual-tour/scene-interactions/)

产品推论：scene state 可以恢复和撤销，但不能变成 Relation、TrailStep 或 SavedPathStep。

## 15.5 TheBrain：以当前 Thought 为中心与访问序列

TheBrain 官方说明 active Thought 会成为当前中心，并以 Past Thought List 按顺序保留访问过的 Thoughts，支持沿“train of thought”返回。[TheBrain Navigation](https://help.thebrain.com/androidphone/navigating.html) · [Thought Relationships](https://help.thebrain.com/androidphone/thoughtrelationships.html)

产品推论：顺序访问轨迹对于方向感有价值；但原始 visited list 仍不能自动成为用户策展的 Saved Path。

## 15.6 研究没有证明什么

这些官方资料证明层级位置、局部预览、中心对象、访问序列、场景操作与焦点语义是不同的成熟责任。Apple、Notion 与 Tana 又共同表明状态恢复、默认落点、Pinned 与 Recent 可以是不同责任；但它们不证明本产品的五状态拆分、分支保留时长、单条 Library Resume、Path revision policy、progress 汇总或具体文案已经通过用户测试。这些仍是产品决定和待验证假设。[Apple — Launching](https://developer.apple.com/design/human-interface-guidelines/launching/) · [Notion — Home and My tasks](https://www.notion.com/help/home-and-my-tasks) · [Tana — Sidebar](https://outliner.tana.inc/learn/features/sidebar)

---

# 16. 对未来设计的证明要求

未来设计不是多画一张 Path 页面，而要用连续状态证明：

1. DepthTrail、Back、Up 与 Close 在同一深层任务中后果不同；
2. Graph hover、inspect、open 与 compare 有可识别状态；
3. expand / filter / dismiss / viewport 可恢复但不污染 Trail；
4. 跨群 Open 先解释 relation 与 placement，再改变 primary target；
5. Back 后新 Open 形成分支，另一分支可找回；
6. Save Path editor 能删弯路、重排、补目的和 manual reason；
7. Saved Path 与 PathProgress 在信息架构、动作和版本上分开；
8. Library Resume 能说明 exact position，ordinary Group open 仍进 Overview；
9. Path changed 能比较保存时与当前，不静默升级；
10. QueryRoute 转 Path 必须经过显式 draft；
11. 图与列表完成同一 Explore / Return / Save 任务；
12. mobile、200% zoom、keyboard、screen reader 与 multi-window 不丢失连续性责任；
13. AI / Index / Source unavailable 时仍可沿既有结构和 Path；
14. 当前七张 Ardot 概念画面不具备这些连续状态，因此不能作为已完成设计证据。

---

# 17. 结论

知识网络的价值不在于让用户看见更多线，而在于让用户敢于沿一条线离开、知道怎样回来，并把真正重要的理解顺序保存下来。

> **DepthTrail 告诉用户“我在哪里”；ReturnStack 告诉用户“我刚才从哪里来”；ExplorationTrail 保留“这一轮怎样走到这里”；SavedPath 只保存用户主动挑选的理解顺序；PathProgress 与 ResumePoint 再单独回答“下次从哪里继续”。**

这套分工把自由探索和长期知识所有权连接起来：临时操作可以轻，长期路线可以稳，知识变化可以被解释，而用户永远不必为了不迷路而放弃探索。
