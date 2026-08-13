# AI-native 个人知识库

## 第二真实端到端夹具 v1.0 — 概念学习、多语境复用与群关系

> 文档日期：2026-08-10  
> 文档性质：产品定义压力测试、真实研究内容夹具、未来 Screen 2 / 3 设计证明输入；不是学习建议、课程、界面稿或原型授权  
> 主题：记忆与学习科学 → 为两个月后的考试与长期使用设计个人学习策略  
> 研究边界：只使用论文、出版方页面、PubMed / ERIC 等原始或官方记录；研究结论保留实验任务、比较条件、结果类型与延迟，不写成无条件定律  
> 产品真相源：`AI-native-个人知识库-终局产品设计文档-v6.0.md`；旧类型注册表与 v4.0 只保留为实验 / 历史参考  
> 当前阶段：继续定义产品；不修改 Ardot，不制作 Screen，不授权原型

---

# 0. 执行结论

## 0.1 为什么必须有第二个夹具

第一份真实夹具用法国租房、Visale 与住房补助证明了产品能承载时效规则、个人适用条件、机构结果与变化复核。但它也有一个危险：如果只用资格型案例校准，产品会逐渐像“带来源的规则查询系统”，而不是用户要的知识库。

本夹具故意换成一个低时效、概念密集、需要理解机制与比较证据的主题。它检查同一套产品能否完成另一种旅程：

> 用户先在“记忆与学习科学”知识群里，从 Overview 深入理解学习表现、长期保持、提取练习、间隔与编码线索；再进入“个人学习策略设计”知识群，把同一知识以不同角色复用；保存一个决策型 Question 和四个必需子问题；让 AI 在明确研究范围内综合，而不是给出万能学习法；把答案中的稳定原则与可执行方法形成 Knowledge；建立两条方向不同但都成立的群关系；之后用一篇方法学评论收窄过宽陈述，并精确回到原来的判断现场。

如果产品只能列论文、生成摘要、画概念图或给出学习计划，这条旅程仍然没有成立。

## 0.2 压力测试结果

第二个主题没有要求增加新的产品中心，也没有要求把产品变成学习工具。现有 Group、Topic、Knowledge、Placement、Relation、Question、Source、Evidence、Ask 与 Pair Comparison 足以承载主要工作。

但真实研究比较暴露出七项必须收紧的合同：

1. **研究 Claim 需要可比较的条件快照。** 只保存“这篇论文支持它”不够；至少要知道参与者 / 材料、学习活动、比较对象、结果类型、延迟、反馈与迁移距离。
2. **当下表现不等于长期学习。** Ask 不能把即时测验、主观流畅感或短时回忆与延迟保持混成一个“效果”。
3. **同一 Knowledge 可以在两个知识群承担不同角色。** canonical 正文不复制，但 Placement 的 contextual summary、role 与邻接结构可以不同。
4. **共享知识不是群关系。** 三条共享 Knowledge 只是动态观察；“理论提供基础”和“方法被实际采用”是两条需独立成立的正式关系。
5. **方法学评论首先挑战 Evidence Binding 或 Claim 的泛化范围。** 它不会自动产生 `knowledge.contradicts`，更不会把整篇论文标成错误。
6. **决策型问题可以有必需子问题。** 子问题各自可被回答，父问题只按 criteria 汇总，不因一个子问题 resolved 自动解决。
7. **策略是程序性 Knowledge，日历任务不是。** 产品可以保存“怎样复习”的可复用方法；实际哪天做第几次练习属于外部任务 / 日历系统，不扩张知识库本体。

## 0.3 本夹具冻结的十五项产品决定

1. `G-MEM` 与 `G-STUDY` 是两个独立 Group，不是一个课程的两个章节。
2. 两群各自拥有 Boundary、Overview 与 Topic tree；同一 Knowledge 通过 Placement 跨群出现，不复制 identity。
3. `学习`的评价至少区分 acquisition performance、delayed retention 与 transfer。
4. 研究陈述默认使用“在这项研究及这些条件下”，除非证据本身支持更广范围。
5. Source 的研究类型、Evidence Binding 的作用与 Knowledge 的 standing 分开。
6. meta-analysis 可以支持综合 Claim，但仍需保存纳入范围与结果边界；它不是“最终真相”标签。
7. technical comment 默认形成 `challenges` Evidence Binding / Annotation；只有用户显式形成可复用判断时才成为 Knowledge。
8. `Retrieval practice`、`Spacing` 与`学习表现不等于长期学习`各只有一个 canonical identity，但在两群拥有不同 Placement。
9. lexical similarity 不形成 shared identity；“概念图作为学习活动”与“知识库的关系网络表面”不是同一 Knowledge。
10. 一个父 Question 可拥有四个 required Subquestions；每个子问题有独立 Resolution 与 pursuit。
11. adopted parent Resolution 可以是 `provisionally_resolved + active`：目前足够指导策略，但继续收集课程约束与结果证据。
12. `G-MEM provides_foundation_for G-STUDY` 与 `G-MEM provides_method_for G-STUDY` 可以同时为 Current，因为它们表达独立陈述。
13. `provides_method_for` 只有在目标群实际采用方法后成立；“可能适用”或“被提到”都不够。
14. Pair Comparison 同时显示 Current Relations、Shared Knowledge、Paths、被拒候选、依据与限制，不把它们合并成一条粗边。
15. 未来方向 3 + 2 必须用长正文、真实研究限定、多 Placement、同 pair 多关系和 exact return 证明；星图、短标签与论文卡片墙不计为证明。

---

# 1. 事实、决定与合成情境

## 1.1 证据 standing

| 标记 | 含义 | 在本夹具中的纪律 |
|---|---|---|
| **[研究事实]** | 论文或官方记录直接支持 | 保留研究条件、结果与延迟；不超出原研究措辞 |
| **[夹具事实]** | 本文冻结的对象、ID、路径与状态 | 用于产品验收，不声称来自真实用户 |
| **[产品决定]** | 本产品对对象、交互或写回的选择 | 必须同步到 canonical / 专项合同 |
| **[合成输入]** | 为跑通流程而设定的用户目标与约束 | 不冒充用户本人事实，不默认形成 Knowledge |
| **[待验证假设]** | 仍需真实任务或可用性验证 | 不因夹具跑通而写成用户价值已证实 |

## 1.2 合成学习情境

夹具人物 `P-YU-02`：

| 字段 | 值 | standing |
|---|---|---|
| 学习目标 | 两个月后的闭卷期末考试，且考试后仍希望能解释和应用主要概念 | synthetic decision context |
| 材料 | 约 12 个章节、课堂讲义与一组往年开放题 | synthetic input |
| 当前习惯 | 重读、划线、临近考试集中复习，偶尔画概念图 | synthetic input |
| 可用时间 | 每周 5 天、每天约 45 分钟 | synthetic constraint |
| 目标结果 | 延迟保持、解释概念、解决新情境中的推理题 | synthetic criterion |
| 未知 | 如何组合重读、概念图、提取练习与间隔复习 | synthetic unknown |
| 不在范围 | 诊断注意力障碍、医疗建议、自动生成日历任务 | explicit exclusion |

这些值属于本 Question / Ask Run 的 Applicability；只有用户主动保存为长期属性，才成为可跨运行复用的 Property Assertion。

## 1.3 来源注册表

| ID | 来源 | 类型 | 本夹具采用的边界 |
|---|---|---|---|
| S-M1 | Roediger & Karpicke, 2006, *Test-Enhanced Learning* | 两项实验 | 短期重复学习可能有即时表现优势；延迟测验中先前测试产生更好保持；限于论文任务和时点 |
| S-M2 | Karpicke & Roediger, 2008, *The Critical Importance of Retrieval for Learning* | 实验 | 初次正确回忆后的重复测试提高延迟回忆；重复学习没有同样效果；保留词汇任务与程序条件 |
| S-M3 | Cepeda et al., 2006, *Distributed Practice in Verbal Recall Tasks* | quantitative synthesis / review | 间隔与最终保持间隔共同作用；合适间隔不是固定常数 |
| S-M4 | Soderstrom & Bjork, 2015, *Learning Versus Performance* | integrative review | acquisition 中可观察的表现可能不是长期学习的可靠代理 |
| S-M5 | Tulving & Thomson, 1973, *Encoding Specificity and Retrieval Processes* | 理论与实验论文 | 有效提取线索与编码时的信息关系有关 |
| S-M6 | Godden & Baddeley, 1975, *Context-dependent memory in two natural environments* | 现场实验 | 潜水员在陆地 / 水下学习和回忆词表，同环境条件下回忆更好；不外推为“换环境必然失败” |
| S-M7 | Smith & Vela, 2001, *Environmental context-dependent memory* | review / meta-analysis | 环境情境效应总体可靠，但在鼓励非情境加工时减弱 |
| S-M8 | Butler, 2010, *Repeated testing produces superior transfer of learning* | 实验 | 在论文任务条件下，重复测试相较重复学习支持延迟保持及对新推理问题的迁移 |
| S-M9 | Karpicke & Blunt, 2011, *Retrieval Practice Produces More Learning than Elaborative Studying with Concept Mapping* | 实验 | 在研究设定中，提取练习优于概念图学习，包括若干理解 / 推理测验；不推出“概念图无用” |
| S-M10 | Mintzes et al., 2011, *Comment on Retrieval Practice Produces More Learning...* | technical comment | 对 S-M9 的方法、暴露与认识论解释提出挑战；它是 critique，不自动撤销 S-M9 |

### 可核验 URL

- S-M1：[Association for Psychological Science](https://www.psychologicalscience.org/journals/psychological-science/j.1467-9280.2006.01693.x/)
- S-M2：[Science DOI](https://doi.org/10.1126/science.1152408)
- S-M3：[PubMed 16719566](https://pubmed.ncbi.nlm.nih.gov/16719566/)
- S-M4：[PubMed 25910388](https://pubmed.ncbi.nlm.nih.gov/25910388/)
- S-M5：[ERIC EJ083912](https://eric.ed.gov/?id=EJ083912)
- S-M6：[Wiley DOI](https://doi.org/10.1111/j.2044-8295.1975.tb01468.x)
- S-M7：[PubMed 11495110](https://pubmed.ncbi.nlm.nih.gov/11495110/)
- S-M8：[PubMed 20804289](https://pubmed.ncbi.nlm.nih.gov/20804289/)
- S-M9：[PubMed 21252317](https://pubmed.ncbi.nlm.nih.gov/21252317/)
- S-M10：[Science DOI](https://doi.org/10.1126/science.1203698)

### Fragment 与 Binding 分配

二十个 Evidence Fragments 不是把每篇论文机械切成两段，而是为每项需要回读的`结果 / 条件 / 限制`保存独立 locator：S-M1 三段；S-M2 两段；S-M3 两段；S-M4 一段；S-M5 两段；S-M6 两段；S-M7 两段；S-M8 两段；S-M9 两段；S-M10 两段，共 20 段。

二十五个 Evidence Bindings 按 target 与作用独立保存：S-M1 三条；S-M2 两条；S-M3 三条；S-M4 两条；S-M5 两条；S-M6 两条；S-M7 三条；S-M8 两条；S-M9 三条；S-M10 三条，共 25 条。同一 Fragment 可以支持 K-M3、限定 K-M4，或在 Answer 中承担 ClaimSupport；这些作用不因共用 locator 合并，也不按数量投票。

## 1.4 研究来源不是同权投票

产品不显示“10 篇论文，8 篇赞成，可信度 80%”。比较时至少检查：

- 是否研究同一种学习活动；
- 材料是词对、短文、概念材料还是实际课程；
- comparator 是重读、无测试、概念图还是另一种检索；
- outcome 是即时表现、延迟回忆、理解还是迁移；
- delay 是几分钟、几天、几周还是更长；
- 是否有反馈、重复接触或额外学习时间；
- final test 是否偏向某一种练习形式；
- critique 在挑战结果、方法、解释还是外推范围。

因此 Source count 只说明覆盖，不说明真值强度。

---

# 2. 产品对象总账

## 2.1 固定计数

| 对象 | 数量 | 说明 |
|---|---:|---|
| Groups | 2 | `G-MEM`、`G-STUDY` |
| Topics | 32 | 每群 16 个：4 个一级 Topic + 12 个二级 Topic，形成 Group → Topic → Subtopic → Knowledge 深度 |
| canonical Knowledge | 15 | 研究理解 12 条、策略知识 3 条 |
| Placements | 18 | 其中 3 条 Knowledge 各有双 Placement |
| Shared Knowledge Observations | 3 | 动态 observation，不是 Relation |
| Sources | 10 | 论文 / official scholarly records |
| Evidence Fragments | 20 | 每个来源至少一个可定位片段；关键来源拆分 claim / condition |
| Evidence Bindings | 25 | supports / qualifies / challenges / defines |
| Knowledge Relations | 11 Current + 2 rejected non-relations | 精确类型、方向与限定 |
| Questions | 6 | 1 parent、4 required subquestions、1 context question |
| Answer Snapshots | 2 | 扩展范围后的 Answer v1、评论到来后的 Answer v2；首次范围不足只产生 expansion request，不冒充 Answer |
| adopted Resolutions | 2 | parent provisional、context sufficient-for-current-purpose |
| Group Relations | 2 Current | foundation + method，同一 pair 不合并 |
| Group Relation Candidate | 1 rejected | `complements` 被拒 |
| end-to-end steps | 27 | 从 Overview 到 exact return |

## 2.2 不是新对象的内容

以下都不增加 Product Resource：

- `StudyConditionSnapshot`：Evidence Binding / ClaimSupport 的可选结构字段；
- `Shared Knowledge Observation`：按 pair + Knowledge identity 动态求值；
- `Pair Comparison`：一次 Workspace State；
- 本次 Ask 的 study constraints：Question / Run Applicability；
- 学习安排建议：若被采用，形成 procedural Knowledge；
- 某天 19:00 做练习：不进入知识库对象体系。

---

# 3. Group A — 记忆与学习科学

## 3.1 Boundary

```text
Group: G-MEM / 记忆与学习科学
governing_question:
  学习活动、提取条件与时间安排怎样影响长期保持、理解和迁移？
includes:
  学习与表现的区别；提取练习；间隔；编码与提取线索；
  环境情境；保持与迁移结果；研究比较与方法边界。
excludes:
  临床诊断；完整神经科学；具体课程排期；学习任务执行与提醒。
material_boundary:
  解释机制、经验结果与研究限制，而不是直接替用户制定日历。
```

## 3.2 Topic tree（16 Topics）

```text
记忆与学习科学
├─ 1. 怎样判断“真的学会了”
│  ├─ 1.1 学习与当下表现
│  ├─ 1.2 延迟保持
│  └─ 1.3 迁移与新问题
├─ 2. 提取如何改变学习
│  ├─ 2.1 提取练习
│  ├─ 2.2 重复学习与重复测试
│  └─ 2.3 反馈、错误与再学习
├─ 3. 时间怎样进入学习
│  ├─ 3.1 间隔效应
│  ├─ 3.2 保持间隔与复习间隔
│  └─ 3.3 即时表现与延迟结果反转
└─ 4. 线索与情境
   ├─ 4.1 编码特异性
   ├─ 4.2 环境情境依赖
   └─ 4.3 边界条件与方法争议
```

## 3.3 Group Overview 的真实内容

### G-MEM 开场

这个知识群不从“哪一种学习法最好”开始，而从结果定义开始。学习中的当下流畅、练习阶段正确率和短时回忆可能很有用，但它们不自动等于几天或几周后的保持，也不等于面对新问题时的迁移。

### 三个主要方向

1. **先区分结果。** 研究比较只有在 outcome 与 delay 可比时才有意义。
2. **提取不只是测量。** 在若干受控研究中，主动回忆本身改变了后续保持与迁移；作用范围必须跟随材料、练习和最终测验。
3. **时间与线索共同作用。** 间隔不是固定天数；编码时建立的线索、提取时可用的线索和目标保持间隔都会改变结果。

### 当前不能写成定律的内容

- “测试永远优于学习”；
- “概念图没有价值”；
- “换环境一定损害记忆”；
- “间隔越长越好”；
- “练习时感觉困难说明方法无效”。

### 深入入口

- 想判断方法：进入`怎样判断真的学会了`；
- 想理解 mechanism：进入`提取如何改变学习`；
- 想制定节奏：进入`时间怎样进入学习`；
- 想回答换环境问题：进入`线索与情境`。

---

# 4. Group B — 个人学习策略设计

## 4.1 Boundary

```text
Group: G-STUDY / 个人学习策略设计
governing_question:
  在给定目标、材料、时间与评估方式下，怎样组合学习活动并判断策略是否有效？
includes:
  学习目标；结果指标；活动组合；间隔安排原则；反馈；
  结构综合；迁移检查；策略版本与适用条件。
excludes:
  认知科学领域全貌；医疗 / 诊断；学校教务；日历任务和提醒执行。
material_boundary:
  保存可解释、可复用、可修订的方法与判断，不管理每日待办。
```

## 4.2 Topic tree（16 Topics）

```text
个人学习策略设计
├─ 1. 先定义学习结果
│  ├─ 1.1 两个月后的保持
│  ├─ 1.2 解释与结构理解
│  └─ 1.3 新问题迁移
├─ 2. 选择学习活动
│  ├─ 2.1 重读与首次理解
│  ├─ 2.2 提取问题与自测
│  └─ 2.3 概念图与结构综合
├─ 3. 安排节奏与反馈
│  ├─ 3.1 间隔原则
│  ├─ 3.2 错误反馈与再学习
│  └─ 3.3 难度与可持续性
└─ 4. 评估并修订策略
   ├─ 4.1 延迟检查
   ├─ 4.2 迁移题检查
   └─ 4.3 适用条件与版本
```

## 4.3 Group Overview 的真实内容

### G-STUDY 开场

本群不是一张固定学习计划，而是一套可复用的判断：目标保持多久、要会回忆还是会迁移、材料是什么、每次活动承担什么作用，以及怎样用延迟结果而非当下流畅感修订方法。

### 当前采用的策略骨架

1. 首次接触用阅读与结构整理建立最低必要理解；
2. 尽早把目标概念改写成需要主动生成答案的问题；
3. 在多个时间点进行有反馈的提取，而不是只在最后集中重读；
4. 概念图承担结构综合与暴露连接缺口，不替代延迟提取检查；
5. 用延迟回忆和新情境推理题检查策略，而不是只看练习阶段熟练度。

### 当前限制

这不是对所有课程、所有人和所有考试形式的最优解。课程材料、可用时间、最终评估形式和错误反馈资源尚未完全输入，所以当前策略是 provisional。

---

# 5. 十五条 canonical Knowledge

## 5.1 研究理解 Knowledge（K-M1 至 K-M12）

### K-M1｜学习与 acquisition performance 是不同结果

- kind：Principle Knowledge
- canonical claim：练习阶段可观察表现可以反映当前状态，但不能单独证明长期、稳定的学习。
- qualifiers：结果维度、测量时点、任务类型。
- primary support：S-M4。
- non-claim：困难练习一定更好。

### K-M2｜提取练习

- kind：Method Knowledge
- canonical body：在不给出完整答案的情况下，尝试从记忆中生成目标信息，再核对和修正。
- scope：可包含自由回忆、简答、自测；不等于只做选择题或只看答案。
- primary support：S-M1、S-M2、S-M8。

### K-M3｜提取练习在若干研究条件下改善延迟保持

- kind：Empirical Finding Knowledge
- claim：相较额外重读，在 S-M1 / S-M2 对应任务和测验时点下，先前提取产生更好的延迟保持。
- required language：`在这些研究及其任务条件下`。
- non-claim：对任何材料、任何时长、任何人永远更好。

### K-M4｜即时与延迟结果可能给出不同的“最佳方法”

- kind：Principle Knowledge
- claim：某活动在几分钟后的表现更好，不保证其在几天或一周后的保持也更好。
- primary support：S-M1、S-M4。
- role：防止 Ask 把容易、熟悉与长期效果混为一谈。

### K-M5｜间隔学习

- kind：Method / Principle Knowledge
- body：把对同一目标的学习或提取分布到多个时间点，而非只集中在一个区段。
- primary support：S-M3。
- non-claim：任意拉长间隔都有效。

### K-M6｜合适间隔依赖目标保持间隔

- kind：Empirical Synthesis Knowledge
- claim：S-M3 的综合结果表明，学习事件间隔与最终保持间隔共同影响表现，目标保持越远，合适间隔通常也随之变化。
- qualifiers：verbal recall tasks、纳入研究范围、最终时点。

### K-M7｜提取练习可以支持对新推理问题的迁移

- kind：Empirical Finding Knowledge
- claim：在 S-M8 的材料、练习与最终测验条件下，重复测试相较重复学习改善对新 inferential questions 的表现。
- non-claim：所有形式的 testing 都会产生远迁移。

### K-M8｜在 S-M9 条件下，提取练习优于概念图学习

- kind：Bounded Comparative Finding
- claim：在该研究的学习程序、材料和测验条件下，retrieval practice 的最终表现高于 concept mapping condition。
- mandatory qualifier：不能缩写为`提取练习优于概念图`。
- challenge：S-M10 针对方法与解释提出质疑。

### K-M9｜学习活动比较必须保留暴露与测验对齐条件

- kind：Research Interpretation Principle
- claim：比较两种学习活动时，需要检查额外接触、练习形式、时间投入和 final assessment 是否偏向某一活动；否则结论只能保持在研究设定内。
- support：S-M10 challenges S-M9 的泛化；用户显式形成后才成为 Knowledge。
- non-claim：所有活动比较都无效。

### K-M10｜编码特异性

- kind：Theory / Principle Knowledge
- body：某个线索是否能支持回忆，取决于它与编码时形成的信息之间的关系，而不只取决于线索本身是否“强”。
- primary support：S-M5。

### K-M11｜环境情境可以影响回忆

- kind：Empirical Finding Knowledge
- claim：S-M6 的潜水员词表任务中，学习与回忆环境匹配时回忆更好。
- qualifiers：特定任务、参与者、环境操纵。
- non-claim：所有知识都必须在考试教室学习。

### K-M12｜环境情境效应存在边界条件

- kind：Empirical Synthesis Knowledge
- claim：S-M7 报告环境 context-dependent memory 总体可靠，但鼓励非情境加工等条件会减弱该效应。
- role：限定 K-M11，并支持对“换环境一定有害”的否定回答。

## 5.2 策略 Knowledge（K-S1 至 K-S3）

### K-S1｜耐久且可迁移的学习目标

- kind：Decision / Principle Knowledge
- body：本策略以两个月后的延迟保持、概念解释与新问题迁移为主要结果，不以重读流畅感或当天正确率单独判断成功。
- applicability：本合成课程情境；可被复制为模板，但不自动适用于所有目标。

### K-S2｜间隔提取 + 反馈 + 结构综合的组合策略

- kind：Procedural Knowledge
- body：先建立最低必要理解；把关键概念转为生成式问题；跨多个时间点主动提取；核对错误并再学习；用概念图整合结构；用延迟与迁移题复查。
- basis：K-M2、K-M5、K-M7、K-S3。
- standing：current、provisional、user-adopted fixture。
- exclusion：不包含具体日期、提醒或待办完成状态。

### K-S3｜概念图的角色是结构综合与诊断，不替代提取检查

- kind：Method / Boundary Knowledge
- body：概念图用于外显概念关系、发现结构缺口和综合内容；是否能延迟回忆仍需独立提取与测验。
- basis：K-M8 只提供 bounded comparison；K-M9 防止把单篇比较外推为“概念图无用”。
- standing：provisional synthesis，不冒充某篇论文原句。

---

# 6. Placement 与同一知识的多语境复用

## 6.1 三条 Shared Knowledge

| Knowledge | G-MEM Placement | G-STUDY Placement | canonical body |
|---|---|---|---|
| K-M1 学习与表现不同 | `1.1 学习与当下表现`；role=`core principle`；summary=`为什么即时顺利不能证明长期保持` | `4.1 延迟检查`；role=`evaluation guardrail`；summary=`不要用当天熟练度决定策略有效` | 完全相同 |
| K-M2 提取练习 | `2.1 提取练习`；role=`core method under study`；summary=`提取如何被定义与研究` | `2.2 提取问题与自测`；role=`adopted method basis`；summary=`怎样把材料改成主动生成问题` | 完全相同 |
| K-M5 间隔学习 | `3.1 间隔效应`；role=`core temporal principle`；summary=`分布学习的研究对象` | `3.1 间隔原则`；role=`schedule principle`；summary=`为什么不把复习集中到最后` | 完全相同 |

Shared Knowledge Lens 显示 3 条 observation。它只说明同一 identity 在两群出现，不增加 relation count，不触发 Adopt，不改变 resting Network layout。

## 6.2 从两个语境打开同一 Knowledge

从 `G-MEM / 2.1` 打开 K-M2：

- Primary reading context 是定义、研究范式与证据；
- 上一层返回`提取如何改变学习`；
- 相邻关系优先显示 K-M3、K-M4、K-M7；
- contextual summary 写“提取如何被定义与研究”。

从 `G-STUDY / 2.2` 打开同一 K-M2：

- canonical title、body、Revision、Evidence 完全一致；
- 上一层返回`选择学习活动`；
- 相邻关系优先显示 K-S2、反馈与迁移检查；
- contextual summary 写“怎样把材料改成主动生成问题”。

两次进入使用不同 Return Envelope 与 Placement context，不能为方便而复制 K-M2。

## 6.3 三种容易发生的错误

### 错误 A：把 Placement summary 写回正文

“用于本课程的每周复习”只属于 G-STUDY 语境，不应污染 K-M2 的 canonical definition。

### 错误 B：把共享知识画成正式群边

三条 shared identities 不自动得到`共享核心知识`或`overlaps_with`。若没有独立 Boundary / contribution statement，结果仍可只是 observation。

### 错误 C：按词面错误合并

`概念图作为学习活动`与`知识库 Network / relation space`都含“概念 / 图”，但 identity、governing task、内容与证据不同。Embedding 或标题相似不得自动 merge。

---

# 7. Evidence Condition Contract

## 7.1 可选 StudyConditionSnapshot

研究 Claim 的 Evidence Binding 可以附带：

```text
StudyConditionSnapshot
  population_or_sample?
  material_or_domain?
  learning_activity_or_intervention?
  comparator?
  exposure_or_dosage?
  feedback_condition?
  outcome_kind?
    acquisition_performance
    immediate_recall
    delayed_retention
    comprehension
    near_transfer
    far_transfer
  outcome_delay?
  assessment_format?
  transfer_distance?
  observed_limitations[]
  source_reported_or_interpreted
```

这是 Evidence / Answer ClaimSupport 的可选结构，不是要求所有生活知识填写研究表格。只有当条件会改变 Claim 的可比性、适用范围或回答结论时显示。

## 7.2 三个实际 Binding

### EB-01：S-M1 → K-M3 supports

```text
role: supports
conditions:
  material: prose passages
  intervention: study-test sequences
  comparator: repeated study
  outcome: recall
  delay: 5 minutes / 2 days / 1 week
display:
  该研究在短文学习任务中比较重复学习与测试；即时和延迟结果不同。
```

### EB-02：S-M10 → K-M8 challenges

```text
role: challenges
target: K-M8 current revision
challenge_dimension:
  exposure comparability
  assessment alignment
  epistemic interpretation
effect:
  require narrower wording and visible limitation
does_not_do:
  create contradicts Relation
  retract S-M9
  invalidate every retrieval-practice claim
```

### EB-03：S-M7 → K-M11 qualifies

```text
role: qualifies
condition:
  noncontextual processing encouraged
effect:
  environmental context effect may be reduced
```

## 7.3 什么时候才是 Conflict

只有同时满足以下条件，才建立 incompatible Knowledge claims / Conflict：

1. 两条可理解陈述在同一 outcome dimension 上不能并存；
2. population、material、activity、comparator、delay 与 assessment 的重叠足够；
3. 差异不能由 scope、time、measurement 或 source role 解释；
4. 用户需要在当前目标中处理这项不相容。

S-M9 与 S-M10 不满足这四项：一个报告实验比较，一个挑战方法与外推。因此它们形成 challenge + revision pressure，不形成“retrieval practice 与 concept mapping 矛盾”的粗暴 Conflict。

---

# 8. Knowledge Relations：十一条成立、两条不成立

## 8.1 Current relations

下表中的精确 `type` 名称是夹具表达与实验性标签，不是 v6 默认 UI 或 schema 注册表。`provides_foundation_for`、`explains`、`supports`、`contributes_to` 映射到 `Support / Explain` 意图族；`qualifies` 映射到 `Challenge / Qualify`；`component_of`、`provides_method_for` 映射到 `Apply / Implement`。完整 statement、方向、限定与依据才是关系的规范性内容。

| ID | statement | type | direction | Applicability / reason |
|---|---|---|---|---|
| KR-01 | K-M3 限定性支撑 K-M2 作为长期保持方法 | `provides_foundation_for` | K-M3 → K-M2 | 仅研究覆盖的任务与结果 |
| KR-02 | K-M4 限定 K-M3 的评价时点 | `qualifies` | K-M4 → K-M3 | 即时结果不能替代延迟结果 |
| KR-03 | K-M6 为 K-M5 的安排原则提供基础 | `provides_foundation_for` | K-M6 → K-M5 | 间隔必须相对目标保持期解释 |
| KR-04 | K-M7 支撑 K-S1 把迁移列为目标 | `supports` | K-M7 → K-S1 | argument support，不冒充 Evidence Binding |
| KR-05 | K-M2 是 K-S2 的组成方法 | `component_of` | K-M2 → K-S2 | 提取步骤被实际采用 |
| KR-06 | K-M5 是 K-S2 的时间结构 | `component_of` | K-M5 → K-S2 | 分布到多个时点 |
| KR-07 | K-S3 是 K-S2 的结构综合步骤 | `component_of` | K-S3 → K-S2 | 不替代延迟提取 |
| KR-08 | K-S2 有助于 K-S1 的目标 | `contributes_to` | K-S2 → K-S1 | 贡献，不承诺保证结果 |
| KR-09 | K-M10 解释 K-M11 的线索机制 | `explains` | K-M10 → K-M11 | mechanism-level explanation |
| KR-10 | K-M12 限定 K-M11 的外推 | `qualifies` | K-M12 → K-M11 | 环境效应有边界条件 |
| KR-11 | K-M9 限定 K-M8 的比较解释 | `qualifies` | K-M9 → K-M8 | 保留 exposure 与 assessment 条件 |

## 8.2 两条明确不建立的 Relation

### NR-01：S-M10 contradicts K-M8

不成立。S-M10 是 Source / Evidence，首先通过 Binding `challenges` K-M8；Source 不能为了图谱整齐而冒充 Knowledge endpoint。

### NR-02：K-S2 causes K-S1

不成立。一个组合策略可能支持目标，但本夹具没有证明它必然造成长期保持或迁移。使用 `contributes_to`，不是 `causes`。

## 8.3 视觉表达责任

关系层默认不同时画出十一条边。阅读 K-S2 时只显示与当前理解任务相关的组成关系；进入 Explore 才扩大 Relation Radius；Evidence Binding 仍留在核验层，不混进 ordinary relation graph。

---

# 9. Question family 与求解标准

## 9.1 Parent Question

```text
Q-STUDY-01
question:
  为了两个月后的期末考试和之后仍能使用这些知识，
  应该怎样组合重读、概念图、提取练习与间隔复习？
kind: decision-facing
home_placement: G-STUDY / 选择学习活动
why_it_matters:
  决定有限复习时间怎样分配，并避免只优化当下熟悉感。
applicability:
  decision_objective: delayed retention + explanation + transfer
  desired_retention_horizon: 8 weeks and beyond
  material_type: chapters + lecture notes + open questions
  assessment_target: closed-book recall + inferential use
  time_constraint: 5 × 45 min per week
  excluded: medical advice, task scheduling
pursuit: active
resolution: unresolved → provisionally_resolved
```

## 9.2 四个 required Subquestions

| ID | 问题 | parent criterion | 初始结果 |
|---|---|---|---|
| Q-SUB-1 | 哪种活动在当前证据下更能支持延迟保持？ | C1 activity role | sufficiently answered for current purpose |
| Q-SUB-2 | 相对 8 周目标，复习应怎样分布？ | C2 temporal structure | partially answered；没有唯一日数 |
| Q-SUB-3 | 怎样检查能否迁移到新的推理问题？ | C3 transfer check | sufficiently answered at principle level |
| Q-SUB-4 | 概念图在组合中承担什么角色？ | C4 structural synthesis | provisionally answered；保留 method critique |

父问题使用 `blocking_requirement` 只要求四项都达到当前目的所需的最低 coverage；它不要求所有子问题永久 resolved。

## 9.3 Parent Resolution Criteria

```text
C1: 为四种学习活动分配不互相替代的作用
C2: 给出与 8 周目标一致、但不伪装成唯一最优天数的间隔原则
C3: 同时定义延迟保持与新问题迁移的检查方式
C4: 解释概念图的价值和不能替代的责任
C5: 每个主要判断可回到 Knowledge / Source conditions
C6: 明确剩余未知与适用范围
```

## 9.4 Context Question

```text
Q-CONTEXT-01
question:
  换一个环境复习，一定会降低考试时的回忆吗？
kind: explanatory + evaluative
resolution:
  sufficient_for_current_purpose
adopted_answer:
  不一定。特定研究显示环境匹配可以影响回忆，
  但综合证据也显示该效应受加工方式等条件影响；
  不能从潜水员词表实验推出“必须在考试教室复习”。
basis:
  K-M10, K-M11, K-M12
```

这是独立 Question，不是 parent 的第五个子问题，因为它不阻塞学习策略决定，且可以被单独理解和复用。

---

# 10. Ask：从范围不足到可检查综合

## 10.1 Run A — 只问策略群

```text
Requested Context:
  G-STUDY
Expansion Policy:
  ask before expanding
```

系统发现 G-STUDY 拥有 K-S1 至 K-S3 和三条 shared placements，但比较提取、间隔与迁移所需的核心 Evidence 主要位于 G-MEM。

它不能静默全库检索，也不能直接说“知识库没有”。正确结果：

```text
当前范围能说明你已经采用的策略骨架，
但不足以核验提取、间隔和迁移的研究依据。
是否把本次范围扩展到「记忆与学习科学」？
```

用户确认后，只改变本次 Run 的 Effective Context。

## 10.2 Run B — 扩展后的 Context ledger

| 层 | 内容 |
|---|---|
| Requested | G-STUDY |
| Effective | G-STUDY + G-MEM |
| Used Knowledge | K-M1–K-M9、K-S1–K-S3 |
| Used Sources | S-M1、S-M2、S-M3、S-M4、S-M8、S-M9、S-M10 |
| Not used | context-memory branch K-M10–K-M12；与本问无直接需要 |
| Coverage | sufficient for a provisional strategy; not sufficient for universal optimization |

## 10.3 Answer v1 的可读结构

### 先给结论

在本问题的两个月保持、解释与迁移目标下，不应把四种活动排成一个无条件榜单。更合理的是分配不同责任：重读用于首次理解和错误后的定向再学习；提取练习用于生成式回忆与检查；间隔决定这些提取在多个时点重复；概念图用于结构综合和发现连接缺口。

### 为什么不是“最强方法排名”

S-M1 与 K-M4 说明即时表现和延迟保持可能给出不同排序；S-M9 的 retrieval-versus-concept-mapping 结果受具体学习与测验条件约束；S-M10 要求对其泛化保持谨慎。因此回答不能写成“研究证明概念图没用”。

### 当前策略

1. 每个章节首次阅读后，写出 3–7 个需要主动生成答案的关键问题；
2. 不看材料作答，再核对并对错误做定向再学习；
3. 在多个时间点重新提取，间隔随最终保持目标调整，而不是固定套用一个数字；
4. 在完成若干概念的独立提取后，用概念图组织它们之间的因果、组成、对照和限定；
5. 用延迟简答与未见过的推理题检查结果；不要只看当天正确率。

### 仍不知道什么

- 课程每章的概念密度；
- 期末题型与评分权重；
- 是否有高质量反馈答案；
- 用户能持续承受的单次提取难度；
- 在这一具体课程中的实际延迟结果。

## 10.4 Claim Support

每一段主要结论都可展开：

| Answer Claim | basis | conditions shown |
|---|---|---|
| 即时表现不等于长期学习 | K-M1、K-M4、S-M1、S-M4 | outcome + delay |
| 提取可用于延迟保持 | K-M2、K-M3、S-M1、S-M2 | task + comparator + delay |
| 间隔应相对保持目标解释 | K-M5、K-M6、S-M3 | retention interval |
| 提取可支持新推理题迁移 | K-M7、S-M8 | assessment + transfer distance |
| 概念图不应被宣布无用 | K-M8、K-M9、S-M9、S-M10 | procedure + critique |

## 10.5 五个原子动作

Answer 尾部不是一个含糊的`保存并应用`：

1. `保存本次回答` → 只建立 Answer Snapshot；
2. `形成学习目标` → 草拟 / 确认 K-S1；
3. `形成组合策略` → 草拟 / 确认 K-S2；
4. `形成概念图角色` → 草拟 / 确认 K-S3；
5. `采纳为当前回答` → 建立 parent adopted Resolution，并保持 pursuit active。

每一步可单独完成、撤销或稍后处理。保存回答不会自动形成三条 Knowledge，也不会自动解决 Question。

---

# 11. Adopted Resolution 与后续修订

## 11.1 Parent adopted Resolution v1

```text
resolution_state: provisionally_resolved
pursuit_state: active
adopted_at: 2026-08-10
applies_to:
  8-week exam horizon
  chapter and lecture-note materials
  recall + explanation + inferential transfer goals
satisfied_criteria:
  C1, C2-at-principle-level, C3, C4-provisional, C5, C6
remaining_unknowns:
  course-specific optimal spacing
  sustainable question volume
  final exam format
review_triggers:
  assessment format changes
  user time constraint changes
  course result evidence arrives
  major basis claim receives applicable challenge
```

`provisionally_resolved + active`不是自相矛盾：当前回答足够指导下一版策略，同时用户仍在追踪实际课程结果与更具体条件。

## 11.2 S-M10 到来时发生什么

1. 新 Source Revision 与 Fragment 被保存；
2. 系统发现它指向 S-M9 的比较解释；
3. 生成 Evidence Binding proposal：`S-M10 challenges K-M8`；
4. 用户查看 challenge dimension 与原研究条件；
5. 用户接受 Binding，并把 K-M8 从宽泛标题修订为 bounded statement；
6. K-M9 由用户显式形成，保存比较研究的解释纪律；
7. K-S3 的 basis 更新，但正文核心角色不必改变；
8. parent criterion C4 进入 `review_due`；
9. AI 给出 Answer v2，仅重写受影响部分；
10. 用户采纳 Resolution Revision v2；Question identity 不变。

## 11.3 什么不会发生

- 不把 S-M9 标记为“已被推翻”；
- 不自动创建`concept mapping contradicts retrieval practice`；
- 不删除旧 Answer Snapshot；
- 不把所有依赖 retrieval practice 的 Knowledge 设为 review_due；
- 不重开与 concept mapping 无关的 C1–C3；
- 不创建 successor Question，因为决策目标没有改变。

## 11.4 何时才需要 successor

若目标改为“下周的开卷事实查找测验怎样取得最高分”，结果时点、assessment 与主要活动均发生实质变化。旧 Resolution 无法合理映射到新 criteria，应创建 successor 或 scope fork，而不是无痕改写 Q-STUDY-01。

---

# 12. 群级关系与 Pair Comparison

## 12.1 Current Relation A

```text
GR-FOUNDATION-01
statement:
  「记忆与学习科学」为「个人学习策略设计」中
  对延迟保持、迁移、提取与间隔的核心判断提供理论与证据基础。
type: provides_foundation_for
type_standing: experimental label; intent family = Support / Explain
direction: G-MEM → G-STUDY
foundation_kind: theory + principle + evidence_base
foundation_scope:
  learning/performance distinction, retrieval, spacing, transfer
target_dependency:
  K-S1 evaluation goal and K-S2 rationale
support:
  K-M1→K-S1; K-M2/K-M5/K-M7→K-S2 and criteria
standing: maintained / current
```

移除 G-MEM 的基础后，K-S1 / K-S2 仍可作为个人偏好存在，但它们为何这样安排的核心解释会失去依据，因此满足 foundation dependency。

## 12.2 Current Relation B

```text
GR-METHOD-01
statement:
  「个人学习策略设计」当前实际采用了
  「记忆与学习科学」中的提取练习与间隔学习方法。
type: provides_method_for
type_standing: experimental label; intent family = Apply / Implement
direction: G-MEM → G-STUDY
method_ref_or_scope:
  K-M2 retrieval practice + K-M5 spacing
target_use_scope:
  K-S2 composite strategy
use_state: current
adoption_evidence:
  K-M2 component_of K-S2
  K-M5 component_of K-S2
  K-S2 user-adopted fixture revision
standing: maintained / current
```

若 K-S2 只提到提取与间隔而未实际采用，本关系不成立，只保留 exits 或 `applies_to` Candidate。

## 12.3 为什么两条关系可以共存

`provides_foundation_for`回答“为什么目标群的核心判断有依据”；`provides_method_for`回答“目标群实际采用了什么可重复方法”。二者使用部分相同路径，但 statement、qualifiers、removal result 与生命周期不同。

Pair UI 可以把同 pair 的两条边 bundle 成`2 条当前关系`，但展开后必须保留两个 identity，不能显示为`相关`。

## 12.4 被拒的 complements Candidate

系统曾建议：

```text
「记忆与学习科学」与「个人学习策略设计」互相补充。
```

用户拒绝，理由：

- 两群确实共同服务“形成有效学习理解”，但贡献不是对称；
- 当前更准确的是 G-MEM 向 G-STUDY 提供基础与方法；
- `complements`没有增加非冗余语义；
- 拒绝 Candidate 不删除 shared observations 或 paths。

## 12.5 Pair Comparison 的真实信息顺序

### Pair Orientation

- 左：G-MEM，理解机制、研究结果与边界；
- 右：G-STUDY，形成目标、活动组合与评估策略；
- 当前 snapshot：两群 current Boundary / Overview / Relation inventory 同一时点。

### Current Relations

1. 提供理论与证据基础；
2. 提供当前实际采用的方法。

### Shared Knowledge

3 条：K-M1、K-M2、K-M5。展开显示两侧 Placement 与 contextual summary，不显示 Adopt / End。

### Paths

- K-M7 → K-S1：迁移证据支撑目标；
- K-M2 → K-S2：提取成为组成方法；
- K-M5 → K-S2：间隔成为时间结构；
- K-M9 → K-S3：方法比较纪律限定概念图角色。

同一 Knowledge 的两侧 Placement step 与同一 Source lineage 必须 collapse，不能把 3 个 identity 展开成 12 条“独立支持”。

### Suggested / Unknown

- `complements`：rejected；
- `partially_overlaps_with`：not eligible；Boundary 有关联但 governing purpose 与 material boundary 不同，共享三条 Knowledge 不等于范围重叠；
- index：complete for fixture inventory，不代表真实世界文献穷尽。

### Evidence & Limits

- 两条 Current Relation 的 exact support anchors；
- S-M10 对 K-M8 的 challenge；
- `actual use`只覆盖 K-S2 当前 revision；
- 未证明该策略对真实用户产生学习结果。

### History

1. shared observations 首次出现；
2. foundation Candidate 被用户采用；
3. K-S2 被采用后，method Candidate 获得资格并被采用；
4. complements Candidate 被拒；
5. S-M10 到来，foundation relation 的部分 support 更新，但 relation statement 未改变。

## 12.6 exact return

用户从 K-S3 的 basis 行打开 Pair Comparison，当前 primary section 是 Evidence & Limits，selected support path 是 K-M9 → K-S3。关闭后必须返回：

```text
G-STUDY / 选择学习活动 / 概念图与结构综合
Knowledge: K-S3
Anchor: 为什么不把单篇比较外推为“概念图无用”
scroll offset + expanded evidence state preserved
```

不能回到 Library 顶部，也不能只回到 G-STUDY Overview。

---

# 13. 二十七步端到端旅程

1. 用户从 Library 打开 `G-MEM`，普通 open 进入 Group Overview，不自动恢复上次深层位置。
2. Overview 用“结果—提取—时间—线索”四个方向建立整体认识。
3. 用户进入`怎样判断真的学会了`，阅读 K-M1 与 K-M4。
4. 用户沿层级进入`提取如何改变学习 / 提取练习`，打开 K-M2。
5. 关系 Companion 显示 K-M3、K-M4、K-M7；Evidence 仍按需展开。
6. 用户核验 S-M1，看到即时与延迟测验时点，而非一句“测试更好”。
7. Back 精确回到 K-M2 原 Anchor 与 relation radius。
8. 用户沿 K-M5 进入间隔分支，阅读 K-M6 对固定间隔神话的限定。
9. 用户打开 Library Network，只看 Group-level Current / Candidate standing；此时两群尚未有 method relation。
10. 用户进入 `G-STUDY` Overview，看到策略骨架及 provisional 限制。
11. 从 G-STUDY 打开共享 K-M2；正文 identity 不变，Placement context 与返回位置改变。
12. 用户提出 Q-STUDY-01；Question 保存为 active + unresolved。
13. AI 建议四个 required Subquestions；用户逐条确认，而非一次自动拆解后静默保存。
14. 用户从 Q-STUDY-01 发起 Ask，Requested Context 只有 G-STUDY。
15. 系统说明证据覆盖不足，请求扩展到 G-MEM；用户确认本次扩展。
16. Answer 区分结果维度、四种活动角色、研究条件与剩余未知。
17. 用户先保存 Answer Snapshot；Question 与 Knowledge 状态都不改变。
18. 用户分别形成并确认 K-S1、K-S2、K-S3。
19. 用户分别确认 KR-04 至 KR-08；系统不把 basis 自动变成 ordinary Relations。
20. 用户采纳 parent Resolution v1：provisionally_resolved + active。
21. foundation Candidate 以完整 statement、方向、范围与 support 被采用为 GR-FOUNDATION-01。
22. 因 K-S2 已实际采用 K-M2 / K-M5，method Candidate 通过资格；用户采用 GR-METHOD-01。
23. 用户在 Network 选择两群的 relation bundle，打开 Pair Comparison，看见两条 Current 与三条 Shared observations。
24. 用户拒绝宽泛 complements Candidate；Current relations 与 observations 不受影响。
25. 后来加入 S-M10；系统提出 Evidence challenge 与 affected criterion，不自动创建 Conflict。
26. 用户收窄 K-M8、形成 K-M9、更新 K-S3 basis，并采纳 Resolution v2。
27. 用户从 Pair Evidence 返回 K-S3 原 Anchor；所有临时 pair filter 关闭，但 exact origin 恢复。

这条旅程证明：方向 3 的 Overview → Topic → Knowledge → Claim → Evidence 是主阅读骨架；方向 2 的 Shared / Relation / Pair / Path 是按需横向空间。二者通过同一对象 identity 与 Return Envelope 连接，而不是并排存在的两个产品。

---

# 14. Screen 2 / 3 的真实内容证明要求

本文不画 Screen，但冻结未来必须被看见的内容压力。

## 14.1 Screen 2：层级阅读必须证明

1. `学习与当下表现`、`延迟保持`、`迁移`同时存在，不能压成三张同权卡；
2. K-M8 的长标题和“在研究条件下”限定不被截成误导性结论；
3. 同一 K-M2 从两个 Placement 进入时，canonical body 不变、语境可辨；
4. Answer 可以连续阅读，但每个主要 Claim 可展开 basis / conditions；
5. 四个 Subquestions 的不同状态能在父问题中汇总，且不变成任务清单；
6. adopted Resolution、pursuit 与 review_due 不靠状态码让用户猜；
7. Evidence critique 只标记受影响 Claim / criterion，不制造整页警报。

## 14.2 Screen 3：关系空间必须证明

1. 同一 Group pair 的两条 Current Relations 可选择、可读、方向明确；
2. Shared Knowledge Lens 显示 3 条 identity，且不伪装为 edge；
3. Paths 能区分 formal Relation、Placement step、Evidence 与 retrieval jump；
4. rejected complements 与 Current 不混排；
5. K-M9 → K-S3 的限定路径可以被检查；
6. 关闭 Pair 能精确回到 K-S3 的 basis Anchor；
7. List / keyboard / narrow screen 提供完全相同的 relation inventory 和判断动作。

## 14.3 不合格的视觉证明

- 用“记忆”“学习”“方法”三个圆和几条线代替真实 statement；
- 把论文封面或 citation count 当知识层级；
- 把三条 shared Knowledge 画成三条正式 Group edges；
- 只展示最短标题，不展示限定、challenge 与 provisional；
- 用不同颜色代替 foundation / method 的完整句与方向；
- 从图进入正文后 Back 回到默认 Library；
- 为了视觉干净删除 Subquestion、Evidence limit 或 rejected candidate。

---

# 15. 失败、离线与维护状态

## 15.1 索引不完整

若 S-M10 尚未解析，Pair Comparison 仍显示两条 Current Relations，但 Evidence & Limits 写：

```text
有 1 份已保存来源尚未完成索引。
当前关系可读；“没有其他挑战”这一结论暂不可确认。
```

## 15.2 AI unavailable

用户仍能：

- 浏览两群 Overview 与 Topic tree；
- 打开 15 条 Knowledge；
- 读取 11 条 Knowledge Relations；
- 查看 3 条 shared observations 与 2 条 Current Group Relations；
- 手工编辑 Question、criteria 与 Resolution draft；
- 沿 Evidence locator 核验本地快照。

不能因为 AI 不可用而让知识库变成文件列表。

## 15.3 离线

使用本地 current revisions、Source snapshots 与 index。无法刷新出版方页面时显示`当前离线，使用 2026-08-10 核验快照`，不能写成来源不存在或研究已失效。

## 15.4 Source 无法核验

Source verification state 与 Claim standing 分开。无法打开 DOI 页面会触发核验提示；它不自动删除旧 Fragment、Knowledge 或 Resolution。

## 15.5 Graph unavailable

自动进入 Pair List：Current → Shared → Paths → Suggested / Unknown → Evidence & Limits → History。所有关系判断与 exact return 仍成立。

## 15.6 研究条件缺失

若某 Claim 缺少 comparator 或 outcome delay，Answer 必须写：

```text
这份来源支持方向性理解，但目前保存的信息不足以与延迟保持研究直接比较。
```

不允许模型补造实验条件。

---

# 16. 由夹具触发并已进入 v6 的产品责任

## 16.1 已吸收进 v6 Canonical 的责任

1. 第二真实夹具是对“知识库普适性”的证明，不是新学习场景模块 → v6 §0、§3；
2. 决策型 Question 的 Applicability 支持 objective、retention horizon、assessment / transfer target、material type 与 constraints → v6 §6.6；
3. research comparison 的条件快照属于 Source / Evidence 支持身份 → v6 §6.7；
4. same-pair multi-relation、shared observation 与 exact return 必须进入视觉 Gate → v6 §7、§11、§13；
5. 稳定策略是 procedural Knowledge，计划执行不进入产品中心 → v6 §4、§16。

以下 16.2–16.6 保留的是 Question、Source / Evidence、Placement、Pair 与语言的细化候选。它们在与 v6 当前术语、四类真相和六个关系意图族完成逐项对齐前属于 Migration Queue；夹具不能独立形成第二套 Canonical。

## 16.2 Question 合同必须吸收

- QuestionFrame 的 applicability 可结构化表达 decision objective 与 outcome horizon；
- parent Resolution 按 criteria / Subquestions 汇总，不以 resolved 数量投票；
- context / assessment 实质变化可能产生 successor；
- adopted provisional answer 可以继续 active pursuit。

## 16.3 Source / Evidence 合同必须吸收

- 可选 `StudyConditionSnapshot`；
- Evidence critique 的 target、dimension 与 effect；
- `challenges` Binding 不自动变成 ordinary Relation 或 Conflict；
- research source type 不变成权威 rank。

## 16.4 Placement 合同必须吸收

- 同一 Knowledge 在不同 Placement 可有不同 contextual summary、role、neighbor priority 与 Return Envelope；
- canonical body、Revision、Evidence 与 identity 必须相同；
- shared identity 与 lexical similarity 分开。

## 16.5 Group relation / Pair 合同必须吸收

- 同一 pair 的 `provides_foundation_for + provides_method_for` 真实 fixture；
- method relation 要求 target actual-use evidence；
- shared Knowledge collapse 不计为独立 support units；
- rejected Candidate 在 History 可解释，但不污染 Current。

## 16.6 产品语言必须吸收

推荐默认写法：

- `在这项研究及其任务条件下……`；
- `这项结果支持……，但不能单独推出……`；
- `该评论挑战的是比较方法与外推范围，不等于整项结果已被推翻`；
- `当前回答足以指导这版策略；课程题型与实际延迟结果仍待补充`；
- `同一知识在两个知识群中承担不同作用`；
- `两个知识群当前有 2 条正式关系，并共享 3 条同一知识`。

禁止默认写法：

- `研究证明`；
- `最佳学习法`；
- `可信度 93%`；
- `10 篇论文一致认为`；
- `概念图已被推翻`；
- `共享 3 个节点，所以两个群相关`。

---

# 17. Given / When / Then 验收

## 验收 1：Overview 从结果定义进入领域

**Given** 用户普通打开 G-MEM  
**When** Overview 加载  
**Then** 先解释 performance / retention / transfer 的区别，再给四个深入方向；不先展示论文流或全图。

## 验收 2：真实三层 Topic 深度

**Given** 用户从 Group Overview 进入提取主题  
**When** 连续打开 Topic 与 Knowledge  
**Then** DepthTrail 至少表达 Group → Topic → Subtopic → Knowledge，且 Up / Back 语义不同。

## 验收 3：同一 Knowledge 双 Placement

**Given** K-M2 位于两个 Groups  
**When** 分别从两侧打开  
**Then** body / revision / evidence identity 相同，contextual summary、neighbors 与 return target 不同。

## 验收 4：共享观察不创建关系

**Given** K-M1、K-M2、K-M5 各有双 Placement  
**When** 打开 Shared Knowledge Lens  
**Then** 显示 3 条 observation；Relation count、Current inventory 与 resting layout 不改变。

## 验收 5：词面相似不合并

**Given** 学习活动 concept mapping 与产品 relation network 词面相关  
**When** identity resolver 评估  
**Then** 不自动 merge；显示不同 governing task 与 source lineage。

## 验收 6：研究 Claim 保留条件

**Given** Answer 使用 S-M1  
**When** 用户查看“提取支持延迟保持”  
**Then** 可见 material、comparator、outcome 与 delay；不只显示论文标题。

## 验收 7：即时表现不冒充长期学习

**Given** 来源同时包含 5 分钟与一周结果  
**When** AI 综合  
**Then** 分开陈述，不能压成统一“效果更好”。

## 验收 8：间隔不伪装成固定公式

**Given** Question 的目标时点为 8 周  
**When** AI 使用 K-M6  
**Then** 给原则与待校准条件，不捏造唯一最优天数。

## 验收 9：范围不足时请求扩展

**Given** Requested Context 只有 G-STUDY  
**When** 主要依据在 G-MEM  
**Then** 说明不足并请求 per-run expansion；拒绝时仍给 bounded answer。

## 验收 10：Context ledger 可检查

**Given** 用户确认扩展  
**When** Answer 完成  
**Then** Requested、Effective、Used 与 Not used 可分别检查。

## 验收 11：父问题不被自动拆解污染

**Given** AI 建议四个 Subquestions  
**When** 用户尚未确认  
**Then** 它们保持 proposal；不会自动建立四条 persistent Questions。

## 验收 12：子问题独立状态

**Given** Q-SUB-1 resolved、Q-SUB-2 partial  
**When** 查看 parent  
**Then** 分别投影其状态；不把父问题标为 resolved。

## 验收 13：criteria 汇总不是多数投票

**Given** 三个子问题充分、一个 blocking criterion 未满足  
**When** 计算 parent proposal  
**Then** 不因 3/4 多数自动 resolve；按 criterion mapping 解释。

## 验收 14：保存回答不形成知识

**Given** Answer v1 完成  
**When** 用户只点保存回答  
**Then** 仅建立 Answer Snapshot；K-S1–K-S3、Relation 与 Resolution 均不改变。

## 验收 15：原子形成三条知识

**Given** Answer 含目标、策略与概念图角色  
**When** 用户只接受 K-S2  
**Then** K-S2 成为 current，K-S1 / K-S3 仍是 proposal；不存在`全部保存并解决`。

## 验收 16：provisional 与 active 共存

**Given** 当前策略足够使用但课程题型未知  
**When** 用户采纳 Resolution  
**Then** state=`provisionally_resolved + active`，并列出 remaining unknowns。

## 验收 17：技术评论先形成 challenge

**Given** S-M10 到来  
**When** 系统匹配到 K-M8  
**Then** 提议 Evidence Binding `challenges`，不自动建立 `contradicts` 或 Conflict。

## 验收 18：只复核受影响 criterion

**Given** challenge 只影响 concept-mapping comparison  
**When** impact analysis 完成  
**Then** C4 review_due；C1–C3 保持 adopted standing。

## 验收 19：收窄不等于撤回

**Given** K-M8 原文过宽  
**When** 用户加入 study-condition qualifier  
**Then** 创建 Knowledge Revision；旧 Revision 可读，不标成 false / retracted。

## 验收 20：研究评论不会自动成为 Knowledge

**Given** S-M10 已保存并 challenge K-M8  
**When** 用户未执行形成动作  
**Then** K-M9 不存在；只有用户接受可复用解释后才建立。

## 验收 21：foundation 与 method 同时成立

**Given** G-MEM 同时提供理论基础且 K-S2 实际采用 K-M2 / K-M5  
**When** 查看 pair inventory  
**Then** 显示两条 Current Relations，statement / qualifiers / lifecycle 独立。

## 验收 22：提到方法不够

**Given** target 只在 Overview 提到 retrieval practice  
**When** 评估 provides_method_for  
**Then** 不通过；至少需要 actual-use anchor 与 adopted target revision。

## 验收 23：宽泛 complements 可被拒

**Given** foundation / method 已准确表达 pair  
**When** 系统又建议 complements  
**Then** 用户可因语义冗余拒绝；拒绝不结束 Current relations。

## 验收 24：Pair information order

**Given** 两群有 Current、Shared、Paths、Rejected 与 History  
**When** 打开 Pair Comparison  
**Then** 顺序为 Orientation → Current → Shared → Paths → Suggested / Unknown → Evidence & Limits → History。

## 验收 25：support unit collapse

**Given** K-M2 / K-M5 各有双 Placement 且共享 Source lineage  
**When** 计算 relation support  
**Then** 按 canonical Knowledge / independent source units 去重，不按每个 Placement 重复计票。

## 验收 26：exact return

**Given** 用户从 K-S3 的 basis Anchor 进入 Pair  
**When** 关闭 Comparison  
**Then** 回到同一 Knowledge、Anchor、scroll 与 disclosure state。

## 验收 27：Graph / List 同义

**Given** Graph unavailable 或用户只用键盘  
**When** 查看 pair  
**Then** List 提供相同 2 Current、3 Shared、paths、rejected candidate、limits 与 actions。

## 验收 28：程序知识不扩张成任务系统

**Given** 用户采纳 K-S2  
**When** 需要安排下周练习  
**Then** 知识库保存方法与可导出的安排建议；具体任务需显式发送到外部任务 / 日历，不在本体内生成待办中心。

## 验收 29：离线保持知识可用

**Given** 无网络与 AI  
**When** 用户打开 G-MEM / G-STUDY  
**Then** local Overview、Knowledge、Relations、Questions、Source snapshots 与 Pair List 可读。

## 验收 30：来源不可核验不删除真相历史

**Given** DOI 页面暂时无法访问  
**When** verification 失败  
**Then** 标记 source verification，不删除 Fragment、Knowledge、Relation 或 adopted Resolution。

---

# 18. 结构演化压力场景

本节使用当前 fixture identities 做可逆的 hypothetical transaction，不改变第 2 节的 current snapshot。

## 18.1 SX-01 · 将 Topic「提取如何改变学习」Promotion 为 Group

只有当用户确认它将被反复整体进入、需要独立 Boundary / Overview，并需要与其他 Groups 表达整体 Relation 时，Promotion Candidate 才成立。

### Preview

```text
new Group candidate:
  G-RETRIEVAL / 提取练习、反馈与再学习

source Topic:
  G-MEM / 2. 提取如何改变学习

subtree:
  2.1 提取练习
  2.2 重复学习与重复测试
  2.3 反馈、错误与再学习

affected Knowledge placements:
  K-M2, K-M3, K-M4 and directly scoped neighbors

not copied:
  Knowledge bodies, Sources, Evidence Fragments, Knowledge Relations

review required:
  G-MEM Overview entrances
  G-MEM → G-STUDY Group Relation support coverage
  Saved Paths crossing old Topic path
```

### Commit

- 建立 G-RETRIEVAL Group identity 与 Boundary draft；
- 三个 Subtopics 事务性迁移到新 Group；
- source Topic identity 进入 redirected History，不继续作为 G-MEM 的 active Topic；
- affected Placements 改 owner，不新增 Knowledge copies；
- old deep links 打开 historical path 并跳到 new current path；
- 原 Topic orientation 只成为新 Overview Proposal，不自动变成 Current prose；
- G-MEM 保留明确 cross-group exit；“G-RETRIEVAL 是 G-MEM 的 focused subdomain”只有在完整 statement、scope 与用户采纳后才成为 Group Relation；
- 现有 G-MEM → G-STUDY 两条 Relations 不自动改 endpoint，先检查其有效 support 是否仍覆盖 G-MEM Boundary。

### Cancel / failure

取消或任一子步骤失败时，Groups、Topics、Placements、Overview、Relations 和 Paths 全部保持原 snapshot；不得出现新 Group 已建立但 Placements 仍留在旧 Topic 的半提交。

## 18.2 SX-02 · Absorb 回原 Group

若长期使用证明 G-RETRIEVAL 不需要独立 Boundary、Overview 或 Group Relations，可以显式 Absorb：

- 选择 G-MEM 中的目标 Topic path；
- 将三条 Topic branches 和 Placements 迁回；
- G-RETRIEVAL Group Relations 逐条 End / Redirect / Preserve on successor；
- G-RETRIEVAL identity 进入 redirected / archived History；
- 两份 Overview prose 不自动拼接；
- old G-RETRIEVAL links 仍能解释当时 Scope。

## 18.3 SX-03 · 不成立的 Merge

`G-MEM + G-STUDY`不应仅因 3 条 shared Knowledge、11 条 Knowledge Relations 和 2 条 Group Relations 自动 Merge：

- 两群 governing questions 不同；
- 一个解释研究与机制，一个保存策略判断；
- same-pair Relations 正好证明独立边界之间有真实联系，而不是边界应消失；
- Merge 会把 Overview、research conditions 与 procedural context 混在一起。

系统可以提供 Pair Comparison，但不产生 Merge Candidate。

## 18.4 SX-04 · 不成立的 cross-Group Topic Move

`G-STUDY / 3.1 间隔原则`不应因为依据来自 K-M5 / K-M6 就被自动 Move 到 G-MEM：

- Topic 在 G-STUDY 中承担“怎样安排策略”的 procedural context；
- K-M5 / K-M6 已可通过 Placements 和 Relations 在两群复用；
- 移动 Topic 会丢失它在策略结构中的阅读作用。

若用户希望在 G-MEM 中也有入口，正确动作是给相关 Knowledge 增加 Placement 或建立具体 exit，不复制 Topic tree。

## 18.5 SX-05 · Archive 与 Delete G-STUDY

Archive G-STUDY：

- 所有 Placements 仍 active；
- 其 Knowledge 不涌入独立知识；
- G-MEM → G-STUDY Relations 显示 archived endpoint，但不自动 End；
- Search 与 History 可打开 archived context；
- Restore 保持 identities、paths 与 current statements。

Delete G-STUDY 则必须逐类预览：

- K-S1–K-S3 及 shared Knowledge Placements 是 Move、End 还是保留到 successor；
- 结束最后 active Placement 的 Knowledge 才进入独立知识；
- 两条 Group Relations 是 End 还是 Redirect；
- Overview prose、Questions、Resolutions 与 Saved Paths 怎样保留；
- Source identities 不因 Group delete 被删除。

## 18.6 结构演化验收

1. Promotion 不复制 Knowledge、Sources 或 Relations；
2. old Topic path 可以解释并 redirect；
3. Group Relation endpoint 不因结构变化静默重写；
4. Overview Proposal 不冒充 Current prose；
5. Cancel / partial failure 零副作用；
6. shared Knowledge 与 existing Relations 不自动触发 Merge；
7. procedural context 优先于“来源在哪个群”的机械 Move；
8. Archive Group 不制造独立知识洪水，Delete 必须逐类结算。

---

# 19. 仍待真实用户验证

本夹具证明对象与合同能承载内容，不证明实际可用性。仍需验证：

1. 用户是否能理解同一 Knowledge 在不同 Group 的语境不同但正文相同；
2. Shared Knowledge Observation 与正式 Group Relation 是否能用普通语言稳定区分；
3. “在这项研究及这些条件下”是否足够醒目，又不会让正文像论文数据库；
4. 父问题、四个子问题与 criteria 是否会被误解为项目任务；
5. `provisionally_resolved + active`的人话表达是否自然；
6. 两条 same-pair Current Relations 是否可读，还是会被误认为重复；
7. technical comment → challenge → scoped revision 是否能在不引发警报疲劳的情况下被理解；
8. 方向 3 的长阅读与方向 2 的关系 Companion 应以什么比例共存；
9. exact return 在连续探索中是否真的降低迷失；
10. 真实课程材料增长到数百条 Knowledge 后，Overview 与 shared identity 是否仍清楚。

---

# 20. 最终判断

第二个真实主题证明：这套产品不是资格规则查询器，也不需要为学习主题建立一个新模块。它仍然是同一个个人知识库。

用户拥有的是两个边界清楚、层级丰富的知识群；可以从 Overview 沿 Topic 深入到长 Knowledge 与具体 Evidence；同一 Knowledge 可以在不同知识群承担不同角色而不复制；三条共享知识可以被观察，但不会被误画成群关系；AI 能在显式范围内比较研究、保留条件、形成可复用理解；父问题和子问题保存尚未解决的知识；两条同 pair 的正式关系分别表达理论基础与实际方法；方法学评论通过 challenge 和局部 Revision 改善理解，而不是制造“论文互相打脸”的噪音。

因此方向 3 + 2 的产品含义进一步收敛为：

> **方向 3 是知识的默认阅读形态：从 Overview 到层级、正文、主张和证据；方向 2 是在需要比较、迁移和发现联系时出现的关系空间。二者共享同一知识身份、来源与返回链，关系空间永远不取代阅读。**

本夹具是产品定义与未来设计的输入，不是原型，也不授权开始画界面。
