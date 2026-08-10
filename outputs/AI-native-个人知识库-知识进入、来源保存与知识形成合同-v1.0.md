# AI-native 个人知识库

## 知识进入、来源保存与知识形成合同 v1.0

> 文档日期：2026-08-10  
> 文档状态：**ACTIVE_APPENDIX**  
> 上位权威：`AI-native-个人知识库-终局产品设计文档-v6.0.md`  
> 适用范围：Add、直接写作、Source save、Source Reader、Annotation、Evidence Binding、AI Proposal、Knowledge formation、import / migration 与 partial success  
> 相邻现行合同：`AI-native-个人知识库-关系、群级网络与探索连续性合同-v1.0.md`拥有 Relation Candidate / Current / History 与采用后果；`AI-native-个人知识库-Overview、连续阅读与知识正文合同-v1.0.md`拥有 Overview / Knowledge 的 direct edit、safe commit、Recovery、History 与 Anchor；`AI-native-个人知识库-Library入口、目录浏览与继续阅读合同-v1.0.md`拥有 Empty Library 的入口优先级、formation completion 回到 Catalog、以及 import / write Recovery 不冒充 Resume 的边界；本文拥有 Add entry、Source save、Annotation、Evidence Binding 与 formation transaction，并保证它们分别提交  
> 表面责任边界：`AI-native-个人知识库-表面架构、场景家族与完整设计证明合同-v1.0.md`拥有 Add Overlay、Source / Decision / Recovery surfaces、跨场景 return 与 DPB；本文拥有每次提交建立何种 truth 的事务语义  
> 用户语言边界：`AI-native-个人知识库-用户可见信息架构、产品语言与复杂度披露合同-v1.0.md`拥有添加、保存来源、形成知识、partial / zero-yield 回执与错误表达；本文只拥有 formation transaction truth  
> 不承担：OCR / parser 技术选型、Prompt、模型、存储 schema、原型布局或开发排期  
> 冲突规则：任何冲突以 v6 为准；本文件只深化 v6 AC-06–10、AC-22–30  
> 当前阶段：继续定义产品；不修改 Ardot，不生成新 Frame，不制作原型

---

# 0. 执行结论

知识进入产品时必须保持四次承诺：

```text
材料已保存
≠ 材料已被正确解析
≠ 用户已经形成知识
≠ 既有知识已经被更新
```

同样，用户自己的写作不需要绕道成为“待确认的 AI 候选”：

```text
用户直接写作
→ 本地安全保存
→ Current Knowledge
```

本合同冻结二十八项产品决定：

1. **Add 是不同后果的动作入口，不是一个万能导入框。**
2. **用户自己的直接写作经安全保存后就是 Current Knowledge。**
3. **普通写作不需要 Source、Group、Topic、type、AI review 或“采用自己的内容”。**
4. **从 Library 直接写作可以长期保持为独立知识。**
5. **用户选择的入口决定初始 truth role；系统不靠内容长度或粘贴行为偷偷改判。**
6. **保存外部材料首先建立 Source，不自动建立 Knowledge。**
7. **Source Commit 成功本身就是合法完成结果。**
8. **URL identity、网页快照和原始文件是不同保存程度，回执必须准确。**
9. **解析、OCR、转写和 AI 失败不撤销已经成立的 Source truth。**
10. **Source Attachment 只说明材料为什么进入某个 Group / Topic，不是 Knowledge Placement。**
11. **Highlight / Annotation 可以长期保留在 Source context，但不自动成为 Current Knowledge。**
12. **从 Source 形成 Knowledge 必须由用户发起或确认一个清楚的形成动作。**
13. **纯摘录默认仍是 Source Fragment；可复用理解需要用户表述或明确采用的 AI draft。**
14. **AI draft 是 Proposal，不因生成完成、点击查看或编辑标题而成为 Current。**
15. **一份 Source 可以形成零条、一条或多条 Knowledge；数量不是成功。**
16. **AI 的默认目标是最少必要变化，不是抽取最多卡片。**
17. **相似不等于同一 identity；去重必须区分重复 Source、新 Revision、补充 Evidence、更新 Knowledge、新 Knowledge 与只加 Placement。**
18. **给既有 Knowledge 增加 Evidence 不自动修改正文。**
19. **语义变化才产生 Knowledge Diff；Evidence Binding 和 Content Revision 分开。**
20. **形成带 Source basis 的 Knowledge 时，Knowledge 与必需 Binding 必须原子提交。**
21. **Placement 失败不撤销 Knowledge；它安全进入独立知识并可重试归位。**
22. **Relation、Overview、Question 和 Placement 建议分别提交，不随新 Knowledge 一键全收。**
23. **AI 建议出现在 Source 或受影响 Knowledge 的相关现场，不建立 Review 首页。**
24. **拒绝建议不会产生任何知识副作用，并抑制无新证据的重复建议。**
25. **迁入已有内容前先区分“我的知识”“参考资料”和“不确定”，不把所有文件同一种处理。**
26. **文件夹路径是 import provenance，不自动成为 nested Groups、Topics 或 Relations。**
27. **大批量导入先保护每份原材料，逐对象隔离失败，再汇总少量高影响决定。**
28. **Graph、Search、Ask、export、mobile、keyboard 与 screen reader 只能读取实际已提交的 truth，不读取未采纳 Proposal。**

---

# 1. 产品问题：知识库不能成为 AI 卡片工厂

最容易出现的错误流程是：

```text
导入文件
→ AI 自动拆成很多“知识点”
→ AI 自动建议很多关系和分类
→ 用户逐条接受 / 丢弃
→ 候选越来越多，理解没有增加
```

它的问题不只是 AI 可能错误，而是产品把四件事混在了一起：

- 保存材料；
- 阅读、标记和解释材料；
- 决定什么是用户当前的知识；
- 改变既有知识结构。

高质量产品必须允许用户在任何一层停下：

- 只保存 Source；
- 只做 Highlight / Annotation；
- 只把 Source 作为既有 Knowledge 的 Evidence；
- 形成一条新 Knowledge；
- 修订一条旧 Knowledge；
- 没有任何值得形成的变化。

每个结果都完整、可返回、可继续，不会被标成“尚未完成导入”。

---

# 2. Truth roles 与日常语言

## 2.1 四类 canonical truth 不变

| Family | 在形成流程中的责任 |
|---|---|
| Group | 新 Knowledge 可以出现在哪里；Source 为什么进入该范围 |
| Knowledge | 用户当前认可、可以直接用于阅读和 Ask 的理解 |
| Relation | 两条 Knowledge 或两个 Groups 为什么相连的完整陈述 |
| Source | 外部或可核验材料是什么、在何时保存了什么表示 |

Formation Workspace、Annotation、Fragment、Attachment、Binding、Proposal、Diff、import manifest 和 parser output 都是 Supporting Identities，不新增第五类 canonical truth。

## 2.2 用户看到的形成语言

| 用户意图 | 推荐语言 | 不使用 |
|---|---|---|
| 写自己的理解 | 写一条知识 / 在这里写 | 新建节点、提交草稿到 compiler |
| 保存外部材料 | 添加资料 / 保存资料 | 抽取知识、导入成功即形成知识 |
| 从材料形成理解 | 形成知识 | 接受节点、采纳 chunk |
| 给旧理解补依据 | 添加依据 | 合并 embedding、升级 confidence |
| 修改旧理解 | 更新这段知识 | 接受 AI 结论、覆盖旧卡片 |
| 放到另一个语境 | 放入知识群 | 复制笔记、自动归档 |
| 没有变化 | 资料已保存，没有形成新的知识 | 0 条产出、处理失败 |

## 2.3 Source、Annotation、Knowledge 的边界

```text
Source
  └─ Fragment / Highlight
       ├─ optional user Annotation
       ├─ optional Evidence Binding → Knowledge Claim
       └─ optional Formation action → new / updated Knowledge
```

Highlight 表示“我想再次看到这段材料”；Annotation 表示“我在这段材料旁边写了什么”；Knowledge 表示“我愿意把哪项理解作为当前可使用内容”。三者可以相连，但不能自动互相升级。

---

# 3. Add 是一个入口，不是一个结果

## 3.1 五种合法起点

1. 写一条 Knowledge；
2. 建一个 Group；
3. 添加一份 Source；
4. 迁入已有知识；
5. 保存一个 Question。

Add 在不同现场默认突出最自然动作：

| 当前现场 | Primary | 安静替代 |
|---|---|---|
| Empty Library | 写第一条知识 | 建 Group、添加资料、迁入、提问 |
| Group / Topic | 在这里写 | 添加资料、建 Topic、保存 Question |
| Knowledge | 继续写 / 编辑 | 添加依据、放入知识群、提出 Relation |
| Source Reader | 标记 / 形成知识 | 添加依据、提问、仅保留资料 |
| Answer | Follow-up | 保存 Snapshot、形成知识、更新现有知识、保存 Question |

这些是注意力优先级，不要求一个统一菜单在所有地方永久显示全部动作。

## 3.2 入口决定初始 truth role

- 从`写一条知识`进入：内容按用户原创 Knowledge 处理；
- 从`添加资料`进入：内容按 Source 处理；
- 从 Source 选中 Fragment 后`形成知识`：进入 Formation Preview；
- 从 Answer 执行`保存为知识`：进入 Query formation；
- 从 import 进入：先选择 material role mapping。

系统可以在用户粘贴一整篇文章时提示`如果这是外部材料，可以改为保存资料`，但不能自动改变已选择的 truth role。

## 3.3 Add 不接受的合并

- `提问 / 收录`同一个输入框；
- `导入 / 生成知识`同一个提交；
- `保存`同时创建 Source、Knowledge、Relation 和 Overview；
- `接受全部 AI 整理`；
- 未说明结果的`完成`。

---

# 4. 路径 A：用户直接写作

## 4.1 最低路径

```text
Write Knowledge
→ 输入有意义内容
→ 本地保护
→ Direct Commit
→ Current Knowledge
→ 当前 Scope Placement；无 Scope 时进入独立知识
```

## 4.2 写作不被结构阻断

开始时不要求：

- title；
- Group / Topic；
- Source；
- type；
- tags / properties；
- Relation；
- AI assistance。

标题可以稍后补。未命名时使用可辨认首行作为回退显示，不生成大量`Untitled 47`。

## 4.3 安全保存与用户心智

产品只需要向用户说清三种结果：

| 状态 | 用户语言 | Search / Ask 是否可用 |
|---|---|---:|
| 输入正在本机保护 | 正在保存… / 已在本机保护 | 否，仍是 recovery state |
| Current 已提交 | 已保存 | 是 |
| 提交失败但文字已保护 | 尚未更新当前知识；文字已保护 | 否，直到重新提交 |

Index、embedding、Overview projection 或 sync 延迟不撤销已经成功的 Current Commit。

## 4.4 当前 Scope 与独立知识

- 在 Group / Topic 内写作，默认建立当地 Placement；
- 在 Library 写作，没有 active Placement 时成为独立知识；
- 用户可以稍后 Add Placement；
- AI 可以建议位置，但不自动移动；
- Group archive 不结束 Placement，也不把整群内容变成独立知识。

## 4.5 AI 辅助写作的权力

- Rewrite / simplify / outline：默认只改当前选区 preview；
- 用户接受后按普通直接编辑提交；
- 用户拒绝不留下 Proposal debt；
- AI 不因为参与措辞就把用户正文改成 AI-owned Candidate；
- `总结一下`默认返回临时结果，不自动写入正文。

---

# 5. 路径 B：保存 Source

## 5.1 Source Commit 的最低真相

Source Commit 至少保存：

- source identity；
- material kind；
- origin / URL / file reference；
- received or observed time；
- available representation；
- content hash where possible；
- optional origin Group / Topic Attachment；
- current availability。

## 5.2 回执必须准确表达保存程度

| 实际结果 | 正确回执 | 不得声称 |
|---|---|---|
| 原文件 bytes 已保存 | 文件已保存，可离线打开 | 文字已解析 |
| 网页 snapshot 已保存 | 网页快照已保存 | 原网页永远可访问 |
| 只保存 URL identity | 链接已保存；内容尚未存档 | 网页内容已保存 |
| 音频已保存、转写未完成 | 音频已保存；转写处理中 | 已可全文搜索 |
| 仅部分文字解析 | 资料已保存；当前可搜索前 X 页 / 已解析部分 | 全文已处理 |

## 5.3 解析是 Source 的 representation，不是 Knowledge

Parser / OCR / transcript 可以产生：

- extracted text；
- page / time locators；
- images / tables representation；
- language / encoding diagnostics；
- partial coverage。

这些内容让 Source 可检索和引用，但不自动成为 Knowledge、Relation、Topic 或 Overview。

## 5.4 Scoped Source Attachment

从 Group / Topic 添加 Source 时，成功保存后可建立 Source Attachment：

```text
source_ref
scope_ref
purpose / context?
added_by
added_at
```

Attachment 只回答“这份材料为什么被放到这个语境”。它不意味着：

- Source 中每句话属于这个 Group；
- 已形成 Knowledge；
- 已存在 Evidence Binding；
- Source 与 Group 有 semantic Relation；
- AI 可以把 Source 内容自动写进 Overview。

## 5.5 Source-only 是完整结果

用户可以保存后直接离开。Source：

- 可从 Source utility、Search 或 origin Attachment 再次打开；
- 可以被显式选择进入 Ask；
- 可以以后标注、形成知识或添加 Evidence；
- 不显示整理进度、红点或“待消化”欠债。

---

# 6. Source Reader、Highlight 与 Annotation

## 6.1 Source Reader 的稳定责任

Source Reader 显示：

- identity 与 Revision；
- 原始 / snapshot / parsed / OCR / transcript representation；
- available / partial / unavailable；
- exact locator；
- highlights / annotations；
- used by Claims / Relations / Answer Runs；
- formation actions；
- return origin。

## 6.2 Highlight

用户选中一段材料，可以：

- 只高亮；
- 写 Annotation；
- 添加到现有 Knowledge 的 Evidence；
- 形成新 Knowledge；
- 针对选区 Ask。

高亮不自动进入 Current Knowledge、Overview 或 Network。一个 Source 可以拥有很多 Highlights，但不因此增加“知识数量”。

## 6.3 Annotation

Annotation 是用户在 Source context 中的边注。它可以是：

- 解释；
- 疑问；
- 反驳；
- 翻译；
- 阅读提醒；
- 与另一材料的比较提示。

它默认只在 Source Reader 和 Source Search scope 中出现。需要跨 Source、跨 Group 复用，或需要独立 Relation / Evidence 时，用户再执行`形成知识`。

## 6.4 Exact return

从 Knowledge Claim、Answer citation 或 Relation support 打开 Source Fragment 后：

- Source 打开实际使用的 Revision；
- locator 落到实际片段；
- 显示必要上下文；
- Close / Back 返回原 Claim / Answer / Relation 和 focus；
- original unavailable 时仍显示 saved snapshot / quoted fragment 与状态。

---

# 7. 路径 C：从 Source 形成新 Knowledge

## 7.1 三个形成入口

### 写下我的理解

用户选中 Fragment，打开空的 Knowledge Paper，并把 Fragment 作为 pinned basis。用户自己写标题与正文。

### 让 AI 起草

AI 基于选中 Fragment 或明确 Sources 提出 editable draft。它是 Proposal，用户必须看到 basis、qualifiers、scope 和 effect。

### 作为既有知识的依据

用户选择一个现有 Knowledge / Claim，建立 Evidence Binding；正文默认不改变。

## 7.2 纯摘录不自动成为 Knowledge

如果用户只想保存原文，正确结果是 Highlight / Annotation。形成 Knowledge 时至少要表达一种可复用责任：

- 这段材料说明什么；
- 适用于什么条件；
- 怎样支持、限定或挑战现有理解；
- 为什么值得独立进入其他语境。

产品可以允许 quote-based Knowledge，但 Quote 与用户解释必须区分，且 Source locator 保留。

## 7.3 Formation Preview

Preview 至少显示：

- proposed title / body；
- material origin；
- exact Source fragments；
- qualifiers / applicability；
- new vs update vs evidence-only；
- target Group / Topic Placements；
- similar Knowledge candidates；
- additional effects；
- Cancel 后果。

默认不显示模型 confidence 百分比。用户需要的是“为什么这样建议、会改变什么、还能否撤销”。

## 7.4 原子提交

当新 Knowledge 声称 Source basis 时，以下必须同一事务成功：

- Knowledge identity；
- Current Revision；
- required Evidence Binding；
- Source / Fragment refs。

Placement 可以独立失败：Knowledge 成功但 Placement 失败时进入独立知识，并保留重试归位。Relation、Overview Diff、Question 和额外 Placements 永远是另一次提交。

## 7.5 形成完成后的返回

提交后默认打开新 Knowledge，并提供：

- 回到 Source Fragment；
- 回到 origin Group / Topic；
- 检查 basis；
- Undo / History。

它不进入“AI 处理完成”成绩页，也不强迫继续处理其他建议。

---

# 8. 路径 D：给既有 Knowledge 增加 Evidence 或修订

## 8.1 Evidence-only

当 Source 只是支持、限定、挑战或提供背景：

```text
Source Fragment
→ Evidence Binding
→ existing Knowledge / Claim
```

正文和 Current Revision 不改变。Ask 可以说明“这条来源支持你的当前知识”，但不能说“这条知识已被更新”。

## 8.2 Semantic update

当 Source 真正改变用户当前理解：

```text
affected Knowledge / Anchor
→ before / after Diff
→ basis + applicability impact
→ explicit commit
→ new Current Revision
```

未受影响段落、Placements、Relations 和 Overview projections 不应被整篇重写。

## 8.3 Duplicate、Revision、Evidence 与 New Knowledge

相似内容至少有六种合法解释：

| 判断 | 结果 |
|---|---|
| 相同 Source bytes / snapshot | 复用 Source identity；可增加 Attachment |
| 同一 Source 的新版本 | 新 Source Revision，不覆盖历史 |
| 既有 Knowledge 的新依据 | 新 Binding，不改正文 |
| 既有 Knowledge 的语义变化 | 局部 Knowledge Diff |
| 同一 Knowledge 的新语境 | Add Placement |
| 真正独立的理解 | New Knowledge |

AI similarity 只能提供候选，不能决定 identity。

## 8.4 Source change

Source 新 Revision 进入后，系统先计算 impact：

- 哪些 Bindings 仍有效；
- 哪些 Claims 需要检查；
- 哪些 Answer Snapshots 只需标 stale；
- 哪些 Relations 的 basis 变化；
- 哪些 Overview projection 可以自动刷新；
- 哪些 Editorial prose 只能提出 Diff。

Source change 不静默覆盖 Current Knowledge，也不删除 Original Snapshot。

---

# 9. AI Formation Proposal

## 9.1 Proposal 出现条件

只有满足至少一项时才值得打扰用户：

- 发现可能属于已有 Knowledge 的重要新 Evidence；
- 现有 Claim 的适用条件可能改变；
- Source 明确挑战 Current Knowledge；
- 用户显式要求总结、比较或形成知识；
- 当前操作需要 identity / placement 选择；
- 变化会影响多个已使用对象。

普通 parser completion、chunk count、embedding cluster 或“相似度较高”不够。

## 9.2 Proposal 必须围绕决定组织

不是：

```text
抽取到 23 个知识点
接受  丢弃
```

而是：

```text
这份新资料可能让「K-M8」的结论范围过宽。

建议：把“提取练习优于概念图”收窄为该研究的材料、
练习程序和测验条件；保留旧 Revision 和方法学 challenge。

影响：K-M8 正文、K-S3 basis、一个 Answer Snapshot 的 freshness。
不影响：其他 Current Knowledge、两条 Group Relations、Source identity。
```

## 9.3 Proposal 的结果

- accept：只提交 Preview 中一个明确 action；
- edit then accept：以用户编辑后的内容提交；
- reject：零知识副作用；
- later：不形成 Review debt，只有回到相关现场才可再次看到；
- obsolete：basis / target 已变化时失效；
- zero-yield：Source 已保存，没有需要形成的变化。

## 9.4 建议抑制

拒绝记录：

- target；
- basis signature；
- rejected effect；
- time；
- reappear condition。

没有新 Source revision、目标变化或用户主动重跑时，不重复提出同一建议。

## 9.5 用户明确要求直接改

若用户明确说`直接把这段更新到 K-X`，系统仍需解析唯一 target 与 effect；可以提交并提供 Undo，但不能顺带更新其他 Knowledge、Overview、Relation 或 Placement。

---

# 10. 迁入已有知识

## 10.1 Import 前先确认 material role

批量迁入的顶层选择不是模板，而是：

| Role | 含义 | 默认目标 |
|---|---|---|
| 我的知识 | 我写下并愿意继续使用的理解 | Current Knowledge |
| 参考资料 | 外部材料、网页、论文、附件、摘录 | Source |
| 混合 | 两者都有 | 先按文件 / section preview |
| 不确定 | 暂时无法判断 | 保留原文件 / Source，稍后显式形成 |

系统可以根据 metadata 提议，但不能把一批个人笔记默认降为 Source，也不能把外部资料默认提升为 Current Knowledge。

## 10.2 文件夹路径不是产品本体

Imported path 可以保存在 provenance：

```text
old_vault/learning/memory/retrieval.md
```

它可以帮助建议：

- Group / Topic Placement；
- Source Attachment；
- Saved View；
- import report filter。

但不自动创建 nested Groups、Group Relation、Topic tree 或 formal semantic edges。

## 10.3 Import Preview

Preview 至少说明：

- detected identities；
- Knowledge vs Source mapping；
- duplicate / revision candidates；
- links preserved as references vs Relations needing review；
- selected Group / Topic mapping；
- unsupported content；
- object counts by truth role；
- what will not be imported；
- rollback / `继续未完成导入` boundary；这里是 import action，不是 Library Resume。

## 10.4 Partial import

- 每个 Source / Knowledge 原子提交；
- 一个文件失败不撤销已完成对象；
- manifest 记录 success / skipped / duplicate / partial / failed；
- `继续未完成导入`只重跑尚未成功提交的对象；它属于 Import Recovery，不写入 Library Resume；
- Import report 是 Supporting Record，不进入 Library；
- 删除 report 不删除已导入对象。

## 10.5 链接迁移

- 可解析的 internal link 保留 reference identity；
- 普通引用不自动成为 Relation；
- folder parent / child 不成为 broader / narrower Relation；
- 双链、共同 tag 和 adjacency 不自动形成 semantic edge；
- unresolved link 保留原文和 unresolved target，不静默丢弃。

---

# 11. 大来源与批量形成

## 11.1 先保护，再理解

120 页 PDF、300 Sources 或旧 vault 迁入时：

1. 保存原始材料 / manifest；
2. 按对象验证 Source / Knowledge identity；
3. 后台解析 representations；
4. 显示 coverage 与 partial state；
5. 只有用户要求或高影响变化出现时形成少量 Proposal；
6. 每项独立提交；
7. 随时暂停和恢复。

## 11.2 Decision Bundles 不是任务队列

可以按一个用户决定聚合多个 effects，例如：

> 这 12 份更新后的官方文件共同影响“2026 年租房材料清单”三条 Knowledge；是否先比较 Source revisions，再产生三份独立 Diff？

它不是永久 Inbox：

- 没有必须清零的 count；
- 用户可以忽略；
- 回到受影响 Knowledge 时再看；
- 同一决定内仍逐 object 原子提交；
- 一个失败不回滚其他已完成对象。

## 11.3 规模不改变心智模型

- S1 / S100 使用同一 Source truth；
- K1 / K10K 使用同一 Formation Preview；
- 大规模只增加 batch selection、progress、coverage、pause / resume；
- 不创建 Large Import mode、AI Knowledge Factory 或独立 Review product。

---

# 12. 状态与失败合同

## 12.1 Source states

| 状态 | Source truth | 可用动作 |
|---|---|---|
| Receiving | identity 尚未安全提交 | cancel、retry |
| Saved | representation 已按回执保存 | open、attach、parse、leave |
| Parsing | Source 已成立，representation 扩展中 | open original、leave |
| Partial | Source 已成立，部分内容可搜索 | use available、retry |
| Parse failed | Source 已成立，解析不可用 | open original、manual selection、retry |
| Original unavailable | saved snapshot / locator 仍存在 | inspect snapshot、update availability |
| New revision | predecessor 仍可读 | compare、impact analysis |

## 12.2 Formation states

| 状态 | 是否 Current | 用户可以做什么 |
|---|---:|---|
| Not requested | 否 | 阅读 Source、离开 |
| Preparing | 否 | 取消、修改 scope |
| Proposal ready | 否 | edit、accept、reject、later |
| Committing | 尚未 | 停止等待；不能重复提交 |
| Committed | 是 | open Knowledge、undo / history |
| Partial effects | 只有明确成功对象 | 查看逐项结果、重试失败项 |
| Rejected | 否 | 返回 Source；无副作用 |
| Zero-yield | 否 | 保留 Source；不显示失败 |

Source state 与 Formation state 必须独立。例如`Source Saved + Formation Not requested`是最普通、最健康的结果之一。

## 12.3 关键部分失败

| 失败 | 保留什么 | 不得发生 |
|---|---|---|
| OCR / parser failed | Source、original representation、Attachment | 撤销 Source |
| AI formation failed | Source、selection、user draft | 创建半条 Knowledge |
| required Binding failed | Source、Preview、recovery draft | 提交声称有 basis 的 Knowledge |
| Placement failed | committed Knowledge + Binding | 删除 Knowledge；它进入独立知识 |
| Relation Proposal failed | Knowledge / Source 不变 | 回滚 Knowledge |
| Overview projection failed | Current truth 不变 | 回滚 commit |
| index failed | Current truth 可直接读取 | 声称内容不存在 |
| sync failed | local Current / Source 保持 | 阻止本地阅读和编辑 |

---

# 13. 返回、本地性与责任等价

## 13.1 Return Envelope

Formation 入口保存：

- origin Source / Knowledge / Answer / Group / Topic；
- Anchor / Fragment；
- scroll / focus；
- selected text；
- expanded details；
- pending proposal draft；
- Search / Ask / Explore scene if applicable。

Cancel、commit 或 close 都回到可解释现场；成功提交可以先打开结果，再用 Back 回原 Fragment / Claim。

## 13.2 Local-first

- direct writing、file save、Source Reader、manual highlight、Knowledge commit 和 History 在本地成立；
- AI / OCR unavailable 不阻止 Source-only 或 user-authored Knowledge；
- Source representations、Bindings、Knowledge revisions 与 import manifest 可进入 Knowledge Package；
- parser cache、embedding、thumbnails 和 transient Proposals 可重建；
- restore 后 deep links 指向 current 或明确 historical targets。

## 13.3 Responsive

### Desktop

Source / Knowledge 可以按意图形成 Reader + Companion，但不永久显示 AI candidate rail。

### Compact / mobile

Source、selection actions、Formation Preview、Knowledge result 分时成为 Primary；返回链保持。关键后果不能藏在 hover。

## 13.4 Keyboard / screen reader

- Add actions 名称表达结果；
- file / URL status 有文字，不只用颜色；
- Source Reader 可以键盘选中、Highlight、Add Evidence、Form Knowledge、Back；
- Preview 中 basis、target、effect、Cancel 和 Commit 顺序可读；
- partial result 使用 live region，但不抢走正文 focus；
- 拒绝 / accept 不只依赖绿色和红色；
- success 后 focus 到结果标题或回执，并提供回 origin 的清楚动作。

---

# 14. 真实内容压力场景

## FX-01 · Empty Library 直接写作

Fixture C 的 K-W1 从空 Library 直接写下。无需 Source、Group 或 AI，Current Commit 后出现在独立知识；返回 Library 可再次打开。

## FX-02 · Source saved、parse partial

Fixture C 添加`旧写作草稿.md`。原文件已保存，但只解析前半部分；回执是`资料已保存，当前可搜索已解析部分`，不创建 Knowledge 或 Review item。

## FX-03 · Source Fragment → user-authored Knowledge

Fixture C 从 S-W1 f1 形成 K-W2。用户重写正文；K-W2 + required Binding 原子提交，Placement p2 成功；Source 保持独立 identity。

## FX-04 · Evidence-only

Fixture B 的 S-M10 方法学评论先以 challenge Binding 影响 K-M8，不自动建立 K-M9。只有用户形成可复用研究解释时才创建 K-M9。

## FX-05 · Semantic revision

Fixture B 用户检查 S-M10 后收窄 K-M8。系统提交局部 Revision，保留旧 statement、challenge 和历史；不整篇重写相关 Overview。

## FX-06 · Answer → three separate Knowledge commits

Fixture B 从同一 Answer 分别形成 K-S1、K-S2、K-S3。三者各有 title、body、basis、Placement 与 Cancel；保存 Answer 不创建它们，一项失败不撤销其他项。

## FX-07 · Source change without overwrite

Fixture A 的官方规则 Source 新 Revision 改变。系统先显示 criterion impact，再由用户更新相应 Knowledge / Resolution；旧 Answer 和旧 Knowledge Revision 保留。

## FX-08 · URL identity without snapshot

网页暂时无法抓取，但 URL 有效。系统可以保存`链接 identity`并说明内容尚未存档；它不能被当作离线 Source text 或 Claim Evidence，之后可重试 snapshot。

## FX-09 · Duplicate Source, new Attachment

用户在第二 Group 再次添加同一 PDF。hash 命中既有 Source：复用 Source identity、增加新 Attachment；不复制文件、不自动 Add Knowledge Placement、不创建 Group Relation。

## FX-10 · Placement failure

用户从 Source 形成 Knowledge，Knowledge + Binding 成功，目标 Topic 同时被移动导致 Placement 失败。Knowledge 进入独立知识，返回 Preview 可以重选位置。

## FX-11 · Import mixed vault

旧 vault 包含用户原创 Markdown、PDF、网页剪藏与附件。用户先选择 mixed；Preview 将原创笔记映射为 Knowledge，PDF / clip 映射为 Source，folder path 只保留 provenance 并提出 Group / Topic mapping，不自动创建 nested Groups。

## FX-12 · 120-page PDF zero-yield

Source 完整保存和解析，但用户只需要它作为参考，没有形成稳定新理解。系统显示`资料已保存，没有形成新的知识`；没有 47 个待确认卡片。

---

# 15. 专项验收合同

| FEC | 对应 v6 AC | 验收 |
|---|---|---|
| FEC-01 | AC-09 | 用户直接写作安全提交为 Current，不进入 Proposal / Review |
| FEC-02 | AC-01 / 09 | Library 直接写作无 Placement 时进入独立知识，可再次打开 |
| FEC-03 | AC-06 | Direct Knowledge 使用连续 Paper，不强制原子卡片或 title-first |
| FEC-04 | AC-07 / 08 | Add Placement 不复制正文，Placement 失败不删除 Knowledge |
| FEC-05 | AC-22 | AI rewrite preview 未接受时不进入 Current 或未来 Ask truth |
| FEC-06 | AC-25 | Source Commit 与 parse / OCR / AI 分开；后者失败不撤销 Source |
| FEC-07 | AC-25 | URL-only、snapshot、original file 与 partial parse 回执不夸大保存程度 |
| FEC-08 | AC-12 / 25 | Source Attachment、Knowledge Placement 与 Evidence Binding 不混淆 |
| FEC-09 | AC-20 / 25 | Source Fragment exact locator 与 representation role 可检查并返回 origin |
| FEC-10 | AC-22 / 24 | Highlight / Annotation 不自动成为 Knowledge / Question / Review item |
| FEC-11 | AC-20 / 23 | Source-based Knowledge 与 required Binding 原子提交；Binding 失败不产生半条 Knowledge |
| FEC-12 | AC-23 | New Knowledge、Evidence-only、local Diff、Placement、Relation、Overview 分别提交 |
| FEC-13 | AC-26 | AI Proposal 拒绝零副作用，并抑制无新证据的重复建议 |
| FEC-14 | AC-26 | zero-yield 是 Source-only 合法完成，不显示处理失败 |
| FEC-15 | AC-27 | 新 Source Revision 先 impact analysis，不覆盖 Current Knowledge |
| FEC-16 | AC-27 / 28 | Evidence-only 不创建正文 Revision；Semantic Diff 保留 predecessor |
| FEC-17 | AC-07 / 13 | 同一 Source 增加第二 Attachment 不复制 Source、不创建 Placement / Relation |
| FEC-18 | AC-04 / 12 | imported folder path 不自动成为 nested Group、Topic 或 Relation |
| FEC-19 | AC-25 / 26 | mixed import 逐对象区分 Knowledge / Source / duplicate / unsupported |
| FEC-20 | AC-25 / 29 | 批量解析与 AI 失败隔离；已保存对象可本地打开和恢复 |
| FEC-21 | AC-17 | Formation Cancel / Commit / Result → Back 恢复 origin Fragment / Claim / Scope |
| FEC-22 | AC-30 | Export / Restore 保留 Source revisions、Bindings、Knowledge revisions、Attachments 与 import provenance |
| FEC-23 | AC-31 | desktop / compact / mobile 保留 save receipt、basis、target、effect、partial state 与 return |
| FEC-24 | AC-32 | keyboard / screen reader 可完成 Add → Source save → Fragment → Form → Commit → Back |

---

# 16. 外部研究与产品推论

## 16.1 Zotero：原文标注、Note 与原文返回是不同责任

Zotero 官方 Reader 文档允许用户先在 PDF 建 annotation，再选择把 annotation 加到 note；加入 note 后自动保留 citation 与回到 PDF 页面的链接。[Zotero PDF Reader and Note Editor](https://www.zotero.org/support/pdf_reader)

产品推论：Source Fragment、Annotation、用户形成的内容和 exact return 应保持分权。Zotero 的 note 模型不直接证明本产品应把每个 highlight 变成 Current Knowledge。

## 16.2 NotebookLM：用户写的 Note 与保存的 AI response 需要不同后果

NotebookLM 官方文档区分用户写的新 note 和保存 chat response；保存的 response note 不可编辑，note 还可以另行转换为 source。[Create & add notes in NotebookLM](https://support.google.com/notebooklm/answer/16262519?hl=en)

产品推论：生成结果、用户写作和 Source conversion 必须让用户知道后果。但本产品不复制“把 note 转成 source”的真值模型：Source、Knowledge 与 Saved Answer 从一开始就有不同 owner。

## 16.3 Obsidian Web Clipper：保存范围与 AI interpretation 可以在提交前检查

Obsidian 官方 Web Clipper 允许保存整页、selection 或 highlights；Interpreter 可以提取、总结、解释和转换页面数据，最终由用户选择模板和`Add to Obsidian`。[Clip web pages](https://obsidian.md/help/web-clipper/capture) · [Interpreter](https://obsidian.md/help/web-clipper/interpreter)

产品推论：selection、representation 和 AI transformation 应可预览。但本产品不能让模板输出同时冒充 Source 与 Knowledge，也不把 folder / file creation 当成 semantic formation。

## 16.4 Readwise Reader：Highlight 与 Note 继续依附于原文语境

Readwise Reader 官方文档允许用户在阅读时 highlight、给 highlight 加 note、添加 document note，并从聚合视图回到原文位置。[Highlights, Tags, and Notes](https://docs.readwise.io/reader/docs/faqs/highlights-tags-notes)

产品推论：标记材料和写长期知识不是同一个动作；原文位置必须保留。其 highlight / note taxonomy 不直接证明这些内容应成为本产品的 canonical Knowledge。

## 16.5 研究没有证明什么

这些资料没有证明：

- 用户愿意逐条 review AI 提取；
- 自动摘要比直接阅读和用户表述更能形成理解；
- 文件夹、标签或模板应该决定 Group / Topic；
- Highlight、annotation、saved response 和 Knowledge 可以共享一个 lifecycle；
- 任何固定置信度阈值可以替代 identity 与 effect 判断；
- “生成更多知识点”能提高长期找回、理解或决策质量。

因此 Source-first、Direct Current、zero-yield、Proposal contextuality 和 formation atomicity 都仍需真实任务验证。

---

# 17. 对 Ardot Screen 4 下一轮设计的证明要求

当前 Screen 4 可以保留“先保存输入、再检查结果”的阶段感，但不能继续使用`来源 → AI 抽取节点 / 关系 / 来源 → 置信度 → 接受`这套产品模型。

## 17.1 最少证据包

1. **Add intent**：写知识与添加资料是两个后果清楚的动作；
2. **Direct writing**：无 Source / Group / AI 的 Current Commit 与 Library return；
3. **Source receipt**：文件已保存、解析中，用户可以立即离开；
4. **Partial Source**：原文件可读、部分文字可搜、解析可重试；
5. **Source Reader**：真实 Fragment、Highlight、Annotation 和 Used by；
6. **Formation choice**：写我的理解 / AI 起草 / 添加为现有知识依据；
7. **Formation Preview**：basis、qualifiers、new / update、Placement 与 effect；
8. **Evidence-only**：增加 Binding，不改正文；
9. **Semantic Diff**：只更新受影响 Anchor，保留 predecessor；
10. **Zero-yield / Reject**：Source 保持，零 Review debt；
11. **Duplicate / Attachment**：复用 Source identity，不复制或连边；
12. **Mixed import / batch partial**：逐对象角色、失败隔离、pause / resume；
13. **Result → Source exact return**；
14. **mobile / keyboard / screen reader equivalent**。

这些责任可以由 Full Frame、Overlay、Reader state、Preview、transaction result 和 State Matrix 组合证明，不要求十四张并列页面。

## 17.2 视觉必须避免

- `Knowledge Compiler`等内部名字；
- 一排节点、关系、来源候选卡；
- 置信度百分比；
- `接受 / 丢弃`成为所有形成动作；
- Source 已保存却仍作为待接受候选；
- 把解析完成当知识完成；
- 永久 AI suggestions rail；
- 导入产出数量、完成度或待处理红点；
- folder tree 自动变知识群树；
- 一个`确认捕获`提交所有 truth roles；
- 失败时隐藏已成功保存的 Source；
- 成功后进入成绩页而不是新 Knowledge / Source / origin。

## 17.3 方向 3 + 2 在 Formation 中的比例

- 方向 3 负责 Source Reader、Knowledge Paper、Fragment → Claim 的纵向核验；
- 方向 2 只在已有 endpoints 和完整 statement 时帮助检查 Relation Proposal；
- 导入 / 形成过程不需要星云背景或节点爆炸动画；
- 新 Knowledge 首先以可阅读 Paper 出现，Network 是后续可选表达；
- 温暖阅读面比“AI 正在构建图谱”的视觉表演更重要。

---

# 18. 最终产品判断

一个知识库的可信度不是从 AI 抽取数量开始，而是从每一步后果都准确开始：

> 用户写下的理解，安全成为用户当前的知识；用户保存的材料，先作为可返回来源存在；用户在材料中标记和思考，不被迫马上结构化；只有当用户决定某项理解值得复用时，它才形成 Knowledge；新证据可以补充或修正旧知识，但不会静默覆盖历史。

如果 Source save、Knowledge formation 和 semantic update 被合并，产品会看起来很智能，却无法回答“这句话现在为什么属于我的知识”。把它们分开不是增加流程，而是让用户拥有知识。
