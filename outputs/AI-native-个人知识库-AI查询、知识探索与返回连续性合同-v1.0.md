# AI-native 个人知识库

## AI 查询、知识探索与返回连续性合同 v1.0

> 文档日期：2026-08-10  
> 文档状态：**ACTIVE_APPENDIX**  
> 上位权威：`AI-native-个人知识库-终局产品设计文档-v6.0.md`  
> 适用范围：Search、Ask、Answer、Question、Relation Explore、Source Check、Query History 与 exact return  
> 相邻现行合同：`AI-native-个人知识库-关系、群级网络与探索连续性合同-v1.0.md`拥有 Relation truth、Group qualification、Pair、Graph / List 与 Relation Scene；`AI-native-个人知识库-Overview、连续阅读与知识正文合同-v1.0.md`拥有被查询正文、Anchor、editor flush、History 与 reading return state；`AI-native-个人知识库-Library入口、目录浏览与继续阅读合同-v1.0.md`拥有 Library Search 入口、All Knowledge inventory，以及 Query recovery 不冒充 Resume / Recent 的边界；本文拥有 Search / Ask / Answer / Query Route ↔ Explore 的转换责任  
> 表面责任边界：`AI-native-个人知识库-表面架构、场景家族与完整设计证明合同-v1.0.md`拥有 Overlay → Answer → Inspector / Explore 的 Surface roles、Return Envelope 与 DPB；本文拥有 Query / Answer truth 与动作后果  
> 用户语言边界：`AI-native-个人知识库-用户可见信息架构、产品语言与复杂度披露合同-v1.0.md`拥有搜索 / 提问、scope / basis / coverage、回答与错误的用户表达；本文只拥有 Query / Answer truth  
> 不承担：Prompt、RAG、模型选型、向量数据库、原型布局或研发排期  
> 冲突规则：任何冲突以 v6 为准；本文件只深化 v6 AC-15–24、AC-29–32  
> 当前阶段：继续定义产品；不修改 Ardot，不生成新视觉方向，不制作原型

---

# 0. 执行结论

AI 查询和网络探索不是两个挂在知识库旁边的功能。它们必须形成同一个可逆循环：

```text
当前知识现场
  → Search 定位 / Ask 综合
  → Answer Workspace
  → 检查 Claim / Knowledge / Evidence
  → 按需进入 Relation Explore
  → Follow-up 或形成知识
  → 精确回到原现场
```

本合同冻结二十四项产品决定：

1. **Ask 是知识库中的一次知识操作，不是独立聊天产品。**
2. **Search、Ask、Explore 是三个承诺不同、但可以显式转换的动作。**
3. **提问前的 Composer 是临时层；提交后 Answer 成为同一 Shell 中的主阅读对象。**
4. **Answer 使用连续 Paper，不使用聊天气泡作为默认阅读结构。**
5. **每次 Ask 都必须拥有 Requested、Effective 与 Used 三层 Context。**
6. **当前位置帮助理解问题，但不自动授权读取整个 Library。**
7. **Group 内结构性后代可以按明确范围检索；跨 Group 扩大必须由问题点名或用户接受。**
8. **Web 默认关闭，且只可按本次 Run 开启；不得变成后续问题的隐藏默认。**
9. **每个主要 Answer Claim 都可以检查自己的依据，而不是只看底部来源列表。**
10. **Coverage 说明查到多少和漏掉什么，不表达模型置信度。**
11. **没有真实 Relation path 时显示 Used Knowledge List，不绘制伪路线。**
12. **Query Route 是本次回答的解释，不是长期 Knowledge Network。**
13. **从 Answer 进入 Network 时以具体 Claim 或 Knowledge 为 anchor，不把整段答案铺成节点。**
14. **从 Network 发起 Ask 时显式使用当前 selection，不静默把整个 Network scene 当作上下文。**
15. **Follow-up 创建新 Run，并显示相对上一轮变化的条件、范围和依据。**
16. **最新 Answer 是主内容；旧轮次以可展开的调查历史存在，不堆成无限消息流。**
17. **Query Workspace 可以为恢复而本地自动保存，但不会进入 Library、Group、Network 或未来回答真相。**
18. **Saved Answer Snapshot、Question Knowledge、Current Knowledge 是三种不同的显式保存。**
19. **保存 Snapshot 不让 Answer 成为未来 Ask 的默认依据。**
20. **Answer 写回必须落到一个明确动作和一个明确目标，不存在 Accept all。**
21. **Search 输入完整问题时不自动切 Ask，只提供带范围预览的转换。**
22. **Explore 的访问、缩放、展开和共同出现不创建 Relation。**
23. **AI unavailable 时 Search、Reading、Relation List、历史 Snapshot 与本地写作仍然成立。**
24. **Graph、List、desktop、mobile、keyboard 和 screen reader 使用同一 scope、selection、claim support 与返回语义。**

---

# 1. 为什么现有定义仍不够完整

v6 已经分别定义了 Search、Ask、Answer 与 Explore，但如果缺少它们之间的转换合同，真实产品仍会碎裂成：

- 一个负责找东西的搜索框；
- 一个脱离当前阅读的聊天页；
- 一个漂亮但无法核验的图谱；
- 一个点击引用后就回不去的 Source Reader；
- 一组语义不清的`保存`按钮。

真正需要解决的不是“AI 回答页面放哪些模块”，而是下面五个用户问题：

1. 系统到底查询了什么；
2. 这句话具体依据什么；
3. 为什么这些知识会一起出现在回答里；
4. 我怎样从回答进入知识网络继续理解；
5. 我检查完以后怎样回到原问题和原阅读位置。

如果这五点不能连续完成，AI 只是在知识库上覆盖了一层问答工具，关系网络也只是一张旁观图。

---

# 2. 用户概念与内部责任

## 2.1 用户日常只需要理解六个概念

| 概念 | 用户理解 | 是否长期知识 |
|---|---|---|
| Search | 找到已经存在的内容或位置 | 否 |
| Ask | 基于明确范围回答一个问题 | 否 |
| Answer | 本次问题的可核验回答 | 否 |
| Explore | 沿真实结构或关系继续查看 | 否 |
| Question | 用户决定长期保留的未知 | 是，Knowledge role |
| Knowledge | 用户当前认可、可以再次进入的理解 | 是 |

用户不需要学习 Query Turn、Run、Context Snapshot、Claim Support、Return Envelope 等内部名字。

## 2.2 内部 Supporting Records

```text
InvestigationWorkspace
  origin_return_envelope
  active_turn_id
  branch_lineage
  recovery_state

QueryTurn
  user_question
  created_from
  requested_context

QueryRun
  predecessor_run_id?
  run_reason
  effective_context_snapshot
  used_context
  answer_claims
  coverage
  route_or_used_list
  run_state

SavedAnswerSnapshot
  question
  answer
  context_snapshot
  citations
  route_snapshot?
  saved_at
```

这些记录用于解释、历史与恢复，但不进入普通 Library Catalog，不成为 Group / Relation endpoint，也不被未来 Ask 默认当作 Current Knowledge。

## 2.3 五种保存不能混淆

| 用户动作 | 产生什么 | 未来 Ask 默认使用 |
|---|---|---|
| 离开但保留恢复现场 | Investigation recovery state | 否 |
| 保存回答快照 | Saved Answer Snapshot | 否 |
| 保存为问题 | Question Knowledge | 只使用 Question statement，不把旧 Answer 当真相 |
| 保存为知识 | 新 Current Knowledge | 是 |
| 更新现有知识 | 指定 Knowledge 的局部 Revision | 是 |

---

# 3. 一个连续的查询—探索循环

## 3.1 起点可以不同，主循环相同

Ask 可以从以下位置发起：

- Library；
- Group Overview；
- Topic；
- Knowledge / Anchor；
- Relation Inspector / Pair Comparison；
- Network selection；
- Source / Fragment；
- Search result set；
- Saved Path；
- Empty Library。

每个入口都必须携带：

- origin object / scene；
- origin Anchor、scroll、focus 与 disclosure；
- 当前 selection；
- 候选 requested scope；
- 返回动作。

## 3.2 查询前、查询后与检查时的主次

### 提交前

Composer 是轻量临时层。它保留用户当前阅读现场，只用一句自然语言表达候选范围：

> 在“个人学习策略设计”的“安排节奏与反馈”中提问；不使用外部资料。

### 提交后

Answer Workspace 成为 Primary Reading Target。原阅读对象不永久与 Answer 等宽并列，而是作为可返回的 origin 和 scope context 保留。

### 检查依据时

Knowledge、Relation 或 Source 可以成为临时 Primary / Companion。关闭检查后回到原 Answer Claim，而不是 Answer 顶部。

### 进入探索时

Relation Space 成为 Primary，Answer 退为 origin context。关闭 Explore 后恢复 Answer Claim、scroll、scope summary、expanded citations 和 follow-up draft。

## 3.3 最小成功循环

```text
Topic 内 Ask
→ 看到 Direct Answer 与决定性限制
→ 打开一条 Claim 的“依据”
→ 进入 Knowledge Anchor
→ 进入 Source Fragment
→ Back 回 Knowledge Anchor
→ Back 回 Answer Claim
→ 打开“在知识网络中查看”
→ 沿一条正式 Relation 打开相邻 Knowledge
→ Back 回 Network selection
→ Close 回 Answer Claim
→ Close Answer 回原 Topic 现场
```

这条循环不能靠浏览器历史碰巧成立，必须由产品自己的 Return Envelope 保证。

---

# 4. Search、Ask、Explore 的边界与转换

## 4.1 Search：我知道自己在找什么

Search 的默认结果是对象、文字位置和可解释状态：

- Group、Topic、Knowledge、Relation、Source、Saved Path；
- title / alias / body / Claim / property / Source fragment；
- current、historical、redirected、ambiguous、unavailable；
- exact Anchor deep open；
- result set 和 index coverage。

Search 不生成综合结论，不把相似结果自动连边，也不因为用户输入问号就静默变成 Ask。

## 4.2 Ask：我需要基于这些知识得到回答

Ask 的默认结果是一次可核验 Query Run：

- Direct Answer；
- decisive qualifiers；
- Claim-level support；
- Scope 与 Coverage；
- Unknown / Conflict；
- Route 或 Used Knowledge；
- 显式后续动作。

Ask 不自动创建 Knowledge、Relation、Question、Overview prose、Saved Path 或 Source。

## 4.3 Explore：我需要看见联系并主动选择下一步

Explore 的默认结果是一个可返回的结构 / 关系现场：

- 明确 scope 和 anchor；
- Current Relations 与 structural connections；
- selection；
- Graph / List equivalent；
- Open / Inspect / Compare；
- branch 和 return。

Explore 不总结问题、不替用户选择“最重要节点”、不把访问路线写成正式 Relation。

## 4.4 合法转换

| From | 触发 | To | Context 后果 |
|---|---|---|---|
| Search | `用当前结果回答` | Ask | 预览 result set、scope 与排除项 |
| Search | 打开 Knowledge / Relation | Reading / Explore | 保存 Search return |
| Ask | 点击 citation | Knowledge / Source Check | 聚焦对应 Claim support |
| Ask | `在知识网络中查看` | Explore | 只带 selected Claim / Knowledge 与真实 steps |
| Ask | `搜索原文` | Search | 保留原问题与 Claim text |
| Explore | `询问当前选择` | Ask | 显示 selected objects 与 current Group scope |
| Explore | 打开 Knowledge | Reading | 保存 scene selection / viewport |
| Source | 选中 Fragment 后提问 | Ask | selected Source Fragment 成为 requested context |
| Answer | `保存为探索路线` | Saved Path draft | 先删除 runtime retrieval jumps 或标为 manual steps |

转换永远由用户动作触发。系统可以建议，但不能因为输入形式、模型判断或设备宽度静默改变承诺。

---

# 5. Query Context 合同

## 5.1 三层 Context

### Requested Context

用户认为自己要求查询的范围。

### Effective Context

系统解析后实际允许检索的范围，包括 scope、state、time、source policy、relation expansion 和 exclusions。

### Used Context

真正支撑、限定或反驳 Answer Claims 的对象。检索到但未使用的候选不冒充依据。

## 5.2 默认范围规则

| 发起位置 | 默认 Requested Context | 自动包含 | 不自动包含 |
|---|---|---|---|
| Knowledge / Anchor | 当前 Knowledge | 当前 Revision、指定 Anchor、必要 Evidence | sibling Knowledge、全 Group、Web |
| Topic | 当前 Topic | descendant Topics、active Placements | sibling Topic、其他 Groups |
| Group | 当前 Group | active Topics / Knowledge、必要 Evidence | 其他 Groups |
| Pair Comparison | 两侧 Groups | Current Relations、shared observation、exits | 第三 Group、Candidates 作为真相 |
| selected objects | 选中对象 | 它们的 Current truth 与必要 Evidence | 未选对象 |
| Library | whole Library | eligible Current Groups / Independent Knowledge | Web、archived / historical |
| Source Fragment | selected Fragment | Source revision 与 locator | 用户 Current Knowledge，除非问题要求比较 |
| Empty Library | 空的 personal context | 当前问题与本次用户输入 | 模型常识伪装成个人知识 |

## 5.3 结构展开与关系展开

- 明确选择 Topic / Group 时，结构性后代属于该范围；
- 当前 Knowledge 的 underlying Evidence 可以按 Claim 需要读取；
- Scope 内 formal Relation endpoint 可以参与检索；
- 越过 Group Boundary 的 endpoint 不自动进入 Used Context；
- 问题明确点名另一 Group / Knowledge 时，可作为用户请求的跨群范围；
- 否则系统先说明“需要查看另一个知识群”，由用户按本次 Run 接受；
- 一次允许扩大不成为后续默认。

## 5.4 适用条件

当身份、地点、时间、目标或材料类型会改变答案时，Context 可以包含本次 Applicability：

```text
dimension
value
origin: user_explicit | current_selection | saved_preference | unresolved
```

推断值不能静默成为事实。缺少决定性条件时，系统应：

1. 只问一个会改变答案的最小问题；或
2. 明确分成条件分支回答；
3. 不用无条件结论掩盖缺口。

## 5.5 全 Library 范围

G100 / K10K 下的“查询整个 Library”不是让模型阅读全部内容。Coverage 必须按 Group 结算：

- eligible Groups；
- covered Groups；
- excluded Groups；
- unavailable / partial-index Groups；
- Independent Knowledge coverage；
- used Knowledge / Evidence。

系统不能用 20 条最相似结果代表“已检查全部知识库”。

---

# 6. Answer Workspace

## 6.1 它不是聊天首页

Answer Workspace 有明确 origin、scope 和 close 后果。用户不会因为 Ask 进入另一个以消息列表为中心的产品。

## 6.2 默认阅读顺序

### P0：先回答

1. 原问题；
2. Direct Answer；
3. 会改变结论的条件或限制；
4. 主要 Claim citations。

### P1：检查可信度

5. 一句话 Scope Summary；
6. Coverage / Unknown / Conflict；
7. Claim Focus 与 Evidence；
8. Used Knowledge 或 Knowledge Route。

### P2：形成与继续

9. 进入知识 / 网络；
10. Follow-up；
11. 保存 Snapshot、Question、Knowledge、Diff、Relation Proposal 或 Path draft。

P0 / P1 / P2 是信息优先级，不是三个页面、Tab 或用户模式。

## 6.3 何时使用 Route

| Answer basis | 默认表达 |
|---|---|
| 单一 Knowledge | Knowledge + Claim citation |
| 多个对象并列支撑，没有真实连接 | Used Knowledge List |
| 存在结构、Evidence 或 Current Relation chain | Knowledge Route + List |
| 外部来源为主 | Source List，外部资料不冒充个人 Network |
| 明确推论 | Inputs + reasoning boundary，不伪造 source statement |

## 6.4 Answer Claim

需要独立 support 的内容包括：

- 直接结论；
- 事实与规则；
- 条件、限制和例外；
- 多对象综合；
- 冲突与否的判断；
- 推荐的关键前提；
- “没有找到 / 不能判断”的 Coverage statement。

过渡语句和界面导航不需要伪造 Claim 对象。

## 6.5 Answer 的状态

| 状态 | 仍然为真 | 用户可以做什么 |
|---|---|---|
| Preparing | 原问题和 Requested Context 已保存 | 修改问题、取消 |
| Clarification needed | 缺少决定性条件 | 回答最小问题、选择条件分支 |
| Retrieving | Context 已解析，Answer 未完成 | 停止、查看范围 |
| Streaming | 已形成部分文字，不保证完整 Coverage | 停止；已生成内容标 incomplete |
| Complete | 本 Run 已结算 | 检查、追问、保存、关闭 |
| Partial | 内部或外部某部分失败 | 使用已完成部分、重试 successor Run |
| Failed | 没有形成可用 Answer | Search、调整范围、重试 |
| Stale | 历史 Snapshot 的 Context / Sources 已变化 | 查看 Original、Re-evaluate |

---

# 7. Claim Focus、Citation 与 Evidence

## 7.1 Claim Focus 是检查单位

选中一条 Answer Claim 后，所有支撑面只回答这条 Claim：

- Knowledge support；
- Source / Fragment；
- formal Relation steps；
- qualifiers / contradicts；
- Coverage state；
- `用于知识`动作。

不能选中一段话却展示整篇 Answer 的混合来源墙。

## 7.2 Basis roles

| Basis | 用户语言 | 不得暗示 |
|---|---|---|
| Current Knowledge | 来自你的知识 | 有外部证据 |
| Source Statement | 来源原文写道 | 用户已经采纳 |
| Current User Input | 根据你这次提供的信息 | 已写入 Library |
| External Source | 外部资料 | 已保存为 Source |
| Reasoned Derivation | 基于这些内容可以推断 | 某来源直接陈述结论 |
| Unknown | 现有范围不足以确定 | 系统已查遍所有可能资料 |

## 7.3 Citation 进入和返回

Citation 必须：

1. 打开实际使用的 Revision；
2. 落到 exact Anchor / Fragment；
3. 提供足够上下文；
4. 区分 quote、translation、OCR、transcript 与 paraphrase；
5. 内容变化后仍可打开 historical target；
6. 无法重定位时保留原引用文字并显示 orphaned / ambiguous；
7. Close / Back 回到原 Answer Claim 和 focus。

## 7.4 Knowledge 与 Source 不一致

Answer 必须分开表达：

```text
来源当前写道：X
你的 Current Knowledge：仍采用 Y
这意味着：Y 可能需要检查，但没有被自动替换
```

新 Source 不自动胜出，Current Knowledge 也不能掩盖来源变化。

---

# 8. Answer 与知识网络怎样真正汇合

## 8.1 Query Route 的五种 step

```text
structural_connection
formal_relation
evidence_connection
retrieval_jump
external_source_connection
```

只有 formal relation 是长期 Relation truth。其他 step 解释本次如何到达依据。

## 8.2 禁止的伪路线

以下情况不得画成普通 Relation edge：

- 两条 Knowledge 同时被向量检索命中；
- 两个对象包含相似词；
- 两个来源共同支持一个 Answer；
- AI 在回答中先写 A 后写 B；
- 两个 Groups 共享一个 tag、View 或 Source；
- 模型认为“它们应该有关”。

## 8.3 从 Answer 进入 Explore

用户必须先有一个明确 anchor：

- 当前 Claim；
- 当前 used Knowledge；
- 当前 Relation step；
- 当前 Group pair。

Explore 打开后：

- Current Relations 使用正常语义；
- structural / Evidence steps 使用不同连接角色；
- runtime retrieval jump 只属于 Query overlay；
- 没有路径时保持并列 Used Knowledge，不补中间边；
- Graph 和 List 同步 selection、filter 与 open；
- 关闭后返回原 Claim。

## 8.4 从 Explore 发起 Ask

用户选择一个或多个对象后执行`询问当前选择`：

```text
你将询问：
- G-MEM / 记忆与学习科学
- K-M2 / 提取练习
- K-M5 / 间隔学习
范围不包含：其他知识群、历史版本、外部资料
```

当前 viewport、隐藏节点、hover 邻居和未选择对象不成为 Context。

## 8.5 Query Route 转 Saved Path

用户显式选择`整理成探索路线`后进入 draft：

- formal Relation 保留其 identity；
- structural step 保留真实 Topic / Placement；
- Evidence step 保留 Source locator；
- retrieval jump 必须删除或改成用户确认的 manual connector；
- 用户补充目的、顺序和说明；
- 保存 Path 不复制 Knowledge，也不创建 Relation。

---

# 9. Follow-up、Branch、Re-evaluate 与历史

## 9.1 四个动作

| 动作 | 新 Run | Context 规则 | 历史规则 |
|---|---:|---|---|
| Follow-up | 是 | 继承未改变的显式 Context，记录 delta | 原 Run 保留 |
| Retry | 是 | Requested Context 相同，执行可以变化 | 不覆盖失败 / 旧 Run |
| Branch | 是 | 从指定旧 Turn 建立新 lineage | 主分支不改变 |
| Re-evaluate | 是 | 用当前 Sources / Context 再运行 | 与 Original 显示 Answer Diff |

## 9.2 Follow-up Delta

每轮追问至少能回答：

- 问题怎样变了；
- Scope 是否扩大或缩小；
- Applicability 怎样变了；
- Web / Source policy 是否改变；
- 新用了哪些 Knowledge / Sources；
- 哪些旧结论改变或保持。

默认用一句自然语言表示，例如：

> 这次加入“两个月后保持”条件，并允许查看“记忆与学习科学”知识群；其余范围不变。

## 9.3 不使用气泡历史作为主阅读结构

- 最新 Answer 始终是主 Paper；
- 上一轮问题和结论以紧凑 lineage 可展开；
- 用户可以从旧轮次 Branch；
- 打开旧轮次时明确显示 Original Context；
- 不把一整条聊天 transcript 当作新的 Source 或 Knowledge。

## 9.4 自动恢复与显式保存

### 自动恢复

为防崩溃和误关，当前 Investigation Workspace 在本机保存：

- unfinished prompt；
- current Run state；
- Answer scroll / Claim focus；
- expanded citation；
- Explore return state。

它不进入 Library、Search 默认结果、backlinks 或 export truth。

### Saved Answer Snapshot

用户显式保存后，Snapshot：

- 可以在 origin Knowledge / Question 的 History 中找到；
- 可以通过带`回答快照`过滤的 Search 找到；
- 可以进入 Knowledge Package；
- 仍不成为未来 Ask 的默认依据；
- Source 变化后保留 Original，并可 Re-evaluate。

---

# 10. Answer 后的原子动作

| 动作 | Preview 必须显示 | Commit 后 |
|---|---|---|
| 保存回答快照 | Question、Context、citations、时间 | 新 Saved Answer Snapshot |
| 保存为 Knowledge | title、body、basis、Placement、去重 | 新 Current Knowledge |
| 更新现有 Knowledge | target Knowledge / Anchor、before / after、basis | 新 Knowledge Revision |
| 保存为 Question | statement、scope、criteria、Placement、origin | 新 Question Knowledge |
| 提出 Relation | endpoints、direction、完整 statement、basis | Relation Proposal，不直接 Current |
| 保存 Source | Source identity、snapshot、locator | 新 Source；不自动形成 Knowledge |
| 保存为 Path | purpose、steps、manual connectors | 新 Saved Path |
| 标记局部缺口 | target Anchor、missing condition / evidence | Persistent Gap Marker |

## 10.1 动作选择原则

- 只显示与当前 Answer / Claim 真实匹配的动作；
- 用户可以只阅读并关闭；
- 一个动作失败不提交其他动作；
- Cancel 零副作用；
- 成功后提供 Undo 或明确 forward restore；
- 返回 Answer Snapshot 的原 Claim；
- 不存在`保存全部`、`接受 AI 整理`或隐式批量写回。

## 10.2 去重不是替用户决定

保存为 Knowledge 时如果发现相似 Current Knowledge，系统提供：

- 建立新 Knowledge；
- 更新明确 Anchor；
- 增加 Placement；
- 取消。

相似度不能自动 Merge，Answer 也不能因为引用了旧 Knowledge 就覆盖它。

---

# 11. 负面回答、Partial 与失败

## 11.1 Unknown taxonomy

```text
no_relevant_knowledge
relevant_but_evidence_limited
scope_too_narrow
decisive_applicability_missing
source_unavailable
index_partial
historical_gap
external_knowledge_disabled
unresolved_conflict
answer_requires_user_judgment
```

它们属于当前 Run，不自动成为长期 Question 或 Review item。

## 11.2 Coverage 不是 confidence

| 状态 | 含义 | 默认语言 |
|---|---|---|
| sufficient | 当前范围足以回答 | 默认不额外强调 |
| partial | 可以回答一部分 | 以下结论只覆盖…… |
| insufficient | 缺少决定性内容 | 现有知识还不足以回答…… |
| indeterminate | 因索引、权限或历史缺口无法判断 | 当前无法确认知识库是否包含完整答案…… |

禁止显示`92% 可信`、`3 条引用所以充分`或`Top 20 已覆盖全部`。

## 11.3 诚实的“没有找到”

只有全 Scope、索引完整、状态范围清楚、排除项为空且来源可用时，系统才可以说“在这个范围中没有”。通常应写：

> 在当前选择的两个知识群和已完成索引的内容中，没有找到直接回答；另有一个来源尚未解析，且本次没有使用外部资料。

## 11.4 对应动作

| 原因 | 最自然动作 |
|---|---|
| Scope too narrow | 预览并扩大本次范围 |
| Missing applicability | 回答一个决定性条件 |
| Evidence limited | 查看或添加 Source |
| Index partial | 使用已索引部分 / 等待重建 |
| External disabled | 仅本次允许外部资料 |
| Conflict | 打开条件对照 |
| AI unavailable | Search / Reading / Relation List |
| Long-term unknown | 显式保存为 Question |

---

# 12. 规模、本地性与责任等价

## 12.1 大规模

- Library-wide Ask 按 Groups 说明 coverage；
- Used Context 只列真正使用的 Knowledge / Evidence；
- 超预算 Route 先给 scope summary 和 List，不画任意 Top N；
- relation expansion 有明确 radius 和 anchor；
- pagination、index 和 virtualization 不改变身份与引用；
- G1 / G100、K1 / K10K 使用同一查询心智模型。

## 12.2 本地优先

- Current Knowledge、Source snapshot、Relation、Saved Answer 与 return state 可以本地读取；
- AI / model unavailable 不阻止 Search、Reading、编辑或 Network List；
- Query recovery record 与 Saved Snapshot 使用不同 retention；
- Query history 可以单独清除，不删除 Knowledge 或 Source；
- clean restore 后 Saved Snapshot 引用仍能解析 current / historical targets。

## 12.3 Responsive

### Desktop wide

Answer 为 Primary；Claim Evidence 或 Relation Companion 可以按意图出现，但不形成永久三栏控制台。

### Compact / tablet

Answer、Source Check、Relation List 分时成为 Primary，通过 Return Envelope 保持现场。

### Mobile

Answer 是单列 Paper；Scope Summary、Coverage、Claim citations、Used Knowledge 与原子动作保持；Graph 可以缺席，但 Relation List 与 exact return 必须成立。

## 12.4 Keyboard / screen reader

- Composer、Submit、Stop、Claim navigation、Open citation、Back、Explore、Graph / List switch、Follow-up 和 atomic action 可用键盘完成；
- Claim 与 citation 有程序化关联；
- Coverage 和 standing 不只依赖颜色；
- `Expand`、`Inspect`、`Open`、`Back`、`Close Answer`拥有不同可读名称；
- focus 返回触发动作；
- reduced motion 不丢失 selection 或 direction。

---

# 13. 真实内容压力场景

## QX-01 · Search 不是 Ask

Fixture C 搜索`材料只在承担论证责任时保留`，直接打开 K-W1 Anchor a1。输入完整问题时只提供`基于当前结果提问`，不自动生成 Answer。

## QX-02 · Topic Ask 需要跨 Group 扩大

Fixture B 在 G-STUDY / 安排节奏与反馈中询问“两个月后的复习间隔怎样安排”。当前 Group 内有策略 Knowledge，但决定性研究依据位于 G-MEM。系统说明需要按本次问题查看 G-MEM；用户接受后新 Run 记录 scope delta，不把全 Library 加入。

## QX-03 · Claim → Knowledge → Evidence → Answer

Fixture B 的 Answer Claim“合适间隔依赖目标保持间隔”打开 K-M6 Anchor，再打开 S-M3 Fragment；两次 Back 分别返回 Knowledge Anchor 和原 Answer Claim。

## QX-04 · 有真实 Route

Fixture B 的策略 Answer 使用 Current Group Relation、K-M5、K-M6 与其 Evidence。Route 可以显示 formal Relation 和 Evidence steps；用户进入 Explore 后沿 K-M5 打开 G-MEM，再精确回到 Answer Claim。

## QX-05 · 没有真实 Route

Ask 同时使用两条没有 Relation 的 Knowledge。Answer 显示 Used Knowledge List；`在网络中查看`只显示二者分别支撑 Claim，不补一条`related_to`。

## QX-06 · Follow-up Applicability Delta

Fixture A 的资格问题在追问中加入新身份或日期。系统建立 successor Run，说明条件变化、受影响 criterion 与仍不变的范围；旧 Answer 保留 Original。

## QX-07 · Runtime Unknown 不制造 Inbox

Answer 发现缺少一个决定性机构结果，只在 Run 内显示 Unknown。只有用户选择`保存为问题`才建立 Question Knowledge。

## QX-08 · Answer 形成知识

Fixture B 用户选择一个 bounded synthesis 保存为 Knowledge。Preview 显示 title、qualifiers、basis、Placement 与相似 Knowledge；提交只建立一个 Knowledge，不保存整条聊天。

## QX-09 · Source 与 Current 不一致

Fixture A 的官方 Source revision 改变。Re-evaluate 分别显示新 Source、旧 Current Knowledge、criterion impact 和 Answer Diff；不自动覆盖旧 Knowledge。

## QX-10 · Empty Library Ask

Fixture C 的 Library 为空。Ask 明确显示 personal context empty；可以让用户直接写下已有理解、添加资料、保存 Question 或按本次允许 Web，但不能用模型常识声称“根据你的知识库”。

## QX-11 · G100 / K10K broad Ask

Synthetic fixture 有 100 Groups、10,000 Knowledge、archived Groups、partial index 与 Independent Knowledge。Answer 显示 eligible / covered / unavailable Groups；Used Context 仍只列实际支撑对象。

## QX-12 · AI unavailable

用户打开历史 Saved Answer，引用仍可进入本地 Knowledge / Source；Re-evaluate 不可用，但 Search、Relation List、Reading 与编辑可用。

---

# 14. 专项验收合同

| QEC | 对应 v6 AC | 验收 |
|---|---|---|
| QEC-01 | AC-17 / 19 | 从任意 Scope Ask 后 Close 精确恢复 origin Anchor、scroll、focus 与 disclosure |
| QEC-02 | AC-18 | Search 打开 exact Anchor；问句输入不静默切 Ask |
| QEC-03 | AC-19 | Composer 用人话显示 Requested Context，Answer 可检查 Effective / Used Context |
| QEC-04 | AC-19 | 跨 Group 扩大由问题点名或本次接受；不继承为后续默认 |
| QEC-05 | AC-19 / 21 | whole Library Ask 按 eligible / covered / excluded / unavailable Groups 结算 |
| QEC-06 | AC-20 | 每个 major Claim 有独立 basis 与 citation role |
| QEC-07 | AC-20 | Citation 打开实际 Revision + Anchor / Fragment，并返回原 Claim |
| QEC-08 | AC-12 / 20 | Source statement、Current Knowledge、inference 和 external source 不混淆 |
| QEC-09 | AC-12 / 16 | 没有 formal path 时显示 Used Knowledge List，不补边；Graph / List 同义 |
| QEC-10 | AC-15 / 17 | Answer → Explore 使用显式 Claim anchor；Close 恢复 Answer Claim |
| QEC-11 | AC-15 / 19 | Explore → Ask 只使用显式 selection，viewport / hover 不进入 Context |
| QEC-12 | AC-12 / 15 | Query overlay、retrieval jump 和 scene 操作不进入 canonical Relation truth |
| QEC-13 | AC-21 | Coverage 与 confidence、citation count 分离 |
| QEC-14 | AC-21 | 负面回答说明 scope、index、excluded、unavailable 和 Web policy |
| QEC-15 | AC-22 | Generate、Follow-up、Retry、Branch、Re-evaluate、Close 都不改变 Current Knowledge |
| QEC-16 | AC-22 | recovery workspace 不进入 Library、Network、backlinks 或 future truth |
| QEC-17 | AC-22 / 23 | Saved Snapshot、Question、new Knowledge、patch、Relation Proposal 与 Path 分权 |
| QEC-18 | AC-23 | 每次写回只有一个 target / action；Cancel 和 partial failure 零副作用 |
| QEC-19 | AC-24 | Runtime Unknown 不自动成为 Question / Gap Marker / Review item |
| QEC-20 | AC-27 / 28 | Re-evaluate 保留 Original Context、旧 Answer 与 Answer Diff |
| QEC-21 | AC-29 | AI unavailable 时 Search、Reading、List、saved citation 和 local edit 可用 |
| QEC-22 | AC-30 | clean restore 后 Saved Snapshot 的 Knowledge / Source targets 可解析 |
| QEC-23 | AC-31 | desktop / compact / mobile 保留 Scope、Claim support、Coverage、action 与 return |
| QEC-24 | AC-32 | keyboard / screen reader 可完成 Ask → Claim → Citation → Explore → Back |

---

# 15. 外部研究与产品推论

## 15.1 NotebookLM：范围选择、行内引用与图上发问可以连续

NotebookLM 官方说明允许用户选择参与回答的 Sources；点击 citation 会进入对应引用位置；Mind Map node 又可以直接成为 Chat 的问题焦点。[Use chat in NotebookLM](https://support.google.com/notebooklm/answer/16179559?hl=en) · [Use Mind Maps in NotebookLM](https://support.google.com/notebooklm/answer/16212283?hl=en)

产品推论：scope selection、citation deep open 和 map → Ask 的连续性有价值。但 NotebookLM 的生成 Mind Map 和保存 chat response 不直接证明长期 Knowledge Relation 或 Current Knowledge 写回语义。

## 15.2 Notion：查询范围必须可以显式缩小

Notion Enterprise Search 官方文档允许通过指定 page / teamspace、workspace、connected app 与 Web 调整查询范围，并在回答中引用来源。[Enterprise Search](https://www.notion.com/en-gb/help/enterprise-search)

产品推论：范围不是内部检索细节，用户需要知道自己问的是哪里。但本产品不复制“默认所有来源 + Web”的策略；个人知识库默认外部资料关闭。

## 15.3 Heptabase：可以搜索全部，不等于模型实际读了全部

Heptabase 官方文档明确区分 search across a Space 与实际发送给模型的 top-N items，并公开 searched / viewed 行为。[Space search in AI](https://support.heptabase.com/en/articles/13009956-what-data-can-ai-access-when-i-turn-on-the-space-search-option-in-an-ai-conversation)

产品推论：Coverage 必须把“可搜索范围”“检索候选”和“真正用于回答”分开。系统不能因为全库索引参与召回，就宣称模型读过全部知识。

## 15.4 Capacities：per-message context 与局部 Graph 说明锚定的价值

Capacities 官方文档允许每条消息通过`@`选择 context，并把 Graph 定义为单一对象周围的 local graph，而不是全空间图。[AI Assistant](https://docs.capacities.io/reference/ai-assistant) · [Graph View](https://docs.capacities.io/reference/graph-view)

产品推论：每轮 Context Delta 和 anchor-first relation exploration 是合理方向。但其 AI chats 自动成为 objects 的做法不适合本产品：普通 Query history 不应自动进入长期 Library。

## 15.5 研究没有证明什么

这些资料没有证明：

- 用户一定理解 Requested / Effective / Used 三层术语；
- 任何固定模块顺序都是最佳 Answer UI；
- 自动保存全部聊天有长期价值；
- Mind Map、retrieval route 或 local graph 可以直接成为 canonical Relation；
- 本产品应复制任一竞品的信息架构。

因此三层 Context、Answer Paper、Query history 分权、Route fidelity 与 exact return 都仍是需要真实任务验证的产品决定。

---

# 16. 对 Ardot 下一轮设计的证明要求

当前 Screen 5 只能保留“长答案适合连续阅读”的气质，不能在原图上补几个 Scope chips 和保存按钮后继续使用。下一轮必须从一条真实 Query Journey 重新设计。

## 16.1 最少证据包

1. **Contextual Composer**：从真实 Topic / Knowledge 发起，显示一句范围和 Web policy；
2. **Answer Primary**：Direct Answer、决定性限制、claim-level citations；
3. **Claim Focus**：一条 Claim 对应 Knowledge / Source / inference roles；
4. **Citation Check**：Knowledge Anchor 或 Source Fragment，并证明 exact return；
5. **Route 正例**：有 formal Relation / Evidence path；
6. **Route 负例**：没有 path，只显示 Used Knowledge List；
7. **Answer → Explore → Back**：同一 Claim、selection 和 return chain；
8. **Follow-up Delta**：条件或 Scope 改变，旧 Run 不被覆盖；
9. **Atomic Write-back**：形成一个 Knowledge 或 patch 一个 Anchor，Cancel 零副作用；
10. **Partial / No Answer**：index partial、scope narrow 或 external disabled；
11. **Saved Snapshot / Re-evaluate**：Original、Current context 与 Diff；
12. **Mobile / List / Keyboard**：不用空间图也能完成同一任务。

这些可以由 Full Frame、Overlay、Inspector、State Matrix 和 flow annotation 组合证明，不要求十二张互相独立的全屏稿。

## 16.2 视觉必须避免

- 聊天气泡成为主阅读结构；
- 一排持续增长的 scope chips；
- Citation 只集中在底部；
- `已引用 3 条`冒充 Coverage；
- 路线图把 retrieval jump 画成正式边；
- 相关问题推荐墙；
- Answer、Source、Network 永久三栏；
- 一个笼统`保存`或`接受全部`；
- 用置信度百分比替代条件、依据和未知；
- 点击引用后丢失 Answer claim 位置。

## 16.3 方向 3 + 2 在 Query 中的准确比例

- 方向 3：Answer 仍然是可阅读、可核验、逐层深入的 Warm Paper；
- 方向 2：Route、Relation Companion 与 Explore 只在用户检查“为什么这些知识相连”时出现；
- 二者不永久等宽；
- Relation Night 不进入普通 Answer 背景装饰；
- 从暖色 Answer 进入深色 Explore 时，Claim anchor 与返回位置必须比视觉转场更重要。

---

# 17. 最终产品判断

一个好的 AI-native 个人知识库，不是“可以对笔记聊天”，也不是“回答旁边有一张知识图”。它应当让用户完成这样一件事：

> 在一个明确知识范围内提出问题，先得到直接但有边界的回答；能够逐句检查它使用了哪些 Current Knowledge、Source 和推论；需要时沿真实关系进入知识网络继续探索；最后回到原问题、原 Claim 或原阅读现场，并决定什么值得进入长期知识。

只要查询不能回到知识、图谱不能解释回答、回答不能核验依据，这三个表面就仍是三个产品。只有 identity、scope、truth、selection 和 return 全部连续，它们才是同一个知识库。
