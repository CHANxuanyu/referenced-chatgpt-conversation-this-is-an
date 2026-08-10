# AI-native 个人知识库

## 表面架构、场景家族与完整设计证明合同 v1.0

> Canonical：`AI-native-个人知识库-终局产品设计文档-v6.0.md`  
> 文档状态：**ACTIVE_APPENDIX；已完成 Canonical 同步、注册与相邻责任划分**  
> 深化范围：v6 §3 App Shell、§11 产品表面架构、§12 Journeys、§13 States、AC-01–AC-32 的设计证明责任  
> 本合同拥有：Scene family、Surface role、App Shell、transition / return、state family、responsive / accessibility equivalence 与 Design Proof Bundle  
> 本合同不拥有：Group / Knowledge / Relation / Source 真相、视觉风格、具体布局、组件造型、技术栈、研发排期或可点击原型  
> 用户语言边界：`AI-native-个人知识库-用户可见信息架构、产品语言与复杂度披露合同-v1.0.md`拥有用户可见术语、动作、状态句、披露层与 copy proof；本合同只拥有承载这些语言的 Scene / Surface / DPB 结构  
> 当前视觉证据：`design-audit-ardot/library-definition-round-2026-08-10/`  
> 日期：2026-08-10

---

# 0. 执行结论

## 0.1 一句话

**完整产品设计不是“为每个功能画一张页面”，而是让同一个 Knowledge Library 在入口、阅读、关系、回答、来源、失败、恢复与返回中拥有连续、可验证、责任等价的表面系统。**

## 0.2 冻结的 42 项决定

1. **产品只有一个稳定 App Shell。**Library、Reading、Relation、Answer、Source 与 supporting utilities 共享位置、全局动作、状态和返回语义。
2. **一级产品地点仍只有 Knowledge Library。**Scene family 不是新的 Place，也不产生多套导航。
3. **五个主要 Scene families 固定为 Library、Continuous Reading、Relation Space、Answer、Source Reader。**
4. **History、Recovery、All Knowledge、Archived、Import / Export、Trash、Settings 是 Supporting Utility scenes。**
5. **Formation、Search results、Decision 与 Compare 是从 owner context 发起的 task surfaces。**它们不成为第六、第七个产品中心。
6. **Scene 与 Resource 分权。**打开一个新 Surface 不创建对象；存在一个对象也不要求独立全页。
7. **同一 Resource 可以出现在 Primary、Companion、Inspector、Overlay 或 Utility context 中。**identity 和 Current truth 不复制。
8. **同一时刻只有一个 Primary task。**desktop 可以有一个 Companion；Inspector 和 Overlay 不与 Primary 争夺任务所有权。
9. **Primary 是用户当前完成任务的主表面。**它不是视觉面积最大的装饰区域。
10. **Companion 只承担与当前 Primary 直接相关的第二责任。**关闭后精确恢复 Primary focus。
11. **Inspector 用于检查 identity、relation、evidence、history 或 impact。**Inspector 不创建新导航中心。
12. **Overlay 用于短暂、可取消、完成后回原现场的动作。**Search、Quick Ask 和 Add 起点可以是 Overlay。
13. **Decision / Recovery surface 只用于有明确后果的选择。**不能把未提交内容、冲突或删除压成普通 toast。
14. **Utility 是支撑长期可信的表面，不是低价值页面。**但 Utility 不接管冷启动、首页和主导航注意力。
15. **Library cold start 永远遵守 Resume → Pins → All Groups 的责任顺序。**视觉可以变化，信息权力不能变化。
16. **Groups / Network 切换是同一 Library scene 的 view change。**不是跳去 Atlas，也不清空 scope / selection。
17. **普通 Open Group 进入 Current Overview。**Continue 才恢复最近安全 deep scene。
18. **Reading 的普通状态是 Quiet。**Relation 只通过 cue → Peek → Companion → Explore 逐级增长。
19. **Explore 可以成为 Primary，但不创建第二份 Reading state。**Back 恢复 origin revision、placement、anchor、scroll 和 focus。
20. **Answer 是同一 Shell 中的连续 Paper。**Composer 是起点，不是聊天产品中心。
21. **Source Reader 是来源核验表面。**连接器设置、Source Registry 和原文 Reader 不混成一页。
22. **Search、Ask、Add 三个全局动作始终有不同后果。**不能用一个含混 omnibox 静默判断模式。
23. **Search 命中后直接 Open target，并携带结果现场的 Return Envelope。**
24. **Ask 形成 Answer scene；关闭或离开不改变 Current Knowledge。**写回必须是独立原子动作。
25. **Add 的入口可以轻，提交后果必须精确。**Direct Current、Source Commit、Formation Proposal 与 Placement 分权。
26. **所有跨 Scene 导航携带 Return Envelope。**Back 与 Up 不混淆，关闭 Inspector / Overlay / Companion 先回 origin。
27. **Workspace state 与 canonical truth 分权。**panel width、selection、zoom、filter、scroll 和 graph layout 不写入知识模型。
28. **窗口各自拥有 Workspace scene。**新窗口默认从 Library 开始；显式`在新窗口打开`才复制 target，不复制未提交状态。
29. **Calm、Focused、Decision、Forensic 是披露级别，不是四个页面。**同一 Scene 依据任务逐步增加信息。
30. **Empty、partial、offline、unavailable、conflict、recovery、historical、large-scale 都是核心 state families。**不是原型后的补充。
31. **任何派生能力失败都保留 canonical reading。**Index / AI / graph layout unavailable 不变成产品级错误页。
32. **Graph 永远有 List Equivalent。**两者共享 selection、filter、relation semantics、open 和 return。
33. **Responsive 改变排布，不改变责任。**Companion 可以变 Sheet，Graph 可以变 List，Evidence 可以顺序展开；能力不能消失。
34. **Keyboard focus、selection、open 和 inspect 分权。**移动焦点不能自动写 Recent、改变 Current 或打开重型场景。
35. **设计完整度按 Design Proof Bundle 计算，不按 Screen 数计算。**
36. **一个 Bundle 必须证明 entry、context、main action、result、failure / partial、recovery 与 return。**
37. **静态 Frame 只能证明可见结构。**持久化、键盘、读屏、响应式和 exact return 需要相应证据。
38. **当前七张 Ardot Screen 全部降级为 Visual Specimens。**它们不自动通过任何完整产品责任。
39. **Screen 1 必须整体重构。**Screen 2 保留视觉母体、重建状态；Screen 3 保留艺术方向、替换产品语义。
40. **设计图必须使用三份真实 fixture 和 G100 / K10K synthetic fixture。**抽象节点和短占位文案不计语义证明。
41. **本合同不授权制作原型。**先确认 Surface Architecture、Proof Bundles 和当前 Ardot 的处置。
42. **只有全部核心 Bundles 有可定位证据、无产品冲突并通过跨状态 QA，才可称为“完整产品设计”。**

## 0.3 本合同解决什么

现行专项合同已经分别定义了：

- Library 入口与 Catalog；
- Group / Topic / Placement；
- Overview 与连续正文；
- Relation truth 与 Network；
- Ask / Answer 与返回；
- Source 与 Knowledge formation。

本合同解决它们共同缺失的桥：

> 这些产品责任如何共用一个 Shell，什么时候成为 Primary、Companion、Inspector 或 Overlay，怎样跨场景进入和返回，以及需要什么设计证据才能证明它们真的属于一个完整产品。

---

# 1. 为什么七张好看的图仍然不是产品

## 1.1 Page list 不是 Surface Architecture

当前 Ardot 七屏用功能名组织：Home、dual mirror、IA graph、capture、answer、overview editor、sources / storage。它们混合了：

- Place；
- Scene；
- presentation；
- workflow step；
- object editor；
- settings；
- conceptual diagram。

如果没有统一 Surface taxonomy，设计会自然产生：

- 每个功能一套 Header；
- 每个画面一套 Back；
- 同一对象在阅读、编辑、图谱和回答中看似四份内容；
- Supporting utility 被误当一级页面；
- 正常态画完就宣称完成；
- 失败、恢复和移动端永远延期。

## 1.2 视觉隐喻不能承担产品真相

纸张、星图、光点和空间连线可以表达气质，但不能替代：

- canonical membership；
- Group Boundary；
- Relation statement；
- Current / Suggested / History；
- Anchor；
- Source revision；
- Resume eligibility；
- Return Envelope；
- failure / partial state。

视觉隐喻必须投影真实数据，而不能为了“像知识网络”生成装饰性真相。

## 1.3 一张图无法证明行为

例如 Screen 2 同时画出正文和关系面，只能证明两种视觉可以并存，不能证明：

- 普通阅读是否 Quiet；
- 谁触发关系面；
- Peek 与 Open 是否不同；
- 图关闭后回到哪一段；
- mobile 是否保留 relation meaning；
- graph failed 是否仍能完成任务。

这些责任需要连续状态和行为证据。

---

# 2. 核心术语

## 2.1 Scene family

Scene family 是用户当前任务的稳定表面语境。它回答“我正在做什么”，而不是“数据库里是什么对象”。

五个主要 Scene families：

| Scene | 用户问题 | Primary content |
|---|---|---|
| Library | 我拥有什么，从哪里开始或继续 | Catalog / Network view |
| Continuous Reading | 这个范围和理解是什么，怎样深入 | Overview / Topic Opening / Knowledge Paper |
| Relation Space | 两端为什么相连，可以向哪里探索 | Graph / List / Inspector / Pair |
| Answer | 基于这些知识，问题的回答、依据和未知是什么 | Answer Paper / Claim support |
| Source Reader | 原材料是什么，具体片段怎样支持或挑战理解 | Source revision / Fragment context |

## 2.2 Surface role

Surface role 说明一个表面在当前任务中的权力：

| Role | 责任 | 生命周期 |
|---|---|---|
| Primary | 当前主任务 | 直到明确导航或关闭 Workspace |
| Companion | 与 Primary 同时参考 / 操作的第二责任 | 按需打开，可关闭 |
| Inspector | 检查选中对象的语义、依据、历史或影响 | 跟随 selection，可 Pin |
| Overlay | 短暂 Search / Ask / Add / command | 完成或取消即回 origin |
| Decision / Recovery | 理解并提交有后果的变化 | 解决、延期或取消 |
| Utility | 管理长期支撑责任 | 显式进入，完成后返回 |

Role 不是固定区域。Desktop Companion 在 mobile 可以成为 Sheet；Inspector 可以从右侧转为顺序 detail；语义不变。

## 2.3 Presentation profile

v6 的三个 Presentation profiles 保持：

- Reading：正文 Primary；
- Companion：正文 Primary + 一个第二责任；
- Explore：Relation Primary + Reading context / Inspector。

Profile 属于 Workspace，不改变 Resource、Relation standing 或 current revision。

## 2.4 Workspace scene

Workspace scene 是可恢复的当前现场，包含：

- window identity；
- Scene family / profile；
- primary target；
- revision / placement context；
- anchor / scroll；
- selection / filters；
- companion / inspector state；
- overlay / decision origin；
- Return Envelope。

它不包含 canonical content copy，也不因恢复而自动提交 Buffer / Proposal。

## 2.5 Frame 与 Design Proof Bundle

- **Frame**：某个 viewport 与 state 的可见设计证据；
- **Flow Step**：一次动作前后的连续证据；
- **Component Variant**：同一责任在不同状态的可见变化；
- **State Matrix**：状态、仍然为真、可做动作和降级方式；
- **Behavior Evidence**：真实交互、焦点、持久化或响应式结果；
- **Design Proof Bundle**：共同证明一条产品责任的一组证据。

---

# 3. App Shell

## 3.1 Shell 必须持续回答六个问题

1. 我在同一个 Library 的哪个范围；
2. 当前 Primary 是 Library、Group / Topic / Knowledge、Answer、Relation 还是 Source；
3. 我从哪里进入，关闭当前层回到哪里；
4. 当前 revision、placement 和 scope 是否为 Current；
5. Search、Ask、Add 与 Library 怎样到达；
6. 保存、索引、AI、来源和同步有哪些真实状态。

## 3.2 Shell 的语义区域

```text
App Shell
├─ Library return / current scope
├─ Primary scene header
│  ├─ target identity
│  ├─ DepthTrail / scope
│  └─ truthful state
├─ Global actions: Search / Ask / Add
├─ Primary region
├─ optional Companion
├─ optional Inspector / Overlay / Decision
└─ system status / recovery cue
```

这不是布局处方。区域可以被折叠、重排或按设备改为顺序，但语义所有权不变。

## 3.3 Shell 不允许

- 每个 Scene 自己发明一套顶栏；
- Network 成为另一个品牌空间；
- Answer 无法回到发问范围；
- Source Reader 隐藏 Knowledge return；
- Utility 页面拿走 Search / Ask / Add 的全局可达性；
- Back 只依赖浏览器历史而没有产品语义；
- 保存状态用一个图标同时表示 local commit、sync、index 与 AI analysis。

## 3.4 Shell 与视觉

方向 3 + 2 在 Shell 中不是 50 / 50 布局：

- Warm Paper 可以主导 Library、Reading、Answer 与 Source 的阅读区域；
- Relation Night 在 Network / Explore 或 Relation Companion 中出现；
- Global actions、return、identity 和状态跨两种视觉语言保持同义；
- 视觉切换不改变对象 identity 和返回目标；
- 深色空间不能吞掉 Shell 的位置感和可访问文本。

---

# 4. 五个主要 Scene families

## 4.1 Library Scene

Owner：Library Active Appendix。

### Groups view

Primary 顺序：

```text
optional one safe Resume
→ limited explicit Pins
→ exhaustive All Groups
→ secondary Independent / Recent / Saved Views / All Knowledge
```

### Network view

- 同一 Current Groups；
- Current Group Relations；
- scope / selection / filters 与 Groups 可解释映射；
- Graph / List Equivalent；
- zero relation 合法；
- G100 / G1K 要求 scope，不使用全图缩小。

Library scene 不显示：推荐 Feed、AI 自动排序、维护红点墙、全库混合对象星图。

## 4.2 Continuous Reading Scene

Owner：Overview / Reading Active Appendix。

```text
Group Overview
→ Topic Opening
→ Knowledge Paper
→ Section / Claim
→ Evidence entry
```

Reading Primary 需要：

- Boundary / orientation；
- DepthTrail；
- local outline / current section；
- continuous content tree；
- anchorable sections / claims；
- direct edit 与 truthful save state；
- optional Relation / Evidence / History companions；
- exact return。

Reading 默认 Quiet，不因存在 relations、AI suggestions 或 changed sources 自动永久分栏。

## 4.3 Relation Space

Owner：Relation Active Appendix。

四种 presentation：

| Level | Primary | 作用 |
|---|---|---|
| Quiet | Reading / Library | 无额外关系表面 |
| Peek | Reading / Library | 临时检查，不导航 |
| Companion | Reading | 局部关系与 Inspector |
| Explore | Relation | Graph / List / Pair 成为主任务 |

Relation Space 必须可读：

- scope / anchor；
- endpoints；
- statement；
- direction / qualifier；
- formation basis；
- standing；
- Current / Suggested / History；
- Open / Compare / Ask / Back；
- Graph / List 等价。

## 4.4 Answer Scene

Owner：AI Query Active Appendix。

默认顺序：

1. Direct Answer；
2. decisive limits / unknowns；
3. Requested / Effective scope summary；
4. claim-level citations；
5. coverage / exclusions；
6. Route 或 Used Knowledge List；
7. follow-up / branch / re-evaluate；
8. atomic save / write-back actions。

Answer 是 Paper，不是无限气泡流。进入 Evidence / Explore 后关闭必须回到原 Answer Claim。

## 4.5 Source Reader

Owner：Formation Active Appendix。

Source Reader 必须显示：

- Source identity / revision；
- original / snapshot / URL-only / partial representation；
- current locator / fragment context；
- Highlight / Annotation；
- 被哪些 Claims 使用；
- unavailable / changed / parse partial；
- Open original / retry / form knowledge / add evidence；
- 返回 origin Claim / Knowledge / Answer。

连接来源、选择存储策略属于 Utility / Settings，不冒充 Source Reader。

---

# 5. Supporting Utility scenes

## 5.1 All Knowledge

- secondary inventory；
- 同一 Knowledge 一条 identity entry；
- 展开 Placements；
- Independent 是零 active Placements 的 filter；
- 支持 archive、export、duplicate inspection；
- 不成为第三个 Library 主视图。

## 5.2 History

History 分开：

- Knowledge / Overview revisions；
- Relation revisions；
- Source revisions；
- Change Set / formation history；
- Query run / snapshot history；
- workspace activity / Recent。

它们可以在同一 utility 到达，但不能在一条无类型时间线中混义。

## 5.3 Recovery

Recovery 处理未提交、冲突和部分事务：

- Edit Buffer；
- crash checkpoint；
- sync conflict；
- import partial；
- formation pending；
- write failed。

Recovery 不进入 Recent / Resume / All Knowledge，不成为 maintenance Inbox。

## 5.4 Archived / Trash

- Archived 与 Current 分开；
- Trash 显示影响与可恢复性；
- delete shortcut / View / Placement / Resource 分权；
- restore 保留 identity、redirects 与 history；
- permanent delete 需要明确 target 与非级联后果。

## 5.5 Import / Export / Settings

这些 Utility 负责：

- material role；
- partial import / report；
- Knowledge Package；
- local / sync / AI settings；
- Source connection；
- accessibility preferences。

它们不成为产品价值首页，也不要求用户首日配置。

---

# 6. Surface roles

## 6.1 Primary

每个窗口最多一个 Primary。Primary change 只有以下合法来源：

- Open target；
- switch Library view；
- submit Ask → Answer；
- explicit Explore；
- Open Source；
- explicit Utility；
- explicit restore / continue。

hover、focus、selection、Peek、background sync 和 AI suggestion 不改变 Primary。

## 6.2 Companion

Companion eligibility：

- 与 Primary target 有明确 owner / relation / evidence / history link；
- 关闭后可恢复 Primary；
- 不需要独立全局导航；
- 能在窄屏降为可返回 Sheet / sequential surface；
- 不重复已有 Inspector。

desktop 同时最多一个 Companion。多个参考目标用 tabs / list / stacked inspector，不形成三栏控制室。

## 6.3 Inspector

Inspector 可检查：

- Group Boundary / identity；
- Knowledge Placements；
- Relation statement / support / standing；
- Evidence Binding；
- Source metadata；
- revision / history；
- change impact。

selection 改变 Inspector 内容；只有 Open 才改变 Primary。Pin Inspector 是 Workspace state，不创建 Library Pin。

## 6.4 Overlay

Overlay 适合：

- global Search；
- Quick Ask composer；
- Add chooser；
- Command；
- light filter / sort；
- short confirmation。

不适合：

- 长 Answer；
- complex conflict；
- multi-object semantic Diff；
- Source Reader；
- Relation Pair；
- bulk import review；
- history comparison。

## 6.5 Decision / Recovery

至少显示：

- current base；
- proposed / recovered change；
- affected targets；
- what remains unchanged；
- commit / defer / cancel；
- failure isolation；
- undo / history consequence。

Decision surface 同时最多一个，不嵌套 destructive modal。

---

# 7. Global actions 与 task surfaces

## 7.1 Search

```text
origin scene
→ Search Overlay
→ result set / coverage
→ Open exact target
→ Back to same query, filters, scroll, focus
→ close Search returns origin scene
```

Search results 可以进入 Companion / new window，但不自动改变 All Groups membership 或 Ask scope。

## 7.2 Ask

```text
origin scene + requested context
→ Composer Overlay
→ Answer Primary
→ Claim inspect / Evidence / Explore
→ exact Back to Claim
→ close Answer returns origin scene
```

Ask 在提交前显示 requested scope；提交后 Answer 可检查 effective / used context。普通 close 零知识副作用。

## 7.3 Add

```text
origin scene
→ Add chooser
├─ Direct Knowledge
├─ Group
├─ Source
└─ Import
→ truthful commit / partial / cancel
→ return to new asset or origin
```

Add chooser 可以轻量；Direct write、Source save、Formation Preview 和 import recovery 的后果必须分开。

## 7.4 Compare

Compare 从 Group Pair、Relation、Saved View 或 selection 发起：

- 明确两侧 identity / Boundary；
- 使用同一 snapshot；
- Current / Shared / Suggested / History 分层；
- Compare 本身不写入；
- 建立 / 修订 Relation 是独立 Decision；
- closing returns origin selection。

---

# 8. Transition 与 Return Envelope

## 8.1 最小 Envelope

```text
origin_window
origin_scene_family
origin_primary_target
origin_revision
origin_placement
origin_anchor
origin_scroll
origin_focus
origin_selection
origin_filters
origin_presentation
origin_query_claim
return_action
```

并非每次都需要全部字段，但跨对象、跨 Group、Evidence、Search、Ask、Relation 和 History 必须保存足以精确返回的最小集合。

## 8.2 Back、Up、Close、Library

| 动作 | 后果 |
|---|---|
| Back | 回到真实进入来源和现场 |
| Up | 到 canonical owner / parent scope |
| Close Overlay / Inspector / Companion | 回到同一 Primary focus |
| Library | 打开稳定 Library，同时保留可返回 origin |
| Open | 改变 Primary target |
| Peek / Inspect | 不改变 Primary |

## 8.3 不允许的返回

- Evidence close 回到 Knowledge 顶部；
- Explore close 回到 Library 默认；
- Search target close 清空 query；
- Answer citation close 回到 Answer 顶部；
- historical close 静默切到 Current；
- moved Anchor 自动跳到语义相似段落；
- mobile Back 丢失 desktop origin truth。

## 8.4 多窗口

- 每个窗口独立 scene stack；
- Library Pins / Views / Paths 可共享；
- Resume 只取最近安全 committed scene；
- 新窗口默认 Library；
- `在新窗口打开`复制 target / origin link，不复制 Buffer 或 destructive preview；
- 关闭窗口不会覆盖其他窗口的 Resume eligibility。

---

# 9. State families

## 9.1 Universal state matrix

| State | 仍然为真 | 表面责任 |
|---|---|---|
| Empty | canonical scope 存在但无成员 / 内容 | 给真实首要动作，不伪造 demo |
| Loading projection | canonical identity 可读 | 渐进加载，不全屏阻断 |
| Partial | 只有部分派生结果 | 显示 coverage / unavailable set |
| Offline | local truth 可用 | 读写 / browse / export 继续 |
| AI unavailable | knowledge 仍存在 | Search / read / write 不受阻 |
| Index unavailable | canonical catalog 仍可浏览 | 不把零结果当完整 |
| Graph failed | Relations 仍存在 | List Equivalent |
| Source unavailable | Knowledge 仍存在 | 标 Evidence unavailable / locate |
| Write failed | Buffer 仍受保护 | retry / copy / recover，不假保存 |
| Conflict | 两个可识别版本 | diff / preserve / resolve / defer |
| Recovery | 未提交内容受保护 | restore / discard / separate commit |
| Historical | revision 非 Current | 明确 historical / go Current |
| Archived | identity 仍存在 | open / restore / unpin |
| Deleted / tombstone | target 不再 Current | impact / redirect / recoverability |
| Large-scale | truth 超出单视图预算 | summary / list / scope / virtualization |

## 9.2 Scene-specific empty states

- Empty Library：写第一条知识；建 Group / 加 Source 为安静替代；
- Bare Group：写 Boundary / root Knowledge；
- Empty Topic：写 Opening 或 add existing Knowledge；
- zero Relation：诚实无 Current Relation；
- no Search result：说明 coverage，允许改 query / Ask / direct write；
- empty Answer context：personal context empty，不假装基于 Library；
- Source-only：资料保存完成，不强迫形成 Knowledge。

## 9.3 Maintenance budget

全局同时最多一项高影响 notice。以下不主动成为 red badge：

- independent Knowledge count；
- possible relations；
- similar Groups；
- old Sources；
- unused Pins；
- AI proposals；
- unread changes。

阻断任务、存在未提交内容或数据完整性风险时才主动提示。

---

# 10. 披露模型

## 10.1 Calm

只显示完成主任务所需：

- identity / scope；
- primary content；
- one clear main action；
- truthful critical state；
- return。

## 10.2 Focused

用户选中对象或局部任务时增加：

- selection；
- local structure；
- relation / evidence cue；
- Inspector；
- precise actions。

## 10.3 Decision

用户要改变 truth 或结构时增加：

- base / diff；
- impact；
- target；
- commit / defer / undo；
- failure isolation。

## 10.4 Forensic

用户主动核验时增加：

- revision；
- provenance；
- bindings；
- policy / resolver；
- audit trail；
- repair tools。

四层不要求四个页面，也不允许 Forensic 元数据常驻 Calm Library / Reading。

---

# 11. Responsive 与 accessibility equivalence

## 11.1 Desktop wide

- 一个 Primary + 最多一个 Companion；
- Inspector 可叠加但不形成第三主栏；
- Graph 可以空间化；
- Reading 保持可读行宽；
- Shell / return / global actions 稳定。

## 11.2 Compact / tablet

- Companion 转 resizable Sheet / sequential surface；
- Inspector 转 detail overlay；
- Library Catalog 保持优先；
- Graph 默认 focused scope / List；
- filters / sort 可返回，不丢 list position。

## 11.3 Mobile

- 一个 Primary；
- Companion / Inspector 使用顺序导航；
- Network 可完全使用 relation List / Pair；
- Evidence / Source 使用 full surface 并 exact Back；
- Search / Ask / Add 保持分权；
- Library、Open、Continue、Back、Recovery 不消失。

## 11.4 Keyboard

必须区分：

- focus；
- selection；
- expand / collapse；
- inspect；
- open；
- multi-select；
- return。

focus movement 不自动 Open 重型 Scene。Tree、Tabs、Graph List 和 Inspector 使用一致键盘模型；所有隐藏动作有可达等价物。

## 11.5 Screen reader

需要可读：

- current scene / scope；
- heading hierarchy；
- Group / Topic level；
- relation sentence / direction / standing；
- selected vs focused；
- result coverage；
- save / sync / index states；
- opened overlay / dialog；
- exact return announcement。

## 11.6 Motion / zoom / non-color

- 200% zoom 保持任务顺序；
- reduced motion 下取消大幅空间变形；
- color 不单独表达 Current / Suggested / History；
- relation direction 有文本 / shape equivalent；
- focus indicator 不与 selected / active 混淆；
- starfield / texture 可以隐藏而不丢信息。

---

# 12. 完整设计证明模型

## 12.1 五种证据

| Evidence | 能证明 | 不能单独证明 |
|---|---|---|
| Full Frame | hierarchy、visible content、state、actions | 真实行为 / persistence |
| Flow Steps | entry、action、result、return | keyboard / screen reader |
| Component Variants | same responsibility across states | end-to-end journey |
| State / Responsive Matrix | failure、scale、breakpoint responsibilities | visual quality / runtime |
| Behavior Evidence | focus、persistence、return、degradation | 未覆盖的其他状态 |

## 12.2 证据成熟度

| Level | 含义 |
|---|---|
| MISSING | 没有证据 |
| SPECIMEN | 只有视觉方向 / 单一正常态 |
| SEMANTIC | Frame 已表达正确对象、状态和后果 |
| CONTINUOUS | Entry → result → return 有连续证据 |
| EQUIVALENT | responsive、keyboard、List / Graph 等价已证明 |
| VERIFIED | 可运行行为、持久化和失败与合同一致 |

“完整产品设计”至少要求所有核心 Bundles 达到 CONTINUOUS，关键 accessibility / responsive 责任达到 EQUIVALENT；生产完成另需 VERIFIED。

## 12.3 Bundle 最小结构

```text
Bundle ID / owner
User goal
Fixture / scale
Entry
Visible context
Default user copy
Disclosure level
Main action
Result
Failure / partial
Partial / error copy
Recovery
Return
Return copy
Responsive equivalent
Accessibility responsibility
Accessible name
Evidence links
Known limits
```

## 12.4 禁止的完成证明

- “已经有一张相关页面”；
- “七个功能都出现了”；
- “原型可以点击”；
- “组件库里有这些状态名”；
- “桌面正常态看起来合理”；
- “截图没有明显错误”；
- “自动化测试绿了”，但测试没有覆盖产品责任；
- “Graph 有节点和线”，但没有真实 relation semantics；
- “AI 给了答案”，但 scope / basis / write-back 未证明。

---

# 13. 十八个 Design Proof Bundles

| ID | Bundle | 主要 AC | Fixture / scale | 当前 Ardot |
|---|---|---|---|---|
| DPB-01 | Empty Library → first Current Knowledge → reopen | AC-01 / 08 / 09 | C | MISSING |
| DPB-02 | Daily Library：Resume / Pins / All Groups / Open / Continue | AC-01 / 02 / 05 | B / C | Screen 1 冲突 |
| DPB-03 | G100 Catalog / All Knowledge / independent / index partial | AC-01 / 18 / 29 | synthetic | MISSING |
| DPB-04 | Groups ↔ Network same scope / zero relation / list | AC-02 / 15 / 16 | C | Screen 1 / 3 冲突 |
| DPB-05 | Group Overview → Topic Opening → Knowledge | AC-03–06 | A / B | Screen 2 specimen |
| DPB-06 | long Knowledge → Claim → Evidence → exact return | AC-06 / 10 / 17 | A / B | MISSING |
| DPB-07 | same Knowledge multi-Placement / context / edit | AC-07 / 08 | B | MISSING |
| DPB-08 | Quiet → Peek → Companion → Explore → Back | AC-15–17 | B | Screen 2 specimen / behavior conflict |
| DPB-09 | Group Network current / suggested / history / pair | AC-11–16 | A / B | Screen 3 conflict |
| DPB-10 | Search exact Anchor / coverage / Back | AC-18 / 29 | C | MISSING |
| DPB-11 | Ask scope → Answer Claim → citation → Back | AC-19–22 | A / B | Screen 5 specimen |
| DPB-12 | Answer → Explore → Back + atomic write-back | AC-17 / 20 / 23 | A / B | MISSING |
| DPB-13 | direct writing / truthful save / Recovery / History | AC-09 / 28–30 | C | Screen 6 specimen |
| DPB-14 | Source save partial → Reader → Evidence / Formation | AC-25–27 | A / C | Screen 4 / 7 conflict |
| DPB-15 | source revision → local Diff → partial adopt | AC-27 / 28 | A / B | MISSING |
| DPB-16 | offline / AI unavailable / graph failed / index partial | AC-16 / 29 | C / synthetic | MISSING |
| DPB-17 | export / clean restore / missing projections | AC-30 | C | Screen 7 naming only |
| DPB-18 | mobile / keyboard / screen reader / 200% / reduced motion | AC-31 / 32 | A / B / C | MISSING |

## 13.1 Bundle 不是 Screen 数

- DPB-02 可能需要 4 个 Frames + 1 个 state matrix；
- DPB-08 可能需要 Reading Quiet、Peek、Companion、Explore、Back 五步；
- DPB-16 可以用跨 Scene degradation matrix + 关键 Frames；
- DPB-18 需要 responsive variants 与行为注释，不是 18 张手机图；
- 同一个高质量 Frame 可以服务多个 Bundle，但每项证据必须可定位。

## 13.2 Proof index

每个 Bundle 在设计文件或文档中登记：

- status；
- owner contract；
- current frames；
- fixture IDs；
- failure evidence；
- return evidence；
- default user copy 与 disclosure level；
- partial / error copy 与 return copy；
- visible label / accessible name 对照；
- responsive / accessibility evidence；
- known gaps；
- last verified date。

---

# 14. 当前 Ardot 七屏处置

| Screen | 保留 | 替换 / 补齐 | 当前证据等级 |
|---|---|---|---|
| 1 知识主页 | Warm Paper + Relation Night 品牌对比 | Stable Library、All Groups、Resume / Pins、Groups / Network、states | SPECIMEN / CONFLICT |
| 2 双镜工作区 | 方向 3 + 2 视觉母体 | Quiet / Peek / Companion / Explore、真实层级、exact return | SPECIMEN |
| 3 IA 概念星图 | Relation Night 艺术气质 | 删除八对象与 L0 Atlas；真实 Group Network / List / Inspector | CONFLICT |
| 4 采集流 | staged formation 节奏 | Direct Current、Source receipt、partial、Reader、atomic formation | SPECIMEN / CONFLICT |
| 5 回答页 | Answer Paper 阅读气质 | Context、Claim citation、Coverage、Explore、write-back、return | SPECIMEN |
| 6 概览编辑器 | user-owned prose | direct Current、Projection / Reference、Recovery、History、Diff | SPECIMEN |
| 7 来源与存储 | local ownership concern | 降为 Utility；补 Source Reader、representation、revision、impact | SPECIMEN / WRONG LEVEL |

## 14.1 Screen 1 successor

必须先证明 DPB-01–04，不以星图 Hero 为起点。

## 14.2 Screen 2 successor

必须先证明 DPB-05、06、08，以同一真实 Knowledge / Anchor 贯穿。

## 14.3 Screen 3 successor

必须先证明 DPB-04、09，用真实 Group statements、zero relation 与 List Equivalent，不在旧图上换标签。

## 14.4 Screen 4–7

等待其 owner Bundle 的 state / flow 定义后再重做。当前 Frame 可以进入 References / Visual Language 区，不进入完成度计算。

---

# 15. 十六个跨场景压力场景

## SX-01 · cold start 有 safe Resume

应用仍先进入 Library。用户可 Continue，也可普通 Open 同一 Group 从 Overview 开始；两种后果可辨。

## SX-02 · Empty Library direct write

Add Overlay 不强迫建 Group / Source / AI；safe commit 后 Independent / All Knowledge 可再次打开。

## SX-03 · Groups → Network zero relations

同一三个 Groups；Network 诚实零关系，List / Open / Compare 可用，Back 恢复 Catalog selection。

## SX-04 · G100 index partial

All Groups 穷尽 120；Search coverage 93 / 120；AI / index partial 不阻断 Catalog。

## SX-05 · ordinary Group Open

从 Library 打开 G-MEM 进入 Current Overview，不恢复昨日 deep Anchor；Continue 才恢复。

## SX-06 · deep reading to evidence

Overview → Topic → long Knowledge → Claim → Source Fragment；关闭 Source 回原 Claim，不回顶部。

## SX-07 · relation cue ignored

Reading 有关系 cue，用户不打开；页面保持 Quiet，不写 Recent / selection / relation state。

## SX-08 · Peek → Companion → Explore

同一 Relation statement 在三种 presentation 同义；关闭逐级回 origin，identity 不复制。

## SX-09 · graph failed during Explore

Relation truth、scope、selection 不丢；自动进入 List；Back 仍回 Reading Claim。

## SX-10 · Ask from Topic

Requested scope 是 Topic；扩到另 Group 需本次说明；Answer citation → Evidence → Back；关闭 Answer 零写回。

## SX-11 · Answer to Knowledge commit

保存 Snapshot、形成 Knowledge、更新 Anchor、保存 Question、提出 Relation 是不同 Decision；partial failure 只影响目标动作。

## SX-12 · Source parse partial

Source Commit 已成立；AI parse 失败；Source Reader 可打开 original，retry 不撤销 Source；无强迫 Knowledge formation。

## SX-13 · write crash + Resume

Recovery notice 与 safe Resume 同时存在；先保护未提交 Buffer；解决 Recovery 不自动跳 Resume。

## SX-14 · historical deep link

打开旧 revision / Anchor，明确 historical；go Current 与 Back 分开；不静默替换成相似段落。

## SX-15 · mobile relation task

Reading → relation List → Inspector → target → Back；没有空间 Graph 仍完成同一语义任务。

## SX-16 · clean restore without projections

Library / Reading / Relations / Sources / Anchors 成立；Search index、graph layout、Recent / Resume 缺失不算 canonical failure。

---

# 16. 专项验收合同

| ID | Canonical AC | 验收条件 |
|---|---|---|
| SEC-01 | AC-01 | 所有主要 Scene 共用同一 Shell 与 Library return，不产生 Home / Atlas 第二中心 |
| SEC-02 | AC-01 / 02 | Library Groups / Network 是 view change，保留可映射 scope / selection / filters |
| SEC-03 | AC-01 / 05 | cold start / ordinary Open / Continue 后果可见且不混淆 |
| SEC-04 | AC-03–06 | Overview / Topic Opening / Knowledge 是同一 Reading scene family，不是三套页面模板 |
| SEC-05 | AC-06 / 07 | 同一 Knowledge 在 Primary / Companion / Inspector 不复制 Current content |
| SEC-06 | AC-07 / 08 | multi-Placement open 显示 context，删除一个 Surface / Placement 不误删 Knowledge |
| SEC-07 | AC-09 | Buffer / Current / Recovery / Draft / Proposal / Sync 的表面状态分权 |
| SEC-08 | AC-10 / 17 | Evidence / Relation / Search / History / Resume 通过 Return Envelope 精确返回 |
| SEC-09 | AC-11 / 12 | Graph / List / Inspector 使用同一 Relation statement，连接类型不混边 |
| SEC-10 | AC-13 / 14 | exit / shared observation 只在正确 Surface 表达，不冒充 Current Relation |
| SEC-11 | AC-15 | ordinary Library / Reading 为 Quiet；关系只因显式意图增长 |
| SEC-12 | AC-16 | Graph failed / mobile / keyboard 使用同义 List 完成选择、检查、打开和返回 |
| SEC-13 | AC-18 | Search Overlay、result、direct Anchor 与 Back 构成连续证据 |
| SEC-14 | AC-19 | Ask 提交前 Requested、提交后 Effective / Used context 可检查 |
| SEC-15 | AC-20 | Answer Claim → Knowledge / Source → Back 精确，不用底部来源卡代替 claim mapping |
| SEC-16 | AC-21 | Coverage / unknown / unavailable 在 Calm / Focused 层清楚，不用 confidence 替代 |
| SEC-17 | AC-22 | close / retry / follow-up / recovery / Snapshot 不自动改变 Current Knowledge |
| SEC-18 | AC-23 | 每次写回只有一个 target / action / result；Decision surface 显示影响与失败隔离 |
| SEC-19 | AC-24 | runtime unknown 不自动生成 Inbox / badge / Review surface |
| SEC-20 | AC-25 | Source Commit、parse、Reader、Formation 使用连续但分权的 surfaces |
| SEC-21 | AC-26 | Candidate reject 零副作用，Proposal 不因出现在 Inspector 就成为 Current |
| SEC-22 | AC-27 | Source change 先显示 affected Claim / local Diff，不整页自动重写 |
| SEC-23 | AC-28 | restore old revision 形成新 Current，History / Recovery / Query history 不混线 |
| SEC-24 | AC-29 | offline / AI / index / graph failure 时 Primary knowledge 仍可读写和浏览 |
| SEC-25 | AC-30 | clean restore 不依赖 projections；missing workspace state 讲真话 |
| SEC-26 | AC-31 | desktop / compact / mobile 保持 Library、Reading、Answer、Relation、Source 的核心责任 |
| SEC-27 | AC-32 | keyboard 区分 focus / selection / inspect / open；所有核心动作可达 |
| SEC-28 | AC-32 | screen reader 可读 scene、scope、hierarchy、relation sentence、coverage 和 state changes |
| SEC-29 | AC-31 / 32 | 200% zoom / reduced motion / non-color 不丢任务顺序和语义 |
| SEC-30 | AC-01–32 | 每个 DPB 有 owner、fixture、entry、result、failure、return 与证据链接 |
| SEC-31 | AC-01–32 | Visual Specimen 不被计为 CONTINUOUS / EQUIVALENT，静态证据边界明确 |
| SEC-32 | AC-01–32 | 当前 Ardot 七屏不再作为完整度分母；只有 Bundle coverage 可以宣布设计完成 |

---

# 17. 外部模式与产品推论

## 17.1 Capacities：同一对象可以有 full page、preview 与 side panel

[Capacities Navigation](https://docs.capacities.io/reference/navigation)区分同一对象的 full-page、preview modal、side panel 与 tabs，并让 breadcrumbs / side-panel state 随工作环境保持。

**产品推论：**Surface role 不应复制对象。同一 Knowledge / Source / Relation 可以被快速检查、并列参考或完整打开；Focus、Inspect 与 Open 需要不同后果。但本产品不复制 Capacities 的对象类型中心与多个 spaces。

## 17.2 Capacities：Graph 以当前对象为锚，并有列表替代

[Capacities Graph View](https://docs.capacities.io/reference/graph-view)明确 Graph 围绕一个当前对象展开，并用 backlinks / related content list 提供列表表达。

**产品推论：**Relation Space 需要 anchor、scope 与 List Equivalent；全局混合对象星图不是完整表面。该模式不直接证明本产品只能有局部图，因此 v6 仍保留以 Groups 为 resting level 的 Library Network。

## 17.3 Apple：Modal 只适合有明确收益的聚焦任务

[Apple HIG Modality](https://developer.apple.com/design/human-interface-guidelines/modality)把 modal 描述为暂时阻断 parent、要求显式结束的专注体验，并提醒避免无明确收益和多层 modal。

**产品推论：**Quick Search / Ask / Add 可以短暂 Overlay；long Answer、complex conflict、bulk import 与 Relation Pair 不应被塞进轻量弹层。产品是否使用具体 sheet / popover 仍属于视觉与平台选择。

## 17.4 WAI-ARIA：Focus、selection 与 activation 必须分开

[WAI-ARIA Tree View Pattern](https://www.w3.org/WAI/ARIA/apg/patterns/treeview/)明确 focus 与 selected state 可以不同，并定义 expand / navigation / activation；[Tabs Pattern](https://www.w3.org/WAI/ARIA/apg/patterns/tabs/)也区分 focus 与 activation，并要求 active tab / panel 语义关联。

**产品推论：**Topic tree、Catalog、Tabs、Graph List 和 Inspector 必须区分“我移动到这里”“我选中它”“我检查它”“我打开它”。视觉上有焦点框不等于可访问性已经完成，仍需运行验证。

## 17.5 研究没有证明什么

外部模式没有证明：

- 本产品应采用固定侧栏、tabs 或 modal；
- 一个 desktop 布局适合所有设备；
- Graph 应完全局部或完全全局；
- DPB-01–18 已经通过真实用户验证；
- 当前 42 项决定是不可反转的最终答案；
- 静态设计可以证明 WCAG 合规；
- 当前 Ardot 的品牌风格已经验证可读性与长期使用。

研究只支持责任分离、锚定、focus / selection 分权和证据边界；具体视觉仍需 fixture 与可用性测试。

---

# 18. 与相邻现行合同的边界

| Contract | 它拥有 | 本合同拥有 |
|---|---|---|
| Library | Catalog、Resume / Pin / Recent、Open / Continue | Library scene 与跨 Scene Shell / proof |
| Hierarchy | Group / Topic / Placement / Saved View truth | Reading surface continuity / proof |
| Reading | Overview / Knowledge / Anchor / edit / History | Primary / Companion / Inspector roles |
| Relation | Relation statement / standing / Graph / List / return | Relation scene family / transition evidence |
| Query | Search / Ask / Answer / Context / Claim support | Overlay → Answer → Evidence / Explore surface chain |
| Formation | Add / Source / Annotation / Binding / Proposal / import | Source / task / decision surface chain |
| User language | 一个`知识库`、五个日常概念、三个全局动作、copy / disclosure / accessible naming | 在 Scene / Surface / DPB 中承载并定位语言证据 |

本文不重新定义任何 canonical resource、relation lifecycle 或 formation transaction。

---

# 19. 进入视觉设计前的 Gate

必须满足：

1. 用户确认或反对 v6 / Decision Companion 的推荐默认；
2. 用户确认当前七屏只作 Visual Specimen，不作产品结构；
3. DPB-01–18 的 owner、fixture、required states 与 return 已冻结；
4. DPB-01–18 已登记 default、partial / error、return copy、disclosure level 与 accessible name，并映射 LAC-01–LAC-32；
5. Screen 1 successor 先证明 DPB-01–04；
6. Screen 2 successor 先证明 DPB-05 / 06 / 08；
7. Screen 3 successor 先证明 DPB-04 / 09；
8. 使用真实 fixture，不使用抽象星点、短笔记、占位文案或伪统计；
9. 先提取无视觉风格的 Surface Skeleton；
10. 再生成恰好三种视觉目标；
11. 用户选择后才制作完整 Frame family；
12. clickable prototype 在关键 Frames 与 states 被接受后再开始；
13. 当前 Ardot 不通过补按钮或换文案继续累积设计债。

---

# 20. 产品设计完成定义

设计只有同时满足以下条件才可称完整：

- 五个主要 Scene families 和 supporting utilities 共享一个 Shell；
- Search / Ask / Add 有清楚入口、结果、失败和返回；
- 用户表面稳定使用一个`知识库`、五个日常内容概念与三个全局动作；内部 Scene / Surface / Current / Placement 不成为默认用户术语；
- DPB-01–18 均至少达到 CONTINUOUS；
- DPB-01–18 均有真实 default、partial / error、return copy、disclosure level 与 accessible name，并通过 LAC-01–LAC-32；
- DPB-04 / 08 / 16 / 18 达到 EQUIVALENT；
- 三份真实 fixture 与 synthetic scale 贯穿，而不是每屏换一套假数据；
- Empty / partial / offline / conflict / recovery / historical / large-scale 有明确证据；
- desktop / compact / mobile 不删除核心责任；
- keyboard / screen reader / zoom / reduced motion / non-color 路径有可定位证据；
- Workspace state、Projection、Proposal、Current 与 History 没有混淆；
- Graph / List、Open / Continue、Focus / Inspect / Open、Back / Up 没有混淆；
- 当前七屏的错误产品模型没有残留在新 Surface Skeleton；
- 每项完成声明都能定位到真实 evidence，而不是依赖设计者解释。

---

# 21. 最终判断

这个产品的完整表面不是七个页面，而是一条可以持续回来的知识道路：

```text
Stable Library
→ choose a Group or Continue
→ Overview / Topic / Knowledge / Claim
→ inspect Evidence or Relation
→ Ask / Explore when needed
→ form an explicit change if valuable
→ exact return
→ recover after time, failure and scale
```

方向 3 给这条道路层级、连续阅读和安静重力；方向 2 在需要关系时给它空间、比较与跨越。App Shell、Return Envelope、state families 和 Design Proof Bundles 让两种视觉真正成为同一个产品，而不是两张并排的漂亮图。
