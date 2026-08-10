# AI-native 个人知识库

## 核心导航与复杂度收敛合同 v1.0 — 让知识重新成为产品中心

> 日期：2026-08-06；结构修订：2026-08-07  
> 文档性质：产品中心、稳定导航、群级入口与维护复杂度的收敛合同；不是视觉稿、MVP 切割、实现架构或原型授权  
> 用户确认：产品本质是个人知识库；核心是知识群、群间关系、Overview 到细节的丰富层级、AI 查询与知识网络探索；当前先定义产品  
> Canonical 产品定义：`AI-native-个人知识库-终局产品设计文档-v4.0.md`；本合同只是专项证明，不得反向改写 v4.0  
> v4.0 Query 覆写：Ask 是临时知识操作而非稳定 Place；Session / Turn / Run 默认不进入导航，Saved Answer 只作为历史 Snapshot；Requested / Effective / Used Context 与写回后果按需渐进披露  
> v4.0 策展覆写：Overview 的 stable start / representative / recommended Path 是长期 Scope curation；Library Resume、Recent、View sort 与 AI contextual next 不得改变它们或 Contents semantic order  
> v4.0 Scope 覆写：Group Boundary、Knowledge Placement、Source Attachment 与 View / Ask observation 不共享成员真相；Topic direct / descendants 是显式范围；Topic 不增加第五个 Sources Root，Source-only 语境通过 Topic Reading 与 Group Sources 的 exact path 进入  
> 历史深层模型：`AI-native-个人知识库-产品定义-v3.0.md`  
> 群工作区：`AI-native-个人知识库-知识群工作区与双镜连续性合同-v1.0.md`  
> 表面架构：`AI-native-个人知识库-产品表面架构与完整设计证明合同-v1.0.md`  
> 地点连续性：`AI-native-个人知识库-地点编排信息归属与跨地点连续性合同-v1.0.md`  
> 产品语言：`AI-native-个人知识库-产品语言与渐进披露规范-v1.0.md`

> **2026-08-07 Library-first 领域覆写：**`AI-native-个人知识库-核心心智模型与连续探索合同-v1.0.md`已取代本文原“四 Places / 四 Group Roots”数量结论。当前有效架构只有一个 Knowledge Library 主地点；`知识群 / Knowledge Network`是同一 Library 的两种视图；Home 的 Resume 责任并入 Library；Atlas 成为 R3 Network view；Sources 成为 supporting utility。Group 的 Overview、结构、关系、来源仍是四类完整责任，但不再表现为四个同权 Roots，Group / Topic / Knowledge 使用一个连续 reading shell。本文关于 attention routing、Primary / Companion、Focus / Inspect / Open、Decision 降权、返回与复杂度预算的规则继续有效；后文与本覆写冲突的“四 Places / 四 Roots”段落只保留为决策历史。
> **2026-08-09 Scale Invariance 领域覆写：**F1 / F10 / F100 / F10K 不新增导航、容器或 Large mode。Knowledge Library 的默认注意力顺序是最多一条 Resume → 紧凑 Pins → 穷尽 All Groups；Recent 是次级 View。Network 超预算先显示 Scope Summary / exhaustive List 并要求 Anchor，全库 Ask 按 Groups 说明 coverage。完整规则见`AI-native-个人知识库-规模化知识空间与长期可浏览性合同-v1.0.md`。
> **2026-08-10 Relation Lifecycle 领域覆写：**Network 的 Current / Suggested / History 是同一 Library view 的显式图层，不新增 Place；默认层只包含 maintained current Relations。Candidate、Challenge、Review 与历史处置以`AI-native-个人知识库-关系陈述生命周期与网络可信性合同-v1.0.md`为准。

---

# 0. 执行纠偏：完整不等于所有责任都进入导航

前几轮已经补齐对象、来源、版本、冲突、恢复、Review、状态与跨地点连续性。这些能力对一款可信、可长期拥有的知识库是必要的，但必要的内部责任不等于必要的永久入口。

当前规格仍有两个产品中心漂移：

1. 全局导航把 `Review / 待确认`与知识库、图谱、来源并列；
2. 每个知识群把`变化`与概览、结构、关系、来源并列。

这使用户即使只想读知识，也会持续看见两个维护中心。产品在模型上是知识库，在界面叙事上却接近知识治理系统。纠偏原则是：**保留全部维护能力，降低它们的默认显著性；知识是常驻空间，维护是按需任务。**

本合同冻结五十五项决定：

1. **产品唯一中心是用户拥有的知识。** Library Resume、导航、Group Header、空态和默认动作首先帮助进入、理解、查询、探索或建设知识。
2. **用户确认的五个核心需求是可见产品架构的最高约束。** 知识群、群关系、层级阅读、AI 查询、网络探索必须拥有最短主路径。
3. **Build、Maintain、Own 是完整性责任，不自动获得永久导航。** 创建、冲突、恢复、备份、迁移仍完整存在，但只在相关语境进入。
4. **内部对象数量、状态数量和流程复杂度不能为导航入口提供正当性。** 一个责任能被持久保存，不等于用户需要每天看见它。
5. **P0 日常概念仍只有知识群、主题、知识、关系、来源。** Review Item、Change Set、Workspace State、Projection 等只在改变动作后果时出现。
6. **一级产品中心继续收敛为一个 Knowledge Library。** 用户语言只有`知识库`；知识群与 Knowledge Network 是同一 Library 的两种视图。
7. **Review 不再是一级稳定地点。** 它保留为按需打开的 Knowledge Decision Workspace，用户语言为“需要你判断”。
8. **Settings、Trash、Backup、Import / Export、History 与 Decisions 都是 secondary workspaces。** 它们拥有稳定链接与返回，但不与知识世界并列。
9. **一级导航不得随 unread、AI 建议、同步状态或空队列动态增减。** Knowledge Library 始终稳定，维护入口在受影响语境中出现。
10. **Search、Ask、Add 是全局动作。** 它们不成为第五、第六、第七个 Place，也不在每个页面重复成主 CTA。
11. **普通启动进入上次使用的 Library view，并提供一个明确 Resume。** 普通点击 Group 打开 canonical Overview；只有点击`继续`才恢复 last-safe Reading scene。
12. **Library 只定向，不运营用户。** 它不显示每日总结、完成度、未读墙、整理债务或知识健康分数。
13. **Library 是产品的稳定目录。** 它优先呈现 Knowledge Groups；All Knowledge、Paths、Views、Archived 是次级浏览入口。
14. **Network 是 Library 的关系观察方式。** 默认从 Groups 与 maintained current Group Relations 开始，RelationCandidate 与 History 使用显式图层；不能把全部 Nodes、相似度与检索共现画成全局星云。
15. **Sources 是材料与证据的 supporting utility。** 它承载 Source identity、Reader、Revision、Annotation、Evidence、导入与可用性，但不与知识库争夺一级入口，也不成为连接器设置页。
16. **Group Workspace 只有一个连续 reading shell。** Overview、结构、关系、来源是四类完整责任；关系按 R0–R3 以 Peek / Companion / Explore 出现，不再冻结成四个同权 Roots。
17. **Changes 不再是每个 Group 的稳定 Root。** 高影响变化在 Overview notice、受影响对象、History / Impact View 和 Knowledge Decision Workspace 中按需出现。
18. **Reading 仍不是 Root。** 打开 Topic、Node 或 Anchor 后形成 `Group > Topic > Node > Anchor` Reading Path。
19. **普通打开 Group 固定进入 Overview。** `继续`恢复 last-safe Reading Path；deep link / Search / Answer / Relation / Source 进入精确目标。
20. **Overview 只回答“这是什么、边界是什么、从哪里开始”。** 它可以呈现用户策展的 stable start / representatives / recommended Path，并投影主要目录、关键关系、来源概况和最多一条高影响 notice；动态推荐不冒充稳定入口。
21. **Structure mode 承担完整层级。** Topic、Placement、semantic order、展开、移动、复用与定位都在这里成立；Overview 只投影主要结构，不复制完整树。
22. **Relation Companion 承担 Group Map 与 relation list。** Local Graph 仍属于当前 Reading Target 的 Companion，R1 / R2 / R3 范围与预算分开。
23. **Scope Sources 只解释材料为什么与当前 Group / Topic 有关。** direct attachment、used by accepted knowledge、referenced through shared knowledge 三种原因分开；完整 Source 管理进入 supporting utility。
24. **一个 Group Workspace 任一时刻只有一个 Primary Task。** desktop 最多一个 Primary、一个 Companion 与一个 Rail；mobile 顺序展开相同责任。
25. **方向 3 + 2 仍是 Reading-dominant、Balanced dual lens、Map-dominant 三种权重。** 移除 Changes Root 不改变双镜合同。
26. **Focus、Inspect、Open、Compare 保持不同后果。** 维护 notice、图谱 focus 或来源 hover 都不能暗中改变 durable Reading Target。
27. **“变化”是一类事件，不是一处长期地点。** 每个 event 只有一个 identity、一个当前状态与一个需要完成的责任。
28. **低风险变化在原位置解释并完成。** 例如重新生成可重建 Projection、重新定位来源片段、接受无语义影响的显示修复。
29. **高影响变化打开 Knowledge Decision Workspace。** 必须显示 base、change、affected、alternatives、defer、commit、undo 与 failure isolation。
30. **Knowledge Decision Workspace 不是 Inbox。** 只接收 true conflict、identity merge / split、Group transformation、accepted semantic change、high-impact relation 或 destructive migration。
31. **用户可以从四种地方进入同一个 Decision：受影响知识、Overview notice、Source impact、全局 Search / Command。** 不要求先去固定 Review Place。
32. **Decision 完成后返回触发位置。** 受影响对象、Source、Answer 与 Library contextual notice 共享状态，不留下第二份“待处理”。
33. **Library 最多出现一条“需要你判断”的高影响入口。** 它只在存在真实阻塞或会改变当前理解时出现，不显示计数竞争或清零压力。
34. **Group Overview 最多出现一条变化 notice。** notice 写明发生了什么、影响什么、当前能否继续阅读和去哪里处理；普通编辑历史不出现。
35. **History 是对象语境，不是第五个 Group Root。** Node、Overview、Relation、Source 与 Group 各从 owner Surface 打开 History / Impact。
36. **AI 查询继续是全局动作，不成为聊天 Place。** Quick Ask 是可关闭 Overlay；Full Answer 是有范围、依据、路径与返回的任务 Workspace。
37. **Ask 默认继承明确范围。** Focus / hover 不扩张范围；Open target、用户显式选择或提交前 Scope Control 才能改变 Requested Context。
38. **AI 回答必须回到知识。** 每个主要 Claim 能打开 Node / Anchor、Relation path 或 Evidence；保存 Answer 不等于写入 canonical knowledge。
39. **Search 优先定位，Ask 优先综合，Network / Relation Companion 优先探索。** 三者可以建议转换，但不得静默切换模式或写入知识。
40. **Add 同时支持直接写知识与添加来源。** 空 Group 不要求先导入资料；全局添加不要求先选择 Group。
41. **维护复杂度遵守 P0–P3 渐进披露。** P0 只显示后果与一个主要动作；P1 显示影响范围；P2 显示依据与替代；P3 才显示内部记录、运行与诊断。
42. **来源不可用不等于知识不可读。** canonical knowledge 与 last verified evidence 继续可见，并清楚标记当前核验限制。
43. **AI 不可用不改变 Library-first 架构。** 浏览、阅读、Search exact、编辑、关系、来源、History 与导出仍成立。
44. **图谱始终有同义 List Equivalent。** 图、列表共享 scope、identity、relation type、direction、standing、selection 与 open action。
45. **响应式只改变布局。** desktop 的 Library shell 可折叠；mobile 保留 Knowledge Library 和 Search / Ask / Add，关系与来源按需展开而不丢责任。
46. **键盘与辅助技术必须区分 focus、selection 与 activation。** Root、Tree、Graph List、Preview、Decision 的焦点可见且返回可预测。
47. **任何新的一级地点或群级 tab 都必须通过“独立长期问题”准入。** 只表达状态、历史、系统责任、观察方式或罕见维护动作的表面不得升级。
48. **删除 Review Place 与 Changes Root 不删除任何数据、History、Change Set、Decision 或恢复能力。** 这是信息架构收敛，不是功能删减。
49. **外部产品与标准只能证明导航、层级、图谱、preview / panel 和 focus patterns 可成立。** 它们不证明本产品的 Library-first、连续 reading shell 或显著性预算已通过用户验证。
50. **本合同不授权原型。** 先把 Library-first、连续 reading shell、Decision entry、返回与语言同步到所有产品合同，再讨论设计稿重构。
51. **Boundary 不拥有导航成员。** Overview 显示`这个知识群想理解什么`，Contents 显示当前 Placements，Sources 显示 Attachments / usage reasons，View / Ask 显示本次观察；任何一层都不能静默改写其他层。
52. **Group root 是 Contents 的合法位置。** `直接放在这个知识群`与 Topic placements 并列，不能被标成 Unplaced 或藏入虚构`其他`Topic。
53. **Topic 范围显式区分 direct 与 descendants。** `只看这个主题本身`与`包含子主题`改变 projection / browse / search scope，不制造 ancestor mirror membership。
54. **Topic 不获得独立 Sources tab 或 Subgroup shell。** Topic Reading 可以显示 direct Sources 与包含子主题的材料投影；完整管理进入 supporting Source utility，并保存 exact Attachment path。
55. **跨群 Topic transfer 不走普通导航拖拽。** 它进入结构 Change Set，预览 Placements、Source Attachments、Overview、Paths、redirects 与返回现场；导航只在提交后解析到新位置。

---

# 1. 证据边界与审计方法

## 1.1 已确认事实

- 产品本质是个人知识库；
- 用户希望拥有一个个知识群；
- 群之间可以看见 relation；
- 知识拥有丰富层级，能从 Overview 深入到细节；
- 用户能 AI 查询知识，也能在网络中探索；
- 视觉倾向方向 3 的层级阅读与方向 2 的关系空间结合；
- 当前先定义产品，不立即做原型。

## 1.2 当前设计证据

Ardot 当前仍是七张静态 Screen；它们能证明色彩、构图和局部概念，却不能证明稳定导航、根入口、返回、失败、响应式或维护显著性。原图不能反向证明 Review 或 Changes 必须常驻。

## 1.3 本轮判断方法

每个永久入口依次回答：

1. 它是否直接服务已确认的核心需求？
2. 它是否代表用户长期拥有的内容空间，而非状态或任务队列？
3. 用户是否会在没有系统提醒时主动进入？
4. 它是否拥有稳定内容，而不是可能长期为空？
5. 如果移入上下文，能力是否仍完整且更容易理解？

未通过其中至少前三项的，不进入稳定导航。

## 1.4 研究边界

官方产品资料用于理解成熟交互模式，不用于以竞品投票替代产品判断。尤其不能从“某产品有 Activity”推导本产品也需要 Activity，也不能从“某产品没有 Review”推导 Review 无价值。

---

# 2. 五个核心需求的产品证据矩阵

| 用户需求 | 稳定入口 | 核心对象 | 主路径 | 不应被什么取代 |
|---|---|---|---|---|
| 一个个知识群 | Knowledge | Group / Topic / Node / Placement | Knowledge → Group → Overview / Contents → Reading | 对象类型后台、文件列表、AI 推荐流 |
| 群之间 relation 可见 | Map | Group Relation / supporting path | Map → select Group / edge → Inspect → Open | 全节点星云、相似度、共享标签 |
| Overview 深入到细节 | Group Overview + Contents + Reading Path | Overview / Topic / Node / Anchor / Evidence | Overview → Topic → Node → Anchor → Evidence | 六张互不相干页面、摘要直跳原文 |
| AI 查询知识 | Ask | Query Turn / Run / Claim Support | Ask → scope → answer → claim → knowledge / evidence | 独立聊天历史、无范围生成文本 |
| 在知识网络探索 | Map + Relations + Local Graph | Group / Node Relations / Saved Path | inspect → open → companion → save path | hover 自动跳转、装饰连线、无限画布 |

支撑而非竞争产品中心的能力：

| 支撑能力 | 默认位置 | 何时升级 |
|---|---|---|
| 来源核验 | Sources / Evidence Rail | 需要完整 Reader、版本或 locator 修复时 |
| 变化解释 | owner notice / History | 影响当前理解或 accepted truth 时 |
| 高影响判断 | Knowledge Decision Workspace | 无法安全自动完成且后果跨对象时 |
| 备份恢复 | Settings / Recovery Workspace | 用户主动管理或系统检测到风险时 |
| 迁入迁出 | Import / Export Workspace | 用户主动开始或恢复包需要处理时 |

---

# 3. 当前规格的十六个复杂度漂移

## 3.1 Review 把维护误写成日常地点

Review 可能长期为空，也不会在没有提示时被多数用户主动浏览。它是一个需要完整设计的 Decision Workspace，但不满足稳定知识地点的准入条件。

## 3.2 Changes 把事件误写成知识群内容类型

Group Changes 主要表达 accepted content、structure、relation 与 evidence 的变化。它属于 owner history / impact，不与 Overview、Contents、Relations、Sources 同类。

## 3.3 “五 Places + 五 Roots”制造了虚假的整齐

对称数量看起来完整，却没有产品理由。导航结构应来自用户问题，不来自设计表格的均匀感。

## 3.4 Home、Changes 与 Review 重复表达同一事件

即使共享 event identity，用户仍会看见三个入口。技术去重不能解决产品显著性重复。

## 3.5 群内 Changes 与全局 Review 需要额外 handoff 教学

用户必须先理解“这里只看影响，真正处理去另一个 Place”。更自然的模型是：在影响发生处看见，打开同一个决定工作区处理，再返回。

## 3.6 Library 已经承担稳定拥有，却仍被 Review 分走 Working 维护心智

未完成知识应在 Knowledge 中可找回；高影响判断按需出现。用户不需要记忆“什么去 Library、什么去 Review”的治理分类。

## 3.7 十四类资源容易反向塑造页面

Primary Resource 是产品责任清单，不是页面清单。若每一类都要求稳定入口，Deep Model, Simple Surface 会失效。

## 3.8 Answer Workspace 容易成为第二个产品中心

当 Answer 有历史、路径、证据和保存动作后，很容易退化为聊天产品。它必须始终从问题回到知识，而不是把知识作为聊天附件。

## 3.9 Sources 容易成为导入后台

Sources 只有在同时承担阅读、版本、标注和证据核验时才配成为稳定地点；若只显示连接器与解析状态，应降为 Settings。

## 3.10 Map 容易成为视觉中心而非理解工具

全局 Map 必须从 Groups 开始并有关系陈述、方向、依据和 List Equivalent；否则方向 2 会吞掉方向 3。

## 3.11 Home 容易被变化与 Resume 填满

Home 的价值是重新进入知识世界，不是汇总所有系统责任。任何变化卡都必须证明它改变当前理解。

## 3.12 Root 命名仍偏系统语言

`Structure`对内部准确，P0 的`目录`更接近用户意图；`Relations`保留为`关系`，不要求理解 Lens / Root。

## 3.13 维护空态会制造整理焦虑

“没有待确认”不需要占据一个一级页面来庆祝清零。真正的空态是用户正在阅读，维护系统安静退场。

## 3.14 动态导航会破坏空间记忆

不能因为有 Decision 就临时增加第五个入口，也不能因为 Sources 为空就隐藏来源。Place 稳定，task contextual。

## 3.15 技术上可恢复不等于用户知道返回哪里

Decision、Evidence、Source Reader 与 Answer 都必须显示来源语境并原路返回；没有 Return Envelope 的上下文入口仍会迷路。

## 3.16 复杂度删减可能误删完整性

收敛不能简单隐藏冲突、历史和来源。每个被移出导航的能力仍需拥有入口、深链、失败、恢复、响应式和辅助技术合同。

---

# 4. 产品中心与可见复杂度预算

## 4.1 三层产品表面

| 层级 | 用户何时看见 | 内容 |
|---|---|---|
| Stable Knowledge Space | 每次使用 | Knowledge Library + Groups / Network views |
| Contextual Work Surface | 当前任务需要 | Group、Node、Answer、Source Reader、History / Impact、Decision |
| System / Recovery | 主动管理或故障 | Settings、Import / Export、Backup / Restore、Trash、Diagnostics |

第一层定义产品类别；第二层完成任务；第三层保证完整性。第二、第三层再复杂，也不能夺走第一层叙事。

## 4.2 稳定 Place 准入

一个 Place 必须同时满足：

- 对应一个长期用户问题；
- 拥有稳定、可主动浏览的用户资产；
- 不依赖 unread / failure / AI candidate 才有内容；
- 能从任意核心工作区到达并可预测返回；
- 不与另一个 Place 共享同一主要完成语义。

## 4.3 Root 准入

Group Root 必须：

- 围绕同一 Group 回答不同且长期成立的问题；
- 即使没有系统变化也有内容或诚实空态；
- 不只是一个状态过滤器；
- 与 Reading Path、Inspector、History 或全局 Place 分工清楚；
- 在 desktop 与 mobile 上责任一致。

## 4.4 默认可见动作预算

一个普通 Group 工作现场默认最多显示：

- 一个连续 Reading scene；
- 一个可折叠结构入口；
- 一个按需 Relation Companion 入口；
- 一个 Primary Action；
- Search / Ask / Add 三个全局动作中的安静入口；
- 一个必要状态；
- 一个 Context Rail 入口；
- 其余进入 overflow 或当前对象动作。

维护 badge、来源错误、AI suggestion、编辑状态和历史入口不能同时抢占 Header。

---

# 5. 一个稳定 Knowledge Library

## 5.1 Library / 知识库

回答：**我拥有哪些知识范围，现在从哪里继续？**

默认进入 Knowledge Groups。顶部最多提供一个明确 Resume，其后是紧凑 Pins 与穷尽 All Groups catalog；次级入口包括 All Knowledge、Paths & Answers、Views、Recent、Archived。Unplaced、Unfinished、Contested、Recently Updated 是 Views，不成为一级 nav 或待办箱。Library 保证不用 Search、Ask 或 AI 也能穷尽浏览，Paused Group 仍在 Catalog，只有显式 Archive 才离开。

## 5.2 Knowledge Groups view / 知识群

呈现一个个可独立进入的 Group，包含边界、主要 Topics / Knowledge、固定 / 最近状态与普通打开 / Continue 两个清楚动作。它不是营销 Home、统计 Dashboard 或卡片推荐流。

## 5.3 Knowledge Network view / 知识网络

回答：**我的知识群如何相连，我可以沿哪里继续探索？**

默认显示 Groups + Direct / Accepted Aggregated Group Relations、选中 Group 的 3–7 个主要邻接、relation statement、direction、why it matters、support 与 limits、Graph / List Equivalent。Inspect 不打开，Open 才进入 target；Saved Path 只保存探索顺序，不创造 Relation。

Network 不显示全部 Knowledge、相似度边、共享 Source、同一 Query 命中或 View membership 为 canonical edge。

## 5.4 Resume 与 supporting utilities

Resume 是 Library 中一个可解释入口，不是独立 Home。Sources、History、Decision、Import / Export、Backup、Settings 与 Trash 作为 supporting utilities 完整存在；它们主要从受影响 owner 或 utility menu 进入，不占一级产品地点。

---

# 6. 全局动作

## 6.1 Search

用于定位已有知识、来源、路径和精确 Anchor。exact-first，结果聚合到 owner identity；关闭后恢复原位置。

## 6.2 Ask

用于综合、比较、解释和发现缺口。提交前可预测范围，回答后可查实际使用范围；关闭或 Back 返回原知识位置。

## 6.3 Add

提供三个并列结果：写一条知识、新建知识群、添加来源。系统不把“添加”默认解释为 AI 编译，也不要求先分类。

## 6.4 Command

Command 是高级操作入口，可打开 History、Decision、Import / Export、Backup、Settings、Diagnostics；它不是普通用户必须学习的导航。

---

# 7. Group Workspace：一个连续 Scene + Reading Path

## 7.1 Scope Overview / 概览

回答：**这个知识群是什么，我应该从哪里开始？**

包含 boundary、orientation、主要目录投影、代表知识、关键关系、来源概况和可选 notice。Overview 不是 Dashboard，不显示所有状态与计数。

`从这里开始`只用于长期策展；无策展时写`按当前目录从这里开始`；`继续上次`与本次 AI / Explore suggestion 独立出现，不重排 Overview 或 Contents。

## 7.2 Structure / 结构

回答：**这里包含什么，它怎样从整体组织到细节？**

包含完整 Topic tree、Placements、semantic order、展开折叠、移动、复用、其他位置和当前 Reading Target 定位。它通过 DepthTrail、结构 rail、正文内子项和按需完整 tree mode 出现，不要求用户切换到另一个 Root。

Group root 的 Knowledge 以`直接放在这个知识群`单列；Topic 默认显示 direct content，用户显式选择`包含子主题`后才汇总 descendants。同一 Knowledge identity 可以保留多个 exact paths，但不在 ancestors 创建镜像 Placement。

## 7.3 Relation Companion / 关系

回答：**这个知识群内部怎样相连，又通向哪些群？**

关系以 R0 Reading、R1 Local、R2 Group、R3 Library 四个半径出现。Group Map 默认显示主要 Topics、少量 bridge Knowledge、正式关系与 1–3 个跨群出口；Local Graph 围绕当前 Reading Target，只作为 Peek / Companion / Explore，不改变当前阅读位置。

## 7.4 Scope Sources / 来源

回答：**哪些材料参与了这个知识群，我如何回到依据？**

三种 reason 分开：直接加入当前 Group / exact Topic、被当前 Knowledge 使用、通过共享 Knowledge 被引用。同一 Source 只显示一个 identity row，可展开多个 paths；detach 当前 path 不删除 Source 或 Evidence。完整材料进入 Source Reader supporting utility；具体 Claim 的证据仍从 Evidence Rail 进入。Topic Reading 只投影`直接加入这个主题的来源 / 包含子主题中的来源`，不增加 Sources tab。

## 7.5 Reading Path

Reading Path 由当前 Overview、结构入口、Relation、Source、Search、Ask 或外部 deep link 打开对象形成：

```text
Knowledge Group
  → Topic / branch context
    → Knowledge Node
      → Anchor / section
        → optional Evidence context
```

阅读目标改变时保留 origin、placement、depth、relation companion 与 return envelope。Back 回实际访问现场；Up 回结构父级；关闭 Companion / Inspector 回触发位置。

---

# 8. 变化、历史与决定的按需模型

## 8.1 Event 分类

| Event | 默认表达 | 完成地点 |
|---|---|---|
| ordinary edit | owner History | 已在原位置完成 |
| projection refresh | subtle status / refresh | owner Surface |
| Source relocated | Source notice | Source Reader / Sources |
| evidence impact | owner notice | Source Impact / affected knowledge |
| true semantic conflict | “需要你判断” | Knowledge Decision Workspace |
| identity merge / split | impact entry | Knowledge Decision Workspace |
| Group transform | impact entry | Knowledge Decision Workspace |
| destructive migration | system risk entry | Decision / Recovery Workspace |

## 8.2 Overview notice

只有同时满足以下条件才出现：

- 会改变用户当前理解、范围、主要关系或可信依据；
- 尚未被解决、延后或明确忽略；
- 用户从当前 Group 能理解影响；
- 有一个明确主要动作。

## 8.3 Knowledge Decision Workspace

```text
Decision Header
  affected knowledge
  entry context
  current status

Base
Proposed / competing change
Why it cannot be decided automatically
Affected knowledge / relations / overviews / answers
Alternatives
Defer / resolve / commit
Undo and failure isolation
```

Decision 是 task workspace，不加入一级导航。深链可以直接打开，但始终显示 owner 与返回目标。

## 8.4 History / Impact

History 以 owner 为中心：

- Group：boundary、structure、accepted overview 与 relation changes；
- Node：Current / Historical Revisions、Explicit Draft / Recovery、placement impact；
- Relation：statement、direction、support、standing；
- Source：Revision、locator、availability、bindings；
- Answer：Run、used context、snapshot lineage。

这些历史不混成一条全局 Activity feed。

---

# 9. 核心进入与返回合同

| 入口 | Initial Place | Primary Task | 返回 |
|---|---|---|---|
| 普通打开 Group | 当前 Library Surface；无上下文则 Groups view | Orient / Overview | 原知识群列表 |
| Continue Group | 原 Library Surface | last-safe task / Reading | 原启动 / Library Resume context |
| Map edge | Map | Explore / relation Inspect | edge + viewport |
| Search hit | 原 Place | Read exact target | result set + filters |
| Answer Claim | 原 Place / Answer | Read / Verify | Claim position |
| Source evidence | 原 Place / Sources | Verify | Claim / Node Anchor |
| Overview notice | 原 Place | Understand Change | same Overview position |
| Decision deep link | Default owner Place | Decide | caller or owner Surface |

`Review`不再能被用作 Default Place。Decision 无 caller 时按 owner 映射：knowledge / relation → Knowledge；source → Sources；cross-group relation → Map。

---

# 10. 响应式、键盘与辅助技术

## 10.1 Desktop

Knowledge Library 入口 + 当前 Reading Workspace。宽屏最多 Primary + Companion + Rail；不因移除 Home / Atlas / Review / Changes 的并列权力而把空出的空间填入更多永久工具。

## 10.2 Compact / tablet

Library 导航折叠；Companion 与 Rail 使用可返回的 Sheet / sequential panel；DepthTrail 与 Reading Path 保持可见。

## 10.3 Mobile

稳定主目的地仍是 Knowledge Library；Search / Ask / Add 通过固定动作进入，Network 与 Sources 按视图 / supporting utility 打开。复杂图谱默认 List Equivalent；Decision 从 notice / affected object 打开，不新增临时底栏项。

## 10.4 Keyboard

- Root switcher 使用 tabs pattern；
- Contents 使用 tree pattern；
- Graph list 使用 list / treegrid pattern；
- arrow / focus 不自动 activation；
- Enter / explicit action Open；
- Escape / Close 返回触发 control；
- Decision 完成后焦点回到已更新的 notice / object。

## 10.5 Non-visual equivalence

关系类型、方向、standing、变化影响与 Decision status 都有文字表达；不只靠 glow、颜色、位置、动画或 badge。

---

# 11. 十八个代表场景

## 11.1 First use

用户看见建立知识群、直接写知识、添加来源三条入口；没有 Review 空页、Changes Tab 或 AI hero。

## 11.2 普通打开成熟 Group

进入 Overview；目录、关系、来源稳定可见，历史和决定不抢占首屏。

## 11.3 Continue 深层阅读

恢复 Node + Anchor + companion；不先跳 Library 根层或 Overview。

## 11.4 从 Map 沿群关系探索

先 Inspect relation statement 与 support，再 Open endpoint；Back 恢复 edge 与 viewport。

## 11.5 从 Overview 深入 Evidence

Overview → Contents → Node → Anchor → Evidence；每一步保留父级位置和返回。

## 11.6 AI 查询当前 Group

提交前说明范围；回答 Claim 可回到 Node / Relation / Evidence；关闭回到原阅读。

## 11.7 AI 不可用

Library、结构、阅读、图谱列表、来源、编辑与 Search exact 继续成立。

## 11.8 无关系 Group

Relations 显示诚实空态和建立关系 / 查看目录动作，不渲染随机星图。

## 11.9 无来源 Group

Sources 说明用户原创知识合法，并提供添加材料；不显示质量分或治理警报。

## 11.10 普通编辑

完成后进入 owner History，不产生 Library Resume 卡、Group Changes item 或 Decision。

## 11.11 来源更新但知识未受影响

Sources 显示 Revision 更新；Group 与 Library Resume 保持安静。

## 11.12 来源更新影响 accepted Claim

受影响 Node 和 Group Overview 出现同一 event notice；打开 Source Impact 或 Decision，解决后两处同步消失。

## 11.13 True conflict

从受影响知识打开 Knowledge Decision Workspace；显示 alternatives 与影响；完成后返回知识，不要求先进入 Review Place。

## 11.14 Decision 长期为空

产品导航没有空的“待确认”；用户正常使用知识库，不收到清零暗示。

## 11.15 Search 深层命中

打开 Node + Anchor；Reading Path 显示 Group / Topic context；Back 回 result set。

## 11.16 Mobile 关系探索

图谱使用 List Equivalent；Inspect 与 Open 分开；关系完成后能回 Reading。

## 11.17 Source unavailable

知识仍可读；Evidence 显示 last verified snapshot 与当前限制；修复动作去 Sources。

## 11.18 大规模知识库

Knowledge 以 Group / Search / Views 定位，Map 以 Group relations 和预算显示；不恢复全节点 hairball 或全局 Activity。

---

# 12. 二十一条 Given / When / Then

## 12.1 Library-first 稳定

**Given** 用户在任意知识工作区  
**When** 打开全局导航  
**Then** Knowledge Library 是唯一主地点，Groups / Network 是同义视图；Search、Ask、Add 是动作；Sources 与 Decision 不占同权固定位置。

## 12.2 Review 能力未删除

**Given** 存在 true conflict  
**When** 用户从受影响知识打开“需要你判断”  
**Then** 完整 Decision Workspace 可用，并在完成后回到原知识位置。

## 12.3 Group 连续 scene

**Given** 用户打开任意 Group  
**When** 查看根入口  
**Then** 只有概览、目录、关系、来源；阅读通过对象路径形成，变化通过 notice / History 进入。

## 12.4 普通打开与继续

**Given** Group 存在 last-safe 深层阅读  
**When** 分别执行打开与继续  
**Then** 打开进入 Overview；继续恢复 exact Reading Target、Anchor 与 companion。

## 12.5 Overview 不成为 Dashboard

**Given** Group 有来源更新、普通编辑、AI suggestion 与一个 true conflict  
**When** 打开 Overview  
**Then** 最多显示会改变理解的一条 notice；其余信息在 owner / relevant surface。

## 12.6 Contents 完整层级

**Given** Node 在多个 Topics / Groups 出现  
**When** 从目录浏览  
**Then** 每个 Placement 可定位且共享一个 Node identity；移动、保留两处与打开后果清楚。

## 12.7 Map 不画伪关系

**Given** 两个 Groups 只共享 Source 或同次 Query  
**When** 打开 Map  
**Then** 不出现 canonical edge；可以在解释层显示临时线索并清楚标注。

## 12.8 Inspect 不改变阅读

**Given** 用户正在长文 D2 阅读  
**When** 在目录、图谱或来源列表移动 focus / inspect  
**Then** Reading Target、Ask Scope、History 与 scroll 不变；只有 Open 改变目标。

## 12.9 Ask 回到知识

**Given** Answer 使用多个 Groups  
**When** 用户打开 Claim 依据再 Back  
**Then** 依次恢复 Claim、Answer 与原 Workspace；不会进入独立聊天首页。

## 12.10 来源影响不复制任务

**Given** 一个 Source Revision 影响 accepted knowledge  
**When** 从 Node、Overview 或 Sources 打开并解决  
**Then** 三处使用同一 event / decision state；只完成一次，不留下多份未读。

## 12.11 普通历史不打扰

**Given** 用户完成一次普通正文编辑  
**When** 返回 Overview 与 Library Resume  
**Then** 不出现变化卡或待确认；History 仍可从 Node 打开。

## 12.12 Decision 空态不占导航

**Given** 没有任何高影响判断  
**When** 用户使用产品  
**Then** 不显示空 Review Place、0 badge 或“全部处理完成”；知识空间保持安静。

## 12.13 AI unavailable

**Given** 模型不可用  
**When** 用户进入 Library、Group 与 supporting utility  
**Then** 导航不变；浏览、阅读、编辑、Search exact、relations、sources 与 export 继续可用。

## 12.14 Graph / List 同义

**Given** Map 有 typed relations  
**When** 切换到 List Equivalent  
**Then** scope、identity、type、direction、standing、filter、selection 与 open action 一致。

## 12.15 Mobile 责任不缩水

**Given** desktop Group 缩到 mobile  
**When** Primary / Companion / Rail 改为顺序  
**Then** Overview、结构、关系、来源四类责任、Reading、Evidence、History、Decision entry 与返回仍可达；不临时增加 Roots 或 Changes Tab。

## 12.16 Source unavailable

**Given** live Source 不可用但有 verified snapshot  
**When** 用户阅读支撑 Claim  
**Then** canonical knowledge 与 snapshot 可读，当前核验限制明确，修复动作进入 Sources。

## 12.17 Deep link 无 caller

**Given** 用户直接打开一个 Decision deep link  
**When** 没有调用现场  
**Then** 系统按 owner 映射进入 Knowledge、Map 或 Sources，并显示明确 owner 与返回目标；不默认 Review。

## 12.18 完整性没有被隐藏

**Given** Review Place 与 Changes Root 已移除  
**When** 审计 conflict、merge、split、source impact、history、undo、recovery、offline 与 accessibility  
**Then** 每项仍有 owner entry、完整 surface、状态、返回和辅助技术证据。

## 12.19 Root placement 与 Unplaced

**Given** Knowledge 直接 placed 到 Group root  
**When** 用户在 Contents、Search 与 Unplaced 间移动  
**Then** 它始终属于该 Group并写`直接放在这个知识群`；只有最后一个 active Placement 被移除后才进入 Unplaced。

## 12.20 Topic direct / descendants

**Given** Topic 的内容主要位于多层 descendants  
**When** 用户在 Topic Reading、Contents 与 Search 切换 direct / include descendants  
**Then** 三个表面使用同一 scope semantics、保留 exact paths 与 identity dedupe；Topic 仍无独立 Workspace 或第五个 Root。

## 12.21 Source-only exact path

**Given** Source-only 从深层 Topic 加入且解析失败  
**When** 用户从 Topic Reading 与 Group Sources 找回并 detach  
**Then** 两处显示同一 Source identity 与 exact path；Attachment 缺失以具体失败说明；detach 不删除 Source、其他 paths、Fragments 或 Bindings。

---

# 13. 官方研究依据与产品推论

## 13.1 Tana Outline 与 Interface

Tana 官方把 graph data 主要通过 outline editor 交互；层级可展开、折叠、重排并 zoom 到任一 node。其当前 Interface 同时显示 flat destinations、Library、Search、Quick Chat、tabs 和 split，但这些属于 Tana 的协作 / task / meeting 产品范围。

产品推论：graph 不必成为默认内容界面；层级可以是主要阅读和组织方式。Tana 的 Activity / Tasks 不证明个人知识库需要对应入口。

[Tana Outline Editor](https://outliner.tana.inc/learn/features/outline-editor)、[Tana Interface](https://tana.inc/learn/features/interface)

## 13.2 Capacities Navigation 与 Object Types

Capacities 官方区分 full-page、preview modal、side panel 与 tabs；Object Types 和 objects 通过 sidebar / dashboards 进入，维护状态没有因此成为独立永久产品中心。

产品推论：同一知识可以使用不同 surface role，preview / panel / full page 不复制 identity；完整内部对象模型不要求每种责任进入一级导航。

[Capacities Navigation](https://docs.capacities.io/reference/navigation)、[Capacities Object Types](https://docs.capacities.io/reference/content-types)

## 13.3 Obsidian File Explorer 与 Backlinks

Obsidian 官方 File Explorer 提供稳定文件 / 文件夹浏览；Backlinks 跟随 active note 或固定到特定 note；Graph、Outline 等是可调用能力，而不是每种能力都成为强制工作流。

产品推论：稳定目录、当前对象关系与全局图谱是不同责任；局部关系可以跟随阅读，不要求独立维护中心。

[Obsidian File Explorer](https://obsidian.md/help/plugins/file-explorer)、[Obsidian Backlinks](https://obsidian.md/help/plugins/backlinks)、[Obsidian Graph](https://obsidian.md/help/plugins/graph)

## 13.4 Anytype Sidebar 与 Graph

Anytype 官方 sidebar 围绕 Search、Pinned、Objects / Types；Graph 可以从应用中进入，用于看对象连接。Sidebar widgets 可以定制，但其内部对象模型不等于固定一级导航清单。

产品推论：用户资产、常用入口与图谱可以分工；稳定 identity 不自动获得永久 nav。

[Anytype Sidebar](https://doc.anytype.io/anytype-docs/getting-started/customize-and-edit-the-sidebar)、[Anytype Objects](https://doc.anytype.io/anytype-docs/getting-started/object-editor)、[Anytype Graph](https://doc.anytype.io/anytype-docs/advanced/feature-list-by-platform/graph)

## 13.5 WAI-ARIA Tabs、Tree 与 Keyboard Interface

WAI-ARIA Authoring Practices 区分 focus、selection 与 activation，并为 tabs、tree 和 composite widgets 定义可预测键盘行为与焦点返回。

产品推论：Root、目录、图谱列表、Preview 与 Open 不能共用一个 selection changed；收敛入口后仍必须保留完整 keyboard semantics。

[Tabs Pattern](https://www.w3.org/WAI/ARIA/apg/patterns/tabs/)、[Tree View Pattern](https://www.w3.org/WAI/ARIA/apg/patterns/treeview/)、[Keyboard Interface](https://www.w3.org/WAI/ARIA/apg/practices/keyboard-interface/)

## 13.6 研究没有证明什么

以上资料没有证明 Library-first、连续 Group scene、Library notice 上限或 Decision entry 已被用户验证。这些是根据已确认产品中心、现有合同冲突与复杂度预算做出的可测试产品决定。

---

# 14. 对相邻合同的同步要求

## 14.1 主产品定义

- 一级导航收敛为 Knowledge Library；Groups / Network 是同一入口的两种观察；
- Review 改为 Knowledge Decision Workspace；
- Group 改为连续 reading shell，保留概览、结构、关系、来源四类责任；
- Changes 改为 notice / History / Impact；
- 冻结入口准入与可见复杂度预算。

## 14.2 表面架构与地点连续性

- Place taxonomy 使用一个 Knowledge Library 主地点，Groups / Network 为两种视图，Resume 为 Library 内区域；
- Decision / Recovery 继续是完整 surface role；
- Default Surface map 不再指向 Review、Home 或 Atlas；
- Attention 使用 Primary Destination，不假设一定是 Place。

## 14.3 交互与流程

- LibraryNav 只承载 Knowledge Library；ContextControls 按任务披露概览、结构、关系、来源四类责任；
- Changes / Review 入口改为 ContextualNotice、HistoryImpactEntry、DecisionWorkspaceHeader；
- 更新 startup、Library Resume、Group、source impact、conflict、deep link 与 responsive gates；
- 旧 81 个 Coverage ID 不新增、不删除，只作为状态责任重写表面归属；新设计按十二个 proof families 组织。

## 14.4 产品语言

- 稳定主地点：`知识库`；其内视图：`知识群 / 知识网络`；
- 群责任：`概览 / 结构 / 关系 / 来源`，不要求同权标签；
- 高影响判断：`需要你判断`；
- 普通历史：`查看修改记录`；
- 禁止默认出现`Review / Changes / Activity / 未读 0 / 清空待办`。

## 14.5 设计审查

- 原有五地点和五 Roots 的设计忠实度条款被本合同取代；
- 下一轮设计必须先证明 Library-first、连续 Group scene、Reading Path、Relation Radius 与 contextual Decision；
- 仍不授权开始原型或高保真重画。

---

# 15. 结论

产品完整性的真正考验不是“每种内部责任有没有一个入口”，而是：用户是否可以始终感到自己住在知识里，而不是在维护知识的后台里。

因此最终可见骨架收敛为：

```text
Knowledge Library
  Resume region
  Groups view
  Knowledge Network view

Global Actions
  Search
  Ask
  Add

Continuous Group Scene
  Overview reading
  Structure context
  Relation companion / explore
  Source verification
  Topic / Knowledge Reading Path

Supporting Utilities
  Sources / Evidence
  History / Impact
  Knowledge Decision
  Recovery / Settings
```

> **知识、关系和来源长期存在；变化、判断和恢复在需要时出现。完整能力留在产品里，但产品中心回到知识本身。**
