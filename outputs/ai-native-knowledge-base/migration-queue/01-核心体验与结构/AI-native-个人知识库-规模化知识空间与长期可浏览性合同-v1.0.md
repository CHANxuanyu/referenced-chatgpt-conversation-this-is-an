# AI-native 个人知识库

## 规模化知识空间与长期可浏览性合同 v1.0 — Scale Invariance, Focus + Context, Exhaustive Browse

> 文档日期：2026-08-09  
> 文档状态：终局产品定义合同；不是性能方案、数据库分片、页面线框、原型或研发排期  
> 上位真相源：`AI-native-个人知识库-终局产品设计文档-v4.0.md`  
> 领域责任：冻结知识库从 1 个知识群增长到 10、100+ 个知识群，以及从少量 Knowledge 增长到 10,000+ identities 时，怎样仍保持同一心智模型、穷尽浏览、当前方向、关系可读与可预测返回  
> 视觉边界：继续采用“方向 3 的层级阅读 + 方向 2 的按需关系空间”，但本文不授权制作原型
> 状态语义：规模档位不属于 Group state；Paused / Archived / Trash 与 Orientation / Change / Boundary 的完整语义遵守`AI-native-个人知识库-知识群状态演化与身份连续性合同-v1.0.md`
> 关系语义：规模档位不改变 Relation truth；Candidate、Current、History、Review、End / Supersede / Retract、Lifecycle 与 Endpoint Transition 遵守`AI-native-个人知识库-关系陈述生命周期与网络可信性合同-v1.0.md`
> 群级聚合语义：Candidate eligibility 不由 raw path count、degree、component size 或布局中心性决定；Effective Support Unit、Boundary coverage、type policy、CounterSignal、removal test 与 attention budget 遵守`AI-native-个人知识库-群级关系聚合门槛与支撑充分性合同-v1.0.md`
> 群级类型语义：规模增长不新增、合并或重新排序正式类型；十一种 Registry 类型按语义家族渐进展开。共享核心知识是按当前 identity / Placements 重算的 observation，只在 Shared Knowledge Lens 或 pair comparison 中按需显示，不改变 resting Network。完整合同见`AI-native-个人知识库-群级关系类型注册表与语义互斥合同-v1.0.md`

---

# 0. 执行决定

1. **规模增长不产生第二套产品。** 1、10、100 个 Groups 使用同一个 Knowledge Library、同一种 Group identity、同一条 Overview → Topic → Knowledge → Evidence 主干与同一套 Ask / Search / Network 语义。
2. **没有用户可见的 Small / Pro / Large mode。** 数量跨过某个阈值时，产品不能突然更换首页、导航、默认排序、对象名称或返回逻辑。
3. **规模档位只是设计与验收夹具，不是业务状态。** `F1 / F10 / F100 / F10K`帮助证明产品，不被保存到 Group lifecycle，也不向用户展示。
4. **数据容量与注意力预算分开。** Library 可以拥有无限增长的数据，但每个表面只显示当前理解所需的范围、焦点和细节；预算限制初始表达，不限制资产。
5. **所有规模下，All Groups 都必须穷尽。** Search、AI、Pins、Recent 或 Network 都不能成为看见全部知识群的唯一方式。
6. **All Groups 的默认顺序必须稳定、可预测。** 默认按语言感知的标题排序；用户可以显式切换并保存自己的 Catalog View，但 Recent、点击频率、AI relevance、关系度数或“活跃度”不静默重排。
7. **Resume、Pins 与 Catalog 各守责任。** Resume 最多一条；Pins 是用户选择的快捷入口；All Groups 是完整目录。Recent 是次级 View，不在默认首页与 Pins 竞争主权。
8. **规模越大，越不能把目录变成推荐 Feed。** 产品不会用“你可能想看”“最重要”“最活跃”替代稳定范围，也不会因为 Paused 而隐藏 Group。
9. **知识群数量增长不重新引入 Shelf、Folder、Subgroup 或 Workspace。** 顶层组织使用 Group Facets、Saved Group Views、Pins 与正式 Group Relations；这些机制不制造新的 membership truth。
10. **Group Facet 是观察维度，不是父容器。** 一个 Group 可以同时属于多个可筛维度，但它的 Boundary、Overview、Relations 与 identity 不因筛选而改变。
11. **大规模 Network 必须先有有效 Scope 或 Anchor。** 当当前网络范围超过可理解预算时，产品不能任意抽取一部分、按度数展示“核心”、或把全部标签缩小；应让用户选择 Group、Saved View、Facet、Search result 或已有 Path 作为焦点。
12. **Network Overview 可以是可读 Scope Summary，不必是一张全图。** “Overview first”不等于“把所有节点同时画出来”。
13. **自动聚类不是正式知识结构。** 关系模式、embedding 或使用共现形成的 cluster 只能作为可清除的 Query / Suggestion overlay；不创建 Group region、Subgroup、Relation 或 Catalog section。
14. **被选 Group 是 Network 的唯一焦点。** 初始显示它与少量 Accepted neighbours；二跳、其他 relation families 和 unconnected Groups 按明确动作展开。
15. **Network 过滤不会改变关系真相。** Filter、Group View、relation family、direction 和 time 只决定当前可见集合；清除后恢复正式 Network state。
16. **所有图状态都有 List Equivalent。** 图、列表、键盘、屏幕阅读器和 mobile 使用同一 effective scope、selection、relation statement、open action 与 ReturnEnvelope。
17. **Overview 随规模增长保持“导读”，不变成 Dashboard。** 一个成熟 Group 即使有数千条 Knowledge，Overview 仍只说明边界、主要方向、代表理解、限制、关键出口与下一步。
18. **规模由层级吸收，而不是由 Overview 加宽。** 更多内容进入 Topic / Subtopic、Structure、Search 与按需列表；不把 Overview 变成卡片墙、计数墙或 Recent feed。
19. **Topic 层级无限，当前可见范围有限。** 每次显示完整 ancestor path、当前 Topic、直接 children、少量 siblings 与代表 Knowledge；不会一次展开整棵树，也不会因深度超过三层自动扁平化。
20. **All Knowledge 始终是 identity catalog。** 同一 Knowledge 有多个 Placements 时仍只出现一次；位置按需展开。内部 chunks、Blocks、Anchors 与 Search hits 不增加对象数量。
21. **10,000+ Knowledge 不把 Search 变成唯一入口。** 用户仍可从 Group / Topic browse、字母 / 拼音 jump、Saved View 与 Path 找回；Search 是一等定位方式，不是规模税。
22. **无 Query 时没有 AI relevance sort。** 输入查询后，相关性只能作为本次 Search ranking，并显示 match reason；它不改变 Catalog、Overview、Topic semantic order 或未来 Ask 权威。
23. **大量结果先帮助缩小，不先增加密度。** 使用 Scope、Facet、type、state、Applicability、time 与 source coverage 逐步缩小；不通过缩小字号、增加列数或加载无限 chips 解决。
24. **宽泛的全库 Ask 以 Groups 作为覆盖单位。** 系统先说明覆盖了哪些 Groups、哪些未覆盖、索引是否完整，再综合少量 Claims；不能从部分抽样推断“整个知识库都认为”。
25. **Used Context 只显示真正支撑回答的内容。** 大量 candidates、retrieval chunks 或未用 Sources 不因为规模大而进入引用、Graph 或知识真相。
26. **维护事项不随资产数量线性暴露。** Library 最多一条真正改变当前理解的 notice；其余按 owner、impact 和 explicit maintenance View 进入，不建立 1,000 条整理 Inbox。
27. **Paused 不等于 Archived，孤立不等于低质量。** Paused Group 仍在 All Groups；无正式 Relation 的 Group 仍合法；只有用户明确 Archive 才离开 current catalog。
28. **批量操作按选择单位和影响结算。** 100 或 1,000 个结果的 bulk action 必须说明是 identities、Placements、Groups 还是 View rows，并支持分批预览、部分成功、恢复与导出报告。
29. **派生能力失败不抹掉方向感。** Index、Graph layout、embeddings、View evaluation 或 AI 不可用时，canonical Groups、Topics、Placements、titles、manual order、Pins 与 recent safe state 仍可浏览。
30. **Large-state 加载不能先闪 Empty。** 首次可用目录、partial coverage、loading more 与 true empty 使用不同状态；Skeleton 出现不等于产品可操作。
31. **移动端不是简化知识库。** 它可以默认使用列表、顺序窗格与更强的焦点模式，但仍保留 Scope、Selection、Search、Ask、Relation statement、Evidence 与返回责任。
32. **规模成功的标准是方向感，不是吞吐量。** 产品要证明用户知道“我拥有什么、我现在在哪、为什么只看见这些、还有什么未显示、怎样继续和回来”。

---

# 1. 要解决的产品问题

## 1.1 小型 Demo 的幻觉

当 Library 只有三个 Groups、每个 Group 只有十条 Knowledge 时，很多设计都看起来成立：卡片可以全部展开，关系图可以完整显示，Search 几乎总能命中，Overview 可以人工挑选所有内容。

真正的个人知识库会长期增长。届时会出现：

- 100+ Groups，且并非每个都常用；
- 一个 Group 内有五层以上 Topic；
- 10,000+ Knowledge identities 与更多 Placements；
- 同一 Knowledge 出现在多个 Group / Topic；
- 关系极不均匀，有的 Group 完全无边，有的成为高连接 hub；
- 中英文、别名、同名对象、历史版本和 unavailable Sources 并存；
- 搜索、索引、Graph layout 与 AI 不一定全部在线或最新。

如果产品只靠“显示全部卡片”“按最近排序”“让 AI 推荐”“缩小全图”维持，它会在真实规模下从知识库退化成文件仓库、管理后台或装饰性星云。

## 1.2 核心矛盾

产品同时必须满足：

1. **穷尽性**：用户确信全部资产没有被算法藏起来；
2. **可理解性**：当前屏幕不能被全部资产淹没；
3. **连续性**：筛选、深入、跨群和返回不会丢失原现场；
4. **稳定性**：同一个对象不会因为规模、排序或 View 变成不同东西；
5. **探索性**：用户既能找已知对象，也能发现真正成立的相邻关系。

本文的答案不是选其中一项，而是使用 **Stable Catalog + Focus + Context + Progressive Detail**：完整目录保证所有权，当前焦点保证行动，全局语境保证方向，按需细节保证理解。

## 1.3 产品目标

- 在 F1、F10、F100、F10K 夹具中保持同一个产品心智模型；
- 不使用 Search / Ask 时仍能穷尽 browse；
- 不使用 Graph 时仍能理解关系；
- 不使用 AI 时仍能定位、阅读、编辑与返回；
- 让每次过滤、聚合、排序与隐藏都有可解释原因和清除方式；
- 让用户从任何局部细节知道当前 Group / Topic、父级、入口与未显示范围；
- 让规模增长增加资产价值，而不是线性增加管理负担。

## 1.4 永久非目标

- 全局无限画布显示全部 Knowledge；
- 用 relation degree、打开次数或最近修改自动定义重要性；
- 用自动聚类生成新的 knowledge regions；
- 以 Dashboard 数字代替 Library browse；
- 通过强制 Archive、自动清理、健康分或孤立节点告警降低数量；
- 把复杂度转嫁给用户，让其先建完善的 Facet / schema 才能使用；
- 为了性能限制 Group 数、Topic 深度、Placements 或历史；
- 用“系统很快”替代“用户知道自己在哪”。

---

# 2. 规模不变的产品心智模型

## 2.1 五个始终成立的层级

```text
Knowledge Library
  → Knowledge Group
    → Topic / Subtopic
      → Knowledge
        → Section / Claim / Evidence
```

规模只改变同一时刻显示多少，不改变这些对象的含义。

| 对象 | F1 | F10 | F100 / F10K | 永远不改变 |
|---|---|---|---|---|
| Library | 一个 Group 的完整入口 | 可直接 browse 多个 Groups | 稳定 Catalog + Scope / Filter / Jump | 唯一主地点 |
| Group | 一条边界和首份资产 | 多个 Topic 与关系出口 | 数千 Knowledge 的长期范围 | 独立 Boundary / Overview / identity |
| Topic | 可不存在 | 当前分支 | 深层 focus path | 只在 Group 内成立 |
| Knowledge | 可直接在 Group root | 多处 Placement | identity catalog 去重 | 一份 canonical current content |
| Relation | 可为零 | 少量可读陈述 | 按 Scope / Anchor / family 逐步展开 | 正式关系不是相似度 |

## 2.2 四种规模不变的入口意图

| 用户意图 | 主入口 | 规模化责任 |
|---|---|---|
| 我知道大概属于哪里 | Library → Group / Topic browse | 保持稳定层级和穷尽目录 |
| 我知道要找什么 | Search | exact-first、identity 聚合、范围诚实 |
| 我想知道它与什么相连 | Network / Relation | anchor-first、正式关系、列表等价 |
| 我有一个问题 | Ask | Requested / Effective / Used Context 与 coverage |

规模再大，也不能把四种意图压成一个万能 AI 输入框。

## 2.3 Scale Profile 只是 QA fixture

| Fixture | 测试数据 | 主要证明 |
|---|---|---|
| **F1** | 1 Group、0–20 Knowledge、0–3 Relations | 空 / 稀疏状态不伪造结构 |
| **F10** | 10 Groups、100–1,000 Knowledge、多层 Topic | Browse 与 Search 可以自然切换 |
| **F100** | 100+ Groups、10,000+ Knowledge、15,000+ Placements | Catalog、Scope、Network 与返回不崩溃 |
| **F10K+** | 大量 Sources、Views、Paths、history 与 partial indexes | 真值、派生、失败与恢复分开 |

这些数据是压力测试起点，不是用户等级或产品限制。F9 增长为 F10、F99 增长为 F100 时，不发生页面迁移、功能解锁、自动归档或默认排序跳变。

## 2.4 三类预算

| 预算 | 限制什么 | 不限制什么 |
|---|---|---|
| Orientation Budget | 当前表面要解释的范围、位置与入口 | Group / Knowledge 总量 |
| Choice Budget | 同时竞争注意力的主要动作、方向与 relation exits | 可通过 Search / More 找到的对象 |
| Detail Budget | 初始展开的字段、Claims、Evidence 与 neighbours | 深层内容、历史和完整导出 |

预算必须通过`更多 / 展开 / 过滤 / 进入完整列表`显式延展，不能静默截断。

---

# 3. Knowledge Library 在规模下的永久合同

## 3.1 默认页面结构

所有规模下，Library 的责任顺序不变：

1. 当前是`知识库`；
2. 最多一个安全、可解释的`继续`；
3. 一行或一个紧凑区域的用户 Pins；
4. 拥有页面主权的`全部知识群`稳定 Catalog；
5. Recent、Saved Views、Paths / Answers、Archived 等次级入口；
6. 最多一条真正影响当前理解的 contextual notice；
7. 安静但随处可用的 Search / Ask / Add。

没有 Resume 时整块消失；没有 Pins 时不显示空区域；Catalog 自动上移。Recent 不作为默认内容流，不与 Pins 合并，也不重排 All Groups。

## 3.2 All Groups 必须穷尽

`全部知识群`包含所有 active / dormant Groups，不要求存在 Relation、近期活动或完整 Overview。Archived 单独进入，Trash 不在 current catalog。

产品必须能回答：

- 当前总范围是否完整；
- 哪些 filters 正在生效；
- 是否还有未加载 rows；
- 当前结果是 exact、partial 还是 unavailable；
- 一个未显示 Group 是被 filter 排除、Archived、尚未加载，还是根本不存在。

## 3.3 默认排序

All Groups 默认使用语言感知的标题排序：中文按可理解的拼音 / 字符规则，英文按 locale-aware A–Z；别名参与 jump / Search，不制造第二 Row。

用户可以切换：

- 手工保存的 Catalog order；
- Boundary / Facet；
- formation / lifecycle；
- Last opened；
- Updated。

但每次切换必须显示排序名称；只有用户显式保存为 View 才持久化。`Last opened`和`Updated`不能统称`Recent`；无 Query 时不出现 AI relevance。

## 3.4 Pins 与 Recent

Pins 是用户明确挑选的快捷方式：

- 默认只占一个紧凑区域；
- 超出初始显示预算时进入`查看全部固定`，不挤走 Catalog；
- 可以分少量 presentation groups，但不形成 Group boundary 或 membership；
- Pin 顺序只属于个人界面状态。

Recent 是次级 View：

- 分开 Recently opened、edited、created、added to Group 与 updated by Source；
- 默认入口只使用 Recently opened；
- 清除 Recent 不删除对象、ResumePoint 或 History；
- 访问频率不提升 Catalog、Overview 或 Network 显著性。

## 3.5 F1 / F10 / F100 的连续表达

### F1

- Catalog 只显示真实 Group，不制造“常用 / 最近 / 推荐”空 sections；
- 允许直接进入 Group Overview；
- Network 可以只有 Group identity 与诚实无关系状态；
- Add 保持可见，但不催促创建第二个 Group。

### F10

- Catalog 可以直接扫描；
- Pins、title jump、Facet 和 Saved Group View 开始有价值，但都不是必需设置；
- Groups / Network 切换保持 selection；
- 不因仍能一屏容纳而把全部详情铺开。

### F100

- Catalog 保持同一名称、Row contract 与排序；
- 使用 title jump、Search within Groups、Facet、Saved Group Views、progressive loading 与 virtualization；
- 当前 filters 与结果范围固定显示；
- Row 不缩成只有图标或 title；至少保留 Boundary / orientation 的可进入说明；
- 不自动切 Search-first，不自动生成顶层 folders，不把 Paused Group 隐藏。

## 3.6 Group Catalog Row

每个 Group Row 初始只承担识别与进入：

- Group title；
- 一句 Boundary / orientation；
- 少量主要方向或 stable start 提示；
- 必要 lifecycle / availability 状态；
- ordinary open 与明确 Continue 的不同动作。

默认不显示 Knowledge 数、Relation 数、Source 数、完成度、连接率、AI score、最近编辑者或十几个状态 chips。小规模可以使用更宽松的空间，但不能增加另一套语义；大规模可以更紧凑，但不能删掉识别所需信息。

## 3.7 Saved Group Views

Saved Group View 可以保存：

- Group Facets；
- lifecycle；
- presence / absence of maintained current Relations；
- Boundary keyword；
- explicit user properties；
- sort、visible fields 与 density。

View 只保存 criteria 和 presentation，不拥有 Group members，不生成顶层目录或 Network region。手工想把少量 Groups 放在一起时，优先使用 Pins；需要一个有独立知识问题的整体时，建立新的 Group；需要顺序叙事时，使用 Saved Path。

---

# 4. Group Overview 与深层结构在规模下的合同

## 4.1 Overview 不能随内容量线性增长

无论 Group 有 1 条还是 5,000 条 Knowledge，Overview 都回答同样六件事：

1. 这个范围是什么；
2. 它不包括什么；
3. 主要理解方向是什么；
4. 当前有哪些代表性理解与限制；
5. 有哪些重要跨群出口；
6. 下一步从哪里进入。

更多内容不自动增加更多卡片、图表、统计或 Recent activity。

## 4.2 Main Directions

Overview 的初始主要方向预算是少量可区分入口。设计起始假设为 3–7 个，但不是业务上限。

优先顺序：

1. 用户策展的 stable starts / representative Topics；
2. 用户接受的 Overview Diff；
3. canonical Topic semantic order 的结构回退；
4. 没有可靠入口时诚实显示 Structure 入口。

Recent、点击率、Knowledge 数、Relation degree 与 AI relevance 不自动成为 main direction。其余 Topics 进入完整 Structure，不被隐藏或删除。

## 4.3 Topic focus + context

深层 Topic Reading 每次显示：

- 完整 ancestor path；
- 当前 Topic 的局部 orientation；
- direct child Topics；
- direct Knowledge；
- 少量 siblings；
- 是否存在未展开 descendants；
- 当前局部关系出口。

Focus 越深，远处只保留主要 landmarks，不把每一级所有 siblings 同时展开。用户可以通过 Up、DepthTrail、Structure rail 或 Search 回到全局语境。

## 4.4 Direct 与 descendants

`直接放在这里`和`包含子主题`始终分开：

- 默认 Topic 先显示 direct children / placements；
- `同时显示下级主题中的知识`是显式 View State；
- descendant results 按 Knowledge identity 聚合，但保留 exact paths；
- ancestor 不创建镜像 Placements；
- 结果数量明确 direct / descendants / partial。

## 4.5 超宽与超深结构

| 状态 | 正确行为 | 禁止 |
|---|---|---|
| 20+ root Topics | 显示 stable starts + 完整 Structure / jump | Overview 铺满全部 Topic cards |
| 5+ levels | focus path + ancestor context | 自动扁平化或创建 Subgroup |
| 单 Topic 有 500 Knowledge | direct list + filter / Search within Topic | 无限展开、缩小字体 |
| 多个同名 Topics | parent path + orientation 消歧 | 自动合并 |
| single-child chain | 保留真实层级，可提出 impact-aware simplify | 自动 redirect / 静默 flatten |

## 4.6 Overview partial / stale

当 Projection 尚未刷新或部分索引不可用：

- Editorial orientation 与 stable starts 仍显示；
- Structure 使用 canonical Topics / Placements；
- 动态 counts 标记 partial 或暂不显示；
- 不用旧 Projection 冒充 current；
- 不因 projection failure 把 Overview 替换成 loading page。

---

# 5. All Knowledge 与 Sources 在规模下的合同

## 5.1 All Knowledge 是 identity catalog

All Knowledge 包含 current active Knowledge identities，并能标示 Explicit Draft / conflict / archived eligibility。它不混入 Groups、Topics、Sources、Saved Answers、Query Runs 或 internal chunks。

同一 Knowledge：

- 在 catalog 中一行；
- 显示 primary display placement 只是进入语境，不是 canonical parent；
- 其他 Placements 可展开；
- Group filter 通过 active Placements 求值；
- Search 多 Anchor 命中仍聚合到同一 identity。

## 5.2 大量 Knowledge 的默认浏览

- 默认稳定标题排序；
- title / pinyin jump；
- filter by Group、Topic、kind、standing、Applicability、support、freshness 与 time；
- selection 使用 identity，不依赖 visible row index；
- progressive loading / virtualization 不改变结果顺序与焦点；
- Back 恢复 query、filters、sort、scroll、expanded placements 与 selection；
- exact / estimated / partial counts 分开。

## 5.3 Row 识别预算

初始 Row 包含：title、orientation、display placement、其他位置数量、必要 standing / Applicability 与 match reason。默认不加载完整 Sources、Graph、Properties、History 或 AI summary。

Cards 只适合有 preview 价值的小结果集；10,000 identities 的主目录不使用图片卡片墙。Table 只在比较属性时出现；List 仍提供完整任务等价。

## 5.4 Sources 不冒充 Knowledge scale

Sources 使用自己的 identity catalog：

- 一个 Source 的多个 representations / attachments 不重复列为多个 Sources；
- Group / Topic Attachment 用路径说明语境；
- Source-only 保持可返回；
- parsing / OCR / availability 与 Source saved 分开；
- Source 数量不进入 Group maturity 或 Overview quality score；
- 查来源与查 Knowledge 是不同结果类型，但 Search 可以统一入口后清楚分组。

---

# 6. Search 在规模下的合同

## 6.1 Search 是定位层，不是大规模首页

Search 解决 known-item、半记得、精确 Anchor 与跨范围定位。它不会因为 Library 变大就自动接管启动页，也不会把 Catalog 降成 Search history。

## 6.2 Exact-first

优先匹配：

1. exact title / alias；
2. title prefix / locale-aware token；
3. exact phrase；
4. structured path / property；
5. full text；
6. semantic supplement。

结果必须说明 match reason；semantic similarity 不能与 exact result 混成同一种信号，也不能生成 Relation。

## 6.3 大结果集

当结果很多：

- 先显示 Scope 与结果单位；
- 按 owner identity 聚合；
- 提供高价值 facets 与 query refinement；
- 同一 facet 内优先显示与当前 query 相关的 labels；
- 允许在当前 Group / Topic / View 中搜索；
- progressive load 保留稳定 order；
- 不把每个 chunk 展开成结果 Row；
- 不因为存在 10,000 hits 就显示 10,000 snippets。

## 6.4 Ranking 纪律

有 Query 时，ranking 可以使用 exactness、title / alias、current scope、accepted standing、Applicability、support availability 与 semantic relevance；必须保留可解释 match reason。

以下因素不能单独决定长期重要性：

- recency；
- popularity / click count；
- relation degree；
- embedding centrality；
- AI confidence；
- Source count。

关闭 Search 后，任何 ranking 不传播到 Catalog、Overview 或 Network。

## 6.5 No result / partial

产品分别说明：

- 当前 Scope 没找到；
- filters 排除了结果；
- index partial；
- Source 尚未解析；
- semantic search unavailable；
- title / exact 搜索仍可用；
- 真正完整范围中没有匹配。

系统可以建议放宽一个条件、改词、扩大到 Group / Library 或加入指定 Source，但不能直接下结论“你的知识库没有”。

---

# 7. Knowledge Network 在规模下的合同

## 7.1 Network 是窗口，不是全量海报

Library Network 的任务是：

- 看一个 Group 与哪些 Groups 有正式关系；
- 理解 relation statement、方向、条件与依据；
- 沿关系进入相邻知识范围；
- 保留当前 Scope、Trail 与返回现场。

它不负责同时证明全部对象都存在。穷尽性由 All Groups 与 List Equivalent 保证。

## 7.2 Effective Network Scope

每次 Network 都显示：

- Scope 来源：All Groups / Saved Group View / Facet / Search / Path / current Group；
- included Groups；
- excluded / hidden 原因；
- Current / Suggested / History relation layer，以及 unavailable / transition-pending 说明；
- 当前 anchor；
- 是否超过初始可视预算。

过滤、Search highlight 与 temporary cluster 都属于 scene state；清除后恢复原正式 Network。

## 7.3 Under-budget

当 Effective Scope 在当前设备和 label density 下可以完整表达时，可显示全部 included Groups 与 maintained + current lifecycle Group Relations。是否 under-budget 由实际可读性验证，不只按固定节点数。

Suggested layer 即使 under-budget 也不默认混入 Current。Candidate 资格与显示显著性分开：通过前八道聚合门只说明建议有语义资格；是否 ambient 出现还要满足 attention / suppression budget。更多 raw paths、更多重复来源、degree 更高或位于画面中心都不能让 Candidate 升级或排到前面。

设计起始夹具可以使用 6–20 Groups，但不得写成数据限制。

## 7.4 Over-budget / Anchor Required

当 Scope 超过预算：

1. 不绘制 unreadable hairball；
2. 不任意抽取 Top N；
3. 不按 relation degree、recent 或 AI relevance 选择“核心”；
4. 显示完整 Scope Summary 与同义 Group list；
5. 让用户通过选择 Group、Search、Facet、Saved View 或 Path 确定 anchor；
6. anchor 后显示选中 Group + 约 3–7 条高价值 maintained current neighbours；
7. 其他 relations 按 family / direction / Group / disposition / change condition 展开；
8. 二跳只在显式 Expand / Query Route 时出现。

这不是失败或降级，而是成熟 Network 的默认 focus + context 行为。

## 7.5 “高价值邻接”的合法依据

初始 neighbours 的选择顺序：

1. 用户 pinned / curated Relation；
2. 与当前明确任务 / query 直接相关且 maintained / current / applicable；
3. Direct Group Relation；
4. Adopted Aggregated Group Relation；
5. maintained 但 review_due 的 Relation，带一句变化说明且不使用断线暗示失效；
6. 其余 maintained current Relations 进入`查看全部关系`。

Similarity、shared Source、co-use、click count 与 layout centrality 不足以进入正式默认层。

Aggregation Signal、fringe-only support 与 exit-only 结果不进入 neighbour ranking。它们只在用户主动查看跨群 exits、打开 Suggested layer或询问特定 Group pair 时按需解释；关闭上下文后不影响 Current layout 与稳定位置。

Shared Knowledge observation 同样不进入 neighbour ranking、edge budget 或 stable layout。即使 100 个 Groups 共享同一 canonical Knowledge，也只在用户主动打开“共同知识”、选择具体 Group pair 或询问为什么多个 Groups 同时包含它时按需计算；结果先按 Knowledge identity 去重，再列各 Group 的 exact Placement / role。它不生成 4,950 条 pairwise formal edges，也不形成一张新的 Current / Suggested / History 网络。

## 7.6 Unconnected Groups

无 maintained current Group Relation 的 Group：

- 始终存在于 All Groups；
- 在当前 Network Scope 的 List Equivalent 中可见并标为`当前没有明确群关系`；
- 不被标为 orphan、低质量或整理任务；
- 可以从层级、Search、Reference Links 或 cross-group Knowledge exits 开始探索；
- 不为填空生成 Proposal edges。

## 7.7 Temporary cluster

用户可以在 Explore 中显式运行`按当前关系模式分组查看`或 query overlay。结果必须写：

- 依据哪些 maintained current Relations / properties；
- 当前 algorithm / filters；
- 只影响本次 scene；
- 清除方式；
- 不改变 Group boundary / Facet / Relation。

不得把 cluster 自动命名为知识领域、写入 Overview、保存为 Group 或默认作为下次 Network 首页。

## 7.8 Stable layout 与返回

- 同一 Saved Network View / anchor 使用可恢复 layout；
- 新增 relation 增量更新，不让全部 Groups 随机漂移；
- hover / focus / pan / zoom / filter 不进入 ExplorationTrail；
- Inspect 只 Peek，Open endpoint 才推进 ReturnStack / Trail；
- Back 恢复 edge、anchor、viewport、filters、scope 与 List scroll；
- layout cache 丢失只重置 scene，不损坏 Relation truth。

---

# 8. Ask 在规模下的合同

## 8.1 全库 Ask 不是抽样总结

用户从 Library Ask 时，Requested Context 可以是整个 Library；系统必须把 Groups 作为 coverage units，而不是从若干高 rank chunks 直接冒充全库结论。

回答前至少可预测：

- Group / Topic / Knowledge Scope；
- accepted / draft / historical standing；
- Source-only 是否包含；
- 是否沿正式 Relations 扩大；
- external off / on；
- index coverage。

## 8.2 Broad overview

例如用户问`概览我的整个知识库`时：

1. 先给 Library boundary 与 Groups coverage；
2. 以 Groups / stable main directions 作为结构；
3. 标明未覆盖、partial index、Paused / Archived 是否排除；
4. 不把 100 个 Groups 压成 100 条摘要；
5. 提供 3–7 个可进入的高层方向作为当前回答预算；
6. 其余进入可展开 Group list；
7. 每个 Claim 回到真正 Used Knowledge / Evidence；
8. `概览`不自动改写 Library Overview 或建立跨群 Relation。

## 8.3 Too broad / ambiguous

当问题太宽且不同解释会显著改变回答时：

- 最多先问一个决定性澄清；或
- 给出两到三个明确 interpretation branches；
- 每个 branch 保存独立 Effective Context；
- 不用一个隐藏的 AI plan 选择“最有意思的部分”。

## 8.4 Coverage 与负面回答

全库 Ask 必须区分：

- 完整索引且无命中；
- 部分 Groups 未索引；
- Sources 未解析；
- current scope 排除了某些 Groups；
- only historical / draft knowledge exists；
- external knowledge disabled。

Coverage 不以 candidate 数或 token 数表达，而以用户能理解的范围与缺口表达。

## 8.5 Answer → Knowledge / Network

- Claim 打开具体 Knowledge / Anchor；
- Group comparison 可以打开临时 Query overlay；
- Route 只使用 formal Relations 或明确 runtime jumps；
- 关闭 Answer 恢复 Library / Reading scene；
- Saved Answer 保留当时 Scope 与 coverage；
- 写回只提交具体 Claim / block patch；
- 同一次 Answer 共用多个 Groups 不生成 Group Relation。

---

# 9. 日常连续性与长期维护

## 9.1 日常入口不随规模膨胀

Library 仍然只有：

- 最多一个 Resume；
- 紧凑 Pins；
- All Groups；
- Search / Ask / Add；
- 次级 Views / Paths / Answers / Archived。

Group 数量从 10 增长到 100，不增加首页 tabs、今日 Feed、自动 Topics、Health dashboard 或管理 Inbox。

## 9.2 Paused / Archived / Trash

| 状态 | Catalog | Search | Ask 默认 | Network | 恢复 |
|---|---|---|---|---|---|
| Active | All Groups | 是 | 是 | Maintained current Relations | 正常 |
| Paused | All Groups，状态低噪声 | 是 | 默认可用，按具体 change / Evidence 说明 | 关系保留 | 直接打开；Attention 是否恢复另行决定 |
| Archived | Archived | 可显式包含 | 默认否 | 默认否 | Restore |
| Trash | Trash only | 日常否 | 否 | 否 | 在保留期内 Restore |

系统可以依据时间 / 使用模式提出一次 Paused 建议，但只有用户接受才改变 Attention Mode；Paused 不自动 Archive，也不触发“唤醒任务”。

## 9.3 Notice budget

规模下只让真正影响当前理解的事项进入注意力表面：

- Library 最多一条跨范围 high-impact notice；
- Group Overview 最多一条当前范围 notice；
- Knowledge 在受影响 Claim 附近显示局部 notice；
- Source permission / parse 修复回到 Sources；
- bulk maintenance 只在用户显式打开 View 时显示完整集合。

同一 event 只有一个 Primary Destination，不在 100 个 Groups 重复制造 badge。

## 9.4 Bulk at scale

批量动作先冻结选择集与单位：

- Group identities；
- Knowledge identities；
- Placements；
- Source identities；
- View rows / evaluation snapshot。

提交前显示 will change / remain / skip / conflict / unavailable。用户可以只提交 clean subset；每个成功项保留 Change Set 与 Undo，失败项不重复。删除 View / Pin / Recent / Path 永远不删除 canonical Knowledge。

## 9.5 Schema 与 Facet 不成为维护税

- Group / Knowledge 可无 Facet；
- 新 Facet 不触发要求补齐全部历史对象；
- unknown / unset 与 false / N/A 分开；
- AI property suggestions 是 Patch，不静默写入；
- View 显示 partial coverage；
- 大规模 migration 支持 raw legacy value、分批提交与 rollback。

---

# 10. 性能、离线与派生失败的产品边界

## 10.1 First meaningful state

启动 / 切换 View / 打开 Group 时，产品区分：

1. Shell ready；
2. canonical catalog / current owner ready；
3. index / projection partial；
4. AI / semantic / Graph layout ready；
5. fully enriched。

只有第 2 步才算可操作目录；Skeleton 或空容器出现不算成功。后续派生逐步增强，但不能重排已经开始操作的 Row 或偷换 selection。

## 10.2 Canonical fallback

| 失败 | 仍然可用 | 明确降级 |
|---|---|---|
| Search index rebuild | Group / Topic / title / exact local delta | full text / semantic partial |
| Graph layout missing | Relation list / statements / selected path | viewport reset |
| View evaluation stale | saved criteria + last verified results + refresh state | result coverage partial |
| Overview projection stale | Editorial + canonical structure | dynamic summary partial |
| AI unavailable | Catalog、Reading、Search exact、manual Relation | Ask / suggestions unavailable |
| Source remote unavailable | Source identity、metadata、snapshot / history | live original inaccessible |

任何派生失败都不能删除 Group、Knowledge、Placement、Relation 或 Source identity。

## 10.3 Loading / partial / empty

- Loading：尚未完成当前求值；
- Partial：已有可用结果，但覆盖不完整；
- Empty：已完成有效 Scope 的求值且无结果；
- Filtered Empty：内容存在，但被当前 criteria 排除；
- Unavailable：当前能力无法求值。

这些状态使用不同文案、操作和辅助技术公告，不共享一个空页面。

## 10.4 Restore at scale

恢复保存 identity 与语义现场，而不是 DOM index：

- Library mode / Saved View；
- filters / sort / grouping；
- selected identity + placement context；
- virtualized list offset / anchor row；
- expanded focus path；
- Reading target / Anchor / scroll；
- Network Scope / anchor / viewport；
- ReturnStack / focus return。

目标变化时使用 redirect / nearest valid parent 并说明；不能静默选“相似内容”。

---

# 11. Responsive 与 Accessibility 等价

## 11.1 Desktop

可以并列 Catalog / Structure、Reading Primary 与一个按需 Companion，但同一时刻只有一个主任务。大屏不授权永久显示全部 Filters、Properties、Relations 与 History。

## 11.2 Mobile / narrow

- Catalog、Reading、Companion 顺序呈现；
- Network 可以默认 List Equivalent；
- 当前 Scope / filters 在进入结果前可读；
- Back 先恢复 caller scene，Up 才回语义父级；
- filters 不缩成无法解释的图标数量；
- Search / Ask / Add、Sources、Evidence 与 Recovery 仍可完成。

## 11.3 Keyboard / screen reader

- 目录使用正确 list / tree semantics；
- focus 不因 virtualization 丢失；
- Group Row 读出 title、orientation、state 与 ordinary open / Continue；
- Topic disclosure 与 Open 分开；
- Graph list 读出 Relation statement、direction、standing 与 target；
- result count 说明 exact / partial；
- filter change 使用可撤销 live announcement；
- move / reorder / add Placement 有 drag alternative；
- 200% zoom 不丢 scope、status 或操作后果。

---

# 12. 结果指标与反指标

## 12.1 核心指标

| 指标 | 定义 | 验证什么 |
|---|---|---|
| Catalog Exhaustiveness Confidence | 用户能否确认当前 Catalog 是否包含全部 active / dormant Groups，以及哪些 filters 生效 | 所有权是否被算法隐藏 |
| Group Orientation at Scale | 在 F1 / F10 / F100 中能否说清一个 Group 的 Boundary、主要方向与入口 | Overview 是否随规模保持导读 |
| Known-item Re-find Success | 延迟后从 Catalog / hierarchy / Search 找回目标 identity 与 exact path 的比例 | 长期可返回性 |
| Browse-to-Target Success | 不使用 Search / Ask，从大概范围进入目标 Knowledge 的成功率 | Browse 是否仍是一等方式 |
| Scope Visibility | 用户能否解释为什么当前只看见这些 Groups / Knowledge / Relations | Filter / View / Network 是否诚实 |
| Focus–Context Comprehension | 深层阅读或局部 Network 中能否同时识别当前焦点和全局位置 | 局部细节是否导致迷失 |
| Result Identity Precision | 同一 Knowledge 的多 Anchors / Placements 是否仍聚合为一个 identity | 规模是否制造重复对象 |
| Network Clutter Escape | Over-budget Network 能否通过 anchor / filter / list 找到目标关系 | 图谱是否可用而非装饰 |
| Relation Statement Recall | 用户能否复述端点、方向、条件与依据 | 图形是否保留语义 |
| Filter Reversibility | 清除 / Back 后是否恢复 scope、order、selection 与 scroll | 探索是否可逆 |
| Broad Ask Coverage Calibration | 全库 Ask 的 sufficient / partial / indeterminate 是否与实际 Group / index coverage 一致 | AI 是否从抽样冒充全局 |
| Large-state Return Fidelity | virtualization、深层 Topic、Network 与 Answer 往返后现场恢复正确率 | 规模下连续性 |
| Maintenance Attention Ratio | 默认表面中真正改变当前理解的 notice 占全部可见维护提示的比例 | 大库是否变成 Inbox |
| No-AI Browse Completeness | AI / semantic unavailable 时 Catalog、hierarchy、exact search 与 relation list 是否完整可用 | local-first 是否真实 |

## 12.2 反指标

不得把以下数字当作规模成功：

- Group / Knowledge / Relation / Source 总数；
- 图谱连通率或最大 component；
- 平均 relation degree；
- 每日整理数量；
- Archive 率；
- AI 推荐点击率；
- Search 使用率越高越好；
- 用户在 Library 停留越久越好；
- 所有内容都具有 Facet / Source / Relation；
- 首屏显示的对象越多越好。

## 12.3 待验证假设

- All Groups 默认语言感知标题排序是否比 manual / recent 更有长期方向感；
- Pins 初始一行的显示预算是否足够；
- Recent 退出默认首页后，单条 Resume 是否仍支持日常连续性；
- Over-budget Network 的 Anchor Required 是否被理解为成熟行为，而不是能力不足；
- 3–7 个 Group neighbours 与 4–8 个 Knowledge neighbours 是否足够；
- Group Row 的一句 Boundary 是否能在高密度 Catalog 中提供足够 information scent；
- 全库 Ask 按 Groups 表达 coverage 是否能被普通用户理解；
- Saved Group Views + Facets 是否足以组织 100+ Groups，而不需要 presentation-only top-level sections；
- focus path + limited siblings 是否兼顾局部效率与全局方向。

在真实任务验证前，这些预算不成为不可改变的视觉常量。

---

# 13. 规模压力场景

## 13.1 F1：一个 Group、零关系

Library 只显示真实 Group；Network 不画假边；普通打开进入 Overview；用户不被催促创建第二 Group 或 Relation。

## 13.2 F10：十个领域并行

用户通过 Catalog browse、Pin 两个常用 Group、从一个 Group 切 Network，再返回原 Catalog selection；Recent 不重排目录。

## 13.3 F100：一百个 Groups

用户不知道确切名称，只记得“法国生活”。通过 Facet / title jump / Group Search 缩小范围；清除 filter 后恢复完整 Catalog 与 scroll。

## 13.4 F100 disconnected

100 Groups 中只有 12 个拥有 maintained current Group Relations。Network List 仍能说明 88 个当前无明确关系；产品不生成边、不惩罚、不隐藏。

## 13.5 Super-connected hub

一个 Group 有 80 条 maintained current Relations。初始只显示当前任务相关 neighbours；按 family 展开；List Equivalent 可搜索全部；degree 不自动成为“最重要”。

## 13.6 10k Knowledge / multi-placement

同一 Knowledge 在三个 Groups、五个 Anchors 命中。All Knowledge 和 Search 各只显示一个 identity，并展开 exact paths / Anchors。

## 13.7 Deep hierarchy

Group 有七层 Topic。用户从 Search 直达第七层 Knowledge；DepthTrail、ancestor context、Up、Back 与 auto-reveal 不制造中转页。

## 13.8 Very broad Ask

用户问`我的整个知识库对学习有什么理解？`。系统按 Groups 说明 coverage，不从几个 chunks 冒充全库观点，并允许沿某一 Claim 进入 Group / Knowledge。

## 13.9 Partial index

10,000 Knowledge 中 2,000 尚未完成 full-text / semantic index。Catalog 与 exact title 可用；Search / Ask 显示 indeterminate coverage；不说“没有”。

## 13.10 Scale crossing

第 99 个 Group 增长为第 100 个。页面、导航、默认排序、对象语义与 ordinary open 不改变，只增加可用的 jump / filter / virtualization。

## 13.11 200 Saved Views / Paths / Answers

这些 supporting assets 不铺到首页；各自 Catalog / Search 可找回；删除 View 不删除 Knowledge；Path 与 Progress 分开。

## 13.12 Multilingual / same names

中文、英文、别名和两个同名 Groups 并存。Catalog jump 与 Search locale-aware；Row 使用 Boundary / Facet 消歧；不自动 merge。

## 13.13 Bulk 1,000 targets

用户在 View 中选择 1,000 Rows。产品冻结 evaluation snapshot，说明 identities / placements、will change / skip / fail，允许 clean subset 与部分恢复。

## 13.14 Mobile + screen reader

用户只用 mobile 与屏幕阅读器完成 F100 Catalog filter、打开 Group、沿 Relation list 跨群、Back 回到原 filter / focus。

## 13.15 Derived reset

删除 Search index、Graph layout、Overview projections 与 workspace caches 后，canonical Groups / Topics / Placements / Knowledge / Relations / Sources 仍可重建，且不丢 identity 或 history。

---

# 14. Given / When / Then 验收合同

## 14.1 规模跨越不切换产品

**Given** Library 从 9 增长到 10、从 99 增长到 100 Groups  
**When** 用户普通启动、浏览 Catalog、打开 Group 和返回  
**Then** Knowledge Library、Groups / Network、Row identity、默认排序、ordinary open / Continue 与返回语义不改变；只按需出现 jump、filter、progressive loading 和 large-state status，不增加模式迁移或 onboarding。

## 14.2 All Groups 穷尽且不被排名偷换

**Given** 100 active / dormant Groups，其中 10 个常用、20 个 recently opened、88 个无 maintained current Relation  
**When** 打开默认 Library  
**Then** Resume 最多一条、Pins 紧凑、All Groups 包含全部 100 个并使用稳定顺序；Recent、AI relevance、relation degree 与 activity 不重排或隐藏；当前 Scope / filters / exact or partial state 可见。

## 14.3 Paused 不自动消失

**Given** 一个 Group 六个月未打开但 Boundary 和 Knowledge 仍有效  
**When** Library 更新 lifecycle presentation  
**Then** Group 仍在 All Groups 和 Search；Paused 只低噪声说明，不自动 Archive、不触发提醒、不降低 Ask / Network truth。

## 14.4 Overview 不随数量线性膨胀

**Given** 同一 Group 有 40 root Topics、5,000 Knowledge 和 60 relations  
**When** 普通打开 Group  
**Then** Overview 仍围绕 Boundary、少量 stable main directions、representative understanding、limits 与 exits；完整 Topics 进入 Structure，Relations 按需出现，不显示卡片墙、统计 Dashboard 或 Recent feed。

## 14.5 深层 focus + context

**Given** 用户位于七层 Topic 下的一条 Knowledge Anchor  
**When** 查看 Structure、Up、Back 与 Search return  
**Then** 当前 ancestor path、局部 orientation、direct children / Knowledge 与必要 siblings 可知；不会展开整棵树、自动 flatten 或丢失 caller scene。

## 14.6 Identity catalog 去重

**Given** 同一 Knowledge 有五个 Placements、十个 matching Anchors 和三个 Source references  
**When** All Knowledge、Group filter 与 Search 展示结果  
**Then** identity mode 只显示一个 Knowledge，位置 / Anchors 分层展开；Placement mode 才按 exact paths 显示多 Rows；chunks 与 Sources 不制造 Knowledge 数量。

## 14.7 Search ranking 不传播

**Given** Query 让一条最近修改但较弱匹配的 Knowledge 排在前列  
**When** 用户关闭 Search 并回到 Catalog / Overview / Network  
**Then** Search ranking 和 snippets 消失；Catalog、semantic order、stable starts、representative Knowledge 与 Relation truth 完全不变。

## 14.8 Search partial 不冒充无知识

**Given** 10,000 Knowledge 中 20% full-text / semantic index 未完成  
**When** 当前 Scope 无命中  
**Then** exact title / canonical browse 仍可用；Coverage = indeterminate 或 partial；产品说明未覆盖范围并提供重试 / 扩大 / 指定 Source，不说知识库没有。

## 14.9 Over-budget Network 不任意抽样

**Given** Effective Network Scope 含 100 Groups 和 300 maintained current Group Relations  
**When** 打开 Network 且没有 anchor  
**Then** 产品显示 Scope Summary、完整同义 Group list 和选择 anchor / filter / Saved View 的动作；不绘制 hairball、不按 degree / recent / AI relevance 抽 Top N、不把自动 cluster 当 regions。

## 14.10 Anchor 后关系可读

**Given** 用户从 F100 Network 选择一个拥有 40 Relations 的 Group  
**When** 进入 focused Network  
**Then** 初始只显示少量 curated / task-relevant accepted neighbours；每条关系可读、可核验；其余按 family / direction / state 展开；二跳显式；List Equivalent 完整可用。

## 14.11 Unconnected Group 不被惩罚

**Given** Group 没有 accepted Relation 但拥有完整 Overview 与 Knowledge  
**When** 在 Catalog、Network List、Search 与 Ask 查看  
**Then** Group 正常存在，Network 诚实写当前无明确群关系；不显示 orphan warning、质量分、整理任务或自动 Proposal edge。

## 14.12 Temporary cluster 零结构副作用

**Given** 用户在 Network 运行一次基于 maintained current Relations 的临时聚类  
**When** 保存截图 / Path 后清除 overlay  
**Then** Group Boundary、Facet、Catalog order、Relations 与 Overview 不变；Path connectors 保留真实 relation / manual reason，不把 cluster membership 写入知识本体。

## 14.13 Broad Ask 以 Groups 校准覆盖

**Given** Library 有 100 Groups、部分 Paused、两组 index partial、external off  
**When** 用户询问整个知识库的共同观点  
**Then** Answer 先说明 included / excluded Groups 与 coverage，按少量高层方向组织，Claims 回到 Used Knowledge；不会把未检索 Groups 计为同意，也不会由共同使用创建 Group Relation。

## 14.14 Filter 可逆

**Given** 用户从 All Groups 逐步应用 Facet、lifecycle 与 relation-exists filters，打开一个 Group 后返回  
**When** 执行 Back 与 Clear filters  
**Then** 每一步恢复 exact criteria、result order、selection、scroll 与 focus；清除后回到完整 Catalog，不修改 Group identity 或 membership。

## 14.15 Large bulk 作用单位清楚

**Given** 一个 View 返回 1,000 identity Rows，其中部分 Knowledge 有多 Placements  
**When** 用户选择批量加入 Group  
**Then** Preview 明确是在创建 Placements而非移动 / 复制 identities；选择集被冻结；existing / clean / conflict / unavailable 分组；可只提交 clean subset，失败不复制成功项。

## 14.16 派生重建不损坏知识

**Given** Search index、Graph layout、View evaluation cache 与 Overview projections 全部丢失  
**When** 离线打开 F100 Library  
**Then** canonical Catalog、Topic tree、Placements、Knowledge current、manual Relations、Pins 与可读 history 仍存在；各派生层分别显示重建状态，不出现空知识库或 identity 变化。

## 14.17 Large-state loading 不闪 Empty

**Given** Catalog / Search / View 需要 progressive load  
**When** 首批数据尚未完成、部分结果可用和最终无结果分别发生  
**Then** Loading、Partial、Empty、Filtered Empty 与 Unavailable 使用不同状态；焦点与 selection 不因补载跳动；Skeleton 不被记录为可操作完成。

## 14.18 Responsive 等价

**Given** 同一 F100 任务在 desktop、mobile、keyboard、screen reader 与 200% zoom 完成  
**When** 过滤 Catalog、进入 Group、打开 Relation、返回 Search result  
**Then** effective scope、identity、relation statement、ReturnStack、filters 与结果一致；图可以转列表，但产品责任不减少，焦点不因 virtualization 丢失。

---

# 15. 研究事实、产品推论与证据边界

## 15.1 Overview、filter 与 details-on-demand

Shneiderman 的信息可视化任务分类把 overview、zoom、filter、details-on-demand、relate、history 与 extract 分开，并明确“overview first, zoom and filter, then details-on-demand”只是设计大型信息集合的起点。

产品推论：Library、Group Overview、Network Scope Summary 与逐步深入有研究基础；但 overview 不要求全量可视化，history / relate 也不能被一个万能 Graph 取代。

[University of Maryland — The Eyes Have It](https://drum.lib.umd.edu/items/155a868e-fb83-4115-9899-9187ea8c0498)

## 15.2 Focus + context

Furnas 的 Generalized Fisheye Views 研究强调大型结构需要同时保留局部细节与远处的主要 landmarks，并把这种方法应用到列表、树、文本 outline 与图。

产品推论：深层 Topic 与 focused Network 可以显示当前邻域的细节，同时把远处范围压缩成 ancestor、Scope Summary 和主要 landmarks；但本产品不采用会扭曲 identity 或自动重要性的物理 fisheye 布局。

[Generalized Fisheye Views](https://www.cs.columbia.edu/~feiner/courses/csw4170/resources/furnasCHI86.pdf)

## 15.3 Faceted navigation 与 keyword search 可以协作

Hearst 对 faceted navigation 的研究把它描述为支持探索和发现的方式，同时强调大类别系统的界面挑战、facet history、在 facet 结构中加入 keyword search，以及大 label 集合需要动态 suggestion。

产品推论：F100 Catalog 应允许 browse、Facet 与 Search 互相转换，并持续显示当前 criteria / history；但 Facet 不自动成为 Group hierarchy，也不要求用户先结构化所有内容。

[UC Berkeley — UIs for Faceted Navigation](https://people.ischool.berkeley.edu/~hearst/papers/hcir08.pdf)

## 15.4 成熟 Library 分开稳定目录、快捷入口与搜索

Notion 官方 Library 提供统一的内容管理入口，同时把 Recents、Favorites 等分开，并支持按名称搜索、filters 和可见 details 定制；其 sidebar 也允许控制显示哪些 sections。

产品推论：Catalog、Pins、Recent、Search 与显示字段是不同责任；本产品进一步冻结 All Groups 为稳定主目录，Recent 不接管默认排序。

[Notion — Manage your Library](https://www.notion.com/help/manage-your-library)

## 15.5 Global 与 Local Graph 可以分工

Obsidian 官方把整个 vault 的 Graph 与 active note 的 Local Graph 分开，并为 Graph 提供 search filters、existing / orphan toggles、groups、direction arrows 与 local depth。

产品推论：全局范围、局部焦点、过滤与深度应分开；本产品进一步限制正式关系语义、Anchor Required、列表等价和临时 cluster 零结构副作用。

[Obsidian — Graph view](https://obsidian.md/help/plugins/graph)

## 15.6 大集合需要显露还有更多内容

Apple 的 Layout guidance 强调视觉层级、把重要内容置于容易发现的位置、渐进披露，并在无法同时显示大型集合全部 items 时明确还有未显示内容。

产品推论：attention budget 必须配套 Scope Summary、result count、More / Expand 与 partial state，不能静默截断。

[Apple Human Interface Guidelines — Layout](https://developer.apple.com/design/human-interface-guidelines/layout)

## 15.7 研究没有证明什么

以上来源不证明：

- All Groups 必须默认标题排序；
- Recent 必须退出默认首页；
- Over-budget Network 必须使用 Anchor Required；
- 3–7 / 4–8 / 6–20 是正确预算；
- Saved Group Views + Facets 一定足以组织 100+ Groups；
- 全库 Ask 必须以 Groups 作为 coverage units；
- Library 不需要 presentation-only top-level sections。

这些都是本产品为了保持单一心智模型、稳定所有权和关系真相做出的决定或待验证假设。真实任务必须覆盖 F1、F10、F100、F10K、desktop / mobile、Graph / List、AI on / off 与 partial index，而不能只测试一个小型 happy path。

---

# 16. 对现有文档与后续设计的约束

1. Canonical v4.0 必须加入 Scale Invariance、All Groups 穷尽、Over-budget Network Anchor Required 与 broad Ask coverage；
2. Library 合同原`Atlas 聚合 Group regions`改为：自动 cluster 只属于 temporary overlay；正式 Network 超预算时先 anchor / filter / Saved View；
3. Library 合同默认入口明确为 Resume → Pins → All Groups，Recent 作为次级 View；
4. 核心心智模型补充 F1 / F10 / F100 使用同一产品表面；
5. 知识深度与关系合同不得用 Top N degree 或自动 regions 解决 100+ Groups；
6. Search 合同继续使用 exact-first、owner identity aggregation 与 partial coverage；
7. AI 查询合同对全库 broad Ask 使用 Groups 作为 coverage units，不允许抽样冒充全局结论；
8. 产品流程板增加 scale-crossing、Anchor Required、large-state loading 与 broad Ask 场景；
9. 产品语言明确`当前显示 / 还有 / 被筛选 / 尚未加载 / 索引未覆盖`，不使用`核心知识 / 最重要 / orphan / 健康度`掩盖选择机制；
10. 表面证明必须覆盖 F1、F10、F100 / F10K，而不只画一套“中等规模”正常态；
11. Ardot 下一轮视觉必须证明稳定 Catalog、F100 anchor-first Network、深层 focus + context 和 Graph / List equivalent；
12. 本文不授权马上开始原型，产品定义与跨文档 QA 仍优先。

---

# 结论

> **知识库真正成熟，不是因为它能存下 10,000 条知识，而是因为存下以后，用户仍然知道自己拥有什么、当前在哪里、为什么只看见这些、还有什么没有显示，以及怎样继续和回来。**

这个产品用稳定 Catalog 保证所有权，用 Group / Topic 层级承载深度，用 Scope 与 Facet 缩小大集合，用 anchor-first Network 保持关系可读，用 Search 找回已知对象，用 Ask 综合明确范围，并用 ReturnEnvelope 让每次深入都可逆。规模增加的是知识资产，不是第二套首页、管理负担或算法控制权。
