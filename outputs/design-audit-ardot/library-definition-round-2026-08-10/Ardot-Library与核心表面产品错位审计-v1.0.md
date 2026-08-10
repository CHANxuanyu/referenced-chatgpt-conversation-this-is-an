# AI-native 个人知识库

## Ardot Library 与核心表面产品错位审计 v1.0

> 审计日期：2026-08-10  
> 审计对象：[AI-native 个人知识库 · 设计探索 v2（星图手稿）](https://ardot.tencent.com/file/711670254240951?node_id=0%3A1)  
> 当前产品基线：`AI-native-个人知识库-终局产品设计文档-v6.0.md`、`AI-native-个人知识库-Library入口、目录浏览与继续阅读合同-v1.0.md`、`AI-native-个人知识库-表面架构、场景家族与完整设计证明合同-v1.0.md`  
> 本轮新证据：从当前登录 Ardot 画布重新捕获并逐张检查的七屏总览、Screen 1、Screen 2、Screen 3  
> 审计范围：Library 入口 → Group 阅读 → Network 探索的核心三步，以及七屏是否构成完整产品表面系统  
> 边界：只读审计；没有修改 Ardot、没有补画 Screen、没有制作视觉选项或原型  
> 证据限制：静态截图可以证明可见信息、构图、文案和正常态；不能证明真实交互、持久化、键盘、读屏、响应式、错误恢复或 exact return

---

# 0. 总体判断

> **当前七屏不是一个完整产品设计，也不是最新产品定义的正确 Surface Skeleton。它们最有价值的部分是方向 3 + 2 的视觉气质；最需要推翻的部分是“星图就是产品、七张功能页就是完整体验”的结构。**

这不是“再加几个页面”就能修复的问题。当前画布存在四个产品级错位：

1. Screen 1 把星图、内容数量、AI 析出和二合一输入框置于中心，Stable Library Catalog 反而不存在；
2. Screen 2 把阅读与关系永久并排，未表达 Quiet → Peek → Companion → Explore；
3. Screen 3 仍展示旧八对象与 L0 Atlas 模型，和 v6 四类 canonical truth、Groups / Network 两视图直接冲突；
4. 七屏是七个孤立正常态，没有共享 Shell、转场、返回、空态、失败、规模、响应式和辅助技术证明。

因此，当前设计的正确处置不是继续在现有七屏上补按钮，而是：

- 保留 Screen 1 / 2 的 Warm Paper 与 Relation Night 情绪对比；
- 把 Screen 1 产品结构完全重做为 Stable Library；
- 把 Screen 2 从固定双栏变成关系按需增长的 Reading scene family；
- 把 Screen 3 从“对象模型海报”重做为真实 Group Network state family；
- 把七张静态屏降级为视觉 specimen，不再按 Screen 数计算完整度。

---

# 1. 当前证据

## Step 0 · 七屏总览

![七屏总览](/Users/a1234/Documents/Codex/2026-08-03/referenced-chatgpt-conversation-this-is-an/outputs/design-audit-ardot/library-definition-round-2026-08-10/03-current-seven-screen-overview.png)

**健康度：不完整；功能名覆盖较广，但没有形成产品表面系统。**

七张图分别命名为知识主页、双镜工作区、IA 概念星图、采集流、回答页、概览编辑器、来源与存储。这个清单混合了：

- 产品入口；
- 阅读现场；
- 本体说明图；
- 一条形成流程；
- AI 任务结果；
- 一个编辑状态；
- 一个设置页面。

它没有回答：

- 哪个是唯一主地点；
- 哪些是同一对象的不同 presentation；
- 哪些是全局动作产生的临时 Workspace；
- 用户从一张图怎样进入另一张、完成后回哪里；
- 哪些状态共享同一 Shell；
- 哪些图只是 supporting utility；
- 什么证据才能判定设计完整。

七屏目前更接近一套概念提案 Deck，而不是可执行的产品设计系统。

---

# 2. 三步核心体验审计

## Step 1 · Screen 1 知识主页

![当前 Screen 1](/Users/a1234/Documents/Codex/2026-08-03/referenced-chatgpt-conversation-this-is-an/outputs/design-audit-ardot/library-definition-round-2026-08-10/02-current-screen-1-library.png)

**健康度：高风险；视觉个性强，产品入口与最新合同相反。**

### 可保留

- Warm Paper 与深色 Relation Night 已形成差异鲜明的品牌母体；
- 中文大标题、编辑出版感和克制的配色比通用 SaaS Dashboard 更有产品个性；
- Group 卡片使用真实主题名称而不是抽象占位块；
- Ask 与探索被放在可见位置，说明设计意识到 AI 和关系是核心能力。

### 产品级冲突

1. `知识星图 · Codex`和`把零散的笔记，连成一片活的星图`把 Graph 设为产品本体，而用户已明确产品本质是 Knowledge Library；
2. 右侧星图占据最大视觉权重，却没有 Relation statement、direction、standing、scope、selection 或 List Equivalent；
3. `已收录 1,284 条笔记、312 段引用、47 个知识群`用数量替代理解与可找回性；
4. 输入框同时写`提问 / 收录`，混淆 Ask 与 Add 的数据后果，Search 也无独立位置；
5. `精选星群`只显示两个 Group，不能证明 All Groups 穷尽、稳定排序和 G100 / G1K；
6. 没有 Groups / Network 同义视图切换；
7. 没有最多一条安全 Resume、少量 Pins 与完整 All Groups 的注意力顺序；
8. 没有普通 Open Group 与 Continue Group 的不同后果；
9. 没有 All Knowledge 与独立知识的次级 inventory；
10. `最近变化 · AI 新析出 3 条`把系统变化放到首页注意力中心，重新制造维护 Feed；
11. 标签`可逆行动原则 / Agent 失败模式 / 长程记忆策略`看似推荐或动态建议，却没有说明 membership、来源和保存后果；
12. 页面只证明成熟 Library 正常态，没有 Empty、G1、G100、index partial、offline、archived target 或 Recovery。

### 可访问性风险

- 纸张纹理上的灰色小字有对比风险；
- 星图含义依赖亮度、空间距离和细线；
- 图中没有同义列表与文本关系句；
- 多个小标签的键盘顺序与触控目标不可见；
- 截图不能证明 200% zoom、读屏 landmarks、focus 与 selection 分权。

### 结论

Screen 1 不能增量修补。它需要保留视觉气质、重置产品骨架：

```text
Stable Library
→ optional one Resume
→ explicit Pins
→ exhaustive All Groups
→ secondary Independent / Recent / Saved Views / All Knowledge
↔ same-truth Network view
```

星图不再是 Hero，而是 Network view 中由真实 Groups 与 Current Group Relations 生成的任务表面。

---

## Step 2 · Screen 2 双镜工作区

![当前 Screen 2](/Users/a1234/Documents/Codex/2026-08-03/referenced-chatgpt-conversation-this-is-an/outputs/design-audit-ardot/library-definition-round-2026-08-10/04-current-screen-2-reading-relation.png)

**健康度：视觉母体最有价值；Reading 内容仍过浅，Relation presentation 错误。**

### 可保留

- 左侧 Warm Paper、右侧 Relation Night 是用户选择“3 + 2”的最佳现有视觉证据；
- 连续正文、section、引用与留白接近 Knowledge Paper，而不是卡片墙；
- 深色关系面与阅读面具有清楚的任务差异；
- 整体气质克制、成熟，值得成为后续视觉方向输入。

### 产品级冲突

1. Relation Night 永久占据约三分之一画面，普通阅读无法从 Quiet 开始；
2. 没有显式 Peek、Companion、Explore 触发与关闭后的 exact return；
3. 关系节点仍是`可逆行动 / 最小权限 / 可观测轨迹 / HITL 边界`名词，没有可读 statement、direction、qualifier、basis 与 standing；
4. Reading 主面只有短文章，没有 Group Overview → Topic Opening → long Knowledge → Claim → Evidence 的丰富层级；
5. 没有 DepthTrail、local outline、current section、Anchor 或多 Placement context；
6. `知识群概览`是一张统计卡，未承担 Boundary、structure、stable entries、unknowns 与跨群出口；
7. `新建笔记`继续采用 note-first 语言，没有区分直接写 Knowledge、加 Source、建 Group 与提问；
8. `AI 新析出 3 条`再次让系统产出成为常驻注意力；
9. 没有 Graph / List 等价、Inspector、zero relation、one relation、dense relation 或 graph failed；
10. 没有窄屏时 Reading priority 和 Relation sheet / list 的责任等价。

### 可访问性风险

- 关系面标签、细线和背景高光对低视力用户不稳定；
- 关系方向与类型主要依赖几何；
- 固定双栏在窄屏和 200% zoom 下难以保持正文宽度；
- 截图不能证明正文阅读顺序、关系区键盘遍历和关闭后的 focus return。

### 结论

Screen 2 应保留视觉对比，但拆成同一 Reading scene 的四个状态：

```text
Quiet Reading
→ relation cue / Peek
→ optional Companion
→ explicit Explore Primary
→ exact Back to original Claim
```

“方向 3 + 2”不是永久双栏比例，而是同一知识 identity 在阅读与关系任务之间的连续变形。

---

## Step 3 · Screen 3 IA 概念星图

![当前 Screen 3](/Users/a1234/Documents/Codex/2026-08-03/referenced-chatgpt-conversation-this-is-an/outputs/design-audit-ardot/library-definition-round-2026-08-10/05-current-screen-3-network.png)

**健康度：产品语义应整体替换；只保留 Relation Night 艺术方向。**

### 可保留

- 深色空间感可以成为 Explore Profile 的情绪基础；
- 设计尝试区分 Ask、Search、Explore 三种意图；
- 左右辅助区域说明设计意识到图本身需要解释与动作；
- 空间聚焦、发光节点与深色背景具备可发展的品牌语言。

### 产品级冲突

1. `八类对象`把 Note、Topic、Group、Reference、Evidence、Overview、Query、Source 混在一个层级，与 v6 四类 canonical truth 和五个日常概念冲突；
2. `L0 全景 Atlas → L5 证据`把结构深度、关系半径和表面跳转锁成一条旧路线；
3. 画面混合 Groups、Knowledge、数字标签和行星名称，不是 Library Group Network；
4. 图像中的星球、星云和大部分连线是艺术素材，无法承担真实数据可视化；
5. 没有完整 Relation statement、direction、standing、Current / Suggested / History；
6. 没有零关系、一个 Group、一条 Relation、同 pair 多关系和 unconnected Groups；
7. 没有选中 Group 的 Boundary、Relation Inspector、Pair 或 supporting Knowledge；
8. 没有 List Equivalent、keyboard route 和 screen-reader relation sentence；
9. `Ask / Search / Explore`被写成三种进入模式，而不是有不同后果、可以互相转换并返回的全局动作；
10. 没有从 Groups Catalog 切入同一 scope，也没有关闭后恢复 Catalog / Reading scene。

### 可访问性风险

- 信息主要依赖位置、颜色、亮度、大小与连线；
- 中心图中的小字与背景复杂度降低可读性；
- Focus、selection、open 与 inspect 没有非颜色区分；
- 没有可被辅助技术读取的同义结构。

### 结论

Screen 3 不应继续补图例或替换节点名。后续必须从真实 Group Network 状态重新建立：

```text
Current Groups
+ Current Group Relation statements
+ explicit scope / selection
+ Graph / List equivalence
+ Inspector / Pair
+ Current / Suggested / History separation
+ exact return
```

---

# 3. 产品定义与当前设计的差距

| 产品责任 | 当前可见证据 | 判断 |
|---|---|---|
| 一个 Stable Library | Screen 1 有“主页” | 名称存在，产品中心错误 |
| Groups / Network 同一 Library | Screen 1 星图 + Screen 3 Atlas | 两张孤立图，不是同一 view state |
| All Groups 穷尽 | 两张精选 Group 卡 | 未证明且方向相反 |
| Resume / Pin / Recent 分权 | 只有最近变化 | 未证明 |
| Ordinary Open / Continue | 无 | 未证明 |
| All Knowledge / Independent | 无 | 未证明 |
| Group Boundary / Overview | 一张统计卡 + 短文章 | 仅视觉近似 |
| Overview → Evidence 层级 | Screen 3 底部 L0–L5 标签 | 概念说明，不是可走体验 |
| Reading primary | Screen 2 左侧长文 | 视觉部分成立 |
| Relation on demand | Screen 2 永久关系栏 | 行为相反 |
| Group-level Network | Screen 3 混合对象图 | 失败 |
| Relation statement | 名词节点与装饰线 | 失败 |
| Search / Ask / Add 分权 | Screen 1 `提问 / 收录` | 直接冲突 |
| Answer ↔ Evidence ↔ Explore ↔ Back | Screen 5 单一回答页 | 未证明 |
| Source Reader / formation | Screen 4 / 7 功能页 | 局部命名，不成连续流程 |
| History / Recovery | 无 | 未证明 |
| Empty / partial / failure / scale | 无 | 未证明 |
| Responsive / accessibility | 只有 1440×920 正常态 | 未证明 |

---

# 4. 完整设计为什么不能继续按“Screen 清单”推进

一个产品责任至少需要：

```text
Entry
→ visible context
→ main action
→ result
→ failure / partial
→ recovery
→ return
→ responsive / accessibility equivalent
```

一张正常态 Screen 最多证明可见结构和视觉层级，不能证明：

- Open 与 Continue 的后果；
- Ask / Add 是否写入；
- Back 是否回到原 Claim；
- Graph / List 是否同义；
- offline / index partial 是否保留 knowledge；
- Recovery 是否保护未提交内容；
- narrow / mobile 是否保留责任；
- keyboard / screen reader 是否完成同一任务。

因此后续设计单位应从 Screen 改为 **Design Proof Bundle**。一个 Bundle 可以由 Full Frame、Flow Steps、Component Variants、State Matrix、Return Annotation 与可运行行为证据共同完成；不要求每个组合都画成独立页面。

---

# 5. 最高影响的修订顺序

## 5.1 先冻结完整 Surface Architecture

先定义：

- 一个持续 App Shell；
- Library / Reading / Relation / Answer / Source 五种主要 scene family；
- Overlay、Companion、Inspector、Decision / Recovery 与 Utility 的职责；
- Search / Ask / Add 入口、结果与返回；
- Window / Workspace state 和 canonical truth 的边界。

## 5.2 再定义 Design Proof Bundles

至少覆盖：

- Empty / daily / G100 Library；
- Overview → deep Knowledge → Evidence；
- Quiet → Peek → Companion → Explore → Back；
- zero / one / dense Group Network + List；
- Search exact Anchor；
- Ask scope / claim citation / write-back；
- Source-only / formation / semantic update；
- Recovery / History / clean restore；
- mobile / keyboard / screen reader。

## 5.3 最后才进入视觉 Frames

新视觉应先从 Screen 1 successor、Reading state family 和 Group Network state family开始，不修补当前七屏。Screen 4–7 在其 owner contracts 完成设计证明前只保留为局部视觉 specimen。

---

# 6. 审计结论

当前画布已经给出了一个值得保留的审美答案：

> 温暖、编辑出版式的知识阅读，遇到关系任务时进入深色、空间化的探索。

但它还没有给出完整产品答案：

> 用户每天怎样进入全部知识、怎样从 Overview 深入、怎样在关系空间中选择、怎样 Ask 并回到依据、怎样在失败和长期演化中保持知识可找回。

所以这一轮最重要的设计修订不是画得更多，而是把视觉 specimen 重新放回正确产品结构：Library 是重力中心，Reading 是默认道路，Relation 是按需第二维度，AI 是可核验能力，Source / History / Recovery 是支撑责任。只有这些责任通过连续状态被证明，设计图才可以被称为完整产品设计。
