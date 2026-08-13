# AI-native 个人知识库

## 知识群层级、目录规模与结构演化合同 v1.0

> 日期：2026-08-10  
> Canonical 指针：`AI-native-个人知识库-终局产品设计文档-v6.0.md`  
> 文档身份：**ACTIVE_APPENDIX**；只深化 Group、Topic、Catalog、Placement、规模、结构演化及其对 Overview 的结构输入，不新增产品中心或 canonical truth family  
> 相邻现行合同：`AI-native-个人知识库-关系、群级网络与探索连续性合同-v1.0.md`拥有 Group Relation、Library Network、Pair 与 relation return；`AI-native-个人知识库-Overview、连续阅读与知识正文合同-v1.0.md`拥有 Overview / Topic Opening / Knowledge Paper 的阅读、编辑、Anchor 与 History；`AI-native-个人知识库-Library入口、目录浏览与继续阅读合同-v1.0.md`拥有 cold start、All Knowledge、Resume / Pin / Recent / Saved Path / Recovery 分权及普通 Open / Continue；本文拥有 Group / Topic / Placement、All Groups membership 与 Saved View 的结构真相  
> 表面责任边界：`AI-native-个人知识库-表面架构、场景家族与完整设计证明合同-v1.0.md`拥有统一 Shell、Scene / Surface role、transition / return 与设计证明；本文只提供其 Catalog / hierarchy / placement truth  
> 用户语言边界：`AI-native-个人知识库-用户可见信息架构、产品语言与复杂度披露合同-v1.0.md`拥有用户可见术语、动作、状态句与披露；本文只拥有 Group / Topic / Placement / Catalog 的结构真相  
> 冲突规则：用户最新明确意图 > v6 Canonical > 本合同；本合同不得反向扩大日常概念  
> 当前阶段：产品定义；不是视觉稿、原型、工程 schema 或实现排期  
> 证据边界：官方资料说明外部产品当前模式；三份 fixtures 证明语义可承载；真实可用性与长期规模仍待验证  

---

# 0. 产品答案

## 0.1 一句话

Knowledge Group 是一个值得整体反复进入、拥有独立 Boundary 与 Overview 的知识范围；Topic 是 Group 内可递归、可直达、但不拥有独立群边界的阅读分支；Library View 只帮助大量 Groups 被看见，不拥有或嵌套 Groups。

## 0.2 冻结的结构

```text
Library
  ├─ All Groups Catalog                    exhaustive projection
  ├─ Saved Views / Pins / Resume           optional projections
  ├─ Independent Knowledge                 zero active Placements projection
  └─ Group                                 canonical boundary
       ├─ Group Overview                   scope-owned orientation
       ├─ Root Knowledge                   legal without Topic
       └─ Topic                            stable recursive structure identity
            ├─ Topic Opening               thin or authored
            ├─ Knowledge Placement         contextual entry, not copy
            └─ Subtopic                    same Topic identity family
                 └─ Knowledge Paper
                      └─ Anchor / Claim
                           └─ Evidence Fragment in Source context
```

Group 与 Group 不做结构性嵌套。若两个 Groups 存在“子领域、组成、基础、应用或延伸”关系，使用完整 Group Relation statement；若只是为了 Catalog 中一起浏览，使用 Saved View。

## 0.3 为什么不允许嵌套 Group

`A contains B`可能同时意味着：

- B 是 A 的 Topic；
- B 是有独立边界的子领域；
- 用户只是想在目录中把 A、B 放在一起；
- A 与 B 有语义上的 component / foundation relation；
- B 的 Knowledge 在 A 中有 Placements。

若都用 parent / child Group 表达，结构、语义、组织视图和权限后果会被同一条边承担。产品因此坚持分权：

| 用户意图 | 正确表达 |
|---|---|
| 在一个范围内继续深入 | Topic hierarchy |
| 一个范围整体上是另一范围的子领域 / 基础 / 应用 | Group Relation statement |
| 同一 Knowledge 在两个范围承担作用 | Multiple Placements |
| 只想把若干 Groups 一起浏览 | Saved View |
| 暂时比较两个 Groups | Pair workspace |

---

# 1. 外部模式研究与产品推论

## 1.1 无限页面嵌套解决路径，却混合容器与内容

**观察事实：**Notion 允许任意数量 subpages，并用 breadcrumb 表示当前位置；其文档明确说明没有 folders，page 同时承担内容与容器。  
[Notion — Create a subpage](https://www.notion.com/help/create-a-subpage)

**产品推论：**递归层级和 breadcrumb 是必要能力，但本产品不让每个结构节点都成为一篇必须维护的 Knowledge Paper。Topic 必须拥有稳定地址，却可以只有 thin opening。

## 1.2 文件夹层级清楚，但把位置绑定到存储结构

**观察事实：**Obsidian File Explorer 支持 folders / subfolders、移动、排序、展开和 active file auto-reveal；文件路径是实际存储位置。  
[Obsidian — File explorer](https://obsidian.md/help/plugins/file-explorer)

**产品推论：**结构树需要 expand / collapse、active reveal 和 move 等成熟行为，但 Knowledge identity、Relations 与 Sources 不应由唯一文件路径决定。

## 1.3 子集合支持多归属，但父级聚合语义可能独立变化

**观察事实：**Zotero Collections 可以递归，同一 item 可属于多个 collections；父 collection 是否显示 subcollection items 由单独选项控制。  
[Zotero — Collections and Tags](https://www.zotero.org/support/collections_and_tags)

**产品推论：**同一 Knowledge 多 Placement 是正确方向；但“祖先 Topic 显示后代内容”必须是明确 Projection，不能偷偷创建多重 Placements 或改变数量语义。

## 1.4 多空间提供聚焦，也会切断搜索和连接

**观察事实：**Capacities Spaces 彼此分离，对象不能跨 Space reference，Search 默认也只在当前 Space；官方建议通常从一个 Space 开始。  
[Capacities — Spaces](https://docs.capacities.io/reference/spaces)

**产品推论：**本产品默认坚持一个 Library。Group 是 Scope，不是隔离数据库；只有未来出现真实权限或所有权边界时，才考虑多个 Libraries。

## 1.5 子白板有空间价值，但空间不是完整目录

**观察事实：**Heptabase 支持 sub-whiteboards，同时保留独立 Card Library；官方帮助也提供 whiteboard 内容在空间中难以找回时的重新居中方法。  
[Heptabase — Collaboration and sub-whiteboards](https://support.heptabase.com/en/articles/10510497-collaboration-q-a) · [Heptabase — Find content on a whiteboard](https://support.heptabase.com/en/articles/10410065-i-can-open-my-whiteboard-but-i-can-t-find-my-content)

**产品推论：**Relation Space 可以表达局部空间，但 exhaustive Catalog、List equivalent、Search、scope anchor 与 exact return 仍是不可替代的骨架。

## 1.6 组织概念越多，用户越需要判断树

**观察事实：**Capacities 分开 Spaces、Object Types、Tags、Collections、Queries、Properties 和 Labels，并为选择组织方式提供 decision tree。  
[Capacities — Organizational structures](https://docs.capacities.io/reference/organizational-structures)

**产品推论：**内部可以有 Library View、Placement 和 Projection，但日常概念仍保持 Group、Topic、Knowledge、Relation、Source 五个。用户不应在第一次写作时选择“Collection / Tag / Query / Folder / Type”。

---

# 2. Group 合同

## 2.1 成为 Group 的三问

一个范围满足三问中的至少两项，系统才推荐建立 Group：

1. **整体重返：**用户是否会反复以它为整体进入，而不只是从父范围继续深入？
2. **独立导读：**它是否需要自己的 Boundary、Overview 和主要入口？
3. **跨群表达：**它是否需要与其他 Groups 表达整体 Relation，而不只是具体 Knowledge exits？

内容数量不是决定因子。

## 2.2 Group 必须拥有的身份

| 责任 | Bare Group | Oriented Group | 说明 |
|---|---|---|---|
| stable identity | 必须 | 必须 | rename / restructure 不改变 |
| name | 必须 | 必须 | 唯一创建门槛 |
| Boundary | 可空 | 建议明确 | 说明包含 / 排除 / governing question |
| Overview | 可空 | 有 orientation | 用户 prose 可少量开始 |
| root Knowledge | 可有 | 可有 | 不强迫建立 Topic |
| Topics | 可空 | 按需 | 不是成熟度要求 |
| Sources / Relations | 可空 | 按真实内容 | 不以数量打分 |
| history / restore | 必须 | 必须 | Bare 也拥有 |

Bare / Oriented 描述当前 orientation coverage，不是阶段评分，不产生完成度和升级任务。

## 2.3 Boundary 最小合同

Boundary 可以只是一句话，但应能够逐渐回答：

- governing question：这个 Group 反复回答什么；
- includes：什么属于当前范围；
- excludes：什么明确不属于；
- neighbor distinction：与最容易混淆的 Group 如何区分；
- time / jurisdiction / audience：只有改变适用性时才出现。

Boundary 不成为创建表单门槛。AI 可以根据内容提出草稿，但不能因聚类自动改变。

## 2.4 Group root content

Group Overview 之后可以直接放 Knowledge。用户不需要为了“目录整齐”建立只有一个孩子的 Topic。

Root Knowledge 是正式 Placement，不叫未归类；它可以与 Topics 并存。只有当一组 root Knowledge 形成稳定阅读分支时，才建议建立 Topic。

## 2.5 Group 不结构性嵌套

- Library Catalog 中所有 current Groups 处于同一 canonical level；
- broad / narrow domain 使用 Group Relation statement 表达；
- Saved View 可以同时列出 broad 与 narrow Groups，但不改变两者 identity；
- 从 broad Group Overview 可以通过重要 Group Relation / exit 打开 narrow Group；
- Up 返回结构 owner；Back 返回访问历史；Group Relation Open 不是“进入子文件夹”。

---

# 3. Topic 合同

## 3.1 Topic 是什么

Topic 是 Group 内稳定、可寻址、可递归的结构身份，回答“在这个 Group 里，当前沿哪条分支深入”。它不拥有：

- 独立 Group Boundary；
- Library Catalog entry；
- Group-level Network node；
- 独立权限 / Library；
- 与父 Group 隔离的 Search corpus。

## 3.2 三种 Topic Opening

每个 Topic 都可 Open，但不要求每层写一篇页面：

| Opening | 默认内容 | 用户负担 |
|---|---|---|
| Structural | title、breadcrumb、children、root Knowledge、当前位置 | 零额外写作 |
| Oriented | Structural + 一句 orientation + 主要入口 | 极低 |
| Authored | Oriented + 用户维护的局部导读、限定和未知 | 按真实需要 |

这三种是当前内容形态，不是阶段、质量分或升级队列。

## 3.3 Expand 与 Open 分开

| 动作 | 后果 |
|---|---|
| Expand / Collapse | 只改变 Structure projection，不改变主阅读对象或 history |
| Focus | 选择 Topic，供键盘或 inspector 使用 |
| Open | Topic Opening 成为主阅读目标，记录 Return Envelope |
| Direct Open Knowledge | 绕过中间 Topic pages，breadcrumb 仍显示完整结构路径 |
| Up | 回到直接结构 owner |
| Back | 回到上一访问现场，可能不是 parent |

用户可以从 Overview、Search、Relation、Source citation 或 deep link 直达深层 Knowledge；丰富层级不能变成强制点击税。

## 3.4 递归深度

模型不设置固定三层上限，但显示只围绕当前路径：

- breadcrumb 保留 ancestors，过长时压缩中段而不丢 current parent；
- Structure 默认显示 current path、相邻 siblings 和一层 children；
- 用户显式展开才增加更多层；
- mobile 默认通过 list / drill-in 表达同一层级，不展示微型树；
- 当连续多个 Topic 各只有一个 child、没有 orientation、没有 root Knowledge 时，系统可以建议 flatten，但拒绝零副作用。

系统不能用“超过五层”自动移动内容；深度问题必须由真实导航成本证明。

## 3.5 祖先聚合不是多 Placement

一条 Knowledge Placement 指向一个具体 Scope：Group root 或某个 Topic。祖先 Overview / Topic Opening 可以在 Projection 中显示 descendant Knowledge，但不会因此生成祖先 Placements。

```text
Placement p1 → Topic T3
Projection(T2, include descendants) shows K1
Projection(Group, main entries) may show K1

count(active Placements of K1) = 1
```

若用户明确把同一 Knowledge 放进 sibling Topic T4，才建立第二个 Placement，并显示当地 context。

## 3.6 Topic 与 Saved View

Topic 是用户维护的结构路径；Saved View 是按规则或策展形成的动态观察。

- Topic children 变化需要显式 Move / Create / Delete；
- Saved View 结果随规则自动变化；
- 把 Search snapshot 保存为 View 不创建 Topic；
- 只有用户确认“这是一条长期阅读分支”时，才可从 View 形成 Topic Candidate；
- 删除 View 不影响 Topics、Knowledge 或 Placements。

---

# 4. Overview 合同

## 4.1 Group Overview 的阅读顺序

默认依次回答：

1. 这个范围是什么；
2. 用户为什么会进入；
3. 主要从哪几条路径深入；
4. 当前最重要的限定、争议或未知是什么；
5. 哪些相邻 Groups 值得跨出去。

它不是“所有内容摘要”，也不按最近更新时间生成 feed。

## 4.2 Topic Opening 的阅读顺序

默认依次回答：

1. 当前位于哪条 Group path；
2. 这个分支解决什么；
3. root Knowledge 与 subtopics 是什么；
4. 是否有一条影响理解的限定或出口；
5. 怎样继续或回到上层。

## 4.3 三种权力

| 层 | Owner | 是否 Current | 编辑后果 |
|---|---|---|---|
| Editorial prose | 用户 / Scope | 是 | 普通安全提交 |
| Structure projection | canonical structure | 可重建 | 调整显示不改正文 |
| Proposal overlay | AI / change trigger | 否 | 采纳后才形成局部 Current revision |

AI 生成的 orientation scaffold 只能以 Projection 身份出现，不能伪装成用户 prose。

## 4.4 信息预算

Group Overview Calm 层优先：

- 1 条 orientation；
- 3–7 个主要入口；
- 1 段结构导读；
- 最多 3 个重要 relations / exits；
- 最多 1 条真正影响当前理解的 change / unknown。

Topic Opening 的预算更小；当它没有独立方向价值时保持 Structural，而不是生成填充文字。

## 4.5 结构变化后的 Overview

- Move Topic：只刷新受影响结构 projection；
- Rename：更新结构标签和链接显示，不改 Editorial prose 含义；
- Split / Merge：提出具体 prose Diff，不自动拼接两篇 Overview；
- Promotion：Topic authored orientation 可作为新 Group Overview 草稿，但必须由用户确认；
- Source change：只 cue 受影响 Claim / section，不整页重写。

---

# 5. Library Catalog 与大量 Groups

## 5.1 Catalog 的不变量

`All Groups`始终是可穷尽、可搜索、可排序的 current Groups Catalog。以下都是快捷 Lens，不能取代它：

- Pins；
- 最多一条安全 Resume；
- Recent；
- Saved Views；
- Search results；
- Network；
- AI suggestions。

本节只拥有 All Groups membership、Saved View 与规模结构。Resume → Pins → All Groups 的默认注意力、cold start、All Knowledge 次级 inventory，以及 Resume / Pin / Recent / Saved Path / Recovery 的生命周期由 Library 入口合同拥有。普通 Open Group 进入 Current Overview；只有显式 Continue 才恢复深层 scene。

## 5.2 Saved View 的身份

Saved View 是 Library supporting identity，可以是：

- **Manual View**：用户策展的一组 Group refs 与顺序；
- **Rule View**：按属性、时间、状态或明确 query 动态返回 Groups；
- **Snapshot View**：保留某次明确结果及时间，用于比较而非持续组织。

Saved View：

- 不拥有 Groups；
- 不改变 Group Boundary；
- 不创建 Group Relations；
- 不影响 Ask scope，除非用户明确从该 View 发起 Ask；
- 可以被 pin、rename、archive、delete；
- 不允许递归嵌套成第二棵目录树。

一个 Group 可以出现在多个 Views；删除 View 对 Group 零副作用。

## 5.3 为什么不新增“Area / Domain / Folder”对象

Library 规模变大时，用户真正需要的是：

- 找到某组 Groups；
- 保存一种浏览切片；
- 跨多个 Groups Ask / Compare；
- 保持 All Groups 可穷尽；
- 不因换一个目录位置改变知识身份。

Saved View 已能承担这些任务。只有未来证据证明某种上层范围需要独立 Boundary、Overview、Relations 和整体重返，它本身就应成为 Group，而不是再增加 Area 对象。

## 5.4 两条规模轴

旧的`F1 / F10 / F100 / F10K`容易把 Groups 数量与 Knowledge 数量混为一谈。当前改为两条轴：

### Group scale

| 规模 | Catalog 责任 | Network 责任 |
|---|---|---|
| G1 | Group 可直接成为主入口；独立知识仍合法 | 0 relation 是正常状态 |
| G10 | All Groups 可一次扫描；Pins / Resume 克制出现 | 少量 Current Group Relations 可直接图示 |
| G100 | Search、stable sort、filters、Manual / Rule Views；All Groups 仍穷尽 | 默认 scope summary + List，用户选择 View / Group 后再画图 |
| G1K | 虚拟化 / 分页属于实现；产品仍是 All Groups + Views + Search | anchor required；禁止无范围全图和 AI Top N 冒充全库 |

### Knowledge scale

| 规模 | Group 内责任 |
|---|---|
| K1 | root Knowledge 合法，不要求 Topic |
| K100 | Overview + Topic path + local Search；不显示全部卡片墙 |
| K10K | 只展开当前路径；Search / Saved View / anchor direct；Overview 保持策展入口 |
| K100K | canonical content 可穷尽导出与查找；任何可视图都必须 scope-bound |

这些是设计责任，不是已经通过的性能承诺。

## 5.5 Catalog 排序与重要性

默认允许用户可解释的排序：

- 用户自定义；
- 名称；
- 最近打开 / 最近修改；
- 创建时间；
- lifecycle / explicit property。

AI relevance、degree、使用频率或“知识成熟度”不能静默成为默认顺序。AI 可以提供临时 View，并解释规则。

## 5.6 Archived Groups

- Current Catalog 默认不混入 archived Groups；
- Archived 是稳定 utility view，可 Search；
- Group archive 不结束 Placements，也不让其 Knowledge 变成独立知识；
- Restore 保留 Group identity、Topic paths、Placements 与 History；
- 删除 Group 前必须处理结构与 Placements，Archive 不能被当作轻量 Delete。

---

# 6. 结构演化合同

## 6.1 Rename

- Group / Topic identity 不变；
- display path 更新；
- old deep link 解析到 current，并可查看 historical label；
- Relation statement 只有在名称改变导致语义不再准确时才 cue review；
- Editorial prose 不做全局字符串替换。

## 6.2 Move Topic within Group

- Topic identity、children 与 direct Placements 保持；
- owner path 改变并记录 History；
- ancestor projections 重新计算；
- Saved Path / deep link 使用 redirect；
- Back 返回进入前现场，Up 使用新 owner。

## 6.3 Move Topic across Groups

这是跨 Boundary 操作，必须预览：

- Topic 与 descendants 的新 owner；
- direct / descendant Placements 的 context 是否仍成立；
- source truth 不移动；
- Group Overview projections 的增减；
- Group Relations、exits 与 Saved Paths 的受影响项；
- 失败时整项回滚，不能移动一半。

Topic identity 可以保持，但 owner change 与 old path redirect 必须进入 History。

## 6.4 Promote Topic to Group

Promotion 不复制 Knowledge：

1. 建立新 Group identity 与 Boundary draft；
2. Topic subtree 成为新 Group 的 root structure；
3. 相关 Placements 事务性改 owner；
4. old Topic path 成为 redirect；
5. authored Topic orientation 只作为 Overview proposal；
6. 原 Group 保留明确 cross-group exit；是否建立 Group Relation 另行判断。

Promotion 取消或失败零副作用。

## 6.5 Absorb Group into Topic

只有当 Group 不再需要独立 Boundary / Overview / Group Relations 时才允许：

- 选择目标 Group / Topic；
- 将内部 Topic tree 和 Placements 迁入；
- 对 Group Relations 逐条 End、Redirect 或保留到 successor Group；
- 原 Group identity 进入 redirected / archived History；
- Overview prose 不自动拼入目标 prose。

## 6.6 Split Group

- 先声明新 Boundaries，而不是按 Topic 数量自动切；
- Knowledge 可 Move Placement 或 Add second Placement；
- shared Knowledge 不复制；
- Relations 按 endpoints 保留，Group Relations 重新检查 coverage；
- Overview Editorial prose 由用户选择保留、复制为 draft 或重新写；
- Source identity 不按 Group 拆分。

## 6.7 Merge Groups

- 选择 canonical Group identity；
- 另一个 Group 进入 redirect / historical；
- 同名 Topics 不自动合并，只形成 review pair；
- 同一 Knowledge 在两个来源 Groups 的 Placements 可保留两个 context，也可显式 collapse；
- Relations 不按名称去重；
- 两篇 Overview 不拼接成 Current；
- old Group links、Saved Paths 与 Answer snapshots 仍能解释当时 Scope。

## 6.8 Delete Topic

删除前按对象类型分开预览：

- subtopics：move to parent / move elsewhere / delete structure；
- direct Placements：move / end；
- Knowledge：不会因 Topic 删除而静默删除；结束最后 active Placement 后进入独立知识；
- authored Topic prose：archive snapshot / export / discard；
- redirects、Saved Paths 与 deep links：明确 successor 或 orphan state。

## 6.9 Delete Group

删除不是 Archive 的快捷方式。必须逐类选择：

- Move Placements to another Group / Topic；
- End Placements，Knowledge 可能成为独立知识；
- Archive selected Knowledge；
- End / supersede Group Relations；
- redirect or orphan external paths；
- retain History / export package。

任何批量默认都显示实际对象数量，但不使用恐吓或“待清理”语气。

---

# 7. 导航与返回合同

## 7.1 Return Envelope

从 Overview / Topic / Knowledge 打开任何深层对象前保存：

- origin object；
- Topic path；
- Anchor；
- scroll；
- focus；
- expanded Topics；
- active Saved View / filter；
- Relation presentation。

关闭 Source / Relation Inspector、Compare 或 temporary Search 后恢复原现场。

## 7.2 Breadcrumb

Breadcrumb 表达结构 path，不表达访问历史：

```text
Library / Group / Topic / Subtopic / Knowledge
```

- 点击 ancestor 是 Open；
- Up 去直接 structural owner；
- Back 去上一访问现场；
- Placement 切换会改变结构 path，但不改变 Knowledge identity；
- 从 Search 直达时 breadcrumb 仍显示 chosen Placement；若多个 Placements，先用命中 context，并允许切换。

## 7.3 Multiple Placements 的路径选择

打开同一 Knowledge 时路径优先级：

1. 当前 origin Scope 的 Placement；
2. Search / Relation result 明确携带的 Placement；
3. 用户标记的 primary Placement；
4. 最近明确使用的 Placement；
5. 若仍 ambiguous，显示选择，不替用户静默决定。

切换 Placement 只改变 context、breadcrumb、neighbor priority 和 Return Envelope，不改变正文 Current。

## 7.4 Anchor 与结构变化

- Topic move 不改变 Knowledge Anchor；
- Knowledge split / merge 使用 redirect / historical locator；
- old breadcrumb 可以显示 historical path，再跳 current；
- orphan state 说明目标是否删除、移动、无权限或仅 source unavailable；
- Index unavailable 时 direct identity / stored path 仍应解析。

---

# 8. 状态与失败

| 状态 | 必须仍然是真的 | 用户可做 |
|---|---|---|
| Empty Library | 没有 Groups 不等于没有合法起点 | 写独立 Knowledge / 建 Bare Group |
| Bare Group | identity 与 History 已成立 | 写 root Knowledge / Topic / Boundary |
| Empty Topic | stable address 已成立 | 写 orientation / Knowledge / Subtopic / delete |
| Deep link redirected | historical path 可解释 | 打开 current / 查看 History |
| Index partial | Catalog truth 不受影响 | 浏览结构 / last good / retry Search |
| Projection rebuilding | Current prose、Topics、Placements 仍存在 | 直接打开 / List / wait |
| Topic move failed | old owner 与 paths 保持 | retry / inspect error |
| Promotion partial | 不提交任何一半结果 | retry / export draft |
| Archived Group | Placements 仍 active | Search / open Archive / restore |
| Deleted owner | Knowledge 不被静默删除 | open successor / independent / History |
| Offline | Current structure 可读写 | local checkpoint / later sync |

---

# 9. 三份真实 Fixture 映射

## 9.1 Fixture A · 时效资格

- 两个 Groups 拥有独立 Boundaries；
- 每群多层 Topics 与 root / deep Knowledge；
- cross-group exits 不自动成为 nested Group 或 Group Relation；
- Source change 只刷新相关 Overview projection；
- deep Evidence close 恢复原 Question criterion 与 Topic path。

## 9.2 Fixture B · 概念学习

- 每群 4 个一级 Topics + 12 个二级 Topics；
- 三条 Knowledge 各有双 Placement；
- ancestor view 不增加 Placement count；
- G-MEM 与 G-STUDY 有两个 same-pair Group Relations，但不是 parent / child；
- Pair close 精确回到 origin Knowledge 与 Anchor。

## 9.3 Fixture C · 基础可用性

- Empty Library 可写独立 Knowledge；
- Bare Group 无 Topic / Overview 也合法；
- 添加 / 移除最后 Placement 改变独立知识 projection；
- Group archive 不结束 Placement；
- Search direct open 与 clean restore 保持 path / identity。

---

# 10. 合成规模压力夹具

本节是 synthetic scale fixture，不是用户数据或性能测试结果。

## 10.1 S-G100

```text
current Groups: 120
archived Groups: 18
Independent Knowledge: 37
Saved Views:
  - 人文与社会：manual 22 Groups
  - 计算与系统：manual 31 Groups
  - 当前研究：manual 7 Groups
  - 最近 90 天有实质变化：rule 16 Groups
  - 含 provisional Questions：rule 9 Groups
Group Relations: 46 current, 12 historical, 8 candidates
Knowledge: 12,400 current
Placements: 15,870 active
Sources: 4,800
```

## 10.2 必须成立

1. All Groups 能穷尽 120 current Groups；
2. 同一 Group 可以出现在多个 Views，但只有一个 identity；
3. View 删除不改变 Group、Relation 或 Ask history；
4. Network 默认不直接画 120 nodes + 46 edges；先显示 scope summary / List / choose View；
5. Search 命中深层 Knowledge 后显示准确 Group / Topic path；
6. 37 条独立 Knowledge 不显示为待清空 badge；
7. archived 18 Groups 不混入 current Catalog，但可搜索；
8. AI 回答 whole Library 时说明实际覆盖，不以 120 Groups 标签冒充全部读取；
9. export / restore 不依赖 Saved Views、layout 或 index 也能恢复 canonical truth；
10. mobile 与 keyboard 可完成 View → Group → Topic → Knowledge → Back。

## 10.3 必须拒绝

- 自动创建“区域 / 大洲 / 星系”等永久上层对象；
- 把 degree 或 recent activity 当默认重要性；
- 用漂亮聚类隐藏未覆盖 Groups；
- 把 Manual View 变成 Group owner；
- 多 View appearance 计为多个 Groups；
- archived Group 内容涌入独立知识；
- Search-only 作为唯一完整 Catalog。

---

# 11. Appendix Acceptance Checks

这些检查深化 v6 AC-01–AC-32，不新增第二套核心验收编号。

| HC | 映射 v6 AC | 验收 |
|---|---|---|
| HC-01 | AC-01 / 03 | Empty Library、Bare Group 与 Independent Knowledge 共用同一 Library Shell |
| HC-02 | AC-03 | 只有名称的 Group 可再次打开，不显示完成度 |
| HC-03 | AC-04 | Topic 可递归，Search / deep link 可绕过中间 opening |
| HC-04 | AC-04 | Expand 不改变主阅读对象；Open 才写 Return Envelope |
| HC-05 | AC-05 | Structural Topic 不生成假 Editorial prose |
| HC-06 | AC-05 | ancestor aggregation 不生成 Placements 或影子 Knowledge |
| HC-07 | AC-07 | 同一 Knowledge 在 sibling Topics 的两个 Placements 共享正文 identity |
| HC-08 | AC-08 | 移除最后 active Placement 后进入独立知识；Archive Group 不触发 |
| HC-09 | AC-10 | Topic move / rename 后 old path 可解释并 redirect |
| HC-10 | AC-11 / 13 | broad / narrow Groups 使用完整 Relation，不使用 nested Group edge |
| HC-11 | AC-14 | Saved View / shared appearance 不创建 Relation |
| HC-12 | AC-17 | deep direct open 关闭后恢复 origin path、Anchor、scroll、focus 和 expanded Topics |
| HC-13 | AC-18 | Search result 携带命中 Placement，多个 Placements 不静默选错 |
| HC-14 | AC-26 | Promotion / View / Group Candidate 拒绝零副作用 |
| HC-15 | AC-27 | Structure change 只刷新受影响 Overview projection / Proposal |
| HC-16 | AC-28 | Restore / merge / split 保留 predecessor、redirect 和 historical path |
| HC-17 | AC-29 | Index / Projection unavailable 时 Catalog 与 direct identity 仍可用 |
| HC-18 | AC-30 | Export / Restore 不依赖 Views、layout、embeddings 或 cache |
| HC-19 | AC-31 | desktop tree 与 mobile drill-in 保留相同 path / direct open / return |
| HC-20 | AC-32 | keyboard / screen reader 可区分 Expand、Open、Up、Back 与 current level |

---

# 12. 后续设计证明责任

后续 Surface Skeleton 和视觉设计必须证明：

1. Library 在 G1、G10、G100 使用同一骨架；
2. All Groups 永远可达，Pins / Resume / Views 不把它藏掉；
3. Saved View 看起来像 Lens，而不是第三种知识容器；
4. Group、Topic、Knowledge 三种 Open 既连续又可辨；
5. Structural Topic 不像空白失败页；
6. Authored Topic 不抢走 Knowledge Paper 的阅读主位；
7. expand、open、up、back、close 的后果无需猜测；
8. multiple Placements 显示同一 identity 与当前 context；
9. promotion / merge / split / delete preview 不使用数据库术语墙；
10. G100 Network 先 scope / list，不能用拥挤全图冒充完整；
11. archived Group 与 Independent Knowledge 不混淆；
12. desktop、compact、mobile、keyboard 和 screen reader 责任等价。

这些是状态和行为证明，不等于必须新增十二张主屏。

---

# 13. 仍未冻结的视觉与实现选择

- G10 时 Catalog 是 list、cards 还是两者可切换；
- Saved Views 的具体命名、入口和最大 pin 数；
- breadcrumb 压缩阈值；
- Topic tree 在 desktop 的宽度和层级线样式；
- Topic Opening 的具体版式；
- G100 的默认分页 / virtual scroll 实现；
- promotion / split preview 是 modal、sheet 还是 workspace；
- Group Relation 中“子领域”的最终 starter phrase；
- 数据库 schema、索引和缓存策略。

这些选择不能反向允许 nested Groups、强制中转、影子 Placements 或 Search-only Catalog。

---

# 结论

丰富层级不是“可以无限缩进”。它必须同时给用户三种能力：从 Overview 获得方向、直接进入需要的深度、在返回时仍知道自己在哪里。

本产品因此只保留一种结构性深入：Group 内的 Topic hierarchy。Library 的大量 Groups 由 Views 观察，Groups 之间由 Relations 解释，同一 Knowledge 由 Placements 复用。四种机制各自回答一个问题，互不冒充。
