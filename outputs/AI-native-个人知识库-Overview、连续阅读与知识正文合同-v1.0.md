# AI-native 个人知识库

## Overview、连续阅读与知识正文合同 v1.0

> 文档日期：2026-08-10  
> 文档状态：**ACTIVE_APPENDIX；已完成注册、Canonical 同步与相邻责任划分**  
> Canonical：`AI-native-个人知识库-终局产品设计文档-v6.0.md`  
> 本合同只深化：Overview、Topic Opening、Knowledge Paper、正文深度、Anchor、直接编辑、版本历史与阅读返回  
> 本合同不重新定义：Group / Topic 的结构治理、Source formation、AI Answer、Relation truth 或 Library navigation；`AI-native-个人知识库-Library入口、目录浏览与继续阅读合同-v1.0.md`拥有 cold start、普通 Open / Continue、Resume eligibility 与 Library return，本合同拥有进入后 Overview / Knowledge 的 scene 内容、Anchor 与 History  
> 表面责任边界：`AI-native-个人知识库-表面架构、场景家族与完整设计证明合同-v1.0.md`拥有 Reading scene 的 Primary / Companion / Inspector、跨 Scene transition / return 与 DPB；本文拥有正文、Anchor、edit 与 History truth  
> 用户语言边界：`AI-native-个人知识库-用户可见信息架构、产品语言与复杂度披露合同-v1.0.md`拥有概览、主题、知识、依据、编辑 / 保存 / 历史 / 返回的用户表达；本文只拥有正文、Anchor、edit 与 History truth  
> 产品阶段：定义产品，不授权制作原型或修改 Ardot 画布  

---

# 0. 执行结论

方向 3 不是一种“暖色长文视觉”，而是产品的默认知识道路：

> **用户进入一个知识范围，先得到恰当的方向感，再在同一个连续阅读现场中逐步进入结构、正文、局部主张与证据；写作、核验、历史和跨空间探索都能精确回到原处。**

方向 2 是这条道路按需打开的第二维度。它不能拥有另一份知识正文，也不能让用户在关闭关系空间后丢失阅读现场。

本合同冻结 36 项产品决定：

1. Group Overview、Topic Opening 与 Knowledge Paper 属于同一个连续阅读系统，不是三类互不相干的页面模板。
2. Overview 是 scope-owned guide，不是 Knowledge、AI summary、Dashboard 或新的 canonical truth family。
3. 每个 Group / Topic scope 至多有一个 Current Overview identity；它随 scope 存续，不因正文密度变化而复制。
4. Overview 中的 Editorial prose、Structure projection 与 Reference 必须分权。
5. Structure projection 可以自动刷新，但不得改写 Editorial prose。
6. Bare Overview 是完整合法状态；系统不得用 AI 成熟文案掩盖真实空缺。
7. 用户直接编辑 Overview，经安全保存后更新 Current，不经过“采用 AI 建议”。
8. Overview 中需要独立证据、关系、复用或修订节奏的判断应提升为 Knowledge；Overview 不形成影子知识层。
9. Group Overview 负责边界、方向、主要入口、关键限制与少量跨群出口，不承担全量目录或状态面板。
10. Overview Calm 状态遵守明确的信息预算；完整结构、来源、历史、关系和建议按需进入。
11. Topic Opening 是进入该 Topic 后同一阅读滚动中的开场区域，不是强制中转页。
12. Topic Opening 依据真实内容自然表现为 Structural、Oriented 或 Authored，不成为生命周期评分。
13. Search、Ask、Citation、Relation 与 Resume 的深层目标可以绕过 Opening，直接落到 Knowledge / Anchor。
14. 递归 Topic 只增加当前层的局部方向；祖先只压缩为 DepthTrail，不重复整段 Overview。
15. Knowledge 围绕一个主要理解任务；长文与短文都合法。
16. 一份 Knowledge 只有一棵 Current content tree；Orientation、Outline、正文和 Claim 是同一内容的不同深度投影。
17. Section 与 Block 是正文内部结构，不成为日常知识对象或默认 Relation endpoint。
18. Section 是否提升为 Knowledge 由独立理解、证据、关系、复用与修订需要决定，不由长度、token 或 AI chunk 决定。
19. Knowledge Paper 默认连续可读，既不成为卡片汤，也不成为无法定位的文档孤岛。
20. Anchor 是 Knowledge / Overview 内部的稳定 locator，不是 Knowledge identity。
21. Claim 与 Evidence 必须通过 Knowledge revision、Anchor 和 Source fragment 构成可解释定位链。
22. 普通直接编辑经安全 commit 更新 Current；Edit Buffer、Recovery、Explicit Draft、Proposal 与 Sync 分开。
23. 保存状态必须讲真话；“已保存”只表示 Current commit 已成功，不表示同步、索引或 AI 分析完成。
24. 正常关闭、切换或发起读取动作应先安全 flush；成功时不出现额外确认，失败时保留 Recovery。
25. 用户可见 History 按有意义的编辑会话分组，而不是暴露每次按键或底层 checkpoint。
26. Restore 以新 revision 向前恢复，不抹掉后续历史，也不静默让旧引用改指新内容。
27. AI 修改默认是局部 Proposal / Diff，不重写整篇正文，不移动 Current pointer。
28. 从编辑现场 Ask 前先 flush Current；若 commit 失败，只能在用户明确同意后把未提交 Buffer 作为本次临时上下文。
29. 同一 Knowledge 的多个 Placements 共享正文；Placement context 只在当地生效。
30. 在多 Placement 场景编辑时，产品必须明确用户正在改 canonical body、当地 context，还是建立 fork。
31. Split / Merge / Promotion 是身份变换，必须迁移或重定向 Anchors、Placements、Relations、Evidence、Paths 与 History。
32. 从 Evidence、Search、Ask、Relation 和 History 返回时，恢复 origin revision、Placement、Anchor、scroll、focus 与必要 selection。
33. 长 Knowledge 通过 outline、section focus、find、Anchor 与渐进披露管理，不因长度自动拆碎。
34. AI、索引、网络或同步不可用时，Current reading、直接写作、local outline、History 和 Recovery 仍成立。
35. Desktop、compact、mobile、keyboard 与 screen reader 保留相同的理解、编辑、核验和返回责任。
36. 可恢复导出包含 canonical content、revisions、Anchors、redirects、Overview prose 与必要 Placement context；outline cache、embedding 和 scroll state 可重建。

---

# 1. 本合同解决的产品问题

## 1.1 “Overview 到细节”不能只是页面层级

如果 Overview、Topic 和正文只是三个不同页面，用户会经历：

- 每深入一层都先看一张中转卡；
- 每层都重复相同的摘要与目录；
- Search 命中深层内容却被迫回到上层入口；
- 从 Evidence、关系或 AI Answer 返回时只回到“这篇文档”，而不是原主张；
- 写作发生在另一个编辑器，阅读现场和知识语境消失。

这不是丰富层级，而是点击层级。

## 1.2 连续正文也有两个失败极端

### Card soup

每个段落、Claim、AI 摘要和引用都被提升为卡片：

- 阅读被对象边框切碎；
- 用户需要先决定粒度和类型；
- Overview 只会通向更多卡片；
- 复杂论证的条件、反例和证据失去上下文。

### Document island

所有内容都塞入没有内部定位能力的长文：

- Search、Ask 和 Relation 只能命中整篇；
- 证据无法说明支持哪一句；
- 多语境复用只能复制整篇或失去局部说明；
- 历史恢复与跨空间返回变得含糊。

## 1.3 产品答案

本产品选择：

```text
Scope identity
  └─ one Current content tree
       ├─ Orientation / Opening
       ├─ semantic Sections
       ├─ continuous Explanation
       ├─ local Claims / Anchors
       └─ Evidence exits

External structure: Group → Topic → Placement → Knowledge
Internal structure: Knowledge → Section → Block / Anchor
```

外部结构回答“这份知识在哪里、从什么范围进入”；内部结构回答“正文怎样阅读、定位和核验”。两者不能用同一 parent / child 关系混写。

---

# 2. 统一连续阅读模型

## 2.1 四类阅读目标

| Reading target | 用户正在理解什么 | 主要内容 | 是否有独立 canonical Knowledge identity |
|---|---|---|---|
| Group Overview | 一个完整知识范围 | Boundary、orientation、主要入口、限制、出口 | 否；由 Group owning |
| Topic Opening | 当前局部分支 | 当地 orientation、children、root Knowledge | 否；由 Topic owning |
| Knowledge Paper | 一个主要理解任务 | 连续正文、sections、Claims、Evidence | 是 |
| Source Fragment | 原始依据的精确上下文 | 原文、revision、locator、使用位置 | 否；由 Source owning |

用户不需要理解 owner 模型，但必须始终知道自己位于“范围导读、局部开场、知识正文还是来源原文”。

## 2.2 Reading Shell

Group、Topic 与 Knowledge 共享同一个 Reading Shell：

- Library / Group / Topic / Knowledge 的 DepthTrail；
- 当前 reading target 的标题与类型；
- 主阅读面；
- 可折叠 Structure；
- Contextual Search / Ask / Add；
- 必要时出现的 Evidence / Relation Companion；
- Back / Close 所需的 Return Context。

共享 Shell 不表示三者内容相同。它表示用户深入时不用切换产品心智模型。

## 2.3 DepthTrail

DepthTrail 表达 canonical Placement path：

```text
Library / 认知科学 / 记忆 / 长期记忆 / 检索练习的边界条件
```

规则：

- 当前项可辨，祖先可返回；
- 中段过长时压缩，但不丢失真实层级；
- 同一 Knowledge 有多个 Placements 时显示本次进入语境，并可查看其他语境；
- Search / Ask 直接进入时，用命中 Knowledge 的最佳可解释 Placement，不伪造唯一归属；
- 独立知识显示 `Library / 独立知识 / Knowledge`，`独立知识`是 derived view，不是 Placement。

## 2.4 Open、Expand、Inspect 与 Focus

| 动作 | 改变 Primary reading target | 写入 Return Context | 改变 canonical truth |
|---|---:|---:|---:|
| Expand / Collapse structure | 否 | 否 | 否 |
| Focus a section / Anchor | 否 | 只更新现场 | 否 |
| Inspect Evidence / Relation | 否；打开 Companion | 是 | 否 |
| Open Group / Topic / Knowledge | 是 | 是 | 否 |
| Edit and safe commit | 否 | 保留 | 是，更新 Current revision |

这四个动作必须使用不同交互语义。仅展开 Topic 不能偷偷改变当前阅读对象。

---

# 3. Overview：范围导读而非影子知识

## 3.1 Overview 的责任

Overview 先回答六个问题：

1. 这个范围是什么、不是什么；
2. 为什么值得现在进入；
3. 当前最稳妥的结构怎样理解；
4. 从哪里开始最合适；
5. 哪些限制、争议或未知会改变理解；
6. 有哪些少量但真实的跨群出口。

它不负责：

- 重复所有 Knowledge 的摘要；
- 展示所有 Sources、Relations、Questions 和状态；
- 生成“完成度”；
- 代替正文表达独立判断；
- 把 AI 建议包装成用户已经认可的叙述。

## 3.2 一个 scope，一份 Current Overview identity

Group / Topic 创建时即可拥有稳定 Overview identity，即便还没有正文。Bare、Structural、Oriented、Authored 只是内容密度，不是四份对象。

Rename、Move、Topic Promotion 与 Group restructuring 保留或明确迁移这份 identity；不得因为模板变化重新创建 Overview。

## 3.3 三种内容权力

### Editorial prose

用户直接维护的范围导读、判断与组织意图。它进入 Current revision，可以被历史、导出和恢复。

### Structure projection

从当前 canonical structure 生成的目录、入口、数量、范围状态与少量关系出口。它可以刷新，但必须能说明依据和更新时间；它不是用户写作。

### Reference

指向真实 Knowledge / Anchor / Question / Relation / Source 的可读引用。引用展示可以更新，目标身份不被复制。

AI Proposal 是临时变化权力，不是第四类 Current 内容。它以 Diff 覆盖在明确 target 上，未采纳时关闭即消失。

## 3.4 单一正文真相

Overview 的 Editorial content 只有一棵 Current tree。阅读时可以把 projection 与 references 穿插在其中，但不能把 projection 结果复制成另一段需要人工同步的 prose。

若用户把一段当前结构列表改写为叙述，产品必须明确：

- 原 projection 仍是自动结构；
- 新 prose 是用户 Editorial；
- 两者可以同时存在，但不互相覆盖；
- 结构以后变化时只提示相关 prose 可能过时，不自动重写。

## 3.5 Bare Overview

Bare Group / Topic 合法显示：

- 名称；
- 可选 Boundary；
- 已存在的直接 children / root Knowledge；
- `写一段导读`、`添加 Knowledge`、`建立 Topic` 三个适当入口。

不得显示：

- AI 自动补出的成熟总论；
- 0% 完成度、红色待办或“尚未整理”；
- 空白星图；
- 假装有结构的 skeleton cards。

## 3.6 默认信息预算

Calm Overview 的优先预算：

- 1 段 orientation；
- 3–7 个主要入口；
- 1 段结构导读或 local outline；
- 不超过 3 个关键 Relation / cross-group exits；
- 不超过 1 条真正影响理解的 change / unknown。

超出预算时使用“展开结构”“查看全部关系”“查看变化”，不在首屏堆叠折叠卡。

## 3.7 Overview 中的判断何时提升为 Knowledge

满足任一条件时，系统可建议 Promotion：

- 需要独立 Evidence；
- 需要成为正式 Relation endpoint；
- 会在其他 Group / Topic 复用；
- 需要独立适用条件或状态；
- 修订节奏明显不同；
- 用户频繁 Search / Ask / link 到它。

Promotion 保留原 Anchor，并在 Overview 留下可读 Reference。用户拒绝时该段仍可作为导读存在，不产生 Review debt。

---

# 4. Topic Opening：递归层级中的局部方向

## 4.1 三种自然密度

| Opening density | 真实条件 | 呈现 |
|---|---|---|
| Structural | 没有当地 Editorial | path、direct children、root Knowledge |
| Oriented | 有一句当地 orientation 或 curated entries | Structural + orientation + 主要入口 |
| Authored | 用户维护了局部导读 | Oriented + 连续 Editorial opening |

密度可以随着内容增加或删除自然变化，不触发状态迁移或升级庆祝。

## 4.2 同一滚动面

用户显式 Open Topic 后，Opening 出现在同一主阅读滚动的顶部，其下连续连接：

- direct root Knowledge；
- child Topics；
- 当前选择的 Knowledge Paper。

在宽屏上可以同时看到局部 structure 与正文；在窄屏上可以 drill-in，但返回仍恢复同一 Topic scene。Topic Opening 不是一张必须“继续”才能离开的中转页。

## 4.3 直接进入深层目标

下列入口不经过 Topic Opening：

- Search 命中 Knowledge Anchor；
- Ask citation / used Knowledge；
- Source usage；
- Relation open；
- Saved Path / Resume；
- History deep link。

到达后仍显示 DepthTrail 和当前 Topic context。用户选择“向上看”时才展开 Opening。

## 4.4 递归不重复祖先

进入深层 Topic 时：

- 当前 Topic 显示完整 local Opening；
- parent 只保留名称和必要 orientation；
- 更高 ancestors 压缩为 DepthTrail；
- 祖先 projection 可以列出 descendant 入口，但不创建镜像 Placement；
- 相同 Knowledge identity 在聚合列表只显示一次，并保留可选 paths。

## 4.5 Single-child 与 flatten

只有连续多个 Topic 同时满足以下条件时才可建议 flatten：

- 没有 orientation；
- 没有 root Knowledge；
- 没有 siblings；
- 每层只有一个 child。

建议必须预览 path redirects、Placements 和 saved returns。拒绝后不重复催促。Single-child 本身不自动 redirect。

---

# 5. Knowledge Paper：连续正文的产品合同

## 5.1 一份 Knowledge 的边界

Knowledge 回答一个主要理解任务，例如：

- “检索练习为什么有效，以及在哪些条件下失效”；
- “用户直接写作为什么应成为 Current”；
- “法国租房担保中 Visale 的适用条件”。

它可以包含定义、机制、例子、反例、条件、证据和结论。只要这些仍服务同一主要任务，就不必拆分。

## 5.2 Knowledge Paper 的默认组成

1. 标题；
2. 一句 orientation / applicability；
3. 可见但克制的 local outline；
4. 连续 Explanation；
5. 有需要才显露的 Claim / Anchor；
6. Evidence、Relation 与其他 Placements 入口；
7. History / status 按需。

正文不要求填满固定模板。缺少“反例”“结论”或“下一步”不显示空卡。

## 5.3 一棵 content tree

同一 Knowledge 不分别保存 summary、outline、long form、AI digest 与 mobile version 五份正文。

```text
Current Knowledge Revision
├─ title
├─ orientation range
├─ section tree
│  ├─ blocks
│  └─ inline claims / anchors
└─ local metadata required for interpretation
```

Outline 从 headings / semantic sections 投影；Orientation 取自用户明确维护的 opening range；Claim view 只呈现有 locator 的局部主张。任何 AI synthesis 都是 Answer 或 Proposal，除非用户明确写入 Current。

## 5.4 五层阅读深度

| Depth | 用户问题 | 产品行为 |
|---|---|---|
| D0 Orientation | 这是什么、对我是否适用 | 1–3 句；不隐藏 decisive limit |
| D1 Outline / Synthesis | 它怎样组成、结论在哪里 | local outline + curated section openings |
| D2 Explanation | 为什么、如何、有什么条件 | 连续正文 |
| D3 Claims | 哪些句子可以单独核验 | 只显露相关 local Anchors |
| D4 Evidence | 依据是什么、原文在哪里 | Source revision + exact fragment + context |

这是同一知识的深入，不是五个对象或五次保存。

## 5.5 Section 与 Block

- Section 提供语义结构、outline 和可折叠 focus；
- Block 支持编辑、渲染和定位；
- 两者默认都不出现在 Library、Network 或 Group catalog；
- Search 可以命中 Block，但结果显示 Knowledge title、section context 和 Anchor；
- Relation 默认连接 Knowledge；需要独立 Relation neighborhood 的局部主张先 Promotion。

## 5.6 Promotion 判断

Section 保持在正文中，当它：

- 依赖前后文才能理解；
- 与整篇共享适用条件；
- 只在当前解释中有意义；
- 不需要独立 Placement、Relation 或 Evidence state。

Section 可提升为 Knowledge，当它：

- 可独立解释一个理解任务；
- 需要独立复用；
- 需要独立 Evidence / challenge / applicability；
- 需要不同修订节奏；
- 用户明确希望独立进入。

字符数、段落数、token、embedding cluster 和 AI chunk 均不得成为自动拆分阈值。

## 5.7 长文导航

长 Knowledge 使用：

- sticky / on-demand local outline；
- 当前 section 高亮；
- Find within Knowledge；
- Anchor copy / deep link；
- collapsed secondary evidence，而非折叠主要正文；
- `回到上次阅读位置`与`回到开头`分开。

Outline 只列真实 headings / semantic sections。它可以帮助 rearrange，但拖动 section 是正文编辑，必须进入 Current history。

---

# 6. Anchor、Claim 与 Evidence

## 6.1 Anchor 的产品定义

Anchor 是 Overview / Knowledge 当前或历史 revision 内部的稳定定位引用。它可以被 Search、Ask、Evidence、Relation explanation、Reference、History 或 Saved Path 使用，但不拥有：

- 独立 Library row；
- Placement；
- Group membership；
- 正式 Relation identity；
- 独立 Current / History 生命周期。

## 6.2 Selector bundle

稳定 Anchor 不能只使用字符 offset。它至少结合：

- stable block / section id；
- origin revision；
- exact text quote；
- prefix / suffix context；
- semantic path；
- last resolved location。

编辑后按强到弱尝试：stable id → structural path → exact quote + context → controlled fuzzy relocation。解析结果必须可审计。

## 6.3 Anchor 状态

| State | 用户含义 | 行为 |
|---|---|---|
| exact | 仍在原处 | 正常打开 |
| relocated | 内容仍可明确定位，但位置改变 | 打开新位置并可查看迁移说明 |
| redirected | Split / Merge / Promotion 后由 lineage 指向新目标 | 显示目标变化 |
| ambiguous | 多处都可能是原位置 | 要求选择，不静默猜测 |
| orphaned | 当前正文已无可定位内容 | 打开历史上下文并提供修复 |
| unavailable | 所需 revision / content 不可读 | 说明原因，不显示空白成功态 |

## 6.4 两段 Evidence 链

```text
Knowledge Revision + Knowledge Anchor
  → Evidence Binding
  → Source Revision + Source Fragment
```

第一段说明“知识里的哪一条主张”，第二段说明“来源里的哪一处依据”。两者不能合并成一个 URL。

## 6.5 Claim 不是自动抽取对象

Claim 是正文中可单独核验的局部主张。以下行为不会自动创建新的知识对象：

- AI 识别一句陈述；
- 用户高亮一句话；
- Search 命中一个段落；
- 添加 Source citation；
- 关系 Inspector 引用某处。

只有需要独立 truth standing 时才 Promotion。

---

# 7. 阅读与编辑的连续性

## 7.1 读写不是两个产品

用户在 Overview / Knowledge Paper 中直接进入编辑，主阅读对象、Placement、Anchor 和 scroll 不变。退出编辑后回到同一位置，不跳到“文档列表”或“已保存页面”。

## 7.2 六种状态必须分开

| State | 拥有什么 | 能否改变 Current |
|---|---|---:|
| Edit Buffer | 当前设备尚未安全 commit 的输入 | 否 |
| Recovery Checkpoint | 防崩溃的本地恢复现场 | 否 |
| Current Revision | 用户当前认可并安全保存的正文 | 是，只有 safe commit |
| Explicit Draft | 用户主动保留的独立未完成版本 | 否，直到明确合并 |
| Proposal | AI / system / conflict 建议 | 否，直到采纳目标 Diff |
| Sync state | Current 是否复制到其他位置 | 否 |

Recovery 不能在 Library 里显示为一份“草稿 Knowledge”；Proposal 不能被 Search / Ask 当作 Current；Sync 失败不能回滚已成功的 local Current。

## 7.3 Safe commit boundary

系统可在以下边界尝试原子 commit：

- composition 完成后的短 idle；
- editor blur；
- 切换 reading target；
- normal close；
- explicit save；
- 发起 Search / Ask / Evidence / Relation 前。

commit 必须验证内容树完整、identity 未丢失、写入成功并生成 revision / history grouping。底层可以更频繁写 checkpoint，但不能把每次 checkpoint 都冒充 Current revision。

## 7.4 诚实保存状态

用户可见状态只使用：

- `正在保存…`：Current commit 尚未完成；
- `已保存到本机`：local Current commit 成功；
- `等待同步` / `同步失败`：不影响 local Current；
- `已恢复未保存内容`：Recovery 已载入 Buffer，尚未 commit；
- `保存失败，内容已保留`：Current 未改变，Recovery 可用。

不得用一个绿色勾同时代表本地保存、云同步、索引和 AI 分析。

## 7.5 关闭与导航

- commit 成功：无确认弹窗，保持返回现场；
- commit 暂时失败但 Recovery 成功：允许离开，但明确“当前版本未更新，输入已保留”；
- Recovery 也失败：阻止静默离开，提供复制内容与重试；
- 空白新 Knowledge 未产生 meaningful commit：退出不创建 `Untitled` 垃圾；
- 已有 Knowledge 删除到空：作为一次真实 revision 保存，删除对象需独立动作。

## 7.6 Ask from editor

提交 Ask 前：

1. 尝试 safe commit；
2. 成功则 Ask 使用新 Current revision；
3. 失败则默认只使用上一个 Current；
4. 用户可明确选择“仅本次包含未保存内容”；
5. 该选择不提交 Buffer、不改变 Current，也不被 Query history 当作以后知识。

## 7.7 AI 修改

AI 的默认修改单位是明确 Anchor / section：

- 显示 target、before、after、basis 和影响；
- 可逐项接受，不强迫整篇采用；
- 未受影响的正文保持字节 / 语义稳定；
- 接受后形成新的 Current revision；
- 拒绝不产生 Review debt；
- AI 不因“语气优化”重排所有 Anchors。

---

# 8. 多 Placement 与编辑范围

## 8.1 同一正文，多种进入语境

同一 Knowledge 出现在多个 Group / Topic 时，共享：

- title；
- Current content tree；
- History；
- Knowledge Anchors；
- Evidence Bindings；
- Knowledge Relations。

Placement 独有：

- 当地 orientation；
- 当地排序 / entry role；
- 当地可见状态；
- 当地问题与相关出口；
- 进入与返回现场。

## 8.2 编辑范围提示

从一个 Placement 进入并编辑时：

- 正文编辑默认清楚提示“将更新此 Knowledge 的所有位置”；
- 编辑当地说明只改变本 Placement；
- `Fork for this context` 建立新 Knowledge identity，并预览引用与关系后果；
- 不能让用户在一个嵌入片段里编辑，保存后才发现其他位置全部变化。

## 8.3 Reference / live excerpt / pinned excerpt / quote

| 方式 | 是否共享 Current | 目标变化后的行为 |
|---|---:|---|
| Reference link | 否；只指向目标 | 打开目标 Current |
| Live excerpt | 是；展示目标当前 Anchor | 更新并显示来源身份 |
| Pinned excerpt | 固定历史 revision | 保持原内容，提示有新版本 |
| Quote | 否；复制一段并保留出处 | 不自动更新 |

四者必须有不同视觉与编辑语义。

---

# 9. History、恢复与冲突

## 9.1 用户可见 History

History 按 meaningful editing session 分组。每项至少说明：

- 时间；
- 人 / AI / import / restore；
- 变化摘要；
- 受影响 sections / Anchors；
- 是否是 restore、split、merge 或 accepted Proposal；
- 可查看 Diff。

自动保存不等于每秒生成一条历史。系统可以保留细粒度 recovery logs，但放在 Forensic 层。

## 9.2 Restore forward

恢复旧版本时：

1. 先只读查看旧 revision；
2. 用户选择恢复全部或复制局部；
3. 全部恢复生成新的 Current revision；
4. 原当前版本仍在 History；
5. 旧 deep links 仍可打开原 revision；
6. 指向 current 的链接看到新 current，并可辨识 restore event。

## 9.3 Recovery 与 History 不同

Recovery 用于崩溃、写入失败与未完成输入；History 用于已经成为 Current 的过去版本。Recovery 被成功 commit 后可以清理，不能把它永久伪装成历史版本。

## 9.4 多设备 / 外部修改冲突

当本地 Current A 与另一路 Current B 都从同一 base 修改：

- 不允许 last-write-wins 静默覆盖；
- 自动合并只处理无重叠、可证明安全的局部变化；
- 其余形成 conflict Proposal；
- 用户可以接受 A、B、局部组合或 Fork；
- 决定生成新 Current revision，并保留两条 lineage。

## 9.5 Split / Merge / Promotion

身份变化至少处理：

- content blocks / sections；
- Anchors 与 redirects；
- Placements；
- Evidence Bindings；
- Relation explanations；
- Overview References；
- Search / Ask deep links；
- Saved Paths；
- History lineage。

剪切粘贴正文后删除旧 Knowledge 不满足该合同。

---

# 10. 跨场景返回合同

## 10.1 Return Context 最小组成

```text
origin_target
origin_revision
placement_context
anchor
scroll / focus / selection
structure_expansion
presentation_profile
optional query / relation / history scene
```

Workspace state 可以过期，但必须尽最大可能恢复；canonical target 与 Anchor 状态必须讲真话。

## 10.2 Evidence 往返

Knowledge Claim → Evidence → Source Fragment → Close：

- Source 显示 revision 与上下文；
- Close 回到同一 Knowledge revision / Anchor；
- 若 Current 已变化，先恢复原 revision 现场，再提示可切换 Current；
- Anchor relocated / orphaned 时显示状态，不跳到文档顶部。

## 10.3 Search 往返

Search result → Knowledge Anchor → Back：恢复 query、filters、result set、scroll、focus 和发起前现场。Search 不因为命中深层 Anchor 强制先开 Topic Opening。

## 10.4 Ask 往返

Answer Claim → used Knowledge Anchor → Evidence / Relation → Back：按栈逐层恢复，而不是全部退回 Ask 首页。未显式保存的 Answer 不进入 Current Knowledge。

## 10.5 Relation 往返

Knowledge Anchor → Peek / Companion / Explore → related Knowledge → Close：恢复 origin revision、Placement、Anchor、scroll、focus、relation selection 与 presentation radius。方向 2 永远能回到方向 3 的精确现场。

## 10.6 History 往返

Current → historical revision → inspect old Anchor → Back：回到 Current 原现场。选择 Restore 后生成新 Current，返回 restored Anchor 或最接近的明确位置。

---

# 11. 失败、规模、响应式与可访问性

## 11.1 AI unavailable

- Current Overview / Knowledge 可读写；
- Structure projection 使用本地 canonical data；
- AI Proposal 与 semantic assistance 说明不可用；
- 不隐藏 direct edit；
- 不用旧 AI output 伪装实时结果。

## 11.2 Index unavailable

- local outline、DepthTrail 与 direct hierarchy 可用；
- Search 可退化为标题 / 正文扫描并说明 coverage；
- exact links 仍按 stored Anchor 解析；
- projection incomplete 不覆盖 Editorial。

## 11.3 Very long Knowledge

对 100+ sections 或大型媒体正文：

- outline 虚拟化但保持顺序；
- 当前 section 与相邻内容优先加载；
- deep link 先解析 target，再加载周围上下文；
- Find 返回可解释 section；
- 导出包含完整 content，不以当前已渲染部分为准。

## 11.4 Large Group / deep hierarchy

- Overview 只显示主要入口和当前范围；
- Structure 默认只展开当前 path、siblings 与少量 children；
- direct Search / Anchor 仍可越层到达；
- 深度不固定封顶；
- 结构大不转化为一张全量画布。

## 11.5 Responsive responsibility

### Desktop wide

Primary Paper + optional Structure / Companion；编辑与阅读可在同一主面切换。

### Compact / tablet

Structure 与 Companion 使用可切换 pane / sheet；关闭恢复正文 Anchor。

### Mobile

保留：完整正文、local outline、直接编辑、保存状态、Evidence、History、Recovery、Search / Ask 与 exact return。不能把移动端降为只读摘要。

## 11.6 Accessibility

- headings 使用真实层级，不靠字号假装结构；
- outline、正文 heading 与当前 section 建立可读关联；
- Anchor focus 可由键盘和 screen reader 到达；
- 编辑、保存、同步、Proposal 状态不只依赖颜色；
- 200% zoom 时 Primary Paper 顺序不被 Companion 打断；
- reduced motion 下仍能理解 Opening → Paper、Paper → Evidence 与 Paper → Relation 的空间变化；
- Close 后焦点返回原 Claim / control。

---

# 12. 十四个真实场景压力测试

## WX-01 · Bare Group 的第一段理解

用户建立“认知科学”，只有名称。Overview 诚实显示空结构和写作入口；用户写一句 Boundary，安全保存后立即成为 Current Editorial，不要求 AI 采用。

## WX-02 · Group 有资料但没有成熟导读

Group 已有 18 条 Knowledge 和 4 个 Topics。Structure projection 列出主要入口，Editorial 仍可为空；系统不自动生成“认知科学完整总览”。

## WX-03 · 三层 Topic 直接进入

Search 命中“记忆 / 长期记忆 / 检索练习”内的一个 Claim。用户直接到达 Claim；DepthTrail 解释层级，Back 恢复 Search，不先经过三个 Opening。

## WX-04 · Authored Topic Opening

用户为“检索练习”写两段局部导读，其下有 6 条 Knowledge。Opening 与 root Knowledge 在同一连续阅读面；删除导读后自然退化为 Structural，不更换 Topic identity。

## WX-05 · 长 Knowledge 不拆卡

一篇 8,000 字 Knowledge 有 12 个 sections、4 个关键 Claims 和 9 条 Evidence。默认呈现连续 Paper；outline 负责扫描，Evidence 按 Claim 打开，不把 12 sections 全部变成卡片。

## WX-06 · 短 Knowledge 合法

一条只有标题、orientation 和两段解释的 Knowledge 可以独立复用和被引用，不因太短并入 Overview。

## WX-07 · Section Promotion

“间隔效应”一节开始在多个 Groups 被引用并需要独立 Evidence。Promotion 建立新 Knowledge，原位置留下 Reference，Anchors 与 deep links redirect，拒绝建议也不产生债务。

## WX-08 · 同一 Knowledge 多 Placement

“反馈延迟的边界条件”同时位于“学习科学”和“AI 教练”。编辑正文前提示影响所有位置；用户只改“AI 教练”当地说明时，另一 Placement 不变。

## WX-09 · 编辑时发起 Ask

用户刚改完一个结论便 Ask。safe commit 成功，Answer 使用新 Current。若磁盘写入失败，系统默认用旧 Current，并询问是否仅本次包含未保存文字。

## WX-10 · 崩溃恢复

编辑中应用崩溃。重新打开时载入 Recovery 到 Buffer，标明尚未保存；用户确认后 commit 成新 Current。History 不凭空出现几十个 checkpoint。

## WX-11 · Anchor 在改写后移动

一条 Evidence 原先指向第三节 Claim。重排 sections 后 stable id / quote 解析到第五节，状态为 relocated；Evidence 往返仍准确。若出现两个相同段落则进入 ambiguous，不静默选择。

## WX-12 · 恢复旧版本

用户查看两周前 revision，只复制一个段落回 Current，或选择整版恢复。整版恢复生成新 revision；两周后的历史仍存在，旧 citation 仍能打开旧 revision。

## WX-13 · 关系空间往返

用户从正文 Claim 打开跨群 Relation，比较另一篇 Knowledge 后关闭。产品恢复原 revision、Placement、Claim、scroll、focus 和 relation selection，而不是回到 Group 顶部。

## WX-14 · 离线、索引失败与导出恢复

离线仍可读写和打开 outline / History。索引损坏后 exact link 用 stored Anchor 解析。Knowledge Package 在干净环境恢复 Overview prose、content revisions、Placements、Anchors 和 redirects；embedding 与 scroll cache 可重建。

---

# 13. 可验证验收合同

## WEC-01 · Overview 不是 Knowledge

Group / Topic Overview 不出现在 Knowledge catalog，不成为普通 Relation endpoint，也不被 AI 当作独立 accepted Knowledge；它仍可被 Search 定位为 scope guide。

## WEC-02 · 单一 Overview identity

Bare → Structural → Authored → Structural 的变化不复制 overview_id、URL、History 或 Anchors。

## WEC-03 · Editorial / Projection 分权

Move Topic 后 projection 自动刷新；用户 Editorial 保持字面不变，只在确有语义影响时出现局部 cue。

## WEC-04 · Bare 不填充

没有 Editorial 与可投影内容时，界面不生成 AI prose、完成度、待办或空关系图。

## WEC-05 · Overview 直接编辑

用户编辑 Overview，经 safe commit 后直接成为 Current；界面没有“完成并采用”。

## WEC-06 · Shadow Claim 防线

Overview 中需要独立 Evidence / Relation 的判断可以 Promotion；未提升前 Ask 不把它伪装成独立 Knowledge claim。

## WEC-07 · Topic Opening 连续

显式 Open Topic 后，Opening 与其 direct structure / root Knowledge 属于同一阅读现场，不要求额外“进入正文”。

## WEC-08 · Deep target bypass

Search / Ask / Evidence / Relation / Resume 命中深层 Anchor 时直接到达；DepthTrail 正确，Back 恢复来源现场。

## WEC-09 · 递归 Overview 不复制

深层 Topic 只展示当地 Opening；祖先 prose 不重复，descendant projection 不创建新 Placements。

## WEC-10 · Expand / Open 分权

Expand 只改变 tree state；只有 explicit Open 改变 Primary target 和 Return Context。

## WEC-11 · 连续 Knowledge Paper

长正文默认不是逐段卡片；Section / Block 不出现在 Library 或 Network。

## WEC-12 · 长短 Knowledge 同权

产品不以字数、token 或 paragraph count 自动拆分、合并或降低 Knowledge 身份。

## WEC-13 · 单一 content tree

Orientation、Outline、Explanation 与 Claim view 可从同一 Current revision 追溯，不存在互相漂移的第二份 summary。

## WEC-14 · Promotion 有 lineage

Section Promotion 后原引用、Evidence、Search result、Saved Path 和历史链接可解析到旧 context 或新 Knowledge；取消零副作用。

## WEC-15 · Anchor 不静默漂移

编辑后 Anchor 只能为 exact、relocated、redirected、ambiguous、orphaned 或 unavailable；ambiguous / orphaned 不自动落到最接近文本。

## WEC-16 · Evidence 两段链

任一 Claim citation 可说明 Knowledge revision / Anchor 与 Source revision / Fragment；关闭 Source 后回到原 Claim。

## WEC-17 · 直接编辑 Current

普通用户写作的 safe commit 更新 Current；AI Review、Source 或 Proposal 不是前置条件。

## WEC-18 · 状态分权

Edit Buffer、Recovery、Current、Explicit Draft、Proposal 与 Sync 各自可构造测试状态，任何非 Current 状态都不能单独改变 Search / Ask truth。

## WEC-19 · 保存状态诚实

local commit 成功但 sync / index 失败时显示“已保存到本机”及独立失败状态；不得显示整体失败或整体成功。

## WEC-20 · 关闭不丢输入

commit 成功无确认；commit 失败但 Recovery 成功可恢复；两者都失败时不静默离开并允许复制输入。

## WEC-21 · Ask flush

Ask 前 commit 成功则使用新 Current；失败时默认用旧 Current，只有用户明确同意才仅本次包含 Buffer。

## WEC-22 · History 可理解

连续编辑形成有意义 session；用户可查看 Diff，而不是看到每个按键或 checkpoint。

## WEC-23 · Restore forward

恢复旧版形成新 Current revision；被恢复前的 Current 仍可见，历史 deep links 不改写。

## WEC-24 · 多 Placement 不复制

改 canonical body 后所有 Placements 读取同一 revision；改当地 context 不影响其他 Placements；移除一个 Placement 不删除正文。

## WEC-25 · AI local Diff

AI Proposal 有明确 target / before / after / basis；局部接受只改变目标，拒绝不创建 Review debt。

## WEC-26 · Exact return

Evidence、Search、Ask、Relation 与 History 往返恢复 origin target、revision、Placement、Anchor、scroll、focus 和必要 scene。

## WEC-27 · Failure responsibility

AI、index、sync 或 network 任一不可用时，Current reading、direct edit、local outline、History 和 Recovery 仍能独立工作。

## WEC-28 · Export / restore

在无 embedding、graph layout、search cache 与 saved scroll 的环境中，仍可恢复 Overview prose、Knowledge content / revisions、Placement context、Anchors、redirects、Evidence targets 与可读 History。

## 13.1 与 v6 Canonical AC 的映射

| 本合同 | v6 AC | Fixture / 场景压力 |
|---|---|---|
| WEC-01–06 | AC-03、AC-05、AC-09 | Fixture A / B 的成熟 Overview；Fixture C Bare Group；WX-01 / 02 |
| WEC-07–10 | AC-04、AC-10、AC-17、AC-18 | Fixture A / B 深层 Topic；Fixture C Search；WX-03 / 04 |
| WEC-11–16 | AC-06、AC-10、AC-20 | Fixture A / B 连续正文与 Evidence；WX-05–07 / 11 |
| WEC-17–23 | AC-09、AC-22、AC-27、AC-28、AC-29 | Fixture C direct write / offline / restore；Fixture A / B source change；WX-09 / 10 / 12 |
| WEC-24–26 | AC-07、AC-08、AC-17、AC-18、AC-20 | Fixture B 多 Placement / exact return；WX-08 / 13 |
| WEC-27–28 | AC-29–32 | Fixture C offline / clean restore；synthetic long-content / hierarchy scale；WX-14 |

映射表示本合同深化已有责任，不增加第 33 条 Canonical AC。任何 WEC 与 AC-01–AC-32 冲突时，v6 为准。

---

# 14. 外部研究与推论边界

## 14.1 长文需要可跟随的结构入口

Notion 官方把 Table of Contents 作为长文的 heading projection，可在页面顶部或滚动时位于侧边；编辑目录项需要编辑真实 heading。Obsidian Outline 同样列出 active note headings，并允许点击进入和拖动重排。

产品推论：local outline 应从同一 content tree 投影并与正文位置联动，不应保存为第二份手工目录；长文的答案是可到达的内部结构，不是自动碎片化。

- [Notion — Columns, headings & dividers](https://www.notion.com/help/columns-headings-and-dividers)
- [Obsidian — Outline](https://obsidian.md/help/Plugins/Outline)

## 14.2 深链接需要 heading / block 级定位，也要承认互操作边界

Obsidian 官方支持链接到 heading 与 block；block reference 使用特定 identifier，并明确说明这不是标准 Markdown 能力。

产品推论：知识库需要正文内部 Anchor 与清楚的 portable export 语义；Anchor 是产品能力，但不能假装所有外部格式都能无损表达它。

- [Obsidian — Internal links](https://obsidian.md/help/Linking%2Bnotes%2Band%2Bfiles/Internal%2Blinks)

## 14.3 单一内容多处出现需要明确共享语义

Notion Synced Blocks 让同一 block 在多处显示，任一实例的编辑会同步到其他位置，并明确展示 original / other pages；unsync 后各副本变为独立内容。

产品推论：live excerpt、fork 与普通 copy 必须有清楚不同的后果；本产品进一步选择 Knowledge identity + Placement 作为正文级多语境复用，而不是默认 block-level transclusion。

- [Notion — Synced blocks](https://www.notion.com/help/synced-blocks)

## 14.4 History 与 Recovery 是不同责任

Google Docs 官方支持查看、复制和恢复旧版本；Notion 的版本历史按编辑过程记录页面版本并支持查看变化、复制局部或恢复；Obsidian File Recovery 另外用设备本地 snapshots 保护意外删除、损坏和非预期变化，并明确说明它不是完整备份。

产品推论：已经提交的版本历史、尚未提交的崩溃恢复和完整备份不能用一个“历史”入口含混处理；本产品采用 session-grouped History、Recovery Checkpoint 与 Knowledge Package 分权。竞品的“恢复为当前”不直接证明本产品应回退 current pointer，因此本产品选择 restore forward。

- [Google Docs — Find what's changed in a file](https://support.google.com/docs/answer/190843?hl=en_)
- [Notion — Delete & restore content](https://www.notion.com/en-gb/help/duplicate-delete-and-restore-content)
- [Obsidian — File recovery](https://obsidian.md/help/Plugins/File%2Brecovery)

## 14.5 单一字符位置不足以稳定定位

W3C Web Annotation Selectors and States 同时定义 Text Quote Selector 与 Text Position Selector，并指出 position selector 对内容编辑非常脆弱，建议结合资源状态识别正确表示。

产品推论：Anchor 需要 stable id、revision、quote context 与 structural path 的 selector bundle；这是稳健定位的设计推论，不表示本产品必须采用 W3C 数据模型。

- [W3C — Selectors and States](https://www.w3.org/TR/selectors-states/)

## 14.6 研究没有证明什么

这些资料证明了成熟产品确实分别处理长文目录、深链接、共享内容、历史恢复和局部定位；它们没有证明：

- 本合同的五层 depth 一定最易理解；
- 用户愿意长期维护 Overview Editorial；
- Anchor relocation 的提示强度已经正确；
- restore forward 比用户熟悉的 restore-to-current 更直觉；
- Topic Opening 在真实深层目录里不会成为额外认知负担；
- 方向 3 + 2 的具体视觉布局。

这些仍需要三份 fixture、规模 fixture 与以后真实可用性测试验证。

---

# 15. 与相邻合同的所有权边界

| 问题 | Owner |
|---|---|
| Group / Topic 是否存在、如何 Move / Promote / Merge | `知识群层级、目录规模与结构演化合同` |
| Overview / Topic Opening / Knowledge Paper 如何读写 | **本合同** |
| Search / Ask / Answer 怎样发起与返回 | `AI查询、知识探索与返回连续性合同` |
| Source 如何保存、Annotation / Evidence / Formation 如何提交 | `知识进入、来源保存与知识形成合同` |
| Relation statement、Group Relation qualification、Graph / List | `关系、群级网络与探索连续性合同` |
| 本合同跨场景部分 | 只定义阅读目标、Anchor 和编辑现场的交接，不重新拥有对方流程 |

本合同吸收以下旧文档的有效部分，但不继承它们的旧术语和对象膨胀：

- `Overview形成编辑与更新合同-v1.0.md`；
- `直接创作编辑与版本历史合同-v1.0.md`；
- `知识节点粒度与内容组成合同-v1.0.md`。

三份旧文档继续留在 `MIGRATION_QUEUE` / 历史证据。发生冲突时，以 v6 Canonical 和本 Active Appendix 为准。

---

# 16. 对后续视觉设计的证明要求

在用户确认产品并允许视觉设计前，不修改当前 Ardot。之后 Screen 2 / Screen 6 至少必须证明：

1. Bare Group、Structural Topic、Authored Topic 和 long Knowledge 使用同一 Reading Shell；
2. Overview Editorial、Structure projection 与 Reference 在 Calm 状态可理解地共存；
3. Topic Opening 与 Knowledge Paper 连续，不是两张中转页；
4. long Knowledge 有真实 outline、current section、Claim 与 Evidence；
5. 普通直接编辑没有 AI 审批；
6. `正在保存 / 已保存到本机 / 等待同步 / 已恢复未保存内容`可区分；
7. AI Proposal 是局部 Diff，不是常驻右栏和整篇重写；
8. 同一 Knowledge 两个 Placements 的正文与当地 context 可区分；
9. Search / Ask / Evidence / Relation 直接进入 Anchor，并能精确返回；
10. exact / relocated / ambiguous / orphaned Anchor 至少有可理解的异常证明；
11. History session、Recovery 与 Restore forward 不混淆；
12. desktop / compact / mobile / keyboard 责任等价。

Screen 2 只保留“温暖主阅读面 + 按需深色关系空间”的视觉母体；Screen 6 只保留 user-owned Overview。旧永久双栏、常驻 AI 建议栏和“完成并采用”不得作为产品前提延续。

---

# 17. 最终判断

方向 3 的真正产品价值不是长文章，而是**有方向的连续深入**：

> **Overview 负责告诉用户这个知识范围是什么、从哪里进入；Topic Opening 只补当前层的局部方向；Knowledge Paper 承担完整理解；Anchor 和 Evidence 让长文可精确核验；直接编辑、History 与 Recovery 让它成为长期属于用户的 Current Knowledge。**

方向 2 由此不再与正文竞争：它从一个真实 Anchor 打开关系，帮助比较和迁移，再把用户送回同一个阅读现场。

这才是“知识库 + 丰富层级 + 可见关系 + AI 查询 + 网络探索”的统一产品，而不是文档工具、知识图谱和聊天工具的并排拼接。
