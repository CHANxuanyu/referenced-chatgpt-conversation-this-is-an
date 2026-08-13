# AI-native 个人知识库

## Library 入口、目录浏览与继续阅读合同 v1.0

> Canonical：`AI-native-个人知识库-终局产品设计文档-v6.0.md`  
> 文档状态：**ACTIVE_APPENDIX；已完成 Canonical 同步、注册与相邻责任划分**  
> 负责范围：Library 启动、日常返回、Groups / Network 入口、All Groups、All Knowledge、独立知识、Resume、Pins、Recent、Saved Views / Paths 的入口语义，以及大规模和失败时的目录可用性  
> 不负责范围：Group / Topic / Placement 的结构真相、Knowledge 正文、Relation 真相、Ask / Answer、Source formation、视觉风格或可点击原型  
> 表面责任边界：`AI-native-个人知识库-表面架构、场景家族与完整设计证明合同-v1.0.md`拥有统一 App Shell、Library scene 的 Surface roles、Search / Ask / Add transitions、Return Envelope 与 DPB；本文拥有入口、Catalog、Open / Continue 与快捷状态语义  
> 用户语言边界：`AI-native-个人知识库-用户可见信息架构、产品语言与复杂度披露合同-v1.0.md`拥有`知识库 / 知识群 / 知识网络 / 独立知识`、打开 / 继续 / 返回与空态文案；本文只拥有入口和目录真相  
> 日期：2026-08-10

---

# 0. 执行结论

## 0.1 一句话产品答案

**Library 是用户每天进入个人知识的稳定目录，不是推荐首页、活动流、聊天入口或知识图海报；它先保证全部知识可被找回，再用一条明确 Resume、少量 Pins、Recent 和 Saved Views 帮助用户继续。**

## 0.2 本轮冻结的 36 项决定

1. **Library 是唯一稳定入口。**打开应用、打开新窗口或关闭深层场景后，都能回到同一个 Library Shell。
2. **Groups / Network 是同一 Library 的两种视图。**二者共享对象、范围、selection 与 filter，不是 Home / Atlas 两个产品中心。
3. **应用启动默认先显示 Library，不自动把用户送入上次深层正文。**连续性由显式 Resume 提供。
4. **Resume 最多一条。**它恢复最近一个符合安全条件的 committed scene，不形成继续队列。
5. **Recovery 不是 Resume。**未提交缓冲、崩溃恢复和冲突修复使用单独、就地且更保守的恢复机制。
6. **普通打开 Group 始终进入其 Current Overview。**只有选择`继续`才恢复该 Group 内上次安全的深层场景。
7. **Resume 只有在目标、revision、placement、anchor 和 presentation 都可安全解析时才精确恢复。**
8. **无法精确恢复时降级到最近的安全 owner。**产品说明哪些位置未能恢复，不伪装成功。
9. **Resume 是 device-local Workspace state。**它不是 Knowledge、History revision、Saved Path 或跨设备真相。
10. **Pin 是用户显式创建的快捷入口。**Pin 不表达重要性、归属、成熟度、事实权重或 AI 排名。
11. **Recent 记录成功 Open。**Inspect、hover、Peek、搜索命中、AI 使用或后台修改不写入 Recent。
12. **最近打开与最近修改分开。**二者可以作为可解释排序，但不能被一个含混的“最近”合并。
13. **Unpin、清除 Recent 或删除 Resume 都不改变任何知识。**
14. **Saved Path 是用户保存的探索顺序。**它不是 Resume、Recent、Relation truth 或目录结构。
15. **Saved View 继续继承结构合同。**Manual / Rule / Snapshot View 是 Group catalog 的观察方式，不拥有 Group，也不形成第二棵目录树。
16. **All Groups 是全部 Current Groups 的穷尽目录。**任何 lens、推荐或个性化都不能替代它。
17. **All Knowledge 是次级完整 inventory。**它帮助按 Knowledge identity 找回内容，但不是第三个主视图、第二棵层级或卡片墙首页。
18. **独立知识是 All Knowledge 中零 active Placements 的派生子集。**它不是 Inbox、未整理状态、待办或错误。
19. **Catalog 在 Search、AI、embedding、relation layout 和派生索引不可用时仍须工作。**
20. **Empty Library 的首要动作是直接写下第一条知识。**建立 Group、保存资料和提问同时可达，但不阻断写作。
21. **Group catalog entry 只承载识别与进入所需信息。**名称、Boundary / orientation、稳定入口与必要状态优先；不用卡片塞入成熟度、置信度和活动摘要。
22. **默认顺序必须稳定并可解释。**存在用户顺序时沿用用户顺序，否则使用名称；最近打开、最近修改和 AI relevance 必须由用户显式选择。
23. **Search 直接找目标，Filter 改变当前列表切片。**二者不能用同一个无语义输入状态混淆。
24. **临时 filter 不自动保存。**只有显式`保存视图`才形成 Saved View。
25. **Groups ↔ Network 尽量保留可解释的 scope、selection 与 filters。**不能映射的条件要明确放下，而不是静默改义。
26. **零 Group Relation 不移除 Network。**Network 提供诚实空状态和 List Equivalent，不生成装饰性连线。
27. **Resume、Pins、Recent、Saved Views、Search results 与 AI suggestions 永远不能遮蔽 All Groups。**
28. **Library 同时最多出现一项高影响维护提示。**没有 review feed、待整理红点或自动生成的维护队列。
29. **Archived 与 Current 分开。**归档 Group 不结束 Placements，也不把群内知识重新归类为独立知识。
30. **快捷入口的目标失效必须显示真实状态。**relocated、historical、archived、deleted、unavailable 与 permission / local-file missing 不混为“打不开”。
31. **多个窗口各有自己的 Workspace scene。**Library 只展示最近活动窗口的一条安全 Resume；不同窗口不互相抢夺阅读位置。
32. **产品不依据使用频率静默重排。**行为数据可以生成显式、可检查的临时 View，不能改写默认目录。
33. **G1、G10、G100、G1K 使用同一 Library 骨架。**规模只改变 list virtualization、filters、Search 和 scope 选择，不产生新产品中心。
34. **Offline、index partial 和 graph unavailable 时，Canonical Catalog 仍可浏览。**派生能力降级不能把用户挡在知识之外。
35. **Compact、mobile、keyboard 与 screen reader 保持责任等价。**空间图可以降为列表，完整目录、Resume、Open 和 Back 不能消失。
36. **Export / Restore 区分长期知识与工作现场。**Canonical content、placements、views 和显式 pins 可迁移；Resume / Recent 默认是可选的 device-local 状态，Search cache 和 graph layout 不是恢复必需品。

## 0.3 这不是一个视觉决定

本合同不决定：

- Library 使用左栏、顶部栏还是分段控件；
- Group entry 是行、书脊、卡片还是紧凑表格；
- Resume 是横条、入口块还是上下文动作；
- 方向 3 + 2 的色彩、材质、动效和空间比例；
- Screen 1 的最终构图。

本合同先冻结这些视觉必须证明的产品语义。只有在真实 fixture、空状态、G100、失败和可访问性状态都能成立后，才进入视觉探索。

---

# 1. 为什么产品内部已经清楚，入口仍然不完整

## 1.1 进入 Group 以后已经有主干

现行产品已经定义：

```text
Library
  → Group Overview
    → Topic Opening
      → Knowledge Paper
        → Section / Claim
          → Evidence Fragment
```

关系空间、Ask、Source formation、History 和 exact return 也各有 owner。真正未闭合的是更早的三秒：

1. 用户打开应用先看见什么；
2. 怎样继续昨天的现场，又不被软件替自己决定；
3. 知识规模增长后，怎样确定自己仍然看得见全部内容。

如果这三秒没有清楚合同，产品会在实现时自然滑向三种常见但错误的形态：

- 用漂亮全局图替代目录；
- 用 Recent / 推荐 / 待整理替代全部知识；
- 用自动恢复上次页面替代清楚、可控的入口。

## 1.2 Library 的首要承诺不是“智能”，而是“没有把东西藏起来”

对个人知识库而言，首屏的基础信任来自：

- 我知道有哪些 Groups；
- 我能找到没有归群的 Knowledge；
- 我知道昨天在哪里；
- 我能选择继续，也能重新从 Overview 开始；
- 系统能力部分失败时，我仍能进入自己的知识；
- 软件没有根据不透明算法偷偷决定什么更重要。

AI、Network 和动态视图建立在这层信任之上，不能替代它。

## 1.3 “看全部”与“看得懂全部”是两个任务

`All Groups`与`All Knowledge`都必须可穷尽，但不承担同一责任：

| 表面 | 回答的问题 | 默认地位 |
|---|---|---|
| All Groups | 我有哪些长期知识范围，从哪里整体进入 | Groups 主视图的稳定主体 |
| All Knowledge | 某条具体 Knowledge 在哪里、叫什么、有哪些 placements | 次级 inventory |
| 独立知识 | 哪些 Current Knowledge 目前没有 active Placement | All Knowledge 的派生子集；Groups 入口中的安静兜底 |
| Network | Groups 之间有哪些已确认关系 | Library 的第二视图 |

All Knowledge 不能变成首屏卡片墙，因为 Knowledge 数量远大于 Group 数量，也没有 Overview 提供的边界和阅读顺序。它存在是为了对象级找回和治理，不是为了推翻以 Group 为主的产品心智。

---

# 2. Library 的表面架构

## 2.1 冻结的信息架构

```text
Knowledge Library
├─ Groups view
│  ├─ Resume                     0..1 safe workspace shortcut
│  ├─ Pins                       explicit shortcuts
│  ├─ All Groups                 exhaustive canonical catalog
│  ├─ Independent Knowledge      quiet derived subset / shortcut
│  ├─ Recent                     secondary opened history
│  └─ Saved Views                manual / rule / snapshot lenses
├─ Network view
│  ├─ Current Groups
│  ├─ Current Group Relations
│  └─ List Equivalent
└─ Supporting inventory / utilities
   ├─ All Knowledge
   ├─ Archived
   ├─ Saved Paths
   ├─ History / Recovery / Trash
   └─ Settings / Import / Export
```

这是一套责任图，不要求界面同时展示所有项。

## 2.2 默认注意力顺序

Groups view 的默认信息顺序是：

1. 有安全现场时，最多一条 Resume；
2. 用户明确固定的少量 Pins；
3. All Groups；
4. 当存在时，以安静入口呈现独立知识；
5. Recent 与 Saved Views 作为次级 Lens；
6. Archived、All Knowledge 和管理工具在 supporting navigation。

当 Resume 或 Pins 很多时，不允许把 All Groups 挤到首屏以下变成“查看更多”。Resume 固定最多一条；Pins 超出合理密度后折叠为可进入的快捷区域，而不是持续横向扩张。

## 2.3 Library 不是 Dashboard

Library 不默认展示：

- 今日回顾数量；
- 待整理来源；
- AI 推荐阅读；
- 知识成熟度；
- 本周编辑统计；
- 活跃度排行榜；
- 尚未建立关系的数量；
- “你可能感兴趣”；
- 自动生成的知识健康分；
- 无限 Recent feed。

这些信息若未来有明确任务，可以成为显式 View、局部提示或 supporting utility；它们不能改变 Library 的默认身份。

## 2.4 Library 不是一张全局图

Network 是 Library 的合法第二视图，但不能取代 Catalog，因为：

- 没有 Group Relation 的 Group 仍然是完整 Group；
- 空 Library、G1 和零 Relation 都是合法状态；
- 图的布局不是 canonical order；
- G100 / G1K 时不能同时保证穷尽、稳定与可读；
- keyboard、screen reader 和 graph failure 需要同义 List。

Network 的价值是解释已确认的群关系，不是证明 Library “很丰富”。

---

# 3. 启动、返回、Resume 与 Recovery

## 3.1 四种进入必须分开

| 进入类型 | 默认结果 | 理由 |
|---|---|---|
| 冷启动 / 正常重开应用 | Library，保留上次 Groups / Network 视图偏好 | 给用户稳定定位，不自动承诺深层现场仍安全 |
| 打开新窗口 | 新的 Library scene | 新窗口表达新任务，不复制深层上下文 |
| 从深层场景选择 Library | 同一窗口 Library，保留可返回的 origin envelope | 允许浏览其他范围后返回 |
| 崩溃 / 未提交内容恢复 | 最近安全 Library 或 owner + Recovery 提示 | 未提交状态不能伪装为普通 Resume |

应用可以恢复窗口尺寸、侧栏开合和 Library view preference，但不能仅因为“上次退出时在某段正文”就自动深开该段。

## 3.2 Resume 的完整语义

Resume 是一句可理解的继续承诺：

> 继续阅读「间隔重复的适用边界」· 在“迁移到课程安排”这一节

它至少说明：

- 主对象名称与类型；
- 所属 Group / Topic context；
- 上次安全动作或位置；
- 是否可以精确回到 Anchor；
- 最近活动时间只作解释，不作为重要性；
- `继续`与`从 Overview 打开`两个不同后果。

Resume 不显示系统内部 workspace ID、token、graph coordinate 或 revision hash。

## 3.3 Resume eligibility

一个 scene 只有同时满足以下条件才可成为 Resume：

1. 主 target 仍存在，或有唯一 redirect；
2. target 是 Current，或用户当时明确在读 historical revision；
3. Group / Topic / Knowledge owner 可解析；
4. Placement context 仍存在，或有唯一安全替代；
5. Anchor 为 exact / relocated，而不是 ambiguous / orphaned；
6. 上次状态不是 destructive preview、delete confirmation 或半完成批量操作；
7. 没有未决的 Source import、AI Proposal、semantic Diff 或 write conflict 被错误视为已完成；
8. 权限、本地文件与必要内容当前可读取；
9. presentation 可在当前设备责任等价地表达；
10. 保存的状态来自 committed event，而不是 hover、Peek 或后台 selection。

## 3.4 精确恢复与安全降级

恢复结果按以下顺序解析：

```text
Exact scene
→ Same Knowledge, relocated Anchor
→ Same Knowledge, nearest stable section
→ Same Topic Opening
→ Same Group Overview
→ Library with unavailable Resume explanation
```

每次降级必须：

- 保留用户仍可理解的 owner；
- 显示“原位置已移动 / 不可用”的短说明；
- 提供 History / locate current / remove Resume 等相关动作；
- 不把近似位置标成精确恢复；
- 不自动创建新 Placement、Relation 或修订。

## 3.5 普通 Open 与 Continue

| 动作 | 结果 |
|---|---|
| Open Group | Current Group Overview，从稳定顶部开始 |
| Continue Group | 该 Group 内最近安全 Reading / Explore / Answer scene |
| Open Knowledge | Current Knowledge 的 canonical reading entry；deep link 除外 |
| Continue Knowledge | 最近安全 Anchor / scroll / local outline state |
| Open from Search / citation / relation | 打开明确 target，并带 Return Envelope |

Group entry 的主体动作永远是 Open。Continue 只有在真实安全现场存在时才出现，不能让“上次打开位置”悄悄取代 Overview 的产品责任。

## 3.6 Recovery 不进入普通 Library hierarchy

Recovery 处理：

- 尚未 commit 的 Edit Buffer；
- 应用异常退出后的 checkpoint；
- 同步冲突的本地修改；
- 未完成 import / source parse；
- 半完成 formation proposal；
- 无法安全重放的批量操作。

它遵循三个原则：

1. 在相关 owner 或启动时以一项高影响提示出现；
2. 先保护本地内容，再要求用户理解冲突；
3. 恢复、丢弃、另存为 Draft / Knowledge 是不同动作。

Recovery 不能成为 Library 中一个永久“待处理”栏目。

## 3.7 多窗口

- 每个窗口持有自己的 Navigation / Reading / Relation scene；
- Pin、Saved View、Saved Path 属于 Library，可被多个窗口读取；
- Resume 默认指向最近活动且满足 eligibility 的窗口；
- 关闭一个窗口不覆盖另一个窗口的 scene；
- 同一 Knowledge 在两个窗口修改时，History / conflict owner 处理内容一致性，Resume 不做合并；
- 新窗口从 Library 开始，不复制当前窗口的 deep state，除非用户明确`在新窗口打开`某个 target。

---

# 4. All Groups：稳定、穷尽、可解释

## 4.1 Canonical membership

All Groups 包含全部 Current Groups，并排除：

- archived Groups；
- deleted / tombstoned Groups；
- Saved Views；
- AI Candidate groups；
- import preview 中尚未 commit 的 groups；
- Topic、Knowledge、Source、Question 或 Saved Path。

Bare Group 也是 Current Group，必须立即出现。

## 4.2 Group entry 的内容合同

Calm level 的 Group entry 只需要：

1. Group name；
2. 一句用户可写的 Boundary / orientation；
3. 当 Boundary 尚未写时，显示诚实的 Bare state，不让 AI 伪造；
4. 必要的 archived / unavailable / local-only 等可操作状态；
5. Open；
6. 存在安全现场时的 Continue；
7. 多选或 context menu 中的 Pin、Rename、Archive 等次级动作。

Focused level 可以补充：

- 有限 Topic landmarks；
- 一个用户选择的 cover / marker；
- Current Group Relations 的少量、可读出口；
- 最近修改时间，前提是用户选择这种浏览方式；
- Saved View 命中原因。

默认 entry 不展示：

- “87% mature”；
- AI confidence；
- 未读数量；
- 待连接数量；
- Source 数、Note 数、token 数；
- 最近活动瀑布；
- 伪造的自动摘要；
- 装饰性 mini graph。

## 4.3 稳定排序

默认排序规则：

1. 若用户显式维护 manual order，则使用 manual order；
2. 否则按 locale-aware name order；
3. 同名时用稳定 ID 作不可见 tie-break；
4. 新 Group 在 manual order 中进入可解释位置，不把其余 Group 全部抖动；
5. 当前 sort 明确可见且可撤销。

可选排序：

- name；
- user order；
- recently opened；
- recently modified；
- created time；
- explicit property。

禁止默认：

- AI relevance；
- relation degree；
- usage frequency；
- source volume；
- inferred maturity；
- paid promotion / shared popularity。

## 4.4 Search、Filter 与 View

| 能力 | 作用 | 是否保存 | 是否改变 Catalog truth |
|---|---|---:|---:|
| Search | 找目标或内容位置 | Query history 可本地恢复，不自动成为知识 | 否 |
| Filter | 当前列表只显示符合条件者 | 默认不保存 | 否 |
| Sort | 改变当前展示顺序 | 可作为本地 preference | 否 |
| Saved View | 保存 refs、rule 或 snapshot | 显式保存 | 否 |
| Pin | 保存单个快捷入口 | 显式保存 | 否 |

Search 命中 Group 时 Open Group；命中 Knowledge / Anchor 时直接 Open target 并带 Return Envelope。Search 结果不能被伪装成“All Groups 只剩这些”。

## 4.5 Empty、G1、G10、G100、G1K

| 规模 | 同一骨架下的表现 |
|---|---|
| G0 | 直接写第一条 Knowledge 为主；建 Group、保存资料、Ask 可达 |
| G1 | 单一 Group 是清楚入口；All Groups 仍成立；零 Relation 合法 |
| G10 | 可扫描完整列表；Resume / Pins 克制；Network 可直接查看少量群关系 |
| G100 | Search、filters、stable sort、Views 成为必要工具；All Groups 仍可穷尽 |
| G1K | 分页 / virtualization 属于实现；默认先列出稳定目录，Network 必须先选择 scope |

规模增长不能触发：

- 自动 Top N 替代 All Groups；
- “更多”后隐藏无法到达的尾部；
- 用 mini graph 替代名称和 Boundary；
- 自动建立 Area / Folder / Workspace；
- AI 自动合并相似 Groups；
- 用活跃度决定首屏成员。

---

# 5. All Knowledge 与独立知识

## 5.1 All Knowledge 的角色

All Knowledge 是按稳定 Knowledge identity 浏览的次级 inventory，主要支持：

- 找到忘记放在哪个 Group 的 Knowledge；
- 检查一条 Knowledge 的所有 active Placements；
- 识别无 Placement 的独立知识；
- 在重构 Group 前进行对象级选择；
- 处理 duplicate candidate、archive、export 或 restore；
- Search / index partial 时按可用 canonical metadata 找回。

它不是：

- 第三个顶层主视图；
- Home feed；
- 全部正文同时展开；
- 原子卡片墙；
- Topic hierarchy 的替代品；
- 默认 Ask scope；
- 维护 Inbox。

## 5.2 Knowledge inventory entry

entry 最小信息：

- Knowledge title；
- 一段由 Current content tree 提取、可追溯的 orientation；
- active Placements 的数量和主要路径；
- independent / placed / archived-owner / unavailable 等真实状态；
- Current revision 的最近修改时间，只在相应 sort / detail 中出现；
- Open target。

同一 Knowledge 多 Placement 只出现一个 identity entry，不复制成多条知识；用户可以展开 placements，选择某个上下文打开。

## 5.3 独立知识的推导

```text
Independent Knowledge
= Current Knowledge
  AND active Placement count = 0
```

以下情况不会让 Knowledge 成为独立知识：

- 所在 Group 被 archive，但 Placement 仍存在；
- 临时 filter 隐藏其 Group；
- Saved View 不包含它；
- relation target 不可用；
- Source attachment 被移除；
- Ask 本次没有使用它。

以下情况会让它成为独立知识：

- 从 Library 直接写作且未选 Placement；
- 用户移除最后一个 active Placement；
- Group 删除流程明确结束了相关 Placements，但保留 Knowledge；
- import 明确把内容 commit 为 Knowledge 而未建立 Placement。

## 5.4 独立不等于未完成

产品不对独立知识显示：

- 红色数量；
- “待归档”；
- overdue；
- 清空目标；
- AI 强制分类；
- 默认每日提醒。

用户可以长期保留独立知识。只有当用户主动整理或当前任务明确需要 Group context 时，系统才提供 placement suggestions；建议保持 Candidate，拒绝后抑制。

## 5.5 独立知识的规模

- 1–10 条：Groups view 可显示紧凑的可继续列表；
- 10–100 条：Groups view 只显示少量最近明确打开项与`查看全部独立知识`；
- 100+：进入 All Knowledge 的 filtered inventory，使用 Search / filters / explicit batch placement；
- 10K：虚拟化、分页、local index 属实现责任；不引入 Inbox 或自动分类产品模式。

这些阈值是初始设计假设，需要真实 Library 验证；语义不依赖具体数字。

---

# 6. 六种“回去”机制必须分权

## 6.1 对照表

| 机制 | 用户意图 | 形成方式 | 生命周期 | 是否改变知识 | 默认是否跨设备 |
|---|---|---|---|---:|---:|
| Resume | 继续最近安全现场 | 系统从 committed scene 计算 | 被新安全 scene 替换或用户清除 | 否 | 否 |
| Pin | 固定一个常用入口 | 用户显式 Pin | 直到 Unpin / target unavailable | 否 | 可选 |
| Recent | 看我成功打开过什么 | Open event | 有限本地历史，可清除 | 否 | 默认否 |
| Saved View | 保存一种 Group 浏览切片 | 用户显式保存 refs / rule / snapshot | 直到 archive / delete | 否 | 是 |
| Saved Path | 保存一条探索顺序 | 用户显式策展 | 直到 edit / archive / delete | 否 | 是 |
| Recovery | 找回未提交或冲突内容 | checkpoint / failure | 解决后退出 | 可能在用户确认后形成 Current | 本地优先 |

## 6.2 Pin

可 Pin 的 target：

- Group；
- Knowledge；
- Saved View；
- Saved Path；
- 明确允许的 stable Anchor deep link。

不直接 Pin：

- hover / Peek state；
- unsaved filter；
- AI Candidate；
- destructive preview；
- query runtime selection；
- graph coordinates；
- recovery buffer。

Pin 顺序由用户控制。系统不能用“常用”自动 Pin，也不能把 Pin 当作 Ask 的优先依据。

## 6.3 Recent

Recent 只记录成功导航到可阅读 target 的 Open event：

- Open Group；
- Open Topic；
- Open Knowledge / Anchor；
- Open Answer Snapshot / Saved Path / Source，若其是明确 target。

不记录：

- hover；
- Peek；
- Graph selection 未 Open；
- Search result 只被键盘经过；
- AI runtime 使用；
- background sync / index；
- 别的窗口修改；
- relation edge 高亮。

同一 target 重复打开更新其 opened_at，不制造无限重复；不同 Placement context 可以保留最近一次 origin，以支持正确重返。

## 6.4 Recently modified

最近修改依据 Current commit，不依据 buffer keystroke、AI proposal、source parse 或 index update。它在需要时作为 sort / filter，不能与 Recent opened 混为“活动”。

## 6.5 Saved Path

Saved Path 保存：

- 有序 steps；
- 每个 step 的 stable target；
- 必要的 relation / explanation；
- 可选的 path title、orientation 和起点；
- target relocated / historical / unavailable 的解析状态。

它不保存：

- 每次滚动位置；
- 所有浏览 Trail；
- 临时 graph layout；
- 自动推断的中间 Relation；
- Current truth 的复制品。

## 6.6 Target unavailable

快捷入口失效时，产品保留入口语义并解释状态：

| 状态 | 合法动作 |
|---|---|
| Relocated | 打开新位置；查看原路径 |
| Historical | 打开历史版本；转到 Current |
| Archived | 打开 archived context；Restore（若允许） |
| Deleted / tombstone | 查看影响与可恢复性；移除快捷入口 |
| Local file missing | 定位文件 / 查看已保存 representation |
| Ambiguous anchor | 选择候选位置 / 从 owner 顶部打开 |
| Unavailable capability | 使用列表或 canonical metadata 降级 |

系统不能在 target 删除后静默把 Pin 指向“相似内容”。

---

# 7. Groups / Network 切换合同

## 7.1 同一 selection owner

两种视图共享：

- Current Group identity；
- Saved View scope；
- 明确的 Current / Archived boundary；
- 可映射的 property filters；
- user selection；
- Search / Ask / Add 全局动作。

Network 额外持有 presentation state、graph / list mode、zoom / layout 和 relation filters；这些是 Workspace projection，不写回 Group truth。

## 7.2 Groups → Network

- All Groups → R3 whole-current-groups scope；G100 / G1K 时先显示 scope summary + List，避免不可读全图；
- Saved View → 同一 View 的 Group refs / rule results；
- selected Group → 以该 Group 为 anchor，显示可解释的邻接关系；
- property filter → 只在其能解释为 Group set 时映射；
- text Search result → 不自动伪装为 Network truth，必须显式`在这些 Groups 中查看关系`。

## 7.3 Network → Groups

- selected Group 在 All Groups 或当前 View 中被定位并聚焦；
- relation-only filter 若无法映射成 catalog property，回到对应 Group set，并以短说明保留过滤来源；
- selected Relation 打开 Inspector 不改变 catalog membership；
- closing Network 恢复原 Groups view scroll、focus 和 filter；
- zero-relation scope 回到同一 Groups set，不回退到推荐 Groups。

## 7.4 零关系与失败

当有 Groups 但没有 Current Group Relations：

- Network 仍可选择；
- 显示真实 Groups 与“当前没有你已确认的群级关系”；
- 提供 Compare、Open Group 或回到 Groups；
- 不显示相似度虚线、AI 星云或随机布局来填空。

当 graph layout 失败：

- selection、scope 和 filters 不丢失；
- 自动使用同义 List Equivalent；
- Relation Inspector 与 Open / Back 仍可用；
- 恢复图只改变 presentation，不改变数据。

---

# 8. 首日、日常与长期循环

## 8.1 First use

```text
Open empty Library
→ Write first Knowledge
→ Current commit
→ Appears in Independent Knowledge
→ Return to Library
→ Reopen exact Knowledge
```

成立条件：

- 不要求先建 Group；
- 不要求 Source；
- 不要求 AI；
- 不要求选择模板或类型；
- Commit 后立即可在 canonical inventory 找回；
- 索引尚未完成也能按 metadata 打开；
- 之后建立 Placement 不复制 Knowledge。

## 8.2 First Group

```text
Library → Add Group → Name → Commit Bare Group
→ All Groups → Open → Bare Overview
→ Write boundary / root Knowledge when ready
```

Bare Group 不显示“0% complete”。建立 Group 不需要一次性决定 Topic hierarchy、Relations、Sources 或 AI instructions。

## 8.3 Daily return

```text
Open Library
→ See one Resume + stable Catalog
→ choose Continue OR choose Group Open
→ read / edit / ask / explore
→ return to Library with position preserved
```

产品不因为存在 Resume 就隐藏 Catalog，也不因为没有 Resume 就制造推荐内容。

## 8.4 Browse and rediscover

用户可能只记得：

- Group 范围；
- 一条 Knowledge 的词；
- 某个 Source；
- 最近打开过；
- 某条跨群路径；
- 内容大概没有归群。

对应入口：

| 记忆线索 | 入口 |
|---|---|
| Group / domain | All Groups / Saved View |
| title / phrase / claim | Search / All Knowledge |
| recently opened | Recent |
| curated route | Saved Path |
| unplaced | Independent Knowledge |
| relationship | Network / Pair |

这些入口可以重合，但不能合并成一个不透明“智能首页”。

## 8.5 Maintenance without a maintenance product

维护提示只能在以下情况主动出现：

- Current target 已失效，阻断 Resume / Pin / Path；
- Recovery 中有用户未提交内容；
- Source change 直接影响当前正在阅读的 Claim；
- export / restore / sync 出现数据完整性风险；
- 用户主动打开相关 utility。

Library 一次最多显示一项最高影响提示。相似 Group、独立知识过多、可能关系和旧来源默认不构成红点。

---

# 9. 状态、失败与诚实降级

## 9.1 Library-level states

| 状态 | 必须成立 | 禁止 |
|---|---|---|
| Empty | Direct writing + Add Group / Source / Ask 可达 | 伪造示例 Groups 冒充用户知识 |
| Loading projection | Canonical names / IDs 可逐步出现 | 全屏 spinner 阻断本地 Catalog |
| Index partial | Catalog / metadata browse；Search 标 coverage | “没有结果”冒充完整检索 |
| AI unavailable | Read / write / browse / Search metadata 可用 | 把 Library 变成错误页 |
| Offline | local Current truth 可打开和编辑 | 用“无法联网”阻断本地知识 |
| Graph unavailable | Groups Catalog + relation List 可用 | 隐藏 Network truth |
| Missing local source | Knowledge 仍可读；Source 说明 representation | 级联删除 citations / knowledge |
| Corrupt projection | rebuild projection；canonical truth 不删 | 清空数据库式修复 |
| Restore partial | 列出 restored / missing / degraded | 成功 toast 掩盖缺失 |
| Read-only volume | 浏览与 export 可用，写入讲真话 | 假保存 |

## 9.2 Catalog consistency

以下不一致必须被检测：

- Current Group 不在 All Groups；
- archived Group 混入 Current；
- 同一 Group 因多个 Saved Views 被复制成多个 canonical identities；
- Independent Knowledge 仍有 active Placement；
- All Knowledge 同一 ID 出现多条；
- Pin 自动改变 Ask scope；
- Recent 因 hover 写入；
- Resume 指向未提交 / destructive scene；
- graph filter 静默改变 Group membership；
- restore 后快捷入口指向错误相似对象。

修复先重建 projection，再检查 canonical truth；不能通过删除“异常对象”让表面看起来一致。

## 9.3 Offline 与 index partial

最低离线责任：

- 打开 Library；
- 浏览 All Groups / All Knowledge canonical metadata；
- 打开已在本地的 Current Knowledge；
- 直接写作并 local commit；
- 使用已有 Pins / Saved Views / Saved Paths；
- 记录 Recent / Resume 本地状态；
- export 当前可用的 Knowledge Package。

需要派生索引的 Search、Ask、suggestions 和 graph layout 分别说明可用范围，不把整个产品标为不可用。

## 9.4 Archived、Trash 与删除

- Archive 是可逆生命周期，不是移除 Placement；
- Archived utility 可 Search / browse，但不与 All Groups 混排；
- Group deletion 先显示 Topics、Placements、Relations、Pins、Paths 和 deep links 的影响；
- 删除快捷入口不删除 target；
- 删除 Saved View 不删除成员 Groups；
- 清除 Recent 不删除 History；
- 清除 Resume 不丢弃 Recovery；
- permanent delete 后保留必要 tombstone / redirect 以解释旧引用。

---

# 10. 响应式、键盘与辅助技术

## 10.1 Desktop wide

- Library 主体保持 Catalog 可扫描；
- supporting detail 可以在 Inspector / secondary region 展开；
- Groups / Network 切换不改变全局动作位置；
- Resume 不占据类似营销 Hero 的大面积；
- Network 可以使用空间图，但 List Equivalent 同时可达。

## 10.2 Compact / tablet

- Resume、Pins、All Groups 仍按同一优先级；
- filter / sort 进入可返回的 sheet，不丢当前 scroll；
- Group detail 可成为临时 surface，关闭回到原 entry；
- Network 默认可使用 List + focused graph，而不是缩小桌面全图。

## 10.3 Mobile

- 默认从 Groups Catalog 开始；
- Resume 是一个明确动作，不自动深开；
- Group entry 主动作与 overflow actions 分开；
- All Knowledge / Recent / Views 通过 supporting navigation 到达；
- Network 可以完全使用关系 List、Pair 和 Inspector；
- Back 恢复 list position、filter、selection 和 focus target。

## 10.4 Keyboard

键盘必须能完成：

1. 在 Groups / Network 切换；
2. 进入 Resume；
3. 遍历 Pins 与 All Groups；
4. Search / Filter / Sort；
5. Open / Continue 区分；
6. Pin / Unpin；
7. 打开 Group / Knowledge / Path；
8. 从 Network List 检查 Relation；
9. Back 精确返回；
10. 跳到 All Groups，绕过所有 lenses。

## 10.5 Screen reader

- 报读 Library 当前 view、scope 与结果数量；
- Resume 读出 target、context 和恢复精度；
- Group entry 的名称、Boundary 与状态使用结构语义，不依赖位置 / 颜色；
- Pins、Recent、All Groups 是清楚的 landmarks；
- Network List 读出 endpoints、statement、direction 和 standing；
- sort / filter 变化通过状态信息通知，不重新把整页当新页面朗读；
- unavailable target 说明原因与合法动作。

## 10.6 Motion

Groups ↔ Network 的形态转换可以帮助建立同一对象连续性，但：

- reduced motion 下使用无位移动画的状态切换；
- 不依赖 Group entry 飞入图中来证明 identity；
- layout 稳定，不因 background index 自动漂移；
- motion 不写 Recent、不改变 selection owner、不触发 Open。

---

# 11. 本地所有权、Export 与 Restore

## 11.1 长期知识包

Knowledge Package 必须足以恢复：

- Groups、Knowledge、Relations、Sources 的 canonical identities；
- Topic hierarchy 与 Placements；
- Current / History / redirects / tombstones；
- Anchors 与 source bindings；
- Saved Views 与 Saved Paths；
- 用户显式 pins（可作为可选层）；
- machine-readable manifest 与人可读内容。

## 11.2 Workspace state package

可选、device-local 或按用户选择同步：

- Resume；
- Recent；
- window layouts；
- current filters / sorts；
- graph layout；
- drafts / recovery checkpoints（需要更高保护级别）。

恢复知识包不要求恢复这些状态才算成功。恢复 Workspace state 也不能覆盖已恢复的 canonical truth。

## 11.3 不作为恢复真相

- embeddings；
- Search index；
- AI suggestions；
- generated summaries 未形成 Current；
- graph coordinates；
- usage ranking；
- hover / Peek state；
- runtime query route；
- cache。

它们可以重建，重建失败不应改变目录 membership。

---

# 12. 与相邻现行合同的责任边界

| 领域 | Owner | 本合同只负责 |
|---|---|---|
| Group / Topic / Placement / Catalog structure | `知识群层级、目录规模与结构演化合同` | Library 入口、镜头优先级和日常返回 |
| Overview / Knowledge / Anchor / direct edit / History | `Overview、连续阅读与知识正文合同` | Open / Continue / Resume 怎样进入与返回 |
| Group Relation / Network / Pair / Relation Scene | `关系、群级网络与探索连续性合同` | Groups / Network 切换与 Library-level scope continuity |
| Search / Ask / Answer / Query recovery | `AI查询、知识探索与返回连续性合同` | Search 入口和 Query recovery 不冒充 Resume / Recent |
| Add / Source / Formation / import recovery | `知识进入、来源保存与知识形成合同` | Empty Library 入口和 formation completion 返回 Library |

## 12.1 结构合同拥有的内容

- Group membership；
- Topic hierarchy；
- Placement；
- Manual / Rule / Snapshot Saved View 的正式语义；
- Catalog scale 与结构演化。

## 12.2 本合同新增的内容

- Library cold start / new window / daily return；
- All Groups 的默认注意力与 entry 信息责任；
- All Knowledge 次级 inventory；
- Resume / Pin / Recent / Saved View / Saved Path / Recovery 分权；
- ordinary Open 与 Continue；
- Library-level degradation；
- Screen 1 的完整产品证明责任。

## 12.3 不新增 Primary Resource

Resume、Recent、Pin 和 Workspace state 都是 supporting identities / records；All Knowledge 与独立知识是 views。本文不新增第五种 canonical truth，也不把 Library 拆成新的 Places。

---

# 13. 真实内容压力场景

## LX-01 · Empty Library 直接写作

Fixture C 的用户首次打开空 Library，直接写下 K-W1。Commit 后即使 Search index 尚未完成，Groups view 的独立知识入口和 All Knowledge 都能再次打开同一 Knowledge identity。

## LX-02 · Bare Group 与普通 Open

用户创建只有名称的 G-WRITE，回到 All Groups 后打开它。普通 Open 进入 Bare Overview，不恢复上一次停在创建表单的位置，也不显示“0% complete”。

## LX-03 · 有安全 Resume，但用户选择重新开始

用户昨天停在 G-MEM / K-SPACING 的深层 Anchor。今日打开应用先进入 Library，看见一条 Resume 和完整 Catalog。选择 Group 主体后从 Current Overview 打开；选择 Resume 才精确回到 Anchor。

## LX-04 · Anchor relocated

K-SPACING 的 section 被移动，旧 Anchor 有唯一 redirect。Resume 文案说明原位置已移动，打开 relocated Anchor，并允许查看原 revision；不把近似段落冒充 exact。

## LX-05 · Recovery 与 Resume 同时存在

用户有一份未提交的 K-W1 buffer，同时上次安全阅读现场是 K-SPACING。Library 只显示一项高影响 Recovery 提示，Resume 保持可达但不覆盖未提交内容；解决 Recovery 不自动跳入 Resume。

## LX-06 · Pin、Recent 与修改时间不同

用户 Pin 了 G-QUAL；今天打开 G-MEM；后台 source change 影响 G-STUDY。Pins、Recent opened 与 recently modified 分别反映三件事，不合并成“最重要的三个 Group”。

## LX-07 · 同一 Knowledge 多 Placement

Fixture B 的一条方法 Knowledge 同时位于 G-MEM 和 G-STUDY。All Knowledge 只出现一次，展开显示两个 Placements；从某个 path 打开后 Return Envelope 回到所选上下文。

## LX-08 · 最后一个 Placement 被移除

用户显式移除 K-W1 的最后一个 active Placement。Knowledge 不删除，进入独立知识；只 archive 其 Group 时则不会发生这一变化。

## LX-09 · Saved View 切换 Network

用户在 Rule View“正在研究的群”中看到 12 个 Groups，切到 Network 后范围仍是这 12 个 Current Groups 及其 Current Group Relations。回到 Groups 后恢复原 list scroll 和 filter。

## LX-10 · 零群关系

Library 有三个 Groups，没有 Current Group Relation。Network 保留三个 Group identities、诚实零关系说明和 List Equivalent，不生成 AI 相似虚线。

## LX-11 · G100 与 index partial

用户有 120 Groups。索引只覆盖 93 个时，All Groups 仍穷尽列出 120 个 canonical entries；Search 明确显示 coverage 93 / 120，不能把 27 个未索引项说成无结果。

## LX-12 · Pin target archived

用户 Pin 的 Group 被归档。Pin 显示 archived 状态，可打开归档上下文、Restore 或 Unpin；不能静默指向同名新 Group。

## LX-13 · 新窗口与多场景

窗口 A 正在 Answer Claim，窗口 B 正在 Relation Pair。用户打开窗口 C 时进入 Library。只有最近活动且安全的 scene 形成一条 Resume；A / B 的独立 scene 不互相覆盖。

## LX-14 · Clean restore

在新设备恢复 Knowledge Package 后，All Groups、All Knowledge、Placements、Views、Paths 和 Anchors 成立。Resume / Recent 没有恢复也不算知识丢失；索引重建前仍可按 canonical metadata 浏览。

---

# 14. 专项验收合同

| ID | Canonical AC | 验收条件 |
|---|---|---|
| LEC-01 | AC-01 | 冷启动和新窗口先进入 Stable Library，不自动进入聊天、全图或深层正文 |
| LEC-02 | AC-01 / 03 | Empty Library 可直接写 Current Knowledge，也可建 Bare Group；二者 commit 后可再次打开 |
| LEC-03 | AC-02 | Groups / Network 共享 Group identities；切换不增删对象 |
| LEC-04 | AC-02 / 15 | 零 Current Group Relation 时 Network 仍存在且不制造装饰边 |
| LEC-05 | AC-01 / 03 | All Groups 包含所有 Current / Bare Groups，排除 archived / preview / View |
| LEC-06 | AC-01 / 08 | All Knowledge 同一 Knowledge 只出现一次，可展开多个 Placements |
| LEC-07 | AC-08 | Independent Knowledge 严格等于 Current 且 active Placement count = 0 |
| LEC-08 | AC-01 | Resume 最多一条，不能替代 All Groups |
| LEC-09 | AC-10 / 17 | Resume eligibility 检查 target、revision、placement、anchor 与安全状态 |
| LEC-10 | AC-10 / 17 | 无法精确恢复时逐级降级并讲真话，不创建近似 target |
| LEC-11 | AC-05 / 06 | 普通 Open Group 进入 Current Overview；Continue 才恢复深层 scene |
| LEC-12 | AC-09 / 29 | Recovery 与 Resume 分权，清除 Resume 不丢 Recovery buffer |
| LEC-13 | AC-01 | Pin 只能由用户显式创建，不影响 Ask / Search / Overview / Network 排名 |
| LEC-14 | AC-01 | Recent 只由成功 Open 写入；hover / Peek / AI use / background update 不写入 |
| LEC-15 | AC-01 | recently opened 与 recently modified 可独立排序且标签明确 |
| LEC-16 | AC-01 / 31 | Unpin、clear Recent、clear Resume、delete View 对 canonical knowledge 零副作用 |
| LEC-17 | AC-17 / 23 | Saved Path 与 Resume / Recent / Relation truth 分权，target 状态可解释 |
| LEC-18 | AC-01 / 02 | Saved View 不拥有 Group、不改变 membership、不形成第二棵目录树 |
| LEC-19 | AC-01 / 18 | Search direct target 与 list Filter 分权；临时 filter 不自动保存 |
| LEC-20 | AC-02 / 16 | Groups ↔ Network 保留可映射 scope / selection / filters；不可映射条件明确放下 |
| LEC-21 | AC-01 / 32 | G1、G10、G100、G1K 使用同一 Library 骨架；All Groups 始终可穷尽 |
| LEC-22 | AC-29 / 30 | Offline / AI unavailable / index partial 时可浏览 canonical Catalog 和本地 Current |
| LEC-23 | AC-16 / 32 | Graph failed 时 List Equivalent 维持 selection、scope、Open 和 Back |
| LEC-24 | AC-29 / 31 | Archive Group 不结束 Placements；archive / delete / shortcut removal 后果分开 |
| LEC-25 | AC-30 / 31 | Export / clean restore 后 All Groups、All Knowledge、Placements、Views、Paths 与 Anchors 可解析 |
| LEC-26 | AC-30 | Resume / Recent / graph layout 缺失不算 canonical restore failure |
| LEC-27 | AC-32 | Mobile、keyboard、screen reader 可绕过 lenses 到 All Groups，完成 Open / Continue / Back |
| LEC-28 | AC-01 / 29 | Library 同时最多一项高影响维护提示，不出现 Review feed、待整理红点或 AI 推荐瀑布 |

---

# 15. 外部产品模式与本产品推论

## 15.1 Apple：状态恢复有价值，但恢复粒度必须服从产品权力

[Apple Human Interface Guidelines：Launching](https://developer.apple.com/design/human-interface-guidelines/launching)强调启动连续性，并建议恢复窗口、滚动位置等细节。

**产品推论：**精确 scene restoration 值得保留，但本产品把“自动恢复工作现场”和“进入稳定知识目录”分开。窗口与 Library preference 可以自动恢复；深层内容通过一条显式、安全 Resume 恢复。这是基于个人知识库可控性作出的产品选择，不是 Apple 指南直接规定的唯一答案。

## 15.2 Obsidian：Recent、Workspace 与 Bookmark 是不同责任

[Obsidian Quick Switcher](https://obsidian.md/help/plugins/quick-switcher)在空查询时可以显示最近笔记，并在大型 vault 使用不同搜索策略；[Workspaces](https://obsidian.md/help/Plugins/Workspaces)保存 tabs、files 和 sidebars 的布局；[Bookmarks](https://obsidian.md/help/Plugins/Bookmarks)可固定文件、文件夹、搜索、图、heading、block 或 link。

**产品推论：**Recent、Workspace scene 与 Pin / bookmark 不是一个概念。本产品进一步明确：三者都不改变 Knowledge truth，Resume 只取一个安全 scene，Recent 只记录 Open，Pin 只来自用户显式决定。

## 15.3 Zotero：完整 Library、Collections 与 Saved Searches 可以分权

[Zotero Collections and Tags](https://www.zotero.org/support/collections_and_tags)说明 Library root 可以显示全部 items，同一 item 可出现在多个 collections 而不复制，删除 collection 不必删除 items；[Saved Searches](https://www.zotero.org/support/searching)保存条件并随 Library 变化更新。

**产品推论：**Canonical inventory、结构性 placement 与动态 lens 应分开。本产品据此坚持 All Groups / All Knowledge 可穷尽，Placement 不复制 Knowledge，Saved View 不拥有成员。

## 15.4 Notion：Recents、Favorites 与完整 Library 可以共存

[Notion sidebar navigation](https://www.notion.com/help/navigate-with-the-sidebar)和[Manage your Library](https://www.notion.com/help/manage-your-library)展示了 Recents、Favorites、Search、Filters 与完整内容浏览可以共存。

**产品推论：**快捷入口不必替代完整目录。但本产品不复制 Notion 的 Home / teamspace / page 多中心导航；个人 Knowledge Library 仍是唯一主地点，Groups / Network 是同一真相的两个视图。

## 15.5 研究共同支持什么

外部模式共同支持以下一般规律：

1. 完整 inventory 与快捷入口可以分开；
2. 同一内容可被多个组织入口引用而不复制；
3. saved query / view 应保存规则或 refs，而不是拥有内容；
4. workspace restoration、recent history 和 bookmarks 有不同生命周期；
5. 大规模下需要 Search、filters 和稳定列表，不能只依赖空间图；
6. 删除组织入口不应默认删除内容。

## 15.6 研究没有证明什么

这些产品没有证明：

- Resume 必须自动打开；
- Library 必须使用卡片、侧栏或表格；
- Recent 必须位于首屏；
- All Knowledge 必须成为主导航；
- 任何使用频率排序都适合个人知识；
- 全局图适合替代 Catalog；
- Notion / Obsidian / Zotero 的对象模型应被直接复制；
- 本合同的 10 / 100 / 1K 阈值已经通过真实用户验证。

因此，外部研究只约束责任分离与失败边界；最终信息密度、排序偏好和视觉形态仍需用本产品真实 fixture 验证。

---

# 16. 对三份真实 Fixture 的闭环

## 16.1 Fixture A · 时效资格与流程知识

- G-QUAL、G-PROCESS 等 Groups 在 All Groups 可穷尽；
- cross-group exit 不自动形成 Library Network edge；
- Pin 的资格 Group 不因此成为 Ask 默认首选；
- recent opened 与 source-driven recently modified 分开；
- Group archived 后 placements、sources 和 history 保持解释性。

## 16.2 Fixture B · 概念学习与跨语境复用

- G-MEM、G-STUDY 等 Groups 可从 Overview 打开；
- K-SPACING 多 Placement 在 All Knowledge 只出现一个 identity；
- Saved View 切 Network 保持同一 Group set；
- Resume 可恢复 deep Anchor，但 ordinary Group Open 仍从 Overview；
- Saved Path 保存学习迁移顺序，不把所有经过的内容变成 Relation。

## 16.3 Fixture C · 基础可用性

- Empty Library 直接写 K-W1；
- K-W1 无 Placement 时进入独立知识；
- 建立 Bare G-WRITE 后立即进入 All Groups；
- Search index partial 不影响 canonical reopen；
- Offline local commit 与 clean restore 可完成；
- Resume / Recent 不恢复不构成知识丢失。

## 16.4 Synthetic scale · G100 / K10K

必须证明：

- 120 Groups 都能通过 All Groups 穷尽；
- sort / filter / View 不改变 canonical membership；
- All Knowledge 不展开 10K 篇全文；
- independent subset 在规模上降级为 filtered inventory；
- Network 需要明确 scope，不绘制不可读全局星图；
- index partial 说明 coverage，Catalog 仍成立；
- keyboard / screen reader 有同义路径。

---

# 17. 对 Ardot Screen 1 后续设计的证明要求

## 17.1 Screen 1 必须证明

1. 第一眼知道这是个人 Knowledge Library，而不是 AI dashboard；
2. Groups / Network 是同一地点的两种视图；
3. 有 Resume 时只是一条明确继续入口，不成为 Hero 故事；
4. Pins 不遮蔽 All Groups；
5. All Groups 是稳定、真实、可穷尽的主体；
6. Group entry 能表达名称、Boundary 与 Open，不用假成熟度；
7. Empty、G1、G10、G100 使用同一骨架；
8. 独立知识安静可达，不像待办 Inbox；
9. Recent、Saved Views、All Knowledge 是次级入口；
10. 零关系、graph failed 和 index partial 都有诚实状态；
11. ordinary Open 与 Continue 在交互后果上可辨；
12. Search、Ask、Add 是三个不同动作；
13. keyboard / mobile 可到达完整 Catalog；
14. 方向 3 的层级与阅读气质承担默认，方向 2 的星座关系只在 Network 中出现。

## 17.2 最少设计证据包

在制作高保真原型前，至少需要以下静态或低保真 Frames：

1. Empty Library；
2. G1 + one Independent Knowledge；
3. Daily Library with one Resume + Pins + All Groups；
4. G100 with Search / filter / stable sort；
5. All Knowledge with multi-Placement entry；
6. Independent Knowledge 100+ filtered inventory；
7. Groups → Network same scope；
8. zero Group Relations；
9. graph failed List Equivalent；
10. Resume exact / relocated / unavailable；
11. Recovery + Resume conflict；
12. archived Pin；
13. mobile Groups Catalog；
14. keyboard / screen reader structure annotation。

## 17.3 必须淘汰的 Screen 1 模式

- 星图占据 Hero，而真实 Groups 只是装饰标签；
- 自动生成“今日洞察”；
- 最近活动瀑布；
- 知识成熟度 / 健康分；
- 待整理红点；
- AI 推荐 Group；
- 只展示几个精选 Groups；
- All Groups 藏在二级“查看全部”；
- 把 Network 当作默认启动页；
- 用抽象统计替代真实名称与 Boundary；
- 把独立知识称为 Inbox；
- 打开应用后自动深开上次页面而无稳定 Library。

## 17.4 方向 3 + 2 在 Library 的准确比例

- Groups view 由方向 3 主导：有边界的层级、编辑出版感、稳定目录、清楚入口；
- Network view 由方向 2 主导：空间关系、群级星座、局部选择和暗色关系语法；
- 同一 Group identity 在两种视图保持连续；
- Library 默认不平均混合两种视觉，不把每个 entry 都做成 mini constellation；
- 切换是“同一知识换一种读法”，不是进入另一个产品。

---

# 18. 最终产品判断

这个产品每天最重要的动作不是“让 AI 给我推荐什么”，而是：

> 我打开自己的 Library，知道全部知识仍在那里；我可以从 Overview 重新理解一个知识群，也可以明确继续昨天的现场；当我需要联系时再进入 Network，当我只记得一句话时用 Search，当我需要综合时 Ask。

因此 Library 的产品品味来自克制：

- 完整目录先于推荐；
- 用户显式选择先于行为排名；
- 安全 Resume 先于自动深开；
- 普通 Open 先于 Resume 垄断；
- Group 边界先于活动统计；
- All Knowledge 兜底先于卡片墙；
- 零关系和空状态先于装饰丰富；
- 本地可浏览先于 AI 可用；
- 真实状态先于顺滑假象。

这使 Library 成为整个产品的重力中心：它不抢夺阅读、关系和 AI 的任务，却保证这些任务都从用户拥有的知识出发，并且能够准确回来。
