# AI-native 个人知识库

## 知识群状态、演化与身份连续性合同 v1.0

> 日期：2026-08-09  
> 文档性质：终局产品专项合同；定义 Knowledge Group 在长期使用中的状态配置、演化、归档、恢复与 identity continuity，不是技术状态机、视觉稿、原型或研发排期  
> Canonical 产品定义：`AI-native-个人知识库-终局产品设计文档-v4.0.md`  
> 领域覆写：本文取代旧文档中把 `Seed → Forming → Established ↔ Evolving → Dormant` 视为单一互斥 `formation_phase` 的规则；旧词可以继续作为历史场景简称，但不能再作为 canonical 单轴状态  
> 相关合同：`AI-native-个人知识库-核心体验与知识群生命周期-v1.0.md`、`AI-native-个人知识库-知识群边界与跨群架构合同-v1.0.md`、`AI-native-个人知识库-Overview形成编辑与更新合同-v1.0.md`、`AI-native-个人知识库-知识群工作区与双镜连续性合同-v1.0.md`、`AI-native-个人知识库-产品对象层级与身份治理合同-v1.0.md`、`AI-native-个人知识库-关系陈述生命周期与网络可信性合同-v1.0.md`  
> 2026-08-10 Relation Endpoint 覆写：Group identity transition 不向新 scope 复制、merge 或 retarget Relations；每条受影响边建立 RelationTransitionCase，旧 relation_revision_id 与 endpoint snapshot 保持可重建  
> 当前阶段：先冻结产品本身；本文不授权制作或继续迭代原型

---

# 0. 结论先行：一个 Group 不是处在一个阶段，而是同时具有几种彼此独立的条件

旧模型把五种看似连续的状态放在同一条轴上：

```text
Seed → Forming → Established ↔ Evolving → Dormant
```

这个模型在展示少量样例时足够直观，但无法支撑一个会使用数年的真实知识库。原因是五个词并没有回答同一个问题：

- `Seed / Forming / Established` 描述 Group 当前能否提供足够清楚的方向与进入路径；
- `Evolving` 描述是否出现了会改变现有理解的重要变化；
- `Dormant` 描述用户当前是否希望它参与注意力竞争；
- `Archived` 描述它是否仍属于 current knowledge；
- Boundary revision、successor、split 与 merge 又描述 identity 是否连续。

这些条件可以同时成立。一个 Group 完全可能是：

- 已有稳定 Overview，同时正在经历高影响变化；
- 已有稳定结构，但用户暂时暂停关注；
- 结构仍在形成，同时用户暂停关注；
- 已归档，但历史版本、关系和变化依据仍完整可读；
- 内容很少，但边界与唯一进入路径已经非常清楚；
- 内容很多，但仍只有一堆来源，尚未形成可读的整体理解。

因此，本文冻结三个根本决定：

1. **Group identity 是持续存在的知识范围，不由阶段、大小、活跃度或变化数量决定。**
2. **长期状态使用正交配置，不再用一个互斥阶段承载多个问题。**
3. **状态模型服务产品正确性，不成为用户需要学习的界面。**普通页面只展示真实知识；只有某个条件改变当前动作时，才出现一句可解释说明。

新的 canonical 配置为：

```text
Group identity
  + orientation_profile   bare | structuring | oriented
  + change_condition      no_material_change | changes_available | review_due | transition_in_progress
  + attention_mode        normal | paused
  + lifecycle_state       current | archived | trash
  + boundary_condition    continuous | tension | revision_available | identity_transition_required
```

这五个维度不是五组用户标签。它们分别决定：当前如何开场、是否需要解释变化、是否降低注意力、是否仍属于 current catalog，以及是否还能保持同一个 `group_id`。

---

# 1. 为什么单一阶段会把产品带错

## 1.1 它制造了不真实的“升级路线”

`Seed → Forming → Established` 很容易被界面和指标误读为知识成熟度：内容越多、关系越多、用户越勤奋，阶段越高。最终会自然长出完成环、健康分、模板补齐任务和 AI 自动升级。这与本产品的核心品味冲突：知识库应帮助用户理解知识，不评价用户有没有把知识库经营得足够漂亮。

一个只有一条长期判断的 Group 可能非常完整；一个拥有一万份来源的 Group 也可能仍没有可读 Orientation。数量、时间与复杂度都不能当作“成熟”。

## 1.2 它让“正在变化”错误地抹掉“已经可用”

`Established → Evolving` 暗示 Group 一旦变化就不再稳定。真实情况是：最后稳定理解仍然可用，只是某些部分出现了新输入、影响或待判断事项。

若把 Evolving 作为整个 Group 的互斥阶段，产品容易：

- 把普通打开改成变化处理台；
- 用一个全局徽章覆盖所有内容；
- 要求用户先清空 Review 才能阅读；
- 用 AI 新生成的文字替代最后稳定 Overview；
- 在变化处理完后含糊地“回到成熟”。

正确语义是：**Group 仍拥有自己的 Orientation；变化只是叠加在相关对象上的可解释条件。**

## 1.3 它让“暂停关注”错误地改变知识结构

`Dormant → prior phase` 需要产品偷偷记住一个所谓“休眠前阶段”，证明 Dormant 本来就不属于形成轴。用户暂停关注不应改变 Overview、Topic、Relation、Ask scope、freshness 或 reliability；重新进入也不需要重新评价这个 Group 成熟到哪里。

正确语义是：**暂停关注只改变注意力竞争和恢复开场，不改变知识真相。**

## 1.4 它无法解释组合状态

单轴模型无法无损表达：

| 真实情况 | 单轴模型的错误 |
|---|---|
| 稳定 Overview + 高影响变化 | 必须在 Established 与 Evolving 中二选一 |
| 结构形成中 + 暂停关注 | 必须在 Forming 与 Dormant 中二选一 |
| 休眠期间出现新证据 | 无法同时表达 Dormant 与 changes available |
| 已归档但仍有历史影响 | Archived 变成“第六阶段”或丢失变化条件 |
| 内容删除后只剩一个标题 | 被解释为“降级”，而不是呈现能力改变 |
| 巨大 Group 仍然清楚可读 | 容易把规模误当成熟或自动拆分依据 |

## 1.5 它会让未来设计变成五套互不兼容的页面

如果每个阶段都有不同首页、导航、主动作和结构，用户会在同一个 Group 中不断被换产品。正确做法是保持一个 Group shell、一个 Overview identity 和同一套 Reading / Relations / Sources 语法，只让真实内容与至多一个必要提示改变。

---

# 2. 产品宪法：状态可以变化，知识群仍是同一个知识世界

以下决定在后续产品、交互、视觉和实现中同时成立：

1. **Group identity 的锚点是持续的 governing question、长期用途与可解释范围。**标题、内容量、关系度数、最近访问、形成速度和 AI 判断都不是 identity。
2. **同一 identity 始终使用同一个 `group_id`、canonical URL、Overview owner 与历史主线。**状态变化不创建新 Group，也不复制 Overview。
3. **Orientation Profile 是呈现能力投影，不是成熟度。**它可以向任意方向变化，不使用升级、降级、等级或完成语言。
4. **Change Condition 是变化影响，不是 Group 品质。**它可以与任意 Orientation、Attention 和 Lifecycle 配置并存。
5. **Attention Mode 是用户的注意力选择，不是知识新鲜度。**系统只能建议暂停，不能因未访问自动执行。
6. **Lifecycle State 由显式资源操作改变。**暂停关注不是 Archive；Archive 不是 Trash；Trash 不是 Permanent Delete。
7. **Boundary Condition 负责 identity continuity。**普通边界澄清保持 identity；核心问题被替换时使用 successor / split / merge。
8. **任何一个轴的变化都不得静默改变其他轴。**例如 Archive 不接受 Change Set，Pause 不改变 freshness，新增来源不自动修订 Boundary。
9. **系统以 accepted truth 判定有效状态。**未接受 AI proposal、候选 Topic、候选 Relation 和临时 Query 不得让 Group 看似已经形成或已经改变。
10. **状态不是用户任务列表。**没有“把 Group 做到 Oriented”“处理完所有变化”或“连续使用以保持活跃”的产品目标。
11. **状态不参与 Library 默认排序。**All Groups 的稳定目录不因 Oriented、paused、changes available、访问频率或 AI relevance 重排。
12. **状态不决定 Group 是否值得存在。**一个长期 Bare、没有 Relation 或只有一条 Knowledge 的 Group 仍是合法 Group。
13. **状态不替代内容事实。**`oriented` 不等于正确、可靠、完整或新鲜；`bare` 不等于低质量；`review_due` 不等于整个 Group 失效。
14. **变化必须定位到影响对象。**Group-level notice 是聚合入口，真正的 Diff、证据和决定落在 Overview Block、Topic、Knowledge、Relation、Source 或 Saved Answer 上。
15. **恢复以最后安全现场为准，而不是恢复所谓阶段。**Pause 或 Archive 前的 Reading Target、Map focus 和 Saved Path 可以恢复，但不会恢复一个已经过时的状态标签。
16. **大 Group 不进入另一套生命周期。**规模只改变检索、虚拟加载、Network focus 和目录跳转能力，不改变本合同。
17. **AI 不拥有高影响状态转换权。**AI 可以发现、解释和提出；Boundary revision、Pause、Archive、Split、Merge 与 accepted Knowledge Change 由用户提交。
18. **离线与 AI unavailable 不改变 canonical 状态。**派生判断暂不可刷新时保留 last-known fact 与明确计算状态，不能让 Group identity 或 current knowledge 消失。
19. **界面默认不展示内部枚举值。**只有当条件改变下一步时，才用自然语言说明发生了什么和用户可以做什么。
20. **任何状态决策都必须可解释、可恢复或明确不可恢复。**系统不得用神秘分数推动结构变化。

---

# 3. Canonical Group State Configuration

## 3.1 数据责任

```text
KnowledgeGroup
  identity
    group_id
    title
    aliases[]

  boundary
    current_boundary_revision_ref
    governing_question
    includes[]
    excludes[]

  organization
    overview_ref
    topic_roots[]
    stable_start_ref?

  state_configuration
    orientation_profile_ref
    change_condition_ref
    attention_mode
    lifecycle_state
    boundary_condition_ref

  continuity
    last_safe_workspace_state_ref?
    last_focus_at?
    lineage_refs[]
    redirect_refs[]

  history
    state_event_refs[]
    boundary_revision_refs[]
    change_set_refs[]
```

`orientation_profile_ref`、`change_condition_ref` 与 `boundary_condition_ref` 是可重建的 Projection，必须保存 reason facts 与 evaluated basis；canonical truth 仍是 accepted Overview、Topics、Knowledge、Placements、Relations、Sources、Boundary Revisions 与 Change Sets。`attention_mode` 与 `lifecycle_state` 是显式用户决定，不能由派生算法覆盖。

## 3.2 五个正交维度

| 维度 | 回答的问题 | 值 | 能否自动刷新 | 用户是否通常看见值名 |
|---|---|---|---|---|
| **Orientation Profile** | 当前 Group 能提供怎样的整体开场和进入路径 | `bare / structuring / oriented` | 可以，仅改变 Presentation | 否 |
| **Change Condition** | 是否有会影响当前理解的变化 | `no_material_change / changes_available / review_due / transition_in_progress` | 可以发现与聚合；接受高影响变化不自动 | 否，只看事实句 |
| **Attention Mode** | 用户是否希望它参与当前注意力竞争 | `normal / paused` | 不可以；只能建议 | 只有 paused 时低噪声显示 |
| **Lifecycle State** | 它是否仍属于 current knowledge | `current / archived / trash` | 不可以 | 非 current 时明确显示 |
| **Boundary Condition** | 当前范围是否仍能保持同一 identity | `continuous / tension / revision_available / identity_transition_required` | 可以发现；修订或转换不自动 | 仅有实质影响时显示 |

## 3.3 一个配置，不是一串复合标签

内部可以准确记录：

```text
orientation = oriented
change = review_due
attention = paused
lifecycle = current
boundary = continuous
```

用户不应看到：

```text
[ORIENTED] [REVIEW DUE] [DORMANT] [CURRENT] [CONTINUOUS]
```

用户只应看到与当前进入有关的一句话：

> 你曾暂停关注这个知识群；休眠后有一项变化会影响“租房担保条件”。

随后仍是原来的 Overview、目录、关系与进入路径。

---

# 4. Orientation Profile：当前怎样诚实地把整体呈现出来

## 4.1 它不是知识成熟度

Orientation Profile 只决定 Group Overview 该怎样开场。它不评价知识正确性、完整性、重要性或用户投入，不保存为不可逆历史阶段，也不提供进度百分比。

Profile 由三个事实问题共同决定：

1. 当前是否存在可进入的真实内容：Knowledge、Topic、Source-only Asset 或 accepted Overview；
2. 当前是否能诚实说明“这个范围是什么”；
3. 当前是否能提供至少一个确定、有效的继续入口：用户策展的 stable start 或基于真实结构的 deterministic fallback。

这些是能力判断，不是数量阈值。系统不得规定“至少三条 Knowledge、两个 Topic、五个 Source 才算 oriented”。

## 4.2 Bare

`bare` 表示当前只能诚实呈现 Group identity、已有内容与开始方式，尚不能提供稳定的整体方向。

典型情况：

- 只有名称；
- 只有一个问题或一条刚写下的 Knowledge；
- 只有少量 Sources，尚未形成 Current Knowledge；
- 原有内容被移动或删除，stable start 已失效；
- 用户明确保留这个范围，但暂时不想建立结构。

Presentation 责任：

1. 显示名称、可选边界与真实已有内容；
2. 有内容时先让内容可读，不用空态覆盖；
3. 完全空白时只突出一个最轻主动作`写下第一条知识`；
4. `添加资料`与`建立主题`是安静替代；
5. 不生成假 Overview、假 Topics、空 Network 或完成度。

## 4.3 Structuring

`structuring` 表示 Group 已出现多个真实方向或足够材料，但整体说明、边界或稳定进入顺序仍在形成。

典型情况：

- 已有多个 Topics，但它们的区别和顺序尚不清楚；
- 大量 Sources 已进入，只有部分已形成 Knowledge；
- 有可读内容，但尚无 accepted Orientation；
- Boundary tension 较多，Group 与相邻范围仍需澄清；
- stable start 已失效，结构 fallback 仍可用。

Presentation 责任：

1. 先显示当前真实边界与覆盖说明；
2. 展示已经成立的主要方向，而不是候选聚类；
3. 候选 Topic、Boundary Diff 与 AI 建议单独标明为 proposal；
4. 使用真实结构提供 deterministic fallback；
5. 不要求“把所有材料整理完”才能正常阅读或 Ask。

## 4.4 Oriented

`oriented` 表示普通进入时，Group 已经能回答“这是什么、目前有哪些主要方向、从哪里开始”，足以支持稳定阅读、探索与查询。

它不要求：

- 内容很多；
- 拥有多个 Topic；
- 拥有跨群 Relation；
- 所有 Knowledge 都有外部来源；
- 没有未知、冲突或变化；
- 用户近期活跃。

Presentation 责任：

1. 状态本身退到背景，不显示“已成熟”；
2. Overview、stable start、主要方向、代表理解与必要出口优先；
3. 维护、来源与历史按需可达；
4. 当变化、暂停或 Boundary condition 需要说明时，叠加一条事实 notice，不切换页面。

## 4.5 Profile 可以变化，但不叫升级或降级

以下情况可以重新计算 Profile：

- 用户写下或接受 Orientation；
- stable start 被建立、移动、归档或删除；
- Topic structure 发生 accepted Change Set；
- 当前内容被加入、移动、归档或恢复；
- Boundary Revision 改变 Overview 的解释能力；
- 派生 Projection 修复完成。

Profile 改变只会重新编排 Overview Blocks 和空态动作。它不会：

- 创建 Editorial revision；
- 重写 accepted prose；
- 接受候选 Topic；
- 修改 Boundary；
- 改变 Library 排序；
- 影响 Ask 可用性；
- 生成成就或失败记录。

---

# 5. Change Condition：变化是叠加层，不是新阶段

## 5.1 `no_material_change`

没有尚未处理、且足以影响当前整体理解的变化。这不表示 Group 静止，也不表示所有内容最新；普通编辑、低影响来源更新与不影响当前 Overview 的新 Knowledge 可以持续发生。

界面不显示“无变化”或绿色健康徽章。

## 5.2 `changes_available`

系统或用户发现一项有依据的变化，可能影响 Overview、Topic 边界、关键 Knowledge、Relation、stable start、Saved Path 或 Saved Answer，但尚未构成已确认失配。

必须记录：

- 变化来源；
- 影响对象；
- 为什么可能重要；
- 当前稳定理解仍有哪些部分成立；
- 检查或忽略的后果。

它是一条可返回的变化入口，不是任务红点。用户可以继续阅读，不需要先处理。

## 5.3 `review_due`

已经发生的 accepted truth 改变了当前策展或解释依据，例如：

- 被 Overview 引用的 Knowledge 已被修订，原判断不再完全成立；
- stable start 离开 Scope 或进入 Trash；
- 正式 Relation 的 supporting path 失效；
- Boundary Revision 使一段 accepted Overview 明显超出范围；
- Source 删除使关键 Citation 不再可核验；
- Group Split / Merge 后某些旧路径只能通过 redirect 解释。

`review_due` 必须定位到具体 affected owners。它不能把整个 Group 标成“不可靠”，也不能阻断未受影响内容。

## 5.4 `transition_in_progress`

用户已经确认一个高影响 Change Set，但转换尚未完整提交、索引或投影，例如 Split、Merge、Topic transfer、Boundary migration 或批量 Placement change。

产品必须区分：

- canonical transaction 已提交，derived projections 尚在刷新；
- transaction 仍在预览，尚未改变任何 truth；
- 部分派生失败，但 canonical truth 完整；
- transaction 失败并已安全回滚。

只有第一种进入 `transition_in_progress`。预览中的 proposal 不改变 Group 状态。

## 5.5 Change Condition 的收敛

变化不会因为用户“点了已读”而消失。它按影响对象收敛：

| 用户决定 | 后果 |
|---|---|
| 接受 Knowledge / Boundary / Relation / Structure Change | 提交对应 Change Set，刷新相关 Projection 与 alignment |
| 保留当前理解 | 记录 `knowingly_diverged` 或限定 applicability；不反复催促 |
| 证明变化不影响当前 Scope | 关闭该 impact，保留依据与历史 |
| 延后 | 保持可返回，但不占据所有入口 |
| 撤销已接受 Change Set | 回到历史 truth；若有后续修改，进入三方影响预览 |

只有全部高影响 owners 都已形成明确结果时，Group-level aggregate 才回到 `no_material_change`。这不是“回到 Established”，也不改变 Orientation Profile。

---

# 6. Attention Mode：暂停关注不改变知识

## 6.1 Normal

Group 正常参与：

- All Groups catalog；
- Search 与 Ask 的 current scope；
- Library Network；
- 用户设置的 Pins、Saved Views 与 Resume；
- 与当前知识有关的少量 contextual notices。

Normal 不等于“活跃”，也不要求最近访问。

## 6.2 Paused

Paused 的产品含义是：

> **这个知识群仍属于当前知识库，但用户暂时不希望它主动竞争注意力。**

它仍然：

- 出现在 All Groups 稳定目录；
- 可以被 Search、Ask、direct link 和 Relation 进入；
- 保留 Overview、Topics、Knowledge、Sources、Relations 与历史；
- 保留 freshness、reliability 与 change conditions 的真实值；
- 可以被 Pin，用户显式进入后可以形成 Resume checkpoint。

它默认不：

- 产生“回来整理”提醒；
- 仅因时间流逝占据 Resume；
- 在主动维护建议中反复出现；
- 因暂停而降低 Ask 权重或被标记 stale；
- 自动进入 Archive。

## 6.3 谁可以改变 Attention Mode

- 用户可以随时`暂停关注`或`恢复正常关注`；
- 系统可以基于长期未进入、无 Pin、无 current Saved Path 等事实提出一次低噪声建议；
- 用户拒绝后，没有新依据不重复建议；
- 系统不得自动 Pause；
- Search、Ask、Source update、AI recommendation 与设备离线都不得改变 Attention Mode。

## 6.4 Paused Group 的重新进入

普通打开时仍进入 canonical Overview。若距离 last focus 较久，顶部可以显示一段短 reorientation：

1. 你上次关注的范围；
2. 上次安全位置；
3. 此后真正影响理解的变化；
4. `继续原位置`、`从概览开始`、`保持暂停`。

点击`继续原位置`恢复 `last_safe_workspace_state`；点击普通目录项或 Group title 不暗中恢复深层现场。恢复现场与恢复 Attention Mode 是两个动作：用户可以临时打开 Paused Group 而不把它改回 Normal。

---

# 7. Lifecycle：Current、Archived、Trash 与 Permanent Delete

## 7.1 四种行为不能合并

| 行为 | 是否仍属 current knowledge | 是否可读 | 是否可编辑 | 默认 Search / Ask | 默认 Library / Network | 是否可恢复 |
|---|---:|---:|---:|---:|---:|---:|
| **Current + Normal** | 是 | 是 | 是 | 包含 | 包含 | 不适用 |
| **Current + Paused** | 是 | 是 | 是 | 包含 | All Groups 包含；主动注意力降低 | 直接恢复关注 |
| **Archived** | 否 | 是 | 默认只读 | 排除；可显式包含 | Archived View；关系保留但默认不绘制 | 是 |
| **Trash** | 否 | 仅 Trash / impact preview | 否 | 排除 | 排除 | 在保留期内是 |
| **Permanent Delete** | 否 | 仅 tombstone / required lineage | 否 | 排除 | 排除 | 否 |

## 7.2 Archive

Archive 表示：这个 Group 不再属于当前工作范围，但它仍是需要理解历史引用的知识资产。

Archive 必须保留：

- `group_id`、canonical URL 与 title history；
- 归档时 accepted Overview 与 Boundary；
- Topics、Knowledge Placements、Relations、Sources 与 Evidence 的可解释去向；
- Saved Answer Scope、Saved Paths、deep links 与 redirects；
- state configuration snapshot 与 last safe workspace state；
- 归档原因、时间与执行者；
- Restore 入口。

Archive 不会：

- 删除 Knowledge body 或 Source bytes；
- 接受 pending proposals；
- 把 Relations 变成失效事实；
- 把 Paused 当作归档理由自动执行；
- 自动归档 descendants、Sources 或跨群 Knowledge identities。

恢复 Archive 时回到同一个 `group_id`。恢复目标不是“归档前 phase”，而是：恢复 current lifecycle、重新计算 Orientation / Change / Boundary projections，并提供 last safe workspace state。Attention Mode 默认恢复归档前值，由用户决定是否 Normal。

## 7.3 Trash

Trash 是准备删除的可恢复状态，不是另一种 Archive：

- 从默认 Library、Search、Ask、Network 和 Relations exploration 排除；
- direct link 进入 Trash context，而不是悄悄显示正常 Group；
- 禁止内容编辑与新 Relation；
- 显示直接依赖、历史依赖、derived dependents、外部引用和恢复后果；
- Restore 回到 Trash 前 lifecycle / attention 配置并重新计算派生状态。

## 7.4 Permanent Delete

Permanent Delete 只能从 Trash 发起，并在执行前逐层说明：

1. 哪些 canonical truth 将不可恢复；
2. 哪些 Knowledge identities 属于其他 Groups，因此不会被级联删除；
3. 哪些 Topic、Placement、Attachment 与 Relation 只属于本 Group；
4. 哪些 Saved Answer、Path、deep link 与 export 将保留 tombstone；
5. 哪些 Source bytes、Evidence snapshots 或 Citation locators 仍存在；
6. 哪些 derived indexes 可以重建，因而不属于删除风险。

稳定 ID 不复用。只要已有历史、导出或外部引用，最小 tombstone 与 redirect 依据必须保留；它们说明“曾经存在及去向”，不保留用户已明确永久删除的正文。

---

# 8. Boundary Condition：什么时候仍是同一个 Group

## 8.1 Continuous

以下变化通常保持同一 Group identity：

- rename、alias 与措辞改善；
- includes / excludes 更精确；
- Applicability 被限定；
- 同一 governing question 的自然扩大或收窄；
- Contents 与既有 Boundary 之间的纠偏；
- Topic 重排、Overview 改写、Relation 增删与 Source 更新。

它们可以创建 Boundary Revision、Overview Revision 或 Change Set，但不创建新 `group_id`。

## 8.2 Tension

Tension 表示 Current Contents 与 Boundary 暂时不完全一致，例如一条 Knowledge 超出 excludes。它是范围解释，不是错误、冲突、质量问题或必须处理的待办。

合法动作：

- 保留为 context / example / bridge / reference；
- 调整当前 Placement；
- 在另一个 Group 增加 Placement；
- 提出 Boundary Revision；
- 暂时保留。

系统不得因为内容进入就自动扩大 Boundary。

## 8.3 Revision Available

系统或用户已经形成可检查 Boundary Diff，但 governing question 和长期用途仍连续。接受后：

- 保持同一 `group_id`；
- 创建新的 `GroupBoundaryRevision`；
- 刷新 Ask scope interpretation、Overview alignment、Relations applicability 与 curation impacts；
- 不自动新增、移动、归档或删除 Knowledge / Sources。

## 8.4 Identity Transition Required

以下情况不再适合普通 Boundary edit：

- governing question 被另一个问题替换；
- 主要长期用途或 Applicability 已不连续；
- 新范围无法解释旧 Overview、Ask 与 Saved Paths；
- 一个 Group 已经形成多个可独立进入的知识世界；
- 两个 Groups 被确认是同一 identity；
- 原 Group 只剩历史壳，新范围应作为 successor。

此时产品提出 successor、split、merge 或 absorb 的影响预览，不允许同一个 `group_id` 静默换成另一个知识世界。

## 8.5 结构变换与状态继承

| 变换 | identity 结果 | State Configuration 处理 |
|---|---|---|
| Rename / alias | 同一 Group | 全部状态保持；仅 title history 更新 |
| Boundary Revision | 同一 Group | Boundary 重新计算；可能触发 Overview `review_due` |
| Topic Promotion | 新 Group + 原 Topic Gateway | 新 Group 按真实内容重新解析 Orientation；不继承父 Group 的“成熟状态” |
| Group Split | 新 Groups 获得新 identities；原 Group 按用户选择保留、Gateway 化或归档 | 每个新 Scope 独立解析五个维度；每条旧 Relation 进入 Transition，successor 只得到 Candidate |
| Group Merge | 选择 canonical Group identity；其他 identity 保留 redirect / history | canonical Group 重新解析；Relations 按 identity-continuous / scope-expanded / duplicate / self-edge 逐条处理 |
| Successor | 新 Group identity；旧 Group 标明 superseded lineage | 新 Group 从自身真实内容解析；旧 Relations 保留旧 endpoints，逐条提出 successor Candidates |
| Absorb into Group | 目标 Group 保持；被吸收 Group 保留 identity 与 redirect | 被吸收 Group 归档；目标 Group 重新解析 Boundary / Orientation / Change |

Split / Merge / Successor 不自动合并 Knowledge identities，不机械切割 Overview prose，不复制 Source bytes，也不让新 Group 继承 accepted edge。所有高影响后果由 Change Set 与 RelationTransitionCase 预览和提交。

---

# 9. 同一个 Group shell 如何容纳所有配置

## 9.1 永久不变的骨架

无论配置如何，ordinary open 都遵守同一骨架：

```text
Library
  → Group canonical Overview
      → Topic Reading
          → Knowledge
              → Detail / Evidence

同时可按需展开：Relations / Sources / History / Impact
```

以下内容不因状态变化而改变：

- Group canonical URL 与 `group_id`；
- Group / Topic / Knowledge 的同一连续 reading shell；
- Overview、Structure、Relations、Sources 的责任；
- Reading Depth 与 Relation Radius 的双轴语法；
- DepthTrail、Back、Up、ReturnStack 与 ExplorationTrail；
- Search、Ask、deep link 和 Saved Path 的 exact-target 进入规则。

## 9.2 Ordinary open、Continue 与 Impact entry 分权

| 入口意图 | 打开结果 |
|---|---|
| 点击 Group title / catalog row | canonical Overview 顶部 |
| 点击`继续` | 恢复 last-safe exact scene |
| 点击 change notice | 打开 affected owner 的 Impact / Diff context |
| Search / Ask / Relation 命中 | 直接进入 exact target，Overview 通过路径可达 |
| 打开 Paused Group | Overview + 必要 reorientation；不自动恢复 Normal |
| 打开 Archived Group | 同一 Overview 的只读历史态 + Restore；不伪装 Current |
| Trash deep link | Trash context + impact / restore；不打开正常 Workspace |

Change Condition 不夺走 ordinary open；Attention Mode 不暗中改变 Continue；Lifecycle 不丢失 historical context。

## 9.3 P0 状态说明预算

Group Overview 顶部最多出现一条状态说明。多个条件同时存在时，按“是否改变当前动作”合并，而不是堆徽章：

1. `trash` 或 `archived`：先说明 lifecycle 与可用动作；
2. `identity_transition_required` 或 `transition_in_progress`：说明正在发生的结构后果；
3. `review_due`：说明具体受影响对象；
4. `paused` 且长期未进入：说明恢复语境与 since-last-focus change；
5. `bare` 且确实为空：说明如何开始；
6. 其余条件退到 Impact、History 或按需说明。

一条 notice 可以组合事实，例如：

> 这个知识群已归档；归档前“担保条件”有一项尚未检查的来源变化。你可以查看历史或先恢复。

禁止：

- 状态徽章墙；
- 红点计数；
- “健康 / 不健康”色彩；
- 每次打开重复弹窗；
- 用状态替代内容标题与边界；
- 把所有变化汇总成后台 Inbox 作为 Group 首页。

---

# 10. Overview 的组合语法

## 10.1 一个 identity、一棵 content tree

同一 Group 全程只有一个 `overview_id` 与一棵 accepted content tree。状态配置只决定哪些已有 Blocks 在当前入口被优先显示，以及是否叠加一条事实 notice。

```text
accepted Overview truth
  + live Structure / Relation / Source projections
  + Orientation presentation profile
  + at most one state notice
  = current Group Overview surface
```

任何 Profile 或 Condition 改变都不自动：

- 生成新的 Editorial prose；
- 覆盖 accepted Overview；
- 创建一个“Evolving Overview”副本；
- 为 Paused / Archived 复制静态页面；
- 把 Projection refresh 伪装成用户 revision。

## 10.2 组合矩阵

| 配置 | Overview 先显示什么 | 仍保持什么 |
|---|---|---|
| Bare + normal + no change | 名称、边界、真实内容、一个首要开始动作 | 同一 shell、Search / Ask、History |
| Structuring + normal + changes available | 当前真实方向 + 一条局部变化说明 | accepted content 与结构 fallback |
| Oriented + normal + no change | Overview、stable start、主要方向 | 状态完全退到背景 |
| Oriented + normal + review due | 最后稳定理解 + 具体 affected notice | 未受影响分支可继续阅读 |
| Oriented + paused + no change | 最后稳定 Overview + 上次安全位置 | Search / Ask / Relations 继续有效 |
| Oriented + paused + changes available | reorientation + since-last-focus impact | 不自动恢复 Attention，不要求先 Review |
| Structuring + paused | 真实方向 + 上次位置 | 不因 Pause 伪装成 Oriented 或 Archived |
| Any + archived | 归档说明 + 归档时 Overview | links、history、sources、restore |

## 10.3 Orientation 与 Alignment 分开

`orientation_profile = oriented` 只说明页面能提供可靠进入方向；Overview 自己仍使用：

```text
aligned | changes_available | review_due | knowingly_diverged
```

一个 Overview 可以同时 `oriented + review_due`：用户仍能理解整体，只是某段 accepted prose 的依据已改变。反之，一个 Bare Group 也可能 `aligned`，因为它没有冒充已有一篇完整 Overview。

---

# 11. Topic、Knowledge、Relation 与 Source 的状态边界

## 11.1 Topic 与 Knowledge 不继承 Group 标签

Group 的 Orientation Profile 不向下传播成 Topic / Knowledge 的成熟标签。每个 Topic Opening 根据自身真实内容使用 Bare / Compact / Editorial 密度；每条 Knowledge 维护自己的 revision、freshness、conflict 与 evidence 状态。

## 11.2 Relation 不决定 Orientation

- 没有 Group Relation 的 Group 可以是 `oriented`；
- 关系很多的 Group 可以仍是 `bare` 或 `structuring`；
- Relation review_due 只在它承担 Overview、Path 或跨群判断时聚合到 Group change condition；它仍可能是 maintained current Relation；
- RelationCandidate 不进入 Network truth，也不改变任何 Profile；dismissed Candidate 不成为 rejected Relation；
- Relation 的 ended、superseded、retracted、archived 与 review_due 分属不同责任，不能聚合成 Group“健康度”。

## 11.3 Source 变化不等于 Group 变化

新增、解析、修订或删除 Source 先改变 Source Truth 与 Evidence：

- 只有当它影响 accepted Knowledge、Overview、Relation、Path 或 Answer 时，才产生 `changes_available / review_due`；
- Source-only 数量不决定 Orientation；
- parsing failed 不使 Group 退回 Bare；
- Citation 不可核验只影响相关 Claim，不把整个 Group 标成 stale；
- Source freshness 与 Attention / Lifecycle 分开。

## 11.4 Conflict、Freshness、Reliability 继续是对象事实

状态配置不得吞并：

- Knowledge conflict；
- Source freshness；
- Citation availability；
- Answer support basis；
- Overview alignment；
- Relation standing；
- index completeness。

这些事实可以触发一条具体 impact，但不能被压缩成 Group health score。

---

# 12. 规模不改变状态语法

## 12.1 数量不是阶段

以下都不能直接改变 Orientation、Attention、Lifecycle 或 Boundary：

- Knowledge / Topic / Source 数量；
- Group 存在时间；
- 最近访问与编辑频率；
- Relation 度数与图中心性；
- embedding cluster 稳定度；
- AI confidence；
- 搜索点击率。

数量可以触发性能、导航或检查建议，但不能写成“知识群已经成熟 / 退化”。

## 12.2 一个大型 Group 仍然使用同一产品

当 Group 从 10 条增长到 10,000 条：

- ordinary open 仍是 canonical Overview；
- Overview 仍是导读，不变成运营 Dashboard；
- Topic hierarchy 使用 virtualized tree、jump、filter 与 progressive loading；
- Relation view 使用 anchor-first focus + context，不画 hairball；
- Ask 明确 Effective Scope、coverage 与未索引部分；
- All Knowledge 保持穷尽列表能力；
- state notice 预算不增加。

## 12.3 Split 的依据是语义独立，不是规模

系统只有在出现多个独立 governing questions、独立再次进入意图、独立 Overview 与稳定跨群关系时，才可以提出 Split。性能过慢、Topic 太多或图太密只能触发技术与导航优化，不能迫使用户改变知识本体。

---

# 13. AI 在 Group 演化中的边界

## 13.1 AI 可以做什么

- 依据 accepted truth 解释当前 Orientation Profile；
- 发现新的 Boundary tension、Overview misalignment 与 affected objects；
- 生成有依据的 Topic、Relation、Boundary、Split / Merge 与 Overview Diff；
- 汇总 since-last-focus changes；
- 解释某项变化为什么只影响一个分支；
- 在 Ask 中使用 Current / Paused Group，并明确是否显式包含 Archived；
- 在用户接受后刷新派生 Projection。

## 13.2 AI 不能做什么

- 用内容数量或 embedding confidence 宣布 Group 成熟；
- 自动把 Bare 改写成一篇完整 Overview；
- 因新来源出现就把整个 Group 切成 Evolving 页面；
- 因未访问自动 Pause 或 Archive；
- 自动修订 Boundary；
- 自动执行 Split、Merge、Absorb 或 Successor；
- 为了让 `review_due` 消失而静默改写 accepted content；
- 把 Paused / Archived 内容从 explicit Scope 中隐藏却不说明；
- 把状态枚举写进回答，替代真实范围与证据说明。

## 13.3 Ask 行为

| Group condition | Ask 默认行为 |
|---|---|
| Bare | 可以查询已有 Current Knowledge / Sources；明确覆盖很少，不用模型常识填满内部答案 |
| Structuring | 使用真实 Scope；说明尚未形成完整 Orientation 不等于查询失败 |
| Oriented | 正常查询；状态不提高权威性 |
| Changes available / review due | 回答可使用未受影响 Current Knowledge；受影响 Claim 显示 basis 与变化提示 |
| Paused | 仍属于 current knowledge，默认可用 |
| Archived | 默认排除；显式选择时清楚标明 historical / archived basis |
| Trash | 排除 |

AI unavailable 时，已有 Overview、目录、关系、来源、history、state reason facts 与 saved answers 仍可读；只暂停新的推断与 Ask generation。

---

# 14. 用户语言合同

## 14.1 默认不用内部词

| 内部条件 | 推荐用户语言 | 禁止语言 |
|---|---|---|
| `bare` 且空 | `这个知识群刚刚开始` | `成熟度 0%`、`待完善` |
| `structuring` | `已有几个真实方向，整体说明仍在形成` | `结构完成度 43%` |
| `oriented` | 默认不显示状态句 | `成熟知识群`、`已升级` |
| `changes_available` | `有一项变化可能影响当前理解` | `你的知识已过期` |
| `review_due` | `一项已发生的变化使“X”需要检查` | `知识群不健康` |
| `paused` | `你曾暂停关注这个知识群` | `长期不活跃`、`沉睡资产` |
| `archived` | `此知识群已归档；内容和历史仍可查看` | `已删除`、`失效` |
| `tension` | `这条知识位于本群，但超出当前边界` | `错误归类` |
| `identity_transition_required` | `当前范围已经形成两个可独立进入的知识世界` | `系统建议优化结构` |

## 14.2 每句话回答三个问题

可见状态句必须尽量回答：

1. 发生了什么事实；
2. 影响哪里；
3. 用户现在可以做什么。

例如：

> 新加入的 2026 年法规只影响“担保人收入要求”；原 Overview 其他部分仍可阅读。查看变化或继续原路径。

而不是：

> 本知识群处于演化阶段，请完成 3 项 Review。

---

# 15. 事件与轴变化合同

每个事件只改变自己有权改变的责任：

| 事件 | 可改变 | 不得顺带改变 |
|---|---|---|
| 新建空 Group | identity、Boundary 初始 revision、`bare` | Attention、Archive、假 Overview / Topics |
| 写入第一条 Knowledge | Current Contents、Orientation projection | Boundary、Attention、Relation、accepted Overview |
| 导入大量 Sources | Attachments、Source Truth、可能 `structuring` | 自动形成 Knowledge、自动 `oriented` |
| 接受 Overview / stable start | Overview revision、Orientation projection | Lifecycle、Boundary identity |
| AI 生成 Topic proposal | Proposal only | Current Topics、Orientation、Library Network |
| 新证据可能影响 Claim | Change condition | 自动修订 Claim / Overview、Pause / Archive |
| 用户接受 Knowledge Change | Knowledge revision、affected projections | 无关 Topics / Relations / Boundary |
| 用户暂停关注 | Attention = paused | Orientation、freshness、Ask membership、Lifecycle |
| 用户重新进入 | Workspace state / session | 自动恢复 Attention、清除 changes |
| 用户 Archive | Lifecycle = archived | 删除内容、接受 proposals、改变 identity |
| 用户 Restore Archive | Lifecycle = current；重新解析派生状态 | 创建新 Group、重置 Overview history |
| 用户移入 Trash | Lifecycle = trash | 永久删除、级联删除共享 Knowledge |
| 用户 Restore Trash | 恢复前配置；重新解析 | 新 identity、丢失 redirects |
| 接受 Boundary Revision | Boundary revision、affected alignments | 自动移动 Contents |
| 接受 Split / Merge | identities、Placements、lineage、redirects、相关 projections | 自动合并 Knowledge identities、机械拼 prose |
| Permanent Delete | 已确认的不可逆 truth | ID 复用、未说明的级联删除 |

---

# 16. 代表性长期场景

## 16.1 空白“认知科学”

用户只输入名称。配置为：

```text
bare + no_material_change + normal + current + continuous
```

页面显示名称、可选边界、`写下第一条知识`，以及安静的`添加资料 / 建立主题`。它已经是合法 Group，但没有假 Overview、假 Network 或“完成度 0%”。

## 16.2 一条判断已经足够形成清楚入口

用户写下一条长篇 Knowledge，并补充清楚边界。Group 没有多个 Topics，但可以说明范围并直接进入这条 Knowledge。系统可以解析为 `oriented`；它不需要为了“成形”制造第二个 Topic。

## 16.3 导入 2,000 份来源

Group 内容很多，但只有 Source Attachments 与部分解析结果。配置可能是：

```text
structuring + no_material_change + normal + current + continuous
```

产品展示来源覆盖、已形成的 Current Knowledge 与确定性结构入口，不因数量宣称成熟，也不自动写一篇宏大 Overview。

## 16.4 稳定知识群出现关键变化

“法国租房”已有可用 Overview。新法规可能改变担保条件：

```text
oriented + changes_available + normal + current + continuous
```

ordinary open 仍显示最后稳定 Overview，顶部仅一条 notice 指向受影响分支。用户可以继续阅读其他内容。确认法规适用后，相关 Knowledge / Overview 进入可检查 Diff；Profile 始终可以保持 `oriented`。

## 16.5 Paused 期间出现变化

用户曾暂停关注“法国租房”，其间担保法规变化：

```text
oriented + changes_available + paused + current + continuous
```

重新打开时显示上次范围、last-safe position 和一项 since-last-focus impact。用户可以`从概览开始`、`继续原位置`或`保持暂停`；任何选择都不自动接受变化。

## 16.6 结构仍在形成，但被暂停关注

“认知科学”有多个真实方向，没有 accepted Orientation，用户暂时搁置：

```text
structuring + no_material_change + paused + current + continuous
```

它仍在 All Groups、Search 和 Ask 中。再次进入显示真实方向，不会先“恢复到 Forming”，因为它从未离开自己的结构事实。

## 16.7 内容移走后呈现能力减少

一个 Group 的唯一 Knowledge 被移动到另一个 Group，原 Group 仍被用户保留。Orientation 可能从 `oriented` 重新解析为 `bare`，但：

- `group_id`、Boundary、history 与 URL 不变；
- 这不是降级；
- 原 deep links 指向 Knowledge 的新 Placement 或历史语境；
- 页面诚实说明当前范围尚无内容。

## 16.8 Boundary tension 后选择保留例外

一条模型训练知识被放进“AI Agent 产品设计”，超出 excludes。Group 标记 tension，但用户选择作为 background reference 保留：

- Boundary 不自动扩大；
- Knowledge 不自动移动；
- tension 记录已解释，不反复提醒；
- Orientation、Attention、Lifecycle 均不改变。

## 16.9 Governing question 被替换

用户想把“AI Agent 产品设计”改造成“所有 AI 行业新闻”。这不是 rename 或自然扩大。产品提出 successor：

- 旧 Group 保留原 identity、Overview、Ask history 与 links；
- 新 Group 获得新 identity 和独立 Boundary；
- 用户逐项决定 Knowledge Placements、Sources、Relations 与 Saved Paths；
- 旧 Group 可以归档并指向 successor；
- 新 Group 不继承一个虚构的 Established 状态。

## 16.10 一个 Group 分成两个知识世界

“法国生活”逐渐形成“法国租房”与“法国行政”两个独立范围。Split 预览：

- 每个新 Group 有独立 Boundary 与 Overview；
- shared Knowledge 可保留多个 Placements，不复制正文；
- old Overview prose 不机械一分为二；
- 原 Group 可以保留为 Gateway / historical hub 或归档；
- 原 Group 的 Relations 逐条进入 Transition；两个新 Groups 只获得各自适用的 RelationCandidates，无法判断时不画新边；
- 三个 Groups 分别解析自身状态配置。

## 16.11 已归档知识仍解释历史答案

Group Archive 后，一条旧 Saved Answer 仍引用它。Answer 可以打开 archived Group 的 exact Knowledge / Evidence，并显示 historical basis；默认全库 Ask 不再使用 Archived，除非用户显式包含。

## 16.12 10,000 条知识仍是同一个 Group

只要 governing question 连续、Overview 仍能导向主要方向、层级与查询可用，Group 不因规模 Split、Archive 或“进入下一成熟阶段”。产品只增加 jump、filter、progressive loading、anchor-first Network 与 coverage disclosure。

---

# 17. 可验证验收标准

## 17.1 互不覆盖

**Given** 一个 Group 已 `oriented` 且用户将其设为 Paused  
**When** 新证据产生 `changes_available`  
**Then** Orientation、Change 与 Attention 三个事实同时保留；界面合成一条 reorientation / impact 说明，不丢失任何轴，也不生成三个徽章。

## 17.2 变化不夺走阅读

**Given** 一个可稳定使用的 Group 出现高影响变化  
**When** 用户普通打开 Group  
**Then** 仍进入同一 Overview；最后稳定理解和未受影响路径可读；只有受影响对象显示变化入口；用户无需先处理 Review。

## 17.3 Paused 不等于 stale

**Given** Group 半年未打开但 Sources 与 Knowledge 仍可靠  
**When** 用户进入  
**Then** 产品说明暂停与上次焦点，不声称内容过期、不降低 Ask 权重、不自动 Archive。

## 17.4 Bare 不等于失败

**Given** Group 只有名称或一条 Knowledge  
**When** 用户进入  
**Then** Group、Search、Ask、History 与写作均可用；无完成度、无假结构、无补模板任务。

## 17.5 Oriented 不等于正确或完成

**Given** Group 有清楚 Overview 与 stable start，但存在一个明确未知  
**When** 用户阅读  
**Then** Group 仍可提供稳定 Orientation；未知被如实显示；界面不把 Oriented 写成“已完成 / 已验证”。

## 17.6 Profile 变化不改正文

**Given** Group 因 stable start 建立而从 `structuring` 解析为 `oriented`  
**When** Profile 刷新  
**Then** 只改变 Presentation；不创建 Editorial revision、不接受 AI prose、不重排 Library、不改变 Boundary。

## 17.7 删除内容不改 identity

**Given** Group 的主要内容被移动或归档  
**When** Orientation 重新解析为 `bare`  
**Then** `group_id`、URL、Boundary、Overview history、Relations lineage 与 Saved Answer Scope 仍可解释。

## 17.8 Proposal 零副作用

**Given** AI 生成 Topic、Boundary 与 Split proposal  
**When** 用户拒绝  
**Then** Current Contents、Orientation、Boundary、Library Network、Ask scope 与 identity 均不改变；同一依据不重复催促。

## 17.9 Archive 与 Pause 分开

**Given** 一个 Paused Group 仍是 current knowledge  
**When** 用户执行 Archive  
**Then** Lifecycle 独立改变；Archive 前 Attention snapshot 保留；默认 Ask / Library 按 Archive 规则处理；Restore 回到同一 identity。

## 17.10 Archive 与 Delete 分开

**Given** Group 已 Archived  
**When** 用户打开旧 deep link  
**Then** 内容、历史、来源与 Restore 可达；只有移入 Trash 后才进入删除路径；Archive 不伪装 Delete。

## 17.11 Restore 不恢复旧标签

**Given** Archived Group 在归档期间有 Source 与 index 状态变化  
**When** Restore  
**Then** lifecycle 回到 current，系统基于当前 truth 重新解析 Orientation / Change / Boundary；不机械恢复一个旧 `formation_phase`。

## 17.12 Boundary Revision 不搬内容

**Given** 用户接受 Boundary 收窄  
**When** 新 revision 生效  
**Then** Knowledge / Source 去向不自动改变；超出范围内容形成可解释 tension；Overview 与 Ask impacts 可检查。

## 17.13 Successor 保留连续性证据

**Given** governing question 被替换  
**When** 用户创建 successor  
**Then** 新旧 Groups 使用不同 identities；旧 URL、Overview、Query history 与 redirects 保留；新 Group 按自身 truth 解析状态。

## 17.14 Split / Merge 不复制复合状态

**Given** 一个 `oriented + changes_available + paused` Group 被 Split  
**When** Change Set 提交  
**Then** 每个新 Scope 分别解析 Orientation / Change / Attention / Boundary；不把原组合标签盲目复制到所有新 Groups。

## 17.15 大小不触发状态变换

**Given** Group 从 100 条增长到 10,000 条 Knowledge  
**When** 它的 governing question 和 Orientation 仍连续  
**Then** identity、ordinary open 与 state grammar 不变；只有加载、导航、Network focus 与 coverage 行为扩展。

## 17.16 AI unavailable

**Given** AI 与 embedding 暂不可用  
**When** 用户打开任意配置 Group  
**Then** accepted Overview、目录、关系、来源、state reason facts、history 与手工编辑仍可用；系统不因无法重算而改变状态。

## 17.17 P0 复杂度预算

**Given** 同一 Group 同时 Archived、Paused、review_due 且存在 Boundary tension  
**When** 用户打开  
**Then** 顶部最多一条合成说明，优先说明 Archive 与可用动作；其他事实在 Impact / History 按需展开，不显示标签墙。

## 17.18 Ask 范围诚实

**Given** Query Scope 包含 Current、Paused 与 Archived Groups  
**When** 用户未显式选择 Archived  
**Then** Current 与 Paused 正常参与，Archived 默认排除并在 coverage 中说明；Trash 永不参与。

## 17.19 State event 可审计

**Given** Attention、Lifecycle 或 Boundary 被改变  
**When** 用户查看 History  
**Then** 可以看见谁在何时因何操作改变了哪一轴；派生 Profile refresh 与 accepted content revision 分开记录。

## 17.20 同一 shell

**Given** 用户依次打开 Bare、Oriented + review_due、Paused 和 Archived Groups  
**When** 比较导航与进入行为  
**Then** 四者使用同一 Library → Group → Topic → Knowledge 主干、同一关系镜头与返回语义；只改变内容权重、权限和一条必要说明。

---

# 18. 指标、反指标与实证问题

## 18.1 应观察的产品质量

- **Reorientation Success**：长时间离开后，用户能否在两分钟内说清 Group 范围、上次位置与最重要变化；
- **State Explanation Success**：用户能否用自然语言说清 notice 为什么出现、影响哪里；
- **False Change Notice Rate**：被用户判断为与当前理解无关的高影响提示比例；
- **Identity Continuity Success**：rename、revision、pause、archive、restore 后 old links、Saved Paths、Answers 与历史仍可解释比例；
- **Boundary Transition Precision**：普通 revision 与 successor / split / merge 是否被正确区分；
- **Archive Recovery Success**：恢复后是否回到同一 Group，且 current truth、workspace state 与 lineage 完整；
- **Unaffected Reading Continuity**：有 review_due 时，未受影响知识能否继续阅读与查询；
- **Composite State Comprehension**：用户能否理解“可用但有变化”“暂停但仍属当前知识”“归档但未删除”；
- **Notice Silence Quality**：无必要动作时，状态是否真正退到背景。

## 18.2 禁止作为成功指标

- Oriented Group 比例；
- 从 Bare 到 Oriented 的平均天数；
- 每个 Group 的 Topic / Relation / Source 数量；
- Review 清空率；
- Paused Group 唤醒率；
- Archive 率；
- “知识健康分”；
- 连续使用天数；
- AI 自动结构接受率；
- 大 Group 被拆分的数量。

这些数字可以用于故障诊断，但不能成为推动用户改变知识结构的增长目标。

## 18.3 仍待真实验证

以下是产品决定，不是假装已经得到用户证实：

1. Bare / Structuring / Oriented 三种 Presentation 是否足够覆盖真实内容形态；
2. `暂停关注`是否比`休眠`更容易理解；
3. Paused Group 默认参与 broad Ask 是否符合用户预期；
4. Archived 默认排除 Ask、但 explicit include 是否清楚；
5. P0 一条合成 notice 能否承载多个条件而不模糊；
6. 用户能否区分 Boundary revision 与 successor；
7. `review_due`怎样避免制造维护焦虑；
8. Restore 后“重新解析而不是恢复阶段”是否容易预期。

这些问题需要以后用真实知识内容、长期返回任务和可用性测试验证；不能用设计团队内部理解代替。

---

# 19. 研究依据与产品推论边界

## 19.1 正交状态与历史恢复

W3C SCXML 明确定义了 parallel state：多个子状态可以同时 active，并各自独立响应事件；它也定义 history state，用于退出后恢复此前 active configuration。[W3C SCXML](https://www.w3.org/TR/scxml/)

**[研究事实]**复杂对象不必被压缩成一个互斥状态；并行条件与恢复现场是成熟状态建模中的正式能力。  
**[产品推论]**本产品应把 Orientation、Change、Attention、Lifecycle 与 Boundary continuity 分开，并将恢复目标定义为 last-safe workspace configuration，而不是“休眠前 phase”。SCXML 不直接证明本文五个具体维度是唯一答案。

## 19.2 Revision 与 identity lineage

W3C PROV-O 将 `wasRevisionOf` 定义为一种 derivation：新实体是原实体的修订版本，并保留相当部分原内容。[W3C PROV-O](https://www.w3.org/TR/prov-o/#wasRevisionOf)

**[研究事实]**版本修订、派生和 provenance 可以被明确建模，而不是只保留一个当前值。  
**[产品推论]**Boundary Revision、Overview Revision 与 successor / split / merge 应分别保留 lineage；普通修订保持同一 Group continuity，核心用途不连续时建立新 identity。PROV-O 不直接决定本产品的 Group identity 门槛。

## 19.3 Archive 与 Delete 分开

Notion 官方帮助说明 Archive 用于标记内容“不再 current”而不删除，归档页面仍可访问、链接继续有效，并可恢复；Trash 与版本历史另行处理。[Notion Archive / Trash / Version history](https://www.notion.com/help/duplicate-delete-and-restore-content)

Confluence 官方帮助说明 archived content 保留查看、历史、附件、链接与恢复能力，同时限制编辑；恢复后回到内容树。[Confluence Archive](https://support.atlassian.com/confluence-cloud/docs/archive-pages/)

GitHub Projects 官方文档把 Archive、Restore 与 Permanent Delete 明确分开。[GitHub Projects Archive](https://docs.github.com/en/issues/planning-and-tracking-with-projects/managing-items-in-your-project/archiving-items-from-your-project)

**[研究事实]**成熟知识与工作工具普遍把“暂不处于当前视图”“仍可恢复”和“永久删除”分成不同操作，并保留历史与链接。  
**[产品推论]**本产品应区分 Paused、Archived、Trash 与 Permanent Delete，并让 old links 和 historical Answers 继续可解释。竞品实现不直接证明本文具体默认 Search / Ask 范围已经通过用户验证。

---

# 20. 对 Canonical、专项合同与未来设计的约束

## 20.1 文档同步规则

以下旧表达失效：

- `formation_phase = Seed / Forming / Established / Evolving / Dormant`；
- `Established → Evolving → Established`；
- `任一 phase → Dormant → prior phase`；
- “五个形成阶段”；
- Group 状态随内容数量升级或回退；
- Archived 是形成阶段之外的第六项，但仍和五项共用一张互斥表。

替代规则：

- Seed、Forming、Established 仅可作为 Bare、Structuring、Oriented fixture 的历史简称；
- Evolving 改读为 Change Condition overlay；
- Dormant 改读为 `attention_mode = paused`；
- Archived / Trash 只属于 Lifecycle；
- Boundary continuity 独立决定 ordinary revision 或 identity transition；
- 下游文档若尚未逐段更新，以本文拥有领域覆写权。

## 20.2 未来视觉证据必须证明组合，而不是五张换皮页面

进入 Surface / Frame 设计后，至少使用以下真实 fixtures：

1. Bare + Current：完全空白或只有一条 Knowledge；
2. Structuring + Source-heavy：材料多但整体仍在形成；
3. Oriented + no change：低噪声普通日常；
4. Oriented + review_due：稳定理解与变化共存；
5. Oriented + Paused + changes available：长时间返回；
6. Archived + historical Answer link：只读与恢复；
7. Boundary tension：内容与范围暂时不一致；
8. Identity transition required：successor / split / merge 影响预览；
9. Large Group：同一状态语法下的规模化导航；
10. AI unavailable / partial index：canonical truth 不消失。

这些 fixtures 必须使用同一个 Group shell、Overview identity、DepthTrail、Relations、Sources 与 return grammar。设计若为每个 fixture创造不同应用结构，即使单张视觉漂亮，也不满足产品定义。

## 20.3 当前仍不授权原型

本文完成的是产品本体与长期语法的冻结，不是视觉方向选择。下一步仍应继续审计产品对象、核心 journeys、失败恢复与跨合同一致性；只有用户明确允许进入设计后，才制作 Surface skeleton、真实内容 fixture 与高保真视觉。

---

# 结论

> **知识群不是从“幼小”升级到“成熟”、再因为变化或沉寂换成另一种页面的项目。它是一个持续存在的知识范围：有时内容很少，有时已经能清楚导读；有时正在发生变化，有时用户暂时不关注；有时仍属于当前知识，有时被归档；只有当它要回答的问题本身不再连续，才需要新的 Group identity。**

这套模型的产品价值不在于状态更复杂，而在于它让用户看到的产品更安静：同一个 Overview、同一个知识层级、同一个关系空间、同一条返回路径。内部复杂度只用于保证历史、变化、恢复和 identity 不说谎；界面注意力继续留给知识本身。
