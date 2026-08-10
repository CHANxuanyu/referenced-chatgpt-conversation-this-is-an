# AI-native 个人知识库

## 关系、群级网络与探索连续性合同 v1.0

> 日期：2026-08-10  
> Status：**ACTIVE_APPENDIX**  
> Canonical：AI-native-个人知识库-终局产品设计文档-v6.0.md  
> 深化范围：v6 §7 Relation 与知识网络、§11.1–11.6 方向 3 + 2、§12.8–12.9 关系旅程、AC-11–AC-17，以及 AC-20、AC-23、AC-31、AC-32 的关系侧责任  
> 相邻现行合同：知识群层级、目录规模与结构演化合同；AI 查询、知识探索与返回连续性合同；知识进入、来源保存与知识形成合同；`AI-native-个人知识库-Overview、连续阅读与知识正文合同-v1.0.md`拥有作为关系起点与返回目标的 Overview / Knowledge content、Anchor、revision 与 reading scene；`AI-native-个人知识库-Library入口、目录浏览与继续阅读合同-v1.0.md`拥有 Groups / Network 入口切换、cold start、Catalog scene 与 Resume / Pin / Recent / Saved Path 分权  
> 表面责任边界：`AI-native-个人知识库-表面架构、场景家族与完整设计证明合同-v1.0.md`拥有 Quiet / Peek / Companion / Explore 的 Surface roles、Graph → List 降级、Return Envelope 与 DPB；本文拥有 Relation statement、standing、scope 与 graph/list 同义真相  
> 用户语言边界：`AI-native-个人知识库-用户可见信息架构、产品语言与复杂度披露合同-v1.0.md`拥有完整关系句、查看 / 打开 / 探索动作、Current / Suggested / Past 与 Graph / List 的用户表达；本文只拥有 Relation truth  
> 真实压力来源：Fixture A 的跨群出口负例、Fixture B 的同 pair 双关系与 Shared Knowledge、Fixture C 的零关系与 Graph unavailable  
> 当前设计证据：Ardot Screen 2「双镜工作区」、Screen 3「IA 概念星图」及现有关系审计截图  
> 本轮边界：只定义产品；不修改 Ardot、不制作新 Frame、不制作点击原型

---

# 0. 执行结论

这个产品的知识网络必须满足一条最严格的边界：

> **图上看见的线，只能是已经成立的 Relation 的投影；不能因为两个对象相似、被一起访问、共享来源或存在可走路径，就把它们画成一条知识关系。**

方向 3 + 2 也不是两张画面的平均混合：

- 方向 3 是默认知识形态：Overview → Topic → Knowledge → Anchor / Evidence；
- 方向 2 是用户明确需要比较、迁移或追问联系时才展开的关系空间；
- 两者共享对象 identity、selection、scope、history 与 return；
- 关系空间可以成为当前主任务，但永远不取代知识正文；
- 普通打开永远回到安静阅读，不把上次打开过的图强行恢复。

本合同冻结三十六项产品决定：

1. **Relation 是一条可独立阅读、核验、修订和结束的陈述；Graph edge 只是投影。**
2. **正式 Relation 只连接同层 Knowledge ↔ Knowledge 或 Group ↔ Group。**
3. **Structure、Evidence、Semantic Relation、Reference 与 Runtime Route 五类连接不混边。**
4. **个人判断可以没有外部来源，但 formation basis 与 evidence condition 必须诚实。**
5. **用户直接写出的完整关系经提交后就是 Current Relation，不需要采用自己的判断。**
6. **AI、相似度、共同来源、路径聚合和来源抽取只能先形成 Candidate。**
7. **Candidate 不是 Relation，不进入 Current Network、Ask truth、degree、Overview 或 History。**
8. **拒绝 Candidate 零知识副作用，并抑制没有新依据的重复建议。**
9. **方向、时间、范围、人群、条件与比较维度属于 Relation 的意义，不是装饰 metadata。**
10. **增减 Evidence 不制造语义 Revision；陈述或限定改变才产生 Relation Revision。**
11. **同一 endpoint pair 可以拥有多条不同 Relation；Bundle 只折叠展示，不合并 identity。**
12. **Inverse reading、对称镜像和布局中的重复线不创建第二份 Relation truth。**
13. **无法说清为什么相关时，保留 Reference、Exit 或 Candidate，不建立万能 related-to。**
14. **Cross-group exit 只说明可以走过去，不自动升级为 Group Relation。**
15. **同一 Knowledge 在两个 Groups 的 Placement 只形成 Shared Knowledge Observation，不形成群关系。**
16. **Group Relation 必须能对两个 Group 整体或明确 named subscope 说出一句成立的话。**
17. **系统主动提出群关系前，必须检查支撑独立性、Boundary coverage、类型适配、反例与最强支撑移除结果。**
18. **路径数量、共同标签、相似度、degree 和 confidence 不能弥补任何一个失败门槛。**
19. **没有正式关系是完整、合法、可长期保持的知识库状态。**
20. **Pair Comparison 是临时比较现场，不是新资源，也不会因打开而创建任何 Relation。**
21. **Current、Suggested 与 History 是不同层；Suggested 和 History 不污染默认 Network。**
22. **Library Network 的 resting level 只显示 Groups 与 Current Group Relations。**
23. **不存在把 Group、Topic、Knowledge、Source、Answer 和 Query 节点混铺的全局万能图。**
24. **Quiet / Peek / Companion / Explore 表达注意力强度；R0–R3 表达关系半径，二者正交。**
25. **普通 Library、Group、Topic、Knowledge、Search result 或 supporting Knowledge open 都从 Quiet 开始。**
26. **Inspect 只检查，不改变 Reading Target；Open 才改变目标并写入 Return Envelope。**
27. **Graph、List 与 Inspector 必须读取同一 scope、selection、filter、statement、standing 与动作后果。**
28. **跨群探索必须精确返回 origin object、Anchor、scroll、focus、selection 与 relation scene。**
29. **Viewport / scene、Exploration Trail、Return Stack 与 Saved Path 是不同状态。**
30. **Query Route 解释本次回答怎样找到依据，不自动成为 Relation 或 Saved Path。**
31. **高密度 Network 先收窄 scope、显示总量与隐藏原因，并提供穷尽 List；不静默截取 AI Top N。**
32. **Graph layout 失败时自动使用 List Equivalent；关系真相不依赖布局缓存。**
33. **Current、needs check、ended、superseded、retracted 与 archived 的意义分开。**
34. **Group / Knowledge split、merge、redirect 或删除不能静默复制、换端或改写 Relation。**
35. **Desktop、compact、mobile、keyboard 与 screen reader 必须能完成同样的关系判断和返回。**
36. **Export / Restore 保存 Relation identity、Revision、qualifiers、basis、standing、history 与 redirects，不依赖视觉坐标。**

---

# 1. 产品问题：一张图不等于知识网络

## 1.1 当前设计最危险的错觉

Screen 2 与 Screen 3 已经找到对的气质：

- 温暖阅读面适合纵向理解；
- 深色空间适合横向探索；
- 两种气质之间有明显模式差。

但当前截图仍然容易让用户产生三个错误判断：

1. **看见一条线，就以为系统知道两端为什么相连；**
2. **看见很多节点，就以为知识库已经形成丰富结构；**
3. **看见中心节点或粗线，就以为它更重要或更可信。**

如果没有 statement、direction、qualifiers、basis、standing、scope 与 return，这些线首先是视觉素材，不是产品对象。

## 1.2 关系产品真正回答的五个问题

每一次关系探索都必须让用户回答：

1. 我现在以哪个对象为锚点？
2. 两端究竟以什么方式相连？
3. 这句话在什么范围、条件与时间下成立？
4. 它是当前知识、系统建议、可走路径，还是历史关系？
5. 我打开另一端以后，怎样准确回到刚才的理解现场？

不能回答其中任何一项时，产品都不应只靠节点位置、线型、颜色或数字补偿。

## 1.3 产品成功不是图更密

以下指标不构成产品成功：

- Relation 数量；
- 每日新增边数量；
- 图谱密度；
- 平均 degree；
- AI Candidate 接受率；
- 用户在图上的停留时长；
- 视觉上是否形成漂亮星群。

更接近真实成功的结果是：

- 用户能复述一条关系，而不是只记得两点相连；
- 用户能区分 Current、Suggested、Exit 与 History；
- 用户能从阅读进入探索，并回到原 Anchor；
- 同一 pair 的多条关系不会被压成“相关”；
- 无关系、关系很少或关系很多时，产品都诚实可用；
- AI 与布局不可用时，长期关系仍可读、可维护、可导出。

---

# 2. 五类连接与两种正式 Relation

## 2.1 五类连接必须分权

| 连接 | 回答的问题 | 是否正式 Relation | 是否默认画成 semantic edge |
|---|---|---:|---:|
| Structure | 这个对象位于什么范围与层级 | 否 | 否 |
| Evidence | 哪段来源支持或限制哪条 Claim | 否 | 否 |
| Semantic Relation | 两份理解或两个知识范围为什么相连 | 是 | 是，满足当前投影条件时 |
| Reference / Exit | 从这里可以去哪里继续看 | 否 | 否，可作为导航 cue |
| Runtime Route | 本次 Search / Ask 怎样找到这些对象 | 否 | 否，只在本次 Route 中显示 |

同一对对象可以同时拥有多类连接。例如：

- Knowledge A 在 Topic X 中拥有 Structure connection；
- Source Fragment S 支持 A 的一条 Claim；
- A 与 Knowledge B 有正式 Relation；
- 本次 Ask 又通过 retrieval jump 使用了 A 和 B。

界面必须分别表达，不能把四条线合并成“相关”。

## 2.2 Knowledge Relation

Knowledge Relation 连接两份可独立阅读的 Knowledge。

它回答：

> 这两份理解之间，存在什么可长期维护的支持、限定、延伸、应用、实例或比较关系？

Section、Block、Anchor 可以解释局部参与位置，但不成为 Relation endpoint。若某一局部内容需要长期拥有自己的关系，先将它提升为独立 Knowledge。

## 2.3 Group Relation

Group Relation 连接两个拥有独立 Boundary 与 Overview 的 Knowledge Groups。

它回答：

> 基于两群当前边界，我们愿意长期维护哪一句关于这两个知识范围整体关系的判断？

它不是底层边的汇总线，不改变 Group ownership、Topic 结构、Placement 或删除语义。

## 2.4 不成为普通 Relation endpoint 的对象

以下对象不进入 ordinary semantic relation layer：

- Topic；
- Source / Fragment；
- Evidence Binding；
- Answer / Answer Claim；
- Question lifecycle state；
- Placement；
- Saved View；
- Saved Path；
- Search result；
- Query Route step；
- Change / Review record。

它们可以与 Relation 发生 supporting、origin、impact 或 navigation connection，但不伪装成同一种边。

---

# 3. Relation statement：先是一句话，再是一条线

## 3.1 最小陈述合同

一条 Current Relation 至少拥有：

| 部分 | 用户需要知道什么 |
|---|---|
| From / To | 哪两个 Knowledge 或 Groups |
| Relation phrase | 以什么方式相连 |
| Full statement | 一句可独立阅读的自然语言陈述 |
| Direction / inverse | 从另一端如何准确读 |
| Qualifiers | 时间、条件、人群、范围、比较维度或 named subscope |
| Why it matters | 为什么值得在网络中维护 |
| Formation basis | 用户直接判断、来源明确陈述、导入或 AI 聚合建议 |
| Evidence condition | 当前有哪些可核验依据，或暂无外部依据 |
| Standing | Current、needs check 或 historical disposition |
| History | 何时建立、修订、结束、替代或撤回 |

## 3.2 自然语言优先

默认首先显示完整中文关系句，而不是 predicate key：

> 记忆机制为学习策略提供理论基础，尤其用于解释为什么提取练习与间隔安排有效。

从另一端阅读时：

> 学习策略建立在记忆机制的部分理论基础之上，主要涉及提取与间隔。

两个读法解析到同一个 Relation identity。不能因为换了阅读方向，就生成镜像边。

## 3.3 六个意图家族

主产品继续使用 v6 的六个用户意图，不把旧 25 + 11 类型表暴露为必填分类：

| 意图 | 用户想表达什么 | 最低限定 |
|---|---|---|
| Support / Explain | A 怎样支持或解释 B | 被支持或解释的方面 |
| Challenge / Qualify | A 在哪里限制、反驳或修正 B | 重叠 Applicability 与限制范围 |
| Extend / Refine | A 怎样补充或细化 B | 新增的机制、条件或粒度 |
| Apply / Implement | A 怎样被用于具体问题 | 适用场景；真实采用与潜在适用分开 |
| Example / Instance | A 怎样作为 B 的例子或实例 | 分类或实例化依据 |
| Compare / Contrast | 两端在哪些维度相同或不同 | 共同比较维度 |

如果用户只能说“它们好像相关”，产品提供：

- 普通 Reference；
- Cross-group exit；
- 暂存 Candidate；
- 继续 Compare / Ask；

但不强迫选择一个虚假的正式类型。

## 3.4 Qualifier 是意义的一部分

以下变化必须建立语义 Revision：

- “适用于所有学习者”收窄为“适用于已经具备基本先验知识的成人学习者”；
- “A 支持 B”改为“A 只在低认知负荷条件下支持 B”；
- “2024 年规则约束流程”结束为“截至 2024 年底有效”；
- 比较维度从“成本”改为“学习迁移”；
- Group Relation 从整群收窄为一个 named subscope。

只补充一份来源、修正引用定位或增加说明文字，不建立新的 Relation Revision。

## 3.5 同 pair 多关系

同一 Knowledge pair 或 Group pair 可以存在多条真正不同的 Current Relations。

Fixture B 中“记忆机制 → 学习策略”至少同时存在：

1. 提供理论基础；
2. 提供实际设计方法。

两条关系拥有不同 statement、why it matters、support 与 lifecycle。Graph 可以显示一个 bundle：**当前有 2 条关系**；展开后必须逐句阅读，不能合并为“强相关”。

---

# 4. 直接建立、AI Candidate 与拒绝

## 4.1 用户直接建立

用户从两个已选对象、Pair Comparison 或阅读现场写出完整关系时：

1. 选择或确认 endpoints；
2. 写出完整 statement；
3. 检查方向与 inverse reading；
4. 补充必要 qualifier；
5. 可选添加 Evidence；
6. 预览 Network / Ask / Overview 的后果；
7. 提交为 Current Relation。

产品不要求用户再“接受自己的关系”。如果没有外部 Evidence，可以显示：

> 这是你的当前判断；尚未添加外部依据。

不能把个人理解降格为 Candidate，也不能伪称证据充分。

## 4.2 系统只能提出 Candidate

以下信号只能形成 Candidate 或更低层 observation：

- embedding similarity；
- 共同关键词、标签或来源；
- 同一 Answer 同时使用；
- 多次共同访问；
- Graph layout proximity；
- Cross-group exits；
- 来源中检测到关系表达；
- trusted import 中已有 predicate；
- 多条底层 Relations 的聚合。

Candidate 必须能回答：

- 建议的完整 statement；
- 为什么是这个意图和方向；
- qualifiers / named scope；
- formation basis；
- supporting paths 与去重结果；
- CounterSignals / limits；
- 接受后会改变什么；
- 拒绝后不会改变什么。

## 4.3 Candidate 不是半条 Relation

Candidate 在采用前：

- 不拥有 Current Relation standing；
- 不进入默认 Graph / List；
- 不被 Ask 当作 Library truth；
- 不影响 endpoint degree；
- 不投影到 Overview；
- 不产生关系 History；
- 不被计入“当前关系数量”。

Suggested layer 是用户明确打开的检查层。关闭后，Current layout 必须与打开前一致。

## 4.4 采用

采用 Candidate 时，原子建立：

- Relation identity；
- 首个 Relation Revision；
- formation basis；
- 用户确认或修改后的 statement；
- qualifiers；
- Evidence / support snapshot；
- adoption event。

不能把 Candidate 自己改名成 Current Relation，以免拒绝记录、系统生成内容与用户知识混成一个对象。

## 4.5 拒绝与抑制

拒绝后：

- 不产生 Relation；
- 不改变 Current Network；
- 不改 Overview；
- 不删除真实 exits；
- 不影响未来 Search / Ask；
- 保存低成本 suppression fingerprint。

只有出现新 statement、不同 qualifiers、新独立依据或 endpoint Boundary 实质变化时，系统才可以重新提出。

“布局重新计算”“多了一次共同访问”“同一来源增加一段摘录”不构成新依据。

---

# 5. 从跨群出口到 Group Relation

## 5.1 四个层级

| 层级 | 含义 | 是否进入 Current Network |
|---|---|---:|
| Cross-group Exit | 一条具体 Knowledge path 可以走到另一 Group | 否 |
| Aggregation Signal | 系统观察到可能值得综合的模式 | 否，默认不暴露 |
| Group Relation Candidate | 已形成完整群级 statement，等待判断 | 只在 Suggested layer |
| Current Group Relation | 用户直接声明或明确采用 | 是 |

这四层不能只用线的虚实、透明度或粗细区分。

## 5.2 用户直接群关系

用户可以不经过系统聚合门槛，直接建立自己的 Group Relation，但仍必须完成：

- 两个 Groups；
- 完整群级 statement；
- direction / inverse reading；
- 整体范围或 named subscope；
- why it matters；
- 可选 Evidence；
- 回读确认。

系统聚合门槛约束的是**AI 什么时候有资格打扰用户**，不是限制用户表达。

## 5.3 系统主动建议资格

系统主动提出 Aggregated Group Relation Candidate 前，依次检查：

1. **完整群级陈述**：不是“两个群有关”，而是一句可整体阅读的话；
2. **类型适配**：支撑形状真的符合 Support、Apply、Compare 等意图；
3. **支撑独立性**：折叠同一 Knowledge 的多 Placements、同一来源 lineage、inverse duplicate 与重复 traversal；
4. **Boundary coverage**：触及两侧核心、一个核心与明确扩散，或一个 named subscope；
5. **方向一致**：底层 paths 支持同一方向与 inverse reading；
6. **Applicability 一致**：时间、人群、范围和条件没有被混成多数票；
7. **CounterSignals**：同范围的反例、限制与相反路径已检查；
8. **最强支撑移除**：移除唯一最强 unit 后，陈述是否仍值得升到群级；
9. **用户采用**：全部通过也只允许提出，不允许自动成立。

系统聚合 Candidate 默认至少需要两个去重后的 Effective Support Units。来源明确写出群级关系时，可以凭一条 explicit source statement 形成 source-asserted Candidate，但必须明确它是“来源的陈述”，而不是系统已证明的 Library truth。

## 5.4 Boundary coverage 的普通语言

内部可以计算 coverage footprint，但用户只需要看到：

- 两个群的核心问题都被支撑；
- 一侧核心与另一侧多个部分相连；
- 只适用于明确子范围；
- 目前只触及边缘内容；
- 当前无法判断覆盖。

“只触及边缘”与“无法判断”不能进入主动 Suggested layer。它们保留为 exits，并在用户主动 Compare / Ask 时解释。

## 5.5 失败后的诚实落点

如果群级门槛没有通过：

- 真实 Knowledge Relations 保留；
- Cross-group exits 保留；
- Pair Comparison 仍可显示 shared Knowledge 与 paths；
- Ask 仍可解释“当前发现了哪些具体联系”；
- Library Network 不画 Group edge；
- 不制造“还差两条关系即可升级”的整理债务。

没有群关系不是缺失状态。

## 5.6 支撑变化

Current Group Relation 的底层 supporting paths 变化时：

- 不自动消失；
- 不退回 Candidate；
- 更新 support snapshot；
- 若意义或覆盖可能改变，标记 needs check；
- Ask 使用时说明当前限制；
- 用户选择 Maintain、Revise、End、Supersede、Retract 或 Defer。

系统建议资格与已经采用后的维护门槛不同，不能因为支撑减少就自动撤销用户知识。

---

# 6. Shared Knowledge 与 Pair Comparison

## 6.1 Shared Knowledge 只是一种观察

同一 Knowledge identity 在两个 Groups 都有 active Placement 时，Pair 可以显示：

> 两个知识群共享 3 条同一知识。

这不会：

- 创建 Relation；
- 增加 relation count；
- 改变 resting Network layout；
- 触发 Adopt；
- 形成新的 Knowledge 副本。

关闭 Shared Lens 后不留下 edge。

## 6.2 Pair Comparison 的产品身份

Pair Comparison 是一次 Workspace State：

- 比较对象固定为两个 Groups；
- 使用一致的 Boundary / Overview / Relation snapshot；
- 打开不写知识；
- 关闭后恢复 origin；
- 可以从 Library Network、Group exit、Relation Inspector、Ask Claim 或 Search result 进入。

比较三个以上 Groups 时使用 Ask compare、Saved View 或逐对比较；不把 Pair 扩展成矩阵产品。

## 6.3 Pair 的信息顺序

默认顺序：

1. **Orientation**：两群各自 Boundary、Overview 与当前 snapshot；
2. **Current Relations**：逐句显示同 pair 当前正式关系；
3. **Shared Knowledge**：同一 identity 的动态观察；
4. **Concrete Paths**：具体 Knowledge Relations、Placements 与 exits；
5. **Suggested / Unknown**：只有用户主动打开才显示；
6. **Evidence & Limits**：support、counterexamples、unavailable source；
7. **History**：ended、superseded、retracted 与旧 snapshot。

不能先用一个 AI 相似度分数总结两群。

## 6.4 Pair 内的 Ask

Pair Ask 的 Requested Context 是两个 Groups。回答必须显示：

- Requested / Effective / Used Context；
- 每个 Group 的 coverage；
- 使用了哪些 Current Relations；
- 哪些只是 shared observation、exit 或 runtime co-use；
- 没有正式 Group Relation 时，明确写“当前只有具体路径，尚无群级关系”。

回答不自动建立 Relation。建立建议是另一个显式、原子动作。

## 6.5 Pair exact return

从 Knowledge K 的 basis Anchor 进入 Pair 时，关闭必须恢复：

- K identity 与 Revision；
- 原 Group / Topic Placement context；
- Anchor 与 scroll；
- focus target；
- selected support path；
- 原 relation presentation / radius；
- Ask scope（若来自 Answer Claim）。

Pair 内的临时 filters 不泄漏回 Reading，除非用户显式保存为 Scene / View。

---

# 7. 关系注意力与关系半径

## 7.1 两个正交维度

### Presentation / 注意力强度

| 模式 | 谁是 Primary | 进入条件 | 关闭后果 |
|---|---|---|---|
| Quiet | Reading / Library task | 普通打开 | 无额外关系状态 |
| Peek | 当前 Reading | 明确 Inspect 一条关系或 endpoint | 回触发点，不改目标 |
| Companion | Reading | 明确“查看相关知识” | Reading 仍为主，最多一个 Companion |
| Explore | Relation Space | 明确“在网络中探索” | Back / Close 恢复 origin |

### Radius / 看多远

| 半径 | 含义 |
|---|---|
| R0 | 不主动显示图；只保留安静 cue 或 List entry |
| R1 | 当前 Knowledge / Group 的直接正式关系 |
| R2 | 一条有解释的多步路径或 Pair context |
| R3 | Library Group Network |

Presentation 不决定 Radius，Radius 也不决定当前主任务。

例如：

- 用户可以在 Peek 中检查一条 R3 Group Relation；
- 可以在 Explore 中只看 R1 当前 Knowledge；
- Companion 可以在 R1 与 R2 之间显式切换；
- ordinary open 即使上次停在 R3 Explore，也回到 Quiet。

## 7.2 Quiet 是确定的默认

以下行为不能自动打开关系面：

- 打开 Library、Group、Topic 或 Knowledge；
- Search 打开 result；
- Ask 打开 supporting Knowledge；
- hover、keyboard focus、text selection 或 scroll；
- AI 生成 Candidate；
- 后台重新布局；
- 上次曾打开过 Companion。

只有显式 Continue 一个安全保存的 exploration scene，才可以恢复 Explore。

## 7.3 Peek：检查而不导航

Peek 至少显示：

- relation statement；
- endpoints；
- direction / inverse reading；
- qualifiers；
- standing；
- why it matters；
- Open / Compare。

关闭 Peek 恢复触发前 focus。Hover 只能高亮，不得打开 Peek、写 Recent 或改变 Selection owner。

## 7.4 Companion：阅读仍为主

Companion 的责任：

- 跟随用户显式打开的 Relation / related Knowledge；
- 显示有限 R1 或解释过的 R2；
- 保持正文和当前 Anchor 可读；
- 选择一条 Relation 先 Inspect；
- 只有明确 Open target 才改变 Reading Target；
- 同一 Workspace 最多一个关系 Companion。

窄屏时 Companion 变为可关闭 sheet / sequential surface，而不是把正文和图同时压缩。

## 7.5 Explore：关系成为当前任务

Explore 必须显示：

- scope 与 anchor；
- presentation / radius；
- current selection；
- filters；
- visible / total counts；
- Current / Suggested / History layer；
- Graph / List switch；
- origin summary 与 Back；
- Inspector；
- empty / partial / dense / layout failed 状态。

Explore 中 pan、zoom、filter 和 expand 只改变 scene，不写知识历史。

## 7.6 Relation deep link

普通 Relation deep link 默认进入 relation-focused Peek，解释这一条关系。

只有以下链接可以直接恢复 Explore：

- 明确保存的 Network Scene；
- Saved Path 的显式 Continue；
- 用户自己复制的带 scene state 链接；
- 安全可恢复的 Resume。

产品不能从一个 relation_id 猜测用户想看哪张全局图。

---

# 8. Library Network：群级网络不是全对象星图

## 8.1 Resting level

Library Network 只包含：

- Current Groups；
- Current Group Relations；
- selected / pinned scope；
- 明确打开时的 Suggested 或 History layer。

它不默认铺开：

- Topics；
- Knowledge；
- Sources；
- Evidence；
- Questions；
- Answer nodes；
- Query results；
- Candidates；
- decorative stars。

Knowledge-level 网络必须锚定当前 Group、Topic、Knowledge、Relation 或 Query Claim，不与 Library Network 混成一个尺度。

Groups ↔ Network 是同一 Library scene 的两种视图。Library 入口合同拥有切换时 scope、selection、filter 与 list position 的保存；本文拥有切换后 Relation truth、Graph / List、Inspector 和 relation return。零关系不移除 Network，Graph unavailable 时 List Equivalent 维持相同 Group set。

## 8.2 零关系

当 Library 有 Groups 但没有 Current Group Relations：

- 不画空星云；
- 不用 similarity 线填满；
- 不显示“网络尚未完成”；
- 明确写“当前没有你已确认的群级关系”；
- 仍可从 Group Catalog 打开任一 Group；
- 可查看具体 cross-group exits；
- 可显式 Compare 两个 Groups。

这是合法的成熟状态，不只是新用户空状态。

## 8.3 一个 Group / 一条 Relation

- 一个 Group：使用 Group orientation，不制造 Network canvas；
- 一条 Relation：优先显示完整 statement、方向和 Inspector；图只是可选辅助；
- 两到八条可读关系：可以使用局部 Graph + List；
- 超过可读预算：先要求 anchor / scope，不静默选择“最重要的几条”。

## 8.4 大规模 Network

当有 100、1000 或更多 Groups：

1. 先显示当前 effective scope；
2. 显示总 Group 数、Current Relation 数与被过滤数量；
3. 给出明确过滤原因；
4. 提供穷尽 Search / List；
5. 要求选择 Group、Saved View、relation family、direction、Path 或 Search result 作为 anchor；
6. 围绕 anchor 展开 direct Current neighbours；
7. 更多关系由用户按 family、direction、standing 或下一跳继续展开。

系统不根据 degree、recency、AI relevance 或 embedding cluster 静默决定“核心知识群”。自动 cluster 不能成为 Group、Boundary、region 或 Relation truth。

## 8.5 稳定性

同一 scope、anchor 与 filter 下，布局应尽量稳定，减少用户空间记忆被后台变化打断。

但坐标不是 canonical：

- layout 可以重算；
- 用户可以临时拖动；
- scene 可以保存；
- export / restore 不依赖坐标；
- 位置接近不意味着关系更强；
- 中心位置不意味着更可信。

## 8.6 Unconnected Groups

未连接 Groups 始终能在 Catalog / List 中穷尽找回。

在预算内，它们可以作为明确的 isolated Groups 显示；超出预算时，用“另有 N 个当前没有群级关系的 Groups”进入列表，不能静默消失。

---

# 9. Local Relation、Group Exit 与 Relation Companion

## 9.1 Local Knowledge Relation

从 Knowledge Reading 打开 R1 时，默认只显示直接 Current Knowledge Relations。

每个 neighbour 至少显示：

- title / identity；
- relation statement 摘要；
- direction；
- Group / Placement context；
- standing；
- relation family；
- Open / Inspect。

Evidence Binding、same Topic、same Source、backlink 与 Query co-use 不混入同一默认 edge layer。

## 9.2 Cross-group target

跨群 Knowledge Relation 被打开时，用户需要知道：

- target Knowledge 是哪一份 identity；
- 它在哪些 Groups 有 Placements；
- 这条 Relation 为什么从当前 scope 指向它；
- 推荐 Placement context 的理由；
- “保持当前群语境”与“切换到目标群”会有什么不同；
- Back 会返回哪里。

打开 target 改变 Reading Target；只在 Companion 中预览不改变。

## 9.3 Exit-only 表达

当一条 Knowledge Relation 跨群，但尚无 Group Relation：

- Local Graph 可以显示这条具体 Knowledge edge；
- Group Overview 可以显示“通往另一知识群的 1 条具体路径”；
- Library Network 不画 Group edge；
- Pair 可以解释为什么尚未上升；
- UI 不显示“待完成关系”红点。

## 9.4 Same Knowledge 多 Placement

如果 target Knowledge 同时属于两个 Groups：

- graph node 仍是一份 Knowledge identity；
- Placement context 作为可选择入口；
- Shared Knowledge Lens 只在 Pair / Compare 中出现；
- 不复制正文；
- 不因为两处出现而增加 relation strength。

## 9.5 Recommendation

Explore 可以推荐下一条 Current Relation 或 path，但必须说明：

- 与当前目标的关系；
- 使用了哪条 Current statement；
- 是否只是 exploration suggestion；
- 打开是否改变 target；
- 为什么没有展示其他邻居。

Recommendation 不创建 Relation、Path 或 priority truth。

---

# 10. Graph、List 与 Inspector 同义

## 10.1 共享状态

Graph、List 与 Inspector 必须共享：

- scope；
- anchor；
- selected object / relation；
- relation family；
- direction；
- qualifiers；
- standing layer；
- filters；
- visible / total counts；
- Open / Inspect / Compare；
- Return Envelope。

切换 Graph ↔ List 不能重置 selection、filter 或返回现场。

## 10.2 Graph 的责任

Graph 只负责：

- 显示当前 scope 内的对象与正式关系；
- 帮助扫描邻接、方向、bundle 与路径；
- 表达 selection、focus 与 hidden count；
- 让用户进入 Inspector 或 Open。

Graph 不负责：

- 单独承载完整 statement；
- 用线宽表达真值；
- 用颜色同时表达 type、standing、evidence 与 recency；
- 通过位置决定长期重要性；
- 把 Candidate 画得像 Current。

## 10.3 List Equivalent

List 必须可以独立完成：

- 浏览当前 scope 的全部关系；
- 读取完整 statement；
- 理解 direction / inverse；
- 检查 qualifiers、standing 与 why it matters；
- 按 endpoints、family、direction、standing、Group 筛选；
- 打开 Inspector；
- Open target；
- Compare pair；
- 进入 Evidence / History；
- exact return。

List 不是“无障碍降级版”，而是高密度、键盘、屏幕阅读器和 layout failure 时的一等视图。

## 10.4 Inspector 信息顺序

默认按以下顺序：

1. 完整 statement；
2. why it matters；
3. endpoints 与 direction；
4. qualifiers / named subscope；
5. Current / needs check / historical standing；
6. Evidence / support；
7. limits / CounterSignals；
8. Open / Compare；
9. Revision / decision history。

内部 gate、unit、policy、hash 与 registry ID 只在 Forensic disclosure 中出现。

## 10.5 不只靠颜色

Standing、direction、selection 与 unavailable 状态必须同时使用：

- 文本；
- shape / line pattern；
- icon；
- focus outline；
- screen reader label。

低对比细线、微小星点和 hover-only target 不承担唯一交互。

---

# 11. Inspect、Open、Return、Trail 与 Path

## 11.1 四个动作

| 动作 | 改变什么 | 不改变什么 |
|---|---|---|
| Focus | 键盘或视觉焦点 | Selection、Target、Trail |
| Inspect | 临时查看对象或 Relation | Reading Target、ReturnStack、Trail |
| Open | 改变 Primary target | Relation truth |
| Compare | 建立临时 Pair workspace | Current Relations、Paths |

单击、回车、双击或触控手势可以按平台映射，但后果必须一致并可解释。

## 11.2 Return Envelope

每次跨目标 Open 前保存：

- origin object identity / Revision；
- Group / Topic / Placement context；
- exact Anchor；
- scroll；
- focus；
- selected Relation / endpoint；
- filters；
- Graph viewport；
- presentation / radius；
- Ask scope / Answer Claim origin（若有）。

Back 恢复 Return Envelope；Up 进入当前 target 的结构父级；Close 关闭 Inspector / Companion。三者不能互换。

## 11.3 分支

用户走 A → B → C，Back 到 B，再 Open D：

- current branch 成为 A → B → D；
- Forward 不再假装指向 C；
- 提供低噪声“刚才的另一条分支：C”；
- 恢复 C 时恢复相应 Return Envelope；
- 日常界面不常驻完整树状历史。

分支不会自动成为 Saved Path。

## 11.4 Scene、Trail 与 Path

| 状态 | 责任 | 是否长期知识 |
|---|---|---:|
| Relation Scene | viewport、filters、expanded nodes、layout | 否 |
| Exploration Trail | 本次有意义的 Open 顺序 | 否 |
| Return Stack | 浏览器式回返 | 否 |
| Saved Path | 用户筛选、命名、带目的的路线 | 是，curation artifact |
| Path Progress | 当前阅读到哪一步 | 否，个人进度状态 |

Pan、zoom、hover、filter、dismiss、Inspect 不写 Trail。只有明确 Open target 才写入。

## 11.5 保存 Path

从 Trail 保存 Path 时，用户可以：

- 删除弯路；
- 重排步骤；
- 补充目的；
- 为 manual connector 写理由；
- 选择 target Placement context；
- 决定保存 current 还是 pinned revision basis。

保存 Path 不建立 Relation、不改变 Topic order、不复制 Knowledge，也不把 runtime jump 冒充 formal edge。

## 11.6 Query Route

Query Route 只解释本次 Answer：

- 哪些步骤是 Structure；
- 哪些是 Current Relation；
- 哪些是 Evidence；
- 哪些是 runtime retrieval jump；
- 哪些对象实际被使用。

“进入探索”只建立 Exploration origin；“整理成路线”打开 Path draft；“建立关系”打开独立 Relation Candidate / direct relation flow。三个动作不得合并。

---

# 12. Current、变化、结束与历史

## 12.1 用户可理解的六种结果

| 状态 | 普通语言 | 是否进入默认 Current layer |
|---|---|---:|
| Current | 当前仍采用 | 是 |
| Needs check | 当前仍采用，但变化可能影响它 | 是，必须说明 |
| Ended | 在明确旧时间 / 范围内曾成立，现在自然结束 | 否 |
| Superseded | 被一条更准确 successor Relation 替代 | 否，默认转 successor |
| Retracted | 用户不再认为原陈述成立 | 否 |
| Archived | 保留但不再放入当前工作视图 | 否 |

“陈旧”“低置信度”“坏关系”不能代替这些不同含义。

## 12.2 Relation Revision

以下通常是同一 Relation 的新 Revision：

- statement 更准确但仍承担同一关系角色；
- Applicability 收窄；
- direction explanation 修正；
- why it matters 更新；
- comparison dimension 修正；
- named subscope 改变。

如果新陈述承担不同关系角色，建立新 Relation，并明确 supersede 或并存；不能用大改 Revision 隐藏新主张。

## 12.3 Evidence 与 Relation 分开

增加、删除或替换 supporting Evidence：

- 更新 Evidence Binding / support snapshot；
- 不自动建立语义 Revision；
- 可能触发 needs check；
- 不用“多数来源”投票决定 Current。

个人知识 Relation 可以没有来源；高后果 Ask 必须诚实说明 evidence condition。

## 12.4 Challenge

AI 或新 Source 发现反例时，先比较：

- 是否在同一 Applicability；
- 是否挑战 statement、qualifier、support 还是 endpoint；
- 是否只要求增加限制；
- 是否需要 new parallel relation。

未经用户处理，反例不自动 retract Relation。Needs check 的 Relation 仍是 Current，但相关 Answer Claim 必须说明影响。

## 12.5 Split / Merge

Group 或 Knowledge split / merge preview 必须逐条列出关联 Relations：

- 继续指向原 identity；
- 只适用于一个 successor；
- 分别适用于多个 successors；
- 不再成立；
- 变成内部 self-edge；
- 当前无法判断。

系统可以生成 successor Candidates，但不得把旧 Relation 自动复制到所有 successors，也不得静默 retarget。

Merge 形成的 self-edge 进入 History，不改造成新的普通 Relation。

## 12.6 Archive / Delete

- Archive endpoint 不静默改变 Relation statement；
- Trash 前显示受影响的 Current Relations、Paths、Answers 与 deep links；
- Permanent delete 保留最小 tombstone、identity、title snapshot 与 decision history；
- 删除 Graph scene / layout 不删除 Relation；
- 删除 Placement 不删除 endpoint Knowledge 或 Relation。

## 12.7 History 的阅读

History 默认不与 Current 混排。

进入 History 时可以：

- 查看旧 statement / qualifiers；
- 查看当时 Evidence / support snapshot；
- 比较 successor；
- 打开历史 endpoints；
- 回到 current；
- 理解为什么 End / Supersede / Retract。

历史边不能画得像当前边。

---

# 13. Search、Ask、Overview 与 Formation 的关系边界

## 13.1 Search

Search 可以找回：

- Relation statement；
- endpoint；
- qualifier；
- Current / History；
- Pair；
- cross-group exit。

搜索结果中两个对象同时出现，不创建 Candidate。打开 Relation result 默认 Peek；打开 endpoint result 默认 Reading Quiet。

## 13.2 Ask

Ask 默认只把 Current Relations 当作 Library truth。

- Needs check：可以使用，但在相关 Claim 说明影响；
- Candidate：不作为已知事实，可在 Suggested context 单独说明；
- Ended / Superseded / Retracted：只有历史或 as-of 问题才使用；
- Runtime co-use：只进入 Route；
- 无正式 path：使用 Used Knowledge List，不编造中间 edge。

## 13.3 Answer → Explore

用户从 Answer Claim 进入 Explore 时：

- Claim 是 origin，不成为 graph node truth；
- 高亮实际 Current Relations / Structure / Evidence / runtime jumps；
- Route 与 Claim support 对齐；
- Close 返回同一 Answer Snapshot、Claim、scroll 与 focus；
- 本次 filter 不写回 Library Network。

## 13.4 Overview

Overview 可以：

- 提及 Current Group Relations；
- 推荐进入 Pair / Explore；
- 显示 needs check cue；
- 通过 local Diff 更新关系描述。

Overview 不自动从图密度生成“最重要联系”，也不因 Candidate 出现而改变 prose。

## 13.5 Formation

形成新 Knowledge 时产生的 Relation 建议必须另行提交：

- New Knowledge + required Evidence Binding 可以原子；
- Relation、Overview、Question 与额外 Placement 分别提交；
- 拒绝 Relation Candidate 不撤销已形成 Knowledge；
- AI 不能把“已提取 8 条关系”当作 Source processing 成功指标。

## 13.6 Structure

- Topic parent / child 是 Structure，不是 Relation；
- Group 之间不结构性嵌套；
- Saved View 只是 Catalog Lens；
- Placement 是同一 Knowledge 的语境归属；
- Group Relation 不改变 ownership、Topic tree 或 deletion cascade。

---

# 14. 失败、本地性、响应式与可访问性

## 14.1 失败分层

| 失败 | 仍然成立 | 产品行为 |
|---|---|---|
| Graph layout failed | Relation truth | 自动进入 List Equivalent |
| AI unavailable | Current Relations 与人工维护 | 可读、可建、可修订、可结束 |
| Index partial | 已加载 Current / last good list | 标记 coverage，不显示“无关系” |
| Source unavailable | Relation statement 与历史引用 snapshot | 标记核验不可用，不删除 Relation |
| Endpoint unavailable | Relation history 与 tombstone | 明确不可打开，不重定向到错误对象 |
| Write failed | 当前编辑 buffer | 不显示假成功，不更新 Graph |
| Offline | 本地 Current / History / List | 图布局可降级，本地维护继续 |

## 14.2 零、一与高密度

- 0 条：文本 + Catalog / Compare，不画空星云；
- 1 条：完整 statement 优先；
- 2–8 条：Graph / List 均可；
- 高密度：先 scope / anchor，再穷尽 List；
- 1000 条直接关系：不一次铺开，必须显式筛选且显示 total / hidden reason；
- 10,000 Candidates：不建立 Review Inbox，只在相关现场按语义 fingerprint 聚合。

## 14.3 Desktop

Desktop 可以同时显示 Reading + Companion，或 Explore + Inspector；主次必须清楚，不能永久等宽。

## 14.4 Compact / mobile

小窗口保留：

- scope / anchor；
- Current / Suggested / History；
- statement / direction / qualifiers；
- Graph / List 等价；
- Inspect / Open 差异；
- Back / Close / Up；
- origin summary。

Graph 可以变为 List-first；不得通过把节点缩小到不可点击来“保留桌面图”。

## 14.5 Keyboard

键盘用户可以：

- 在 List 中移动 focus；
- 读取完整 relation label；
- Inspect；
- Open endpoint；
- Compare pair；
- 切换 layer / filter；
- Back exact return；
- 进入 Evidence / History。

Focus 不等于 Open，Esc 关闭 Inspector 并恢复触发点。

## 14.6 Screen reader

每条 Relation 的可读标签至少包含：

> From — 完整关系短句 — To — direction — standing — qualifiers。

屏幕阅读器不需要遍历视觉坐标或每一条交叉线，即可完成与 Graph 相同的任务。

## 14.7 Motion 与 zoom

- reduced motion 下取消自动飞行与弹性布局；
- zoom 只改变视图尺度，不改变 Scope / Radius；
- selection、hidden count 与 direction 不依赖动画；
- 任何“进入另一群”的空间动画都必须有同义位置文字与 Back。

## 14.8 Export / Restore

Knowledge Package 保存：

- Relation identity / endpoint IDs；
- current 与 historical Revisions；
- statements / qualifiers；
- formation basis；
- Evidence / support snapshots；
- standing / decision events；
- Candidate adoption lineage 与必要 suppression；
- Group / Knowledge redirects 与 tombstones；
- Saved Paths。

可选保存 Scene。Scene 损坏或缺失不影响 Relation、List、Ask 或 restore。

---

# 15. 真实内容压力场景

## RX-01 · 有三个 Groups，但零群关系

Fixture C 的 Library 已有写作 Group 与其他独立内容，但用户没有建立正式群关系。Network 不显示星云或推荐线，只说明“当前没有你已确认的群级关系”，并提供 Catalog 与 Compare。

## RX-02 · 用户直接建立无来源的 Knowledge Relation

用户写下“先明确失败恢复边界，可以降低自动化流程中的不可逆风险”。保存后成为 Current Relation，并标记“你的判断；暂无外部依据”。不经过 Candidate。

## RX-03 · AI 相似建议被拒绝

两个标题都含“概念图”，但一个是学习活动，一个是产品关系空间。AI 提出 similarity Candidate；用户判断 governing task 不同并拒绝。Current Network 零变化，同一相似信号不重复出现。

## RX-04 · Cross-group exit，不形成群关系

Fixture A 中一条资格规则 Knowledge 指向另一个 Group 的流程知识，只证明存在具体可走出口。用户可以沿路径打开目标，但 Library Network 不生成 Group edge。

## RX-05 · 同 pair 两条 Current Group Relations

Fixture B 的“记忆机制”与“学习策略”同时拥有：

- 提供理论基础；
- 提供实际设计方法。

Network 显示“2 条当前关系”的 bundle；展开后两个 identities、statements、directions、qualifiers 与 support 分开。

## RX-06 · 三条 Shared Knowledge 不成为第三条关系

同一 pair 共享三条 Knowledge identities。Pair 的 Shared Lens 显示三条 observation；Current relation count 保持 2，关闭 Lens 后无新 edge。

## RX-07 · Pair exact return

用户从 K-S3 的 basis Anchor 打开 Pair，查看第二条 Group Relation 的 support，关闭后回到同一 K-S3 Revision、Anchor、scroll、focus 与 selected path。

## RX-08 · Query Route 没有正式中间边

Answer 同时使用 Knowledge A 与 B，但 Library 中没有 A ↔ B Relation。Route 显示两个 Used Knowledge 与 runtime jumps，不画一条伪 edge；用户可另开 Relation Candidate flow。

## RX-09 · 新来源只挑战不同范围

新研究在企业团队场景下限制原 Relation，而原 Relation 只适用于个人学习。系统比较 Applicability 后建议增加 qualifier 或 parallel relation，不把原 Relation 全局 retracted。

## RX-10 · 群关系支撑减少

一条 Current Group Relation 失去最强 supporting path。Relation 仍是 Current，标记 needs check；Pair 显示剩余支撑与移除影响，用户决定 Maintain 或 Revise。

## RX-11 · Group Split

一个 Group 拆成两个 successors。旧 Group Relation 只适用于其中一个。系统生成一个 successor Candidate；旧 Relation 不复制到两个新 Groups，采用后明确 supersede。

## RX-12 · 1000 条直接关系

一个高连接 Knowledge 有 1000 条 Current Relations。Explore 不自动显示 AI Top 8；先要求 relation family、Group、direction 或 Search anchor，显示 visible / total 与 hidden reason，List 可穷尽。

## RX-13 · Graph unavailable

布局引擎不可用。产品自动进入 Relation List，用户仍能读取 statement、Inspect、Open、Compare、History 与 exact return；不得显示“关系不存在”。

## RX-14 · Mobile + keyboard

同一 Pair 在 mobile 使用 List-first sequential flow，在 desktop 使用 Graph + Inspector；键盘用户不用进入 graph canvas 即可完成同样的关系判断和返回。

---

# 16. 专项验收合同

| REC | 对应 v6 | 验收责任 |
|---|---|---|
| REC-01 | AC-11 | 每条 Current Relation 可读为完整 statement；edge 不能是唯一表达 |
| REC-02 | AC-11 / 12 | 正式 endpoints 只允许 Knowledge ↔ Knowledge 或 Group ↔ Group，不跨层混接 |
| REC-03 | AC-12 | Structure、Evidence、Relation、Reference 与 Runtime Route 在 Graph / List / Inspector 中可区分 |
| REC-04 | AC-09 / 11 | 用户直接写完整关系可提交 Current；不进入 Candidate / Review |
| REC-05 | AC-22 / 26 | AI、来源抽取、相似度与路径聚合只创建 Candidate，不进入 Current truth |
| REC-06 | AC-26 | 拒绝 Candidate 零副作用，并抑制无新依据的重复建议 |
| REC-07 | AC-11 / 27 | direction、qualifiers 与 named subscope 改变会产生 Relation Revision |
| REC-08 | AC-27 / 28 | Evidence-only 更新不制造语义 Revision；History 可重建两类变化 |
| REC-09 | AC-11 / 16 | same-pair 多 Relations 保持独立 identities；Bundle 可展开完整 statements |
| REC-10 | AC-13 | 单条 cross-group exit、共同标签、co-use 或路径数量不会自动形成 Group Relation |
| REC-11 | AC-14 | Shared Knowledge Lens 不改变 relation count、Current inventory 或 resting layout |
| REC-12 | AC-13 / 21 | 系统群关系 Candidate 检查独立支撑、Boundary coverage、type fit、counter 与 removal；不用 confidence 替代 |
| REC-13 | AC-13 / 15 | 零 Relation 是合法状态，不显示空星云、相似度补边或维护催促 |
| REC-14 | AC-15 / 21 | Current、Suggested、History 分层；打开 Suggested 不改变 Current layout / Ask truth |
| REC-15 | AC-02 / 15 | Library Network resting level 只显示 Groups + Current Group Relations |
| REC-16 | AC-12 / 15 | Group、Topic、Knowledge、Source、Answer、Query 不混铺为全局万能图 |
| REC-17 | AC-15 | Quiet / Peek / Companion / Explore 与 R0–R3 正交；ordinary open 回 Quiet |
| REC-18 | AC-17 | Inspect 不改 target / Trail；Open 写 Return Envelope 并改变 target |
| REC-19 | AC-16 / 32 | Graph / List / Inspector 共享 scope、selection、filters、actions 与 complete truth |
| REC-20 | AC-17 | 跨群 Open / Pair / Answer Explore 关闭后恢复 exact object、Anchor、scroll、focus 与 origin |
| REC-21 | AC-17 | Back 后新 Open 形成轻量 branch；alternate 可恢复，不自动保存 Path |
| REC-22 | AC-12 / 17 | Scene、Trail、ReturnStack、SavedPath 与 Progress 分权，pan / zoom / Inspect 不污染历史 |
| REC-23 | AC-20 / 23 | Query Route 只显示真实 Structure / Relation / Evidence / runtime jumps；转 Path / Relation 均需显式动作 |
| REC-24 | AC-15 / 16 | 高密度先 scope / anchor、visible / total、hidden reason 与穷尽 List，不静默 AI Top N |
| REC-25 | AC-28 | Current、needs check、ended、superseded、retracted、archived 可分别重建 |
| REC-26 | AC-08 / 28 | Split / Merge / delete 不静默复制、retarget 或改型 Relation；逐条预览后果 |
| REC-27 | AC-29 / 30 | AI / layout / offline failure 不阻断人工关系维护；Export / Restore 不依赖坐标或 index |
| REC-28 | AC-31 / 32 | desktop / compact / mobile / keyboard / screen reader 可完成等价 Inspect、Open、Compare、List 与 return |

专项验收增加边界证明，不改变 v6 的 AC-01–AC-32 编号与责任。

---

# 17. 外部研究与产品推论

## 17.1 Obsidian：全局图与局部图分开

**官方事实：**Obsidian Graph View 将 vault 内部链接可视化；Local Graph 以当前 active note 为中心，并允许控制 depth、filters、groups 和 arrows。

来源：https://obsidian.md/help/plugins/graph

**产品推论：**锚定当前对象、显式控制半径，比默认铺满全部对象更适合日常探索。  
**不能照搬：**Obsidian 的线主要投影内部链接，不证明一条 link 已经拥有本产品要求的完整 semantic statement、qualifiers 与 standing。

## 17.2 TheBrain：Active Thought 驱动 Focus + Context

**官方事实：**TheBrain 以 Active Thought 为中心，周围按 parent、child、sibling 与 jump 显示语境；同一 Thought 可以位于多个上级之下，Past Thought List 保存激活顺序。

来源：https://help.thebrain.com/androidphone/thoughtrelationships.html  
来源：https://help.thebrain.com/androidphone/navigating.html

**产品推论：**关系空间围绕一个明确 anchor 重新组织 context，比固定全局坐标更适合连续导航；同一 identity 多语境不需要复制。  
**不能照搬：**parent / child / jump 是很宽的导航关系，本产品仍需把 Topic structure、Placement 与正式 semantic Relation 分开。

## 17.3 Wikidata / Wikibase：Statement 不只是 property-value

**官方事实：**Wikidata statement 至少由 property-value 组成，并可通过 qualifiers、references 与 rank 增加语境和依据。

来源：https://www.wikidata.org/wiki/Help:Statements/en

**产品推论：**时间、范围、条件与依据会改变关系的可读意义，因此不能只保存在不可见 metadata，更不能只画一条无标签 edge。  
**不能照搬：**Wikidata 面向公共结构化事实，本产品允许用户维护没有外部来源的个人判断，并以自然语言优先。

## 17.4 Neo4j Bloom：Perspective 与 Scene 分开

**官方事实：**Neo4j Bloom 的 Perspective 定义当前业务视角中可见的 categories、properties 与 relationship types；Scene 只包含用户通过 Search 或 Explore 找到的图的一部分，并可配合 Card List / Inspector。

来源：https://neo4j.com/docs/bloom-user-guide/current/bloom-perspectives/bloom-perspectives/  
来源：https://neo4j.com/docs/bloom-user-guide/current/bloom-visual-tour/bloom-overview/

**产品推论：**全图 truth、当前可见 scope 与临时 scene 必须分开；Scene 的选择、位置和筛选不能反向修改知识。  
**不能照搬：**Bloom 的数据图默认把数据库 relationships 当作已存在事实，本产品还需要 Candidate、Current、History 与用户采用边界。

## 17.5 研究共同支持什么

四类官方模式共同支持：

- anchor + local context；
- global scope 与 local exploration 分开；
- relation direction / type / statement 需要可检查；
- temporary scene 与 underlying truth 分开；
- list / inspector 是图探索的重要同伴；
- 同一 identity 可以在不同语境中被访问。

## 17.6 研究没有证明什么

这些来源没有证明：

- 全局 Graph 应该成为知识库首页；
- 更多节点与连线代表更好的知识；
- AI similarity 应自动成为 Current Relation；
- 所有用户需要维护精细 relation taxonomy；
- 每次探索都应保存为 Path；
- 固定 50/50 双栏就是方向 3 + 2；
- 图形界面可以替代完整 statement、List 与 exact return。

因此本合同中的 Current / Suggested / History 分权、群关系升级门槛、Quiet default、Group resting level 与 exact return 是本产品的设计判断，仍需真实任务验证。

---

# 18. 对 Ardot Screen 2 / 3 下一轮设计的证明要求

## 18.1 Screen 2 · Reading + Relation Companion

下一轮必须用同一真实 Knowledge fixture 证明：

1. ordinary open 为 Quiet，正文没有自动展开关系面；
2. 显式“查看相关知识”后出现唯一 Companion；
3. 一条 Relation 显示完整 statement、direction、qualifier 与 standing；
4. Inspect 不改变左侧 Reading Target；
5. Open target 后 Reading context 更新；
6. Back 恢复原 Anchor、scroll、selection 与 Companion scene；
7. cross-group target 显示 Placement context；
8. 窄屏使用 sequential / sheet，不把双栏缩成不可读；
9. List Equivalent 能完成同样操作。

## 18.2 Screen 3 · Library Group Network

下一轮必须证明：

1. resting level 只有 Groups + Current Group Relations；
2. Fixture B 同一 pair 的两条 Current Relations 可展开阅读；
3. Shared Knowledge 显示为 observation，不画第三条 edge；
4. Fixture A 的 cross-group exit 可走，但 Library Network 没有 Group edge；
5. Suggested layer 明确分离，拒绝后 Current layout 不变；
6. needs check / History 可读，但不与 Current 混排；
7. 0 relation、1 relation、dense relation 三种状态；
8. selected Group、scope、filters、visible / total 与 hidden reason；
9. Graph / List 同义；
10. 从 Network 打开 Knowledge 后 exact return。

## 18.3 最少设计证据包

未来不是只画两张 Hero 图，而是至少需要以下连续证据：

1. Quiet Reading；
2. Relation Peek；
3. Companion Inspect；
4. Cross-group Open；
5. Exact Back；
6. Library Network Current；
7. same-pair relation bundle；
8. Pair Comparison；
9. exit-only 负例；
10. Suggested Candidate inspector；
11. Reject zero side effect；
12. needs check / History；
13. zero / dense / layout failed；
14. Relation List；
15. mobile / keyboard responsibility。

这些可以由 Full Frame、overlay、component variants、flow annotation 与 state matrix共同证明，不等于十五个新页面。

## 18.4 必须避免

- 无标签金色连线；
- Group / Topic / Knowledge / Source 混合星点；
- “312 引用、89 关联”但没有 scope 与对象定义；
- 固定永久双栏；
- confidence 百分比替代资格解释；
- Candidate 与 Current 只靠虚实线区分；
- 关系类型只靠颜色；
- 全局图静默隐藏大部分对象；
- 没有 List Equivalent；
- 点击节点后无法回到原正文；
- 背景粒子与真实节点无法区分；
- 为填满画面自动生成关系。

## 18.5 方向 3 + 2 的准确比例

不是固定像素比例，而是任务主次：

- **阅读时：方向 3 是 100% 的主任务，方向 2 只是一枚克制入口；**
- **Companion 时：方向 3 仍是 Primary，方向 2 提供局部解释；**
- **Explore 时：方向 2 成为 Primary，但方向 3 以 origin、Preview 和 exact return 保持连续；**
- **关闭 Explore 后：产品回到同一条方向 3 阅读主干。**

---

# 19. 最终产品判断

真正的知识网络不是把知识库空间化，而是让用户可以：

- 从一条具体理解出发；
- 读懂它为什么与另一条理解或另一个知识群相连；
- 区分路径、观察、建议、当前关系与历史；
- 在需要时扩大关系半径；
- 沿真实关系进入另一处知识；
- 回到刚才的正文与证据；
- 在没有关系、关系很少或关系很多时仍然不被图欺骗。

如果线条不能被读成一句可维护的话，它就不应被当作 Relation。  
如果跨群探索不能准确回到原 Anchor，它就还不是方向 3 + 2 的产品结合。
