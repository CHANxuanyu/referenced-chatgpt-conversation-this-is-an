# AI-native 个人知识库

## Ardot v5 产品决策错位审计 v1.0

> 审计日期：2026-08-10  
> 审计对象：[AI-native 个人知识库 · 设计探索 v2（星图手稿）](https://ardot.tencent.com/file/711670254240951?node_id=0%3A1)  
> 本轮证据：从当前登录 Ardot 画布重新只读捕获的 Page 1 七屏；Page 2 当前为空  
> 产品基线：`AI-native-个人知识库-终局产品设计文档-v6.0.md`；文件名中的 v5 仅记录本审计形成时的轮次  
> 决策基线：`AI-native-个人知识库-关键产品决策审阅稿-v1.0.md`  
> 本轮边界：不修改 Ardot、不补画 Screen、不生成视觉选项、不制作原型  
> 证据限制：截图可以审查信息、层级、文案、构图和可见状态；不能证明真实点击、键盘、焦点、读屏、响应式、数据持久化或错误恢复  

---

# 0. 执行结论

## 0.1 总体判断

> **当前七屏仍不是完整产品设计。它们保存了可用的视觉气质和局部隐喻，但仍在表达一个“AI 知识星图”，而不是 v6 定义的“层级阅读优先、关系按需展开的个人知识库”。**

七屏的问题不是“按钮不够多”，而是产品中心、对象语义和跨屏连续性尚未成立：

1. 星图在 Screen 1 和 Screen 3 中承担了产品主视觉与本体，压过 Knowledge Library；
2. Screen 2 有正确的方向 3 + 2 气质，但被画成永久文章 / 星图分屏；
3. Group、Topic、Knowledge、Evidence 没有形成可执行的 Overview → detail 主干；
4. 边仍是装饰线或名词标签，没有 Relation statement、direction、standing 和条件；
5. Ask、Capture、Overview Edit 与 Sources 是孤立页面，没有 scope、write-back、return 和 truth continuity；
6. 内容仍使用“AI Agent 产品设计”的短演示材料，未承载两份真实夹具；
7. 七屏只展示宽屏正常态，没有 empty、partial、offline、historical、review、narrow、keyboard 或 screen-reader 等价证明。

## 0.2 保留、重构与淘汰

| 处置 | 当前资产 | 结论 |
|---|---|---|
| **保留为核心气质** | Screen 2 温暖阅读面 + 深色关系面 | 保留 3 + 2 的情绪对比，但改成 Reading Primary、Relation on demand |
| **保留为产品原则** | Screen 6 用户维护正文、AI 只提供建议 | 保留 user-owned Overview；重做 Proposal、Diff 和 disclosure |
| **保留为局部模式** | Screen 5 长答案与来源入口 | 保留可读 Answer；补 scope、basis、coverage、unknowns、atomic actions |
| **保留为流程骨架** | Screen 4 分步骤形成内容 | 保留 staged formation；拆开 Source Commit 与 Knowledge Commit，删除置信度审批流水线 |
| **仅保留为艺术参考** | Screen 3 深色空间感、星际关系气质 | 不再作为 IA、对象模型或全库默认图 |
| **必须重构** | Screen 1 首页 | 从“知识星图 Hero”改为稳定 Library catalog；Network 只是同义视图 |
| **必须降级到支撑工具** | Screen 7 Sources / Storage | 保留 local ownership，但不让存储策略成为七大主屏之一 |
| **明确淘汰** | 全局节点云、永久双栏、无类型连线、置信度百分比、八对象列表、三进入模式 | 这些表达与 v5 本体冲突，不能继续修补 |

## 0.3 十四项产品决定的当前覆盖

| KPD | 当前证据 | 判断 |
|---|---|---|
| 01 一个个人 Knowledge Library | Screen 1 有首页，但品牌和 Hero 都指向“知识星图” | **方向冲突** |
| 02 Groups / Network 同一 Library 两视图 | 没有稳定 Groups catalog，也没有同一 Shell 中的 view switch | **未证明** |
| 03 Group 是有边界的知识范围 | Screen 1 / 2 使用“知识群”字样，但没有 Boundary、governing question 或真实 Overview | **仅命名** |
| 04 Overview → Topic → Knowledge → Claim → Evidence | Screen 3 写了 L0–L5；七屏没有可走层级、Topic open 或 exact return | **概念图，不是体验证明** |
| 05 连续 Knowledge Paper | Screen 2 有文章气质，Screen 5 有长答案；没有 Section / Anchor / Evidence 连续阅读 | **视觉方向部分成立** |
| 06 一条 Knowledge 多 Placements | 无同一 identity 的双入口或语境差异 | **未证明** |
| 07 Relation 是完整语义陈述 | Screen 2 / 3 只有名词节点与装饰线 | **失败** |
| 08 Library Network 以 Groups 为 resting level | Screen 1 / 3 把混合节点星图作为主视觉 | **方向相反** |
| 09 Reading default + relation on demand | Screen 2 证明两种气质能共存，但关系面永久占据约三分之一画面 | **方向成立，交互模型错误** |
| 10 Ask 随处可用但不是聊天首页 | Screen 1 顶部有 Ask，Screen 5 有回答；范围与返回缺失 | **部分命名** |
| 11 Answer / Proposal 不自动推进 Current | Screen 6 写明“绝不自动改写”，但 Screen 4 使用逐条接受与置信度审批 | **局部成立、整体矛盾** |
| 12 Question / Conflict 可长期存在 | Screen 6 有“开放问题”建议，Screen 5 的提问仍是一次性查询 | **未形成产品对象** |
| 13 维护在相关上下文，不以 Review 驱动首页 | Screen 1“最近变化”和 Screen 6 常驻 AI 建议有抢占注意力风险 | **未证明克制性** |
| 14 本地 current knowledge、可导出可恢复 | Screen 7 显示本地来源，但把复杂 storage mode 直接暴露给用户 | **责任存在，表面过度** |

当前没有任何一项能够仅凭七张静态图被判为完整通过。

---

# 1. 本轮七步证据

## Step 1 · Screen 1 知识主页

![Screen 1 知识主页](/Users/a1234/Documents/Codex/2026-08-03/referenced-chatgpt-conversation-this-is-an/outputs/design-audit-ardot/v5-decision-audit-2026-08-10/02-screen-1-knowledge-home.png)

**健康度：高风险；视觉气质可用，产品入口错误。**

### 可保留

- 纸张质感、温暖排版和深色关系面形成明确品牌个性；
- 主要标题和少量精选内容比 Dashboard 更安静；
- Ask、探索和知识群入口同时出现，说明设计已意识到三种核心意图。

### 产品问题

1. 标题`知识星图 · Codex`和主句`把零散的笔记，连成一片活的星图`把 Graph 变成产品本体；
2. 右侧星图占据首页最大视觉权重，却没有可读 Relation statement；
3. `已收录 1,284 条笔记、312 段引用、47 个知识群`以数量证明价值，容易鼓励积累而非理解；
4. 输入框同时写`提问 / 收录`，把 Ask 与 Add 两种后果混为一个动作；
5. `精选星群`只有两张卡，没有完整 Groups catalog、稳定排序、Pins、Resume 和 Network view；
6. `最近变化 · AI 新析出 3 条`把系统生成变化放到首页注意力中心，与 contextual maintenance 冲突。

### 可访问性风险

- 纹理背景上的灰色小字对比度可能不足；
- 星图中的含义主要依赖位置、亮度和连线；
- 标签字号偏小，图中没有 List equivalent；
- 截图不能验证键盘焦点、读屏顺序和缩放后的重排。

### 未来证明责任

Screen 1 的 successor 必须先证明 Stable Library Groups catalog，再证明 Network 是同一 Library 的第二视图；不能继续把星图当 Hero 背景。

---

## Step 2 · Screen 2 双镜工作区

![Screen 2 双镜工作区](/Users/a1234/Documents/Codex/2026-08-03/referenced-chatgpt-conversation-this-is-an/outputs/design-audit-ardot/v5-decision-audit-2026-08-10/03-screen-2-dual-mirror.png)

**健康度：最值得保留；视觉方向成立，产品行为仍未成立。**

### 可保留

- 左侧阅读、右侧关系空间准确表达了用户选择的方向 3 + 2；
- 阅读面有连续文章、section、引用和留白，接近 Knowledge Paper；
- 关系面与正文气质不同，但仍在同一整体 Shell 中；
- 关系标签相对克制，没有把整个页面做成工具 Dashboard。

### 产品问题

1. 关系面永久常驻，普通阅读无法处于 Quiet；
2. 左右面积固定，尚未证明 Peek、Companion、Explore 由用户动作逐级打开；
3. `可逆行动、最小权限、可观测轨迹、HITL 边界`只是名词节点，不是完整关系句；
4. 文章没有 Group Overview、Topic hierarchy、DepthTrail、Anchor 或其他 Placements；
5. `新建笔记`沿用 note-first 语言，未表达写 Knowledge、加 Source 或保存 Question；
6. 右侧图没有 selection、Inspector、basis、standing、List 或 exact return。

### 可访问性风险

- 深色图中的小标签、细线和亮点对低视力用户不稳定；
- 方向不能只靠几何线条表达；
- 永久双栏在窄屏无法保持同等责任；
- 截图不能证明关系区域的键盘遍历和正文阅读顺序。

### 未来证明责任

保留温暖 Reading Primary 和深色 Relation Space，但必须用同一真实 Knowledge 演示 Quiet → Peek → Companion → Explore，并能关闭后精确回到原段落。

---

## Step 3 · Screen 3 IA 概念星图

![Screen 3 IA 概念星图](/Users/a1234/Documents/Codex/2026-08-03/referenced-chatgpt-conversation-this-is-an/outputs/design-audit-ardot/v5-decision-audit-2026-08-10/04-screen-3-ia-graph.png)

**健康度：不应继续作为产品结构；仅保留为 Relation Space 艺术参考。**

### 可保留

- 深色、空间感和局部发光可以成为 Explore profile 的情绪基础；
- 左侧对象、右侧动作、底部深度的尝试说明设计想表达可解释 IA；
- Ask / Search / Explore 三种意图已经被区分。

### 产品问题

1. `八类对象`与 v5 的五个日常概念、十四类内部资源均不一致；
2. `笔记 Note、主题 Topic、知识群 Group、引用 Reference、证据 Evidence、概览 Overview、查询 Query、来源 Source`混合了日常概念、Supporting Identity 和运行结果；
3. `三种进入模式`把 Ask、Search、Explore 画成模式选择，而不是不同意图和结果；
4. 图中混合群、知识和随机标签，违反 Group-level resting Network；
5. 节点名、边、方向和关系意义无法读取；
6. `L0 全景 Atlas → L5 证据`只是一条说明，画面本身没有层级打开、Focus / Open 或返回；
7. 太空图像比真实知识数据更醒目，视觉在替产品完成解释。

### 可访问性风险

- 信息主要靠空间、颜色、亮度和连线；
- 大量小字与低对比标签；
- 没有同义 List、表格或完整关系句；
- 无法从截图验证 focus、selection 与 activation 的分离。

### 未来证明责任

未来 Network 设计不能在这张图上补图例。应从真实 Group pair、两条 Current Relations、三条 Shared Knowledge 和一条 exact return 任务重新建立。

---

## Step 4 · Screen 4 采集流

![Screen 4 采集流](/Users/a1234/Documents/Codex/2026-08-03/referenced-chatgpt-conversation-this-is-an/outputs/design-audit-ardot/v5-decision-audit-2026-08-10/05-screen-4-capture.png)

**健康度：流程骨架可用，真相边界和语言需要重写。**

### 可保留

- 来源选择 → 检查 AI 结果 → 选择进入范围的分步结构容易理解；
- AI 结果要求用户确认，没有直接静默写入；
- 链接、文件和浏览器剪藏覆盖了真实输入来源。

### 产品问题

1. Source Commit 和 Knowledge Commit 被合成一次`确认捕获`；
2. `节点、关系、来源`三个抽取结果混合不同 Truth Roles；
3. 来源本身已经被保存，却仍作为一条“AI 已抽取、接受 / 丢弃”的对象；
4. `置信度 94% / 87% / 99%`无法说明 coverage、basis 或语义正确性；
5. 逐条`接受`把所有知识形成变成审批流水线，普通直接写作不应如此；
6. 只展示放入一个 Group，没有多 Placement、Source Attachment 或仅保存 Source 的结果；
7. 没有 OCR / AI 失败但原资料已保存的 partial success；
8. `Knowledge Compiler`是内部概念，不应进入日常产品语言。

### 可访问性风险

- `接受`状态主要依赖绿色按钮；
- 三行结果结构相似，但缺少可读后果说明；
- 小字号置信度与类型 badge 可能难以扫描；
- 截图不能验证批量操作、焦点保留和错误播报。

### 未来证明责任

未来 Formation 先证明`资料已保存`，再逐对象展示 Knowledge、Overview、Placement 或 Relation Proposal 的独立结算；拒绝 Candidate 必须零副作用。

---

## Step 5 · Screen 5 回答页

![Screen 5 回答页](/Users/a1234/Documents/Codex/2026-08-03/referenced-chatgpt-conversation-this-is-an/outputs/design-audit-ardot/v5-decision-audit-2026-08-10/06-screen-5-answer.png)

**健康度：阅读层可用，尚未证明 AI 与知识库真正汇合。**

### 可保留

- Answer 以连续正文呈现，适合阅读复杂回答；
- 顶部保留当前 Group，避免完全脱离知识范围；
- 来源与相关问题都有后续入口；
- 视觉克制，没有聊天气泡堆积。

### 产品问题

1. `已回答 · 引用 3 条来源`把 answer state、citation count 和充分性混在一起；
2. 没有 Requested / Effective / Used Context；
3. 没有 Answer Basis、claim-level citation、Coverage 或 remaining unknowns；
4. 来源只在底部以三张卡出现，无法知道哪一段使用了什么；
5. 没有`保存回答 / 用于现有知识 / 形成知识 / 保存问题 / 建立关系`的分权动作；
6. `相关追问`是推荐按钮，不是可持续 Question Knowledge；
7. 当前截图甚至显示了正文中的 Markdown `**`标记，说明排版仍是概念稿；
8. 没有从 citation 返回 Source Fragment、再关闭回原 Claim 的路径。

### 可访问性风险

- 正文、引用和辅助信息字号较小且对比偏弱；
- 相关问题横排在窄屏会失去顺序；
- source cards 没有可见的 claim mapping；
- 截图不能验证 heading 语义、读屏引用关系和焦点返回。

### 未来证明责任

使用真实长 Question 同时展示 scope、分层 Answer、Coverage、Unknown、Claim Support 与原子写回；用户可以只阅读离开，不被强迫保存。

---

## Step 6 · Screen 6 概览编辑器

![Screen 6 概览编辑器](/Users/a1234/Documents/Codex/2026-08-03/referenced-chatgpt-conversation-this-is-an/outputs/design-audit-ardot/v5-decision-audit-2026-08-10/07-screen-6-overview-editor.png)

**健康度：核心产品原则成立；需要从常驻 AI 审批面收敛为安静编辑。**

### 可保留

- 文案明确写出`由你维护正文，AI 只在右侧提供可插入的建议，绝不自动改写`；
- Overview 是连续可编辑正文，而不是卡片 Dashboard；
- AI 建议以独立动作插入或忽略，符合 Proposal 不自动推进 Current；
- 温暖阅读气质与主产品一致。

### 产品问题

1. AI 建议永久占据约三分之一宽度，普通编辑无法保持 Calm；
2. `AI 建议 · 开`把建议变成常驻模式，而不是局部 cue / Peek；
3. 每条建议只有`插入 / 忽略`，没有目标位置、Diff、依据和影响；
4. `保存`没有区分 Direct Edit Commit、Recovery、Current 与 Sync；
5. 没有 Topic tree、stable entrances、unknowns 和 cross-group exits 的结构投影；
6. 没有来源变化只影响局部 Overview 片段的复核状态；
7. 建议数量和右栏可能把维护重新变成主要任务。

### 可访问性风险

- 右栏低对比、小字号、重复按钮增加扫描成本；
- `开`状态和插入按钮依赖颜色；
- 双栏在窄屏需要保持正文优先和精确插入位置；
- 截图不能验证编辑器键盘行为、撤销、IME 和焦点恢复。

### 未来证明责任

Overview 默认是纯编辑阅读面；只有发生局部相关变化或用户明确查看建议时，才打开单一 Proposal inspector，并显示 exact target、Diff、basis 和可撤销后果。

---

## Step 7 · Screen 7 来源与存储

![Screen 7 来源与存储](/Users/a1234/Documents/Codex/2026-08-03/referenced-chatgpt-conversation-this-is-an/outputs/design-audit-ardot/v5-decision-audit-2026-08-10/08-screen-7-sources-storage.png)

**健康度：长期所有权责任正确，但被过早做成主产品决策页。**

### 可保留

- 本地文件夹和浏览器剪藏作为来源合理；
- 画面意识到“原始文件、知识库副本和同步”不是同一种责任；
- 当前选择明确，不把双向同步假装成唯一正确答案。

### 产品问题

1. 用户被要求在`原始文件为准 / 应用内副本为准 / 双向同步`之间做全局技术决策；
2. `双向同步——两边互相推送，按时间戳自动合并`隐藏严重冲突语义，不能作为简单 radio 选项；
3. 页面没有 Source Library、Source identity、Revision、Representation、availability 或 Reader；
4. 来源连接和 storage truth 被合在同一 Screen；
5. `Notion / 微信读书`等 connector 变成视觉中心，容易把插件能力误认为产品本体；
6. `完成`没有说明改变了什么、哪些来源受影响、能否撤销；
7. 用户已经说明这是本地产品，隐私不是当前主要设计问题；本屏不应因此占据七分之一核心设计覆盖。

### 可访问性风险

- radio 选择主要通过圆点和金色边框表达；
- 长技术说明字号较小；
- 三个选项并未清楚说明风险与恢复路径；
- 截图不能验证选择确认、冲突预览和读屏状态。

### 未来证明责任

把 Source Reader、来源可用性和本地所有权分别放回相关任务；只有用户进入 Forensic / Settings 时才展示存储策略，并先显示影响与恢复能力。

---

# 2. 跨屏连续性审计

## 2.1 当前七屏不是一条可执行旅程

屏幕标题看似覆盖 Home、Workspace、Graph、Capture、Answer、Overview Editor、Sources，但当前没有证明：

- Screen 1 打开 Group 后怎样进入 Screen 2；
- Screen 2 从一个 Relation 怎样进入 Screen 3，再怎样精确返回；
- Screen 4 保存 Source 后怎样进入 Knowledge 或 Overview；
- Screen 5 怎样从 Answer Claim 回到 Knowledge / Source；
- Screen 6 更新 Overview 后怎样影响 Screen 1 / 2；
- Screen 7 的 storage 选择怎样影响可读、可编辑和可恢复行为。

七个页面名称不能替代 Navigation、Scope、Owner、ReturnEnvelope 和状态转换。

## 2.2 产品 Shell 不连续

Screen 1 使用`知识星图 · Codex / Ask / 探索 / 设置`；Screen 2 使用`知识群 / 当前群 / 新建笔记`；Screen 3 使用概念模型；Screen 4–7 各自拥有不同 header。没有一套稳定 Shell 证明：

- Library Groups / Network；
- Search / Ask / Add；
- 当前 Group / Topic / Knowledge；
- Back / Up / Close；
- Supporting Utilities；
- Resume 与普通打开的区别。

## 2.3 真实内容压力为零

全部关键页面使用同一组`AI Agent 产品设计`短内容。它没有证明：

- 长标题和复杂限定条件；
- 三层以上 Topic hierarchy；
- 同一 Knowledge 双 Placement；
- same-pair 两条 Group Relations；
- Shared Knowledge observation；
- partial / provisional Resolution；
- Evidence challenge；
- exact Anchor return。

未来不能只替换文案；真实 fixture 会改变布局、披露、导航和关系密度。

---

# 3. 视觉资产迁移规则

## 3.1 可以进入下一阶段的资产

1. 温暖纸张与深色空间的双气质；
2. 编辑性长文而非卡片墙；
3. 关系空间比阅读面更深、更具空间感；
4. AI 建议不自动改写的明确原则；
5. Answer 使用连续正文而非聊天气泡；
6. staged formation 的清楚顺序；
7. 低饱和金色作为少量强调，而不是 standing 编码。

## 3.2 不能迁移的资产

1. `知识星图`作为产品名或首页中心；
2. 星云、星球或光点冒充 Group / Knowledge 节点；
3. 无意义的装饰连线；
4. 全库所有层级混在一张图；
5. 永久左右双镜；
6. 置信度百分比；
7. 八对象列表和三进入模式；
8. `新建笔记`、`节点`、`Knowledge Compiler`等旧语言；
9. 常驻 AI 建议栏；
10. 存储模式作为核心产品页面。

## 3.3 只能在用户确认后决定的资产

- Overview 是多强的编辑表面；
- Knowledge Paper 与 outline 的具体比例；
- Quiet / Peek / Companion / Explore 的转场；
- Group-level Network 的 resting density；
- Relation statement 与 graph label 的分工；
- Ask 的默认 disclosure；
- contextual maintenance cue 的醒目程度；
- desktop / mobile 中关系空间的布局方式。

这些必须服从关键产品决策，不能由现有七屏反向冻结。

---

# 4. 可访问性与验证限制

## 4.1 截图已经能证明的风险

- 多处浅灰小字与纹理背景组合；
- Graph 依赖颜色、空间、线条和亮度；
- 关系没有完整文本等价；
- 宽屏双栏缺少窄屏责任；
- 控件选中状态大量依赖金色 / 绿色；
- 标签密度和字号在 200% zoom 下可能无法维持；
- 视觉层级中英文混用，部分概念仍是内部术语。

## 4.2 截图不能证明的事项

- 颜色对比度精确数值；
- Tab order、focus visible、activation；
- screen reader name / role / state；
- Graph / List 的实际语义等价；
- motion reduction；
- 触控目标尺寸；
- mobile reflow；
- loading、empty、offline、partial、failed、historical 与 review 状态；
- 导入、保存、恢复和 AI 写回的真实后果。

因此当前不能声称可访问性通过，也不能把静态截图数量当设计完成度。

---

# 5. 下一阶段 Gate

进入任何新视觉选项前，必须先得到以下产品确认：

1. 一个 Library、Groups / Network 两个同义视图；
2. Overview 是可编辑导读；
3. Topic 可递归，Knowledge 默认连续 Paper；
4. 同一 Knowledge 多 Placements；
5. Relation 是完整语义陈述；
6. Network 以 Groups 为 resting level；
7. Ask 不自动改变 Current Knowledge；
8. 维护提示在相关上下文，而非独立 Review 首页。

确认后也不直接搭原型。正确顺序仍然是：

1. 用两份真实夹具冻结任务和 content state；
2. 提取不带视觉风格的 Surface skeleton；
3. 生成恰好三种视觉选项；
4. 用户选择一个目标；
5. 制作关键 Frames 和状态矩阵；
6. 把参考图与新设计逐屏并列比较；
7. 最后才判断是否需要可点击原型。

---

# 结论

现有设计不是全部推倒重来。Screen 2 已经找到了正确的情绪中心：知识应该安静地读，关系应该在需要时打开。Screen 6 也找到了正确的权力边界：AI 可以建议，但用户拥有正文。

真正需要放弃的是“星图就是产品”的假设。未来产品应该让用户先进入一个知识群、读懂它、逐层深入，再在明确需要时打开关系空间。图谱的价值来自关系可读、范围明确和能够返回，不来自节点数量或星云气氛。

这就是方向 3 + 2 从视觉喜好变成产品结构的分界线。
