# AI-native 个人知识库

## 完整性审计与产品修订 v1.1 — 从“AI 编译与阅读系统”补全为真正的知识库

> 审计日期：2026-08-06  
> 审计对象：产品定义 v3.0、交互架构 v1.0、场景压力测试 v1.0、九块流程板与 62 项覆盖合同、Ardot 七张概念图与三种新视觉方向  
> 文档性质：结构审计与冻结修订，不是新功能愿望清单，也不是 MVP 排期  
> Canonical 产品定义：`AI-native-个人知识库-终局产品设计文档-v4.0.md`；本文档保留审计历史，不得反向改写 v4.0  
> 2026-08-07 Library-first 覆写：当前只有一个 Knowledge Library 主入口，知识群 / Knowledge Network 是同一知识库的两种视图，Home 的继续责任并入 Library Resume，Atlas 变为 R3 Network，Sources 变为 supporting utility；Overview / Structure / Relations / Sources 是连续 Group 场景中的责任而非四个同权 Roots。本文后文“四 Places / 四 Roots / 81 屏”只保留为历史审计语境，完整性基线以`AI-native-个人知识库-核心心智模型与连续探索合同-v1.0.md`的十二个 proof families 为准  
> 2026-08-09 Scale Invariance 覆写：本文后文以小数据推断的大库首页、自动聚合与 Home order 只作历史；当前完整性必须证明 F1 / F10 / F100 / F10K 使用同一 Library、穷尽 Catalog、focus + context、Anchor Required Network、Group coverage Ask 与 Graph / List / mobile / keyboard 等价。完整规则见`AI-native-个人知识库-规模化知识空间与长期可浏览性合同-v1.0.md`  
> 2026-08-09 Group State 覆写：本文后文 Seed / Forming / Established / Evolving / Dormant 单轴表述只作历史审计语境；当前完整性必须证明 Orientation、Change、Attention、Lifecycle 与 Boundary continuity 可组合且共享同一 Group shell。完整规则见`AI-native-个人知识库-知识群状态演化与身份连续性合同-v1.0.md`  
> 2026-08-07 历史边界：本文关于 Working Branch、Accepted Revision、auto-save 与“完成并采用”的结论已被新直接写作合同推翻，只作为当时发现产品缺口的审计证据读取；当前模型是 Buffer / Recovery / Direct Edit Commit / Current / Draft / Proposal / Sync / Projection  
> 2026-08-10 Relation Lifecycle 覆写：旧文档把 Candidate、证据可信度、时间有效性和对象生命周期压进 Relation 状态的做法已失效；当前必须分别证明 Candidate、Revision、Evidence、Challenge、Disposition、Change Condition、Lifecycle、Current / Suggested / History 与 Split / Merge Transition。完整合同见`AI-native-个人知识库-关系陈述生命周期与网络可信性合同-v1.0.md`  
> 2026-08-10 第二真实夹具覆写：`AI-native-个人知识库-第二真实端到端夹具-概念学习、多语境复用与群关系-v1.0.md`已证明产品不只处理时效资格规则，也能处理稳定概念层级、研究比较、多 Placement、父子 Question、Shared Knowledge 与同 pair 多关系；它新增的是 Evidence condition 与显示责任，不是学习模块、任务中心或第二套 ontology  
> 审计时结论：产品的“理解、查询、探索、证据与演化”已形成骨架，但“直接创作、对象生命周期、迁移与长期所有权”尚不完整；这些缺口已在本修订及同步文档中补齐  
> 后续核心体验复核：`AI-native-个人知识库-核心体验与知识群生命周期-v1.0.md`
> 后续知识深度与关系复核：`AI-native-个人知识库-知识深度与关系探索合同-v1.0.md`
> 后续知识形成与维护复核：`AI-native-个人知识库-知识形成与维护循环-v1.0.md`
> 后续知识群边界与跨群架构复核：`AI-native-个人知识库-知识群边界与跨群架构合同-v1.0.md`
> 后续知识节点粒度与内容组成复核：`AI-native-个人知识库-知识节点粒度与内容组成合同-v1.0.md`
> 后续 Overview 形成、编辑与更新复核：`AI-native-个人知识库-Overview形成编辑与更新合同-v1.0.md`
> 后续 AI 查询与知识回答复核：`AI-native-个人知识库-AI查询与知识回答合同-v1.0.md`
> 后续搜索定位复核：`AI-native-个人知识库-搜索定位与知识找回合同-v1.0.md`
> 后续 Library 浏览复核：`AI-native-个人知识库-Library浏览与动态视图合同-v1.0.md`
> 后续来源证据复核：`AI-native-个人知识库-来源证据与可追溯性合同-v1.0.md`
> 后续直接创作复核：`AI-native-个人知识库-直接创作编辑与版本历史合同-v1.0.md`
> 后续属性、Facet 与适用条件复核：`AI-native-个人知识库-属性Facet与适用条件合同-v1.0.md`
> 后续产品对象层级与身份治理复核：`AI-native-个人知识库-产品对象层级与身份治理合同-v1.0.md`
> 后续产品表面架构与完整设计证明复核：`AI-native-个人知识库-产品表面架构与完整设计证明合同-v1.0.md`
> 后续地点编排与跨地点连续性复核：`AI-native-个人知识库-地点编排信息归属与跨地点连续性合同-v1.0.md`
> 后续知识群工作区与双镜连续性复核：`AI-native-个人知识库-知识群工作区与双镜连续性合同-v1.0.md`
> 后续核心导航与复杂度收敛复核：`AI-native-个人知识库-核心导航与复杂度收敛合同-v1.0.md`

---

# 0. 执行判断

现有规格已经成功纠正了两个早期偏差：

1. 产品不再被 Project Continuity 定义，而被明确收敛为个人知识库；
2. 设计不再由七张孤立概念图定义，而由 App Shell、Selection State、L0–L5、双镜联动、九块流程板与 62 项覆盖合同共同定义。

但这一轮复核发现，**“62 项已覆盖”不能继续被当作完整产品的同义词。**

62 项主要证明了以下能力：

- 进入并理解知识群；
- 从 Overview 深入到 Evidence；
- 沿关系横向探索；
- Search 与 Ask；
- 资料 Capture 与 AI Knowledge Compiler；
- 冲突、版本与来源维护；
- 离线、失败与大规模状态。

它没有完整证明以下最基础的知识库任务：

- 不导入资料时，用户能否直接创建一个空知识群；
- 用户能否像写知识一样直接创建、编辑和重组 Node；
- 用户能否明确编辑 canonical content 与某个 Group 中的 contextual summary；
- 用户能否手工建立、修改或撤销关系，而不是只处理 AI 建议；
- 用户能否安全地归档、移出、删除和恢复对象；
- 用户能否迁入旧知识库，并在任何时候完整迁出；
- 本地存储损坏、索引重建、设备冲突和模型策略如何被理解与控制。

因此，当前产品更接近一套优秀的 **AI 编译、阅读与知识推理系统**，但还没有在所有基本任务上证明自己是一个 **用户可以亲手建设、长期居住并带走全部资产的知识库**。

---

# 1. 完整产品的五个闭环

完整性不再按页面数量判断，而按五个闭环判断：

| 闭环 | 用户问题 | 当前状态 | 修订要求 |
|---|---|---|---|
| Build / 建设 | 我如何把想法与资料变成自己的知识？ | Capture 深，直接创作浅 | 手工创建、编辑、关系与层级操作必须成为一级能力 |
| Understand / 理解 | 我如何从整体逐层理解到证据？ | 强 | 保留 L0–L5、Overview 与 Evidence |
| Use / 使用 | 我如何查找、提问和探索？ | 强 | 保留 Search / Ask / Graph 联动 |
| Maintain / 维护 | 知识变化、冲突或重复时怎么办？ | 强 | 把直接编辑也纳入 Change Set 与影响传播 |
| Own / 拥有 | 我能否在离线、迁移、备份和恢复时继续拥有它？ | 原则存在、操作缺失 | 补齐迁移、导出、备份、恢复、存储和模型策略 |

五个闭环缺少任何一个，产品都会退化：

- 没有 Build：变成只会消费导入资料的阅读器；
- 没有 Understand：变成搜索框和文件堆；
- 没有 Use：变成静态百科；
- 没有 Maintain：变成不断累积冲突的摘要仓库；
- 没有 Own：变成被本地外观掩盖的封闭数据容器。

---

# 2. 本轮冻结的十一项产品修订

## 2.1 手工创作是一等路径，不是 AI 失败时的降级路径

用户可以从 Group、Topic、选中文本、全局 Capture 或快捷键直接创建 Node。创建时不要求先有 Source，也不要求先通过 AI 编译。

AI 可以补充结构、关系、来源或 Overview，但不能让用户觉得“只有被 AI 处理过的文字才算知识”。

## 2.2 空知识群是合法而完整的开始状态

新建 Group 的最低要求只有稳定名称；Boundary、类型、Topics 与来源可以稍后补充。系统可建议模板和边界，但不能强迫用户先导入资料或回答一轮设置问卷。

空 Group 必须提供三条同等真实的开始路径：

1. 直接写一个 Node；
2. 添加来源；
3. 先建立 Topic 骨架。

## 2.3 用户原创知识不因缺少外部来源而被贬低

Node 的 provenance 可以是：

- external evidence / 外部来源；
- user observation / 用户观察；
- user synthesis / 用户综合；
- user hypothesis / 用户假设；
- system inference / 系统推断。

“没有外部引用”与“AI 不确定”不是同一状态。用户原创内容可以被接受为个人知识，但必须清楚表达作者、依据类型与适用边界。

## 2.4 编辑必须明确作用域

当一个 Node 出现在多个 Group / Topic 中，编辑器必须区分：

- **Edit Node**：修改全局 canonical content，可能影响所有 Placements、Overview 与回答；
- **Edit in this context**：只修改当前 Placement 的 contextual summary、顺序或强调；
- **Fork as new Node**：当前语境已经产生独立含义，需要新身份。

默认根据用户点击位置进入最小影响范围；扩大影响范围前必须预览。

## 2.5 用户可以直接建立正式关系

关系不是 AI Suggestion 的专属产物。用户可以从正文选区、Node 菜单、Relation Inspector 或图谱拖拽进入“创建关系”，但提交前必须明确：

- 起点与终点；
- 类型与方向；
- 适用条件；
- 可选依据或说明；
- 是正式关系还是仅保存为探索线索。

自由拖线不能绕过语义确认。

## 2.6 Overview 是可编辑知识产品

用户可以直接编辑 Space / Group / Topic / Saved Path Overview。每个合法 scope 至多拥有一个 canonical Overview identity 和一棵连续 content tree；Home、View、Search Result 与 AI Answer 不创建平行 Overview。

Overview Block 分为 Editorial、Projection、Reference、Navigation 与 Status。用户直接编辑 Editorial prose；Projection 只保存规则并根据当前知识刷新；accepted AI prose 与用户文字一样只能经 Semantic Diff 修改。authorship、update policy 与 lock 是三个治理轴，alignment 是独立一致性状态；它们不能被 `User-owned / AI-assisted / Generated` 一个枚举混合表达。

Overview Anchor 可通过 Support Map 回到 Node Anchor、Relation、Structure Projection、Boundary 或历史 Overview，但 Overview 本身不是正式 Evidence endpoint。需要独立依据、Applicability、关系、引用或跨群复用的 Claim 必须提升为 Node。

## 2.7 结构操作与知识删除严格分离

产品至少区分四种动作：

| 动作 | 影响 |
|---|---|
| Remove Placement | 只从当前 Topic / Group 位置移除 |
| Archive | 从默认导航隐藏，但对象、关系与历史仍可访问 |
| Move to Trash | 对象进入可恢复区，影响范围在提交前可见 |
| Delete Permanently | 明确不可逆；需从 Trash 发起并再次确认 |

删除 Topic 不删除 Node；删除 Group 不应静默删除共享 Node；删除 Source 不自动删除由它形成的知识。

## 2.8 所有高影响编辑进入 Change Set

直接编辑、批量移动、关系改变、Overview 重写、Group 归档和永久删除都使用同一影响语言：

- Changed：直接改变什么；
- Affected：哪些 Overview、Answers、Paths、Relations 与 Search index 受影响；
- Review：哪些内容不能自动决定；
- Undo / Recovery：提交后如何恢复。

## 2.9 默认只有一个个人 Knowledge Space

产品默认呈现一个连续的个人知识世界，不在首屏制造 Workspace 管理负担，也不默认显示 Space Switcher。

只有当用户需要硬隔离的数据边界、不同存储位置或独立同步策略时，才创建额外 Vault / Space。跨 Space 不建立隐式关系；导入或复制必须明确发生。

## 2.10 本地优先必须有可操作的所有权界面

“数据在本地”不是一句品牌文案。用户必须能看见并操作：

- canonical knowledge store 与 Sources 的位置及健康状态；
- 最近备份与可恢复点；
- 索引状态与重建范围；
- 完整导出及其内容清单；
- 恢复前预览与冲突处理；
- 可选同步状态；
- 每次 Ask 是否使用云模型、外部知识或仅本地资料。

## 2.11 导入与导出必须保留知识语义

迁入不是“把每个文件变成一个 Node”，迁出也不是“把所有内容拍平成 Markdown”。完整 Knowledge Package 至少保留：

- Groups、Topics、Nodes 与稳定 ID；
- Placements 与层级顺序；
- 类型化 Relations；
- Overviews 与锁定状态；
- Sources、版本、Evidence locators 与 provenance；
- Saved Paths、Knowledge Snapshots 与 Change Sets；
- aliases、redirects、历史与删除状态；
- 一份人可读说明和一份机器可重建 manifest。

Markdown / HTML / PDF 可以作为阅读导出，但不能冒充完整备份。

---

# 3. 主要产品资源由九类扩展为十四类，但日常语言保持五个概念

现有九对象模型遗漏了系统必须长期维护、且用户在特定判断中会接触的主要产品责任。修订后的十四类 Primary Product Resources 为：

| 对象 | 用户语言 | 为什么必须显式存在 |
|---|---|---|
| Knowledge Space | 我的全部知识 | 顶层数据与存储边界 |
| Knowledge Group | 一个可独立进入的知识整体 | 宏观组织单位 |
| Topic | 群内的一条稳定理解分支 | 层级与局部 Overview |
| Knowledge Node | 一个可独立理解与复用的知识单元 | canonical identity |
| Placement | 这个 Node 在当前语境中的位置 | 解释多重归属而不复制正文 |
| Relation | 两条知识或两个知识群为什么相连 | 横向探索与推理；结构与证据连接另行表示 |
| Overview | 当前范围的地形说明 | 从整体进入细节 |
| Source | 原始材料 | Source Truth |
| Evidence Fragment | 来源中的精确依据 | 精确核验 |
| Saved Path | 一条被保存的探索路径 | 继续探索与分享思路 |
| Knowledge Snapshot / Saved Answer | 当时问题、作用域与回答 | 保留历史理解，不被静默改写 |
| Change Set | 一次变化及其影响 | 预览、传播与撤销 |
| Proposal / Review Item | 尚未进入正式知识的建议 | 让 AI 建议与事实分离 |
| View | 同一知识的一种观察方式 | 层级、图谱、时间、对照与派生体验 |

这不意味着界面同时展示十四种术语，也不意味着用户需要记住十四个概念。默认日常语言只有知识群、主题、知识、关系、来源；Overview、Evidence、Path、Version 与 Suggestion 使用普通含义按需出现；Placement、Snapshot、Change Set 等只在用户判断位置、影响、来源或历史时以人话逐步显露。

完整翻译与 P0–P3 披露合同见 `AI-native-个人知识库-产品语言与渐进披露规范-v1.0.md`。

---

# 4. 设计覆盖从 62 项扩展为 81 项

原 A–G 62 项全部保留。新增两类 19 项，解决“亲手建设”和“长期拥有”。

## 4.1 H. Author & Organize / 直接创作与组织（11）

| ID | 屏幕 / 状态 | 必须回答 |
|---|---|---|
| H01 | Create Knowledge Group | 不导入资料时如何创建并进入空 Group |
| H02 | Group Setup & Boundary | 名称、边界、primary kind、facets 与默认结构如何设置 |
| H03 | Create Knowledge Node | 如何从 Group、Topic、选区或快捷入口直接写知识 |
| H04 | Edit Scope Choice | 编辑 canonical Node 还是当前 contextual placement |
| H05 | Node Editor | 长内容、结构、属性、状态与保存冲突如何处理 |
| H06 | Topic Authoring | 创建、改名、排序、移动、缩进与提升 Topic |
| H07 | Placement Manager | 同一 Node 如何加入、移出或移动到多个位置 |
| H08 | Manual Relation Editor | 用户如何建立类型、方向、条件与依据明确的关系 |
| H09 | Overview Editor & Governance | Editorial、Projection、Reference 如何共存；authorship、update policy、lock 与 alignment 如何分开 |
| H10 | Archive / Trash / Restore | 移出位置、归档、删除和恢复如何不混淆 |
| H11 | Bulk Organize | 多选移动、建立关系、归档或改状态如何预览影响 |

## 4.2 I. Own & Configure / 迁移、所有权与配置（8）

| ID | 屏幕 / 状态 | 必须回答 |
|---|---|---|
| I01 | First-run Knowledge Space | 从空白开始、迁移旧库或添加首批来源如何选择 |
| I02 | Library Migration Mapping | 旧文件夹、链接、标签、frontmatter 与附件如何映射 |
| I03 | Full Export / Knowledge Package | 导出包含什么、能否完整重建、如何验证 |
| I04 | Backup & Restore | 备份频率、恢复点、恢复前预览与失败回滚 |
| I05 | Storage & Index Health | 本地位置、容量、索引覆盖、重建与损坏状态 |
| I06 | AI & External Knowledge Policy | 本地/云模型、外部知识、发送范围与每次 Ask 的实际策略 |
| I07 | Optional Sync & Device Conflict | 未启用同步时不受影响；启用后冲突与离线提交可解释 |
| I08 | Preferences & Accessibility | 快捷键、默认布局、字号、减少动态与图谱等价视图 |

新的完整性基线：

```text
A–G existing coverage   62
H Author & Organize     11
I Own & Configure        8
Total                   81
```

81 仍不是“要画 81 张大页面”。它是 81 个必须有可验证设计证据的用户问题，可以由 Full Frame、Overlay、Component State、Flow Annotation 或测试说明承载。

---

# 5. 两块新增流程板

## PB-09 Author & Organize

覆盖从空 Group 到可用知识结构的直接创作路径：

```text
Create Group
  → choose empty / suggested skeleton
  → create or convert a Node
  → edit canonical or contextual scope
  → place in Topic hierarchy
  → create relation
  → update Overview by Diff
  → save Change Set
```

关键恢复：编辑冲突、未完成 Working content、错误作用域、重复 Node、误删 Placement、批量操作撤销。

## PB-10 Own & Configure

覆盖知识资产从进入产品到可迁出的长期所有权路径：

```text
First run
  → create local Knowledge Space or migrate
  → verify mapping and import report
  → inspect storage / index / AI policy
  → create backup
  → export Knowledge Package
  → verify manifest or restore preview
```

关键恢复：导入部分失败、磁盘空间不足、索引损坏、备份中断、导出校验失败、同步冲突与模型不可用。

---

# 6. 视觉设计必须因此改变什么

三种已生成的视觉方向只回答了 Group Overview 与关系视图的视觉构成，尚未回答完整产品。用户选择方向后，不能直接把一张 Group Overview 扩成全部页面；必须先证明所选语言能覆盖：

1. 阅读态与编辑态不会变成两个产品；
2. 空 Group 仍然有明确但不幼稚的开始路径；
3. canonical edit 与 contextual edit 的影响范围看得懂；
4. 图谱拖线不能跳过关系语义；
5. Archive、Trash 与 Remove Placement 不被一个“删除”图标吞并；
6. 深色 Relation Night 在设置、导出、恢复等事务界面中不被滥用；
7. 高密度编辑与配置使用温暖、清晰、连续的 Knowledge Paper；
8. Change Set 成为创作、导入、维护和恢复共用的设计语法。
9. Group、Topic、Node 与 View 不被同一种容器卡片表示；Library 不出现 Subgroup。
10. Topic Gateway 与 Group Relation Inspector 能分别解释范围提升和跨群关系。

因此，视觉方向选择只是视觉语法冻结，不是产品定义完成，也不是原型开工许可。

---

# 7. 研究依据与产品推论

本轮只使用公开官方资料验证“直接创作、批量组织、导出、本地存储与恢复为什么是知识库基础能力”，不把竞品功能直接复制为需求：

- Capacities 官方文档显示，对象内直接创作、把选中文本转换为对象、批量移动/转换/删除，以及全空间和单对象导出，均属于日常对象知识库的基础闭环；推论是本产品不能只依赖 Capture → AI Proposal。[Blocks](https://docs.capacities.io/reference/blocks) · [Turn blocks into objects](https://docs.capacities.io/faq/editing/blocks-into-object) · [Bulk Actions](https://docs.capacities.io/reference/bulk-actions) · [Export](https://docs.capacities.io/reference/export)
- Anytype 官方文档明确区分本地优先存储、Local-only、导入导出、Bin 与恢复；其文档也提醒 Local-only 仍需要用户主动备份。推论是“本地”不能替代 Backup / Restore 与可迁出设计。[Storage & Deletion](https://doc.anytype.io/anytype-docs/advanced/data-and-security/data-storage-and-deletion) · [Local-only](https://doc.anytype.io/anytype-docs/advanced/data-and-security/self-hosting/local-only) · [Import & Export](https://doc.anytype.io/anytype-docs/advanced/data-and-security/import-export)
- Obsidian 官方帮助中的 URI 支持直接创建、追加、打开和搜索本地 Vault 中的 Note；推论是成熟个人知识工具必须保留无需 AI 的直接创作与可预测入口。[Obsidian URI](https://help.obsidian.md/Extending+Obsidian/Obsidian+URI)
- Heptabase 官方 Wiki 把 capture、organize、learn/research、write 与 AI 并列为完整工作流；推论是 AI 应进入知识生命周期，而不是替代写作与组织本身。[Heptabase Public Wiki](https://wiki.heptabase.com/)

这些资料只证明产品类别中的基础交互已被真实产品长期采用，不证明本方案已经通过用户验证。

---

# 8. 修订后的完成门槛

进入完整视觉设计前，产品文档必须同时满足：

- 十四类主要产品资源与五个日常用户概念保持可追踪映射，支撑身份和内部记录不额外挤入日常心智；
- 五个闭环均有主流程、失败、恢复与影响范围；
- 81 个覆盖 ID 有唯一 Primary Board；
- 手工创建和 AI 编译都能形成合法知识；
- 同一 Node 的 canonical content 与 contextual placement 编辑不会混淆；
- 所有删除与结构操作遵守对象生命周期；
- 完整 Knowledge Package 可以重建语义，而不只是阅读文本；
- 默认单一个人 Knowledge Space，不用多 Workspace 破坏知识连续性；
- 视觉方向选择后，先用 PB-00、01、02、09、10 验证视觉语法，再扩展其余 Boards。
- 同一 Group Overview 已定义 Seed、Forming、Established、Evolving、Dormant 体验；阶段不成为成熟度评分。
- Scope Level、Reading Depth、Relation Radius、五类连接与忠实 Knowledge Route 已被独立定义；检索跳转不写入长期关系。
- Source、Working Branch、Proposal 与 Accepted knowledge 具有不同落点；Placement / 未归类状态独立表达；新来源和普通 Working content 不进入 Review。
- 一份 Source 可以 zero-yield 成功；解析片段不自动成为 Node。
- Identity Resolution 支持补证、修订、新 Placement、新 Node、版本、重复与 Source-only。
- Proposal 按用户决定组织，一次默认只呈现 3–7 个高价值 Decision Bundles。
- 用户纠正和来源更新沿依赖传播，但历史 Answer Snapshot 不被静默改写。
- 产品不存在 Subgroup 对象；Group 是独立范围，Topic 是单父群内结构，View 是观察方式。
- Group membership 可以只从 active Placements 重建，Topic children 可以只从直接 parent 重建。
- Topic Promotion、Group Absorb、Split 与 Merge 保留 identity、redirect、Overview、Relations 与 Saved Paths。
- 正式 Relation endpoint 只允许 Node↔Node 或 Group↔Group；每条群关系都可展开底层解释。
- 每个合法 scope 只有一个 Overview identity 与一棵 content tree；Home、View、Answer 与阶段变化不复制 Overview。
- Projection refresh、accepted Editorial Diff、Support Map、Claim Promotion 与 alignment 分别拥有状态和验收；锁定不等于一致。

---

# 9. 知识形成完整性补充审计

81 项覆盖证明了 Capture、Compiler、Review 与 Direct Authoring 都“存在”，但存在本身仍不能保证形成机制合理。若没有进一步合同，产品仍可能退化为：AI 从每份来源拆出大量卡片，用户在 Review 中长期清理。

因此，完整性必须再满足四个非页面条件：

1. **输入忠实**：外部材料先成为 Source，用户想法先成为 Working Node，AI 回答先成为 Query Result；三者不因共用文本表现而混同；
2. **产出克制**：Source 可以零 Node 成功，Evidence Fragment、summary 和 retrieval co-use 不自动升级为正式知识；
3. **决定压缩**：内部 Candidate 先经过 identity、Applicability、knowledge difference 和 bundling，用户审的是少量决定而不是模型检测量；
4. **传播忠实**：availability、revision、epistemic impact 与 historical snapshot 分别处理，不能用一次“刷新知识”覆盖全部历史。

这四条不增加第十五个产品对象，也不增加新的一级导航；它们修正 PB-04、05、06、07、09 的状态与验收。完整定义见 `AI-native-个人知识库-知识形成与维护循环-v1.0.md`。

---

# 10. 知识群架构完整性补充审计

对象数量、流程覆盖和知识形成合同齐全后，结构仍可能因多份归属真相而失效。本轮进一步发现：`subgroup_refs` 没有对应对象；`member_node_refs` 与 Placement 重复表达成员；Topic 同时保存 parent / children 会在移动后漂移；Promotion / Merge 缺少旧路径语义。

因此完整性再增加五个非页面条件：

1. **范围唯一**：可独立进入、理解、查询和维护的是 Group；依赖父语境的是 Topic；筛选结果是 View；不设 Subgroup；
2. **归属唯一**：Placement 是唯一 canonical membership truth，成员列表只能是 derived index；
3. **层级唯一**：Topic 只保存一个直接父级，children、ancestors 与 breadcrumb 可重建；
4. **变换忠实**：Topic Promotion 保留 Gateway，Group Absorb / Split / Merge 保留 identity、redirect 与历史，并与 Node identity merge 分开；
5. **关系忠实**：正式 Semantic Relation 只连接 Node↔Node 或 Group↔Group；Atlas 群边必须能说明 statement、why it matters、supporting paths、Evidence 和 limits。

这些条件不增加对象或一级导航，而是消除结构歧义；它们修正 PB-02、03、06、08、09 的状态与验收。完整定义见 `AI-native-个人知识库-知识群边界与跨群架构合同-v1.0.md`。

---

# 11. 知识节点内容完整性补充审计

对象边界与结构真相统一后，Node 内部仍可能制造第二类“假完整”：页面能显示摘要、详情、引用和编辑器，但这些表面来自多份正文、没有稳定局部定位，或把每个 Block 都当作知识。这样的系统在一次性演示中成立，长期更新后会失去可信度。

因此完整性再增加六个非页面条件：

1. **身份完整**：Node 是可独立理解、维护和复用的 Primary Resource；Block 是 Embedded Record，Anchor 是 locator value，二者都不获得独立 Library / Atlas / Relation endpoint；
2. **内容唯一**：Orientation、Synthesis 与 Explanation 从同一 Content Revision 投影，不分别保存 definition / overview / detail / body；
3. **粒度克制**：Section 只有在拥有独立语义、Evidence、Applicability、正式关系、跨群复用或更新节奏时才建议提升；长度与 Heading 不触发自动切卡；
4. **定位忠实**：Search、Ask、Evidence 与 Reference 以 Node + Anchor + Placement 精确进入，Anchor 变化有 resolved、redirected、ambiguous 与 orphaned 修复；
5. **复用忠实**：Link、Live excerpt、Pinned excerpt 与 Explicit quote 的更新、历史和所有权语义不能合并；
6. **变换忠实**：Section Promotion、Node Split / Merge 与 AI block-level patch 必须预览 Anchors、Evidence、Placements、Relations、Overview、Answers、redirect、History 与 Undo。

这些条件不增加 Coverage ID 总数；它们加深 PB-02、04、06、07、09 中现有阅读、查询、维护、Evidence 与 Node Editor 的通过标准。完整定义见 `AI-native-个人知识库-知识节点粒度与内容组成合同-v1.0.md`。

---

# 12. Overview 完整性补充审计

Node 正文、结构归属和维护传播已经统一后，产品仍可能在 Overview 层重新制造第二套知识：把 Orientation、Structure、Synthesis 与 AI Summary 分别保存，把动态结构和人工文字混在一次重新生成中，或让 Overview 中的结论绕过 Node / Evidence 合同。

因此完整性再增加八个非页面条件：

1. **身份唯一**：Space / Group / Topic / Saved Path 各自至多一个 canonical Overview；Home、View、Search Result 与 AI Answer 只是表面或结果，不拥有 Overview；
2. **正文唯一**：Overview 只有一棵连续 content tree；Orientation、Structure、Synthesis 是阅读语义区，不是三份持久化正文；
3. **刷新分离**：Editorial 保存文字，Projection 保存规则；结构刷新不创建 prose revision，accepted AI prose 不静默更新；
4. **治理正交**：authorship、update policy、lock 与 alignment 分开记录；`locked + review_due`、`user-authored + auto projection` 等组合合法；
5. **依据可追**：Overview Anchor 用 Support Map 指向 Node Anchor、Relation、Structure Projection、Boundary 或 Historical Overview；“来自知识库”不是合格依据；
6. **没有影子知识**：Overview 不作为 Evidence endpoint；需要独立核验、关系、Applicability 或复用的 Claim 必须保存为 Node；
7. **写入显式**：Ask for Overview 仍是 Query Result，只有用户明确选择“建议更新概览”才产生 Semantic Diff；
8. **生命周期连续**：Seed、Forming、Established、Evolving、Dormant 只改变 Presentation Profile 与默认内容权重，不复制 `overview_id` 或自动产生 Editorial revision。

这些条件不新增 Primary Resource 或新导航；Overview Projection 属于 Derived Evaluation，Support Map 与 Anchor 属于其支撑记录。它们修正 PB-00、01、02、04、06、08、09 中 Overview 阅读、写作、维护与 AI 查询的通过标准。完整定义见 `AI-native-个人知识库-Overview形成编辑与更新合同-v1.0.md`。

---

# 13. AI 查询完整性补充审计

Search、Ask 与 Knowledge Route 已经存在，并不代表 AI Query 已经属于知识库。如果问题、执行、回答和历史只有一个 Query 对象，如果系统扩大范围后仍显示用户最初选择，如果引用只在回答底部成组出现，或 Saved Answer 自动回到下一轮检索，产品仍会长成一个用个人资料做 Context 的聊天系统。

因此完整性再增加十二个非页面条件：

1. **运行身份**：Query Turn 与 Query Run 分开；Retry、Follow-up、Resume 与 Re-evaluate 新建 Run，不覆盖历史；
2. **范围三分**：Requested、Effective 与 Used Context 分开；Scope Anchor、Expansion Policy 与 Current Focus 分开；
3. **条件完整**：Knowledge as-of、valid-at、状态、Applicability、Source policy、External policy 与 exclusions 可被历史重建；
4. **默认边界**：Accepted active personal knowledge 是默认；External knowledge 关闭，模型无来源记忆不能偷偷补洞；
5. **Claim grounding**：每个主要 Answer Claim 有 basis、support role、exact locator、Applicability、conflict 与 unknown；
6. **真相分层**：个人知识、Source statement、External source 与 reasoned derivation 使用不同语义，不互相冒充；
7. **Coverage 诚实**：sufficient / partial / insufficient / indeterminate 与结论确定性分开；负面回答限定 Scope、索引、排除项、时间与来源可用性；
8. **Route 忠实**：没有正式连接不造路径；retrieval jump 是 Run overlay，关闭后不进入 canonical graph；
9. **多轮安全**：Follow-up 显示 Context Delta；上一 AI Answer 默认不成为事实 support；
10. **保存隔离**：Saved Answer 是 Knowledge Snapshot subtype，不是 Node，默认不参与当前事实检索；
11. **历史重评**：Re-evaluate 产生新 Run / Answer Snapshot 与语义 Diff，Original 永不覆盖；
12. **写入与退化**：八类 Answer Transform 走不同对象流程；Streaming / Incomplete / Cancelled / Failed 分开；AI、index 或 source unavailable 时知识库仍可用。

这些条件不增加新的顶层知识对象、一级导航或 Coverage ID 总数；Query Session、Turn、Run、Answer Snapshot 与 Claim Support 是运行与历史结构。它们加深 PB-00、02、03、04、06、07、08、10 中查询、探索、维护、来源、退化和所有权的通过标准。完整定义见 `AI-native-个人知识库-AI查询与知识回答合同-v1.0.md`。

---

# 14. 搜索定位完整性补充审计

已经有 Search Overlay、对象分组和混合检索，并不代表产品已经拥有可靠的知识找回。如果一个长 Node 的每个 chunk 都成为一条结果，如果同一 Node 的两个 Placements 被当成两个对象，如果 Semantic 压过用户记得的精确标题，或 Index partial 时仍显示“没有相关知识”，Search 会在最基础的定位环节破坏知识身份与用户信任。

因此完整性再增加十二个非页面条件：

1. **结果身份**：Search 以 Group / Topic / Node / Source / Snapshot / Path / View identity 为结果单位，Block、Evidence Fragment 与 Answer Claim 只作为 locator；
2. **聚合与消歧**：同一 identity 的多 Anchors / Placements 聚合，同名不同 identity 通过 definition、Group、Applicability 与状态消歧；
3. **范围可预测**：Scope Anchor、descendants、Source / Relation expansion、revision 与状态过滤分开，Current Focus 不静默扩大范围；
4. **默认状态正确**：Search 包含 Accepted 与用户 Working content；Archived / Historical 显式开启，Trash 只在 Trash 内；Saved Answer 可找回但不成为当前事实；
5. **排序忠实**：exact title、confirmed Alias、exact phrase 与 lexical full-text 优先于 Similar Meaning；recentness 只作 tie-break，不显示裸 relevance / confidence；
6. **相似不造边**：semantic similarity、共同命中和结果共现只属于 Search Run，不生成正式 Relation 或改变 canonical Graph；
7. **定位连续**：Hit 保存 identity、revision、Anchor 与 Placement；打开直达精确位置，Back 恢复 Request、Result Set、scroll 与 Selection；
8. **覆盖诚实**：Scoped no result / Global yes、filter excluded、Index partial / stale、Source unparsed、OCR uncertain、semantic unavailable、failure 与 true empty 分开；
9. **索引可恢复**：canonical knowledge store 与 Search Index 分离；Index 可重建且不删除知识，新保存内容立即可找；
10. **本地退化**：AI、网络或 semantic index 不可用时，local exact、Alias、full-text 与 property Search 继续成立；
11. **跨模式安全**：Search → Ask 只传 identities / revisions / anchors，Search → Explore 不传 semantic edge，Picker 选择后仍需正式提交；
12. **保存语义**：Recent Search 是本地便利，Saved Search 是动态 View，冻结结果是 Knowledge Snapshot / export，三者不混合。

这些条件不新增 Primary Resource、一级导航或 81 项 Coverage ID；Search Session 与 Request 属于 Workspace State，Run 与 Result Set 属于 Supporting Identity，Hit 属于 Embedded Record，Saved Search 复用既有 View。它们加深 A04、C07、G02、G03、I05 以及 PB-00、02、04、08、10 的通过标准。完整定义见 `AI-native-个人知识库-搜索定位与知识找回合同-v1.0.md`。

---

# 15. Library 浏览完整性补充审计

已经有 Groups、Pinned Topics、Saved Paths 和旧称 `Unplaced Draft` 的列表，并不代表产品已经拥有可长期使用的知识目录。如果“全部知识”把同一 Node 的多个 Placements 显示成多个对象，如果 View 把动态结果保存成成员清单，如果最近编辑替代人工结构顺序，或删除 Topic / View 时连带删除知识，Library 会在最日常的浏览环节破坏知识身份与结构真相。

因此完整性再增加十二个非页面条件：

1. **根目录稳定**：Library 是不依赖推荐、查询和最近活动的穷尽目录；Knowledge Groups、All Knowledge、Paths / Answers、Views 与 Archived 各有稳定入口，Library Root 自身不是知识对象或 Overview；
2. **结果单位明确**：All Knowledge 与跨范围 View 按 identity 去重，Group / Topic hierarchy 按 Placement 表达结构位置；打开、选择和返回同时保留 identity 与可选 placement context；
3. **多位置与同名诚实**：同一 identity 多 Placement 不复制内容，同名不同 identity 不自动合并；定义、Group、Applicability、状态与其他位置在动作前可检查；
4. **View 三层分离**：View Definition 保存 scope、criteria、filter、sort、grouping、layout 与 property visibility；Evaluation 计算当前结果；Workspace State 保存本次滚动、展开和临时调整；View 不保存 `member_ids`；
5. **容器边界收敛**：独立边界用 Group、群内结构用 Topic + Placement、动态聚合用 View、顺序策展用 Saved Path、快捷入口用 Pin、冻结结果用 Snapshot；不新增泛化 Manual Collection；
6. **Pin 与 Recent 中性**：Pin 只改变快捷入口，Recent 明确 open / edit / update / ask / use event；二者不改变 authority、truth、Ask retrieval、Overview、Search factual rank 或 canonical Graph；
7. **结构与呈现分离**：Topic semantic order、Path step order 和 Placement structure 只有通过正式结构动作改变；temporary sort、grouping、layout 与 property visibility 只改变当前呈现；
8. **选择与返回连续**：Selection 保存 identity、placement context 与 presentation row；Back 恢复 Library scope、View revision、filters、sort、grouping、layout、expanded rows、scroll 与焦点；对象移动或归档时通过 redirect / nearest valid state 恢复；
9. **批量与拖放有作用域**：多选先声明 identities 或 placements；跨群拖放区分 add placement、move this placement 与 move all placements，并预览其他位置、Overview、Paths 与失败项；
10. **空态与部分结果诚实**：true empty、filter empty、View partial / stale、index unavailable、source unavailable 与 offline-local 分开；无 Placement Node 与未完成 Working content 分别可找回但不被写成整理债务；
11. **离线、规模与可访问性成立**：本地目录、层级、Pin、Path 与可本地评估 View 离线可用；100+ Groups / 10k Nodes 仍有虚拟化、键盘树导航、200% zoom、屏幕阅读器语义与稳定 Selection；
12. **删除、导出与恢复不混淆**：删除 View / Pin / Topic / Placement 不删除 canonical Node；导出与恢复分别保留结构、View definitions、Pins、Paths、Archive state 与必要 workspace state，不把临时排序固化为知识结构。

这些条件不新增 Primary Resource、一级导航或 81 项 Coverage ID；Library Root 与 rows 是 Surface / Embedded presentation，View Evaluation 是 Derived Evaluation，Pin / Recent event 是 Embedded Record，Workspace State 保留现场但不保存知识真相。它们加深 A02、A03、A04、B02、B07、C04、G01、G03、G07、H07、H10、H11、I05、I06 以及 PB-00、01、03、04、08、09、10 的通过标准。完整定义见 `AI-native-个人知识库-Library浏览与动态视图合同-v1.0.md`。

---

# 16. 来源、证据与可追溯性完整性补充审计

已经有 Source Registry、Source Reader、Evidence Fragment、版本 Diff 和 Evidence Role，并不代表产品已经拥有可长期核验的 provenance。如果 Source 等于文件、Citation 只指向 current URL、同一片段只能全局“支持或反驳”、OCR 被当作原文，或 Source changed 直接替换旧片段，产品仍会把“看起来有引用”误当成“知识可追溯”。

因此完整性再增加十四个非页面条件：

1. **六层分离**：Source identity、immutable Revision、Representation、Evidence Fragment、Evidence Binding 与 Knowledge Target 分开；PDF / HTML / snapshot / OCR / transcript / translation 不重复 Source，也不互相冒充；
2. **阅读标记不自动升格**：Highlight、comment、bookmark 和 question 是 Annotation；只有显式选择 Target 与作用才形成 Fragment / Binding，Knowledge Proposal 另行提交；
3. **作用属于 Binding**：Fragment 保存片段身份和 provenance，不保存全局 supports / challenges；同一 Fragment 可通过多个 Bindings 分别 supports、challenges、qualifies、defines 或 exemplifies 不同 Claims；
4. **五轴 Evidence**：Material Origin、Derivation Distance、Support Role、Extraction Fidelity 与 Verification State 正交，不用一个 Role 或 confidence 分混合来源、方法、作用和可核验性；
5. **定位可修复**：文本、PDF、网页、表格、代码、图像、音视频、对话与数据记录使用 Revision-specific Selector Bundle、content / context snapshot 与 digest；resolved、relocated、changed、ambiguous、orphaned、unavailable 分开；
6. **自动修复有门槛**：只有 digest / exact quote / context 唯一且语义未变时自动 redirect；多候选和跨 Revision 推断只形成 repair proposal，旧 Fragment 永不覆盖；
7. **来源变化不改知识**：新 Revision 产生 citation-only、support-changed、knowledge-review 与 historical-only impact；Node、Relation、Overview、Answer 和用户锁定内容只通过 Diff / Change Set 演化；
8. **派生文本不冒充原文**：native、OCR、transcript、translation、summary 与 inference 分开；修正 derived Representation 形成 successor revision / activity，并保留回到原媒体；
9. **双向语境连续**：Target Claim → Evidence Inspector → Source Reader → Back 保留 Claim、Anchor、Binding、Revision、Representation、Selector、Scope、Placement、Reading Depth 与 scroll；
10. **生命周期逐层安全**：Disconnect、Archive、Trash、Permanent Delete、delete Annotation、delete Binding 与 delete managed bytes 各有影响预览；任何动作都不静默级联删除 Knowledge Node；
11. **Source-only 长期成立**：zero-yield Source 可长期阅读、Find、标注、建立 Evidence、稍后形成知识或 Archive，不显示欠账、失败或产出评分；
12. **重建只影响派生层**：Re-parse / Re-index 不能删除 Source Revision、original bytes、Annotations、Fragments、Bindings 或 Knowledge；partial failure 保留上一份可用结果；
13. **离线、规模与可访问性成立**：managed / linked Sources、snapshots、parsed text、Annotations、Fragments 与 Bindings 离线可用；300 Sources / 100k Fragments、200% zoom、键盘、screen reader 与 reduced motion 可完成核验；
14. **导出恢复可证明**：完整包保留 Revisions、Representations、Selectors、Fragments、Bindings、Annotations、Activities、digests、redirects、tombstones 与 rights metadata；恢复验证 bytes、lineage、locator 和 Source → Target 可达性，而不是只看文件存在。

这些条件不新增 Primary Resource、一级导航或 81 项 Coverage ID；Evidence Fragment 本身仍是十四类 Primary Resources 之一，Source Revision、Representation、Selector Bundle、Evidence Binding、Source Annotation 与 Provenance Activity 都是 Supporting Identity，并分别保存 Source Truth 或 Decision History。它们加深 B06、C02、C03、C09、D02、D03、D04、D06、D08、E04、E05、E06、F01–F07、G02、G03、G05、G09、I03–I07 以及 PB-02、04、05、06、07、08、10 的通过标准。完整定义见 `AI-native-个人知识库-来源证据与可追溯性合同-v1.0.md`。

---

# 17. 直接创作、编辑与版本历史完整性补充审计

已经有 Node Editor、auto-save、Accept、Version、Undo 和 Offline，并不代表产品已经长期可写。如果 Node 整体只有 draft / accepted / superseded / archived 一个状态，如果 `Saved` 同时表示本机写入、同步和采用，如果恢复旧版会覆盖 current，或 AI / 多设备依靠 last-write-wins，知识库仍会在最基本的亲手建设过程中丢失用户意图和内容。

因此完整性再增加十四个非页面条件：

1. **七层分离**：Knowledge Identity、Accepted Revision、User Working Branch、Proposal Branch、Edit Session、Acceptance Change Set 与 Recovery / History 分开；一个 Node 可同时有 current Accepted 和未完成 Working；
2. **状态正交**：Object Lifecycle、Identity Standing、Accepted pointer、Working / Proposal state、Epistemic、Freshness 与 Availability 分开；旧 draft / accepted / superseded / archived 单轴废止；
3. **保存三分**：input received、durable local save、sync 与 accepted knowledge 分别显示；auto-save 只推进 Working Checkpoint，完成并采用才创建 immutable Accepted Revision；
4. **作用域明确**：Canonical、Contextual、Fork、Structure 与 Historical Read-only 在开始、切换和提交时说明影响；已有改动不能静默跨 scope 迁移；
5. **历史四分**：Session Undo、Accepted Version History、Recovery Checkpoints 与 Change Set History 分别承担短期撤销、正式修订、近期找回和多对象影响；Recovery 不冒充 Backup；
6. **恢复向前**：历史 Revision 只读；整体或局部 Restore 创建 Recovery Working Branch，接受后形成新 Revision，中间历史不消失；
7. **AI 不直写**：Inline candidate 接受前不持久化；Selection rewrite 与 Structured Patch 进入独立 Proposal Branch，绑定 Base Revision、支持 partial accept、stale / rebase，不能整篇覆盖；
8. **冲突不丢失**：非重叠变化才自动合并；content、structure、property、delete-vs-edit、scope 与 identity 冲突保留 common Base 和所有竞争值，不使用不可见 last-write-wins；
9. **Working 可找但不冒充真相**：Library / Search 可找回 Working，Ask、Overview Projection、Atlas 和 formal Relations 默认只使用 Accepted；显式包含 Working 时分层说明；
10. **Block / identity 忠实**：Heading 不等于 Topic，Block 不等于 Node；copy / paste、move、split、merge、promotion 与 Link / Live / Pinned / Quote 使用不同 identity / lineage 规则；
11. **结构提交分层**：明确的小型 Topic / Placement / Relation 动作可直接提交并 Undo；Section Promotion、Node Split / Merge、Topic Promotion 与 Group 变换进入 identity Impact Preview；
12. **离线完整写入**：Group、Topic、Node、Overview、Placement、Relation、Accepted commit、History 与 Recovery 离线成立；network、AI、Source / Index failure 只降级相关增强；
13. **故障可恢复**：crash、storage full、permission lost 和 write failure 不清空 editor state、不误报 Saved，并提供 copy、recovery export、retry 与 last durable checkpoint；
14. **可访问且可扩展**：连续 Knowledge Paper、按需 Block controls、keyboard、screen reader、200% zoom、IME、2k Blocks 与 large History 状态可完成创作、Diff、Conflict 和 Recovery。

这些条件不新增 Primary Resource、一级导航或 81 项 Coverage ID；Working / Proposal Branch、Content Revision 与 Recovery Checkpoint 是 Supporting Identity，Conflict Record 是 Embedded Record，Edit Session 是 Workspace State；它们共同服务 Node / Overview / Change Set，而不与其平级。它们加深 A03、A04、B04–B06、C01、C06、E03、E05、E06、G03、G04、G06、G09、H01–H11、I03–I07 以及 PB-00、02、04、06、08、09、10 的通过标准。完整定义见 `AI-native-个人知识库-直接创作编辑与版本历史合同-v1.0.md`。

---

# 18. 属性、Facet 与适用条件完整性补充审计

已经有 `primary_kind`、`facets[]`、property Search、property visibility、frontmatter mapping 和 property migration，并不代表产品拥有一致的结构化知识模型。若 Definition 与值混在一起，View 会被重命名破坏；若 Applicability 只是属性包，系统会制造伪冲突；若 Node reference 自动画边，属性会绕过 Relation 门槛；若 Schema 变化原地转换，长期知识会丢值。反过来，若所有能力都引入公式、Rollup、必填 schema 和表格主视图，产品又会偏离知识群、层级阅读与关系探索，退化成任意数据库构建器。

因此完整性再增加十六个非页面条件：

1. **Definition / Assertion 分离**：Property Definition 有 stable identity、版本、语义、目标、类型、cardinality 与治理；Property Assertion 表达某个 target 的具体值，不成为顶层知识对象；
2. **归属准确**：稳定对象特征属于 identity，随正文变化的结论属于 content revision，只在一个出现语境成立的值属于 Placement，材料元数据属于 Source，一次筛选属于 Query Context；
3. **系统字段隔离**：object ID、lifecycle、Accepted pointer、title、alias、Primary Kind 与 Facet 不被同名自定义 Property 覆盖；visibility 只改呈现；
4. **Primary Kind / Facet / Profile 克制**：一个 Primary Kind 与多个 Facets 组合建议字段、顺序和 Overview hints；不生成空 Assertions、不强迫填写、不因移除而删除值；
5. **没有万能 tag**：Source Tag、User Facet、System Marker、Alias 与正文关键词分别保存，不互相升级；
6. **五种值状态**：`unset`、`known`、`unknown`、`no_value` 与 `not_applicable` 分开；false、0 和空白都不能推断为其他状态；
7. **适用条件一等**：Applicability 只表达对谁、何地、何时、何条件成立；qualifier、Evidence、provenance、Property 与 Relation 各有唯一职责；
8. **冲突先比较范围**：target、Applicability、valid time、qualifier / basis 与 supersession 先于 true value conflict；多个可解释值可以并存；
9. **有限强类型**：Text、Number + Unit、Boolean、Enum、Date / Interval + Precision、Node Reference、External ID / URL 与 Structured Applicability 覆盖核心场景；不开放任意 nested object；
10. **Property 不造 Relation**：Node-reference Assertion 只提供原子特征、Search 与导航；用户补全类型、方向、statement、Applicability 与依据后可直接提交正式 Relation；AI 发现只形成独立 RelationCandidate；
11. **Source / Query 不静默回写**：frontmatter、source tags 与 Query bindings 只有经过 Mapping / Save 才进入 Node / Group Accepted Assertion 或 Saved View；
12. **AI 只提 Patch**：属性提取包含 target、Base、Definition、value state、origin、support、Applicability、collision 与 impact；接受前不进入 Accepted Search / View / Ask；
13. **View 按 stable ID**：criteria、option、visibility 与 Profile 引用 stable identities；rename 不破坏，type / option 变化进入 compatibility review；View 不保存成员；
14. **Schema evolution 无损**：type / cardinality / option / Definition merge / split / archive 使用 Impact Preview、clean / ambiguous / unsupported / conflict 分组、Legacy retention、partial commit、History、rollback 与 index rebuild；
15. **导出恢复保留语义**：Definitions、Assertions、value states、qualifiers、Applicability、Evidence、Profiles、Views、migrations、redirects 与 tombstones 可 round-trip；Markdown fallback 报告降级；
16. **低噪声与反指标**：属性默认退到 Context Rail，不以字段数、覆盖率、AI 填充率、模板使用率或表格密度衡量知识质量，不提供通用公式、Rollup 和业务 workflow。

这些条件不新增 Primary Resource、一级导航或新的 Coverage ID；Property Definition、Profile 与 Migration 是 Supporting Identity，Assertion 是 Embedded Record；它们为既有 Primary Resources、View 与 Change Set 提供 Definition Truth 和治理历史。它们加深 B04–B06、C01–C03、C06、C09、E03、E05、E09、G02、G03、G06、H02–H05、H08、H11、I02–I05、I07–I08 以及 PB-02、04、05、06、08、09、10 的通过标准。完整定义见 `AI-native-个人知识库-属性Facet与适用条件合同-v1.0.md`。

---

# 19. 产品对象层级与身份治理完整性补充审计

已经列出十四类主要产品资源，并零散地把 Block、Run、Definition 或 Annotation 排除在顶层资源之外，仍不等于拥有完整对象模型。系统事实上还需要 Revision、Branch、Binding、Assertion、Activity、Evaluation 和 Workspace State；如果有 stable ID 就画成卡片与页面，产品会退化成内部记录后台；如果为了简洁全部当作临时数据，又会丢掉历史、证据、迁移和恢复。

因此完整性再增加十六个非页面条件：

1. **十四类主要资源**：原“十四个正式对象”改为十四类 Primary Product Resources，表达不可替代的产品责任，不声称穷举全部持久记录；
2. **身份等级分开**：Primary Resource、Supporting Identity、Embedded Record、Derived Evaluation 与 Workspace State 各有准入、入口和 lifecycle；
3. **六平面分开**：Knowledge、Source & Provenance、Structure & Curation、Governance & History、Definition & Policy、Projection & Workspace 不互相冒充；
4. **Truth Role 明确**：knowledge truth、source truth、definition truth、decision history、derived observation 与 workspace continuity 各有权威；
5. **owner-first Search**：Block、Revision、Assertion、Fragment、Binding、Answer Claim 命中聚合到 owner identity，并保留 exact locator 与专用模式；
6. **owner-first deep link**：内部 record 首先说明“这是谁的什么记录”、current / historical / derived standing、basis 与返回现场；
7. **Library 不看全部 records**：Revisions、Runs、Bindings、Assertions、Evaluations 与 Workspace 不与 Groups / Nodes / Paths / Snapshots / Views 平级；
8. **Atlas 只看真实连接**：supporting ID、shared Source、View membership、similarity、history 与 query overlay 不进入 canonical Semantic Graph；
9. **Projection 可重建**：View Evaluation、Overview Projection、Search index、Graph cluster 与 recommendation cache 可以清除、刷新、离线缓存，但不能直接编辑；
10. **Workspace 不写知识**：Selection、Return Stack、temporary filter、graph viewport、cursor、pane 与 Edit Session reset 不产生 Knowledge Change；
11. **Definition 是稳定规则**：Property / Facet / Relation Type / AI / Import policy 可以版本化、迁移和归档，但不自动成为知识对象；
12. **跨平面不级联删除**：删除 Annotation、Binding、View、Source、Node、Definition 或 Projection 使用不同 ownership / derivability 合同；
13. **新对象有准入门槛**：Insight、Collection、Thread、Memory、Digest 等只有在独立意图、不可重建真相、lifecycle、history、delete、export 与现有模型不可替代时才可新增；
14. **AI 按层读取与写入**：Answer、Projection、Proposal、Working Patch 与 Knowledge Change 使用不同后果，旧 Answer、Working、Proposal 与 stale cache 默认不作 accepted factual basis；
15. **分层导出**：Primary resources、supporting records、Definitions、provenance、history、redirects、tombstones 与 optional projections / workspace 分区保存；
16. **无缓存恢复**：删除全部 optional derived / workspace data 后，Group → Placement → Node、Source → Revision → Fragment → Binding → Target、View definition 与 Snapshot used revisions 仍可重建。

这些条件不新增一级导航、Coverage ID 或用户心智名词；它们重写“什么算对象”的准入规则，并加深 A01–A05、B04–B06、C01–C06、E03–E06、F01–F07、G02–G09、H03–H11、I02–I08 以及 PB-00、04、06、07、08、10 的通过标准。完整定义见 `AI-native-个人知识库-产品对象层级与身份治理合同-v1.0.md`。

---

# 20. 产品表面架构完整性补充审计

已经定义 Home、Library、Atlas、Sources、Group Workspace、Ask、Search、Decision / History 与大量组件，并不等于用户拥有可预测的产品空间。若每项功能都生成一张 Screen，同一 Group 在文章页、星图、AI 回答和设置页里使用不同 Header、Selection、返回与状态语义，完整对象模型仍会被界面重新切碎；若“完整设计”只按静态正常态或 Screen 数量判断，失败、恢复、窄屏与可访问状态仍然不可验证。

因此完整性再增加十六个非页面条件：

1. **四个 Places**：Home、Library、Atlas、Sources 是长期地点；Search、Ask、Add、Command 是全局动作；Knowledge Decision 是 contextual surface；工作模式不产生第二导航；
2. **五类 Surface role**：Place、Scope Workspace、Lens / Panel、Overlay / Inspector、Decision / Recovery Surface 分工明确；表面不创造资源，对象 identity 不强迫独立页面；
3. **Group Workspace 为核心**：Overview、Contents、Relations、Sources 是四个稳定 Roots；Reading 是 Group > Topic > Node > Anchor 的上下文路径；Changes / History / Decision 按需出现；共享 Group、Ask Scope、Relation Radius 与 Return Envelope；
4. **Scope / Depth / Radius 正交**：L0–L5 是语义层，不是六个 Route；Focus、Inspect、Open、Compare 后果分开，展开关系不移动正文，进入 Evidence 不伪造层级；
5. **全局动作可返回**：Search、Quick Ask、Add、Command 从任意 Place 调用并逐层回到原现场，不强制回 Home；
6. **owner-first surface**：Supporting Record deep link 先说明属于谁、为何打开、current / historical / derived standing 与返回目标；
7. **Return Envelope 完整**：保存 Place、surface role、owner、Selection、Anchor、scroll、expanded、filter、pane、graph viewport 与必要 focus；
8. **Decision Surface 足够厚**：Change、Conflict、Migration、Restore、Identity Change 与 Permanent Delete 显示 Base、change、affected、preserved、failure isolation、undo 与 defer；
9. **History / Recovery 分面**：Accepted History、Working Recovery、Change Set History、Query History 不混成一条含混时间线；
10. **状态族完整**：First-use、Empty、Partial、Stale、Rebuilding、Offline、AI / Source / Index unavailable、write failed、Conflict、Recovery 与 large scale 分开；
11. **last good truth 保留**：派生层 partial / stale / failed 保留 canonical reading 与上一份可用观察，不显示成 zero 或删除；
12. **响应式责任不缩水**：desktop、compact / tablet、mobile 只重排 Nav、Split、Rail、Sheet 与顺序，不删除读、问、搜、写、核验与恢复；
13. **Graph 有正式 List Equivalent**：共享 Selection、filters、relation family、direction、standing、expansion budget 与 open action，不是错误降级；
14. **可访问性是表面合同**：keyboard、screen reader、200% zoom、reduced motion、focus return 与 non-color cues 在相同任务上成立；
15. **完整设计是 Evidence Bundle**：Full Frame、Overlay / Rail、Component Variant、Flow Annotation、State Matrix 共同证明 Coverage；缺少 entry、failure、recovery、return 或必要 viewport 仍为 partial；
16. **七屏归档**：当前 Ardot 七张画面只保留视觉气质和旧语义证据，不计 81 项完成度，也不授权先做原型再倒推产品。

这些条件不新增 Primary Resource 或 Coverage ID；Places、Workspaces、Lenses、Overlays 与 Inspectors 是 Product Surface，Return Envelope 是 Workspace Continuity，Coverage Evidence 是设计治理记录。它们加深 A01–A05、B01–B11、C01–C11、D01–D08、E01–E11、F01–F07、G01–G09、H01–H11、I01–I08 与 PB-00–10 的通过标准。完整定义见 `AI-native-个人知识库-产品表面架构与完整设计证明合同-v1.0.md`。

---

# 21. 地点编排与跨地点连续性完整性补充审计

定义四个 Places 仍不等于用户拥有一个连贯知识产品。如果打开 Group 后无法判断左侧应该亮 Home、Library 还是 Atlas，Home 与 Library 都展示 Recent，Sources 与 contextual Decision 又同时复制同一个来源变化，那么四个地点仍只是名称不同的功能页。完整性再增加十六个非页面条件：

1. **三层位置分开**：Active Place、Surface Owner、Entry Context 分别回答当前地点、当前 owner 与从哪里进入；Selection 不能替代任一层；
2. **owner 不按入口复制**：同一 Group、Node、Source、Answer、View 或 Change Set 无论从哪个 Place 打开都使用同一 owner identity 与 canonical truth；
3. **显式地点切换**：打开 owner、切 Lens、改变 Selection 或 keyboard focus 不改 Place；只有 PlaceNav、明确 handoff 或 Place-aware link 改变 current Place；
4. **启动优先级确定**：普通启动恢复 last-safe Workspace，first use / New Window / unsafe restore 进入 Home；Home 不是强制门厅；
5. **Library knowledge-first**：最多一条 Resume、紧凑 Pins、穷尽 All Groups、secondary browse、optional contextual notice 先于 quiet Search / Ask / Add；Recent 不成为 feed，没有 Ask hero、AI 日报、待整理数字或通知矩阵；
6. **Recent 不重叠**：Home 只负责少量重新进入，Library 保存完整 Recently Opened / Edited / Created；Pin、Recent、Resume 与 importance 不混用；
7. **唯一 Primary Destination**：每个 event 只有一个完整处理位置，其他表面只投影、解释和 handoff；处理状态共享而不复制任务；
8. **无通用 Inbox**：Unplaced / Working、source status、knowledge judgment、formal relations 与 recent activity 分别归 Library、Sources、contextual Decision、Atlas 与 Home / Library views；
9. **Attention 可路由**：impact、requires-decision、failure isolation、merge、suppress、defer 与 Home eligibility 可解释，不能靠 unread badge 代替；
10. **scoped 与 global 共用真相**：Group Contents / Map / Sources、owner History / Impact 与 Library / Atlas / Sources / contextual Decision 共享对象、状态与处理结果；
11. **handoff 可返回**：`在图谱中打开 / 在来源中打开 / 需要你判断`保存 origin Place、owner、selection、anchor、viewport 与 return target；失败留在原现场；
12. **Capture 有 Receipt**：complete、partial、queued、source-only、working-only、proposal-required 与 failed-but-retained 逐项说明保存对象、目的地、知识结果与下一步；
13. **Default Place 确定**：无显式地点的 object / supporting-record deep link 使用稳定映射；Place-aware 与 object-only 分享链接后果不同；
14. **Place State 独立**：每个 Place 保存自己的 scope、filters、selection、scroll、pane、graph viewport 与 last-safe owner，切换后不串线；
15. **窗口与 Space 隔离**：每个窗口、每个 Space 独立恢复；一个 state corruption、owner unavailable 或 partial handoff 不影响其他窗口或知识 truth；
16. **语言与响应式不泄漏**：P0 不出现内部地点编排术语；desktop、compact、mobile、keyboard、screen reader 与 reduced motion 只改变布局和提示方式，不改变归属与返回。

这些条件不新增 Coverage ID、Primary Resource、Place 或用户心智名词；它们加深 A01–A06、B01、D01–D08、E01–E11、F01–F07、G01–G09、H01–H11、I01–I08 与 PB-00、01、05、06、07、08 的通过标准。完整定义见 `AI-native-个人知识库-地点编排信息归属与跨地点连续性合同-v1.0.md`。

---

# 22. 知识群工作区与双镜连续性完整性补充审计

把 Group Workspace 写成“文章 + 图谱双镜”仍然不够。旧规格一处列出`Overview / Structure / Map / Sources / Changes`，另一处又写`Overview / Structure / Reading / Map / Sources / Changes`；单一 Selection 还会让 keyboard focus、Map click、正文打开、Rail 和 Ask Scope 同时变化。完整性再增加十六个非页面条件：

1. **四个 Group Roots**：概览、目录、关系、来源是稳定群级入口；Reading 是 Topic / Node / Anchor contextual path，不是第五 Root；Changes / History / Decision 不占 Root；
2. **Entry Intent 可预测**：ordinary open → Overview，Continue → last-safe Primary Task，deep target → exact Read / Explore / Verify / Change；
3. **一个 Primary Task**：Orient、Browse、Read、Explore、Verify、Understand Change 任一时刻只有一个主任务，并列不等于双主任务；
4. **四层 Selection**：Focus、Inspect、Open、Compare 引用同一 identity 但后果不同；focus / hover 不改变 durable Reading、Ask Scope 或 History；
5. **Overview / Contents 分工**：Overview 只做 orientation / projection / navigation，Contents 承担完整 hierarchy / Placement browse 与 authoring；
6. **Group / Local Map 分工**：Group Map 围绕 Topics / bridge / exits，Local Graph 围绕 Reading Target 的有限一跳；Relation Rail 只解释当前 target；
7. **Graph / List 等价**：五类连接、direction、standing、scope、selection 与 open action 在图和列表一致；
8. **Group Sources 三种原因**：direct attachment、used by accepted knowledge、referenced through shared knowledge 分开，同一 Source identity 不复制；
9. **Changes contextual**：只在 Notice / History / Impact 中解释高影响 knowledge changes；source repair 与 judgment 分别进入 Sources / contextual Decision，并共享 event identity；
10. **Header complexity budget**：identity、path、必要状态、一个 Primary Action 与 overflow；Ask / Add / AI suggestion 不常驻抢占；
11. **一个 Companion 上限**：desktop 默认一个 Primary + 一个 Companion + Rail；Follow / Pinned target 可知，不无限追加 panels；
12. **formation 只改权重**：Seed、Forming、Established、Evolving、Dormant 不改变 Root taxonomy、Reading Path、identity 或 accepted content；
13. **编辑跨表面保留**：Working、IME、undo、Base、save status 与 recovery 不因 Root / layout / companion change 丢失；
14. **Workspace instance 隔离**：同一 Group 多窗口 / tabs 的 selection、scroll、map、Root state 独立，canonical truth 共享，并发编辑显式解决；
15. **响应式责任等价**：mobile 用顺序、Sheet 与 Relation List 完成 Read → Relation → Evidence → Back，不依赖并排才能成立；
16. **局部失败隔离**：Root partial、Graph failure、Source unavailable、Projection stale 与 Workspace state corruption 保留 canonical reading 和 other roots。

这些条件不新增 Coverage ID、Primary Resource、Place 或第五 Group Root；它们加深 A02、B02–B11、C01–C11、D01–D08、E01–E11、F01–F07、G01–G09、H01–H11 以及 PB-01–09 的通过标准。完整定义见 `AI-native-个人知识库-知识群工作区与双镜连续性合同-v1.0.md`。

---

# 23. 核心导航与复杂度收敛完整性补充审计

前述审计一度把 Review 与 Changes 提升为稳定导航，以保证维护能力不被遗漏。再次从用户的五个原始需求——知识群、群间关系、纵向层级、AI 查询、网络探索——反向检查后，发现这种做法虽然功能完整，却让治理和变化持续与知识本身竞争产品中心。本轮以“能力不删除、常驻显著性收回”为原则，再冻结十六个条件：

1. **稳定地点只有四个**：Home、Library、Atlas、Sources；它们分别负责重新进入、稳定浏览、网络探索和原始材料；
2. **全局动作只有三项主入口**：Search、Ask、Add 随处可用但不占 Place；Command 只作为高级操作入口；
3. **Knowledge Decision 不常驻**：只有判断会改变 accepted knowledge、identity、关键 relation、group boundary、locked content 或重要 Applicability 时才出现；
4. **没有空判断页**：无事项时不显示空 Place、0 badge、清零动画或“全部处理完成”；
5. **一个事件一个 Primary Destination**：可能是 Sources、受影响 owner、Knowledge Decision 或 Recovery，而不必永远是 Place；
6. **Home 提醒有预算**：默认 0 条，最多 1 条真正影响当前理解的 contextual notice；不使用 unread matrix 或活动流；
7. **群级 Roots 只有四个**：Overview、Contents、Relations、Sources；它们分别回答整体、层级、连接和材料；
8. **Reading 是对象路径**：Group > Topic > Node > Anchor；不与四个 Roots 竞争，也不复制正文；
9. **Changes 属于 History / Impact**：变化事件由 owner 保留，在影响当前理解时投影到 Overview Notice 或 Decision，不形成第五 Root；
10. **History 与 Decision 分工**：History 回答发生过什么，Decision 回答现在需要选择什么；历史记录不自动制造任务；
11. **维护能力完整保留**：Conflict、Merge / Split、Overview Diff、Source impact、Change Set、Undo、Recovery 与 deep link 均保留 normal / failure / return 合同；
12. **目录词优于模型词**：中文界面使用`概览 / 目录 / 关系 / 来源`，不要求用户理解 Structure、Root、Lens、Primary Place；
13. **显著性服从频率与价值**：长期高频的知识浏览常驻；低频高风险判断按需加深；低频低价值状态不主动出现；
14. **响应式不扩张导航**：desktop、compact、mobile 都保持四 Places / 四 Roots；Decision 使用 Full Surface / Sheet 的布局变化不改变其 contextual 性质；
15. **旧合同明确失效**：任何“五 Places”“五 Roots”“Review Place”“Group Changes Root”“Primary Place”作为当前规范的表述均被本节与核心导航合同取代；
16. **没有原型授权**：这次收敛只冻结产品架构、进入与返回责任；在用户确认产品本身前，不把新结构直接画成高保真或可点击原型。

完整定义、五需求证据矩阵、复杂度漂移清单、十八个场景与十八条验收合同见 `AI-native-个人知识库-核心导航与复杂度收敛合同-v1.0.md`。

---

# 24. 关系陈述生命周期与网络可信性补充审计

把 Relation 定义成带类型的一条边，仍不足以让知识网络长期可信。此前模型把 Candidate、用户是否采用、证据多少、反例、时间有效性、维护需求、语义替代和 Archive 混在少数状态中；Group Split / Merge 之后又缺少逐边转移合同。短期图可以看起来完整，长期却会出现被拒建议仍像知识、正确历史被标成过时、证据更新制造无意义版本、旧边静默挂到新端点和历史路径无法解释等问题。

因此完整性再增加十六个非页面条件：

1. **Candidate 与 Relation 分开**：AI、来源抽取、相似度与路径聚合只创建 RelationCandidate；用户补全并提交或采用 Candidate 后才物化 Relation；
2. **正式关系是一条陈述**：Relation 拥有稳定 identity，RelationRevision 保存 endpoints、type、direction、statement、Applicability、qualifiers 与时间边界；
3. **语义变化才创建 Revision**：端点角色、关系类型、方向、陈述或限定变化创建新 Revision；新增、移除或替换 Evidence 不制造语义版本；
4. **证据与反例可解释**：EvidenceBinding 与 RelationChallenge 分开保存具体支撑、限制、反例和适用范围，不用 supported / contested 一枚标签代替；
5. **四种陈述处置分开**：maintained、ended、superseded、retracted 分别表达仍在采用、正确历史已结束、被 successor 替代和不再采纳；
6. **Superseded 必有 successor**：没有 successor 时只能 End、Retract、Archive 或先创建新 Relation，不能留下悬空替代状态；
7. **Archive 不表达真伪**：current / archived / trash 只回答怎样保留对象，与陈述处置正交；
8. **Review 不表达失效**：changes_available、review_due 与 transition_in_progress 只表达需要处理的变化；未决状态不让当前边静默消失；
9. **时间结束不等于错误**：显式 valid_to 到达后进入 ended history；as-of Ask 仍可使用，不写成 stale 或 retracted；
10. **Network 三层分开**：Current 只含 maintained + current lifecycle + 可解析端点；Suggested 只含 RelationCandidate；History 承载 ended / superseded / retracted / archived 与旧 Revision；
11. **Group Relation 有独立 Support Set**：底层路径只是支撑，不是群级关系本身；Support Set 变化触发 review，但不静默改 statement 或 standing；
12. **Split 不复制边**：每条受影响 Relation 建立 RelationTransitionCase；successor 只得到独立 Candidate，无法判断时不在 Current Network 画边；
13. **Merge 不偷换端点**：唯一 identity 连续时才可解析 redirect；scope 扩大、近似重复和 self-edge 分别进入 Candidate、独立审查与历史；
14. **下游引用具体 Revision**：Overview、Saved Path、Ask、Decision 与 Export 保存 relation_revision_id 和当时 statement，不只引用可变 current pointer；
15. **图与列表同义**：standing、Challenge、Review、Current / Suggested / History、successor 与动作不能只靠颜色、线型或动画表达；
16. **可从本地包重建**：删除 graph cache 后，Relation revisions、dispositions、Bindings、Challenges、Support Sets、Transition Cases、successors 与默认 Current edge set 可重建。

这些条件不新增一级导航或新的用户产品中心；它们让方向 2 的关系空间成为方向 3 层级阅读的一条可信横轴，而不是装饰图。完整对象、场景、语言、二十五条验收合同、官方研究事实与产品推论见 `AI-native-个人知识库-关系陈述生命周期与网络可信性合同-v1.0.md`。

---

# 25. 群级关系聚合门槛与支撑充分性补充审计

“Group Relation 与底层 paths 分开”仍不足以阻止网络被自动连接污染。如果系统只要求多条 paths、多个 core / bridge Nodes 或一个高 confidence，就会把同一事实的镜像、同一 Knowledge 的多 Placements、同一来源的多次转述与同一次查询经过重复计数；也会把 fringe Knowledge 的局部联系外推成两个知识范围整体的关系。

因此完整性再增加十四个非页面条件：

1. **四级 standing 分开**：cross-group exit、Aggregation Signal、Group RelationCandidate 与 maintained Group Relation 不能共用一条 edge state；
2. **Signal 不污染 Suggested**：观察到 paths 不等于 Candidate eligible，失败结果仍保留具体 exits；
3. **Raw path count 无资格意义**：系统先折叠 assertion、content、provenance 与 traversal 重复；
4. **同一身份不重复计数**：inverse / symmetric mirror、同一 canonical Knowledge 的多 Placements、同一 Source / study lineage 的多 reports 与同一 Query route 只算相应 lineage；
5. **两个 Effective Support Units 只是下限**：数量不能替代 Boundary、type、direction、Applicability、counter 与 removal 检查；
6. **跨层陈述必须明确**：Candidate 必须能写成“Group A 在什么范围内，以什么方式影响 Group B”，不能使用`有关`或`related_to`占位；
7. **Boundary coverage 可解释**：bilateral-core、anchor-and-spread 与 named-subscope 合法；fringe-only 不提升；
8. **Type-specific policy**：`scope_within` 不可聚合，`evolved_from` 需要 lineage，方法、对照、重叠、因果与约束各有不同支撑形状；
9. **方向不能多数表决**：A→B 与 B→A 分裂时收窄、拆分或进入 ambiguous，不选择数量更多一侧；
10. **反例先于建议**：同 Applicability 的 CounterSignals、Boundary exclusions、open Challenges 与 exceptions 必须进入 Assessment；
11. **Strongest-unit removal**：移除最强 unit 后决定 ambient、on-demand、needs-more-support 或 exit-only，而不是生成强度分；
12. **Eligibility 与 prominence 分开**：通过语义资格不等于必须常驻；attention / suppression budget 防止 Candidate 卡墙与重复建议；
13. **采用后是独立知识**：正式 Relation 后来低于系统建议门槛，只创建 Support Set Revision 与 Review Case，不自动删除、改型或退回 Candidate；
14. **Graph / List / Ask / Overview 同义**：Current、Suggested、History 和 exit-only 在所有表面使用同一 standing；AI 查询不因描述可能关系而写入对象。

这些条件不要求用户学习 unit、gate 或 origin cluster。P0 只解释“可以沿这里继续”“可能值得建立的关系”“当前采用的群关系”；深层审查再展示 coverage、collapse、counter 与 removal。完整定义、二十八条验收合同、官方研究边界与 Ardot 当前视觉缺口见 `AI-native-个人知识库-群级关系聚合门槛与支撑充分性合同-v1.0.md` 与 `design-audit-ardot/群级关系升级门槛与视觉证明缺口审计-v1.0.md`。

---

# 26. 群级关系类型注册表与语义互斥补充审计

聚合门槛回答“有没有资格形成群级陈述”，仍没有回答“它究竟是哪一种陈述”。旧列表同时缺少`complements`与`challenges`，把`shares_core_knowledge_with`误当成需要生命周期的正式边，又让`overlaps_with`混合部分交叉与包含、让`influences`承担过宽兜底。若不修正，两个产品表面会对同一 Group pair 产生不同类型，Registry 更新还可能静默改写历史关系。

因此完整性再增加十六个非页面条件：

1. **正式 Registry 固定十一种**：`scope_within`、`partially_overlaps_with`、`provides_foundation_for`、`provides_method_for`、`applies_to`、`complements`、`contrasts_with`、`challenges`、`constrains`、`influences`、`evolved_from`；
2. **部分交叉与包含互斥优先**：`partially_overlaps_with`要求交集非空且双方各有不属于对方的范围；一方完全被另一方包含时使用`scope_within`；
3. **Knowledge overlap 由独立 Registry 处理**：本节只废弃旧 Group-level `overlaps_with`别名；Knowledge-level 旧 overlap 后续已由独立合同收紧为 `knowledge.partially_overlaps_with`，并要求逐条检查 identity、taxonomy 与 composition，不因跨层同名而共用定义；
4. **共享核心不是正式关系**：`shares_core_knowledge_with`从 Registry 移除；同一 canonical Knowledge 出现在两群时生成可重建`shared_core_knowledge` observation；
5. **Observation 没有 Relation lifecycle**：它不采用、不撤回、不结束、不计 Relation 数、不进入 Current / Suggested / History，也不改变 resting layout；
6. **互补进入正式类型**：`complements`要求面向同一目标或问题，并分别提供不可替代、非冗余的贡献；
7. **挑战与对照分开**：`contrasts_with`只表达同维度差异；`challenges`要求方向、重叠适用范围、被挑战对象及削弱机制 / 效果；
8. **挑战不自动撤回对象**：Group、Relation 或 Knowledge 是否继续采用由各自 lifecycle / review 决定；挑战本身只是正式陈述；
9. **影响只能高级兜底**：`influences`必须说明机制、受影响维度与为何没有更窄类型；系统不在 resting Network ambient 建议；
10. **沿革区分直接与间接**：`evolved_from`必须有 lineage；direct 可作当前邻接，indirect 默认作 path / history；
11. **方向、对称与反向读法显式**：每个类型定义固定 canonical direction、inverse label 与 symmetric / asymmetric 特征，不靠界面猜测；
12. **意图先于 enum**：用户先选择范围、作用、协同、比较、限制或演化，再回答相邻类型问题；英文编码不进入 P0；
13. **类型验证不修改数据**：`TypeValidationReport`只报告不一致、缺失条件、相邻类型与可选修正；用户提交前不改变 Candidate / Relation；
14. **定义本身版本化**：RelationRevision固定`type_definition_revision_id`，新定义不反向改变旧陈述当时的意义；
15. **迁移必须逐项审查**：别名废弃、语义收窄、direction 变化与新 required fields 生成`GroupRelationTypeMigrationReview`，不得批量静默改型；
16. **视觉按家族收敛**：Graph 使用有限家族语法 + 完整标签 + List Equivalent，不为十一种类型各造一种颜色；Shared Knowledge Lens 不伪装成正式 edge layer。

这些条件让关系类型成为可维护的知识定义，而不是一组随模型输出漂移的标签。完整 Registry、选择树、四十八项决定、十八个场景、三十二条验收合同与研究边界见 `AI-native-个人知识库-群级关系类型注册表与语义互斥合同-v1.0.md`。

---

# 27. 知识群对照与关系检查器完整性补充审计

关系类型与聚合资格已经严格，却仍可能因为没有一个可信的 Group pair 阅读行为而在界面中重新混合：正式关系、共同知识、具体路径、候选与历史若都被画成“连接”，用户无法判断知识库当前到底承认什么；左右并排还可能把 directed relation 错读成视觉对称。

因此完整性再增加十六个非页面条件：

1. **Compare 是显式 Workspace State**：普通 Group open、hover、Focus 与 Query 共现不进入 Pair；比较不创建 Primary Resource；
2. **Pair identity 与 direction 分开**：unordered pair key 去重 inventory，左右显示顺序不改变 directed Relation；
3. **同一 snapshot**：两侧 Boundary / Overview、Relation revisions、Registry、Placements、observations、Candidates 与 coverage 属于同一 evaluation boundary；
4. **五层 standing 分开**：Current / Shared / Paths / Suggested / History 不按连接数量混排；
5. **Pair Orientation 先于图**：先解释两个 Groups 各自想理解什么，再解释连接；
6. **Relation Bundle 不合并语义**：同 pair 多条 Relations 保留 identity、type、direction、support、Revision 与 lifecycle；
7. **Observation 只按需出现**：Shared Lens 不改变 layout，不拥有 relation actions；
8. **Exit 仍是路径**：用户可以沿真实 Knowledge connector 探索，但不足时不生成 Candidate；
9. **类型编辑意图优先**：相邻类型问题与 TypeValidationReport 不自动写入；
10. **Pair Ask 不写入**：两个 Groups 作为 Requested Scope，回答与建立 Candidate / Relation 是独立动作；
11. **语义与支撑修改分权**：statement / type / direction / Applicability 变化走 RelationRevision / successor，support-only 变化走 Support Set Revision；
12. **刷新不制造时间撕裂**：变化先提示，显式 refresh 创建新 snapshot，并处理 stale Draft；
13. **exact return**：从 Graph edge、Ask Claim、Knowledge Anchor 或 Overview row 进入后分别恢复原 viewport、scroll、selection 与 focus；
14. **Graph / List 同义**：图不可用时仍可完成全部核验、编辑与导航任务；
15. **responsive responsibility 等价**：200% zoom 与 mobile 使用单栏顺序，不删除两侧范围、五层 standing、Evidence 与 Back；
16. **0 Relation 合法**：双方 Boundary 仍可读，可 Ask / Open Group，不生成连接债务、完成度或装饰边。

完整对象模型、四十六项决定、十八个场景、三十二条验收合同与 Screen 2 / 3 证明要求见 `AI-native-个人知识库-知识群对照与关系检查器合同-v1.0.md`。

---

# 28. Knowledge Relation 类型注册表与跨层语义完整性补充审计

群级 Registry 已经解决“两个知识范围怎样相连”，但 Knowledge-level 仍混合了正式语义、证据作用、回答依据、身份取代、撤回动作与 Question 状态。旧词表中的 `supports` 在三种对象上同名，`blocks / overlaps_with`含义过宽，`applies_to`同时承担潜在适用与真实采用，`supersedes / retracts / reopens / uncertain_about`又让生命周期变化伪装成普通知识边。若不修正，Screen 2 的深层阅读与 Screen 3 的关系空间会在同一条线上承诺不同事实。

因此完整性再增加十八个非页面条件：

1. **Knowledge Registry 独立版本化**：使用 `knowledge.*` namespace；Group 同名谓词不共享 endpoint、充分性、TypeDefinitionRevision 或迁移；
2. **正式类型固定为二十五种**：分类与组成 5 种、解释与因果结构 7 种、论证与推导 5 种、比较与应用 5 种、时间与演化 3 种；
3. **Family 不是可保存类型**：五个 family 只服务意图选择、过滤与视觉语法，不能生成“解释类关系”模糊边；
4. **三种 support 分权**：Knowledge semantic support、EvidenceBinding role 与 Answer ClaimSupport 使用不同对象、端点、Revision、语言和 connector；
5. **分类不复制结构**：`subtype_of / instance_of / exemplifies / defines / component_of`与 Topic、Block、Placement、Reference 分开；
6. **因果强度不能偷换**：`causes / contributes_to / enables / prevents / depends_on`分别承诺充分因果、促成、使能、阻止与先决依赖；confidence 与共现不能升级强度；
7. **`blocks` 被废弃**：旧边逐条迁移为 `prevents`、反向 `depends_on`、UI state、argument conflict 或无 Relation；
8. **argument 与 foundation 分开**：`supports`要求具体 argument bridge；`provides_foundation_for`表达概念、理论、原则或证据框架的基础作用；
9. **冲突先核对 Applicability**：`contradicts`只在同一问题与重叠条件下成立；局部限制使用`qualifies`，比较差异使用`contrasts_with`；
10. **推导与来源分开**：`derived_from`要求 inference / transformation trace；Source provenance、quotation、revision 与 identity transition 各走专属对象；
11. **Knowledge overlap 收紧**：旧 `overlaps_with`逐条迁移为 `partially_overlaps_with`、identity resolution、taxonomy、composition 或结束；embedding 只能提出 Candidate；
12. **适用与采用分开**：`applies_to`只表达 potential applicability；新增`implements`表达已有 implementation trace 的真实落实；
13. **时间、精化与演化分开**：`precedes`不推出 cause；`refines`不替代同一 identity Revision；`evolved_from`不替代 successor standing 或 derivation；
14. **四个旧词移出 ordinary Relation**：`supersedes`进入 KnowledgeIdentityTransition，`retracts`进入 disposition event，`reopens`进入 QuestionLifecycleEvent，`uncertain_about`进入 QuestionTargetReference；
15. **意图先于类型表**：默认只问五类自然问题，第二步显示 3–5 个完整候选句与“为什么不是相邻类型”；二十五项英文编码不成为菜单；
16. **验证与迁移只生成报告**：TypeValidationReport 与 MigrationReview 不直接改 Candidate、Relation、Question、Identity standing 或 History；
17. **Network 按五个家族收敛**：完整 label 与 List Equivalent 承担意义；二十五种类型不拥有二十五种颜色 / 线型；direct edge 与 derived path 分开；
18. **Ask 与探索不造边**：共同支撑一次 Answer、共同 Source、向量相似、检索跳转与 manual Path step 不自动形成 formal Relation。

这些条件不把用户变成本体工程师。P0 只让用户说清“它是什么”“为什么发生”“怎样支持另一条理解”“哪里相似或被使用”“怎样发展”，并用完整句子确认。深层 Inspector 才展开 endpoint kind、required qualifiers、definition revision、相邻类型排除与迁移历史。

完整 25-type Registry、五十二项决定、十八个场景、三十二条 Given / When / Then、官方研究边界与 Screen 2 / 3 证明要求见 `AI-native-个人知识库-知识关系类型注册表与跨层语义合同-v1.0.md`。

---

# 29. Question Knowledge、未知与求解生命周期完整性补充审计

上一轮已经把 `uncertain_about` 与 `reopens`移出 ordinary Relation，却仍没有定义 Question 本身怎样从未知走向部分回答、暂时采用、充分回答、停止追问、复核和重新打开。若只保留一个 `open / closed`，产品会把“没有答案但放弃”伪装成已解决，也会把“一段 AI Answer”误当成已采纳知识。

因此完整性再增加二十个非页面条件：

1. **Question 是 Knowledge**：拥有 stable identity、Current Revision、Placements、Sources、History 与导出恢复；
2. **六类问题相邻对象分权**：Query Turn、Runtime Unknown、questioning Annotation、Persistent Gap Marker、Conflict 与 Question Knowledge 不共用 identity；
3. **Unknown 不制造 Inbox**：Run 产生的缺口默认只属于 Run，用户显式提升后才进入 Library；
4. **Unknown value / no value / not applicable / not searched 分开**：空字段不承担多种认识语义；
5. **Question frame 有版本**：问题、Context、Applicability、why it matters 与 excluded interpretations 随 revision 保存；
6. **实质改题建立 successor**：改变答案类别、criteria 或决策后果时不覆盖旧 Question；
7. **Subquestion 是 supporting reference**：required / optional / diagnostic 与 criterion rollup 可解释，不冒充目录或 formal Relation；
8. **Targets 多类型、多角色、可版本化**：Group、Topic、Knowledge / Anchor、Relation Revision、Property Assertion、Source / Fragment、Conflict 与 Decision 都可指向；
9. **Target 不是 Relation**：about / challenge / seeks evidence 不进入 ordinary filters、Relation counts 或 Group aggregation；
10. **Resolution Criteria 定义充分性**：partial / provisional / resolved 由 required criteria、Applicability 与用户采用决定，不由长度、引用数或 confidence 决定；
11. **求解程度独立**：unresolved / partially_resolved / provisionally_resolved / resolved；
12. **继续意愿独立**：active / paused / concluded；停止追问必须有 reason；
13. **变化提醒独立**：no_material_change / changes_available / review_due；依据变化不静默覆盖 Resolution；
14. **Library state 独立**：current / archived / trash 不判断是否回答；
15. **合法组合可读**：resolved + active 与 unresolved + concluded 都能用人话表达；
16. **候选与采用分开**：Answer candidate、answer basis、Resolution Proposal、adopted Resolution 与 historical Resolution 保持 standing；
17. **原子动作分开**：保存 Answer、形成 Knowledge、链接 basis、采纳当前回答、标记充分回答、暂停 / 停止追问分别提交；
18. **AI 不自动解决**：模型只能提议 criterion coverage、Resolution 或 impact，不自动 resolved、concluded、reopen 或 successor；
19. **Reopen 保留历史**：旧 closure、旧 Resolution、旧依据与本次 reason 全部可读；重开不必自动降级 resolution；
20. **Screen 2 / 3 同义**：Question Paper 纵向阅读，Target / Basis / Subquestion / ordinary Relation 横向分层，Graph / List / mobile 与 exact return 完整。

这些条件使知识库既能保存“当前知道什么”，也能保存“还不知道什么、怎样才算知道、为什么暂时采用、何时需要再检查”。完整五十项决定、十八个场景、三十二条验收合同与研究边界见 `AI-native-个人知识库-问题知识、未知与求解生命周期合同-v1.0.md`。

---

# 30. 真实端到端内容夹具完整性补充审计

抽象对象和状态合同已经能够自洽，但只有真实内容才能揭示“语义上成立、使用时仍会误导”的问题。本轮以 2026 法国私人租房、Visale 与个人住房补助为合成夹具，使用官方 Source 快照，跑通两个 Groups、递归 Topics、十条 Knowledge、七条正式 Relation 判断、两条 cross-group exits、两条 Question 与一条个人条件变化。

夹具新增十二项非页面检查：

1. **Applicability Snapshot 结构化**：高后果 Resolution 固定 `as_of`、jurisdiction、decision period、subject context、governing rules、assumptions、exclusions 与 operational decision standing；
2. **个人条件不自动知识化**：本次身份、职业、奖学金、住房与日期默认只属于 Run / Question；跨问题复用需要显式 Profile / Property Assertion；
3. **三层 Answer standing**：官方来源陈述、结合当前条件的推断与机构实际结果不得使用一个完成态句子混写；
4. **ReviewTrigger 可解释**：time、source material change、target / basis、subject context、Applicability、basis unavailable 与 manual reason 分开；
5. **变化只影响相关 criterion**：一个职业条件改变不让整条 Question 自动降级或变红；
6. **旧回答按旧快照继续可读**：新的例外路径不把过去适用于“无职业活动”的 Resolution 改成错误；
7. **Reopen 不自动降 resolution**：先恢复 pursuit，再由用户采用新 Resolution；
8. **规则限定优先于 Conflict**：不同时间 / 人群可同时成立时使用 `qualifies`、validity 与 Applicability；
9. **服务流程不互相替代**：DossierFacile dossier 验证、Visale 担保与 CAF 补助分别保存对象、来源与阶段；
10. **cross-group exit 不升级**：从签约进入补助申请的具体路径不自动创建 Group Relation；
11. **真实长内容是设计输入**：Screen 2 / 3 必须承载长标题、条件、来源、changed criterion、provisional Resolution 与历史，而不是短占位符；
12. **终点是可继续的知识库**：Ask Answer 之后必须留下可读 Overview、Knowledge、Relation、Question、Resolution、Evidence 与 exact return，而不是只留下聊天历史。

完整内容、二十二步旅程、失败状态与二十四条验收见 `AI-native-个人知识库-真实端到端使用样例与设计数据夹具-v1.0.md`。它是产品真实性证明，不是对真实用户资格的判断，也不授权开始原型。

---

## 结论

这轮修订不把产品变成更大的“认知操作系统”，反而让它更坚定地成为知识库：

> **用户既可以让 AI 从资料中形成知识，也可以亲手写下、组织、连接、修改和带走知识；系统还知道何时只应保存来源、何时提出少量建议、何时必须让用户判断。AI 查询与网络探索建立在这套用户真正拥有的知识之上。**

产品的完整性基线由此从“九块流程板、62 项阅读与推理覆盖”升级为“十一块流程板、81 项建设—理解—使用—维护—所有权覆盖”，并进一步要求每条 Node 只拥有一份内容真相、稳定局部定位和可解释的复用与身份变换；每个 Overview 也只拥有一个身份和一棵正文树，动态投影、人工文字、AI 建议与独立 Claim 各走自己的更新路径；每次 Ask 还必须保留可重建的范围、执行、Claim 依据、Coverage 与历史重评；每次 Search 则必须围绕稳定 owner identity、精确 Anchor、可见 Scope 和诚实 Coverage 找回知识；Library 还必须以 identity / placement 双结果单位、规则化 View 和可恢复浏览语境承载长期目录；Source / Revision / Representation 与 Fragment / Binding 必须形成可修复、可导出、可恢复的核验链；直接创作还必须把 Working / Proposal Branch、Accepted Revision、Edit Scope、Conflict、History 与 Recovery 分开；结构化事实则必须把 Property Definition / Assertion、Facet / Profile、Applicability、Relation 与 Schema History 分开；最后，所有这些深模型都必须服从 Primary / Supporting / Embedded / Derived / Workspace 身份层级，确保稳定 ID、动态结果、工作现场、AI 提取、来源映射、自动保存、历史恢复和删除动作都不会制造第二知识对象系统或绕过知识身份、结构、版本与 provenance 合同。
