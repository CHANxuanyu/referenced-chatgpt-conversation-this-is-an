# AI-native 个人知识库

## 核心心智模型与连续探索合同 v1.0 — 一个知识库、一个纵向主干、一个按需关系层

> 文档性质：终局产品定义与视觉设计前置合同；不是 MVP、数据库表设计、页面清单或原型说明  
> 当前修订：2026-08-09  
> 用户已确认：产品本质是知识库；拥有一个个知识群、丰富层级、可见群间关系、AI 查询与知识网络探索；视觉偏好是方向 3 与方向 2 的结合，但应先定义产品  
> 本轮依据：2026-08-08 对 Ardot 当前七张设计图的复核、知识群形成路径研究、关系支撑表面研究，以及 canonical v4.0 和相邻合同的一致性审查  
> 2026-08-09 首日旅程覆写：空 Library 提供写、建群、加资料、迁入与提问五种合法起点；首个价值是 Current Knowledge 或 Source-only Asset 形成的可返回资产。Empty Group 合法但不冒充价值；Empty Bare Overview 使用一个首要动作 + 两个安静替代；Relation 不是首日门槛。完整规则见`AI-native-个人知识库-首日到日常核心旅程合同-v1.0.md`  
> 2026-08-09 Scale Invariance 覆写：F1 / F10 / F100 只是压力夹具，不是产品模式；All Groups 始终穷尽，Recent 不重排 Catalog；深层结构使用 focus + ancestor context；Over-budget Network 先显示 Scope Summary / List 并要求 anchor，不抽 Top N、不自动生成 Group regions。完整规则见`AI-native-个人知识库-规模化知识空间与长期可浏览性合同-v1.0.md`  
> 2026-08-09 Group State 覆写：Group 使用 Orientation、Change、Attention、Lifecycle 与 Boundary continuity 的正交配置；不再用 Seed / Forming / Established / Evolving / Dormant 五段生命周期。完整规则见`AI-native-个人知识库-知识群状态演化与身份连续性合同-v1.0.md`  
> 2026-08-10 Relation Lifecycle 覆写：AI / 来源抽取 / 聚合路径先形成 RelationCandidate；用户直接建立完整关系时形成 maintained Relation。Network 的 Current / Suggested / History 三层、证据绑定、挑战、修订、结束、替代、撤回、归档与端点迁移以`AI-native-个人知识库-关系陈述生命周期与网络可信性合同-v1.0.md`为准  
> 决策优先级：本文对“知识库核心入口、Place / Root 数量、层级与关系的呈现方式”具有领域覆写权；与旧合同冲突时，以本文和同步后的 canonical v4.0 为准

---

# 0. 最终决定

## 0.1 一句话产品答案

> **这是一个从知识群开始、沿主题与知识逐层深入、又能随时沿有意义关系横向探索，并可由 AI 在当前范围或全部知识中查询的本地优先个人知识库。**

它不是“AI 助手旁边放了一个知识库”，也不是“关系图旁边放了几篇文档”。

知识本身是产品；AI、关系图、来源管理、历史与同步都服务于知识的建立、理解、找回和演化。

## 0.2 产品只要求用户先理解五个词

| 日常词 | 用户真正拥有的东西 | 最简单的判断 | 不是什么 |
|---|---|---|---|
| **知识群** | 一个可长期进入的完整知识范围 | “我会不会把它作为一个整体回来理解？” | 文件夹、标签、数据库、一次搜索结果 |
| **主题** | 知识群内部的理解分支 | “它是不是帮助我把这个群分成更清楚的部分？” | 子知识群、对象类型、筛选器 |
| **知识** | 一篇可独立阅读、修改、引用和复用的活知识 | “它离开当前目录后还能不能被理解？” | 每个段落一张卡、原始文件、AI 摘要 |
| **关系** | 两条知识或两个知识群为什么相连的可读陈述 | “我能不能把这条线读成一句具体的话？” | 相似度、共现、目录父子、装饰连线 |
| **来源** | 用户读过或导入的材料，以及可回到原处的证据 | “这条理解从哪里来，能不能核验？” | 知识本身、只有 URL 的附件列表 |

Overview、目录、段落、证据、路径、历史、建议和回答可以出现，但不增加新的本体学习负担。

## 0.3 一个核心地点，不再有四个并列产品中心

产品只有一个主地点：**知识库**。

知识库有两种同义入口：

1. **知识群视图**：看见一个个知识群、边界、主要方向、最近进入与当前变化；
2. **知识网络视图**：看见知识群之间已经成立的重要关系，并从整体进入某个群。

它们观察的是同一套知识群，不是两个导航终点。切换视图不改变选择、筛选、最近路径或知识真相。

以下能力不再与知识库并列成一级产品地点：

- **Ask**：全局或当前范围的动作；
- **Search**：找回动作；
- **Add**：写知识、建主题、加来源的统一动作；
- **来源库**：支撑性资产管理入口；
- **历史、回收站、备份、设置**：完整性工具；
- **继续上次阅读**：知识库内的恢复入口，不是独立 Home。

## 0.4 一个连续纵向主干

用户进入知识世界时，永远沿同一条主干深入：

```text
知识库
  → 知识群概览
    → 主题概览 / 更深主题
      → 知识正文
        → 具体段落或主张
          → 来源中的证据位置
```

每一层都回答三个问题：

1. 我现在进入了什么；
2. 它在上一级中为什么重要；
3. 我接下来可以继续去哪里。

层级可以很深，但用户不需要管理“深度等级”。产品只显示当前位置、父级路径、少量兄弟、直接子项和当前最值得进入的内容。

## 0.5 一个按需出现的横向关系层

关系不是另一套信息架构，而是覆盖在当前阅读范围上的第二种看法：

- 在知识库：只看知识群及少量已成立的群关系；
- 在知识群：看群内主要知识关系、跨主题桥接与跨群出口；
- 在一篇知识：看与当前知识直接相关的正式关系；
- 在证据：只看当前主张的支撑、挑战和出处，不画整个网络。

阅读深度与关系半径相互独立。打开更深正文不自动放大关系半径；展开更多关系也不改变当前位置。

## 0.6 三个日常主动作

产品每天的主动作只有三个：

1. **浏览**：从知识群概览沿层级读到细节与证据；
2. **探索**：从当前位置沿正式关系进入相邻知识或另一个知识群；
3. **查询**：通过 Search 找回，或通过 Ask 综合，并回到用过的知识路径。

建设、导入、整理、纠错、版本、备份与恢复必须完整，但不得重写为用户每天要清空的管理队列。

## 0.7 产品从第一条内容开始就必须成立

空 Knowledge Library 不是 Chat 欢迎页或 Import Center。用户可以从五种真实意图进入：

1. 写第一条 Knowledge；
2. 建立一个 Knowledge Group；
3. 加入一份 Source；
4. 迁入已有内容；
5. 先问一个问题。

五条路径都汇入同一终局模型。首个产品价值是 **First Returnable Asset**：至少一条 Current Knowledge 或一份 Source-only Asset 已本地保存，拥有稳定 identity 与可解释位置，并能在离开后再次找到。前者是当前理解，后者是可继续形成或核验知识的材料，真值角色不混淆。Source 至少从 Sources 返回，选择具体范围时再建立 Attachment。Empty Group 合法但只证明范围已经建立；一次 Answer、Candidate、Preview 或尚未提交的 Buffer 都不能冒充可返回资产。

空 Library 以`写第一条知识`为视觉首要动作；建群与加资料保持易发现，迁入与提问作为明确文字入口。用户可以先写后归位，选择新建 / 现有 Group 或暂不归类。空库提问时产品保留问题、说明内部覆盖为空，并让用户加入资料、写下已有理解、保存 Question Knowledge 或按次允许外部研究；它不会静默使用外部资料。

首次使用没有强制教程、示例库、模板墙、完成环或 Relation 任务。第一次真正证明产品成立的是用户离开后能从稳定 Library 回到同一资产，并理解普通 Group open 与显式`继续`的不同后果。

## 0.8 从 1 到 100 个知识群仍是同一个产品

数量增长不能改变产品语义：

- F1 / F10 / F100 仍进入同一个 Knowledge Library；
- All Groups 始终包含全部 active / dormant Groups，默认使用稳定、语言感知的标题顺序；
- Resume 最多一个，Pins 是用户快捷入口，Recent 是次级 View；三者不重排 Catalog；
- Group Overview 仍是范围导读，更多内容由 Topic / Subtopic、Structure、Search 与按需列表吸收；
- Topic 越深，越突出当前 focus path，同时保留 ancestor landmarks；
- All Knowledge 按 identity 去重，不把 Placements、Anchors 或 chunks 变成重复对象；
- Network Scope 可读时显示全部；超过预算时进入 Anchor Required，先让用户选择 Group、Facet、Saved View、Search result 或 Path，再展开少量 accepted neighbours；
- 自动 cluster 只是可清除 overlay，不创建 Group region、Boundary、Relation 或 Catalog section；
- 全库 Ask 以 Groups 作为 coverage units，不从部分 chunks 冒充整个知识库结论。

规模只增加 jump、filter、progressive loading、virtualization 与 focus，不创建 Search-first 首页、AI 推荐 Feed、管理 Dashboard 或另一套“大型知识库模式”。

---

# 1. 为什么必须做这次结构修订

## 1.1 用户意图已经比旧架构更清楚

用户最新确认的不是 Cognitive OS、项目恢复工作台、自动捕获系统或 AI 聊天产品，而是：

- 本质是个人知识库；
- 顶层是一个个知识群；
- 群与群之间可能有可见关系；
- 群内有丰富层级；
- 知识可以从 Overview 逐渐深入到细节；
- 可以 AI 查询；
- 可以在网络中探索；
- 视觉可以结合温暖阅读面与深色星图，但产品先于原型。

这组意图足以推翻为了“功能完整”而形成的多 Place、多 Root、多工作区架构。

## 1.2 当前 Ardot 七张图的共同问题

当前设计已经有独特气质，但仍以功能页面而非产品心智模型组织：

| 现有画面 | 已表达 | 没有证明 |
|---|---|---|
| 知识主页 | 温暖纸张、Ask、星图与两个群 | 知识库如何成为默认入口；群列表与群网络如何同义；如何继续上次深层位置 |
| 双镜工作区 | 阅读与关系并置 | 用户在哪里；Group / Topic / Knowledge 如何连续；关系如何选择、检查与返回 |
| IA 概念星图 | 对象类别、Ask / Search / Explore、L0–L5 | 真实产品界面；真实节点类型；可读关系；每次进入发生什么 |
| 采集流 | 链接、文件、剪藏、AI 抽取 | 直接写作；Source-only 成功；Proposal 与当前知识边界；零卡片成功 |
| 回答页 | 带引用的回答 | 请求范围、实际范围、用过知识、未知与冲突；回答如何回到原知识 |
| 概览编辑器 | 人写正文、AI 右侧建议 | Overview 与 Knowledge 的边界；直接编辑如何成为当前知识；结构投影如何更新 |
| 来源与存储 | 连接器与存储选项 | Source Reader、Evidence、版本、失败、恢复；为什么这是支撑层而不是核心产品页 |

它们不是“还差很多张图”这么简单；它们缺少一条所有画面共同遵守的产品骨架。

## 1.3 旧文档的复杂度漂移

旧定义把完整性写成了：

- 四个稳定 Places；
- 每个 Group 四个 Roots；
- Reading Path、Context Rail、Answer Workspace、Decision Workspace、Sources Registry 等多个现场；
- L0–L5 同时承载范围、内容深度和图谱缩放。

这些能力大多合理，但它们被过早写成并列地点，造成三个后果：

1. 用户要先学产品架构，才能读自己的知识；
2. 同一个 Group 被切成概览、目录、关系、来源四个后台栏目，破坏连续理解；
3. 视觉稿自然会变成“每种功能一张页面”，而不是完整的知识库体验。

## 1.4 本次修订不是删功能

本次修订只收敛**表面权力**，不删掉长期能力：

- 全局网络仍存在，但成为知识库的网络视图；
- 群内完整目录仍存在，但融入当前范围的结构导航；
- 群内关系仍存在，但作为按需关系层；
- 来源库仍存在，但作为全局工具和上下文入口；
- 历史、Decision、备份、恢复仍存在，但由受影响对象进入；
- 所有 canonical identities、版本和可移植性合同继续成立。

完整性由状态与任务覆盖证明，不由一级导航数量证明。

---

# 2. 规范本体

## 2.1 Personal Knowledge Library

Personal Knowledge Library 是用户所有知识群、知识、关系和来源的完整边界。它拥有：

- 一个稳定 library identity；
- 一个默认知识群视图；
- 一个同义网络视图；
- 全局 Search / Ask / Add；
- 最近进入、固定入口与安全恢复现场；
- 来源、历史、备份与设置工具；
- 完整导出和恢复边界。

Library 不是数据库总表，也不直接把所有内部对象平铺给用户。

## 2.2 Knowledge Group

Knowledge Group 是 Library 中最高层的、可独立进入的知识范围。

一个 Group 至少有：

- 稳定身份与名称；
- 可逐渐澄清的边界；
- 一个 Group Overview；
- 零个或多个 Topic；
- 零个或多个直接放在 Group root 的 Knowledge；
- 零个或多个 Source Attachment；
- 零个或多个已成立的 Group Relation；
- 一条持续演化的历史。

空 Group 也成立。创建时只要求名称；边界句、目录和关系都可以后来形成。

## 2.3 Topic

Topic 是 Group 内的可打开理解分支。它拥有：

- 稳定 identity；
- 一个父 Group 或父 Topic；
- 有序的直接子 Topic；
- 指向 Knowledge 的 Placements；
- 可选但 canonical 的局部 Overview；
- 指向这里的 Source Attachments；
- rename / move / merge / split / transfer lineage。

Topic 不拥有独立 Group boundary、Group Relation、四套工作区或第二份 Knowledge 正文。

## 2.4 Knowledge

Knowledge 是一篇围绕一个主要理解任务持续演化的活知识。它可以很短，也可以很长，只要离开当前目录后仍可独立理解。

Knowledge 拥有：

- 稳定 identity；
- 当前正文版本与历史；
- 标题、摘要或 orientation；
- 连续正文；
- Section、Block、Anchor 与可定位 Claim；
- 零个或多个 Placements；
- 零个或多个正式 Relations；
- 零个或多个 Evidence Bindings；
- 属性、适用条件与认识状态。

Section 默认属于正文，不自动变成独立 Knowledge。只有需要独立关系、适用条件、证据、复用或修订时才提升。

## 2.5 Relation

Relation 是一条拥有稳定身份的知识陈述：

```text
起点 —[关系语义 / 方向 / 适用条件]→ 终点
```

它至少保存：

- 两个合法端点；
- canonical type 与用户可读表述；
- 方向与反向读法；
- why it matters；
- applicability；
- supporting / challenging evidence；
- standing、revision 与 history。

目录父子、Placement、Source Binding、Backlink、共同标签、相似度和本次 Ask route 都不是正式 Relation。

## 2.6 Source 与 Evidence

Source 是材料 identity；Source Revision 是一次不可变版本；Fragment 是可定位片段；Evidence Binding 说明一个片段如何支撑、限定或挑战具体 Knowledge、Claim、Relation 或 Overview。

Source 可以先被加入 Group 或 Topic，而不形成任何 Knowledge。零提取结果是合法成功，不应制造待清理的卡片。

---

# 3. 两条独立坐标轴

## 3.1 纵向阅读深度

| 深度 | 用户看到什么 | 核心问题 | 产品必须保留 |
|---|---|---|---|
| **D0 Library** | 知识群整体 | 我拥有哪些知识范围 | Group identity、边界、最近入口、群关系摘要 |
| **D1 Group** | 群概览 | 这个范围是什么，从哪里开始 | Group Overview、主要 Topics、代表 Knowledge、关键出口 |
| **D2 Topic** | 局部概览 | 当前分支是什么，下一层是什么 | DepthTrail、Topic Overview、子 Topic、直接与后代内容 |
| **D3 Knowledge** | 连续正文 | 这条知识完整说了什么 | stable identity、content revision、placements、relations |
| **D4 Anchor / Claim** | 具体段落或主张 | 当前细节的准确含义与条件是什么 | precise address、context window、applicability |
| **D5 Evidence** | 来源片段 | 这条理解如何被核验 | Source Revision、locator、support role、return path |

D0–D5 是设计和测试语言，不是必须显示给用户的标签。

## 3.2 横向关系半径

| 半径 | 默认节点 | 何时出现 | 禁止行为 |
|---|---|---|---|
| **R0 Reading** | 不显示图，只显示少量可读出口 | 默认阅读 | 不把无图误写成无关系 |
| **R1 Local** | 当前 Knowledge 与直接正式关系 | 用户打开“相关”或选择关系段落 | 不把 backlinks / 相似项混进正式边 |
| **R2 Group** | 当前 Group 中的主要知识与跨 Topic 桥接 | 用户切到关系镜头 | 不绘制全部 descendants 或检索命中 |
| **R3 Library** | Groups 与少量 Group Relations | Library 切到网络视图 | 不显示全部 Knowledge 节点汤 |

## 3.3 两轴组合规则

任何现场都表示为：

```text
当前阅读位置 + 当前关系半径
```

例如：

- `AI Agent 产品设计 / 可靠性 / 可逆行动` + R0：阅读 Topic Overview；
- 同一位置 + R1：查看“可逆行动”与“审计轨迹”的直接关系；
- 当前 Group + R2：理解四条主线怎样连接；
- Library + R3：查看“AI Agent 产品设计”与“认知科学”的群关系。

切换关系半径不得改变正文滚动、当前 Anchor、返回栈或 Ask scope。打开一个关系端点才创建新的阅读位置。

## 3.4 结构、关系与证据三种线不能共用语法

| 连接 | 用户读法 | 视觉责任 | 是否可争议 |
|---|---|---|---|
| Topic parent / Placement | 位于哪里 | 树、breadcrumb、缩进 | 通常是结构编辑，不是知识真假 |
| Knowledge Relation | 为什么相连 | 有标签、有方向的 edge / list statement | 是 |
| Evidence Binding | 为什么相信或质疑 | 引用标记、support role、source locator | 是 |
| Source Attachment | 材料被加入哪里 | 来源语境标签 | 不是知识结论 |
| Query Route | 这次回答用了什么 | 临时高亮路径 | 不写入 canonical graph |

---

# 4. Knowledge Group 的用户心智模型

## 4.1 最好用的比喻：一册会演化、会连接的知识书

一个 Group 更像一册长期演化的知识书：

- Overview 是封面后的导读；
- Topic 是章节与分支；
- Knowledge 是可独立阅读的文章；
- Relation 是文章或整册之间有意义的连接；
- Source / Evidence 是可以翻回去核验的材料。

这个比喻只解释阅读，不限制底层结构。同一 Knowledge 可以出现在多册“书”中，并共享同一正文。

## 4.2 何时建 Group，何时建 Topic

用三个问题判断：

1. 用户是否会把它作为一个整体重新进入？
2. 它是否有自己的边界和多个可继续增长的部分？
3. 它是否值得独立查询、概览或与其他整体建立关系？

多数为“是”时，适合作为 Group；否则先作为 Topic。大小不是判断依据。

例如：

| 名称 | 推荐 | 原因 |
|---|---|---|
| AI Agent 产品设计 | Group | 长期范围、多个主线、可独立查询和连接其他领域 |
| 可逆行动 | Topic | 当前是 Group 内一条理解分支 |
| 可逆行动的三条原则 | Knowledge | 可独立阅读、引用、核验 |
| 本周待读 | View | 按状态观察，不是稳定知识范围 |
| PDF | Source type | 材料形式，不是知识边界 |

## 4.3 Empty Bare Group 不制造建库仪式

用户输入名称后立即进入合法 Group，Orientation 解析为 Bare。首屏只显示真实内容：

- 群名称；
- 可选的一句“我想在这里理解什么”；
- 写第一条知识；
- 建第一个 Topic；
- 添加来源。

不自动生成三层假目录、模板数据库、空指标、长篇 AI 介绍或待办清单。

## 4.4 Group root content 是一等公民

用户可以直接在 Group 下写 Knowledge，不必先建 Topic。这适用于：

- 刚开始只有一条想法；
- 横跨多个 Topic 的基础知识；
- 尚不值得结构化的内容；
- 用户只想先写后整理。

Group root content 不叫“未归类”，不显示整理债务。只有没有任何 Placement 的 Knowledge 才是全局未归入知识群。

## 4.5 一个 Group 只有六种合法起点

创建 Group 的本质不是“AI 识别出一个聚类”，而是用户决定：**这批知识值得成为一个以后会作为整体重新进入、阅读、查询和维护的范围。** 产品允许六种起点，但最终都生成同一种 Group identity：

| 起点 | 创建时真正发生什么 | 明确不发生什么 |
|---|---|---|
| **空白 Group** | 输入名称即可建立合法 Bare Group | 不自动生成假目录、假概览或假关系 |
| **选择已有 Knowledge** | 为选中 identities 新建或迁移 Placements，并逐项说明`移动 / 两处保留 / 仅引用` | 不复制正文，不让同一 Knowledge 获得第二个 identity |
| **一组 Sources** | 创建 Group，并把材料作为 Source Attachments 放入当前范围 | 不把每份文件自动变成 Knowledge，不用摘要卡伪造成熟群 |
| **Topic 提升** | 新建 Group identity，迁移结构并在原位置保留 Gateway 与 lineage | 不在旧、新两处维护同步 Topic tree |
| **View / Search 结果** | 让用户选择当前结果中的 identities，并把这一次选择转为 Placements | 不把动态规则变成 Group membership；未来命中不会自动进入 |
| **导入层级** | 先预览外部层级到 Group / Topic / Source 的映射，再保存 identity 与 lineage | 不把每个文件夹都自动当成 Group，也不把路径当知识边界 |

无论从哪条路径开始，创建前都要让用户看懂：这个 Group 暂定理解什么、实际包含哪些 identities / Sources、哪些被排除、已有位置如何处理、初始 Topics 从何而来。空白 Group 只需名称；其余路径根据影响使用紧凑预览或完整 Change Set，而不是把每次创建都做成建库向导。

## 4.6 Group Candidate 不是 Group

AI 可以根据 Unplaced Knowledge、Sources、重复进入、跨群出口或 Topic 成长提出 **Group Candidate**，但 Candidate 只是一次可丢弃的形成方案：

```text
GroupCandidate
  trigger: selection | source_bundle | topic_promotion | view_conversion | import | ai_suggestion
  proposed_boundary
  included_identity_refs[]
  excluded_identity_refs[]
  placement_plan[]
  source_attachment_plan[]
  initial_topic_plan[]
  relation_impacts[]
  explanation
```

它不是 Primary Resource，不进入 Search、Library Network、Overview、Ask 默认范围或导出真相。只有用户接受后，才原子生成 Group、Placements / Attachments、初始结构和对应 Change Set；拒绝或丢弃不创建空壳 Group，也不在没有新证据时反复提示。

AI 主动建议 Candidate 至少需要同时满足：边界可独立说明、存在独立再次进入意图、已有多个连贯方向或稳定知识集合、纳入与排除理由可解释；并至少出现独立 Sources、跨群出口或重复使用中的一个增强信号。数量、文件夹名、标签共现、embedding 相似度或一次 Search 结果都不能单独成立。

---

# 5. Topic：丰富层级而不制造层级管理负担

## 5.1 Topic 必须可打开，不只是树上的一行

显式打开 Topic 时，用户进入同一 Group shell 中的 Topic Reading 顶部，先看到一个紧凑局部开场；它不是单独 Overview 页面，也不自动跳到第一篇 Knowledge：

- 当前 Topic 在父级中承担什么；
- 直接子 Topic 之间有什么区别；
- 哪些 Knowledge 最能建立初始理解；
- 当前有哪些跨分支或跨群出口；
- 哪些地方仍空白、争议或证据不足；
- 下一步可以进入哪里。

当内容很少时，一句说明加真实结构投影已经足够；不生成占位长文。

Topic opening 只有三种真实密度：Bare（title + path + 真实子项）、Compact（局部说明 + stable start / structure fallback + 3–5 个方向）、Editorial（Compact + 已接受的局部综合、条件 / 分歧与少量关系出口）。三者是同一个 Topic 的内容密度，不是模板、成熟度或三套页面。

Expand 只展开 children；Inspect 只预览；Open Topic 才进入 Topic Reading；点击 Knowledge row 直接打开 Knowledge；Search / Ask deep link 直接进入 exact object / Anchor。Topic Overview 不拦截明确的深层目标，Resume 也不把 exact scene 重置到 Topic 顶部。

每一级只解释相对父级的新信息：当前分支承担什么、与兄弟分支怎样不同、直接 children 怎样组成、从哪里开始。祖先只保留在 DepthTrail 与最多一句 context；Group Boundary、父 Overview、全部后代、全部 Relations 和 Sources 不逐层复制。

## 5.2 Topic 不是 Subgroup

Topic 不出现：

- 一套新的 Group header；
- 独立全局导航身份；
- Group Relations；
- 四个根级 tabs；
- 独立来源政策；
- 独立完整工作区壳层。

它只保留当前 Group 的壳层与完整 DepthTrail。

## 5.3 无限深度，有限可见

底层深度不设硬上限；每次只默认显示：

- 当前完整祖先路径；
- 当前节点；
- 少量相邻兄弟；
- 一级直接子 Topic；
- 少量代表 Knowledge；
- 一个“展开更多”入口。

系统不得以深度超过三层为由自动扁平化，也不得一次展开整棵树。

## 5.4 直接内容与后代内容必须可区分

Topic 中永远可以解释：

- **直接放在这里**：Knowledge 的 Placement 直接指向当前 Topic；
- **包含子主题**：Knowledge 只存在于后代 Topic；
- **多个路径**：同一 Knowledge 在多个后代拥有不同 Placement；
- **当前分支之外**：Relation 指向别处，但没有 Placement。

查询结果按 Knowledge identity 去重，但保留所有实际路径与局部说明。

---

# 6. Knowledge：连续正文，而不是卡片汤

## 6.1 一篇 Knowledge 围绕一个主要理解任务

判断标准不是长度，而是语义独立性：

- 标题表达一个主要问题或理解对象；
- 正文可以形成连续解释；
- 读者不必依赖当前目录名称才能明白它；
- 它可以被独立链接、查询、版本化和复用。

## 6.2 同一 Knowledge 可以多处出现

同一 Knowledge 可以同时被放在：

- `认知科学 / 记忆`，角色是理论基础；
- `AI Agent 产品设计 / 长期记忆`，角色是产品设计依据；
- 两个 Overview 的推荐入口；
- 一条 Saved Path。

所有位置共享正文、版本、Relation 和 Evidence；每个 Placement 只保存局部作用、顺序与进入说明。

修改正文影响全部位置；只改当前 Placement 的局部说明不会改写其他语境。

## 6.3 写作自然成为当前知识

用户直接写自己的 Knowledge 或 Editorial Overview 时：

- 输入中的半句话只在 Edit Buffer；
- 本机 Recovery Checkpoint 保护异常恢复；
- 安全提交后立即成为 Current Revision；
- 不要求“完成并采用”；
- AI 建议在接受前不是当前知识；
- 显式草稿、冲突和高影响身份变换仍需清楚边界。

---

# 7. Overview：每次深入前先获得方向

## 7.1 Overview 是范围导读，不是自动摘要

Overview 必须帮助用户理解一个范围，而不是复述所有内容。它由两类内容组成：

1. **Editorial truth**：用户维护的方向、判断、边界与阅读建议；
2. **Projection**：从真实 Topic、Knowledge、Relation、Source 与状态计算的结构信息。

Projection 可以刷新；Editorial prose 只能由用户直接修改或接受可检查建议。

## 7.2 Group Overview 与 Topic Overview 的分工

| | Group Overview | Topic Overview |
|---|---|---|
| 范围 | 整个知识群 | 当前分支 |
| 必须说明 | 边界、主要方向、代表知识、关键群出口 | 父级作用、子分支差异、代表知识、局部缺口 |
| 关系 | 少量重要群关系与跨群入口 | 后代 Knowledge 的相关关系投影 |
| 不做 | Activity dashboard、全量目录、全量来源 | 缩写整个 Group、复制 Group boundary |

Topic Overview 不是必须写满的“章节摘要”。Bare / Compact 以 direct children projection 为主；只有当前分支确实形成需要长期维护的整体解释时，才出现 Editorial synthesis。`包含子主题`是显式 rollup，不默认把所有后代知识铺进当前层。

## 7.3 Overview 不形成影子知识

如果 Overview 中一段内容需要：

- 独立 Relation；
- 独立 Evidence；
- 独立 Applicability；
- 跨 Group 复用；
- 独立修订与引用；

它应提升为 Knowledge，Overview 改为简短引入和链接。

---

# 8. Relation：一句可读的话，而不是一条漂亮的线

## 8.1 Knowledge Relation

合法例子：

- `可逆行动 — 是 — 可靠 Agent 的安全原则`；
- `最小权限 — 限制 — Agent 可执行动作范围`；
- `可观察轨迹 — 为 — 异常恢复提供依据`；
- `长期记忆策略 A — 与 — 策略 B 在跨会话一致性上冲突`。

不合法例子：

- “相关”；
- “相似 87%”；
- 两个对象被同一次 Ask 用到；
- 两个 Topic 同在一个 Group；
- 两篇 Knowledge 互相链接但没有明确语义。

## 8.2 Group Relation

只有两种关系可以出现在 Library Network：

1. **Direct Group Relation**：用户直接对两个整体做出判断；
2. **Accepted Aggregated Group Relation**：系统从多条稳定 Knowledge Relations 提出聚合解释，用户检查后接受。

共享一条 Knowledge、共同标签、相似 embedding、一次跨群路径或多次 Query 共现都不足以建立 Group Relation。

## 8.3 关系检查顺序

用户选择一条 Relation 后，Inspector 按固定顺序说明：

1. 一句话关系；
2. 方向与反向读法；
3. 为什么重要；
4. 适用于什么条件；
5. 由哪些知识或证据支撑；
6. 当前 standing 与更新时间；
7. 打开端点或沿关系继续。

## 8.4 图与列表必须语义等价

图不是唯一入口。Relation List 必须能完成：

- 读取关系陈述；
- 按类型、方向、Group、状态筛选；
- 选择关系；
- 打开两个端点；
- 查看证据；
- 沿关系继续探索。

---

# 9. 产品表面架构

## 9.1 Persistent Shell

桌面端永久壳层只需要：

- 当前 Library / Group / Topic / Knowledge 的路径；
- `知识库`主入口；
- Search；
- Ask；
- Add；
- 当前对象的按需动作；
- 来源库、历史、回收站、设置等 utility menu。

不显示多个同权知识中心；一个 Library 内保留 Groups / Network 两种观察，其他能力按需出现。

## 9.2 Scene A：Knowledge Library

默认打开 Knowledge Library。它保留同一个 selection state，并允许切换：

- **知识群**：阅读友好的群列表 / 分组 / 固定入口；
- **网络**：仅显示 Groups 与正式 Group Relations。

Library 顶部可以出现：

- 最近继续的一条安全路径；
- 固定的知识群；
- 最近进入；
- 少量真正影响理解的变化。

它不是营销首页、统计 Dashboard、通知中心或随机推荐 Feed。

## 9.3 Scene B：Scope Reading

打开 Group 或 Topic 后进入同一连续阅读场景：

- 顶部 DepthTrail；
- 当前 Overview；
- 左侧或内联的当前结构；
- 正文中的直接子 Topic、代表 Knowledge 与继续入口；
- 按需出现的关系 Companion；
- 当前范围 Ask。

Group 与 Topic 使用同一基础布局；Topic 只是更深 scope，不套一层新应用。

Topic 的 disclosure、Inspect 与 Open 不能共用一次点击后果。普通层级浏览可以只展开；显式 Open 才把 Topic 设为 Primary Reading Scope。Topic Reading 的局部开场与 direct children 在同一 scroll surface 中连续出现，用户不会经过“Overview → 目录”两次页面切换。

## 9.4 Scene C：Knowledge Reading

打开 Knowledge 后，正文拥有主权：

- 连续可读、可直接编辑；
- Outline 跟随当前 Section；
- DepthTrail 保留 Placement path；
- 关系、其他出现位置、Evidence 与 History 按需出现；
- 从 Search / Ask / Relation 深链进入时精确定位 Anchor，并保留返回来源。

## 9.5 Relation Companion

关系层使用四级 presentation，并且不绑定固定分屏：

1. **Quiet**：普通阅读的 resting state。正文只显示少量可读关系 Cue，不打开独立关系面；
2. **Peek**：用户明确选择一条 Relation / endpoint 后的局部 Inspector；不改变 Reading Target、ReturnStack 或 Trail；
3. **Companion**：用户明确执行`查看相关知识`后出现的唯一支撑面；Reading 仍是 Primary，默认只跟随 explicit Open；
4. **Explore**：用户明确执行`在地图中探索 / 打开知识网络`后，关系获得主画布；Reading 变为 Preview / Companion，并保留完整返回现场。

四级 presentation 与 R0–R3 正交：前者回答“关系占多大注意力”，后者回答“关系看到多远”。hover、focus、text cursor、scroll、AI suggestion 和 Answer rendering 都不能自动升级 presentation。普通打开和 deep Knowledge / Anchor entry 始终进入 Quiet；Relation deep link 默认进入可关闭 Peek，只有显式保存的 map / network scene 或 Resume 才恢复 Explore。

Companion 的默认是 `follow_open`，不是跟随 hover / Inspect。用户可以固定 target；固定后持续显示`已固定：X`，不能伪装成当前正文的关系。一个 Workspace 最多一个 Companion；打开第二个支撑对象时只能替换、进入 Peek / Rail、显式 Compare 或新窗口。

## 9.6 Supporting Utilities

来源库、Source Reader、History、Decision、Backup、Restore、Trash 与 Settings：

- 完整存在；
- 可由全局 utility menu 进入；
- 更常由当前 Knowledge、Relation、Group 或失败状态上下文进入；
- 不用空页面和 badge 争夺日常注意力。

---

# 10. 打开、继续与返回

## 10.1 冷启动

若用户有知识：打开上次稳定的 Library mode 与 catalog state，并在顶部提供最多一条可解释的 Resume；不自动跳回深层现场。catalog 保持页面主体，Resume 只是显式恢复入口。

若用户没有知识：打开 Empty Library，主动作是`创建知识群`，同时允许`写第一条知识`与`添加来源`。

| 状态 | 默认落点 | 恢复规则 |
|---|---|---|
| safe checkpoint | Stable Library catalog | 显示一条`继续`；点击后恢复 exact target / Anchor / scroll / companion |
| no checkpoint | Stable Library catalog | 不显示 Resume，不用 Recent 填充 |
| first use / empty | Empty Library | 三条真实起点，不生成示例 feed |
| new window | 独立 Stable Library state | 不复制现有 live reading scene，可显示同一条安全 Resume |
| needs repair | 最近安全 Reading fallback | 解释原现场变化，并提供恢复草稿 / 重新授权 |
| offline / AI unavailable | 本地 Stable Library | 目录和本地 Resume 可用，AI 提示消失 |

Pin、Recent、Saved Path 与 Resume 各守语义：Pin 是用户快捷方式，Recent 是访问记录，Saved Path 是长期理解顺序，Resume 只保存一个安全现场。它们不合并为统一“最近内容”，也不通过 AI 排名改变 Group catalog。

## 10.2 普通打开 Group

普通点击 Group：打开 canonical Group Overview，而不是恢复旧滚动位置。

明确点击`继续`：恢复 last-safe reading target、Anchor、scroll、Relation Companion 与 Ask branch。

二者不能由系统猜测成同一个动作。

## 10.3 深链进入

从 Search、Ask、Relation、Source 或外部链接进入深层对象时，产品同时恢复：

- 精确 target / Anchor；
- 完整 DepthTrail；
- 当前 Placement path；
- caller 与 Return Stack；
- 当前查询或关系的临时高亮，而不写入 canonical graph。

## 10.4 返回语义

| 动作 | 后果 |
|---|---|
| Back | 回到上一个真实场景与滚动 / 筛选 / 选择状态 |
| Up | 进入结构父级 Overview |
| Close Inspector | 回到触发关系或证据的正文现场 |
| Library | 回到知识库，不清除当前 Group workspace state |
| Continue | 恢复 last-safe scene，而非最新页面顶部 |

---

# 11. Search、Ask 与 Explore

## 11.1 Search 找回，Ask 综合，Explore 导航

| 意图 | 返回 | 是否生成新陈述 |
|---|---|---|
| Search | 已有 Group、Topic、Knowledge、Section、Source、Answer / Path | 否 |
| Ask | 带范围、用过知识、Claim Support 与 Coverage 的 Answer | 是，但默认不写回 |
| Explore | 当前 scope 的层级入口与正式关系 | 否 |

## 11.2 Ask 永远锚定当前位置

Ask composer 必须显示本次请求范围：

- 全部知识；
- 当前 Group；
- 当前 Topic；
- 当前 Knowledge；
- 用户明确选择的多个范围；
- 是否允许扩展到范围外 / 来源原文 / 外部知识。

系统还必须区分 Requested Context、Effective Context 与 Used Context。

## 11.3 Answer 回到知识网络

Answer 不是一个脱离知识库的聊天房间。它至少提供：

- 简明结论；
- Claim-level Support；
- Used Knowledge List 或真实 Knowledge Route；
- Coverage、Unknown、Conflict 与索引限制；
- 打开原 Knowledge / Anchor / Evidence；
- 沿用过的 Relation 继续；
- 明确的保存后果。

Save Answer、形成新 Knowledge、合入已有 Knowledge、提出 Relation、更新 Overview、保存 Path 与只保存 Source 是不同动作。

## 11.4 Explore 不依赖全局节点汤

用户可以从任意 Overview、Knowledge 或 Answer 开始探索：

- 先显示 3–7 个高价值出口；
- 每个出口说明关系或推荐理由；
- 用户主动扩展才增加半径；
- 退出后保留 Return Stack；
- 只有主动挑选的路线才成为 Saved Path。

---

# 12. 直接建设知识

## 12.1 Add 是一个动作，不是导入中心

Add 根据当前位置提供最多四个清楚结果：

- 写知识；
- 建主题；
- 添加来源；
- 建立关系。

在 Library 中还可创建 Group；在正文选区上可以形成 Knowledge、Evidence，或直接建立一条完整 Relation；AI 对选区发现的关系只形成 RelationCandidate。

## 12.2 从写作开始与从来源开始同等正式

```text
路径 A：创建 Group → 直接写 Knowledge → 安全提交为 Current
路径 B：添加 Source → 保存 Source → 可选解析 → 可选 Proposal → 用户检查后写入
```

用户不必先导入资料，也不必经过 AI Compiler 才能拥有知识。

## 12.3 AI 整理建议不制造管理债务

AI 可以建议：

- Topic 结构；
- Duplicate / Merge；
- Placement；
- Relation；
- Evidence Binding；
- Overview Diff。

建议默认按少量 Decision Bundle 呈现；不能把模型发现的每个候选变成待清空卡片。

---

# 13. 方向 3 + 2 的产品化解释

## 13.1 两种视觉气质承担不同责任

- **温暖、纸张、编辑气质**：承担 Overview、Knowledge、Topic、Ask Answer 与 Source Reader；重点是可读、可写、长期停留。
- **深色、星图、空间气质**：承担 Library Network、Group Relation、Local Relation Explore；重点是方向、选择和跨范围发现。

两者共享同一 identity、selection、DepthTrail 和操作语言。

## 13.2 不是固定左右分屏

默认 Reading 以正文为主；关系按需从 Quiet → Peek → Companion → Explore 增强。Quiet 是普通打开的确定 resting state，而不是“记住上次右栏是否开着”；只有显式`继续`可以恢复安全的 Companion / Explore。只有用户正在比较或沿网络探索时才让深色关系面获得更大权重。

这意味着视觉上的“3 + 2”不是永远同时看见两块，而是：方向 3 持续提供层级、正文和位置；方向 2 以可见 Cue 保持可发现，并随明确意图弹性长成 Inspector、Companion 或主关系场。宽屏可以并列，compact / mobile 顺序呈现，产品责任和返回语义不变。

## 13.3 星图必须来自真实数据

禁止：

- 生成式星云图作为可点击图谱背景；
- 随机星点冒充知识节点；
- 只用亮度表达重要性；
- 所有连接用同一种细线；
- 把 Group、Topic、Knowledge、Source 混在同一层。

允许：

- 受真实 Group / Relation 数据约束的空间布局；
- 稳定选中与键盘顺序；
- 有标签、有方向、可展开的关系；
- list equivalent；
- 把星空纹理作为非交互氛围层，但不承担信息。

---

# 14. 响应式与无障碍

## 14.1 Desktop wide

正文为主，可同时显示结构 rail 或 Relation Companion；最多一个主 Companion 和一个轻量 Inspector。

## 14.2 Compact / tablet

结构、正文和关系变成可切换的同一现场，不丢失 selection、DepthTrail 或 return state。

## 14.3 Mobile

默认单列：

```text
DepthTrail → Overview / Knowledge → 相关 → Evidence / Source
```

关系图可用专门场景打开；返回正文时恢复 Anchor。

## 14.4 无障碍等价

- 每张关系图必须有 Relation List；
- 颜色、位置、亮度都不能是唯一含义；
- Tree 支持方向键、展开、收起、选择与激活分离；
- 200% zoom 时正文、路径与主动作不被裁切；
- reduced motion 关闭图谱动画；
- screen reader 读出当前位置、关系陈述、方向、状态与返回目标。

---

# 15. 完整状态，不用页面数量冒充完整性

## 15.1 十二个设计证明家族

| ID | 证明家族 | 必须覆盖的正常态 | 必须覆盖的关键变体 |
|---|---|---|---|
| P01 | Empty / Bare Library | 新建第一个 Group | 无 AI、离线、只写知识、只加来源 |
| P02 | Mature Library | 群视图与 Network 同义切换 | 1 / 20 / 200 Groups、无群关系、大规模过滤 |
| P03 | Group Overview | 边界、主方向、代表知识、继续 | Bare / Structuring / Oriented / review_due / Paused / Archived composites |
| P04 | Topic Reading | 局部 Overview、子 Topic、直接与后代内容 | 深层、空 Topic、多个 Placement、Source-only |
| P05 | Knowledge Reading / Editing | 连续正文、Outline、Current commit | Buffer、Recovery、Draft、Proposal、Conflict、write fail |
| P06 | Local Relation | R1 inspect 与打开端点 | 多关系、反向读法、无证据、失效关系、list equivalent |
| P07 | Group / Library Network | R2 / R3、跨群出口与 Group Relation | 无关系、候选、聚合待确认、大图退化 |
| P08 | Search / Deep Link | 精确进入与返回 | 多 Placement、旧链接、缺失 target、索引不完整 |
| P09 | Scoped Ask / Answer | 范围、回答、Support、Route | Unknown、Conflict、Source-only、external、retry、follow-up |
| P10 | Source / Evidence | Source Reader、Fragment、Binding | Source-only、版本变化、权限失效、解析失败 |
| P11 | Structure Evolution | Topic move / merge / split、Group split / merge | impact preview、undo、redirect、跨群 transfer |
| P12 | Ownership / Recovery | export、backup、restore、history | corrupt cache、多设备冲突、partial restore、offline |

每个家族可以由多个状态、组件和流程板证明，不要求“一状态一张全屏稿”。

## 15.2 当前七张 Ardot 图的处理决定

| 当前画面 | 决定 | 下一轮设计责任 |
|---|---|---|
| Screen 1 知识主页 | **重定义** | 改为 Knowledge Library 群视图；删除营销 hero 权力；保留温暖气质与轻量 Resume |
| Screen 2 双镜工作区 | **保留方向，重构结构** | 成为 Group / Topic / Knowledge 连续场景；加入 DepthTrail、真实目录、selection、关系三态 |
| Screen 3 IA 星图 | **退出产品主稿** | 可保留为概念海报；真实设计改为 Library Network / Group Network 两个数据约束状态 |
| Screen 4 采集流 | **降权并补直接写作** | Add 分流；Source commit 与 Knowledge proposal 分开；零提取成功 |
| Screen 5 回答页 | **上下文化** | 变为 Ask result scene / overlay；显示 scope、used context、route、unknown 与回写后果 |
| Screen 6 概览编辑器 | **并回阅读面** | 不另开后台编辑器；在 Overview 中直接编辑，AI 建议为可检查 Diff |
| Screen 7 来源与存储 | **拆分** | Source Registry / Reader 与 Storage / Backup 分开，进入 utilities；不作为核心产品故事结尾 |

---

# 16. 代表场景

## 16.1 空白开始

用户创建“AI Agent 产品设计”，不填模板。产品进入 Bare Group；用户直接写“可逆行动”；安全提交后成为第一篇 Current Knowledge，并直接放在 Group root。Overview 只显示真实的一条知识、一个主动作与安静替代。

## 16.2 形成三层结构

用户创建`可靠性 → 操作安全 → 可逆行动`。进入“操作安全”先看到局部 Overview、直接子 Topic 和代表 Knowledge；返回、向上和 DepthTrail 都不丢失位置。

## 16.3 一条知识跨两个 Group

“工作记忆的容量限制”同时出现在“认知科学 / 记忆”和“AI Agent 产品设计 / 上下文管理”。正文只有一个 identity；两个 Placement 分别解释它在当前 Group 中为什么重要。

## 16.4 群关系可见但克制

“认知科学”与“AI Agent 产品设计”因多条稳定 Knowledge Relations 形成聚合建议。接受前 Library Network 只显示 suggestion layer；接受后才出现群关系“认知科学为 Agent 记忆与决策设计提供理论基础”，并可检查底层关系。

## 16.5 从 Overview 读到 Evidence

用户从 Group Overview 进入“可逆行动”，再定位到“所有副作用必须可撤销”的 Claim，打开 Evidence 后看到原 PDF 第 23–27 页片段，并可一步返回原段落。

## 16.6 从当前 Topic 提问

用户在“长期记忆”Topic 问“有哪些失败模式？”Requested scope 是当前 Topic；系统扩展到当前 Group 的一条桥接 Knowledge，Answer 明确显示 Effective / Used Context。点击某条结论回到原 Knowledge Anchor；关闭后回到提问前的 Topic 现场。

## 16.7 深层网络探索后返回

用户从一篇 Knowledge 打开 R1，沿关系跨到另一个 Group，再进入一条 Evidence。Return Stack 保留每个真正打开动作；hover 和 graph pan 不进入历史。用户可把精选的三个节点保存为 Path，但原始探索轨迹不会自动变成长期对象。

---

# 17. 指标与反指标

## 17.1 质量指标

- **Library Orientation Success**：用户能在 10 秒内指出“我有哪些知识群、当前从哪里继续”；
- **Scope Recognition**：用户能区分 Group、Topic 与 Knowledge，且不把 Topic 当成 Subgroup；
- **Depth Continuity**：从 Group 深入 Evidence 后仍能正确返回每一级；
- **Relation Readability**：用户能把所选 edge 读成一句关系并找到依据；
- **Placement Comprehension**：用户理解同一 Knowledge 多处出现但没有复制；
- **Ask Scope Predictability**：提问前能预测范围，回答后能解释实际用过什么；
- **Answer-to-Knowledge Return**：回答中的核心 Claim 可回到 Knowledge / Anchor / Evidence；
- **Direct Writing Trust**：用户理解普通写作会自然成为 current，不需要审批；
- **Structure Cost**：成熟 Group 增长时，整理动作不随内容数量线性增加；
- **Network Signal Ratio**：默认图中正式关系占可见连接的比例保持高，建议和临时 route 不污染 canonical graph。

## 17.2 反指标

- 用一级导航、tab 或页面数量证明完整；
- 用户最先学会的是 Objects、Lens、Compiler、Projection 等内部词；
- 用户把 Group 当文件夹，把 Topic 当子文件夹，把 Knowledge 当附件；
- 每条笔记都被 AI 拆成卡片；
- 所有节点都默认进入全局图；
- 相似度、引用、证据和正式关系共享一种线；
- Ask 结束后无法回到知识；
- Overview 成为每次打开重新生成的摘要；
- Source-only 被视为失败；
- 没有关系的 Group 被视为不完整；
- 默认 Home 被统计、变化、推荐和 Resume 同时占满；
- 正常写作需要“完成并采用”。

---

# 18. Given / When / Then 验收

## 18.1 一个产品中心

**Given** 用户打开已存在的个人知识库  
**When** 检查一级导航与首屏  
**Then** 知识库是唯一知识主地点；群视图与网络视图观察同一套 Group；Ask、Search、Add 是动作，Sources / History / Settings 是支撑入口。

## 18.2 群视图与网络视图同义

**Given** 用户在群视图选中 Group A 并设置一个筛选  
**When** 切换到网络视图再切回  
**Then** Group A、筛选、最近路径与 Library state 保持；不创建新 workspace 或改变知识真相。

## 18.3 普通打开与继续不同

**Given** Group A 上次停在深层 Knowledge Anchor  
**When** 用户分别点击 Group 名称与`继续`  
**Then** 前者打开 Group Overview，后者恢复 last-safe scene；两个动作标签与结果可预测。

## 18.4 Topic 可读但不是 Subgroup

**Given** 一个五层 Topic path  
**When** 打开第四层 Topic  
**Then** 显示局部 Overview、完整 DepthTrail、直接子项与代表 Knowledge；不出现独立 Group shell、Group Relations 或四套根入口。

## 18.5 丰富层级有限可见

**Given** 一个拥有 2,000 Topics 的 Group  
**When** 用户进入深层 path  
**Then** 默认只展开祖先、当前、少量兄弟、一级子项与代表 Knowledge；Search 和 deep link 仍可直接进入任何深度。

## 18.6 Group root content 不是未归类

**Given** Knowledge A 直接放在 Group root，Knowledge B 没有 Placement  
**When** 检查 Group 与全局未归入知识群  
**Then** A 是合法群内容，B 才是 unplaced；系统不催促用户为 A 建 Topic。

## 18.7 单一 Knowledge 多处出现

**Given** Knowledge K 在两个 Groups 有三个 Placements  
**When** 从任一路径编辑正文  
**Then** 三处读取同一 Current Revision；每个 Placement 的局部说明独立；History 能解释正文变更与位置变更。

## 18.8 Overview 不生成影子知识

**Given** Overview 中出现需要独立证据与关系的判断  
**When** 用户提升该判断  
**Then** 创建或链接一个 Knowledge，Overview 保留引入；原正文、Support 和历史可追溯，不复制成两份 current truth。

## 18.9 关系半径不改变阅读位置

**Given** 用户停在 Knowledge K 的第三个 Section  
**When** 在 R0、R1 与 R2 间切换  
**Then** Anchor、scroll、DepthTrail 与 Ask scope 不变；只有打开另一个端点才推进 Reading Trail。

## 18.10 图与列表同义

**Given** 当前 Relation scene 有 12 条边  
**When** 切换 List Equivalent  
**Then** 12 条关系的 identity、方向、状态、端点与筛选完全对应；键盘可完成选择、检查和打开。

## 18.11 跨群出口不冒充群关系

**Given** 两个 Groups 共享 Knowledge 并有一次跨群探索  
**When** 打开 Library Network  
**Then** 若没有 Direct 或 Accepted Aggregated Group Relation，不显示 canonical 群边；具体出口仍可在 Group / Knowledge 局部看见。

## 18.12 Search 深层进入可返回

**Given** Search 命中 Topic T 下 Knowledge K 的 Anchor A  
**When** 打开并返回  
**Then** 首先定位 A，同时显示完整 Placement path；返回恢复 Search query、分组、scroll 与 selection。

## 18.13 Ask 范围可解释

**Given** 用户在 Topic T 提问并允许扩展到当前 Group  
**When** 系统实际使用 T、Group 内 K2 与一个 Source Fragment  
**Then** Requested / Effective / Used Context 分开；每条 Answer Claim 可检查支持；本次 route 不写入正式关系。

## 18.14 Answer 不自动成为知识

**Given** AI 已生成 Answer  
**When** 用户关闭它  
**Then** current Knowledge、Overview 与 Relations 不变；只有明确选择保存 Answer、形成 / 合入 Knowledge 或接受 Relation / Overview Diff 才写入对应目标。

## 18.15 直接写作没有审批

**Given** 用户编辑自己的 Knowledge 且输入法 composition 已结束  
**When** 安全本地提交成功  
**Then** 新 Revision 成为 current，并显示`已更新当前知识`；没有“完成并采用”。

## 18.16 半句话不污染知识面

**Given** 用户正在输入未完成句子  
**When** Search、Ask、Overview Projection 或 Graph refresh 运行  
**Then** 仍使用最后一个 Current Revision；Edit Buffer 与 Recovery Checkpoint 不可被默认读取为知识。

## 18.17 Source-only 成功

**Given** 用户把 Source 加入深层 Topic，但解析失败或没有提取结果  
**When** 重新进入该 Topic  
**Then** Source 可从原 path 找回；不生成占位 Knowledge、Relation 或待确认卡片。

## 18.18 Bare 不伪造完整性

**Given** 新 Group 只有名称  
**When** 打开 Overview  
**Then** 显示真实空态和写第一条知识 / 建 Topic / 加 Source；不显示假摘要、假 Topics、假关系和空统计。

## 18.19 响应式责任不缩水

**Given** 同一深层关系探索在 Desktop 和 Mobile 进行  
**When** 检查可用动作  
**Then** 两者都能读关系陈述、查看依据、打开端点、返回原 Anchor；Mobile 只改变排列，不删除责任。

## 18.20 缓存损坏不损坏知识

**Given** 删除全部搜索索引、Graph layout、Overview Projection cache 与 workspace state  
**When** 从 Knowledge Package 恢复  
**Then** Groups、Topics、Knowledge、Placements、Relations、Sources、Evidence 与 Current Revisions 可重建；只丢失可重算或临时状态。

## 18.21 候选知识群不会静默成为知识结构

**Given** AI 从 18 条未归入知识群的 Knowledge 中识别出一个高相似度簇，同时一个 Saved View 当前命中其中 11 条  
**When** 用户检查建议、拒绝一次，再继续编辑知识  
**Then** 系统只显示可解释的 Group Candidate，列出建议边界、纳入 / 排除理由与 Placement 影响；拒绝后不创建 Group、Topic、Placement 或 Relation，View 继续动态，未来新命中也不会自动加入任何 Group；只有出现新证据时才可重新提出。

## 18.22 Library 启动与 Continue 权力分开

**Given** Library 同时存在安全 Resume、Pin、Recent、Saved Path 与一个需要修复的旧现场  
**When** 用户普通启动、打开 Group、新开窗口、显式点击`继续`或离线重启  
**Then** 默认始终是稳定 Library catalog；最多一条 Resume 解释恢复位置；普通 Group open 进入 Overview；只有`继续`进入 last-safe scene；不安全现场先到 safe fallback；其他快捷入口不改变 Resume 排名或 catalog 顺序。

## 18.23 Topic 开场是局部方向，不是额外页面

**Given** 一个深层 Topic 分别处于 Bare、Compact 与 Editorial 密度，并包含 direct Knowledge、descendant branches 与一个唯一子项变体  
**When** 用户 Expand、Inspect、Open Topic、直接打开 child Knowledge、从 Search 命中 Anchor、执行 Up / Back / Resume  
**Then** Expand / Inspect 不改变 Primary Reading；Open Topic 在同一 scroll surface 顶部先给局部 Orientation，再连续显示 direct children；不会自动跳到第一篇 Knowledge；deep link 不被 Overview 截停；祖先解释不逐层复制；单一子项不自动重定向；三种返回动作恢复各自语义。

## 18.24 关系呈现由意图升级

**Given** 用户正在普通阅读，并存在一条可见 Relation Cue、一个可恢复的旧 Companion 和一个 AI RelationCandidate  
**When** 用户仅 hover / focus、明确 Inspect、点击`查看相关知识`、点击`在地图中探索`、固定 Companion、再普通打开另一篇 Knowledge  
**Then** hover / focus 不升级；Inspect 只进入 Peek；显式查看才进入 Companion；显式探索才进入 Explore；普通打开保持 Quiet，不因旧状态或 Proposal 自动占据右侧；Pinned target 明示且不随正文漂移；各级 Close / Back 恢复 exact focus、Anchor、scroll、DepthTrail、Ask scope 和 map viewport。

---

# 19. 研究事实、产品推论与边界

## 19.1 Research Facts

### 同一对象可以属于多个层级集合而不复制

Zotero 官方说明同一 item 可以同时进入多个 collections / subcollections，像 playlist 而不是文件夹；删除 collection 不删除 item；父 collection 是否包含子 collection item 又是独立显示选择。  
来源：https://www.zotero.org/support/collections_and_tags

### 人工集合与动态查询承担不同责任

Anytype 官方把 Collection 描述为手工加入对象的集合，把 Query 描述为从整个 Graph 动态取得对象；两者外观可相似，但 membership 来源不同。  
来源：https://doc.anytype.io/anytype-docs/getting-started/sets/collections

Capacities 官方同样区分手工策展的 Collections 与按规则自动更新的 Queries，并允许一个 object 进入多个 collections。  
来源：https://docs.capacities.io/reference/collections

### 全局图与局部图是不同关系半径

Obsidian 官方 Graph View 显示整个 vault 的 notes 和 links，Local Graph 只显示与 active note 相连的 notes，并允许改变深度；Outline 与 Backlinks 又作为 active note 的上下文能力分别存在。  
来源：https://obsidian.md/help/plugins/graph  
来源：https://obsidian.md/help/plugins/outline  
来源：https://obsidian.md/help/plugins/backlinks

### 层级位置需要持续可见

Obsidian 官方 File Explorer 的 Auto-reveal 会跟随当前 note 并在 folder tree 中高亮其位置，说明“正在读什么”与“它位于哪里”需要保持连续。  
来源：https://obsidian.md/help/plugins/file-explorer

### 顶层工作空间、动态查询与知识范围不是同一种容器

Tana 官方把 Workspace 定义为拥有成员、Home、schema、settings、trash、publishing / export 与访问边界的顶层容器；Search Node 则保存查询条件，结果是指向原对象的实时 references，编辑结果会编辑原对象。Obsidian Bases 同样让多个 Views 在同一份 notes / properties 上保存各自的 filter、sort、group 与 layout。  
来源：https://outliner.tana.inc/learn/features/workspaces  
来源：https://outliner.tana.inc/learn/features/search-nodes  
来源：https://obsidian.md/help/bases

这些资料支持三种责任必须分开：Workspace 负责系统与访问边界，View / Query 负责动态观察，Knowledge Group 负责长期理解范围。本产品因此不让 Group 拥有独立权限 / schema / settings，也不让动态结果直接成为 Group membership。

### 层级节点可以是可聚焦范围，也可以只展开结构

Tana 允许任意 node zoom 成当前页面，同时用 breadcrumb 保留位置；expand / collapse 只改变当前上下文。Docusaurus 允许 category 同时拥有介绍内容与 direct-children generated index。Wikipedia 的 lead guideline要求开头以简洁、可独立理解的方式反映正文重点，而不把正文不存在的重要信息只写在 lead。Apple 的 disclosure / outline guidance也把展开层级与进入内容区分。

这些模式支持 Topic 同时拥有“局部开场”和“真实子结构”，但不证明每层都需要长摘要。本产品因此选择：显式 Open Topic 进入紧凑局部开场；Expand 只展开；deep link 直达；Bare / Compact / Editorial 由真实内容决定。

来源：https://outliner.tana.inc/learn/features/outline-editor  
来源：https://docusaurus.io/docs/sidebar/items  
来源：https://en.wikipedia.org/wiki/Wikipedia:Manual_of_Style/Lead_section  
来源：https://developer.apple.com/design/human-interface-guidelines/disclosure-controls  
来源：https://developer.apple.com/design/human-interface-guidelines/outline-views

### 状态恢复与稳定目录不必互相替代

Apple 建议应用恢复足够细的上次状态；Notion 同时提供 Home、Last visited page 或侧栏顶层页面作为默认落点，并把 Home / Recent / Favorites 与 Library 浏览分开；Tana 也分别提供固定入口与 Recents。

这些资料支持“连续性”和“稳定定位”是两个同时存在的需求，但没有证明知识库应自动恢复深层现场。本产品据此冻结为：稳定 Library catalog 是普通落点，最多一条 Resume 承担显式恢复，普通 Group open 仍进入 canonical Overview。

来源：https://developer.apple.com/design/human-interface-guidelines/launching/  
来源：https://www.notion.com/help/home-and-my-tasks  
来源：https://www.notion.com/help/navigate-with-the-sidebar  
来源：https://outliner.tana.inc/learn/features/sidebar

### 主内容、预览、支撑窗格与完整探索可以分工

Apple Split View 将主内容、导航与 supplementary pane 作为可组合但有主次的区域，并允许在编辑时隐藏其他 pane；Material 3 Adaptive Supporting Pane 让主 pane 保持焦点，宽屏并列支撑信息、窄屏一次只显示一 pane 并用 Back 保持连续；Capacities 区分 full page、preview modal、side panel 与 tabs；Obsidian 区分 hover Page Preview、active-note Backlinks、Local Graph 与真正打开 note。

这些模式支持“关系可以从局部预览逐级增长为支撑窗格和主探索面”，但不证明任何知识库都应固定双栏。本产品因此冻结 Quiet → Peek → Companion → Explore，并进一步限制 ordinary open 为 Quiet、Companion follow explicit Open、单 Companion 上限。

来源：https://developer.apple.com/design/human-interface-guidelines/split-views  
来源：https://developer.android.com/develop/adaptive-apps/guides/build-a-supporting-pane-layout  
来源：https://docs.capacities.io/reference/navigation  
来源：https://obsidian.md/help/plugins/page-preview  
来源：https://obsidian.md/help/backlinks  
来源：https://obsidian.md/help/plugins/graph

## 19.2 Product Decisions

以下是本产品决定，不是研究直接证明：

- 只有一个 Knowledge Library 主地点；
- 群视图与 Network 是同一 Library 的两种观察；
- Topic 拥有局部 Overview，但不是 Subgroup；
- D0–D5 与 R0–R3 两轴独立；
- Group Relation 只接受 Direct 或 Accepted Aggregated；
- Sources 退到支撑层；
- Group / Topic / Knowledge 共用连续 reading shell；
- 普通写作安全提交后自然成为 current。
- Group 可以从空白、已有 Knowledge、Sources、Topic、View snapshot 或导入层级开始，但所有路径生成同一种 Group；
- AI 相似度簇只生成可丢弃的 Group Candidate，不能静默创建 Group。
- 普通启动进入稳定 Library catalog；最多一条 Resume 只在显式点击后恢复深层现场。
- 方向 3 的连续阅读是 resting backbone；方向 2 使用 Quiet → Peek → Companion → Explore 的弹性呈现阶梯，普通打开不自动恢复关系面。
- Companion 默认只跟随 explicit Open，Pinned target 始终明示，一个 Workspace 最多一个 Companion。

## 19.3 Product Hypotheses

仍需真实任务验证：

- Library-first 是否比独立 Home 更容易让用户确认“这是我的知识库”；
- Network 作为 Library view 是否足以支持跨群探索，而不会被误解成筛选样式；
- Bare / Compact / Editorial Topic opening 是否在深层群中降低迷失，同时不制造递归阅读与维护负担；
- D / R 两轴是否能通过界面自然成立，而无需向用户解释术语；
- Local Graph 默认只显示 4–8 个、Group / Library 默认只显示少量高价值出口，是否既克制又不遮蔽重要连接；
- Source utility 降权后，用户是否仍能容易完成阅读、核验、迁入和恢复。
- Group Candidate 的边界、纳入 / 排除解释与一次性预览是否足以帮助用户判断，而不会制造新的整理 Inbox。
- 用户是否自然理解“普通打开进入 Overview、显式继续恢复现场”，以及单条 Resume 是否足以覆盖并行任务。

## 19.4 本轮关闭的产品开放项

本轮已关闭“3 + 2 是否等于永久右半屏”的产品级开放项：**不等于**。连续阅读拥有 resting-state 主权，关系以 Quiet → Peek → Companion → Explore 随明确意图增长。

当前不再保留会反向改变产品本体的布局开放项。具体 pane 比例、转场、视觉 token 与邻接预算仍属于设计证明和任务测试中的假设，不应重新制造第二套信息架构。

---

# 20. 结论

这个产品的完整性不来自更多页面，而来自一套所有页面都无法违背的知识体验：

- 用户首先看到一个真实知识库和一个个知识群；
- Group 可以从用户真实已有材料自然形成，但动态 View、文件夹和 AI 聚类不会冒充知识边界；
- 群视图与知识网络只是同一知识世界的两种看法；
- 每次进入都沿 Group → Topic → Knowledge → Claim → Evidence 连续深入；
- 每一级先给方向，再给结构，再给细节；
- 关系按当前范围出现，且每条都能读成一句话、检查条件与依据；
- 同一 Knowledge 可以跨群出现，却始终只有一份正文和历史；
- Ask、Search 与 Explore 都把用户带回知识，而不是把知识带进另一个聊天产品；
- 写作、来源、版本、恢复与导出可靠存在，但不与阅读和理解争夺中心。

只有这套模型被用户确认，方向 3 + 2 的视觉语言才有稳定的产品对象可以承载。下一轮设计不应继续添加孤立屏幕，而应围绕十二个证明家族，先把 Library → Group → Topic → Knowledge → Relation / Ask → Evidence 这条主路径完整画通。
