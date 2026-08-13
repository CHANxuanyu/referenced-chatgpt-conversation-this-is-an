# AI-native 个人知识库

## v5 结构收敛与文档债审计 v1.0

> 审计日期：2026-08-10  
> 审计对象：`AI-native-个人知识库-终局产品设计文档-v5.0.md`及其当前引用的交互、表面、流程、心智模型和决策文档  
> 审计目的：判断产品是否已经真正收敛为一个知识库，以及文档系统是否足以指导后续设计而不会继续漂移  
> 本轮边界：只修订产品定义与文档权威；不修改 Ardot，不生成视觉方案，不制作原型  

---

# 0. 审计结论

v5 已经完成了最重要的方向纠正：产品中心从 Cognitive OS、AI 工作台和知识星图，回到了一个层级阅读优先、关系按需展开、AI 可查询的个人知识库。

但 v5 仍不是最适合作为长期 Canonical 的文档，原因不是内容不够，而是内容过多、权威分散、旧模型依靠顶部覆写继续存活。当前最大的产品风险已经从“想得不完整”变成“定义得太多，以至于未来设计可以从不同文档读出不同产品”。

因此本轮建议不是继续给 v5 加章节，而是进行一次真正的结构收敛：

1. 把一个 Library、层级阅读、按需关系、可追溯 Ask 固定为唯一产品骨架；
2. 把十四类 Primary Resources 收敛为四类 canonical truth families，加一个用户可见的 Topic 结构身份，其余降为 supporting identities 或 state；
3. 把 25 + 11 个关系类型注册表从主产品定义降为可演化的语义附录；
4. 删除 Home / Atlas / 四 Places / 四 Roots 的现行权威，只保留历史映射；
5. 把一个可独立阅读的 v6 作为唯一 Canonical；专项合同只负责深层边界，不能新增产品中心；
6. 用少量核心旅程和验收合同证明产品完整，而不是用文件数量、对象数量或屏幕数量证明完整。

---

# 1. 已经成立、必须保留的部分

## 1.1 产品中心已经正确

v5 的一句话定义、唯一 Knowledge Library、Groups / Network 两个同义视图、Search / Ask / Add 全局动作，已经与用户的最新意图一致。

必须保留：

- 产品首先是知识库；
- 知识以有边界的知识群存在；
- 知识通过 Overview → Topic → Knowledge → Evidence 逐层深入；
- 关系需要可读语义，而不是装饰线；
- AI 查询能回到知识与来源，而不是停在聊天记录里；
- 方向 3 的阅读连续性是主轴，方向 2 的关系空间是按需第二维度；
- 本地优先主要解决长期所有权、离线可用和可恢复，不应成为首屏技术卖点。

## 1.2 五个日常概念是正确复杂度

知识群、主题、知识、关系、来源足以解释绝大多数日常体验。用户不应先理解 Placement、Projection、Binding、Change Set、Proposal、Snapshot 或 Workspace State 才能使用产品。

## 1.3 两条正交认知轴成立

- 纵向阅读深度回答“我怎样从整体进入细节”；
- 横向关系半径回答“我想把相邻连接打开到多大范围”；
- 调整关系半径不能改变阅读位置；
- 深入证据不能强迫打开图谱。

这是方向 3 + 2 真正产品化的核心，应保留为后续设计的首要结构。

## 1.4 AI 权力边界成立

AI 可以检索、回答、提出关系、提出局部修改和帮助形成知识，但不能：

- 自动把回答升级为 Current Knowledge；
- 静默改写 Overview；
- 用 confidence 百分比替用户决定真相；
- 把 retrieval path 画成长期关系；
- 因为发现新来源就制造 Review debt。

---

# 2. 当前仍然存在的结构问题

## 2.1 主文档承载了过多不同读者

v5 共 2720 行，同时承担：

- 产品愿景；
- 用户心智模型；
- 详细领域模型；
- 交互架构；
- 数据真相分层；
- 失败与恢复；
- 视觉方向；
- 研究综述；
- 60 条验收。

这使“主文档可以独立阅读”的承诺与实际阅读成本冲突。产品负责人需要的决定、设计师需要的表面责任、工程需要的身份语义和测试需要的回归条件应当相连，但不应在同一层级反复出现。

## 2.2 旧架构依靠覆写说明继续存活

多个当前引用文档在顶部写明：旧 Home / Library / Atlas / Sources 四 Places、四 Roots 或旧 Screen 编号已失效；正文却继续保留这些结构。

这造成三个实际后果：

1. 新设计者只读正文时会重新画出多个产品中心；
2. 自动提取组件、流程或需求时会同时得到新旧两套答案；
3. 每次新增修订都需要再增加一层“覆写说明”，文档越来越难维护。

覆写可以用于短期迁移，不能成为长期文档架构。

## 2.3 十四类 Primary Resources 过度提升内部责任

Placement、Overview、Evidence Fragment、Snapshot、Change Set、Proposal、View 都需要稳定语义，但不都需要被称为“主要资源”。

Primary Resource 应回答“用户想长期拥有和再次进入什么”；Supporting Identity 回答“系统怎样保持精确、可追溯和可恢复”。把两者全部放在同一等级，会导致：

- 搜索、创建菜单和导航被内部对象污染；
- 产品设计为每个数据责任发明页面；
- 用户建立知识前先学习系统模型；
- 工程对象数量反过来定义产品。

建议收敛为 Group、Knowledge、Relation、Source 四类 canonical truth families；Library 是根，Topic 是 Group 内稳定结构身份，Overview / Placement / Question state / Answer snapshot / Saved Path 等由 owner 或 supporting layer 承担。

## 2.4 25 + 11 Relation registries 冻结过早

关系必须拥有 direction、statement、qualifier、basis、standing 和 history，这一原则正确；但在没有真实使用数据前冻结 25 种知识关系和 11 种群关系，会产生伪精确：

- 用户可能无法稳定区分相邻类型；
- 菜单、检查器和迁移规则会围绕未验证分类膨胀；
- 设计为类型注册表服务，而不是为“为什么相连”服务；
- 新关系先考虑落在哪个枚举，而不是是否值得长期维护。

主产品定义只需冻结关系句法、少量意图家族和生命周期。精确 registry 可以作为可版本化附录，通过真实内容与可用性测试逐步收敛。

## 2.5 Question 模型把普通未知工程化

Question、Resolution、pursuit、change、library 四轴可以覆盖复杂研究，但普通用户只需要先理解：

- 这是一个尚未解决的问题；
- 当前回答是什么；
- 依据是什么；
- 还不知道什么；
- 何时值得重新检查。

建议把 Question 定义为一种 Knowledge role，而不是新的日常对象系统。只有长期研究问题才逐步显示 Resolution criteria、status 和 review condition。

## 2.6 产品完整性被文件数量和覆盖数量替代

当前系统拥有大量专项合同、81 项 Coverage、90 项 capability 和 60 条验收。它们可以防止遗漏，但不能自动证明产品合理。

更可信的完整性单位应是：

1. 一条用户旅程能否从入口连续走到结果并返回；
2. 同一对象在阅读、搜索、Ask、图谱和来源中是否保持身份一致；
3. happy path、partial、failure、offline、historical 是否拥有同一产品责任；
4. desktop、compact、mobile、keyboard、screen reader 是否责任等价；
5. 用户能否理解后果，而不是系统是否拥有足够多的状态名。

## 2.7 待确认决定与 Canonical 真相混在一起

v5 正确标注了用户确认、产品决定和待验证假设，但正文仍以确定语气完整展开多个待确认模型。后续文档应把三者分开：

- 用户已确认：不可漂移；
- 推荐默认：可以继续设计，但必须可被反对；
- 开放假设：不能进入不可逆对象模型或视觉主导航。

---

# 3. 官方资料校准后的产品推论

## 3.1 全库 Graph 与局部 Graph 应承担不同任务

Capacities 官方只提供围绕当前对象的 local graph，并把 backlinks / related content 作为列表等价；Obsidian 同时提供全局图和以 active note 为中心、可调 depth 的 local graph。

产品推论：本产品的 Library Network 应以 Groups 为 resting level；Knowledge graph 必须锚定当前 Group、Topic、Knowledge 或查询路径，不默认铺开全部知识节点。

## 3.2 手工集合与动态查询必须分开

Anytype 官方把 Collection 定义为手工加入的对象集合，把 Query 定义为从整个 Graph 动态筛选对象；Capacities 也区分手工 Collection、Tag 和动态 Query。

产品推论：Group membership / Placement 是用户可理解的长期结构；Saved View 是动态观察。View 命中不能静默改变 Group membership。

## 3.3 同一内容多处出现不应复制正文

Capacities 的对象可以同时出现在多个 Collections；Anytype 的对象也可以被不同 Collection / Query 观察。

产品推论：同一 Knowledge 多 Placement 是合理方向，但产品需要明确每个 Placement 的语境说明、移除后果和 canonical identity。

## 3.4 AI 查询结果与长期知识必须分权

Notion Research Mode 允许用户选择来源范围、查看被使用的来源，并把研究结果显式`Save as page`；结果不是因为生成完成就自动成为 Workspace 内容。

产品推论：Ask 默认只产生 Answer Run；保存回答、形成 Knowledge、修改现有 Knowledge、保存 Question 或提出 Relation 必须是不同动作。

## 3.5 可视空间有真实规模边界

Heptabase 官方性能说明指出，大约 100–150 张卡片的单一 whiteboard 就可能明显变慢，复杂媒体或高连接度会更早触发问题。

产品推论：自由白板和全库节点云不能成为默认知识结构。层级、范围锚点、局部展开和列表等价是产品能力，不只是性能降级。

## 3.6 本地优先是所有权与连续性，不是首页卖点

Anytype 官方把 local-first / offline-first 与数据所有权直接关联；Heptabase 的版本历史和导出也区分布局恢复与卡片内容恢复。

产品推论：本产品应保证 AI、网络或派生索引不可用时仍可读写和导出；同时必须把 canonical content、layout / workspace state 和 derived index 分层恢复。

---

# 4. v6 重构决定

## 4.1 单一产品骨架

```text
Knowledge Library
├─ Groups view
├─ Network view
├─ Group / Topic / Knowledge continuous reading
└─ Supporting utilities
```

没有独立 Home truth，没有独立 Atlas 产品中心，没有默认 Review / Inbox。

## 4.2 四类 canonical truth families + Topic

| Resource family | 用户长期拥有的东西 | 不单独提升为资源的责任 |
|---|---|---|
| Group | 一个有边界的知识范围 | Overview、Topic tree、membership projection |
| Knowledge | 一份可独立阅读、编辑、复用的理解 | Section、Claim、Question role、Draft state |
| Relation | 一句两端之间可读、有限定的长期陈述 | Graph edge、retrieval route、backlink |
| Source | 一份可定位、可版本化的原始材料 | Representation、Fragment、Binding |

Library 是根；Topic 是用户可见、可寻址的层级身份，但不拥有独立 Group Boundary；Saved Path、Placement、Revision、Proposal、Answer Run、View Definition 和 workspace state 是支撑责任。

## 4.3 六类产品场景

1. Library：选择、继续、切换 Groups / Network；
2. Reading：Group、Topic、Knowledge 共用连续壳层；
3. Relation Space：从 Peek 到 Explore 的按需关系呈现；
4. Answer：显示范围、依据、Coverage、未知和可选写回；
5. Source Reader：核验来源上下文与版本；
6. Supporting utilities：History、Recovery、Import / Export、Trash、Settings。

Search、Ask、Add 是随处可调的 overlays，不是额外 Places。

## 4.4 三十二条核心验收取代主文档中的数量竞赛

v6 主文档只保留足以证明产品本体、连续性、可信、失败和责任等价的核心验收；稀有迁移与类型状态仍可由专项附录覆盖，但不得提高产品复杂度。

## 4.5 文档权威必须可机器读取

每份文档只允许一个状态：

- Canonical；
- Active Appendix；
- Historical / Superseded；
- Fixture / Evidence。

不能再依靠“正文仍有效，但某几段按顶部覆写读取”的隐含规则。任何旧文档若未完成正文迁移，只能降为 Historical Reference。

---

# 5. 下一步

本审计直接触发三项修订：

1. 编写 `终局产品设计文档 v6.0`，以本审计的单一骨架、四类 canonical truth families 和 Topic 结构身份为准；
2. 建立文档权威注册表，显式标记旧合同是 Active Appendix 还是 Historical；
3. 将 Ardot 和视觉方向文件的 Canonical 指针升级到 v6.0，但继续保持“不修改 Ardot、不制作原型”的边界。

---

# 研究来源

- [Capacities — Graph view](https://docs.capacities.io/reference/graph-view)
- [Capacities — Tags vs. Collections](https://docs.capacities.io/tutorials/tags-vs-collections)
- [Capacities — Queries](https://docs.capacities.io/reference/queries)
- [Obsidian — Graph view](https://obsidian.md/help/plugins/graph)
- [Obsidian — Backlinks](https://obsidian.md/help/plugins/backlinks)
- [Anytype — Collections](https://doc.anytype.io/anytype-docs/getting-started/sets/collections)
- [Anytype — Queries](https://doc.anytype.io/anytype-docs/getting-started/sets)
- [Anytype — Storage & Deletion](https://doc.anytype.io/anytype-docs/advanced/data-and-security/data-storage-and-deletion)
- [Notion — Research Mode](https://www.notion.com/help/research-mode)
- [Heptabase — Performance and lag](https://support.heptabase.com/en/articles/11430704-troubleshooting-performance-and-lag-issues-in-heptabase)
- [Heptabase — Version history and restore](https://support.heptabase.com/en/articles/10448124-how-to-restore-cards-and-whiteboards-from-version-history)
