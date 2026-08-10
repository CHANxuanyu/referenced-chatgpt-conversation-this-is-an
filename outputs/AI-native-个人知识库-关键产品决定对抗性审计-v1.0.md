# AI-native 个人知识库

## 关键产品决定对抗性审计 v1.0

> 日期：2026-08-10  
> 审计对象：`AI-native-个人知识库-终局产品设计文档-v6.0.md` 的推荐默认  
> 文档身份：**EVIDENCE**；负责挑战和解释决定，不独立新增产品真相  
> 当前阶段：继续定义产品；不修改 Ardot，不生成新 Frame，不制作原型  
> 事实边界：竞品官方资料只证明其当前模式，不证明本产品选择已经被用户验证  

---

# 0. 执行结论

v6 的大方向已经正确，但五处最容易在长期使用中变形：

1. 允许无 Group 写作，却把结果命名成“尚未进入知识群的知识”，仍暗示整理债务；
2. Group / Topic 有定义，却缺少普通人能执行的升级与降级判断；
3. Overview 分成用户文字与结构投影，但 Proposal、空状态和编辑权仍可能互相覆盖；
4. Relation 有严谨模型，但若没有增长节流，最后仍会变成边越多越成功；
5. AI 写回被拆成原子动作，但“用户已经明确命令 AI 修改”与“系统主动建议”还需要不同授权语义。

本轮推荐：

- 把用户可见的`尚未进入知识群的知识`改为 **独立知识**；
- 把它定义为由`Current Placement count = 0`推导出的 Library view，而非类型、状态、Inbox 或清理队列；
- 为 Group / Topic 建立“整体重返、独立导读、跨群表达”三问测试；
- 为 Overview 冻结 Editorial / Projection / Proposal 三种权力，不冻结视觉比例；
- 为 Relation 冻结“观察 → 候选 → Current”的升级门槛和可读预算；
- 为 AI 冻结“回答、建议、受命编辑、直接写作”四种写入授权。

这些修改收紧的是产品权力和长期行为，不增加新的产品中心、一级导航或日常对象。

---

# 1. 审计方法

## 1.1 五个判断问题

每项推荐默认都必须回答：

1. 它解决了用户的哪个真实理解问题；
2. 它在 G1 / G100 的 Group scale、K1 / K10K 的 Knowledge scale 和不同独立 Knowledge 数量下是否仍是同一个产品；
3. 它会不会把合法状态变成待办、完成度或维护压力；
4. 它与 Current、Proposal、History、Projection 的权力是否清楚；
5. 什么真实证据会让我们反转决定。

## 1.2 证据分层

| 层级 | 可以证明 | 不能证明 |
|---|---|---|
| 用户明确表达 | 产品本质、核心能力、当前工作顺序 | 具体默认行为一定可用 |
| 官方竞品资料 | 当前产品怎样组织、查找和放置内容 | 该模式适合本产品用户 |
| 三份 Fixtures | 本体、状态和后果能否承载真实内容 | 真实用户是否理解、喜欢或长期使用 |
| 当前 Ardot 七屏 | 局部视觉气质与可见结构 | 交互、返回、持久化、无障碍或产品完整度 |

---

# 2. 外部模式研究：事实与产品推论分开

## 2.1 Library root 与 Placement 分权

**观察事实**

- Zotero 的 Library root 始终包含所有 items；Collection 像 playlist，同一 item 可进入多个 Collections 而不复制；移除 Collection placement 不删除 item。它还提供可选的 Unfiled Items special collection。  
  [Zotero — Collections and Tags](https://www.zotero.org/support/collections_and_tags)
- Anytype 把 Query 定义为对 Graph 中 Objects 的动态观察，不由 Query 存储 Objects；其默认 All Objects 列表用于找回全部对象。  
  [Anytype — Queries](https://doc.anytype.io/anytype-docs/getting-started/sets) · [Anytype — Objects](https://doc.anytype.io/anytype-docs/getting-started/object-editor)
- Heptabase 同时存在 Card Library 与 Whiteboards；卡片可从 Library 被放入或移出 Whiteboard，二者不是同一种身份。  
  [Heptabase — CLI / Card Library and Whiteboards](https://support.heptabase.com/en/articles/14715462-how-to-use-heptabase-cli)

**产品推论**

内容 identity 不应该依赖“已经放进某个 Group”。Group Placement 是语境入口，不是存在许可证。Library 需要稳定找回所有 Current Knowledge，但不能把 All Objects 巨型列表作为首页。

## 2.2 延迟组织有价值，但 Inbox 不是中性词

**观察事实**

- Capacities 用 Daily Note 承担“不先决定永久位置”的捕获，再把值得保留的内容转成 objects、tags 或 tasks。  
  [Capacities — Object types vs. folders](https://docs.capacities.io/tutorials/object-types-vs-folders)
- Heptabase 的 AI / MCP 保存新 note card 时会进入 Inbox，官方描述为稍后在 whiteboard 中组织。  
  [Heptabase — MCP](https://support.heptabase.com/en/articles/12679581-how-to-use-heptabase-mcp)
- Zotero 的 Unfiled Items 是可选 special collection，而不是默认待办首页。  
  [Zotero — Collections and Tags](https://www.zotero.org/support/collections_and_tags)

**产品推论**

延迟决定 Placement 是合理能力，但 Daily Note 和 Inbox 都引入额外心智：时间日志或待整理队列。本产品的核心是长期知识库，不应把“仍然独立”解释为“还没处理完”。

## 2.3 关系发现与正式关系必须分开

**观察事实**

- Obsidian 把 Linked mentions 与 Unlinked mentions 分开；后者是由名称 / alias 发现的潜在线索，不自动成为显式 link。  
  [Obsidian — Backlinks](https://obsidian.md/help/backlinks)
- Anytype Query / Capacities Query 都是动态观察；它们不因某次匹配而改变对象的 canonical membership。  
  [Anytype — Queries](https://doc.anytype.io/anytype-docs/getting-started/sets) · [Capacities — Queries](https://docs.capacities.io/reference/queries)

**产品推论**

系统发现“可能相关”是 observation / signal；只有可读 statement、边界、依据和明确采纳才能成为 Current Relation。动态发现不应污染长期图谱。

## 2.4 全对象与全图不是稳定首页

**观察事实**

- Anytype 的 All Objects 有利于完整找回，但官方同时依赖 Type、Query、Sidebar 和 Search 提供不同切片。  
  [Anytype — Objects](https://doc.anytype.io/anytype-docs/getting-started/object-editor)
- Heptabase 官方指出单个 whiteboard 在约 100–150 cards 或大量媒体、长内容、高连接情况下会出现明显性能压力，并建议拆分范围。  
  [Heptabase — Performance and lag](https://support.heptabase.com/en/articles/11430704-troubleshooting-performance-and-lag-issues-in-heptabase)

**产品推论**

完整可找回不等于把全部东西铺在首页或图上。Library resting level 应由 Groups 提供方向；独立 Knowledge 作为安静兜底；Search / filtered view 负责完整找回。

---

# 3. 决定一：独立知识，而不是“未整理知识”

## 3.1 问题

用户从空库直接写下第一条 Knowledge 时，不应该先回答“它属于哪个 Group”。但如果保存后只有 Search 才能找回，用户会怀疑内容是否真正存在；如果进入 Inbox，又会产生必须清空的整理债务。

## 3.2 五个备选

| 方案 | 优点 | 长期代价 | 结论 |
|---|---|---|---|
| 保存前强制选 Group | 目录始终整齐 | 首次写作被分类决策拦截；空库无法自然开始 | 淘汰 |
| 无 Group 可保存，但只靠 Search 找回 | 表面最简 | 返回 Library 看不到刚写内容，破坏保存信任 | 淘汰 |
| 进入 Inbox / 待整理 | 找回清楚、可批量处理 | 合法知识变成 backlog；维护系统占据首页 | 淘汰为默认，可作为用户显式 saved view |
| AI 自动归群 | 使用动作少 | 相似度替代用户语境；静默移动 Current | 淘汰 |
| Library 中显示“独立知识” | 立即找回；不要求组织；可自然进入 Group | 成熟库需控制列表规模和语义 | **推荐** |

## 3.3 Canonical 定义

**独立知识（Independent Knowledge）不是新 Resource。** 它是以下条件的派生视图：

```text
Knowledge.lifecycle = current
AND count(active Placements) = 0
```

Active Placement 指尚未结束或删除的语境归属；目标 Group 处于 current、paused 或 archived 不改变 Placement 身份。否则归档一个 Group 会让大量 Knowledge 突然涌入独立知识，制造错误噪音。

它不拥有：

- 独立生命周期；
- “待完成”状态；
- 清空目标；
- 红点、提醒或逾期；
- 自动归类规则；
- 作为 AI 默认维护队列的资格。

## 3.4 生命周期

| 事件 | 结果 |
|---|---|
| 在 Library 直接写 Knowledge | 保存为 Current，并出现在独立知识 |
| 在 Group / Topic 内直接写 | 创建同一 Knowledge，同时建立当前 Placement，不进入独立知识 |
| 给独立 Knowledge 添加第一个 Placement | 从独立知识视图自然消失；不改变正文 identity |
| 移除最后一个 active Placement | Knowledge 回到独立知识；操作前明确预览 |
| Group archive / pause | Placement 仍 active；Knowledge 不重新分类，避免整群内容涌回 Library |
| Group merge / redirect | Placement 随结构事务迁移，不短暂制造独立副本 |
| Group delete | 逐类预览 Move、End Placement、Keep independent 或 Archive Knowledge；不得批量静默改归属 |
| Knowledge archive | 从 current Library 和独立知识消失，进入 Archive |
| Restore archived Knowledge | 按恢复后的 current Placement 重新计算视图 |
| AI 建议 Placement | 只出现局部建议；拒绝零副作用 |

## 3.5 规模行为

| 规模 | Library 表达 | 不允许 |
|---|---|---|
| F0 | 空 Library：直接写 Knowledge 与建 Group 同为合法起点 | Graph 空宇宙、模板墙、AI Hero |
| 1 条 | 独立 Knowledge 是 Library 的主要内容，可直接再次打开 | 要求先建 Group |
| 约 10 条 | Groups 在前；独立知识显示少量最近继续项与“查看全部” | 用数量制造未清空压力 |
| 约 100 条 | 独立知识进入稳定 list / filters；Library 只保留克制入口 | 卡片墙、随机 AI 精选 |
| 10K 量级 | Search、saved view、排序和批量显式 Placement；首页不展开全部 | All Objects 或全图作为 resting surface |

数量可以在用户主动打开完整列表后用于分页、筛选和批量选择，但不作为首页 badge、健康分或待办数。

## 3.6 反转条件

只有真实可用性证据同时证明以下两点，才考虑取消独立知识入口：

1. 用户在保存后不需要从 Library 视觉确认刚写内容；
2. Search-only 找回在 1 条、约 10 条以及离线 / index partial 下仍不会降低信任。

当前 Fixture C 与产品所有权原则都支持保留该入口。

---

# 4. 决定二：Group / Topic 三问测试

## 4.1 问题

“Group 是大范围、Topic 是分支”仍然过于抽象。若判断只看内容数量，用户会得到大量空 Group；若只看层级，Topic 会被误当文件夹。

## 4.2 三问测试

一个范围满足以下问题中的两个，才推荐成为 Group：

1. **整体重返：** 用户是否会反复以它为整体进入，而不只是沿父范围深入？
2. **独立导读：** 它是否需要自己的 Boundary、Overview 和主要入口来说明“这整个范围是什么”？
3. **跨群表达：** 它是否需要与其他 Group 建立整体 Relation，而不是只有具体 Knowledge exits？

若主要价值只在父 Group 内组织深入，并不需要独立 Boundary 或 Group Relations，它是 Topic。

## 4.3 数量不是决定因子

- 1 条 Knowledge 也可以构成 Group，只要范围值得整体重返；
- 100 条 Knowledge 也可能仍是 Topic，只要它只在父范围内有意义；
- AI clustering、source 数量和 node degree 只能形成建议，不能静默升级；
- Topic promotion 与 Group absorption 必须预览 Placements、Overview、Relations、Paths 和 redirects。

## 4.4 边界案例

| 情况 | 推荐 |
|---|---|
| “法国住房”下的“CAF 资格”需要自己的 Overview，并与“租房申请”整体关联 | Group |
| “记忆与学习科学”下的“提取练习机制”主要用于领域内继续深入 | Topic |
| 一个项目暂时有大量会议记录，但项目结束后不需要长期知识边界 | Topic / Saved View，不自动 Group |
| 一个小范围只有两条 Knowledge，却会长期独立演化并跨群复用 | Group |

## 4.5 反转条件

如果测试发现普通用户无法稳定理解三问，产品仍保留内部判断，但界面只问一句结果性问题：“你以后会把它作为一个完整知识范围反复进入吗？”其他条件由 Preview 解释，不暴露为表单。

---

# 5. 决定三：Overview 的三种权力

## 5.1 Editorial prose

用户直接写下并认可的导读，是 Current Knowledge of Scope。它可以表达：

- 为什么这样组织；
- 从哪里开始；
- 什么暂时不要混在一起；
- 当前关键判断、限定和未知。

普通编辑安全提交 Current，不需要 AI 审批。

## 5.2 Structure projection

从 Topics、Knowledge、Relations 和状态动态生成：

- 主要入口；
- 当前结构；
- 可见跨群出口；
- 受影响状态。

它是 Projection，不冒充用户 prose，不因刷新覆盖 Editorial。用户可以调整展示规则或 pin 入口，但不通过编辑一份影子正文改变 canonical objects。

## 5.3 Proposal overlay

AI 或 Source revision 只能针对一个明确目标片段提出：

- 为什么建议改变；
- before / after Diff；
- basis；
- 采纳后影响；
- 拒绝 / 延后 / 局部采纳。

Proposal 不是 Overview 的常驻第三栏。关闭后恢复纯阅读；未采纳内容不进入 Current，也不被未来 Ask 当成用户已认可知识。

## 5.4 空状态

Bare Group 的 Overview 可以只有名称。界面可以显示由当前结构生成的 orientation scaffold，但必须标为可重建 Projection；不能自动写一段看似属于用户的成熟导读。

## 5.5 反转条件

若长期研究证明多数用户不维护 Editorial prose，可以让 Structure projection 承担更多默认可见面积，但不能把自动摘要提升为 Current，也不能删除用户直接编辑权。

---

# 6. 决定四：Relation 增长节流

## 6.1 三层增长模型

| 层级 | 含义 | 是否进正式网络 |
|---|---|---|
| Observation / Signal | shared identity、unlinked mention、co-use、similarity、cross-group exit、candidate path | 否 |
| Candidate | 两端、完整 statement、方向、qualifiers、basis、counterexample 可检查 | 否；只在相关上下文出现 |
| Current Relation | 用户直接声明或明确采纳，拥有 standing 与 history | 是 |

## 6.2 两种 Current 入口

1. **用户直接建立：** 用户明确写出关系 statement，可以直接保存 Current；系统负责提示缺失方向或范围，但不强迫 AI 审批。
2. **系统建议建立：** 必须先作为 Candidate；相似度、引用数量和 co-use 不能替用户采纳。

## 6.3 可读预算

- Quiet：0 条关系正文；只有克制入口；
- Peek：1 条完整关系；
- Companion：围绕当前理解任务的少量关系；
- Explore：扩大范围，但先提供 scope summary、List 和 filter；
- Library Network：只显示 Current Group Relations；
- 没有关系时不制造“完善网络”提示。

## 6.4 删除与结束

Relation end / supersede 不删除 endpoints；历史关系不会以虚线悄悄混入 Current Graph。用户显式查看历史时，时间、原因和 successor 一起出现。

## 6.5 反转条件

如果真实探索任务证明用户频繁需要弱连接，可把 Observation 作为可切换 Lens，但必须保持与 Current Relations 不同的视觉、计数、筛选和写入后果。

---

# 7. 决定五：AI 写回的四种授权

## 7.1 权力矩阵

| 情况 | 用户意图 | AI 可做 | 默认提交 |
|---|---|---|---|
| Ask / Explain | 只想获得回答 | 读取明确 Scope、生成 Answer、展示 basis / coverage / unknowns | 不写入 |
| 系统主动发现变化 | 用户没有要求修改 | 建立局部 Proposal | 不写入 |
| 用户明确要求“把它写入 / 更新 X” | 已给出目标与写入意图 | 生成目标明确的 Change Preview；说明影响与可撤销性 | 由用户确认目标后原子提交；若用户同时明确说“直接改”，可以提交并提供 Undo |
| 用户在编辑器直接写作 | 用户本人正在修改 Current | 辅助润色、结构建议或完成文本 | 与普通编辑相同安全提交；不经过 Review |

## 7.2 “用于知识”不是一个对象

Answer 表面的`用于知识`只是 progressive disclosure。展开后必须区分：

- 保存 Answer Snapshot；
- 建立新 Knowledge；
- 更新指定 Anchor；
- 保存 Question；
- 提出 Relation；
- 保存 Source；
- 保存 Path。

一个按钮可以减少首屏复杂度，但不能把不同提交重新合并成`Accept all`。

## 7.3 写回后的可解释性

每次 Current 变化至少能回答：

- 谁发起；
- 目标是什么；
- 哪些对象 / Anchors 改变；
- 哪些建议未采纳；
- 如何 Undo / restore；
- Answer Snapshot 和 Source basis 在哪里。

## 7.4 反转条件

若真实使用证明逐项 Preview 造成高频阻碍，可以按已验证的低风险模式减少确认步骤；但不得取消目标可见性、Change Set、Undo 和“系统主动建议不自动提交”边界。

---

# 8. 九项高影响决定的对抗结论

| 决定 | 最强替代 | 为什么仍推荐 v6 | 最需要验证的风险 |
|---|---|---|---|
| 一个 Library | 多 notebooks / isolated libraries | 知识 identity、跨群关系与 Ask 才能连续 | 未来是否需要真正权限隔离 |
| 独立知识合法 | 强制归群 / Inbox | 第一条知识可直接写、可返回、无维护债 | 成熟库是否造成首页噪音 |
| Overview 可编辑 | AI 自动摘要 | 用户拥有范围解释与组织意图 | 用户是否愿意维护 prose |
| Topic 可递归、可直达 | 固定层级 / 全扁平 | 丰富层级与高效找回同时成立 | 过多空 Topic Overview |
| 连续 Knowledge Paper | 原子卡片优先 | 复杂论证、条件和 Evidence 保持上下文 | 长文扫描效率 |
| 多 Placement | 内容复制 | 多语境复用但只有一份 Current | identity 是否足够易懂 |
| Relation 是完整陈述 | related_to / similarity edge | 网络可读、可核验、可维护 | 创建成本与语言负担 |
| Network 以 Groups resting | 全 Knowledge graph | 全局方向稳定，细节按范围展开 | 意外连接发现是否不足 |
| Ask / Proposal 不自动写 Current | AI 默认整理 | 长期知识仍由用户拥有 | 写回是否显得过慢 |

维护提示留在相关上下文是上述权力边界的横向原则，不另建第十个产品中心或 Review 任务系统。

---

# 9. 三份 Fixture 复测

## 9.1 Fixture C：空库与直接写作

- K-W1 无 Group 保存后进入独立知识；
- 返回 Library 可见，Search 也可找回；
- 添加 G-WRITE Placement 后从派生视图消失；
- 移除最后 Placement 后重新出现；
- 无红点、完成度或 AI 归类；
- export / clean restore 后由 Placements 重新计算，而不是导出一个独立类型。

结论：通过语义压力测试；仍欠真实界面理解测试。

## 9.2 Fixture A：时效资格

- 两个成熟 Groups 与具体 cross-group exits 不自动产生 Group Relation；
- Source revision 只影响相关 Claim / criterion；
- AI Answer 不自动改 Current；
- 独立知识不是该旅程的主要表面，但任何新形成 Knowledge 都可选择暂不 Placement。

结论：关系节流和 AI 权力成立。

## 9.3 Fixture B：概念学习

- 同一 Knowledge 双 Placement 仍只有一份 Current；
- shared observation 不自动成边；
- same-pair 两条 Group Relations 保持两个完整 statements；
- Overview 需要表达学习目标和领域结构，不能由同一套自动摘要覆盖。

结论：Group / Topic、Overview 与 Relation 的精确语义成立。

---

# 10. 回写范围与未验证项

## 10.1 应进入 v6 Canonical

- 用户可见名称从“尚未进入知识群的知识”改为“独立知识”；
- 独立知识是由零 active Placements 推导的合法 Library view；
- Group / Topic 三问测试；
- Overview Editorial / Projection / Proposal 权力；
- Relation observation / candidate / current 升级节流；
- AI 四种写入授权。

## 10.2 不应现在冻结

- 独立知识在 desktop 的具体卡片 / list 布局；
- 独立知识增长后首页显示 3、5 还是 7 条；
- Overview 三类内容的像素比例；
- Relation Companion 宽度、动画和节点样式；
- `用于知识`的具体按钮文案；
- AI 低风险直接提交的最终规则清单。

## 10.3 仍需真实验证

- 用户是否把“独立知识”理解为合法内容，而不是孤立、低质量或待整理；
- 用户是否能分清 Group 与 Topic；
- 同一 Knowledge 多 Placement 是否会被误解成复制；
- Relation statement 的创建成本；
- AI 原子写回是否既可信又不显得繁琐；
- G100 / K10K 与大量独立 Knowledge 下 Library 是否仍保持安静。

---

# 结论

真正克制的知识库不是把所有知识强迫放好，也不是让 AI 替用户自动整理。它先保证每一份 Knowledge 都有稳定 identity、可找回、可直接编辑；再允许 Group、Topic、Placement 和 Relation 逐渐表达用户真正形成的结构。

“独立知识”因此不是产品遗漏，而是用户还没有、也可能永远不需要做出归属决定时的合法状态。产品品味体现在：系统承认这种状态，却不把它变成另一种首页、任务队列或焦虑来源。
