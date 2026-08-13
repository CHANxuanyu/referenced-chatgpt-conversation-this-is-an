# AI-native 个人知识库

## v6 需求、旅程、验收与设计证据追踪矩阵 v1.0

> 日期：2026-08-10  
> Canonical：`AI-native-个人知识库-终局产品设计文档-v6.0.md`  
> Active Appendices：`AI-native-个人知识库-知识群层级、目录规模与结构演化合同-v1.0.md`、`AI-native-个人知识库-AI查询、知识探索与返回连续性合同-v1.0.md`、`AI-native-个人知识库-知识进入、来源保存与知识形成合同-v1.0.md`、`AI-native-个人知识库-关系、群级网络与探索连续性合同-v1.0.md`、`AI-native-个人知识库-Overview、连续阅读与知识正文合同-v1.0.md`、`AI-native-个人知识库-Library入口、目录浏览与继续阅读合同-v1.0.md`、`AI-native-个人知识库-表面架构、场景家族与完整设计证明合同-v1.0.md`、`AI-native-个人知识库-用户可见信息架构、产品语言与复杂度披露合同-v1.0.md`  
> Fixture A：`AI-native-个人知识库-真实端到端使用样例与设计数据夹具-v1.0.md`  
> Fixture B：`AI-native-个人知识库-第二真实端到端夹具-概念学习、多语境复用与群关系-v1.0.md`  
> Fixture C：`AI-native-个人知识库-基础可用性夹具-空库直接写作搜索与恢复-v1.0.md`  
> 当前设计证据：`design-audit-ardot/library-definition-round-2026-08-10/Ardot-Library与核心表面产品错位审计-v1.0.md`、同目录本轮 Screen 1 / 2 / 3 / 七屏总览截图，以及`AI-native-个人知识库-v6用户可见语言迁移审计-v1.0.md`；历史审计仅作补充  
> 本轮边界：只收敛产品定义与证据追踪；没有写入 Ardot、没有制作新 Frame、没有制作原型

---

# 0. 结论

v6 已经从“完整的产品主张”推进到一套可追踪、可被真实内容反驳的产品合同：九项用户意图、十一条核心旅程和三十二条核心验收，均能找到定义位置、夹具压力来源与专项合同。Add 不再被当作一个笼统流程；Overview、Topic Opening 与 Knowledge Paper 也不再只是“从概览到细节”的口号；Library 入口也不再只是“放一张 Catalog”。本轮进一步关闭了 Page list 与产品表面系统之间的缺口：一个 App Shell、五个 Scene families、六类 Surface roles、Return Envelope 与 DPB-01–18 已拥有现行合同；同时关闭了内部精确模型与用户可见语言之间的缺口，冻结一个`知识库`、五个日常内容概念、三个全局动作、LPX-01–18 与 LAC-01–32。

但必须严格区分三种完成度：

1. **产品定义覆盖：较强。** 三份夹具共同覆盖空库与直接写作、时效资格判断、稳定概念学习、多语境复用、关系探索、Ask、Source change、离线和恢复。
2. **静态视觉证据覆盖：弱。** 当前 Ardot 七屏全部只是 Visual Specimens，没有一项能完整证明 AC-01–AC-32 或 DPB-01–18；Screen 2 只提供方向 3 + 2 的视觉母体，Screen 3 只保留 Relation Night 艺术气质。
3. **交互与运行证明：尚不存在。** exact return、键盘、读屏、响应式、持久化、失败恢复和 clean restore 不能由静态截图证明。

因此当前可以继续确认产品定义，但不能宣称“产品设计已完成”，也不应在旧七屏上继续补按钮来伪造覆盖。

---

# 1. 追踪规则

## 1.1 证据等级

| 标记 | 含义 |
|---|---|
| **S** | fixture 内有完整对象、状态、步骤和明确结果，足以压力测试语义合同 |
| **P** | fixture 或设计只覆盖局部责任，不能独立证明完整旅程 / AC |
| **N** | 当前证据没有证明；不是产品不需要，而是仍欠设计或运行证据 |
| **C** | 当前视觉与产品合同方向冲突，后续必须重构 |

Fixture 只能证明内容、本体、状态与期望后果可表达；静态 Frame 只能证明可见信息与布局；真实交互、持久化和无障碍必须由后续可运行证据证明。

Design Proof Bundle 另使用 `MISSING → SPECIMEN → SEMANTIC → CONTINUOUS → EQUIVALENT → VERIFIED` 成熟度。只有完整 entry / result / failure / recovery / return 链可达到 CONTINUOUS；responsive / keyboard / screen reader 责任等价后才达到 EQUIVALENT；真实运行复核后才可标 VERIFIED。

## 1.2 三份夹具的分工

| 夹具 | 首要压力 | 不重复承担的责任 |
|---|---|---|
| A · 时效资格 | 高后果 Question、Applicability、规则 / 推断 / 机构结果、Source change、跨群 exit、负面群关系 | 不证明空库首用和完整 Search |
| B · 概念学习 | 深层 Topic、同一 Knowledge 多 Placement、研究限定、Question 演化、知识与群关系、Pair / exact return | 不证明空库、直接创作和 clean restore |
| C · 基础可用性 | 空 Library、无来源直接写作、未归群找回、Bare Group、Search、Source partial、离线、export / clean restore | 不重复证明复杂 Ask、Question 和群关系成立 |

---

# 2. 用户原始意图 → 产品定义 → 证明责任

| UR | 用户意图 | v6 定义 | 核心旅程 / AC | Fixture 压力 | 当前 Ardot 证据 | 判断 |
|---|---|---|---|---|---|---|
| UR-01 | 本质上就是一个知识库 | §0、§3 + Library / Language Active Appendices：一个 Stable Personal Knowledge Library；用户可见地点固定为`知识库`；cold start 先到完整目录；Resume / Pins / Recent 不能替代 All Groups | J1、J2；AC-01、02；LPX-01–03；LAC-01–03 | C + LX-01–03 / 11 / 14 强证明空库、daily return 与 degraded Catalog | Screen 1 仍以星图为 Hero，且`知识星图`形成第二中心 | **入口与语言合同成立；视觉冲突** |
| UR-02 | 有一个个知识群 | §5 + Hierarchy / Library Active Appendices：Group 是有边界、可长期演化的知识范围；All Groups 穷尽 Current Groups | J2、J3；AC-01、03–05 | A / B 证明成熟群，C + LX-02 证明 Bare Group | Screen 1 / 2 只有“知识群”字样，没有 Boundary、完整 Catalog 与真实 Overview | **定义成立；视觉仅命名** |
| UR-03 | 群之间可能有可见 relation | §7 + Relation Active Appendix：完整 statement、Candidate / Current / History 分权、群级资格、Pair；没有关系合法 | J8、J9；AC-11–17 | B + RX-05–07 证明 same-pair 双关系与 Shared；A + RX-04 证明 exit 不升级 | Screen 2 / 3 只有节点和装饰线 | **语义合同成立；视觉失败** |
| UR-04 | 从 Overview 深入到细节的丰富层级 | §3.3、§5、§6 + Reading Active Appendix：Overview → Topic Opening → single-tree Knowledge Paper → Anchor / Evidence；同一 Reading Shell、direct deep target、History / Recovery / exact return | J3、J4、J10、J11；AC-04–10、28–30 | A / B 用真实多层内容，C 用 direct edit / recovery / restore 证明 | Screen 2 有阅读气质；Screen 6 有 user-owned 原则，但没有连续 Opening、local outline、Anchor 与状态链 | **完整阅读合同成立；视觉未证明** |
| UR-05 | 可以 AI 查询知识 | §8 + Query Active Appendix：Context、Claim support、Coverage、history、atomic write-back 与 return 分权 | J6、J7；AC-19–24 | A / B + QX-01–12 压力 Ask、Follow-up、citation 与 Question | Screen 5 有长 Answer，但 scope、claim basis、coverage、history 和原子写回不足 | **合同成立；视觉部分** |
| UR-06 | 可以在知识网络里探索 | §3.4、§7、§11 + Query / Relation Active Appendices：Reading 为主，Presentation / Radius 分权，Answer Claim ↔ Explore 可逆 | J6、J8、J9；AC-11–20 | B 正例，A 负例，QX-04 / 05 + RX-07 / 08 / 13 证明路径、无路径与 fallback | Screen 2 提供气质；Screen 3 以全局混合星图表达，方向错误 | **定义成立；交互未证明** |
| UR-07 | 视觉上方向 3 和 2 的结合 | §11 + Surface / Language Appendices：Warm Paper 为连续阅读 Primary，Relation Night 按 Quiet → Peek → Companion → Explore 增长；用户不需要学习 Scene / Surface 模式名 | J8；AC-15–17；DPB-08；LPX-09–11；LAC-12 / 13 | B 的纵向阅读与横向关系共用同一 identity；SX-07–09 压力渐进与降级 | Screen 2 最接近，但永久分栏与`双镜工作区`语言不成立 | **视觉母体可保留；Surface behavior 与语言需重做** |
| UR-08 | 先定义产品，不马上做原型 | §17.3–17.4 + Library / Surface / Language Appendices：先冻结产品选择、Scene / Surface、用户语言与 DPB copy proof，再到 Surface Skeleton、视觉与原型 | 当前工作方式；SEC-30–32；LAC-31 / 32 | 三份 fixtures、LX-01–14、SX-01–16 与 LPX-01–18 已冻结任务、状态、失败、返回和用户表达 | 本轮只捕获并审计当前 Frame；未创建或修改 Ardot | **已遵守** |
| UR-09 | 本地产品，隐私不需要过度设计 | §10.7–10.9：本地所有权是底层责任，不是首页主角 | J11；AC-29、30 | C 强证明离线与 clean restore | Screen 7 把 Storage 暴露成核心主屏 | **责任保留；表面应降级** |

---

# 3. 十一条旅程覆盖

| J | 核心旅程 | A | B | C | 当前 Ardot | 仍欠的设计证明 |
|---|---|---:|---:|---:|---|---|
| J1 | 空库到第一条可返回知识 | N | N | **S**；Formation FX-01；Library LX-01；Language LPX-01 | N；Screen 1 不是空库方案 | DPB-01：Empty → direct Current Commit → 独立知识 / All Knowledge → Library return → reopen；回执为`已保存这条知识`，不能插入 AI 审批 |
| J2 | 建立第一个知识群 | P；已有成熟群 | P；已有成熟群 | **S**；Library LX-02 | P；只有名称 | Bare Group → All Groups → ordinary Open → Bare Overview；Boundary optional，不显示完成度 |
| J3 | 从 Overview 深入到 Evidence | **S** | **S** | P；Reading WX-03 / 05 / 11；Language LPX-05 / 06 | P；阅读气质存在，真实 Opening / Anchor / 返回不存在 | DPB-05 / 06：Group Overview → Topic Opening → long Knowledge → Claim → Evidence → exact return；同一 Reading Shell、single content tree 与自然路径词 |
| J4 | 同一 Knowledge 跨两个 Groups | N | **S**；Reading WX-08 | P；只做 Placement 删除后果 | N | 两个 Group context、同一正文、当地 context、canonical edit scope 与 fork 后果 |
| J5 | Search 深层找回与返回 | N | P；只含找回需求 | **S**；Library LX-07 / 11 | N | Search target / list Filter 分权、All Knowledge multi-Placement entry、exact Anchor、Back envelope、index coverage |
| J6 | 当前 Topic 内 Ask | **S** | **S** | N；Language LPX-10 | P；Screen 5 只有回答外观 | requested / effective / used context、Claim citation、Answer → Explore、Follow-up Delta、close no mutation；先显示提问范围，回答区分知识、来源、外部资料与推断 |
| J7 | Answer / Source 形成知识 | **S**；Formation FX-03–06 | **S**；Formation FX-06 | N | C / P；Screen 4 把保存、抽取和形成合并为审批流 | 分开证明 Source-only、Annotation、Evidence-only、New Knowledge 与 semantic Diff；一项一项原子写回，并 Back to origin Snapshot / Fragment |
| J8 | 沿关系跨群探索 | P；exit 与 exact return；Relation RX-04 / 08 | **S**；Relation RX-05–07 | P；Quiet → Peek / List；Relation RX-01 / 13 / 14；Language LPX-08 / 09 | P；Screen 2 永久展开，Screen 3 全局混合 | DPB-08 / 09：关系先以完整句出现，再`查看 / 在旁边查看 / 在知识网络中打开`；exact return；Scene、Trail、Path 分权 |
| J9 | 建立 Group Relation | **S** 负例：不成立；Relation RX-04 | **S** 正例：两条成立、一条拒绝；Relation RX-05 / 06 | N；Relation RX-01 | N / C；装饰线无 statement、qualification 与 adoption | Signal collapse、Boundary / type / counter / removal gate、Candidate、拒绝零副作用、采纳后 Graph / List 同义 |
| J10 | 新来源改变旧知识 | **S**；Formation FX-05 / 07 | **S**；Formation FX-04 / 05 | P；Reading WX-09 / 12 | P；Screen 6 有用户权力边界，没有 Evidence-only / local Diff / Current / Recovery / History 状态链 | Source revision → affected Anchor → Evidence-only or local semantic Diff → partial adopt → session History / predecessor / Overview projection |
| J11 | 离线与恢复 | P | P | **S**；Reading WX-10 / 14；Library LX-05 / 11 / 14；Language LPX-16 / 17 | P；Screen 7 只有存储概念 | DPB-13 / 16 / 17：local Current、truthful save / sync state、Recovery ≠ Resume、canonical Catalog under index partial、Knowledge Package、clean restore；失败先说明保留项、未完成项与下一步 |

结论：十一条旅程都至少有一份 fixture 承担主要语义压力；J1、J2、J5、J11 因新增 Fixture C 才形成完整定义闭环。当前没有一条旅程被七张静态图完整证明。

---

# 4. AC-01–AC-32 追踪

## 4.1 产品中心与层级

| AC | 合同 | Fixture 证明 | 当前 Ardot | 状态 |
|---|---|---|---|---|
| AC-01 | 一个产品中心 | C：空库进入 Stable Library；Library LX-01–03 / 06、LEC-01–08 / 13–16；Surface DPB-01 / 02、SEC-01；Language LAC-01–03 | Screen 1 星图 Hero 与`知识星图`第二中心 | **C** |
| AC-02 | Groups / Network 同义 | C：同一 Group truth；B：Pair / Network；Library LX-09 / 10、LEC-03 / 04 / 20；Surface DPB-04、SEC-02 | 没有 catalog ↔ network scope / selection 映射 | **N** |
| AC-03 | Bare Group 合法 | C：只有名称的 G-WRITE | 只有成熟概念卡 | **N** |
| AC-04 | Topic 可递归、Opening 连续且不强迫中转 | A / B 深层 Topic；C Search 直达；Reading WX-03 / 04、WEC-07–10 | Screen 3 只写 L0–L5 | **P** |
| AC-05 | Overview Editorial / Projection / Reference 分权，不形成影子知识 | A / B 区分正文、结构与投影；Reading WX-01 / 02、WEC-01–06 | Screen 6 有 user-owned prose 原则 | **P** |

## 4.2 Knowledge 与身份

| AC | 合同 | Fixture 证明 | 当前 Ardot | 状态 |
|---|---|---|---|---|
| AC-06 | 单一 content tree 的连续 Knowledge Paper | A / B / C 都有连续正文；Reading WX-05 / 06、WEC-11–13 | Screen 2、5 有长阅读气质，无 local outline / Anchor 证明 | **P** |
| AC-07 | 多 Placement 不复制，正文与当地 context 分权 | B 完整正例；Reading WX-08、WEC-24 | 没有同一 identity 的双语境 | **N** |
| AC-08 | 移除 Placement 不删除 Knowledge | B / C | 没有删除后果 | **N** |
| AC-09 | 普通写作没有审批；Buffer / Recovery / Draft / Proposal / Sync 分权 | C 直接写作；B procedural writing；Reading WX-09 / 10、WEC-17–22；Language LAC-07 | Screen 6 局部支持，Screen 4 的审批感冲突；没有 truthful save state | **C / P** |
| AC-10 | Anchor 不静默漂移并支持精确返回 | A / B exact return；C export / restore 保持 a1；Reading WX-11 / 13、WEC-15 / 16 / 26 | 没有 Anchor 迁移状态 | **N** |

## 4.3 Relation 与探索

| AC | 合同 | Fixture 证明 | 当前 Ardot | 状态 |
|---|---|---|---|---|
| AC-11 | Relation 是完整陈述 | A / B / C + Relation RX-02 / 05、REC-01 / 09；Language LAC-09 | Screen 2 / 3 只有节点和线 | **C** |
| AC-12 | 五类连接不混边 | A / B / C + Relation RX-08、REC-02 / 03 / 23 | Screen 3 混合对象和线 | **C** |
| AC-13 | Cross-group exit 不冒充群关系 | A + Relation RX-04、REC-10 / 12 / 13 | 没有可见 qualification chain | **N** |
| AC-14 | Shared Knowledge 是观察 | B 双 Placement + Relation RX-06、REC-11 | 没有 shared identity 表达 | **N** |
| AC-15 | 关系按意图增长 | B / C + Relation RX-01 / 12、REC-13–17 / 24；Surface DPB-08、SEC-11 | Screen 2 永久关系面，Screen 3 全局星图 | **C / P** |
| AC-16 | Graph / List 等价 | A / B / C + Relation RX-13 / 14、REC-19；Surface DPB-04 / 09 / 16、SEC-12 | 无 Relation List 证据 | **N** |
| AC-17 | Exact return | A / B 强路径；C Search return；Relation RX-07、REC-18 / 20–22；Surface SEC-08 | 没有跨屏状态连续性 | **N** |

## 4.4 Search、Ask 与 Question

| AC | 合同 | Fixture 证明 | 当前 Ardot | 状态 |
|---|---|---|---|---|
| AC-18 | Search 直接找回 | C exact Anchor + Back envelope；Library LX-07 / 11、LEC-19；Language LAC-14 | 没有 Search / Filter、All Knowledge 与返回证据 | **N** |
| AC-19 | Ask 范围可解释 | A / B + QX-02 / 06 / 11：Requested / Effective / Used、per-run expansion、Group coverage；Language LAC-15 | Screen 5 缺范围说明 | **N** |
| AC-20 | Claim-level grounding | A / B + QX-03–05：Claim → Anchor → Fragment、Route 正 / 负例 | Screen 5 有来源入口但未证明逐 Claim 与 Route fidelity | **P** |
| AC-21 | Coverage 不冒充 confidence | A / B + QX-07 / 11：partial、unknown、condition、broad scope | Screen 4 仍用置信度审批语气 | **C** |
| AC-22 | Answer 不自动成为知识 | A / B + QX-06 / 10 / 12：history、recovery、Snapshot 与 Current 分权 | Screen 6 有“不自动改写”原则，但 Answer 后果未证明 | **P** |
| AC-23 | 写回原子化 | A / B + QX-08 / 09：Snapshot、Knowledge、patch、Question、Relation、Path 分权 | Screen 4 合并成逐条接受流程 | **C** |
| AC-24 | 临时问题不制造 Inbox | A / B + QX-07：Runtime Unknown 只有显式保存才成 Question | 没有临时 / 长期问题边界 | **N** |

## 4.5 来源、形成与演化

| AC | 合同 | Fixture 证明 | 当前 Ardot | 状态 |
|---|---|---|---|---|
| AC-25 | Source-first 部分成功且回执准确 | C：parse failed 但 Source 已保存；Formation FX-02 / 08、FEC-06–09；Language LAC-21 | Screen 4 没有 partial success，也未区分 original / snapshot / URL-only / partial | **N** |
| AC-26 | Candidate 拒绝零副作用，zero-yield 合法 | A / B relation / knowledge candidates；Formation FX-12、FEC-13 / 14 | 没有拒绝后的状态证据；仍制造 AI 待审批暗示 | **N** |
| AC-27 | Source change 不覆盖 Current，Evidence-only 不改正文 | A / B 强变化链；C 简化链；Formation FX-04 / 05 / 07、FEC-15 / 16 | Screen 6 只有建议气质，没有 Evidence-only / Proposal / Diff 分权 | **P** |
| AC-28 | History 按 session 可理解，restore 向前，形成链可追溯 | A / B predecessor；C archive / restore；Formation FEC-16 / 22；Reading WX-10 / 12、WEC-22 / 23 | 没有 Knowledge / Source revision、Recovery、Binding 与 provenance 的联合 History | **N** |

## 4.6 所有权、失败与责任等价

| AC | 合同 | Fixture 证明 | 当前 Ardot | 状态 |
|---|---|---|---|---|
| AC-29 | AI / Index unavailable | A / B / C；C 最完整；Reading WEC-27；Library LX-11、LEC-22 / 28；Language LAC-25 | Screen 7 表达本地，但未证明离线目录、index coverage / Recovery | **P** |
| AC-30 | Export / Restore 语义完整 | C clean restore；A / B 局部；Reading WX-14、WEC-28；Library LX-14、LEC-25 / 26 | Screen 7 只有 storage options | **P** |
| AC-31 | Responsive responsibility | Fixtures 定义不可丢责任；Surface DPB-18、SEC-26 / 29；Language LAC-27 / 30 | 没有 desktop / compact / mobile 等价证据 | **N** |
| AC-32 | Accessibility equivalence | Fixtures 定义键盘 / List 后果；Surface DPB-18、SEC-27–29；Language LAC-28–30 | 没有 keyboard、screen reader、zoom、reduced motion 证据 | **N** |

统计口径不是“画过相关页面”，而是“是否证明完整责任”。当前 Ardot：0 项完整通过；局部证据集中在 AC-05、06、20、22、27、29、30；其余缺失或冲突。

---

# 5. 本轮压力测试发现并修复的产品缺口

| 缺口 | 为什么是真问题 | v6 修复 |
|---|---|---|
| 第一条 Knowledge 可无 Group，但 Library Groups view 原本只列 Groups | 用户返回 Library 后可能找不到自己刚写的知识，直接破坏首日信任 | 增加安静、稳定的`独立知识`区域；它是派生 view，不是 Inbox、类型或第三主视图 |
| 十条旅程没有完整 Search 旅程 | Search 在定义和 AC 中存在，却没有入口、结果、失败、返回的端到端合同 | 新增 J5 Search 深层找回与返回；核心旅程变为十一条 |
| 前两夹具都从成熟 Library 开始 | 无法证明产品不是依赖模板、导入或 AI 的专家工具 | 新增 Fixture C：空库、直接写作、Bare Group、Search、离线与恢复 |
| Source Reader / Evidence 只有概念名 | 无法判断来源 identity、revision、fragment、binding、availability 与 exact return 如何共同工作 | v6 §9.8 明确 Source Reader / Evidence 产品责任 |
| 高后果 Question 的适用条件与复核触发过薄 | Answer 可能看似准确，却无法说明适用于谁、何时、何条件及何时复核 | v6 §6.6 增加 Applicability Snapshot 与 review triggers |
| 旧夹具把 Groups / Knowledge 称 Primary、Sources / Relations 称 Supporting | 与 v6 四类 canonical truth families 冲突，会悄悄恢复旧本体 | 两份旧夹具改为 Canonical inventory + supporting identities，并将精确旧 relation type 标记为 fixture / experimental expression |
| “一个 Group 到一万个 Groups”把 Group 数与 Knowledge 数混为一条规模轴 | Catalog、Topic navigation 与 content retrieval 的压力完全不同，无法形成可验证责任 | 改为 G1 / G10 / G100 / G1K 与 K1 / K100 / K10K / K100K 两条轴；增加 synthetic G100 / K10K fixture |
| nested Group、Topic、Saved View 与 Group Relation 边界不够明确 | 大库可能重新退化为文件夹树，parent / child 同时承担结构、语义与目录 | Groups 不结构性嵌套；Group 内 Topic 深入，Group 间 Relation 解释，Saved View 只做 Catalog Lens |
| Search、Ask、Answer 与 Explore 虽分别存在，却缺少转换与返回合同 | 产品可能退化成搜索框、聊天页和图谱页三个孤岛；引用、追问和网络探索无法回到原 Claim | 新增 Query Active Appendix：Context 三层、Answer Paper、Claim Focus、Route / Used List、Follow-up Delta、history 分权与 Answer ↔ Explore exact return |
| Add、Source save、Annotation、Knowledge formation 与 semantic update 被当作同一条“AI 提取”流程 | 用户无法判断资料是否已保存、AI 草稿是否已成为真相、一次补证是否改写正文；普通写作也被降格为待审批输入 | 新增 Formation Active Appendix：入口决定初始 truth role；直接写作提交为 Current；Source-only 合法完成；Highlight / Annotation 留在原文；Binding、New Knowledge 与 semantic Diff 分别原子提交 |
| Relation、Exit、Shared observation、Candidate、Query Route 与历史边仍可能被同一种线表达 | 图会把可导航、相似、待确认和已成立混成同一真相；固定双镜也无法证明 Inspect / Open / exact return | 新增 Relation Active Appendix：完整 statement、群级 qualification、Current / Suggested / History、Quiet / Peek / Companion / Explore、R0–R3、Graph / List、Scene / Trail / Path 与 exact return 分权 |
| Overview、Topic Opening、long Knowledge、编辑器、Anchor 与 History 只有概念名，没有统一连续性合同 | 方向 3 可能退化为漂亮长文：多层中转、摘要漂移、卡片碎片、保存状态混乱，Evidence / Relation 关闭后回不到原主张 | 新增 Reading Active Appendix：scope-owned Overview、Editorial / Projection / Reference、same-scroll Topic Opening、single content tree、stable Anchor、direct Current、Recovery / History / restore forward 与跨场景 exact return |
| Library 只定义了 Catalog / Pins / Resume 的名词，没有冻结 cold start、普通 Open / Continue、All Knowledge 与各种“回去”状态 | Screen 1 仍可能变成星图 Hero、Recent feed 或自动深开；快捷入口会接管全部目录，Recovery 也会被误当成 Resume | 新增 Library Active Appendix：stable cold start、Resume → Pins → All Groups 注意力顺序、All Knowledge 次级 inventory、Resume / Pin / Recent / Saved View / Saved Path / Recovery 分权、index-partial Catalog 与 Screen 1 proof responsibilities |
| 七张 Screen 被当作七个产品地点，缺少统一 Shell、Surface roles、跨场景返回与设计证据口径 | 功能可以各自好看，却无法证明同一知识在入口、阅读、关系、回答、来源、失败与恢复中连续；Screen 数会制造虚假完成度 | 新增 Surface Active Appendix：五个 Scene families、六类 Surface roles、Search / Ask / Add transition、Return Envelope、state / responsive / accessibility equivalence、DPB-01–18 与 SEC-01–32 |
| 旧语言合同与当前 Ardot 把内部对象、模式和价值指标直接暴露给用户 | `Home / Atlas / Command / 14 resources / 八类对象 / AI 新析出 / 提问与收录`会让用户学习数据库和页面模型，且无法判断动作后果、partial success 与返回 | 新增 Language Active Appendix：一个`知识库`、五个日常概念、三个全局动作、Calm / Focused / Decision / Forensic、真实状态模板、LPX-01–18 与 LAC-01–32；旧 81-screen 语言模型保持非规范 |

---

# 6. 仍未关闭的产品决定

以下不是遗漏功能，而是进入 Surface Skeleton 前需要用户明确确认或接受推荐默认的十一项决定：

1. 一个 Stable Library 与一个稳定 App Shell，Groups / Network 是同一真相的两种视图；cold start 先到 Catalog，最多一条安全 Resume 由用户显式选择，Pin / Recent / Saved View / Saved Path / Recovery 分权，All Groups 不被任何 Lens 替代；
2. 无 Group 的 Current Knowledge 以`独立知识`合法存在，不设 Inbox；
3. Overview 是用户可编辑的导读，不是 AI 自动摘要；Editorial prose、Structure projection 与 Reference 分权；
4. Topic Opening 与单一 content tree 的 Knowledge Paper 构成连续阅读；Topic 可递归，deep Anchor 可被 Search / Ask / Evidence / Relation 直达；
5. 同一 Knowledge 可以多 Placement，不复制正文；
6. Relation 首先是一句完整陈述，Candidate 与 Current 分开，Graph 只是呈现；
7. Library Network 以 Current Groups / Relations 为 resting level，没有群关系合法，不把所有对象铺成全局星图；
8. Ask、Answer 与 Proposal 不自动改变 Current Knowledge；
9. 维护提示出现在相关上下文，不建立 Review 驱动首页；
10. Ask 是同一 Library 中的 Answer Paper，不是聊天产品；普通 Query history 不自动成为知识，Answer 与 Network 通过具体 Claim 可逆联动；
11. 用户直接写作经安全保存后就是 Current Knowledge；Edit Buffer、Recovery、Draft、Proposal、Sync 与 Current 分权；Source save 本身可以完成，Highlight / Annotation、Evidence-only、Knowledge formation 与 semantic update 分别提交，AI 不建立卡片审批队列。

第 2 项已经被对抗性审计进一步收敛：日常名称采用`独立知识`，避免“尚未归入”继续制造未完成暗示；具体布局仍待后续 Surface Skeleton 证明。

这十一项共同落实为五个 Scene families、六类 Surface roles 和 DPB-01–18；在用户表面固定表达为一个`知识库`、五个日常内容概念和三个全局动作。这些是十一项选择的表达与证明语言，不增加第十二项产品选择。

---

# 7. 进入下一阶段的 Gate

当前只满足“产品定义可审阅”的门槛。进入不带视觉风格的 Surface Skeleton 前，需要：

- 用户确认或反对第 6 节十一项决定；
- v6、三份 fixture、权威注册表和本矩阵不存在第二套本体；
- 十一条旅程各有入口、结果、失败、恢复与返回责任；
- AC-01–AC-32 保持唯一编号，不用静态图冒充运行证明。
- Surface Architecture、Return Envelope、DPB-01–18 的 owner / fixture / required states 已冻结；当前七屏只登记为 Visual Specimens，不进入完成度分母。
- 一个`知识库`、五个日常内容概念、三个全局动作与 LPX-01–18 已冻结；DPB-01–18 登记 default、partial / error、return copy、disclosure level 与 accessible name，并映射 LAC-01–32。

在这些条件完成前，不制作点击原型，不把旧 Ardot 七屏当作新产品结构，也不以“视觉已经很完整”为理由跳过产品选择。
