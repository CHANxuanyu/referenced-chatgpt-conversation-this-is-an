# AI-native 个人知识库

## Library 浏览与动态视图合同 v1.0 — Stable Catalog、Placement Browser、View Definition 与认知方向感

> 文档日期：2026-08-08  
> 文档性质：产品本体与交互合同，不是侧边栏线框、数据库表格规格、导航原型或视觉稿  
> Canonical 产品定义：`AI-native-个人知识库-终局产品设计文档-v4.0.md`；本合同只证明 Library 与 View 责任，不得反向改写 v4.0  
> 2026-08-07 写入冻结：无 Placement 的 Direct Edit Commit 是 Current Knowledge 并进入 Unplaced；Explicit Draft 进入 Draft View，Recovery-only 内容只从恢复入口出现  
> v4.0 策展覆写：Library Pin、Recent、View sort 与 Evaluation 不参与 Scope stable start / representative / recommended Path；后者是 Overview 的局部 curation reference  
> v4.0 Scope 覆写：Group Boundary、Placements 与 View criteria 分离；Group root 是合法 Placement target；Topic direct / descendants 是浏览范围，不复制 membership；Topic merge / split / transfer 通过 Change Set 与 lineage 维护 Library 路径连续性  
> v4.0 探索连续性覆写：SavedPath identity / Revision 与 PathProgress / ResumePoint 分开；Library 目录展示路线本身，Library Resume / Continue 展示进度；`last_position`不得写入 SavedPath  
> 2026-08-08 Library-first 冻结：Library 是唯一主地点；Groups / Network 是同一 Library 的两种观察，Resume 是 Library 内的恢复区域；Search / Ask / Add 是动作，Sources 与 Knowledge Decision 是 supporting utilities。本文关于 identity / placement、Views、Pin、Recent、Saved Path、Answers 与返回现场的合同继续有效  
> 2026-08-08 Topic Opening 冻结：Topic disclosure 只展开层级，Inspect 只预览，Open Topic 进入同一 Reading surface 顶部的局部开场；Knowledge row / deep link 直接进入目标，不被 Topic Overview 截停  
> 2026-08-09 Scale Invariance 冻结：F1 / F10 / F100 / F10K 只是设计夹具，不是用户模式；默认顺序固定为最多一条 Resume → 紧凑 Pins → 穷尽 All Groups catalog，Recent 退到次级 View；大规模 Network 超出预算时进入 Anchor Required，不以 AI / 度数 Top N、自动 Group regions 或缩小全图代替完整目录  
> 2026-08-10 Relation Lifecycle 覆写：Library Network 默认只观察 maintained current Group Relations；RelationCandidate、open Challenge / review 与 ended / superseded / retracted / archived History 使用显式图层或筛选。完整合同见`AI-native-个人知识库-关系陈述生命周期与网络可信性合同-v1.0.md`  
> 历史深层模型：`AI-native-个人知识库-产品定义-v3.0.md`  
> 相邻合同：`AI-native-个人知识库-知识群边界与跨群架构合同-v1.0.md`、`AI-native-个人知识库-知识节点粒度与内容组成合同-v1.0.md`、`AI-native-个人知识库-搜索定位与知识找回合同-v1.0.md`、`AI-native-个人知识库-直接创作编辑与版本历史合同-v1.0.md`、`AI-native-个人知识库-属性Facet与适用条件合同-v1.0.md`、`AI-native-个人知识库-产品对象层级与身份治理合同-v1.0.md`  
> 核心问题：当用户不输入搜索词、不向 AI 提问、也不打开图谱时，怎样稳定看见自己真正拥有的知识结构、全部知识身份、当前位置和可复用观察方式

---

# 0. 执行决定

本轮冻结六十八项产品决定。

1. **Library 是唯一知识主地点。** 它同时提供稳定目录、一个克制的 Resume 区域，以及 Groups / Network 两种同义观察；产品不再维护第二个 Home truth。
2. **Browse 是不依赖 Query 的一等使用方式。** 用户可以只凭“我知道大概属于哪里”沿 Group、Topic 与 Placement 找到知识，不必先回忆准确词语或问 AI。
3. **Library 内部观察与支撑能力各守真相。** Groups view 看结构与对象；Network view 看正式关系；Search 负责定位；Sources utility 看原始材料；Knowledge Decision utility 处理高影响判断。它们不是五个并列产品中心。
4. **Library Root 不是一个新的 Knowledge Group，也不拥有 canonical Overview。** “全部知识”只是 Space 内对象的稳定目录入口，不形成第二份 Space truth。
5. **Library 不做万能对象或 record 浏览器。** 默认目录围绕 Groups、Knowledge Nodes、Saved Paths、Saved Answers 与 View Definitions；Revisions、Bindings、Runs、Assertions、Evaluations 与 Workspace State 通过 owner / History / Evidence / Definition 进入，Sources、Relations、Knowledge Decisions 与 Trash 各回到自己的上下文入口或 supporting utility。
6. **Group / Topic Browser 的结果单位是 Placement Row。** 它回答“这条知识在当前结构中的位置”，但 Row 始终引用同一个 canonical Node identity。
7. **All Knowledge Catalog 的结果单位是 Object Identity。** 一个 Node 无论有多少 Placements 默认只出现一次，所有位置可展开。
8. **每个浏览表面必须声明 result unit：identity 或 placement。** 产品不能有时按对象、有时按位置重复，却不给用户解释。
9. **同一 Node 出现在多个 Group / Topic 时不是副本。** 编辑正文影响所有位置；只调整当前位置只改变 Placement；两种动作必须在 Library 中持续可区分。
10. **同名不同对象不能因目录排序靠近而自动合并。** Row 用一句 definition、Group / Placement、Applicability、状态与 kind 消歧。
11. **Group 是可独立维护边界的知识范围，Topic 是 Group 内的有序结构。** Library 不重新引入 Folder、Subgroup、Collection 作为第三套层级容器。
12. **All Knowledge 不是用户必须整理的收件箱。** 它包含当前可浏览知识身份；Unplaced 只是按 `active_placement_count = 0` 求值的系统 View，不以红点、欠账或清零奖励催促。
13. **Draft Node 是显式、合法、可找回的状态，但不是 Node lifecycle。** 用户正常直接写入在本地保存后成为 current Revision；只有显式草稿、冲突或恢复分支进入 Draft View，默认 Ask 不使用它们。
14. **View 是观察规则，不是成员容器。** 它保存 scope、typed criteria、filter、sort、group、layout 与 property visibility，按 stable property / enum IDs 引用 Definitions，不保存静态 member ids。
15. **System View 与 User View 使用同一 View Definition。** “全部知识”“未归类知识”“未完成修改”“最近修改”“可能过时”和用户保存视图的来源不同，但都不创造 membership。
16. **Library 不新增通用 Manual Collection 对象。** 手工长期归属使用 Group / Topic + Placement；有顺序的人工精选使用 Saved Path；快捷入口使用 Pin；冻结集合使用 Snapshot。
17. **Saved Path 与 View 不互相代替。** Path 保存有意图的顺序和进入路线；View 按规则动态求值，没有默认叙事顺序。
18. **Pin 是快捷方式，不是知识关系、优先级或成员资格。** 固定 Group、Node、Path 或 View 只改变个人导航入口，不提升知识权威性。
19. **Recent 是访问历史的派生表面，不是内容状态。** 最近打开、最近编辑与最近形成必须分别命名，不能混成一个含糊的“最近”。
20. **Recent 不参与 Knowledge Truth 或默认重要性排序。** 打开得多、刚编辑或最近访问不能自动让对象进入 Overview、Ask 或 Library Network 高显著层。
21. **Hierarchy Browser 默认遵循用户认可的语义顺序。** Topic sibling order 与 Node Placement order 是结构信息，不被更新时间静默覆盖。
22. **临时 Sort 不改写结构顺序。** 按标题、创建时间、更新时间、状态或 Applicability 排序只改变当前 View；只有显式保存或拖动语义顺序才持久化。
23. **当列表处于计算排序时禁止用拖拽伪装结构编辑。** 用户需先回到“知识结构顺序”，再重排 Topic / Placement。
24. **Grouping 是显示方式，不是 Group / Topic。** 按状态、kind、地区、时间或来源分组不会创建知识群、Topic、Placement 或 Relation。
25. **Filter 只改变当前可见集合，不修改对象。** 清除 filter 后所有合法对象恢复；`0 items`必须说明是目录为空还是被筛选隐藏。
26. **Layout 不改变对象或排序 truth。** Outline、List、Table、Cards 与 Timeline 只是显示；Graph 属于 Library Network view，不能作为 Groups catalog 的装饰性布局按钮。
27. **不是每种 Scope 都提供所有 Layout。** Group hierarchy 默认 Outline；All Knowledge 默认 List；Table 用于比较；Cards 只在可读预览有价值时；Timeline 只有真实日期语义时出现。
28. **Library Row 先帮助识别，不把对象变成 KPI 卡。** 默认显示标题、orientation、位置、状态和必要的 applicability / support；计数、百分比和技术字段渐进披露。
29. **Topic Row 与 Node Row 使用不同动作语义。** Topic 的 rename / reorder / indent 改结构；Node Row 的打开 / add placement / remove placement / edit content 改不同对象。
30. **当前 Selection 同时保存 identity 与 placement context。** 从 Group 打开 Node 时，用户知道自己在该 Group 的哪个 Topic；从 All Knowledge 打开时可以选择或推断 display placement，但不能伪造唯一归属。
31. **Auto-reveal 只展开到当前合法 Placement。** 它帮助保持方向，不在多 Placement 中随机选择，也不因当前 View filter 隐藏而修改结构。
32. **Library Back 必须恢复浏览现场。** Scope、View、filters、sort、group、layout、tree expansion、scroll、selected identity 与 placement context 都要恢复。
33. **切换 View 不等于导航到另一个知识世界。** Selection identity 尽量保持；若当前对象不符合新 criteria，明确显示“当前选择不在此视图”而不是静默改选。
34. **View 的即时调整与保存修改分开。** 用户可临时 filter / sort；只有“保存到这个视图”才更新 View Definition，“另存为视图”创建新 View identity。
35. **删除 View、Pin、Recent record 或 Saved Path 不删除知识。** 删除动作必须在执行前说明只移除观察方式、快捷入口、历史记录或路径。
36. **多选动作必须显示作用单位。** Identity selection 可 Archive / Add Placement / Create Relation；Placement selection 默认只 Move / Remove / Reorder current locations。
37. **跨 Topic 拖动默认移动当前 Placement，不移动 canonical Node。** Drop preview 明确 source / destination，并提供“在两处都保留”作为显式替代，不依赖隐藏 modifier key。
38. **把对象加入另一个 Group 创建新 Placement，不复制 Node。** 如果目标已存在 Placement，系统聚焦现有位置，不生成重复 row。
39. **移除最后一个 Placement 不删除 Node。** Node 满足 Unplaced View 的派生条件并继续可在 All Knowledge / Unplaced View 找回；它是否已有 Current Revision、Explicit Draft / Recovery、是否 Archived / Trashed 仍是不同事实。
40. **Library 的空状态按真实原因分开。** Empty Space、Empty Group、Empty Topic、Empty View、Filtered Empty、Unplaced Empty、Archived Empty 与 Offline Partial 不共享一个“还没有内容”。
41. **Library 核心浏览必须完全本地、离线可用。** Group / Topic tree、All Knowledge、Saved Views、Pins、Recent、Selection 与历史不依赖 AI 或网络。
42. **View Evaluation 与 canonical store 分开。** View 规则损坏、Definition migration、索引 partial 或属性缺失不能删除对象；结果不完整时显示 coverage，并允许回到稳定目录。
43. **Library State 是可恢复工作状态，不是知识本体。** 当前 View、展开节点、列宽、scroll 与 Selection 可跨重启恢复，但不进入 Overview、Graph 或 Ask facts。
44. **完整导出必须保留 Group / Topic / Placement 结构、View Definitions、Saved Paths 与 Pins 的可选用户界面状态。** 可读 Markdown fallback 不应把 View 结果写成静态 membership。
45. **100 Groups、10,000 Nodes 与深层 Topics 时仍优先保持方向感。** 使用稳定树、分段加载、虚拟化、焦点路径和可选折叠，不靠缩小字号或无限层级缩进。
46. **Library 必须支持键盘、屏幕阅读器、200% zoom 与中文输入。** 类型、位置、状态、展开、Selection 和动作后果不能只靠颜色、hover 或拖拽。
47. **Library 质量不以点击、停留、Pins、Views 或整理完成率衡量。** 正确对象发现、结构方向、身份 / 位置理解、返回恢复与无损组织才是成功。
48. **本合同不授权开始原型或视觉实现。** 产品定义确认前，不用一个漂亮三栏目录掩盖 identity、placement、view、selection 与删除后果尚未解决的问题。
49. **Group Boundary 不是 Library membership query。** Boundary 解释范围意图；Library 根据 active Placements 显示当前内容，根据 View criteria 显示动态观察，三者可以暂时不一致。
50. **Group root 是一等 Placement target。** 跨主题或尚未细分的 Knowledge 可以直接放在 Group root；它不等于 Unplaced，也不要求系统创建占位 Topic。
51. **Topic direct / descendant 只改变浏览求值。** 展开后代不创建 ancestor mirror Placements；identity catalog 仍去重，placement browser 保留每条 exact path。
52. **Topic transform 不是普通 Row 拖拽。** rename / move 可在同 Group 结构编辑中完成；merge / split / cross-group transfer 进入 impact-aware Change Set，覆盖 Placements、Attachments、Paths、Overview 与 redirects。
53. **Boundary tension 不变成 Library 债务。** 内容暂时超出 current Boundary 时可以用 example / bridge / reference / needs relocation 解释；不得自动移入 Unplaced、隐藏结果或生成红点。
54. **View / Search 转 Group 是一次显式快照，不是规则继承。** 用户必须选择当前 identities；future matches 不自动加入，View Definition 与新 Group 分别保持 identity。
55. **Group catalog 不新增 Shelf / Collection。** 100+ Groups 使用 Pins、Saved Group Views、Search、manual order 与稳定 filters 定位；命名分区只有在真实规模测试证明必要时，才可作为不改变 Boundary / Placement 的 presentation layout 候选。
56. **普通启动恢复 Library state，不自动恢复深层 Reading。** mode、catalog scope、filter、selection hint 与 scroll 可恢复；Reading target 只有显式`继续`才恢复。
57. **Resume 最多一条且必须安全、可解释。** 没有 meaningful safe checkpoint 时整块消失；不以 Recent、点击频率、AI relevance 或内容重要性填充。
58. **普通 Group open 与 Continue 的后果固定不同。** Group row 进入 canonical Overview；Continue 恢复 exact target、Anchor、scroll、Relation Companion 与允许恢复的 Ask branch。
59. **First use、new window 与 unsafe restore 都以 Stable Library 为落点。** 新窗口不复制 live scene；不安全编辑、AI run、高影响 Decision 或失效权限只恢复最近安全阅读态并提供 repair。
60. **Resume、Recent、Pin 与 Saved Path 不合并。** Resume 是单一现场，Recent 是访问记录，Pin 是用户快捷入口，Saved Path 是长期路线；四者不共享排序真相，也不重排 Group catalog。
61. **Topic disclosure 与 Topic Open 分权。** Disclosure triangle / keyboard expand 只改变 tree expansion；Topic label / Enter / explicit Open 才进入 Topic Reading，并写可返回现场。
62. **Knowledge row 与 deep result 不经过 Topic landing。** 点击 Placement Row、Search / Ask / Relation 的 exact target 直接打开 Knowledge / Anchor，同时保留 origin Placement 与完整 DepthTrail。
63. **Topic landing 默认先看 direct children。** Descendant rollup 是显式 View State；single-child Topic 不自动 redirect，flatten 只能通过可拒绝的 impact-aware Change Set。
64. **F1 / F10 / F100 / F10K 只是验收夹具。** 数量跨档不改变 Library 名称、导航、默认排序、对象语义、打开行为与返回逻辑，用户不会进入“小型 / 大型知识库模式”。
65. **All Groups 在所有规模都保持穷尽。** Pins、Search、Views、Recent 与 Network 只能加速进入，不能成为看见全部 active / dormant Groups 的唯一方式。
66. **Library 首屏的注意力顺序固定。** 最多一条 Resume 之后是紧凑 Pins，All Groups catalog 拥有页面主体；Recent 是明确命名的次级 View，不是默认 feed。
67. **大规模 Network 先获得 Anchor，再绘制局部关系。** 超出可理解预算时先显示 Scope Summary 与穷尽 List Equivalent，要求用户用 Group、Search、Facet、Saved View 或 Path 定位；禁止按度数、最近使用或 AI relevance 任意截取 Top N。
68. **宽泛 Ask 的覆盖不靠样本冒充全库。** 当问题请求整个 Library，Groups 是覆盖单位；回答必须说明已覆盖、未覆盖、被排除与索引不可用的 Groups，再综合实际 Used Knowledge。

---

# 1. 当前规格中的十四个结构缺口

## 1.1 Library 只有页面区域，没有产品承诺

现有规格写了左侧 Groups / Pinned Topics / Saved Paths，主区可切 Group list / Hierarchy browser / Overview / Unplaced list，但没有说明 Library 是穷尽目录、快捷入口还是推荐入口。没有承诺，任何卡片列表都能被叫作 Library。

## 1.2 “全部知识”没有定义结果单位

一个跨两个 Groups 的 Node，在 All Knowledge 中应该出现一次还是两次？若不区分 identity catalog 与 placement browser，产品会在不同页面给用户不同对象数量。

## 1.3 Group Tree 的 Node Row 是知识还是位置不清楚

在 Topic 下看到的 Row 实际代表 `Placement → Node`。如果 UI 把它当 Node 本身，拖动、删除或改名就容易误伤 canonical content；如果只当快捷方式，又会失去正文状态与身份。

## 1.4 View 的规则、结果与呈现混成一个东西

旧规格说 View 是筛选、排序、聚合或布局，但没有冻结 View Definition、一次 Evaluation 与当前可见结果。结果随知识变化后，历史和编辑语义无法解释。

## 1.5 动态集合与人工精选没有对应边界

“法国、学生、当前有效”是规则；“我推荐给朋友的五条知识”是人工判断；“按这个顺序学习”是路径。若都叫收藏夹，用户不知道新增内容会不会自动进入、顺序有没有意义、删除集合会不会删内容。

## 1.6 Pin / Favorite 可能被误当重要性

固定在侧边栏只是访问便利。如果 Pin 同时影响 Ask、Overview 或 Library Network 显著性，个人界面偏好会污染知识显著性。

## 1.7 Recent 的事件语义不清楚

最近打开、最近编辑、最近导入、最近形成和最近受影响并不是同一件事。一个统一 Recent 会把工作记忆、内容变化和知识维护混在一起。

## 1.8 临时 Sort 是否改结构未知

用户在 Topic 中按更新时间排序后拖动一个 Node，如果系统把当前视觉位置写回 semantic order，会悄悄重写群结构。

## 1.9 Grouping 可能再造 Subgroup

按状态或地区分组的 section 看起来像层级。如果产品允许拖入这些 section 并保存 membership，就会以 View 分组重新引入已被删除的 Subgroup 真相。

## 1.10 多选的作用单位不清楚

在 Placement Browser 选中三行，Archive 是归档三个 Nodes，还是只从当前 Topics 移除三个位置？批量动作必须先说明选择的是 identities 还是 locations。

## 1.11 当前对象在切 View 后如何保持未知

如果选择 Node 后切到一个不包含它的 View，系统可能静默改选第一行、清空阅读区或把对象强行塞入结果。三种都会破坏空间连续性。

## 1.12 Library 与 supporting utilities 容易功能膨胀

若 Library 为了“完整”列出 Sources、Relations、Proposal、Trash、索引任务和每个内部对象，就会成为通用后台，而不是日常知识目录。

## 1.13 空状态仍可能被当作整理任务

Unplaced、Unfinished、Empty Topic 和 View no match 都可能合法。如果统一放进待处理队列或红点，产品会把低摩擦记录重新变成维护债务。

## 1.14 大规模与恢复只停留在口号

100 Groups、10,000 Nodes 和五层 Topics 下，树展开、返回位置、选中对象、过滤与重启恢复没有合同；小型 Demo 的三栏布局无法证明长期知识资产可浏览。

---

# 2. 产品目标与非目标

## 2.1 产品目标

Library 必须同时做到：

1. 用户不搜索也能从宏观 Group 进入 Topic、Node 与细节；
2. 用户能随时查看全部 Node identities，不被结构位置藏住；
3. 多 Placement 不制造副本，同名对象不被错误合并；
4. 结构顺序、临时排序、显示分组与动态筛选各自可预测；
5. Pins、Recent、Views、Paths 与 Snapshots 的长期后果不同；
6. Unplaced、Unfinished、Archived 与空 View 合法存在，不形成压力型 Inbox；
7. 打开、切 View、深入和返回始终保持 identity / placement / scroll 上下文；
8. 批量组织不越过 Node、Placement、Topic 和 Group 的动作边界；
9. 离线、索引不完整和大规模下仍可浏览；
10. Library 是唯一主地点；Groups / Network、Resume、Search、Sources 与 Knowledge Decision 的责任清楚，不形成第二知识世界。

## 2.2 非目标

- 不做文件系统式万能 Folder Explorer；
- 不要求用户先设计数据库 schema 才能浏览；
- 不把所有知识强迫进表格、Kanban 或 Calendar；
- 不提供第二套 Manual Collection 与 Group 竞争；
- 不把最近、固定或打开次数解释为知识质量；
- 不把 View 分组写回 Group / Topic；
- 不把 Unplaced 或 Unfinished 变成必须清空的 Inbox；
- 不把 Sources、Relations、Knowledge Decision items 和 Trash 全塞进 Library 主目录；
- 不让 AI 自动重排用户认可的知识结构；
- 不因本合同开始原型、布局实现或视觉皮肤设计。

---

# 3. 一个主地点、两种观察与六种组织机制

## 3.1 Library 与支撑能力的真相边界

| 位置 / 能力 | 核心问题 | 默认结果单位 | 是否穷尽 | 不承担 |
|---|---|---|---:|---|
| **Library · Groups** | 我拥有哪些知识范围、层级和对象 | Group / Placement / identity | 是，在所选目录范围内 | 正式关系全景、原始来源后台 |
| **Library · Network** | 已成立的知识群怎样相连 | Group / Group Relation | 按关系预算 | 全文目录、相似度推荐墙 |
| **Library · Resume** | 我刚才在理解什么，怎样安全继续 | ResumePoint / contextual entry | 否 | 第二套 Home、重要性排名 |
| **Search action** | 我怎样精确找回对象或位置 | Search result + placement context | 在 Effective Scope 内 | membership、知识结论 |
| **Sources utility** | 原始材料、解析、版本和 locator 怎样 | Source / Evidence locator | 是 | Knowledge membership |
| **Knowledge Decision utility** | 哪些高影响变化现在需要我判断 | Proposal / Change Set | 在 contextual criteria 内 | 普通 Working content、新来源 Inbox |

Ask、Search、Add 是全局动作，不是一级目的地。Explore 贯穿 Library 的层级阅读与 Network 观察；Sources 和 Knowledge Decision 只在需要时从当前对象或 supporting navigation 进入。

## 3.2 六种组织机制

| 机制 | 回答 | 是否手工成员 | 是否动态 | 是否有顺序 | 是否创造知识范围 |
|---|---|---:|---:|---:|---:|
| Group | 哪些知识属于一个独立范围 | 通过 Placements | 否 | Topic structure 有 | 是 |
| Topic | Group 内怎样分支与阅读 | 通过 Placements | 否 | 是 | 否，继承 Group |
| View | 哪些对象符合这些规则，怎样显示 | 否 | 是 | sort / group | 否 |
| Saved Path | 我想按什么顺序探索或讲解 | 是，显式 steps | 否 | 是，核心语义 | 否 |
| Pin | 哪些入口我要快速访问 | 单个 shortcut ref | 否 | 可手工排 | 否 |
| Snapshot | 当时这一批对象是什么 | 固定 refs + revisions | 否 | 可保存 | 否，历史记录 |

## 3.3 为什么不增加 Manual Collection

成熟工具常把手工 Collection 与动态 Query 分开，这个区别是真实需要。但在本产品中再增加一个通用 Collection 会和既有机制重叠：

- 若集合有独立主题边界，它应是 Group；
- 若只是群内分支，它应是 Topic；
- 若是规则筛选，它应是 View；
- 若是有顺序的精选，它应是 Saved Path；
- 若只是常用入口，它应是 Pin；
- 若要保留当时成员，它应是 Snapshot。

因此产品保留“人工判断 vs 动态规则”的能力差异，却不新增与现有机制重复的 Primary Resource。

Scope curation 也不是 Manual Collection：它只给一个现有 Topic、Knowledge 或 Saved Path 增加`stable start / representative / recommended`局部角色与理由，不保存另一份 member list。Library 可以显示这些角色，但 Pin、Recent、View result 和访问频率不能创建或改变它们。

## 3.4 判断矩阵

| 用户说法 | 正确机制 | 原因 |
|---|---|---|
| “这是一个要长期维护的独立领域” | Group | 有 boundary / Overview / relations |
| “这是领域中的一条阅读分支” | Topic | 只在父 Group 中成立 |
| “显示所有法国学生当前适用知识” | View | criteria 可计算、会更新 |
| “这是我推荐的五条，按此顺序看” | Saved Path | 成员和顺序都由用户判断 |
| “把这个放到侧边栏，方便下次进” | Pin | 只改变访问入口 |
| “保留今天研究时看到的 23 条” | Snapshot | 需要冻结 revisions / coverage |
| “这条知识也属于另一个领域” | Add Placement | 同一 identity 多位置 |
| “把这几条放在一起但没有顺序” | 先问意图 | 可能是 Group boundary、facet + View 或 Path |

最后一种不能通过默认创建“新收藏夹”逃避产品判断。

## 3.5 View / Search 形成 Group 的边界

动态 View 或 Search 可以帮助用户发现一个值得长期进入的范围，但不能直接拥有这个范围。执行`建立知识群`时必须先冻结一次选择：

1. 显示当前结果数与用户实际选中数；
2. 按 Knowledge identity 去重，并展开现有 Placements；
3. 让用户说明暂定边界，或先只输入名称；
4. 对每个已有位置给出`在两处保留 / 移动当前位置 / 仅引用`；
5. 明确写出`未来符合此视图的知识不会自动加入`；
6. 接受后创建 Group + Placements，原 View / Search 保持独立。

若规则本身已经足够表达用户意图，例如“最近 30 天修改且可能过时”，产品应建议保存 View，而不是创建 Group。AI 只能把当前结果包装成可丢弃的 Group Candidate；Candidate 不进入 catalog、Network、Ask 或 Overview。

---

# 4. Library 运行与持久对象模型

Library 复用既有 Knowledge ontology；新增的是浏览运行结构，不新增顶层知识对象。

## 4.1 Library Session

```text
LibrarySession
  session_id
  entry_surface
  active_scope_ref
  active_view_ref?
  selection_state
  navigation_stack
  workspace_state_ref
  created_at
  last_active_at
```

Session 负责一次连续浏览。它可以跨 Group、All Knowledge、Saved View、Node 与 Evidence，保持 Return Stack，但不进入 Library 目录本身。

## 4.2 View Definition

```text
View
  view_id
  owner: system | user
  name
  description?
  base_scope
  result_unit: identity | placement
  criteria[]
  filters[]
  sorts[]
  grouping?
  layout
  property_visibility[]
  open_behavior
  pin_state?
  created_at
  updated_at
  revision_history
```

View 保存规则和呈现，不保存 `member_ids[]`。`result_unit` 是关键：Unplaced 与 Unfinished View 返回 identities；Group hierarchy 返回 placements；Saved Search 默认返回 identities。

## 4.3 View Evaluation

```text
ViewEvaluation
  evaluation_id
  view_ref
  view_revision_ref
  canonical_revision_snapshot
  result_refs[]
  result_unit
  coverage
  exclusions[]
  generated_at
  freshness: current | stale | refresh_available
```

Evaluation 是运行时结果，可在一次 Session 内冻结以恢复浏览状态。它不是 View identity，也不成为 Snapshot，除非用户明确执行“保存这一刻的结果”。

## 4.4 Library Workspace State

```text
LibraryWorkspaceState
  scope_ref
  view_ref
  temporary_filters[]
  temporary_sorts[]
  temporary_grouping?
  layout_override?
  tree_expansion_refs[]
  selected_identity_ref?
  selected_placement_ref?
  scroll_anchor
  column_state?
  inspector_state?
```

Workspace State 用于 Back、重启和多窗口恢复。它不修改 View Definition，除非用户显式保存当前调整。

## 4.5 Pin Record

```text
PinRecord
  pin_id
  target_ref: Group | TopicPlacement | Node | SavedPath | View
  optional_placement_ref
  label_override?
  order_key
  created_at
```

Pin 不是 Relation，不进入 Graph；不是 Node property，不影响其他设备或视图之外的知识排序；完整导出可以选择保留这种个人界面状态。

## 4.6 Access Record / Recent

```text
AccessRecord
  target_identity_ref
  placement_context_ref?
  surface
  opened_at
  last_read_anchor?
```

Recent View 从 Access Records 动态推导。Access Record 可以按 retention 清理；清理不会删除对象、阅读历史 Snapshot 或 Saved Path。

## 4.7 Result Row

```text
LibraryRow
  result_unit: identity | placement
  identity_ref
  placement_ref?
  object_kind
  orientation
  path_summary
  applicability_summary?
  lifecycle_summary?
  support_summary?
  alternate_placements[]
  open_target
```

Row 是 presentation，不是对象。Identity Row 的 `placement_ref`可以为空或为 display context；Placement Row 必须有 placement。

## 4.8 不进入长期本体的内容

- tree expansion；
- row selection；
- current sort；
- temporary filter；
- group-by sections；
- card / table layout；
- recent access；
- row counts；
- current visible subset；
- virtualized pages；
- auto-reveal state。

这些状态可以持久恢复，但不能被 Ask、Overview 或 Graph 当作知识事实。

---

# 5. Library Root 与目录边界

## 5.1 Library Root 的职责

Library Root 先提供一个稳定模式切换：

1. **Groups**：默认模式，按独立知识范围进入层级和正文；
2. **Network**：观察同一批 Groups 的 maintained current Group Relations，并保留当前 selection / filters / return state；RelationCandidate 与 History 由显式图层进入。

Groups mode 中，`全部知识群`是默认 catalog，不再把“Knowledge Groups”包装成一个需要再次打开的根文件夹。Library 还提供四个次级浏览工具，但它们不是四个同权主地点，也不是新的知识类型：

- **All Knowledge**：所有拥有 Current Revision 的 active Knowledge identities，以及按显式过滤加入的 Draft / Contested / Stale 对象；
- **Paths & Saved Answers**：用户保存的理解路线和历史回答；
- **Views**：System / User dynamic observations；
- **Archived**：显式进入的可恢复内容。

Library 顶部可出现一个克制的 **Resume** 区域，只恢复最近一个安全现场或让用户展开其他最近现场；它不改变 catalog 顺序、Overview 代表知识或 Network 显著性。

`Unplaced` 与 `Drafts` 是高价值 System Views，可以快速进入，但不并列成新的知识类型：前者只回答是否有 Placement，后者只回答是否存在 Explicit Draft / Conflict Draft；Recovery-only 内容从异常恢复入口出现。普通用户直接写作不会因尚未归类而进入 Drafts。

## 5.2 不属于 Library Root 的对象

| 对象 | 正式表面 | Library 中怎样出现 |
|---|---|---|
| Sources | Sources utility | Node support / Source link；不做完整 Registry |
| Evidence Fragments | Source Reader | 只作为 locator |
| Relations | Library Network / Inspector | Node / Group 关系摘要与“查看关系” |
| Proposals / Change Sets | contextual Knowledge Decision | 仅高影响状态提示 |
| Trash | Trash | 底部独立入口，不混入 All Knowledge |
| Query Runs | Ask History | Saved Answer 可见，普通 Run 不进目录 |
| Search Results | Search Session | 可保存为 View / Snapshot，但本身不进目录 |

## 5.3 Root 不是 Dashboard

默认不显示：

- Node / Relation / Source 总数的大号 KPI；
- “知识增长 12%”；
- AI 处理数量；
- 每日整理 streak；
- decision debt；
- 自动生成的洞察 feed；
- 无限 Recently updated 卡片；
- 图谱背景装饰。

Root 可以显示 Groups / Network 的一句 orientation、用户 Pins 和一个 Resume 现场，但不形成独立 Home feed 或情境推荐墙。

## 5.4 Root 的默认进入状态

首次进入 Library：

- 有 Groups：打开 Group catalog，并保留上次 Selection hint；
- 没有 Groups 但有 Unplaced 或 Unfinished Nodes：显示 All Knowledge 与对应动态视图，不强迫先分组或先采用；
- 完全空 Space：提供 New Group、Write Knowledge、Add Source 三条真实路径；
- 从 Node Back：恢复原目录 / View / row；
- 从导航直接进入：恢复用户上一次稳定 Library state，而不是永远回到第一项。

普通启动与从主导航进入使用同一原则：**恢复 Library catalog，不自动打开 deep Reading Workspace**。上次存在安全且有意义的 checkpoint 时，catalog 顶部出现最多一条 Resume；只有用户点击`继续`才进入该现场。

只要 Library 非空，首屏注意力顺序保持为：**最多一条 Resume → 紧凑 Pins → All Groups 完整目录 → Paths / Answers / Views / Recent / Archived 等次级入口 → 安静的 Search / Ask / Add**。不存在 Resume 或 Pins 时对应区域直接消失，Catalog 向上补位；Recent 不因数量增长、活跃度或 AI 判断成为首页主体。

| 状态 | 稳定落点 | Resume / repair |
|---|---|---|
| ordinary launch + safe checkpoint | last stable Groups / Network catalog state | 一条 Resume，说明 Group、target、位置、last-safe time 与两种动作 |
| knowledge exists + no checkpoint | stable Groups catalog | Resume 消失 |
| empty | Empty Library | New Group / Write Knowledge / Add Source |
| new window | independent Stable Library state | 可显示全局最近 safe Resume，不复制 live scene |
| needs_repair | Stable Library 或 nearest safe reading fallback | 显示原现场为何不能直接恢复与明确 repair |
| archived / deleted target | Stable Library 或 nearest explainable owner | 使用 redirect / historical destination，不猜相似对象 |
| AI / index offline | local Library catalog | local Resume 可用，AI-dependent suggestions 隐藏 |

Resume card 固定包含：`继续`、Group、Knowledge / Topic、上次位置的一句话、last-safe time、可选 Path step，以及`从群概览进入`。除 Saved Path 的明确 step 外不显示完成比例。页面默认只突出一个全局最近安全现场；其他最近位置按需展开，不形成多卡片 feed。

## 5.5 根目录的稳定顺序

Groups / Network 的主模式顺序和次级浏览工具层级由产品语义固定，不按活跃度变化。Pins 是独立快捷区域；Groups catalog 默认按 locale-aware title 稳定排序，并允许用户显式保存 Manual Order、Created、Updated 等 Catalog View。最近活跃 Group 属于 Resume / Recent View，不静默重排 Library Root；Paused Group 仍留在目录、Search 与 Ask，只有显式 Archive 才离开 current catalog。

## 5.6 多 Space

默认只有一个个人 Knowledge Space。若用户因硬隔离创建额外 Space：

- 每个 Space 有独立 Library Root；
- All Knowledge 只含当前 Space；
- 跨 Space 不共享 Placement；
- View 的 base scope 不能暗中跨 Space；
- Pin 显示目标 Space；
- Space switch 保留各自 Library Workspace State。

---

# 6. Group / Topic Hierarchy Browser

## 6.1 Result Unit = Placement

Hierarchy Browser 中：

```text
Group
  Topic
    Topic
      Placement → Node
      Placement → Node
```

Topic 是结构 identity；Node Row 是 Placement。Row 打开 canonical Node，但 Selection 同时保留当前 Placement context。

## 6.2 Group Browser 的固定区域

一个 Group 默认提供：

1. Group Orientation / canonical Overview 入口；
2. Topic Tree / Outline；
3. 当前 Topic 的 Placement Rows；
4. 当前选择的短 Context Rail；
5. Group 内 Views / Saved Paths 的可选入口；
6. Group Boundary 与 Relations 的渐进入口。

它不是左树 + 右数据库的强制三栏。区域可以折叠或在窄屏切换，但语义保持。

### 6.2.1 Topic Row 的命中区域与键盘语义

| 操作 | 后果 |
|---|---|
| disclosure triangle / `ArrowRight` | 展开 direct children；Primary Reading、ReturnStack 与 Trail 不变 |
| row focus | 只移动 focus；Selection 是否跟随由当前 browser mode 明示 |
| Inspect / Preview | 显示 Bare / Compact preview；不写导航历史 |
| Topic label click / `Enter` | Open Topic Reading 顶部的局部开场；保存 caller 与 tree state |
| Knowledge Placement Row click / `Enter` | 直接 Open canonical Knowledge，并携带 current Placement context |
| `Up` from Knowledge | 进入结构父 Topic；不等于 Back |
| `Back` | 恢复 caller、expansion、selection 与 scroll |

Topic Open 默认展示 direct child Topics 与 direct Knowledge。`包含子主题`会在同一 Topic Scope 中切换 descendant rollup，并保持 exact paths；它不创建 mirror Placements，也不把所有后代自动塞进 P0。Single-child Topic 仍可打开自己的 Bare / Compact 局部开场，不自动把 URL 或 History 改写到 child。

## 6.3 Topic 直接父级

Topic 只保存同一 Group 内的一个直接 parent。Hierarchy Browser 的 children、ancestors、breadcrumb 与 descendant count 均由直接 parent 推导。不得同时维护 `parent_id`、`children_ids[]` 和独立树缓存作为可编辑真相。

## 6.4 Topic 顺序

Topic sibling order 是 Group 的编辑性结构，默认使用 `semantic_order_key`：

- 用户拖动或键盘移动可修改；
- AI 只能提出 Structure Change；
- Sort by title / updated 是 View override；
- Filter 不改变 order key；
- Split / Merge / Promotion 进入结构 Change Set；
- 历史版本可还原。

## 6.5 Placement 顺序

同一 Topic 下的 Node Placements 可以拥有 `placement_order_key`，表达阅读或概念顺序。规则：

- 只在 `知识结构顺序`中允许直接 reorder；
- 按 updated / title 排序时隐藏或禁用 drag handle，并解释原因；
- 同一 Node 在另一 Topic 的 Placement 有独立 order key；
- 调整 order 不修改 Node content；
- 删除 Topic 前，Placements 的迁移 / unplaced 后果可预览。

### Group root Placement

Group root 与 Topic 并列作为合法 Placement target：

- 用于跨主题、尚未需要细分或本身承担群级作用的 Knowledge；
- 在 Group Browser 中以`直接放在这个知识群`单列，不伪装成 Topic；
- root Placement 计入 active placement count，因此不进入 Unplaced；
- 从 root 移到 Topic 只改变当前 Placement target，不改 Knowledge identity / content；
- 删除最后一个 root Placement 后，只有没有其他 active Placements 时才进入 Unplaced。

## 6.6 Parent Topic 是否显示 descendants

默认 Parent Topic 只显示直接 child Topics 与直接 Placements。用户可显式 `同时显示下级主题中的知识`，此时：

- result unit 仍是 Placement；
- descendant rows 显示完整相对路径；
- 同一 Node 在多个 descendant Topics 出现可显示多条 Placement Rows，但标明 `同一条知识`；
- count 区分 direct / including descendants；
- 开关属于 View State，不改 membership。

## 6.7 Auto-reveal Current

从 Search、Ask、Recent 或 deep link 打开一个 Node 后，Hierarchy Browser 可以：

- 使用 origin Placement；
- 展开其 ancestor Topics；
- 滚动并高亮对应 Row；
- 多 Placement 且无 origin 时先选择当前 Group 内最相关位置；
- 无可确定位置时打开 Node，并在 Placements Rail 提供位置选择；
- 不随机展开所有 Placements。

## 6.8 Topic / Placement 的空状态

- Empty Group：可写 Node、建 Topic、Add Source；
- Empty Topic：说明这是合法结构，可写知识或移动现有知识；
- Filtered Empty Topic：显示 `当前筛选隐藏了此主题中的内容`；
- Direct empty but descendants non-empty：显示 child Topics，不宣称整个 Topic 空；
- Offline partial：保留 cached tree，说明未同步内容范围；
- Archived Topic：只读显示其历史 Placements 与恢复动作。

---

# 7. All Knowledge Identity Catalog

## 7.1 All Knowledge 到底包含什么

默认包含当前 Space 的 Node identities：

- 有 Current Revision；
- Explicit Draft 通过 Draft filter / View 可见；Recovery-only 内容不作为 Node row；
- Contested；
- Stale；
- Superseded 只有显式开启；
- Archived 只有显式进入 Archived；
- Trash 不包含；
- Historical revisions 不作为独立 identities。

Groups、Topics、Paths、Saved Answers 与 Views 有各自目录，不与 Nodes 混成一个“All Objects”结果墙。P3 可以提供 forensic object registry，但不是日常 Library。

## 7.2 Identity 只出现一次

All Knowledge 默认按 `identity`返回：

- 多 Placements 显示 `出现在 3 个位置`；
- 展开列出 paths；
- 未放置显示 `未归入知识群`；
- Group filter 通过 Placements 判断，但结果仍只有一条 identity；
- 同名不同 identity 各自出现；
- Merge redirect 不作为第二行。

## 7.3 Default Row

```text
[Knowledge kind / status when needed]
Title
One-sentence orientation
Primary display path · +2 other locations
Applicability / freshness / support summary when decision-relevant
Updated time only as metadata, not importance
```

默认不显示：Node ID、Block count、embedding score、token count、每个 Source icon、所有关系 chips 或大面积封面。

## 7.4 Display Placement

All Knowledge identity row 需要一个 display context：

1. 若从 Group filter 进入，使用该 Group 内 Placement；
2. 若有上一次使用的合法 Placement，优先恢复；
3. 若只有一个 active Placement，使用它；
4. 若有多个且无上下文，显示中性路径摘要，让用户选择；
5. 若无 Placement，打开 canonical Node 并标明 unplaced。

Display Placement 不写回 primary membership，也不暗中创建“主文件夹”。

## 7.5 同名消歧

至少使用两项可判断信息：

- orientation / definition；
- Knowledge kind；
- Group / Topic path；
- Applicability；
- lifecycle / freshness；
- created / updated time。

同名结果不能只靠图标颜色或序号区分。

## 7.6 All Knowledge 的默认排序

默认 A–Z / 中文自然语言标题排序，提供稳定位置与可预测浏览。可切换：

- Title；
- Created；
- Updated；
- Last opened；
- Knowledge kind；
- lifecycle / freshness；
- Applicability facet；
- User-defined Manual View。

`Last opened`与`Updated`必须写完整，不统一叫 Recent。没有 Query 时不提供 AI Relevance sort。

## 7.7 快速过滤不是 Search

All Knowledge filter 可以按 status、kind、Group、Applicability、support、freshness 和 time 缩小已知目录。输入 free text 时调用当前 View 内 Search，但显示 `在当前目录中搜索`，不暗中切全局 Search 或 Ask。

## 7.8 Unplaced 在 All Knowledge 中的地位

Unplaced 不是异常或隐藏区：

- Row 正常显示 title / orientation / status；
- Placement 字段写 `未归入知识群`；
- 可继续编辑、用显式 Working Context 询问、Add Placement、Archive 或 Trash；
- 默认不出现在 Group hierarchy；
- 不显示 overdue；
- 不因停留时间自动 Archive 或强制建议 Group。

---

# 8. Identity Row 与 Placement Row 合同

## 8.1 两种 Row 对比

| 维度 | Identity Row | Placement Row |
|---|---|---|
| 回答 | 这是什么知识 | 它在这里怎样出现 |
| 主键 | Node identity | Placement identity |
| 正文编辑 | 修改 canonical Node | 打开后仍修改 canonical Node |
| 结构动作 | Add / inspect Placements | Move / remove / reorder current Placement |
| 多位置 | 一行 + 展开 | 每个位置可有一行 |
| 默认表面 | All Knowledge / dynamic View | Group / Topic hierarchy |
| 删除键 | 不直接删除，打开 action scope | 默认只处理当前 Placement，仍需明确 |

## 8.2 Row 类型必须可感知

产品不要求用户学习 `identity row` / `placement row`，但动作语言必须暴露差异：

- `这条知识还出现在 2 个位置`；
- `只从这个主题移除`；
- `在另一个知识群中也显示`；
- `修改知识内容（所有位置都会更新）`；
- `移动当前位置`。

## 8.3 Row Selection State

```text
SelectionState
  selected_identity_ref
  selected_placement_ref?
  selected_row_unit
  selected_scope_ref
  origin_view_ref
  reading_anchor?
```

同一个 Node 在 identity View 与 placement View 之间切换，identity 保持；placement 只在合法且有意义时继承。

## 8.4 Row 状态

支持：

- default；
- hovered；
- focused；
- selected；
- multi-selected；
- current-open；
- working-only；
- accepted-with-unfinished-changes；
- contested；
- stale；
- archived-readonly；
- target-unavailable；
- action-pending。

状态不只靠颜色。`current-open`与`selected`可以相同或不同，例如用户多选后阅读其中一条。

## 8.5 Inline actions 预算

默认 Row 最多一个主打开动作和一个 `更多`入口。Hover 不成为唯一发现方式。高频安全动作可在 focus 后出现：

- Pin / Unpin；
- Open in reading pane；
- View placements；
- Copy deep link。

结构或生命周期动作进入明确菜单 / action sheet，不在 Row 上铺满图标。

## 8.6 Row 与阅读面板

打开 Row 可根据 View Definition 使用：

- Reading pane：保留目录可操作；
- Full reading：进入深度阅读；
- Inspect only：对比属性时保持 Table；

无论表现形式，Navigation Stack 保存原 Row 和 View State；pane / full page 不创建不同内容身份。

## 8.7 Row 更新

Node 内容变化后：

- 所有 Placement Rows 读取同一新 revision；
- View criteria 可能在 Refresh 后重新求值；
- 当前 Evaluation 不静默移除正在阅读 Row；
- 标记 `内容已更新，刷新目录`；
- Placement label / contextual note 的变化只更新对应 Row；
- Saved Snapshot 仍保留旧 revision。

---

# 9. View System：动态观察，不制造归属

## 9.1 View 的三层结构

```text
View Definition
  what rules and presentation should persist

View Evaluation
  which identities or placements match now

Workspace State
  what temporary adjustments and position the user has now
```

三者分开后，用户临时改 Sort 不会改 View；知识变化导致结果更新也不会改 Definition；Back 又能恢复当时 Evaluation 与 Workspace State。

## 9.2 System Views

系统提供少量高价值 View Definitions：

| View | Base scope | Result unit | 默认 criteria | 用户心智 |
|---|---|---|---|---|
| All Knowledge | Current Space Nodes | identity | object lifecycle = active；包含 current Knowledge，并可标出显式 Draft / conflict branch | 我拥有的全部知识身份 |
| Unplaced | Current Space Nodes | identity | active Placement count = 0 | 尚未放入知识群的对象 |
| Unfinished | Current Space Nodes | identity | explicit Draft / conflict / recovery Branch 存在且与 current 不同 | 尚未完成的草稿、冲突或恢复内容 |
| Recently Opened | Access Records | identity | opened_at within window | 我刚看过什么 |
| Recently Updated | Current Space Nodes | identity | content revision recently changed | 什么刚被修改 |
| Needs Freshness Review | Current Space Nodes | identity | freshness = review_due / stale | 哪些可能过时 |
| Contested | Current Space Nodes | identity | epistemic = contested | 哪些仍有分歧 |
| Archived | Archived Nodes / Groups | identity | lifecycle = archived | 可恢复的归档内容 |

System View 的名字、criteria contract 与安全边界由产品维护；用户可以 duplicate 为 User View 再自定义。隐藏快捷入口不删除 Definition 或对象。

## 9.3 User Views

用户可从以下状态创建 View：

- All Knowledge 的 filters / sorts；
- Group / Topic 的当前范围；
- Search criteria；
- Sources / Saved Answers 中合法的对象目录；
- 现有 View 的 duplicate；
- View editor 从空规则开始。

保存前显示一句人话：

> 显示“法国租房”中，适用于学生、当前有效、至少有一个可用来源的知识；按主题分组、标题排序。

## 9.4 View Scope

`base_scope` 可以是：

- All Knowledge identities；
- one Group placements / identities；
- one Topic placements / identities；
- Saved Answers；
- Saved Paths；
- Sources（由 Sources 表面创建和打开）；
- Archived；
- explicit system object kind registry（P3）。

View Scope 不创建 membership。以 Group 为 base_scope 时，Node 是否进入由 current active Placements 计算，并包括 Group root placements；以 Topic 为 base_scope 时必须保存 `direct_only | include_descendants`。Group Boundary、Placement membership 和 View criteria 是三种不同东西，任何一项都不能静默改写另外两项。

## 9.5 Result Unit

View 创建时或根据入口默认声明：

- `identity`：跨范围分析、All Knowledge、状态 View、Saved Search；
- `placement`：层级目录、比较同一 Node 在不同语境中的位置、结构维护。

如果用户从 placement View 切到 identity unit：

- duplicate Placements 聚合；
- Selection identity 保留；
- current Placement 作为 display context；
- count 清楚从“位置数”变为“知识数”。

反向切换时说明同一知识可能出现多行。

## 9.6 Criteria

可组合 criteria：

- object kind；
- lifecycle / epistemic / freshness / availability；
- has / lacks active Placement；
- Group / Topic membership derived from Placements；
- Applicability facets；
- created / updated / opened date；
- source support existence / role / availability；
- has Relation type；
- authored by user / AI-assisted / imported；
- text / title query；
- explicit markers such as pinned / user facet；
- current / historical revision policy。

Criteria 使用 AND / OR / NOT，但默认界面先提供可理解 filter blocks；高级逻辑渐进展开。

## 9.7 Context-aware View

View 可使用安全变量：

- Current Group；
- Current Topic；
- Current Node；
- current date / as-of；
- selected Applicability profile。

变量解析后的 Effective Criteria 在打开时可见并写入 Evaluation。历史 Snapshot 必须保存 resolved values，不能只保存 `Current Group`。

## 9.8 Dynamic Update

对象满足 criteria 时自动出现，不满足时自动离开。规则：

- 进入 / 离开 View 不等于创建 / 删除知识；
- 当前正在阅读对象不因 criteria 刚变化就突然消失；
- 显示 `这个视图有更新`并允许 Refresh；
- Refresh 产生新的 Evaluation；
- 可显示 added / removed / changed criteria reason；
- View 不发送默认通知或形成 Review item。

## 9.9 View Revision

以下操作修改 View Definition 并形成 revision：

- 改名 / 描述；
- 改 base_scope；
- 改 result_unit；
- 保存 filters / sorts / group / layout；
- 改 property visibility；
- 改 open behavior。

临时调整只有在用户选择 `保存到这个视图`后才写 revision。`另存为新视图`创建新 `view_id`。

## 9.10 View 删除

删除前固定说明：

> 这会删除“法国学生当前知识”这个观察视图，不会删除其中显示的 27 条知识，也不会改变它们所在的知识群。

若 View 被 Pin、Overview Reference、Saved Path 或 deep link 引用，显示影响并保留 redirect / unavailable state；不级联删除对象。

## 9.11 View 与 Overview

View 不拥有 canonical Overview。可以显示派生摘要：

- criteria summary；
- current result count；
- coverage；
- grouping summary；
- last evaluated time。

它们都是 Projection / presentation，不是 accepted prose。若用户需要一篇解释该集合为何重要的长期叙事，应创建 Group Overview、Saved Path Overview 或独立的综合 Knowledge。

## 9.12 Saved Search 是 View subtype

Saved Search 使用同一 View model：

```text
base_scope
text query
object filters
state / applicability filters
mode
sort / group / layout
```

Search Result Set 不是 View；只有用户保存 criteria 后才有 View identity。View 打开时重新评估，不保存原 Search ranking snapshot。

---

# 10. Pin、Recent、Saved Path 与 Snapshot

## 10.1 Pin 的产品语义

Pin 回答“我想更快进入哪里”，合法目标包括：

- Group；
- Topic Placement；
- Node，可选某个 Placement / Anchor；
- Saved Path；
- View。

Source Pin 在 Sources 表面管理；Evidence Fragment 不直接成为全局 Pin，用户可以 Pin Source locator 或创建 Saved Path step。

## 10.2 Pin 不做什么

- 不创建 Relation；
- 不创建 Group membership；
- 不改变 Overview Projection；
- 不进入 Ask 默认 Context；
- 不提升 Search factual rank；
- 不改变 lifecycle / epistemic / freshness；
- 不成为“重要知识”标签；
- 不阻止对象 Archive / Trash，但需显示 Pin 影响。

## 10.3 Pin 顺序与分组

Pins 可以手工排序，并允许少量 presentation groups，例如 `常用知识群`、`当前研究`。这些 group 只是 shortcut organization：

- 不能作为 Ask Scope；
- 不能拥有 Overview；
- 删除 group 不删除 Pins targets；
- 不显示在 Library Network；
- 导出为 optional UI state。

若 shortcut group 需要成员语义、知识边界或长期叙事，应升级为 Group / Saved Path，而不是无限扩展 Pin group。

## 10.4 Pin target 变化

| Target 变化 | Pin 行为 |
|---|---|
| Rename | 自动显示新标题，identity 不变 |
| Move Placement | Pin identity-only 时保持；placement-specific 时 redirect / choose |
| Merge | 指向 survivor，并说明原目标已合并 |
| Split | 显示 successor choices，不自动选 |
| Archive | 保留 Pin，但标记 archived，可恢复 |
| Trash | 从普通 Pins 隐藏或标 unavailable，Trash 内可恢复 |
| Permanently delete | Pin 保留 unavailable record 到用户清理，不能指向相似对象 |

## 10.5 Recent 的事件类型

必须使用完整名称：

- Recently Opened：用户看过；
- Recently Edited：用户或接受的 Change Set 改了 content；
- Recently Created：新 identity；
- Recently Added to Group：新 Placement；
- Recently Updated by Source：有 Source impact；
- Recently Re-evaluated：Saved Answer 新 Snapshot。

日常侧边栏默认只使用 Recently Opened，帮助恢复工作记忆。其他事件通过 Views / History / Knowledge Changes 查看。

## 10.6 Recent retention

- 本地、可关闭；
- 可按时间或数量保留；
- 同一 identity 聚合最近一次访问，可展开历史；
- 保存 last read Anchor / Placement context；
- 清除 Recent 不删除 reading position Snapshot、Saved Path 或知识；
- 不形成红点；
- 不因长时间未打开标记 stale。

## 10.7 Saved Path 的边界

Saved Path 保存：

```text
Path identity
title + purpose / orientation
current Path revision
ordered steps
step target refs + anchors / placements
connector kinds + optional relation / evidence refs
manual step rationale
revision basis + version history
```

Path 适合：推荐五条、学习路线、研究叙事、决策依据顺序、跨群探索。它不是动态 filter；新符合条件的对象不会自动插入。

Path identity 不保存 last position、completed / skipped steps、scroll、viewport 或当前窗口。它们属于 PathProgress / ResumePoint。Library 的 Path row 可以显示`你读到第 3 步`作为个人进度投影，但编辑路线与继续阅读使用不同动作；清除 Progress 不删除 Path，Continue 不创建 Path revision。

## 10.8 Path 与 View 的转换

View → Path：用户选择并排序一批当前结果，创建 Path Snapshot of selections；View 继续动态更新。  
Path → View：用户可基于 steps 的 properties 创建 criteria 建议，但不能保证原成员仍全部匹配。  
两种转换都创建新对象，原对象不改写。

## 10.9 Snapshot 的边界

用户选择 `保存这一刻的结果`时创建 Knowledge Snapshot：

- View Definition revision；
- Evaluation criteria；
- resolved scope / variables；
- object identity + revision refs；
- Coverage / exclusions；
- current ordering / grouping；
- captured_at。

Snapshot 是历史核验，不随当前 View 更新。打开时可比较 current state，但 Original 永不改写。

## 10.10 不提供一个含糊 Favorite 对象

产品可以使用日常动词`固定`，不默认引入 Favorite knowledge state。若用户需要：

- 快捷访问：Pin；
- 表达主观评价：User Facet / marker + View；
- 人工精选：Saved Path；
- 领域归属：Placement；
- 重要性主张：写入 Node / Overview 并有理由。

“喜欢”不能偷偷承担五种不同数据语义。

---

# 11. Filter、Sort、Group、Layout 与 Property Visibility

## 11.1 五类显示操作

| 操作 | 改变什么 | 是否改变结果成员 | 是否改变顺序 | 是否写知识 |
|---|---|---:|---:|---:|
| Filter | 可见资格 | 是，动态 | 间接 | 否 |
| Sort | 结果顺序 | 否 | 是 | 否 |
| Group | 视觉 section | 否 | section 内可 | 否 |
| Layout | 呈现形态 | 否 | 否 | 否 |
| Property visibility | 显示字段 | 否 | 否 | 否 |

## 11.2 Filter

P0 常用：

- 当前状态；
- Group / Topic；
- Knowledge kind；
- Applicability；
- 是否有来源；
- 是否已放置。

P2 / P3：

- epistemic / freshness / availability 轴；
- relation type existence；
- source evidence role；
- authorship / formation basis；
- revision / as-of；
- advanced AND / OR / NOT。

Filter chip 默认用人话：`草稿尚未成为当前知识`、`有冲突或恢复内容`、`适用于法国`、`有可用来源`、`未归入知识群`。

### 11.2.1 Typed Property 与 Value State

View criteria 引用 stable `property_id`、Definition revision compatibility 和 enum `option_id`，不保存可变字段名。Property Definition 重命名不改变 View；type / cardinality / option 变化由 Compatibility Review 决定是否可继续评估。

Property filter 默认只比较 `standing = accepted` 的 Assertions。用户显式选择包含 Working / Proposed 时，结果行与 Coverage 分层标示，不能与 current knowledge 混在一起。

五种值状态使用不同条件：

| 用户条件 | 实际语义 |
|---|---|
| 已填写 | `value_state = known` |
| 未填写 | 没有当前 Assertion / `unset` |
| 未知 | `unknown` |
| 无 | `no_value` |
| 不适用 | `not_applicable` |

`status != active` 等否定条件只返回已知且不等于目标的值，不自动纳入 unknown、unset、no value 或 N/A。Sort 缺失值时保持稳定的独立 section，不猜测 false / 0 / 最早日期。

Applicability filter 使用 overlap / contains / excludes 语义；普通 Property filter 使用 typed equality / range / contains。两者不能仅因 UI 都显示 chip 而共用真值逻辑。

## 11.3 Filtered Empty

当 base scope 有对象但 filter 后为 0：

> 当前筛选没有匹配。这个知识群里仍有 38 条知识。

提供 `清除筛选`、逐项放宽和查看 criteria；不显示 Create Group 或导入来源作为唯一动作。

## 11.4 Sort

| Sort | 合法表面 | 语义 |
|---|---|---|
| Knowledge structure order | Group / Topic placement | 用户认可的阅读 / 概念顺序 |
| Title | All identity / placement | 稳定字典序 |
| Created | identity | identity 形成时间 |
| Content updated | identity | canonical content revision |
| Placement updated | placement | 该位置变化时间 |
| Last opened | Recent / identity | 用户访问记录 |
| Applicability / status | View / Table | 属性序 |
| Manual View order | selected View | presentation order，不改 Placement |

`Updated`必须区分 content updated 与 placement updated。无 Query 时没有 relevance sort。

## 11.5 多级 Sort

View 可以保存多个 sort keys 和优先级。例如：

```text
freshness: stale first
then applicability country A–Z
then title A–Z
```

界面显示执行顺序。Sort key 缺失的对象进入 `未设置` section 或稳定末尾，不被静默排除。

## 11.6 Grouping

合法 grouping：

- Group / Topic path；
- Knowledge kind；
- lifecycle / freshness；
- Applicability facet；
- created / updated month；
- source support availability；
- user facet。

Grouping label 必须与知识群语言区分，例如 `按状态分组`而不是创建一个叫“状态”的 Group。默认最多一层主要 grouping；第二层只在 Table / forensic mode 中渐进展开，避免视觉假层级。

## 11.7 Grouping 与 multi-placement

Identity View 按 Group grouping 时，一个 multi-placement Node 有两种可选语义：

1. **Primary display group**：只出现一次，并列出其他 Groups；
2. **Repeat by placement**：切换 result unit 为 placement，可能多行，并明确 `同一条知识`。

不能在 identity mode 中偷偷重复，也不能假装存在 canonical primary Group。

## 11.8 Layout 资格

| Layout | 适合 | 不适合 |
|---|---|---|
| Outline | Topic / Placement hierarchy | 跨全库属性比较 |
| List | All Knowledge、Views、Recent | 大量字段横向比较 |
| Table | 属性比较、维护、forensic | 默认深度阅读 |
| Cards | 有 orientation / preview 的小集合 | 10,000 Nodes 主目录 |
| Timeline | 有真实 date / validity 的对象 | 只有 updated_at 的装饰时间线 |
| Reading sequence | Saved Path | 动态 View |

Graph / Map 属于 Library Network 或特定 spatial View，不能在 Groups catalog 中用同一 layout toggle 把目录变成 hairball。

## 11.9 Property visibility

每个 View 可保存可见字段。P0 List 默认只显示判断所需字段；Table 可以展开：

- object kind；
- placement paths；
- lifecycle / epistemic / freshness / availability；
- Applicability；
- source support；
- created / updated；
- authorship / origin；
- relation count（只作为导航，不代表质量）。

隐藏字段不改变 criteria 或 truth。若 filter 依赖隐藏字段，View summary 必须仍说明该条件。

## 11.10 临时调整 vs View 修改

用户在 View 中改 filter / sort 后，状态显示 `有未保存的视图调整`。动作：

- Reset；
- Save to this View；
- Save as new View；
- Keep temporary for this session。

退出时不需要阻断确认，除非用户明确编辑 View Definition；临时状态可按本地 workspace policy 恢复。

---

# 12. Selection、Open、Navigation 与 Return Stack

## 12.1 Selection 的三个维度

```text
selected identity
selected placement context
selected presentation row
```

Identity 是“我正在看什么”；Placement 是“我从哪里进入”；Row 是“当前 View 怎样呈现它”。三者不能用一个 `selected_id`混合。

## 12.2 Open behavior

View Definition 可保存：

- Reading pane；
- Full reading；
- Context preview；
- Inspector only。

用户可临时 override。打开方式不改变 URL / deep link 指向的 canonical identity 与 origin View。

## 12.3 Preserve Selection across Views

切换 View：

- 新 View 包含 selected identity：保持 Selection，选择最合法 Row；
- 新 View 不包含它：阅读面板可保持，但目录显示 `当前知识不在这个视图中`；
- 用户选择 `定位在此视图`时才清除 filter / 改 Scope；
- 不静默选择第一行；
- 不把 selected object 强制注入 View result。

## 12.4 Auto-reveal

Auto-reveal 可选。开启时：

- 在 hierarchy 中展开当前 Placement ancestors；
- 只滚动当前 View，不改变 filters；
- filter 隐藏当前 row 时显示原因；
- identity 有多个 Placements 时使用 origin context 或提示选择；
- 关闭时用户的 tree / scroll 完全保持。

## 12.5 Back / Forward

History entry 至少保存：

```text
Library scope
View revision + Evaluation
temporary filter / sort / grouping
layout
tree expansion
scroll anchor
selected identity / placement / row
reading anchor
pane state
```

Back 恢复旧现场，不重新求值。若对象已变化，旧 Row 原位显示 changed / unavailable，并提供 Refresh。

## 12.6 DepthTrail

从 Hierarchy 进入：

```text
Space / Group / Topic / Node
```

从 All Knowledge / View 进入：

```text
Library / View name / Node
```

正文仍显示可选 Placement context。DepthTrail 表达当前导航路径，不声称唯一 membership；`查看所在位置`可列出全部 active Placements。

## 12.7 Deep Link

Library deep link 可指向：

- Group / Topic；
- Node identity；
- Node + Placement；
- View Definition；
- View + selected identity；
- Saved Path step；
- Archived object。

不把一次 View Evaluation 的临时 row number 当稳定链接。需要复现当时结果时使用 Snapshot。

## 12.8 Reading position

每个 identity 可以保留 last read Anchor；每个 Placement context 可保留不同进入路径，但不能复制正文位置 truth。打开策略：

- origin deep anchor 优先；
- Saved Path step anchor 次之；
- last read anchor 可选恢复；
- 无明确目标时从 D0 / top 进入；
- Anchor changed 时使用 redirect / ambiguous / orphaned 合同。

## 12.9 Multi-window

每个窗口有独立 Library Session / Workspace State；View Definition、canonical content 与 Pins 共享。一个窗口保存 View revision 时，其他窗口提示 View updated，不静默替换当前 Evaluation。

## 12.10 Trail、Path 与 Resume

- Library 不列出原始 ExplorationTrail；只有显式保存的 SavedPath 进入稳定目录；
- 从 Path row 普通 Open 先进入 Path Overview / start orientation；`继续`才使用 PathProgress / ResumePoint；
- Back / Forward 使用当前窗口 ReturnStack；DepthTrail 仍只表达 Library / View / target 的结构位置；
- Path step changed 时 row 显示 impact summary，不自动重排步骤；
- Re-evaluate 创建 successor / draft revision，不覆盖 original；
- 多窗口可以在同一 Path 的不同 step 工作，ReturnStack / Trail cursor 隔离，canonical Path 共享。

---

# 13. Create、Drag、Multi-select 与结构编辑

## 13.1 Create 的落点

| 当前表面 | New Knowledge 默认 | 可调整 |
|---|---|---|
| Group / Topic | 创建当前 Node + 当前 Placement | title、kind、位置；可显式切换为草稿 |
| All Knowledge | 创建当前 Node | Add Placement；可显式切换为草稿 |
| Unplaced View | 创建没有 Placement 的当前 Node | 推荐但不强迫 Group；写作与归类分开 |
| Dynamic View | 若 criteria 可安全预填则显示预填说明 | 可修改；不满足时说明不会留在 View |
| Saved Path | 创建当前 Knowledge + Path step；可显式切换为 Draft | Placement 独立选择；Draft 不进入默认 Ask |
| Archived | 默认不提供普通 New | 转到 current Library |

View 中 New 不能偷偷把所有 hidden filter properties 写入对象。只有明确、可逆且用户可见的 criteria 可以预填。

## 13.2 Drag within Topic

- 只在 semantic order 下启用；
- 拖 Node Row 修改 current Placement order；
- 拖 Topic 修改 sibling order / parent；
- Drop target 显示对象类型和结果；
- 完成后支持 Undo；
- 复杂 indent / move / merge 进入 preview；
- 不修改 canonical Node content。

## 13.3 Drag across Topics

默认动作：`把当前位置从 A 移到 B`。Drop preview 提供：

- Move current Placement；
- Keep here and also add to B；
- Cancel。

如果 B 已有相同 Node Placement：

- 不创建 duplicate；
- 聚焦现有 Placement；
- 可选择移除 A；
- order key 合并规则可预览。

## 13.4 Drag across Groups

跨 Group 永远不复制 Node identity。新 Placement 继承 Node content，但需要：

- 选择 Topic 或 Group root；
- 检查 Applicability / boundary mismatch；
- 说明 contextual note；
- 预览 Overview / Group membership 影响；
- 保留 origin Placement，除非用户明确移除。

## 13.5 Multi-select Units

工具栏先显示：

> 已选择 5 条知识  
> 或  
> 已选择 5 个位置，来自 3 条知识

Identity actions：

- Add Placement；
- Add to Saved Path；
- Create Relation / Proposal；
- set Applicability / status through Change Set；
- Archive / Trash with impact。

Placement actions：

- Move selected locations；
- Remove from current Topic / Group；
- reorder contiguous selection；
- add another Placement；
- open canonical identities。

## 13.6 Bulk Filter result is not selection

`当前视图中 247 条`不等于已选择 247 条。Select all 分三层：

- Visible page / loaded rows；
- Current Evaluation；
- All matching current criteria after refresh。

高影响动作必须冻结 Evaluation / criteria、显示对象数和 exclusions，并生成 Change Set；不能让动态 View 在执行过程中改变目标。

## 13.7 Rename

- Rename Group 修改 Group identity label / boundary references；
- Rename Topic 修改当前 Group structure；
- Rename Node 修改 canonical title，所有 Placement Rows 更新；
- Rename View 只改观察方式；
- Rename Path 只改路线 identity；
- label_override on Pin 只改 shortcut display。

同一个 `Rename`菜单必须使用对象名词说明范围。

## 13.8 Remove / Archive / Trash

从 Placement Row 的 Delete key 默认不开启 destructive action，先提供：

1. 只从这个主题移除；
2. 移到另一个位置；
3. 归档这条知识；
4. 移到废纸篓。

从 Identity Row 同样不把 Delete 解释为 Remove Placement。永久删除只在 Trash，并检查全部 Placements、Relations、Evidence、Overviews、Answers、Paths 与 Pins。

## 13.9 Undo

Library 结构动作进入共享 History：

- reorder；
- move / add / remove Placement；
- Topic rename / indent / outdent；
- Pin / View / Path delete；
- Archive / restore；
- bulk actions。

Undo 说明恢复哪类对象；不能用撤销 View filter 的按钮撤销 canonical knowledge change。

---

# 14. Lifecycle、Empty、Partial 与 Failure

## 14.1 八类空状态

| 状态 | 真实含义 | 主动作 |
|---|---|---|
| Empty Space | 没有 Group、Node 或 Source | New Group / Write / Add Source |
| Empty Library with Sources | 只有原始材料，尚无 Node | Browse Sources / Write / Compile suggestion |
| Empty Group | 合法独立范围尚无 Placements | Write / Create Topic / Add Source |
| Empty Topic | 合法结构分支暂无直接 Placements | Write / Move existing knowledge |
| Empty View | 当前没有对象满足 criteria | Edit View / keep it |
| Filtered Empty | base scope 有内容，当前 filter 隐藏 | Clear / relax filter |
| Unplaced Empty | 所有 current Nodes 都有 Placement | 正常完成态，不显示 celebration |
| Archived Empty | 没有 archived objects | Back to Library |

## 14.2 Empty View 会自动变化

空动态 View 文案：

> 当前没有知识符合“法国 · 学生 · 可能过时”。这个视图会在知识条件变化时自动更新。

不建议删除 View，不显示失败，也不自动创建对象来填满它。

## 14.3 Explicit Draft、Recovery 与 Current 状态

- Explicit Draft 在 All Knowledge 的 Draft filter 和 Drafts View 可见；Recovery 只在恢复入口可见；
- 在 Group hierarchy 只有存在 Placement 时可见；
- 行上用`草稿，不用于默认回答`或`有冲突待合并`区分 Draft reason；Recovery 写`近期修改已在本机保护，尚未更新当前知识`；普通用户直接写作只显示`已更新当前知识`；
- 可继续编辑、Add Placement、确认草稿 / 合并结果、Archive、Trash；
- 不显示“未完成 7 天”；
- AI 建议 Group / Topic 只在用户进入组织动作时出现。

## 14.4 Contested / Stale

Library 显示重要的人话状态，但不把它们全部移入 Knowledge Decision：

- `有不同结论`；
- `可能需要核对时间`；
- `原来源当前无法访问`。

只有需要用户做高影响决定的 Proposal / Change Set 进入 contextual Knowledge Decision。状态 View 帮助主动浏览，不是任务队列。

## 14.5 Archived

Archived objects：

- 不在 Library 默认 Groups catalog / default Search；
- 在 Archived View 可读；
- 保留 Placements / Relations / History 的历史语义；
- Pin 标记 archived；
- View criteria 可以显式 include；
- Restore 恢复 lifecycle，但需要检查原 Placement 是否仍合法。

## 14.6 View Evaluation partial

原因：

- Index partial；
- property migration incomplete；
- Source-derived support state unavailable；
- remote sync incomplete；
- encrypted / unavailable partition；
- corrupted View rule。

正确行为：返回已知结果 + Coverage，保留 stable Library / Group tree fallback，不把 partial count 写成 complete。

## 14.7 View Rule compatibility

View 引用的 Property Definition 发生变化时分三类：

- `compatible`：rename、translation、alias 或同 ID option rename，criteria 继续按 stable IDs 工作；
- `needs_review`：type / cardinality / option split / merge 可能改变 operator 或成员，保留旧 criteria 并提供 typed mapping；
- `temporarily_partial`：Migration / index rebuild 未完成，返回已知结果 + Coverage；
- `invalid`：Definition archived 后仍可按历史 Definition 读取，但新增 evaluation 无法成立，或 reference / operator 无可解释替代。

所有情况 View identity / History 保留；其他合法条件继续评估或明确暂停；提供 map / remove / replace criterion；不自动删除条件后扩大结果。Definition Archive 不是数据删除，已有 Assertions 与旧 Evaluation 仍可解释。

## 14.8 Target unavailable

Row / Pin / Path / View selection 的 target：

- moved / renamed：identity 跟随；
- merged：redirect survivor；
- split：successor choices；
- archived：read-only / restore；
- Trash：仅 Trash 内恢复；
- permanently deleted：unavailable，不替换为相似对象；
- Source-dependent presentation missing：Node identity 仍可打开。

## 14.9 Offline

Offline 时仍可：

- browse cached canonical Group / Topic / Placement / Node；
- evaluate local Views；
- use Pins / Recent / Saved Paths；
- edit content / structure locally；
- restore Back / Selection；
- queue sync changes。

Remote-only Sources / attributes 显示 partial；AI suggestions 停止，但不影响目录。

---

# 15. Scale、Performance 与 Accessibility

## 15.1 规模夹具

```text
1 Space
100+ Groups
5 hierarchy levels in selected Groups
10,000+ Node identities
15,000+ active Placements
300+ Sources
200+ Saved Views / Paths / Answers
mixed Chinese / English titles
```

产品不能通过把 hierarchy 限制为两层或只加载示例 Group 来规避。

这些规模只用于 QA。跨过 10、100 或 10,000 的数量边界，不出现新的用户可见模式、首页、容器、默认排序或关系真相。

## 15.2 Group Catalog at scale

- 页面顺序保持 Resume → Pins → All Groups，Recent 只在次级 View；
- Pinned shortcuts 与目录分开，不改变 catalog 顺序；
- All Groups 使用 locale-aware title stable order / explicit saved order，并穷尽 active 与 dormant Groups；
- alphabet / pinyin-aware jump；
- filters by domain / lifecycle / facet；
- virtualization；
- orientation preview on selection；
- 未连接 Groups 仍合法；
- Facet / Saved View 只是观察与进入方式，不创建 Shelf、Subgroup 或新的 membership；
- 不用小尺寸 Network 星图代替目录。

## 15.3 Deep Topic Tree

- 默认只展开 focus path 与用户保存的 expansion；
- 每层缩进设最大视觉预算，深层使用 focus mode + ancestor context；
- collapse / expand all 只在安全 Scope；
- lazy load children，但 count / loading 可读；
- tree keyboard semantics；
- auto-reveal 可关闭；
- drag target 不因 virtualization 错位。

## 15.4 Large Identity List

- virtualized rows；
- stable row height 或可预测 measurement；
- selection keyed by identity，不靠 DOM index；
- sort / filter progressive；
- current Evaluation frozen during reading；
- result count 区分 exact / estimate / partial；
- loading 不先闪 empty；
- row preview 不为每条加载完整 Sources / Graph。

## 15.5 Performance budgets

验收记录目标设备上的：

- Library restore p50 / p95；
- Group tree first meaningful render；
- expand Topic；
- switch View；
- filter / sort 10,000 identities；
- open reading pane；
- Back restore；
- multi-select 1,000 targets preview；
- offline evaluation。

不在产品合同写死毫秒，但不能用 skeleton 出现时间冒充可操作完成。

## 15.6 Keyboard

至少支持：

- move focus through tree / list / groups；
- expand / collapse Topic；
- open / close reading pane；
- multi-select contiguous / non-contiguous；
- Pin；
- open actions；
- switch View；
- clear filters；
- Back / Forward；
- move Placement without drag；
- reorder Topic / Placement with keyboard；
- escape temporary mode。

中文 IME composing 时 Enter 不误触打开或 rename submit。

## 15.7 Screen reader

可读 Row 示例：

> 知识，“押金”，当前知识，法国租房 / 费用，另有一个位置，可能需要核对时间。

Placement Row：

> 位置，“押金”，位于法国租房 / 费用；这是同一条知识在此处的位置。

Tree 使用正确 level / expanded / selected 语义；grouping section 不冒充 tree branch；result counts 和 partial state 使用 live region。

## 15.8 200% zoom / narrow window

- Left Nav 可折叠但 Library scope 可访问；
- hierarchy、list、reader 在单列之间切换；
- breadcrumb / Back 保留；
- Row actions 通过 focus / menu 可达；
- Table 允许必要横向滚动，但 List fallback 可完成核心任务；
- status 不被 ellipsis 完全隐藏；
- split pane 不把正文压缩到不可读。

## 15.9 Drag alternative

所有 drag actions 都有菜单 / keyboard alternative：

- Move to Topic；
- Add another Placement；
- Reorder before / after；
- Indent / outdent；
- Pin order move up / down。

拖动不是完成结构任务的唯一途径。

---

# 16. Persistence、Offline、Export 与 Restore

## 16.1 Local-first

以下全部存于本地 canonical / local state：

- Group / Topic / Placement / Node identities；
- View Definitions；
- Saved Paths / Answers；
- Pins；
- Recent access policy / records；
- Library Workspace State；
- structure / view revisions；
- Undo history within retention。

云端同步是增强，不是浏览前提。

## 16.2 Canonical vs derived

Canonical：Group boundary、Topic parent / order、Placement、Node revision、View Definition、Saved Path。  
Derived / rebuildable：children lists、Group membership、View Evaluation、counts、recent sections、index facets、preview snippets。  
UI state：expansion、scroll、selected row、pane width。

恢复或迁移时不得把 derived cache 当唯一真相。

## 16.3 Restart restore

应用重启后：

- 恢复上次 stable Library scope / View；
- 恢复 tree expansion / scroll / Selection；
- 恢复 reading pane / anchor；
- 若 canonical revisions 改变，旧 Evaluation 显示 Refresh；
- target unavailable 时原位解释；
- 不永远跳回 Library Root 第一项。

## 16.4 Sync conflict

冲突分别处理：

- Node content conflict；
- Topic order conflict；
- Placement move conflict；
- View Definition conflict；
- Pin order conflict；
- Workspace State conflict。

内容 / 结构冲突进入可检查 merge；View / Pin / UI state 可采用设备局部或 last-writer policy，但不能覆盖 canonical knowledge。不同冲突不共享一个“同步失败”。

## 16.5 Export

完整 Knowledge Package 保留：

- Group / Topic / Placement hierarchy and order；
- Node identities / revisions；
- View Definitions and revision history；
- Saved Paths / Answers / Snapshots；
- Pins（optional personal UI layer）；
- applicability / state / provenance；
- readable fallbacks。

View export 保存 criteria，不把 current dynamic results冒充 membership；用户显式 Export Current Results 时另带 evaluation snapshot。

## 16.6 Restore

隔离恢复必须证明：

- identity count 与 refs；
- multi-placement coherence；
- Topic parent / order；
- View criteria / result unit / layout；
- Path steps；
- Pin targets；
- archived / unplaced states；
- deep links / redirects；
- current View reevaluation 与 original Snapshot 区分。

## 16.7 Reset UI State

`重置 Library 布局`只清除：

- pane sizes；
- tree expansion；
- temporary filters / sorts；
- scroll / selection restore。

默认不删除 View Definitions、Pins、Recent records、Paths 或知识。若提供更广清理，必须逐项选择并说明后果。

## 16.8 Delete all Views

即使用户删除全部 User Views：

- Groups / Topics / Placements / Nodes 不变；
- System Views 可重新生成；
- Saved Paths / Snapshots 不变；
- Pins to deleted Views 变 unavailable；
- Library 回到 Groups / All Knowledge stable fallback；
- History / Undo 按 retention 可恢复 View definitions。

---

# 17. 十六个端到端场景

## 17.1 不记得词，只记得属于哪里

用户想找“入住前检查”的知识，只记得它属于“法国租房”。他进入 Library → Group → Topic Tree，沿“入住 / 交接”打开 Node。

正确结果：没有 Query 也能完成；DepthTrail、Placement 与正文连续；返回恢复 Topic expansion 和 Row。

## 17.2 一个 Node 有三个位置

“Visale 资格”同时位于“法国租房 / 担保”“法国行政 / 补助”和“学生生活 / 入境准备”。

正确结果：All Knowledge 只显示一个 identity，写 `出现在 3 个位置`；各 Group hierarchy 分别显示 Placement Row；任何正文编辑在三处一致更新。

## 17.3 两条同名知识

两个 Nodes 都叫“押金”，一个是法国住宅租赁，一个是 SaaS 企业合同。

正确结果：All Knowledge 中两条都出现；orientation、Group path、Applicability 和 kind 足以在打开前区分；不自动 Merge。

## 17.4 快速记录形成 Unplaced Current Knowledge

用户在全局 Write 写下“退租时拍摄电表照片”，没有选择 Group。

正确结果：durable local save 后立即成为 current Knowledge，在 All Knowledge 与 Unplaced View 中可见并标记“未归入知识群”；普通直接写作不进入 Unfinished，没有红点或 overdue；用户可以继续写、直接放在 Group root 或加入 Topic，不需要二次采用。

## 17.5 临时按更新时间看 Topic

用户在一个有语义顺序的 Topic 中切换到 `按内容更新时间`。

正确结果：Placement Rows 临时重排，drag reorder 被禁用并说明原因；回到知识结构顺序后原顺序完全不变。

## 17.6 Parent Topic 同时显示 descendants

用户在“租房手续”开启“同时显示下级主题”。同一 Node 在两个下级 Topics 有 Placement。

正确结果：placement mode 显示两条 rows，并标明同一知识与各自路径；切 identity mode 后聚合成一条；count 文案随单位变化。

## 17.7 动态 View 自动变化

View“法国 · 学生 · 当前有效 · 有来源”当前 26 条。新增一条符合条件的 Node，另一条变为 Stale。

正确结果：当前 Evaluation 不在阅读中跳动；显示 View updated；Refresh 后新增和移除有解释；View Definition 不变。

## 17.8 临时调整一个 User View

用户在 Saved View 中临时加 `has unfinished changes` filter 并改为 Cards，随后切到另一 View。

正确结果：原 View Definition 没有被静默改写；返回可恢复临时状态；用户可 Reset、Save to View 或 Save as New View。

## 17.9 Pin 一个 Group 和一个 Node

用户固定“AI Agent 产品设计”Group 和其中一条常用 Node。

正确结果：侧边栏出现快捷入口；Ask、Overview、Library Network 与 Search factual rank 不因 Pin 改变；Unpin 不删除对象。

## 17.10 从 Recently Opened 恢复阅读

用户昨天从“法国租房 / 担保”阅读 Node 第四节，今天从 Recently Opened 返回。

正确结果：恢复 identity、原 Placement context 与 last read Anchor；如果 Placement 已移动，解释 redirect；不会只打开 Node 顶部或随机位置。

## 17.11 人工精选不是 View

用户从一个动态 View 选出 5 条知识，希望按“背景 → 判断 → 例外 → 行动”顺序分享。

正确结果：创建 Saved Path，保存明确 steps 和顺序；原 View 继续动态更新；新符合 View 的对象不会自动插入 Path。

## 17.12 Filtered Empty 不等于 Empty Topic

一个 Topic 有 38 条知识，用户过滤 `Contested + 2026 + 中国`后结果为 0。

正确结果：写“当前筛选没有匹配，这个主题仍有 38 条知识”；提供清除 / 放宽 filters，不显示“开始添加知识”。

## 17.13 多选 Placement Rows

用户在 Group hierarchy 选中来自三条 Nodes 的五个 Placement Rows。

正确结果：工具栏写 `5 个位置，来自 3 条知识`；默认可 Move / Remove locations；Archive Nodes 需要切换 identity scope 并预览全部影响。

## 17.14 跨 Group 组织

用户把一个 Placement 从“法国租房”拖到“法国行政”。

正确结果：Drop preview 默认是 add another Placement 或明确 move current location，由用户选择；Node identity 不复制；检查 Applicability / boundary；Undo 成立。

## 17.15 Archived 与 Definition compatibility

一个 View 依赖 property `办理状态`，该 property 被迁移；同时其中一条 Node Archived。

正确结果：View identity 保留；rename 保持 compatible，type / option change 显示 needs review，索引迁移中显示 partial coverage，不可映射才显示 invalid；不自动删除 filter、扩大结果或丢失对象；Archived Node 只在显式包括时出现。

## 17.16 大规模、离线与无障碍

设备离线，Library 有 100 Groups、10,000 Nodes、15,000 Placements、五层 Topics；用户使用键盘、屏幕阅读器和 200% zoom。

正确结果：本地目录和 Views 可用；焦点路径稳定；virtualization 不丢 Selection；类型、位置和状态可读；无需拖拽即可完成 Move Placement。

---

# 18. 质量指标与反指标

## 18.1 核心结果

Library 成功不是“用户建立了很多目录”，而是用户能够在没有 Query 的情况下找到正确知识、理解它所在的位置与身份，并安全改变组织方式而不损伤正文或其他位置。

## 18.2 核心指标

| 指标 | 定义 | 需要分层 |
|---|---|---|
| Browse-to-target success | 只用 Group / Topic browse 找到目标 identity | depth、Group size、language |
| Structural orientation | 用户能说清当前 Group / Topic / Node path | entry surface、multi-placement |
| Identity / placement comprehension | 用户能预测内容编辑与位置编辑后果 | All Knowledge / hierarchy |
| Multi-placement coherence | 同一 Node 不被误解为副本，所有位置可查 | 2+ / 5+ placements |
| Same-title disambiguation | 打开前选对同名 identity | applicability / group / kind |
| View rule comprehension | 用户能预测新对象何时进入 / 离开 View | system / user / context-aware |
| View adjustment safety | temporary change 不误写 Definition | filter / sort / layout |
| Return restoration | Back 恢复 View / tree / row / anchor | cross-surface journeys |
| Safe bulk scope | 用户能正确选择 identity vs placement action | 10 / 1,000 targets |
| Unplaced recovery | 无 Placement 的 Accepted / Working Node 都可找到并继续使用 | age、has suggestion / no suggestion |
| Offline continuity | 离线完成 browse / open / organize | local / remote attributes |
| Accessibility completion | keyboard / screen reader / 200% zoom 完成核心任务 | tree / list / table |

## 18.3 诊断指标

- duplicate identity rows in identity views；
- wrong-placement open rate；
- filtered-empty misinterpretation；
- accidental canonical action from placement view；
- View Definition unintended modification；
- invalid View recovery；
- auto-reveal wrong branch；
- tree focus loss under virtualization；
- cross-Group duplicate Placement prevention；
- Back state loss；
- system View coverage partial exposure；
- restore parity after export / import。

## 18.4 反指标

不得把以下数值作为单独成功标准：

- Group 数量；
- Topic 层级深度；
- View 数量；
- Pin 数量；
- Saved Path 数量；
- Unplaced 清零率；
- 每日整理时长；
- Library 点击次数；
- 目录停留时长；
- 最近访问占比；
- 拖拽次数；
- Cards / Table 使用率。

更多结构可能意味着混乱，更多操作可能意味着找不到。

## 18.5 评估任务

真实测试不能只用一组干净 Demo 数据。至少包含：

- 100 Groups；
- 同名 Nodes；
- multi-placement Nodes；
- Unplaced 与 Unfinished Nodes；
- deep Topics；
- Archived / Stale / Contested；
- dynamic Views；
- invalid criteria；
- mixed Chinese / English；
- source unavailable；
- offline；
- keyboard / screen reader / zoom。

---

# 19. 二十三条 Given / When / Then 验收

## 19.1 无 Query 浏览

**Given** 目标 Node 位于 Group 的三级 Topic 下  
**When** 用户只通过 Library hierarchy 查找  
**Then**：

- 无需 Search / Ask；
- Topic path 可理解；
- 打开正确 Placement + Node；
- DepthTrail 正确；
- Back 恢复 expansion / scroll / Row。

## 19.2 Multi-placement identity

**Given** 一个 Node 有三个 active Placements  
**When** 用户分别打开 All Knowledge 与三个 Group browsers  
**Then**：

- All Knowledge 一条 Identity Row；
- 三个 Group 各有 Placement Row；
- 所有 Rows 指向同一 content revision；
- 所有位置可展开；
- 不存在复制正文。

## 19.3 同名对象

**Given** 两个 Nodes 标题相同、Applicability 与 Group 不同  
**When** All Knowledge 同时显示  
**Then**：

- 两个 identities 都出现；
- orientation / path / applicability 足够消歧；
- 不按 recentness 隐藏；
- 不自动 Merge；
- 选择正确对象后位置可恢复。

## 19.4 Unplaced Current Knowledge

**Given** 用户直接创建没有 Placement 的 Knowledge  
**When** durable local save 完成后进入 Library  
**Then**：

- All Knowledge / Unplaced 可立即找到，Unfinished 不出现；
- 标记未归入知识群，但内容已经是当前知识；
- 没有红点 / overdue；
- 可继续编辑；
- Ask 按 current Knowledge policy 使用；若用户显式保存为 Draft，才进入 Unfinished 并默认不作为事实。

## 19.5 Sort 不改结构

**Given** Topic 有用户认可的 semantic order  
**When** 切换 Updated sort 并返回  
**Then**：

- 当前 View 临时重排；
- drag reorder 禁止或明确；
- semantic order keys 不变；
- Reset 恢复原序；
- 未显式保存不修改 View。

## 19.6 Descendant 与 result unit

**Given** Parent Topic 的两个 descendants 都放置同一 Node  
**When** 开启 descendants 并切 identity / placement units  
**Then**：

- placement unit 两行且显示 paths；
- identity unit 一行且列出两位置；
- count 随单位解释；
- content identity 始终相同；
- 切换不丢 Selection。

## 19.7 Dynamic View refresh

**Given** 知识变化使一个对象进入、一个对象离开 View criteria  
**When** 当前用户正在阅读旧 Evaluation  
**Then**：

- 列表不静默跳动；
- 显示 Refresh；
- 新 Evaluation 有 change summary；
- View Definition revision 不变；
- 当前对象可继续阅读。

## 19.8 Temporary View edits

**Given** User View 已保存  
**When** 用户临时改变 filter / sort / layout  
**Then**：

- 标记 unsaved view adjustments；
- 可 Reset；
- Save to View 形成 revision；
- Save as New 创建新 identity；
- 普通离开不静默覆盖。

## 19.9 Pin neutrality

**Given** 用户 Pin 一个 Node  
**When** 重新打开 Library Resume、Ask、Search、Library Network 与 Overview  
**Then**：

- shortcut 可用；
- knowledge status 不变；
- Ask scope 不自动包含；
- Library Network salience 不自动提升；
- Unpin 不删内容。

## 19.10 Recent restore

**Given** Access Record 保存 Node + Placement + Anchor  
**When** 从 Recently Opened 返回  
**Then**：

- identity 正确；
- Placement context 正确或解释 redirect；
- reading Anchor 恢复；
- clear Recent 不删知识；
- 最近打开不写成最近更新。

## 19.11 View → Path

**Given** 用户选择动态 View 中 5 条并手工排序  
**When** 保存为路线  
**Then**：

- 创建 Saved Path；
- 保存 steps / anchors / order；
- View 继续动态；
- 新 View results 不自动入 Path；
- 删除 Path 不删 Nodes。

## 19.12 Filtered Empty

**Given** base scope 有 38 条，filters 后 0 条  
**When** View 完成 evaluation  
**Then**：

- 显示 filtered empty；
- base count / coverage 可见；
- 可清除 / 放宽 filter；
- 不显示 Empty Topic 文案；
- 不自动改变 criteria。

## 19.13 Bulk unit safety

**Given** 用户选择五个 Placement Rows、对应三条 identities  
**When** 打开 bulk actions  
**Then**：

- 显示两个数量；
- 默认提供 location actions；
- Archive / Trash identities 要明确切换并预览；
- dynamic View targets 冻结；
- Undo 成立。

## 19.14 Cross-group placement

**Given** Node 已在 Group A，用户拖到 Group B  
**When** Drop  
**Then**：

- 不复制 identity；
- 显示 add vs move current Placement；
- 检查 boundary / applicability；
- 已存在 target Placement 时不重复；
- 所有影响与 Undo 可见。

## 19.15 Property Definition 变化后的 View

**Given** View 依赖的 Property Definition 被 renamed / type changed / archived  
**When** 打开 View  
**Then**：

- View identity / history 保留；
- rename 按 stable ID 继续工作；
- type change 显示 needs review 或 migration partial；
- archived / incompatible criterion 可见；
- 不自动移除后扩大结果；
- 可 map / replace / remove；
- stable Library fallback 可用。

## 19.16 Large-scale accessibility

**Given** 100 Groups、10,000 Nodes、15,000 Placements、离线和 200% zoom  
**When** 键盘 / screen reader 用户浏览、打开、移动并返回  
**Then**：

- focus / Selection 不因 virtualization 丢失；
- type / position / status 可读；
- tree depth 可理解；
- drag 有替代；
- local Views 与 Back restore 成立。

## 19.17 Group root placement

**Given** Knowledge 只 placed 到 Group root  
**When** 用户打开 Group Browser、All Knowledge 与 Unplaced View  
**Then** Group 中显示`直接放在这个知识群`，All Knowledge 只显示一个 identity，Unplaced 不返回它；移动到 Topic 只改 Placement target。

## 19.18 Topic direct / descendants

**Given** Parent Topic 没有 direct Knowledge，但 descendants 有多条 Placements，且一条 Knowledge 出现两次  
**When** 用户打开 direct 与 include-descendants 两种范围  
**Then** direct 空态不宣称整个 Topic 无内容；descendant view 显示 exact paths 与 direct / total counts；identity mode 去重、placement mode保留两行；不写 mirror Placements。

## 19.19 Topic transform 与 Boundary tension

**Given** Group Boundary 已澄清，Topic 又将 merge / split / transfer  
**When** 用户从 Library 发起操作  
**Then** Boundary revision 不自动改成员；Change Set 预览 Placement、Source Attachment、Path、Overview 与 redirect 后果；未处理 tension 可解释但不进入 Unplaced 或红点 Inbox。

## 19.20 View / Search 转 Group 不继承动态 membership

**Given** 一个 Saved View 当前匹配 31 条 Knowledge，用户选择其中 12 条建立 Group，之后又有 4 条新 Knowledge 满足 criteria  
**When** 检查 View、Group catalog、Placements 与 Library Network  
**Then** View 更新为 35 条；Group 仍只拥有接受时创建的 12 条 active Placements；没有 accepted Relation 时 Network 不生成群边；删除 View 不影响 Group，拒绝 Candidate 时两者都不创建结构副作用。

## 19.21 Library entry、Group open 与 Continue 分权

**Given** Library 同时拥有 safe Resume、Pin、Recently Opened、Saved Path、另一个窗口的 live scene 与一个 needs_repair checkpoint  
**When** 用户普通启动、打开 Group row、新开窗口、显式点击`继续`、离线重启与修复旧现场  
**Then** 普通启动和新窗口停在 Stable Library；最多一条 Resume 可预测地说明恢复后果；Group row 进入 canonical Overview；Continue 才恢复 exact scene；Pin / Recent / Path 不参与 Resume 或 catalog 排名；needs_repair 先进入安全 fallback；离线目录与本地 checkpoint 可用。

## 19.22 Topic disclosure、Open 与 direct Knowledge entry 分权

**Given** 一个展开的深层 Topic 同时有 direct child Topics、direct Knowledge、descendant rollup 与 single-child variant  
**When** 用户用 disclosure、Focus、Inspect、Topic Enter、Knowledge Enter、Up 与 Back  
**Then** disclosure / Focus / Inspect 不写主导航；Topic Enter 进入局部开场；Knowledge Enter 直达 canonical Knowledge；Up 进入父 Topic，Back 恢复 caller；descendant rollup 保留 exact paths 且不制造 Placements；single-child 不自动 redirect。

## 19.23 规模跨越不更换产品

**Given** 同一 Library 依次处于 F1、F10、F100 与 F10K，包含 dormant、unconnected、deep-topic 与 multi-placement 数据  
**When** 用户浏览全部知识群、从 Pins / Recent 返回、定位深层知识、打开 Network 并询问整个知识库  
**Then** All Groups 在每档都穷尽且稳定；Resume / Pins / Recent 不争夺目录排序；Topic hierarchy 保留 focus + ancestor context；Network 超预算先显示 Scope Summary / List 并要求 Anchor，不生成 Top N / auto regions；全库 Ask 说明 Group coverage；数量跨档不改变对象、导航、打开或返回语义。

---

# 20. 官方研究依据与产品推论

本轮使用官方资料验证成熟知识工具中真实存在的“目录、层级归属、动态视图、多位置与快捷访问”模式，不把竞品对象模型直接复制成本产品。

## 20.1 Zotero：Library Root、同一 identity 多 Collections、Unfiled 与 Saved Search

Zotero 官方文档说明：Library root 始终显示所有 items；同一 item 可以属于多个 Collections 而不产生副本；从 Collection 移除或删除 Collection 不会删除 item；Unfiled Items 是特殊集合；Saved Searches 按 criteria 自动更新。[Zotero — Collections and Tags](https://www.zotero.org/support/collections_and_tags)

产品推论：All Knowledge identity catalog、Placement browser、Unplaced View 和动态 View 必须分开；结构位置删除不能等于内容删除。本产品不复制 Zotero 的 Collection hierarchy，而使用 Group / Topic / Placement 表达自己的知识边界。

## 20.2 Capacities：人工 Collection 与动态 Query 的语义差异

Capacities 官方资料明确区分：Collection 的成员由用户人工决定，Query 保存规则并随对象条件动态更新；Queries 还可保存 filters、sort、group 和 limit。[Capacities — Query vs Collection](https://docs.capacities.io/faq/editing/queries-vs-collections) · [Capacities — Queries](https://docs.capacities.io/reference/queries)

产品推论：人工判断与规则集合绝不能共用一个模糊“收藏”。本产品已有 Group / Topic、Saved Path、Pin 与 Snapshot，因此只保留动态 View，不再增加一个竞争 membership 的 Manual Collection 对象。

## 20.3 Obsidian：一个数据基础上的多 Views 与文件定位

Obsidian Bases 官方文档允许同一 Base 拥有多个独立 views，每个 view 有自己的 layout、filters、sort、group 和 properties；File Explorer 的 auto-reveal 可以跟随并定位当前 file；Bookmarks 是通往 files、folders、graphs、searches、headings 与 blocks 的 shortcuts。[Obsidian — Bases Views](https://obsidian.md/help/bases/views) · [Obsidian — File Explorer](https://obsidian.md/help/plugins/file-explorer) · [Obsidian — Bookmarks](https://obsidian.md/help/plugins/bookmarks)

产品推论：View Definition、Selection / auto-reveal 与 Pin 必须分开。快捷入口不应变成 membership；多 View 也不能复制底层对象。

## 20.4 Notion：View-specific layout、filters、sorts、grouping 与 open behavior

Notion 官方帮助说明同一 database 可以拥有多个 views，各 View 独立保存 layout、property visibility、filter、sort、group 与页面打开方式。[Notion — Views, filters, sorts & groups](https://www.notion.com/help/views-filters-and-sorts)

产品推论：不同观察方式需要独立持久配置；但本产品不是 database-first 工具，不让所有知识默认变成表格，也不允许 View grouping 冒充 Group / Topic structure。

## 20.5 Anytype：Queries 与 Collections 的相同外观、不同成员来源

Anytype 官方 Collections 文档说明 Collection 从空集合开始，由用户手工加入不同类型 Objects；其 Sets 文档把 Set 描述为按类型或关系实时筛选 Graph 的 live query。[Anytype — Collections](https://doc.anytype.io/anytype-docs/getting-started/sets/collections) · [Anytype — Sets](https://doc.anytype.io/anytype-docs/documentation_cn/ji-chu/sets)

产品推论：视觉相似不能掩盖成员来源不同。对本产品而言，这进一步支持在动作语言中清楚区分 Placement、View criteria、Path steps 和 Pins。

## 20.6 Tana 与 Notion：Workspace、方向面和动态查询不是知识群

Tana 官方把 Workspace 定义为拥有 members、Home、schema、settings、trash、publishing / export 与 access boundaries 的顶层容器；Search Nodes 则保存查询条件并实时返回原节点 references。Notion Wiki 分开可策展 Home、穷尽 All pages 与额外 Views。[Tana Workspaces](https://outliner.tana.inc/learn/features/workspaces) · [Tana Search Nodes](https://outliner.tana.inc/learn/features/search-nodes) · [Notion Wikis](https://www.notion.com/help/wikis-and-verified-pages)

产品推论：Library 承担唯一系统与方向入口，Knowledge Group 不复制 Workspace 权限 / schema / settings，View 不拥有范围 membership，Resume 不成为第二个 Home。动态结果可以帮助发现 Group Candidate，但必须经过一次显式选择才能建立 Placements。

## 20.7 Apple、Notion 与 Tana：恢复、最近与目录是不同入口

Apple 的 Launching 指导建议保留足够细的上次状态；Notion 允许把 Home、Last visited page 或侧栏顶层页面作为默认打开页，并在导航中区分 Home / Recent / Favorites 与 Library；Tana 的 Sidebar 也把 pinned entries 与按最后编辑排序的 Recents 分开。[Apple — Launching](https://developer.apple.com/design/human-interface-guidelines/launching/) · [Notion — Home and My tasks](https://www.notion.com/help/home-and-my-tasks) · [Notion — Navigate with the sidebar](https://www.notion.com/help/navigate-with-the-sidebar) · [Tana — Sidebar](https://outliner.tana.inc/learn/features/sidebar)

产品推论：状态恢复不应夺走 catalog 主权。本产品使用一个显式 Resume 保存连续性，保持 Group catalog、Pin、Recent 与 Saved Path 的排序语义稳定；“是否自动恢复 deep scene”不交给 AI，也不在普通设置中产生多套产品行为。

## 20.8 Tana、Docusaurus 与 Apple：展开层级、打开范围与直接子项不是同一动作

Tana 允许任意 node zoom 成当前页面，同时保留 expand / collapse 与 breadcrumb；Docusaurus category 可以同时拥有介绍内容与 direct-children generated index；Apple outline / disclosure guidance区分展开 nested children 与真正选择内容。[Tana — Outline editor](https://outliner.tana.inc/learn/features/outline-editor) · [Docusaurus — Sidebar items](https://docusaurus.io/docs/sidebar/items) · [Apple — Disclosure controls](https://developer.apple.com/design/human-interface-guidelines/disclosure-controls) · [Apple — Outline views](https://developer.apple.com/design/human-interface-guidelines/outline-views)

产品推论：Topic Row 需要两个可预测后果——展开结构与打开当前 Scope；Knowledge Row 直接打开对象。视觉上可以紧凑，但键盘、屏幕阅读器与点击目标都不能把两者压成一个随机行为。

## 20.9 研究推论边界

官方资料共同证明：

- 用户需要一个能看见所有对象的稳定 root；
- 同一 identity 多位置不应复制内容；
- 结构归属、动态查询与快捷方式是不同机制；
- Views 需要独立 filters / sorts / layout；
- Unfiled / unplaced 是可浏览状态；
- 删除观察方式不应删除对象。

它们不证明本合同的 68 项决定已通过本产品真实用户测试，也不证明“不新增 Manual Collection”“单条 Resume”、稳定标题默认序或 Topic Row 的具体点击分区是唯一正确选择。前两项分别基于避免多份 membership truth 与稳定 catalog / 显式恢复分权；排序与 Topic 语义还需通过真实大库浏览、键盘与触屏任务验证是否足够可预测。

## 20.10 大集合需要稳定概览、渐进筛选与局部关系语境

Shneiderman 的信息可视化任务模型把 overview、zoom、filter、details-on-demand、relate 与 history 分成连续任务；Furnas 的 fisheye view 说明局部细节需要同时保留全局语境；Hearst 的 faceted navigation 研究说明 keyword search 与 facets 可以协作支持探索。Apple 的 Layout 指南要求在大集合无法同时容纳时保持视觉层级与渐进披露；Notion Library 将 Recents、Favorites、Search、Filters 与完整 Library 分开；Obsidian 也区分 Global Graph 与有 depth / filters 的 Local Graph。[Shneiderman — The Eyes Have It](https://drum.lib.umd.edu/items/155a868e-fb83-4115-9899-9187ea8c0498) · [Furnas — Generalized Fisheye Views](https://www.cs.columbia.edu/~feiner/courses/csw4170/resources/furnasCHI86.pdf) · [Hearst — Faceted Navigation](https://people.ischool.berkeley.edu/~hearst/papers/hcir08.pdf) · [Apple — Layout](https://developer.apple.com/design/human-interface-guidelines/layout) · [Notion — Manage your Library](https://www.notion.com/help/manage-your-library) · [Obsidian — Graph view](https://obsidian.md/help/plugins/graph)

产品推论：本产品的大规模状态必须保持“完整目录 + 当前焦点 + 可见上下文 + 按需细节”。这些资料支持能力方向，但不直接证明 stable title order、Anchor Required 阈值或 Group coverage 规则；后者仍是需要用 F1 / F10 / F100 / F10K 任务验证的产品假设。

---

# 21. 对后续视觉设计的约束

本合同不授权开始原型。未来把方向 3 的层级阅读和方向 2 的关系空间结合时，Library 设计必须证明：

1. Knowledge Library 从首屏就能被理解为唯一主地点；Groups / Network 是同义视图，Sources / Knowledge Decision 不常驻同权导航；
2. Library Root 看起来是稳定目录，不是推荐 feed 或数据 Dashboard；
3. Knowledge Groups、All Knowledge、Paths / Answers、Views 与 Archived 有清楚入口层级；
4. Unplaced 是安静的动态 View，不是红点 Inbox；
5. All Knowledge 按 identity 一次显示，Group hierarchy 按 Placement 显示；
6. 同一知识多位置有“同一条知识”语义，不像复制文件；
7. 同名不同知识在打开前可消歧；
8. Group、Topic、Node Row、View、Saved Path 与 Pin 使用不同人话动作；
9. `修改知识（所有位置更新）`与`移动当前位置`不会混淆；
10. Topic semantic order 与临时 Sort 的状态明显不同；
11. 计算排序下不能通过拖拽误改结构；
12. Grouping sections 不像新的 Subgroups；
13. Filtered Empty、Empty Topic、Empty View 与 Empty Space 有不同状态；
14. View criteria 有一句人话 summary，不先暴露 DSL；
15. Current Evaluation updated 时不在阅读中跳动；
16. 临时 View 调整、保存到当前 View、另存新 View 的后果清楚；
17. Pin 只是快捷入口，不使用“权威”“重点知识”视觉；
18. Recently Opened 与 Recently Updated 不共享一个 Recent 标签；
19. Saved Path 的顺序性与 View 的动态性在视觉上可理解；
20. Snapshot 明确是“当时结果”，不会看起来仍在实时更新；
21. 切 View 后 Selection 不符合 criteria 时仍保留阅读对象并解释；
22. Back 恢复目录、Tree、Row、Anchor 和 pane state；
23. Auto-reveal 聚焦正确 Placement，不展开所有分支；
24. 多选工具栏先显示选择单位和真实 identity 数；
25. 跨 Topic / Group drop preview 明确 Move / Keep both；
26. Archive、Remove Placement、Trash、Delete View / Path / Pin 有不同语言和影响；
27. 100 Groups 下不靠星图缩略图替代目录；
28. 10,000 Nodes 下 List / virtualization 仍保持可读密度；
29. 五层 Topic 在 focus mode 中保留 ancestors，不无限右缩进；
30. Table 是比较工具，不成为默认知识阅读表面；
31. Cards 只有在 orientation / preview 真有价值时出现；
32. Graph layout 只属于 Library Network，不在 Groups catalog 用装饰连线制造科技感；
33. 离线和 View partial 时稳定目录仍完整可用；
34. keyboard、screen reader、200% zoom 与中文 IME 可完成 browse / select / move / return；
35. 视觉方向 3 + 2 的结合最终服务“从结构进入知识，再从知识看关系”，不能让关系空间吞掉 Library 的稳定方向感。
36. View / Search 转 Group 时始终显示当前结果、实际选择、existing Placements 与`未来匹配不会自动加入`；
37. 100+ Groups 使用 Saved Group Views、Pins、Search 与 manual order，不出现第二层 Shelf / Collection / Workspace 导航。

---

# 结论

Library 真正成立，不是因为产品有一条侧边栏和几种卡片布局，而是因为用户在不搜索、不提问的情况下，依然能看见一套稳定、可穷尽、可组织、不会制造副本的知识目录。

> **知识身份只有一份，结构位置可以有多处，动态视图只负责观察，人工路线保存顺序，快捷入口只负责抵达；Library 的责任是让这些区别在日常浏览中自然成立。**

因此，Library 不是文件系统、数据库后台或推荐 feed。它是个人知识世界的唯一主地点：Groups / Topic 给出认知结构，Network 观察已成立关系，All Knowledge 保证对象不被遗漏，View 提供可复用观察，Pin / Recent / Resume 帮助快速返回，Saved Path 保留人工叙事，而所有动作最终仍服从同一套 Node identity、Placement 与历史合同。
