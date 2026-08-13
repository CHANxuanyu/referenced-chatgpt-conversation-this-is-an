# AI-native 个人知识库

## 搜索定位与知识找回合同 v1.0 — Search Scope、Result Identity、Deep Anchor 与诚实无结果

> 文档日期：2026-08-06  
> 文档性质：产品本体合同，不是搜索引擎技术方案、输入框线框、快捷键清单或原型规格  
> Canonical 产品定义：`AI-native-个人知识库-终局产品设计文档-v4.0.md`；本合同只证明 Search 定位与找回责任，不得反向改写 v4.0  
> v4.0 写入覆写：普通用户直接写入本地保存后就是当前 Knowledge，Search 可立即找到；只有显式 Draft 或建议结果需要 Draft / Proposed 标记  
> v4.0 深层命中覆写：索引可在 Block / Anchor / chunk 粒度召回，但结果 identity 必须聚合为 Knowledge + matched Anchor + Placement；深层命中不会把 Section、Inline Claim 或 chunk 升级成可收藏和连线的新知识对象  
> v4.0 Query 覆写：Search candidate 不等于 Ask 的 Used Context；Search 无结果与 Ask 负面回答都必须限定 Scope、filters、Index Coverage、Source availability 与 exclusions，不得从局部未命中推断全库不存在  
> v4.0 Scope 覆写：Topic Search 必须显式区分 direct 与 descendants；Group root Placement 属于该 Group，active Placement 为零才是 Unplaced；Source title / body 是否进入范围由 Source Attachment 与 source expansion 分别决定，不能从 Evidence Binding 或 Group Boundary 推断  
> 2026-08-10 Relation Lifecycle 覆写：普通 Search 默认返回 maintained current Relations；ended、superseded、retracted、archived、review_due、open Challenge 与 RelationCandidate 可分别筛选，不能继续压成 Contested / Stale 两个标签。完整合同见`AI-native-个人知识库-关系陈述生命周期与网络可信性合同-v1.0.md`  
> 2026-08-10 Knowledge Relation Type Registry 覆写：Search 按五个 Knowledge relation families、精确 type、方向与 direct / derived 筛选；搜索“支持”时可区分知识关系、来源作用与本次回答依据；`supersedes / retracts / reopens / uncertain_about`只从对应 Transition / Disposition / Question scopes 找回，不出现在 ordinary Relation type filter。完整合同见`AI-native-个人知识库-知识关系类型注册表与跨层语义合同-v1.0.md`  
> 2026-08-10 Question Search 覆写：Question 是 Knowledge result，可按 resolution / pursuit / change / library 四轴筛选；Runtime Unknown 与 Gap Marker 只在所属 Run / owner 专用范围找回。Target references、answer basis 与 Subquestions 不进入 ordinary Relation filters。完整合同见`AI-native-个人知识库-问题知识、未知与求解生命周期合同-v1.0.md`  
> 2026-08-10 时效内容夹具覆写：资格 / 规则型 Knowledge 与 Question 的结果必须显示 effective time、`as_of` 与关键 Applicability；历史规则可以被找回，但不能因文本更相似而冒充 current。真实用例见`AI-native-个人知识库-真实端到端使用样例与设计数据夹具-v1.0.md`  
> 历史深层模型：`AI-native-个人知识库-产品定义-v3.0.md`  
> 相邻合同：`AI-native-个人知识库-知识深度与关系探索合同-v1.0.md`、`AI-native-个人知识库-知识节点粒度与内容组成合同-v1.0.md`、`AI-native-个人知识库-AI查询与知识回答合同-v1.0.md`、`AI-native-个人知识库-直接创作编辑与版本历史合同-v1.0.md`、`AI-native-个人知识库-属性Facet与适用条件合同-v1.0.md`、`AI-native-个人知识库-产品对象层级与身份治理合同-v1.0.md`、`AI-native-个人知识库-关系陈述生命周期与网络可信性合同-v1.0.md`  
> 核心问题：用户怎样在自己的知识世界里，可靠地找回一个对象、对象内部的一段内容或它在结构中的位置，并知道系统搜了哪里、为什么命中、哪里尚未覆盖

---

# 0. 执行决定

本轮冻结五十五项产品决定。

1. **Search 是知识定位能力，不是简化版 Ask。** 它返回已经存在的对象、精确位置与匹配原因，不生成综合结论，不替用户回答问题。
2. **Search、Browse、Ask、Explore、Find 与 Filter 是六种不同承诺。** 它们可互相转接，但不能因为同一个输入框而静默混成一种行为。
3. **全局搜索、范围内搜索、页内查找、链接目标选择器、命令面板和 Saved Search 共用底层查找语义，但拥有不同合法结果与动作边界。**
4. **Search 的结果单位是用户可识别的 owner identity，不是检索 chunk 或 Supporting Record。** Chunk、Block、Revision、Assertion、Binding、Answer Claim 与 Evidence Fragment 只说明命中位置、历史或作用；默认聚合到所属 Node、Group、Source 或 Knowledge Snapshot，专用模式才展开 record。
5. **一个 Search Hit 必须同时保存 Target Identity、Matched Anchor、Matched Revision 与当前 Placement。** 用户点开后必须到达真正命中的位置，而不是只打开对象顶部。
6. **同一 Node 在多个位置出现时仍只是一条对象结果。** 结果展示当前最相关 Placement，其他位置可展开；不能按 Placement 伪装成多个 Node。
7. **相同标题不代表相同对象。** 系统通过定义、类型、Applicability、所属 Group、状态与更新时间消歧，永不因标题相同自动合并。
8. **默认 Search 包含 Current Revision；Explicit Draft 使用可见 Draft scope。** Recovery Checkpoint 与 Edit Buffer 不进入 Search。找回能力不能隐藏草稿，但也不能把异常保护或半句话伪装成知识命中。
9. **Archived 默认不混入普通结果，但可显式包含。** Trash 只在废纸篓内搜索；Historical Revisions 默认关闭，必须显式开启。
10. **Source 与 Saved Answer 可以被搜索，但必须作为独立对象组和独立知识角色显示。** 找到 Saved Answer 不会让它成为当前 Knowledge Truth。
11. **Scope Anchor 与 Expansion Policy 分开。** “当前 Group”只定义起点；是否包含 descendants、跨群 Placements、正式 Relations、Sources 与历史版本分别决定。
12. **当前焦点只帮助恢复位置，不暗中扩大搜索范围。** 搜索发生在哪里、搜了哪些对象必须可见。
13. **范围内无结果而全局有结果时，系统只提供明确的“搜索全部知识”建议。** 全局结果不能偷偷混进当前 Scope 的结果集。
14. **默认模式是 Best Match。** Exact Title、Canonical Name、Alias、精确短语与高保真词面匹配优先于语义相似。
15. **Search 提供 Best Match、Exact Words 与 Similar Meaning 三种可理解模式。** 专业检索操作符是渐进披露，不是普通用户的入场券。
16. **语义相似只是一种命中理由，不是 Relation。** Similar Meaning 结果必须标明，不能在 Graph 中自动生成边或把相似度写成概念关系。
17. **结果不显示裸露的 relevance / confidence 百分比。** 系统显示“标题完全匹配”“正文包含原句”“别名匹配”“含义相近”等可解释理由。
18. **排序优先级是匹配忠实度，其次是身份与类型意图、Scope / Applicability / 状态，再其次是当前上下文，最后才是近期性。** 最近编辑不能凌驾于真正匹配。
19. **近期性只用于合理 tie-break，不代表更新、更正确或更权威。** 搜索不能训练用户把“最近”误读成“可信”。
20. **同一 Search Session 内的结果要足够稳定。** 索引变化时提示刷新，不在用户阅读过程中静默大幅重排。
21. **每次查询、Scope、模式、过滤或排序改变都创建新的 Search Run。** Search Request 保留原始输入和解释后的输入，Search Run 记录一次实际执行。
22. **Search Result Set 是运行时快照，不是知识对象。** 它不进入 Library、Overview、Graph、Review，也不成为 Relation endpoint。
23. **Search Back 必须恢复查询、Scope、过滤、模式、结果顺序、滚动位置和当前选中项。** 返回一个空输入框不算连续体验。
24. **Recent Searches 是本地便利记录，不是 Inbox 或长期知识。** 清除搜索历史不会删除内容、对象或 Saved Search。
25. **查询解释必须保留原始输入。** 同义词、别名、拼写、转写或自然语言过滤被规范化后，用户仍能检查系统理解了什么。
26. **中文、英文、数字、重音字符、缩写、别名与转写都属于一等检索语义。** 产品不能只对空格分词的英文资料表现良好。
27. **OCR 不确定、音视频转写不确定和无法索引的文件必须在命中或无结果时可见。** 低质量解析不能伪装成完整覆盖。
28. **Search Index 与 canonical knowledge store 是两个层次。** 索引损坏、重建或清空不得删除用户知识；完整恢复可以从 canonical data 重建索引。
29. **核心精确搜索和全文搜索必须本地、离线可用。** AI 或语义服务不可用时降级为 Exact / Full-text，而不是让知识库失去查找能力。
30. **无结果的正确表述是“在本次搜索覆盖中没有找到匹配”。** 不能把 Scope 过窄、过滤排除、索引不完整或来源不可用写成“你的知识里没有”。
31. **Search Coverage 必须可检查。** 至少说明 canonical objects、Sources、OCR / transcription、Historical Revisions 与排除状态是否完整。
32. **每一条结果必须有明确的对象类型、人话说明、匹配片段、位置路径、状态和匹配原因。** 只有标题列表无法支撑可靠找回。
33. **精确打开必须保留定位语义。** Search → Node + Anchor + Placement 后，Back、Up、DepthTrail 与 Return Stack 都有效。
34. **Find in Current Object 只查当前对象的当前可读 revision。** 它不暗中查整个 Group，不等于全局 Search，也不承担 Replace。
35. **被折叠、延迟加载、复用或嵌入的内容在页内命中时必须说明所在边界。** 用户应知道结果属于当前正文、引用内容还是嵌入对象。
36. **Link / Relation Target Picker 只返回合法目标 identity。** 匹配到一个 Block 不会把 Block 变成 Relation endpoint；选中对象也只有在编辑器明确提交后才建链接或关系。
37. **Command Palette 查动作，Search 查知识。** 两者可以同一快捷入口并存，但结果分区、键盘行为与执行后果必须不同。
38. **问题形态的搜索只提供“用这些知识提问”。** 不自动切 Ask；转换时传递用户选中的 object identities / anchors，而不是把搜索 snippets 当作事实上下文。
39. **Search → Explore 只打开该对象已有的 Structure / Relations / Placements。** 共同命中、共现或语义相似都不自动形成长期边。
40. **Saved Search 复用既有 View 对象。** 它保存 criteria、scope、filter、sort 与 presentation，不保存结果成员，也不创建 Group、Overview 或 Relation。
41. **Saved Search 每次打开都按当前知识动态求值。** 若用户需要冻结一批结果，应创建 Knowledge Snapshot 或导出，而不是把 View 偷换成静态集合。
42. **Working、Archived、Historical、Source 与 Saved Answer 的进入必须可预测。** 状态过滤是可见产品语义，不是隐藏的 ranking 惩罚。
43. **重命名、Alias、Redirect 与已删除目标必须区分。** 旧名字可以找到新 identity；Redirect 可解释；真正删除的对象不能用幽灵结果冒充存在。
44. **搜索不执行知识修改。** Rename、Merge、Move、Create Relation、Delete、设草稿为当前或应用 Proposal 都必须进入相应 Editor / Change Set，不能由查询文本直接触发。
45. **搜索质量以“找到正确目标并保持上下文”衡量。** 结果数量、查询次数、点击率、Semantic 命中量与 Recent 点击不作为核心成功指标。
46. **大规模结果采用分组、渐进展开与虚拟化。** 100 Groups、10,000 Nodes、300 Sources 时，用户仍先看到少量可判断的高价值结果，而不是无限结果墙。
47. **搜索必须完整支持键盘、屏幕阅读器与 200% zoom。** 高亮不是唯一信号；结果类型、匹配原因、状态和定位都要可被读取。
48. **本合同不授权开始原型或实现。** 产品定义确认前，不能让一个漂亮的 command bar 替代尚未解决的 identity、coverage、ranking 与 no-result 语义。
49. **Topic 的 direct / descendant 是搜索执行语义，不只是树形 UI。** 默认 Topic Search 可以包含 descendants，但结果摘要必须写`包含子主题`；切为`只看这里`后只读取 direct Placements 与 direct Source Attachments。
50. **Ancestor Scope 不制造镜像 membership。** descendant 命中保留 Knowledge identity 与 exact Placement path；同一 Knowledge 在多个后代路径命中时聚合 identity、保留 paths，不写入祖先 Topic。
51. **Source Attachment 与正文索引是两层开关。** attached Source title 可以在 Group / Topic 范围定位；Source body 只有 source expansion 允许且 index coverage 可用时进入结果，Evidence Binding 不能代替 Attachment 推断范围。
52. **Group root 与 Unplaced 不混淆。** Group root Placement 在 Group Search 内合法命中并显示`直接放在这个知识群`；只有全 Space active Placement count = 0 才显示`未归入知识群`。
53. **Question 按 Knowledge identity 聚合。** current / historical question wording、current resolution、remaining unknowns 与 targets 都命中同一 Question result，不拆成 Answer、Criterion 或 Target 结果墙。
54. **Question 的状态筛选保持四轴。** `尚未回答 / 部分进展 / 暂时可用 / 已充分回答`、`正在 / 暂停 / 停止追问`与`依据有变化 / 需要复核`可分别组合，不压成 open / closed。
55. **运行时 Unknown 不污染普通 Search。** 它只在 Query History / Answer 专用搜索中随 owner 找回；用户保存后才以 Question Knowledge 进入 Library Search。

---

# 1. 当前规格中的十二个结构缺口

## 1.1 只定义了“对象分组”，没有定义搜索承诺

旧规格已经列出 Group、Topic、Node、Source 与 Saved Answer 等结果组，却没有回答：Search 到底保证“找对象”“找内容”“找位置”还是“找相关概念”。这些目标的排序、结果粒度和失败含义不同。

## 1.2 Search Result 可能按 chunk 重复污染对象身份

一个长 Node 可能有十处正文命中。如果直接展示十条向量检索结果，用户会看到十个看似不同的对象，无法理解它们实际上属于同一 Node。

## 1.3 Scope 只有标签，没有执行合同

“当前 Group”是否包含 Topic descendants、跨群 Placement、Group Sources、Archived、Explicit Draft 或历史版本尚不清楚。仅显示一个 Scope chip 会制造虚假透明度。

## 1.4 Exact 与 Semantic 的关系没有冻结

如果语义结果覆盖了标题或原句匹配，用户连自己明确记得名称的内容都找不到；如果完全没有语义能力，用户又只能猜系统里保存时的措辞。

## 1.5 Ranking 可能把最近编辑误当最相关

近期性有助于找回工作中内容，但不能压过精确名称、适用条件或正文原句，更不能被理解为知识更新或正确性。

## 1.6 无结果没有覆盖解释

当前 Group 无结果、全局有结果、Source 尚未解析、OCR 失败、历史版本被排除、Trash 中存在和真正无匹配，都可能被写成同一个空状态。

## 1.7 同名对象与多位置对象没有明确展示语义

同名对象不能自动合并；同一对象的多个 Placements 也不能重复显示。若这两条没有同时成立，搜索会破坏整个 identity model。

## 1.8 搜索打开对象后可能丢失精确上下文

只打开 Node 顶部无法证明深层内容找回成立。用户必须看到命中的 Anchor、所在章节、当前 Placement，并能回到原结果位置。

## 1.9 Search、页内查找、链接选择器和命令面板混在一个入口

它们可能共享键盘入口，却不能共享结果资格和动作后果。尤其命令执行与知识打开不能用相同的默认 Enter 语义模糊处理。

## 1.10 搜索历史与 Saved Search 的对象性质不清楚

Recent Query 是临时便利，Saved Search 是动态 View，冻结结果是 Snapshot。三者若共用“保存搜索”一个动作，会造成结果成员、历史和知识对象混乱。

## 1.11 AI 不可用时的搜索降级未定义

如果 Search 的默认体验依赖 embedding 或模型解释，离线本地知识库反而失去最基本的定位能力，这与产品本质冲突。

## 1.12 搜索转 Ask / Explore 的信息传递未定义

把 snippets 直接塞进 Ask 会丢失身份、revision 与 applicability；把共现结果送进 Graph 又可能制造并不存在的 Relation。

---

# 2. 产品目标与非目标

## 2.1 产品目标

搜索系统必须同时做到：

1. 用户记得名称、原句、含义、位置或来源中的任意一种线索时，都有可靠找回路径；
2. 结果始终围绕稳定对象 identity，而不是技术 chunk；
3. 用户在提交前知道搜索范围，结果后知道实际覆盖；
4. 精确命中优先，语义召回补充，而且两者可区分；
5. 同名、多位置、旧名称、历史版本和不同 Applicability 不造成错误合并；
6. 点击结果能直达命中 Anchor，并无损返回原结果状态；
7. 无结果能区分真正未命中、范围过窄、索引不完整和内容不可解析；
8. AI、网络或语义索引不可用时，核心找回能力仍成立；
9. Search 可以自然转到 Ask、Explore、Link 与 Author，但不替这些模式执行后果；
10. 动态 Saved Search 成为组织视图，而不是第二套 Group 或静态收藏夹。

## 2.2 非目标

- 不做通用 Web 搜索引擎；
- 不把 Query 写成知识或自动创建 Note；
- 不以一个万能输入框隐藏多个产品承诺；
- 不为展示 AI 能力而牺牲精确标题、原句和位置查找；
- 不把搜索排名解释为知识质量排名；
- 不把相似结果、共同关键词或用户点击自动升级为 Relation；
- 不要求普通用户学习布尔表达式才能成功；
- 不公开内部 embedding 分数、模型 chain-of-thought 或无法行动的 debug 噪声；
- 不因本合同增加新的一级导航或顶层知识对象；
- 不在产品定义阶段开始 UI 原型。

---

# 3. 六种找回承诺与六类搜索表面

## 3.1 Search、Browse、Ask、Explore、Find、Filter

| 能力 | 用户心智 | 输入 | 默认输出 | 是否综合 | 是否改变知识 |
|---|---|---|---|---:|---:|
| Search / 搜索 | “我记得这里有某样东西” | 名称、原句、含义、属性 | 对象结果 + 命中位置 | 否 | 否 |
| Browse / 浏览 | “我想从结构里看有什么” | Group / Topic / View | 稳定层级与成员 | 否 | 否 |
| Ask / 提问 | “基于这些知识，答案是什么” | 问题 + Context | Claims + Support + Unknown | 是 | 否 |
| Explore / 探索 | “它和什么有关，怎样连过去” | 对象 / Relation / Path | 真实邻接与解释 | 可有短说明 | 否 |
| Find / 页内查找 | “这一个对象里哪里写了” | 字词 / 短语 | 当前对象内的位置 | 否 | 否 |
| Filter / 筛选 | “已知集合里只看符合条件的” | 状态 / 属性 / 日期等 | 当前集合子集 | 否 | 否 |

关键原则：

- Browse 无查询也可以成立；
- Filter 不负责跨边界召回；
- Search 可以从词面或语义找到未知位置；
- Ask 需要生成新表达，因此承担 grounding 合同；
- Explore 只能呈现结构、正式关系和明确的临时推荐层；
- Find 不离开当前对象边界。

## 3.2 六类 Search 表面

| 表面 | 默认 Scope | 合法结果 | 默认主动作 | 特殊边界 |
|---|---|---|---|---|
| Global Search | All Knowledge | 所有允许对象组 | 打开结果 | 不搜索 Commands |
| Scoped Search | 当前 Group / Topic / Node | Scope 内对象 | 打开结果 | 不静默扩大 |
| Find in Object | 当前可读 revision | Anchors / text ranges | 跳到位置 | 不进入其他对象 |
| Link / Relation Picker | 当前编辑动作允许的 target type | 合法 target identities | 选择目标 | 提交后才建链接 / 边 |
| Command Palette | 当前状态可执行动作 | Commands | 执行动作 / 打开流程 | 与知识结果分区 |
| Saved Search View | 保存的动态 criteria | 当前求值对象 | 打开 / 批量查看 | 不保存静态成员 |

## 3.3 共享入口不等于共享语义

产品可以使用统一快捷键打开搜索入口，但必须满足：

1. 知识结果与 Commands 有稳定分区和类型标签；
2. 当前模式在输入前可见，例如“搜索全部知识”“在本页查找”“选择要关联的知识”；
3. Enter 的后果可预测：打开知识、跳到位置、选择目标或执行命令不会混淆；
4. 切换模式保留原始查询，但创建新 Search Request / Run；
5. 用户可以完全关闭 Command results，只搜索知识；
6. 无论入口长得多简洁，Scope、状态和覆盖不能被省略。

---

# 4. 运行时对象模型

以下对象用于可解释执行、恢复与历史，不增加 Knowledge ontology 的顶层对象。

## 4.1 Search Session

```text
SearchSession
  session_id
  entry_surface
  entry_selection_snapshot
  created_at
  last_active_at
  run_refs[]
  active_run_ref
  return_stack_snapshot
  retention: active | recent | cleared
```

Search Session 负责一次连续找回过程。它可以包含多次改词、切 Scope、加过滤、打开结果和返回，但不会进入 Library 或 Graph。

## 4.2 Search Request

```text
SearchRequest
  request_id
  session_id
  raw_query
  normalized_query
  interpretation_summary
  mode: best_match | exact_words | similar_meaning
  surface: global | scoped | find | picker | command | saved_view
  scope_spec
  filter_spec
  sort_spec
  created_at
```

Search Request 表示用户和界面提交的不可变意图。任何 Query、Scope、Mode、Filter 或 Sort 的改变都创建新 Request，不原地改写旧请求。

## 4.3 Search Run

```text
SearchRun
  run_id
  request_id
  started_at
  completed_at
  execution_mode: local | local_plus_semantic | degraded
  index_snapshot_refs
  coverage_snapshot
  exclusions[]
  result_set_ref
  state: queued | searching | partial | complete | failed | cancelled
  successor_run_ref
```

Run 记录一次实际执行。它回答：当时使用了哪个索引、哪些内容被排除、覆盖是否完整，以及结果为何与以后不同。

## 4.4 Search Result Set

```text
SearchResultSet
  result_set_id
  run_id
  ordered_hit_refs[]
  group_counts
  total_estimate
  truncated_state
  generated_at
  freshness_state: current | stale | refresh_available
  selection_state
  scroll_state
```

Result Set 是运行时快照。它不保存为知识，也不因打开某条结果就改变排序。当前知识或索引变化后，显示 `refresh_available`，由用户或清晰规则创建 successor Run。

## 4.5 Search Hit

```text
SearchHit
  hit_id
  target_identity_ref
  target_object_type
  matched_revision_ref
  matched_anchor_ref
  matched_range
  display_placement_ref
  alternate_placement_refs[]
  matched_fields[]
  match_reasons[]
  applicability_summary
  object_state
  index_state
  snippet_snapshot
```

Hit 的 identity 是目标对象，不是 snippet。`matched_anchor_ref` 允许打开深层位置；`display_placement_ref` 允许恢复用户能理解的结构上下文。

## 4.6 Saved Search 不新增对象

```text
View
  view_type: saved_search
  name
  query_template
  scope_spec
  filter_spec
  sort_spec
  presentation_spec
  created_at
  updated_at
```

View 保存条件，不保存 `member_ids[]`。每次打开时形成新的 Search Request / Run / Result Set。

## 4.7 不进入长期本体的对象

以下内容均不是 Node、Source、Relation 或 Knowledge Snapshot：

- raw query；
- interpreted query；
- Search Session；
- Search Run；
- Search Hit；
- result ranking；
- highlight；
- suggested scope expansion；
- semantic similarity；
- recent search。

---

# 5. Scope、Expansion 与状态过滤

## 5.1 Scope Spec

```text
SearchScopeSpec
  anchor_type: space | group | topic | node | source_registry | saved_answers | trash
  anchor_ref
  include_descendants: true | false
  placement_policy: anchor_placements | all_object_placements
  relation_expansion: none | formal_neighbors
  source_expansion: none | attached | all_sources
  revision_policy: current | current_plus_historical
```

Scope 必须分解，而不是只显示“当前 Group”四个字。普通界面可用一句人话总结，例如：

> 搜索“法国租房”内的当前知识与未完成修改；包含所有主题，不包含关系邻居、来源原文、历史版本和已归档内容。

## 5.2 默认 Scope

| 入口位置 | 默认 Anchor | 默认 descendants | 默认 sources | 默认 relations |
|---|---|---:|---:|---:|
| Home / Global bar | Space | 是 | 对象组可搜，正文需开 Source 组 | 否 |
| Group Overview | Current Group | 是 | Attached Source titles；正文按组开关 | 否 |
| Topic | Current Topic | 是 | Attached Source titles；正文按组开关 | 否 |
| Node | Current Node | 当前对象 | Node evidence refs 可见 | 否 |
| Source Reader | Current Source | 当前来源 | 当前 Source full text | 否 |
| Trash | Trash | 是 | Trash 内对象 | 否 |

用户可显式切到 All Knowledge。Scoped Search 不因低结果数自动扩大。

### Direct、descendant 与 Source attachment 的执行规则

- `只看这里`：Topic 的 direct Placements + direct Source Attachment titles；
- `包含子主题`：递归读取 descendants，Knowledge 以 identity 聚合并保留所有命中 paths，Sources 保留 exact attachment paths；
- `整个知识群`：包括 Group root Placements、全部 Topic descendants 与 Group / Topic Source Attachment titles；
- Source body 只有 `source_expansion` 明确包含且 Coverage 可说明时检索；
- Boundary text 可作为 Group identity metadata 命中，但 Boundary 不是成员筛选器；
- View criteria、Ask overlay 与 current Focus 都不能静默修改 Search Scope。

## 5.3 状态进入矩阵

| 对象状态 | 普通 Search 默认 | 可显式包含 | Ask 默认 | 结果表达 |
|---|---:|---:|---:|---|
| Current Knowledge / maintained current Relation | 是 | 是 | 是 | 无需额外噪声 |
| Explicit Draft | 仅 Draft scope | 是，标明草稿 | 否 | `草稿，不用于默认回答` |
| Recovery Checkpoint | 否 | 否 | 否 | 只从异常恢复入口出现 |
| Open RelationChallenge | 是 | 是 | 可含但对重叠范围标明 | `存在未解决的反例` |
| Relation review_due | 是 | 是 | 是但标明具体影响 | `有变化需要检查` |
| Ended Relation | 否 | 是 | as-of / history 时 | `已结束` + time / scope |
| Superseded Relation | 否 | 是 | 默认沿 successor | `已被替代` + successor |
| Retracted Relation | 否 | 是 | 否 | `已撤回` + reason |
| Archived | 否 | 是 | 否 | `已归档` |
| RelationCandidate | 否 | Suggested scope | 否 | `系统建议，不是当前关系` |
| Question：正在追问 | 是 | 是 | 可作为问题与 Context，不作为自身答案 | `正在追问` + resolution phrase |
| Question：暂停追问 | 是 | 是 | 仅显式或当前 Scope | `暂停追问` + 可选等待条件 |
| Question：已停止追问 | 默认否 | 是 | as-of / history 或显式时 | `已停止追问` + closure reason |
| Question：依据有变化 / 需要复核 | 是 | 是 | 可用但必须限定 | `依据有变化` / `需要复核`，不写自动失效 |
| Runtime Unknown / Gap Marker | 否 | owner-specific scope | 否 | 从 Query Run / Knowledge owner 进入，不作为顶级结果 |
| Historical Revision | 否 | 是 | as-of 时 | `历史版本 · 日期` |
| Trash | 仅 Trash | 仅 Trash | 否 | `废纸篓` |

Search 与 Ask 都默认使用 Current Revision。Search 可额外开启 Draft scope 帮助找回显式草稿；Ask 只有用户明确选择时才包含 Draft。Recovery 与 Buffer 对两者都不可见。

## 5.4 对象类型过滤

支持的人话过滤至少包括：

- 知识群；
- 主题；
- 知识；
- 概览；
- 来源；
- 保存的回答；
- 路径与视图；
- 关系说明；
- 问题知识；
- 未完成修改 / 已归档 / 历史版本。

选择`问题知识`后，P1 可组合筛选：

- 尚未回答 / 已有部分进展 / 暂时可用 / 已充分回答；
- 正在追问 / 暂停追问 / 已停止追问；
- 依据有变化 / 需要复核；
- 指向当前 Group / Topic / Knowledge / Source / Conflict / Decision；
- 有 required Subquestions / 有 remaining unknowns。

Search result 仍是一条 Question Knowledge。QuestionTargetReference、Criterion、Resolution Revision 与 Answer basis 只解释命中位置和 standing，不获得顶级结果 identity，也不进入 ordinary Relation type filters。

界面不得把内部 `Node`、`Projection`、`Snapshot` 当作普通用户必须理解的术语。专业层可检查 canonical type。

## 5.5 适用范围过滤

当 Knowledge Nodes 有明确 Applicability 时，Search 支持：

- 地区；
- 人群 / 身份；
- 组织；
- 时间区间 / as-of；
- 情境；
- 产品或版本。

Applicability 不匹配的精确结果可以出现，但必须说明“不适用于当前条件”，不得通过隐藏降权让用户误以为不存在。

若同一查询同时命中一般规则、历史规则与当前特定人群规则，结果先按 standing 分组，再显示 effective / ended time、主体条件和限定关系。排序相关度不能覆盖 currentness；“2025 年一般规则”可以作为历史依据或背景出现，但不能在 2026 年特定情境中以无日期摘要替代当前限定规则。Search 仍只定位对象，不替用户完成个体资格判断。

## 5.6 结构化属性过滤

Property Search 只使用稳定 `property_id`、Definition aliases、typed operators 与明确的 value state。默认评估 Accepted Assertions；Working / Proposed values 可以作为单独层找回，但不能与 current knowledge 混成同一命中原因。

支持：

- known exact / range / contains / Node reference；
- property exists；
- 未填写 `unset`；
- `unknown`；
- `no_value`；
- `not_applicable`；
- qualifier / valid time / origin / Evidence presence 的高级条件。

否定条件遵守多值语义：`状态不是 active` 只返回已知且不等于 active 的 Assertions，不暗中纳入未填写、未知、无或不适用。Property 的 ordinary range / equality 与 Applicability overlap 使用不同解释器，即使两者在界面都显示为 filter chip。

Definition rename 通过 stable ID 和 aliases 继续命中；type / option migration 时 Coverage 显示 compatible、needs review、legacy 与尚未重建索引范围。Source frontmatter / tags 只在 Source group 命中；没有经过 Mapping 的 raw metadata 不冒充 Node Property。

## 5.7 范围内无结果、全局有结果

正确行为：

1. 当前结果区保持为空；
2. 明确显示搜索覆盖和过滤；
3. 独立提示“在全部知识中找到 3 个可能结果”；
4. 用户触发后创建新的 Global Search Request / Run；
5. 返回时仍能恢复原 Scoped Search；
6. 不把全局结果计入原 Result Set。

---

# 6. Query Interpretation 与语言合同

## 6.1 三种模式

| 模式 | 用户意图 | 核心行为 | 不做什么 |
|---|---|---|---|
| Best Match | “尽快找到我想的东西” | Exact + full-text + alias + semantic，按忠实度融合 | 不让 semantic 压过 exact |
| Exact Words | “这里真的写了这些词” | 精确词、短语、字段和全文定位 | 不扩同义词 |
| Similar Meaning | “措辞可能不同，但意思接近” | 概念召回并标明语义理由 | 不宣称 Relation 或事实等价 |

默认 Best Match。模式切换可回退、可检查，不清空原 Query。

## 6.2 普通语言优先，操作符渐进披露

用户可直接输入：

- `法国租房担保`；
- `那篇说“连带担保”的来源`；
- `我去年写的学生住房草稿`；
- `在这个知识群里找关于押金的内容`；
- `只看巴黎、2026 年仍适用的知识`。

系统先呈现解释摘要：

> 搜索词：押金；范围：当前知识群；地区：巴黎；适用时间：2026；对象：当前知识与未完成修改。

高级用户再使用精确操作符，例如：

```text
"连带担保" group:"法国租房" type:source -status:archived
deposit applies:paris asof:2026 type:knowledge
```

操作符错误不应直接得到空结果；系统标出无法解释部分并提供修正。

## 6.3 查询语义

至少支持：

| 语义 | 示例 | 解释 |
|---|---|---|
| 精确短语 | `"连带担保"` | 连续或语言合理等价的精确片段 |
| 必须包含 | `+garantie` | 必须出现 |
| 排除 | `-assurance` | 排除对象或片段 |
| 任一词 | `Visale OR Garantme` | 任一条件 |
| 对象类型 | `type:source` | 仅某类对象 |
| 路径 / Group | `group:"法国租房"` | 指定结构范围 |
| 编辑状态 | `status:draft` | 指定存在 Explicit Draft；不是 object lifecycle |
| 适用条件 | `applies:student` | 指定 subject / location / condition / valid time overlap |
| 结构化属性 | `property:"办理状态"=进行中` | 按 stable Definition / option identity 解析 typed value |
| 值状态 | `property:"入住日期"=unknown` | 明确未知，不等于未填写 / 无 / 不适用 |
| 日期 | `updated:2026-07` | 指定时间范围 |
| 当前 / 历史 | `revision:historical` | 包含历史版本 |

普通用户不需要记住这些语法；筛选器和自然语言解释与操作符保持双向同步。

## 6.4 多语言、别名和转写

系统至少处理：

1. 中英文及混合文本，不依赖空格分词；
2. 大小写、全半角、常见标点和数字格式规范化；
3. 重音字符可宽松召回，例如 `cafe` 找到 `café`，但 Exact Phrase 仍可区分；
4. 用户定义 Alias 优先于系统猜测同义词；
5. 缩写与全称的已确认映射，例如 `CAF` ↔ `Caisse d'allocations familiales`；
6. 音译 / 转写作为可解释扩展，例如 `维萨莱` ↔ `Visale`；
7. 原始语言与翻译文本分开，翻译命中必须标明；
8. 拼写纠正只做建议，不能静默改变精确查询。

## 6.5 原始查询与解释查询

产品必须同时保留：

```text
raw_query: "去年那个巴黎担保的东西"
normalized_query: "巴黎 担保"
resolved_time: 2025-01-01..2025-12-31
resolved_scope: current Group
candidate_aliases: ["garantie", "Visale"]
unresolved_term: "那个"
```

如果代词无法由当前 Selection 可靠消解，系统不假装理解。可以显示候选 Scope 或要求用户选一个对象，而不是自动扩大到全部知识。

## 6.6 搜索不暴露内部推理

解释的目标是让用户判断结果，不是展示模型思维过程。只显示：

- 系统理解了哪些条件；
- 哪些词被规范化；
- 使用了哪些 Alias / 转写；
- 哪些条件未识别；
- 结果为什么匹配；
- 搜索覆盖有什么限制。

---

# 7. Retrieval、Index 与 Coverage

## 7.1 检索层次

Best Match 可以组合以下层次，但产品顺序不等于具体算法实现：

1. canonical title exact；
2. confirmed alias / redirect exact；
3. exact phrase in title / definition / content；
4. all-term lexical match；
5. field / property match；
6. language-aware full-text match；
7. verified abbreviation / transliteration match；
8. semantic similarity；
9. context tie-break；
10. recency tie-break。

产品只冻结结果承诺和解释，不冻结 BM25、向量模型、reranker 或数据库选型。

## 7.2 Canonical Store 与 Index 分离

```text
Canonical Knowledge Store
  identities
  revisions
  placements
  relations
  sources
  snapshots

Search Indexes
  identity/title index
  full-text index
  property definition / accepted assertion index
  applicability overlap index
  anchor index
  source/OCR index
  semantic index
```

不变量：

- 删除 Index 不删除 canonical content；
- Rebuild 可由 canonical data 完成；
- Index snapshot 有版本和覆盖状态；
- 内容已保存但尚未索引时，用户能看到 pending 状态；
- Semantic index 可选或不可用，不影响 exact / full-text 基线；
- 搜索结果指回 canonical identity，而不是 index document identity。
- Property Index 只保存可由 Definitions / Assertions 重建的检索表示；删除或重建它不改变 value states、qualifiers、Applicability 或 Schema History。

## 7.3 Coverage Snapshot

```text
SearchCoverage
  canonical_objects: complete | partial | unavailable
  current_revisions: complete | partial | unavailable
  historical_revisions: included | excluded | partial
  source_metadata: complete | partial | unavailable
  source_full_text: complete | partial | unavailable
  ocr_transcription: complete | partial | unsupported | unavailable
  semantic_index: available | stale | unavailable | disabled
  exclusions[]
  last_indexed_at
```

普通界面用一句话表达：

> 当前知识和未完成修改已完整搜索；12 个来源中有 2 个尚未解析，历史版本未包含，语义匹配当前不可用。

## 7.4 Index 生命周期

| 状态 | 用户仍可做什么 | 搜索行为 | 必须显示 |
|---|---|---|---|
| Current | 全部 | 正常 | 无额外噪声 |
| Updating | 浏览、编辑、精确查已索引内容 | 旧快照 + 新增对象直查 | `正在更新索引` |
| Partial | 全部非 AI 核心能力 | 对已覆盖部分返回结果 | 覆盖缺口 |
| Stale | 全部 | 返回旧索引结果 | `结果可能未包含最新修改` |
| Rebuilding | 浏览、编辑、标题 / identity fallback | 渐进恢复 | 进度与不丢数据说明 |
| Corrupt | canonical content 仍可读 | 降级 identity / direct scan | 修复入口，不说内容丢失 |
| Offline | 本地全部 | local exact / full-text | semantic / remote source 限制 |

## 7.5 Source 与媒体覆盖

Source 搜索至少区分：

- metadata 已索引；
- extracted text 已索引；
- PDF text layer 可用；
- OCR 完成 / 低置信 / 失败；
- audio transcription 完成 / 低置信 / 不支持；
- remote link 只有 title / snapshot / full content 哪一种；
- source disconnected 但历史 snapshot 仍存在；
- encrypted / unsupported / password-protected 无法索引。

在低置信 OCR 中命中时写明 `来自可能有误的 OCR 文本`；无结果时写明这部分覆盖不足。

## 7.6 新保存内容的 read-your-write

用户刚创建或修改的对象必须立即可通过 title / identity / direct content fallback 找到，即使完整索引尚未更新。系统不能让用户保存成功后几分钟内搜不到自己的内容。

## 7.7 隐私与本地优先边界

本产品是本地个人知识库，核心 exact / full-text / property index 在本地成立。若 Similar Meaning 使用本地模型则直接执行；若需要云端能力，必须由设置和运行状态明确约束，并在不可用时无损降级。这里不要求复杂的企业权限模型，但不能把本地内容在用户不知情时发送到外部服务。

---

# 8. Result Identity、聚合与消歧

## 8.1 对象 identity 是第一结果单位

结果聚合顺序：

```text
matched ranges
  → anchors
    → revision
      → target object identity
        → display placement
```

因此，一个 Node 正文有 7 个命中，默认仍是一条 Node result，内部显示“7 处命中”并展开前 2–3 个高价值 Anchors。

## 8.2 各对象的命中单位

| 对象 | Search Result identity | 内部命中位置 | 打开目标 |
|---|---|---|---|
| Group | Group | Overview / definition / property | Group Overview + Anchor |
| Topic | Topic | Topic Overview / structure label | Topic + Anchor |
| Node | Node | Block / Section / Claim anchor | Node + Anchor + Placement |
| Overview | 所属 Scope 的 canonical Overview | Projection / authored block | Overview + Anchor |
| Source | Source | page / paragraph / timestamp | Source Reader + locator |
| Saved Answer | Knowledge Snapshot | Answer Claim / text range | Snapshot + Claim anchor |
| Saved Path | Saved Path | step label / description | Path + Step |
| View | View | name / criteria | View definition / evaluated results |

Source fragment、Block、Answer Claim 和 Path Step 可以作为 locator，但不自动成为顶层对象。

## 8.3 多位置对象

一个 Node 同时出现在“法国租房 / 担保”和“学生生活 / 行政手续”时：

- 只显示一个 Node identity；
- 若从 Scoped Search 进入，优先显示该 Scope 内 Placement；
- 若 Global Search，按 query / current context 选择最相关 Placement；
- 显示 `另有 1 个位置`；
- 展开可看到所有 active Placements；
- 打开默认 Placement 后可切换位置，但正文 identity 不变；
- Placement 变化不改变该结果的匹配内容。

## 8.4 同名不同对象

同名结果必须展示足够 disambiguation：

```text
押金
法国租房 · 住宅租赁 · 适用于法国 · 当前知识

押金
产品定价 · SaaS 合同 · 适用于企业客户 · 尚未采用
```

不得：

- 只用小号灰字显示两条完全相同标题；
- 自动合并；
- 用近期性隐藏另一个；
- 让用户必须逐个打开才知道差异。

## 8.5 Rename、Alias、Redirect

| 情况 | Search 行为 | 结果文案 |
|---|---|---|
| 当前标题命中 | 打开当前 identity | `标题匹配` |
| 用户 Alias 命中 | 打开当前 identity | `通过别名“…”找到` |
| 历史标题命中 | 打开当前 identity | `曾用名“…”` |
| Merge Redirect | 打开 survivor identity | `“旧对象”已并入此知识` |
| Split Redirect | 显示 2+ successor 候选 | `原知识已拆分，请选择` |
| Redirect ambiguous | 不自动跳转 | 显示可修复候选 |
| Target in Trash | 普通 Search 不显示 | Trash 内可查 |
| Permanently deleted | 不返回幽灵结果 | Recent history 标明不可用 |

## 8.6 当前与历史 Revision

默认只聚合当前 Revision。开启历史版本后：

- 同一对象仍按 identity 分组；
- 当前命中和历史命中分开；
- 历史命中显示日期、revision status 和 successor；
- 点击进入历史阅读态，不把旧文本伪装成当前内容；
- 如当前版本也有匹配，默认先打开当前；
- 搜索历史版本不改变当前知识状态。

## 8.7 Source 与 Accepted Node 同时命中

同一短语既在 Source 原文又在用户接受的 Node 中出现时，两者都可以返回，但分组和知识角色清楚：

- `你的知识`：当前采用的 Node；
- `来源`：原文出现的位置；
- 可能还有 `保存的回答`：历史综合；
- 不能因 Source 更长、词频更高就淹没 Node；
- 不能因 Node 已接受就隐藏原文；
- 打开 Source 不等于接受其内容。

---

# 9. Ranking 与可解释匹配

## 9.1 排序目标

Ranking 的目标不是预测用户最可能点击什么，而是在最少结果中优先放出最可能是用户想找的对象，同时不隐藏同名、状态、Applicability 与 Coverage 风险。

优先序：

```text
Match Fidelity
  > Identity / Type Intent
    > Scope / Applicability / Object State
      > Current Context
        > Recency tie-break
```

## 9.2 Match Fidelity

建议产品等级，而不是公开分数：

| 等级 | 典型原因 | 排序承诺 |
|---|---|---|
| F1 Direct Identity | canonical title、唯一标识、confirmed alias exact | 优先出现 |
| F2 Exact Content | 精确短语、完整字段、原句 | 高于语义结果 |
| F3 Strong Lexical | 全部关键词、语言感知全文 | 稳定召回 |
| F4 Structured | property、tag、Applicability、path | 与意图一致时提升 |
| F5 Similar Meaning | 概念相近、措辞不同 | 明确标识，不覆盖 F1–F3 |
| F6 Contextual | 当前 Selection / recent object 相关 | 只用于 tie-break |

不向用户显示 `0.873 relevance`。原因是该数字既不是概率，也不是知识可信度，还会诱导用户把索引内部值误解为“正确率”。

## 9.3 Identity / Type Intent

查询包含明显对象意图时，类型要参与排序：

- “那篇来源”优先 Source；
- “我的回答”优先 Saved Answer；
- “哪个知识群”优先 Group；
- “那条知识”优先 Node；
- “我保存的路线”优先 Saved Path；
- 纯标题词不擅自推断类型。

系统无法确定时按对象组呈现，不把单一类型推到所有结果前。

## 9.4 Scope 与 Applicability

在 Scope 内的匹配优先于 Scope 外建议，但 Scoped Search 根本不混入 Scope 外结果。Global Search 中：

- 当前 Applicability 匹配者优先；
- 条件未知者可出现并标明；
- 条件不匹配者不必隐藏，尤其在 exact match 时；
- Working / Archived 等状态按用户过滤决定进入，不通过无限降权做不可见排除；
- Contested / Stale 是判断信息，不是简单降权。

## 9.5 当前上下文

当前 Group、打开的 Node 和最近 Selection 可以帮助打破相似结果之间的平局，但：

1. 不改变明确 Scope；
2. 不让相关但不匹配对象压过 exact result；
3. 不将打开频率写成权威性；
4. 不因用户之前点击错误结果就形成长期 filter bubble；
5. 可从“为什么出现”中检查其影响。

## 9.6 Recentness

近期性只在以下条件同时成立时使用：

- 匹配忠实度相近；
- 对象状态与 Applicability 相近；
- 没有 canonical identity / alias 的确定信号；
- 用户未选择其他 Sort。

当用户显式按更新时间排序，页面标题要写 `按更新时间`，不再冒充 `最佳匹配`。

## 9.7 稳定性与刷新

一次完整 Search Run 形成稳定排序。期间：

- 新增或修改内容不静默插入当前列表；
- 顶部显示 `知识有更新，刷新结果`；
- 打开结果再返回时恢复同一 Result Set；
- 用户刷新后创建 successor Run；
- Diff 可说明新增、消失和位置变化；
- 只有当前结果目标被删除时，原位显示 unavailable，不把后续项突然顶上来并丢失 Selection。

## 9.8 匹配原因

每个主要结果至少一个可解释原因：

- `标题完全匹配`；
- `通过别名“住房担保”找到`；
- `正文包含原句`；
- `7 处包含全部关键词`；
- `适用于：法国 · 学生 · 2026`；
- `来源标题与正文匹配`；
- `与你搜索的含义相近`；
- `当前知识群中的相关知识`；
- `历史版本包含该内容`；
- `来自可能有误的 OCR 文本`。

原因可以组合，但默认最多显示 1–2 个决定性理由，完整信息渐进展开。

## 9.9 用户反馈不直接改写知识

“这不是我要找的”可以改进本地 ranking 或 Alias 建议，但不能：

- 删除对象；
- 修改 Relation；
- 把对象标为错误；
- 自动 Merge 同名对象；
- 让该对象从所有未来查询永久消失。

如果反馈暗示 Alias 或 identity 问题，生成可检查建议，进入相应编辑流程。

---

# 10. Result Anatomy、打开与返回

## 10.1 一条结果的最小信息合同

```text
[人话对象类型]  标题
一句 orientation / definition 或命中片段
匹配高亮与附近上下文
Group / Topic / Section 路径 · Placement
状态 / Applicability / 来源日期（仅相关时）
匹配原因 · 命中数量 · 索引限制（如有）
```

默认信息必须帮助用户在打开前回答：

1. 这是什么；
2. 为什么匹配；
3. 它在哪里；
4. 是否适用于我；
5. 是当前知识、未完成修改、来源还是历史回答；
6. 打开会去哪里。

## 10.2 Orientation 与 Snippet

Snippet 不是随机截取的向量 chunk。优先级：

1. 对象已有的一句 definition / orientation；
2. 命中 Anchor 所在完整句或短段；
3. 必要的父标题；
4. 高亮 query terms；
5. 不超过可扫描的长度；
6. 不把两个不相邻片段拼成一个看似连续的句子。

若语义命中没有词面高亮，写 `含义相近` 并显示真正内容，不能伪造 query words 出现在原文中。

## 10.3 分组顺序

默认以知识角色分组：

1. `你的知识`：Group、Topic、Node、Overview；
2. `来源`：Source；
3. `保存的回答与路径`：Knowledge Snapshot、Saved Path；
4. `视图`：Saved Search 等 View；
5. `已归档 / 历史版本`：只有开启时；
6. `Commands`：只在 command-capable 入口单独分区。

组顺序可以根据明确 type intent 调整，但对象角色标签不可消失。

## 10.4 多 Anchor 命中

一个对象内有多处命中时：

- 主卡显示最能区分意图的一处；
- 显示 `共 7 处`；
- 展开后按文档顺序或 match fidelity 显示；
- 每个 Anchor 有父 section 和片段；
- 选择不同 Anchor 不创建新 object result；
- 返回结果时保留 Anchor 展开与选中状态。

## 10.5 打开目标

打开时传递：

```text
target_identity
matched_revision
matched_anchor
display_placement
origin_search_session
origin_result_set
origin_hit
```

目标页面必须：

- 进入正确 revision；
- 恢复正确 Placement / DepthTrail；
- 滚动到 Anchor；
- 使用短暂且可访问的定位强调；
- 不把高亮写入内容；
- Anchor redirected 时说明新位置；
- Anchor ambiguous / orphaned 时提供附近上下文和修复入口。

## 10.6 Back、Up 与 Return Stack

| 动作 | 去向 | 必须恢复 |
|---|---|---|
| Back to Search | 原 Search Result Set | Query、filters、排序、滚动、Selection |
| Up | 当前 Placement 的父结构 | Group / Topic / Section context |
| Other Placement | 同一 identity 的另一位置 | 正文 identity 不变 |
| Open Evidence | Source locator | Return to Node Anchor |
| Explore Relations | Local Graph / Inspector | Return to Search Hit |
| Ask with Selection | Ask workspace | Return to selected results |

Back 不是重新执行当前 Query；只有 Refresh 才创建新 Run。

## 10.7 高亮生命周期

- Search highlight 是临时 overlay；
- 默认进入后保留到用户开始编辑、离开 Anchor 或手动清除；
- 屏幕阅读器读出 `匹配位置开始 / 结束` 或等价语义；
- 不能只用颜色；
- 200% zoom 不遮挡正文；
- Print / Export 不默认包含 UI highlight；
- Exact 和 Similar Meaning 使用不同文字标签，而非只用不同颜色。

## 10.8 结果动作

安全的默认动作：

- 打开；
- 在新阅读面板打开；
- 复制深链接；
- 查看其他位置；
- 查看关系；
- 选中后提问；
- 添加到现有 Saved Path；
- 查看来源。

需要转交正式流程的动作：

- Rename；
- Move / Add Placement；
- Merge；
- Create Relation；
- Archive / Trash；
- 把 Explicit Draft 设为当前知识；
- Promote Saved Answer Claim。

---

# 11. Ambiguity、Alias、Redirect 与身份修复

## 11.1 查询歧义的三种处理

| 歧义类型 | 示例 | 产品行为 |
|---|---|---|
| 可并列展示 | 两个名为“押金”的知识 | 展示完整消歧，不先提问 |
| 会改变 Scope | “这个项目”但当前有两个候选 | 先提供 Scope 候选 |
| 会改变模式 | 完整问题句 | 保持 Search，提供 Ask 建议 |

搜索应尽量返回可判断候选，不把每个歧义都变成阻断式问题；只有 Scope 或 target legality 无法确定时才要求选择。

## 11.2 Alias 来源

Alias 分为：

1. 用户明确添加；
2. Rename 后保留的历史标题；
3. Merge 后的 redirect name；
4. 用户确认的缩写 / 全称；
5. 导入时保留的外部标识；
6. 系统提出但尚未确认的候选 Alias。

前五类可以参与 direct identity match。第六类只能作为 Similar / suggestion，不能假装已确认映射。

## 11.3 Alias 冲突

同一 Alias 指向多个 identity 时：

- 不自动选择点击最多的对象；
- 展示冲突对象及其定义 / Group / Applicability；
- 当前 Scope 可排序但不能隐藏冲突；
- 提供 `修复别名`；
- 修复是 identity edit，支持撤销与影响预览；
- 历史 Search Runs 保留当时解析结果。

## 11.4 Redirect 不是 Relation

Redirect 表示 identity lineage，不是概念关系：

- Rename redirect：旧名称 → 同一 identity；
- Merge redirect：retired identities → survivor；
- Split redirect：旧 identity → 多个 successors；
- Move / Placement change 不需要 identity redirect；
- Redirect 不显示在普通 Graph relation layer；
- forensic 层可以检查 lineage。

## 11.5 搜索触发修复建议

搜索可以发现但不能静默修复：

- 两个高度相似对象可能重复；
- Alias 冲突；
- Anchor orphaned；
- Redirect ambiguous；
- 同名对象缺少 definition；
- Source 与 Node identity 对应不清。

建议进入 Review / Editor，搜索结果本身仍保持当前 truth。

## 11.6 已删除与不可用对象

Recent Search 或 Saved Path 指向不可用 target 时：

- Trash 中：显示 `已移到废纸篓`，可在 Trash 中打开；
- 永久删除：显示不可恢复状态，不返回 phantom content；
- Source disconnected：保留 metadata / snapshot 时可打开历史；
- 权限或路径不可用：显示具体不可用原因；
- successor 存在：提供 redirect；
- 不把另一个相似对象悄悄替换为原目标。

---

# 12. No Result、Partial Result 与失败语义

## 12.1 不是一个空状态，而是九类诊断

| 类别 | 真实含义 | 推荐主文案 | 主动作 |
|---|---|---|---|
| True no match | 已搜索覆盖内无匹配 | `在本次搜索范围内没有找到匹配` | 改词 / 创建知识 |
| Scope too narrow | 当前 Scope 无，全局可能有 | `当前知识群里没有找到` | 搜索全部知识 |
| Filters exclude | 过滤排除了候选 | `有结果被当前筛选隐藏` | 查看 / 清除筛选 |
| State excluded | Archived / Historical / Trash 被排除 | `已归档或历史内容未包含` | 显式包含 |
| Index partial | 部分对象未索引 | `结果不完整` | 查看覆盖 / 等待 / 重建 |
| Index stale | 最新变更未进入索引 | `可能未包含最新修改` | 刷新索引 |
| Source unparsed | 文件无法抽取 / 尚未完成 | `部分来源正文尚不可搜索` | 查看来源状态 |
| Semantic unavailable | 只有相似模式不可用 | `含义相近搜索暂不可用` | 使用精确搜索 |
| Execution failure | 本次 Run 失败 | `搜索没有完成` | 重试，保留请求 |

## 12.2 诚实否定句

禁止：

- `你的知识库里没有这条知识`；
- `这件事不存在`；
- `没有相关资料`；
- `AI 没找到，所以没有`；
- `0 个结果`作为唯一解释。

推荐：

> 在“法国租房”的当前知识与未完成修改中没有找到“连带担保”。本次未搜索来源正文、历史版本和已归档内容。

## 12.3 Query reformulation

系统可以提供有限、可解释的改写：

- 拼写候选；
- confirmed Alias；
- 去掉一个过窄 filter；
- Exact → Best Match；
- 当前 Scope → All Knowledge；
- 包含 Source full text；
- 包含 Archived / Historical。

每一个建议都说明将改变什么，并在用户触发后创建新 Request / Run。不能一次把所有限制都移除后宣称找到结果。

## 12.4 创建新知识的时机

真正 no match 时可以提供 `创建知识“…”`，但：

- 不把 Query 自动作为 Node title / content 保存；
- 进入 Author flow 并让用户确认类型、Group / Placement 与初始内容；
- question-looking query 可以创建 Question Node 或普通 Working Node，但由用户选择；
- 创建后可返回 Search Session；
- 新对象通过 read-your-write 立即可找到。

## 12.5 Partial Results

当部分 shard、Source 或 OCR 失败时，可以返回已有结果，但结果头必须：

1. 标记 `结果可能不完整`；
2. 说明未覆盖的类别 / 数量；
3. 不降低已有 Hit 的 identity 可靠性；
4. 不把无结果部分推断为不存在；
5. 支持在恢复后 Refresh；
6. 保留旧 Run 供比较。

## 12.6 Loading、Empty 与 Failure 分开

- Loading：仍在搜索，不能先闪烁空状态；
- Partial streaming：已有结果但尚未完成，排序可先冻结或明确渐进；
- Complete empty：覆盖完成且无命中；
- Complete with exclusions：有或无结果但覆盖受限；
- Failed：执行失败，保留 query / scope / filters；
- Cancelled：用户停止，已有结果不冒充 complete。

## 12.7 索引修复不伤害内容

`重建搜索索引`必须清楚说明：

> 这只重建用于查找的本地索引，不会删除知识、来源、关系、版本或保存的回答。重建期间仍可浏览和编辑。

索引修复失败时停止并保留旧索引；不能以清空 canonical store 作为“修复搜索”的隐藏后果。

---

# 13. Find in Current Object

## 13.1 范围

Find 只查：

- 当前打开对象；
- 当前可读 revision；
- 当前渲染与可按需展开的 authored content；
- 明确属于当前 Overview / Node / Source 的 Anchors。

默认不查：

- 当前 Group 的其他对象；
- backlinks；
- Relation neighbors；
- 其他 Placement；
- 历史 revisions；
- 嵌入对象的完整正文，除非用户进入该对象。

## 13.2 隐藏与折叠内容

| 内容类型 | Find 行为 |
|---|---|
| 折叠 section | 可命中，跳转时展开并标明 |
| 延迟加载 block | 可命中，加载后定位 |
| 当前对象的 footnote | 可命中，进入 footnote anchor |
| Pinned / Live 引用摘要 | 只查当前显示摘要；可跳到源对象继续查 |
| 嵌入 Source preview | 查当前 preview，不把整份 Source 算作当前页 |
| Hidden metadata | 默认不命中正文 Find；可在属性 Search 中找 |
| Historical diff | 只有进入历史阅读态才查该 revision |

## 13.3 Find Result

必须有：

- 当前命中 / 总命中数；
- Next / Previous；
- 区分大小写 / Exact Phrase 等必要选项；
- 当前 Anchor 的父 section；
- 无词面结果时不自动启动 semantic；
- 关闭后恢复正文焦点；
- 键盘与屏幕阅读器可用。

## 13.4 Replace 不属于 Find

Replace 是 Editor operation，必须遵守 edit scope：

- 单处替换；
- 当前 revision 全部替换；
- 对 Projection / Live 引用不可直接替换源内容；
- 高影响跨对象替换进入 Change Set；
- 不把 Search Results 当作批量替换作用域；
- 保存后产生正常 revision / undo。

## 13.5 Source Reader Find

在 Source 中：

- PDF 使用 page + text range；
- 音视频使用 timestamp + transcript range；
- OCR 命中标明不确定；
- 原文和翻译层分开；
- 命中定位可以创建 Evidence Fragment suggestion，但不会自动保存；
- 断连 Source 只在本地 snapshot 覆盖内查找。

---

# 14. Link Picker、Relation Target Picker 与 Command Palette

## 14.1 Picker 的资格约束

Picker 复用索引与匹配逻辑，但先应用 target contract：

```text
PickerContext
  edit_operation
  source_identity
  allowed_target_types[]
  forbidden_targets[]
  self_link_policy
  duplicate_edge_policy
  scope_hint
```

因此搜索命中 Block 时，结果仍返回其合法父 Node identity；如果该 Relation 只允许 Group ↔ Group，Node 结果根本不进入候选。

## 14.2 选择不等于提交

Picker 中选中对象只填入 Editor：

- Reference Link：确认显示文本 / anchor 后保存；
- Relation：确认 relation type、direction、scope / explanation 后提交；
- Add Placement：确认目标 Group / Topic 与位置后提交；
- Saved Path：确认 step position 后加入；
- Evidence：确认 Source locator 与 evidence role 后保存。

用户按 Esc 退出时不产生边、链接或 Placement。

## 14.3 Create New

未找到目标时可显式 `创建新知识`：

- 新对象 title 可预填 raw query；
- 必须进入 Author flow；
- 保存后返回 Picker 并选中新 identity；
- 最终 Relation / Link 仍需提交；
- 取消创建不产生幽灵 target；
- 若发现同名对象，先展示消歧而非强行复用。

## 14.4 Duplicate Relation

若目标之间已有 Relation：

- 显示现有 relation statement、type、direction、Applicability 与 disposition；
- 对 normalized type + direction + overlapping Applicability + 等价 statement 提出 duplicate Candidate，不自动创建或 merge edge；
- 若 statement、time 或 Applicability 真正不同，允许并列 Relation，不用 `related_to` 合并；
- 可以打开 Relation Inspector；
- 修改 type / explanation 是 relation edit；
- 搜索相似不算 existing relation。

## 14.5 Command Palette

Command 结果至少显示：

- 动作名称；
- 当前可用 / 不可用状态；
- 快捷键；
- 影响对象；
- 高影响动作的后续确认，而非在 Palette 里直接完成。

Command 排序以当前状态可执行性和名称匹配为主，不与知识 relevance 共用一个分数。

## 14.6 同一入口的分区规则

当入口同时允许 Search 和 Commands：

```text
Knowledge
  你的知识
  来源
  保存的回答与路径

Actions
  新建知识
  添加来源
  打开图谱
```

- Arrow keys 在分区中连续；
- 分区标题可被屏幕阅读器识别；
- destructive command 不因排第一且按一次 Enter 就执行；
- 用户可输入 `>` 或切换 Action mode，但不是必须；
- 最近执行 Commands 不压过 exact knowledge title。

---

# 15. Search 与 Ask、Explore、Author 的转换

## 15.1 Search → Ask

两条合法路径：

### A. 问题形态建议

用户输入“法国学生租房需要什么担保？”时：

1. Search 仍返回对象结果；
2. 提供 `用知识库回答这个问题`；
3. 显示将使用当前 Search Scope；
4. 用户触发后创建 Query Turn；
5. Ask 再按自己的 Context contract 解析，不把 Search Result Set 全部塞入。

### B. 选择结果后提问

用户勾选 2 个 Nodes 和 1 个 Source：

```text
Search selection
  target identities
  selected anchors
  selected revisions
  display placements

→ Query Requested Context
  explicit object refs
  explicit source ref
  anchor hints
```

Snippets 只用于界面预览，不是事实 Context。Ask 必须回到 canonical objects 与实际 revisions。

## 15.2 Ask → Search

AI unavailable、用户只想定位原文或回答 Coverage 不足时，可以 `改为搜索`：

- 保留原问题；
- 建议提取的关键词可见；
- Scope 沿用但不静默扩大；
- 创建 Search Request；
- Answer / Query Run 不被搜索结果覆盖；
- 找到对象后可返回 Ask。

## 15.3 Search → Explore

选择结果后可：

- 查看所属结构；
- 查看正式 Relations；
- 查看其他 Placements；
- 打开 Local Graph；
- 将多个明确对象作为临时 selection 对比。

必须保持：

- Search co-occurrence 不是 Relation；
- semantic similarity 是推荐 overlay；
- Atlas canonical layout 不因 Query 改变；
- 清除 overlay 后长期图谱恢复；
- Return Stack 回到原 Search Hit。

## 15.4 Search → Author

合法动作：

- 无结果后创建 Working Node；
- 打开已有 Explicit Draft 继续写；
- 对现有对象追加内容；
- 创建 Question Node；
- 为对象添加 Alias；
- 提议 Merge / Split。

Search 本身不执行写入。所有 Author actions 有明确 scope、revision 与 undo。

## 15.5 Search → Browse

用户可以从 Search Result 打开其 Group / Topic，而不是对象 Anchor。该动作：

- 进入稳定结构面；
- 不保留 query highlight 到整个 Group；
- Return Stack 仍可回到结果；
- 不把 Search ranking 变成 Topic member ordering。

## 15.6 转换矩阵

| 从 | 到 | 传递什么 | 不传递什么 |
|---|---|---|---|
| Search | Ask | Query 原文、Scope、显式选中 identities / anchors | ranking score、未选 snippets |
| Search | Explore | target identities、display placements | semantic edge、result order |
| Search | Author | raw query、目标 Scope 建议 | 自动保存、自动 Accept |
| Ask | Search | 原问题、Scope、关键词建议 | Answer 作为事实来源 |
| Explore | Search | 当前 Selection / Scope hint | 图形位置作为 ranking truth |
| Find | Global Search | 当前词、当前对象作为 Scope hint | 当前页命中数 |

---

# 16. Saved Search View

## 16.1 为什么是 View，不是 Group

Saved Search 的成员随知识变化而变化，所以它是观察规则：

```text
所有“法国 + 学生 + 当前有效 + 有来源”的知识
```

它不是：

- 一个新的知识群；
- 一份复制内容；
- 一个静态收藏夹；
- 一个 Overview owner；
- 一组自动 Relations；
- 一次历史结果快照。

## 16.2 保存内容

View 保存：

- 名称；
- raw / normalized query template；
- Scope；
- object type filters；
- status / Applicability / date filters；
- source / revision policy；
- mode；
- sort；
- group / list presentation；
- owner-local settings；
- created / updated time。

不保存：

- Search Hit snapshots；
- static `member_ids`；
- current result count 作为 truth；
- semantic edges；
- copied snippets。

## 16.3 动态求值

每次打开：

1. 使用当前 canonical data 与可用 Index；
2. 创建新的 Request / Run；
3. 显示当前 Coverage；
4. 新符合条件的对象自动出现；
5. 不再符合的对象自动离开；
6. 不把成员变化当作知识删除；
7. 可比较“自上次打开以来变化”。

## 16.4 冻结结果

用户需要“保留 2026-08-06 当时看到的这 23 条”时，提供：

- `保存为 Knowledge Snapshot`；或
- `导出结果及 locator`。

Snapshot 保存 evaluated member refs、revision refs、criteria、Coverage 与时间。它不冒充动态 View。

## 16.5 View 与 Overview

Saved Search View 没有 canonical Overview。可以显示：

- View 名称；
- 人话 criteria；
- 当前结果摘要；
- Coverage；
- 分组与排序。

该摘要是运行时 presentation，不参与 Group / Topic Overview 的 projection tree。

## 16.6 Empty View

空 View 不是错误：

> 当前没有知识符合“法国 · 学生 · 2026 · 有来源”。这个视图会在新内容符合条件时自动更新。

同时显示 filters、Coverage 和编辑 View 的入口，不自动删除 View。

## 16.7 View 的编辑与删除

- 改 criteria 更新 View revision；
- 可 duplicate View 再修改；
- 删除 View 不删除任何结果对象；
- Undo 可恢复 View；
- View export 保留 criteria 和人话 fallback；
- View 不出现在 Relation target picker 中，除非未来定义专门的“View references”且不等于概念 Relation。

---

# 17. Session、History、Refresh 与恢复

## 17.1 Search Session 的连续性

一次 Session 可以包括：

```text
输入 query
→ 查看 Scoped Results
→ 加 Source filter
→ 打开 Node Anchor
→ 打开 Evidence
→ Back to Node
→ Back to Search
→ Expand to All Knowledge
→ 选择 3 个对象 Ask
```

每一步的 Return Stack 必须成立，不能因为跨模式就丢失原 Search Run。

## 17.2 Recent Searches

Recent Search 保存轻量便利信息：

- raw query；
- scope summary；
- last used time；
- optional selected target identity；
- local device retention。

它不保存完整结果快照，不形成待处理任务，不进入知识导出必需层。用户可关闭或清除。

## 17.3 Clear History

清除 Recent Searches：

- 删除本地 query convenience records；
- 不删除 Saved Search Views；
- 不删除 Knowledge Snapshots；
- 不删除 Nodes / Sources / Relations；
- 不清空 Search Index；
- 不影响 Ask history；
- 当前 active Session 可单独选择保留或关闭。

确认文案必须说清上述边界。

## 17.4 Refresh

触发条件：

- canonical content 发生相关更新；
- index snapshot 更新；
- Source parse 完成；
- user changed Scope / filter / mode；
- user explicit refresh。

Refresh 创建 successor Run，不改写原 Result Set。新的结果可提供简短 diff：

- `新增 2 条`；
- `1 条不再匹配`；
- `3 条排序发生变化`；
- `来源覆盖从 partial 变为 complete`。

## 17.5 Crash / Restart 恢复

应用重启后可恢复：

- active query；
- scope / filters / mode；
- last completed Result Set 的可用 snapshot；
- selected Hit；
- scroll position；
- Return Stack 的安全部分。

若 Index 版本已经变化，先恢复旧列表并显示 Refresh，而不是悄悄执行新搜索导致用户上下文变化。

## 17.6 多窗口

每个窗口拥有独立 active Search Session。Saved Search View 与 canonical content 共享；Recent Searches 可共享但按窗口恢复 Selection。一个窗口刷新索引时，其他窗口只获得 `refresh_available`，不静默重排。

## 17.7 历史可解释性边界

普通 Recent Search 不需要永久保存所有 Run。以下情况保存完整 Run / Coverage：

- Search 转入 Saved Answer / Knowledge Snapshot；
- 用户显式冻结结果；
- 高影响批量选择依赖该 Result Set；
- 问题诊断需要并且用户选择保留；
- 导出可重建研究路径。

其余运行可按本地 retention 清理，不影响知识本体。

---

# 18. Scale、Performance 与 Accessibility

## 18.1 终局规模假设

产品定义按长期个人知识库而非小样本 Demo 设计：

```text
100+ Knowledge Groups
10,000+ Knowledge Nodes
300+ Sources
50,000+ Anchors / Blocks
multiple placements per object
years of revisions and saved snapshots
Chinese + English + mixed-language content
```

这些不是硬上限，而是验证交互不会只在 20 条漂亮数据上成立。

## 18.2 体验预算

产品级预算：

| 阶段 | 目标 | 降级行为 |
|---|---|---|
| 输入响应 | 键入、过滤、键盘选择无可感阻塞 | 不因语义请求锁住输入 |
| identity / title results | 尽快出现可判断候选 | local index / direct identity fallback |
| full-text results | 渐进补齐 | 标明仍在搜索，不先显示 No Result |
| semantic results | 可稍后补充 | 单独标明，不扰动 exact top results |
| open deep anchor | 保持结果上下文并准确定位 | Anchor 修复 / 附近定位 |
| large result navigation | 连续滚动与键盘稳定 | virtualization + progressive groups |

不以绝对毫秒写死跨设备承诺，但真实验收必须记录 p50 / p95，并在目标设备和目标数据规模上测试。

## 18.3 Progressive Results

允许渐进显示，但必须保持：

- Exact title / alias results 可以先出现；
- full-text 和 semantic 层状态分开；
- 结果完成前不显示 complete count；
- 后到 semantic 结果不把用户当前选中项推走；
- 同一 identity 的更多 Anchor 可追加到原卡，不新增重复卡；
- 完成后冻结 Result Set。

## 18.4 结果墙控制

默认不一次铺开所有命中：

- 每个对象组先显示有限高价值结果；
- 组内 `查看全部` 保留 Query / filters；
- 一个对象先显示 1 个主 Anchor；
- 其他 Anchors 按需展开；
- 低 fidelity Similar Meaning 单独折叠；
- Archived / Historical 在用户开启后仍独立分组；
- 不用无限滚动掩盖不确定 total 与 Coverage。

## 18.5 Virtualization 不破坏语义

虚拟化列表必须：

- 保留可访问的结果数量和当前位置；
- Back 后恢复精确 scroll / Selection；
- 键盘焦点不因 DOM 回收丢失；
- 屏幕阅读器可以逐组导航；
- 复制链接和打开新面板不依赖当前可视 DOM；
- 更新单条 Hit 不重建整个结果列表。

## 18.6 Keyboard Contract

至少支持：

- 打开 / 关闭 Search；
- 切换 Scope；
- 上下移动结果；
- 展开对象内 Anchors；
- 打开当前结果；
- 多选 / 取消选择；
- 返回结果；
- 打开匹配解释；
- 切换结果组；
- Find next / previous；
- 关闭临时 highlight。

快捷键必须可发现、可重映射或避免与输入法冲突，尤其考虑中文 IME composition 状态。

## 18.7 Screen Reader 与低视力

每条结果需要可读名称，例如：

> 知识，“押金”，法国租房 / 费用，正文精确匹配，共 3 处，当前知识。

同时满足：

- 组标题、结果数、loading / partial / complete 使用 live region；
- 高亮不只依赖颜色；
- type、status、match reason 有文本；
- 200% zoom 下 Scope 与 Query 不被截断；
- 水平滚动不成为阅读结果的必要条件；
- Graph 不是 Search 结果的唯一呈现；
- motion reduction 下定位动画替换为静态强调。

## 18.8 多语言性能验证

测试集必须覆盖：

- 中文无空格长文本；
- 中英混写；
- 法语重音；
- 缩写 / 全称；
- 数字、货币、日期；
- OCR 错字；
- 拼音 / 音译；
- 标题与正文不同语言；
- emoji 或符号仅作为内容而非类型图标；
- CJK Exact Phrase 与全角标点。

---

# 19. 十六个端到端场景

## 19.1 记得精确标题

用户输入 `Visale 申请条件`。一个当前 Node 的 canonical title 完全一致，三个 Sources 也包含这些词。

正确结果：Node 位于 `你的知识`首位，显示标题完全匹配、当前 Placement 与 Applicability；Sources 在独立组。Semantic results 不能压过 exact title。

## 19.2 只记得旧名字

“住房担保”已经重命名为“租房担保方案”，旧标题保留为 confirmed Alias。

正确结果：只返回当前 identity，显示 `通过曾用名“住房担保”找到`；打开进入当前 Node，不创建两条结果。

## 19.3 找一篇长知识中的原句

一个 8,000 字 Node 的第六节写着“保证金不得替代押金”，标题完全不包含查询词。

正确结果：该 Node 作为一条结果出现，显示第六节 Anchor 与完整句；打开直达该段，Back 恢复结果位置。

## 19.4 两个同名对象适用条件不同

两个 Nodes 都叫“居留许可”：一个适用于法国学生，一个适用于西班牙远程工作者。

正确结果：两条 identity 都显示，卡片在打开前就能通过 Group、定义和 Applicability 区分；不自动 Merge。

## 19.5 当前知识群无结果，全局有结果

用户在“法国租房”内搜索“CUDA occupancy”，全局“GPU 工程”中存在精确结果。

正确结果：Scoped Result Set 为空；单独提示全局有结果。只有用户触发后才进入新的 Global Run。

## 19.6 索引部分完成

10 个新 PDFs 中 8 个完成全文解析，2 个仍在 OCR。当前 Nodes 已完整索引。

正确结果：返回已有 Node / Source results，同时标记来源覆盖 partial；无结果不能表述为全部资料没有。

## 19.7 显式草稿

用户明确把“退租检查清单”保存为草稿，尚未设为当前知识，也未放入 Topic。

正确结果：Global Search 能立即通过 title / content 找到，分别标记“尚未采用”和“未归类”；Ask 默认不会把它当事实使用。

## 19.8 Archived、Trash 与 Historical

当前结果无匹配，但一个 Archived Node、一个旧 Revision 和一个 Trash object 包含原句。

正确结果：普通 Search 说明这些范围未包含；用户可显式开启 Archived / Historical；Trash 只能在 Trash Search 中出现。

## 19.9 来源原文与当前知识都命中

政策 PDF 和用户 Node 都包含“30 日内申报”。Node 是用户当前采用结论，Source 是原文。

正确结果：两者独立分组；Node 表示当前知识，Source 表示原文位置。结果排序不把角色混淆。

## 19.10 只有含义相近，没有正式关系

查询“如何证明租金支付能力”，语义结果返回“担保人材料”和“银行流水”，二者没有 Relation。

正确结果：显示 `含义相近`；可以打开各自已有关系，但 Search 不建边，Atlas 不出现新 canonical relation。

## 19.11 Saved Search 动态变化

用户保存 View“法国 · 学生 · 当前有效 · 有来源”。后来新增一个符合条件的 Node，另一个变为 Archived。

正确结果：下次打开 View 时新 Node 出现、Archived Node 离开；View identity 与 criteria 保持，不视为成员被删除。

## 19.12 选择结果后提问

用户选择两个 Nodes 与一个 Source，点击“用这些知识提问”。

正确结果：Ask Requested Context 收到 canonical identities、revisions 与 selected anchors；不使用 snippets 或 ranking score 作为 factual support。

## 19.13 深入阅读后返回

用户从 Search 打开 Node 第六节，再打开 Evidence PDF 第 12 页，然后连续 Back。

正确结果：先回 Node 第六节，再回原 Search Result Set；Query、展开 Anchors、scroll 与选中项不丢。

## 19.14 AI 与网络不可用

设备离线，semantic service 和 remote Source 都不可用。

正确结果：本地 title / alias / full-text / property Search 正常；Similar Meaning 显示不可用；remote Source 覆盖缺口可见；不锁死 Search。

## 19.15 Split 后的旧目标

旧 Node“法国住房手续”已 Split 为“租房材料”和“入住申报”。用户搜索旧标题。

正确结果：显示原知识已拆分并列出两个 successors；不自动选一个，也不把旧内容作为当前 truth 返回。

## 19.16 大规模、多语言与 OCR

在 10,000 Nodes、300 Sources 中输入中英混合查询 `CAF 房补 attestation`，一个 OCR PDF 把 `attestation` 识别得不确定。

正确结果：已确认 Alias / exact terms 优先；OCR 命中独立标明低置信；首屏保持可扫描，键盘和屏幕阅读器可达。

---

# 20. 质量指标与反指标

## 20.1 北极星不是“搜索次数”

核心结果是：用户以可预测方式找到正确知识对象或精确位置，并在打开、核验和返回过程中不失去上下文。

## 20.2 核心指标

| 指标 | 定义 | 需要分层 |
|---|---|---|
| Search-to-correct-target | 一次 Session 内到达目标 identity 的成功率 | exact / lexical / semantic、对象类型 |
| Deep-anchor precision | 打开后直接落到正确 Anchor 的比例 | Node / Source / Saved Answer |
| Context restoration | Back 后完整恢复 Search 状态的比例 | 跨 Node / Evidence / Ask / Explore |
| First useful set | 首个有限结果集合含正确目标的比例 | Scope / language / scale |
| Reformulation recovery | 首次无结果后通过明确建议找回的比例 | spelling / scope / filter / state |
| Honest no-result | 空状态正确说明 Coverage / exclusions 的比例 | partial / stale / unparsed / true empty |
| Scope expansion recovery | Scoped no result、global yes 时正确转接率 | Group / Topic / Node |
| Duplicate disambiguation | 同名对象在打开前被正确区分的比例 | Applicability / Group / state |
| Multi-placement coherence | 同一 identity 不重复且能选正确 Placement | 2+ placements |
| Offline continuity | AI / network unavailable 时核心 Search 成功率 | exact / full-text / property |

## 20.3 诊断指标

- zero-result rate，按真实原因拆分；
- partial coverage exposure rate；
- index freshness lag；
- alias collision rate；
- orphaned Anchor rate；
- result duplicate identity rate；
- Search → Ask context identity preservation；
- Search → Explore false-edge rate；
- Saved View evaluation consistency；
- screen reader task completion；
- 200% zoom task completion；
- p50 / p95 title、full-text、semantic 和 open-anchor latency。

## 20.4 反指标

不得把以下数值单独作为产品成功：

- 结果数量越多；
- 查询次数越多；
- 点击率越高；
- 搜索停留越长；
- Semantic 结果占比越高；
- 最近编辑对象点击越多；
- 用户保存的 Search 越多；
- Query reformulation 次数越多；
- 输入框使用频率越高；
- AI 转换率越高。

这些可能意味着找不到、排序不稳定或被迫反复尝试。

## 20.5 质量分层

所有核心指标至少按以下维度拆分：

- 数据规模；
- 查询语言；
- query type；
- object type；
- current / working / archived / historical；
- exact / alias / lexical / semantic；
- scoped / global；
- index current / partial / stale；
- desktop / keyboard / screen reader / zoom；
- local-only / semantic-enabled / offline。

不允许用小型英文 exact-title 数据集的平均值证明真实知识找回质量。

---

# 21. 十九条 Given / When / Then 验收

## 21.1 精确标题优先

**Given** 一个 Node 标题与 Query 完全相同，五个 Sources 只在正文包含这些词  
**When** 用户使用 Best Match  
**Then**：

- Node 在 `你的知识`首位；
- 标明 `标题完全匹配`；
- Sources 独立分组；
- semantic candidates 不压过它；
- 不显示裸 relevance 分数。

## 21.2 Alias 与 Rename

**Given** Node 已重命名且旧标题保留为 confirmed Alias  
**When** 用户搜索旧标题  
**Then**：

- 只出现一个 current identity；
- 显示旧名匹配；
- 打开当前 revision；
- Back 恢复原 Search；
- Graph 不新增 Alias relation。

## 21.3 深层 Anchor

**Given** Query 只匹配长 Node 第六节的一个句子  
**When** 用户打开结果  
**Then**：

- 结果以 Node identity 聚合；
- 显示第六节 snippet；
- 打开到正确 Anchor；
- DepthTrail / Placement 正确；
- 返回恢复 scroll / Selection。

## 21.4 同名消歧

**Given** 两个对象标题相同但 Group 和 Applicability 不同  
**When** 两者都匹配  
**Then**：

- 两个 identities 均显示；
- 打开前可区分；
- 不自动 Merge；
- exact match 不因 recentness 隐藏任一项；
- Alias conflict 可单独修复。

## 21.5 Scoped no result / Global yes

**Given** 当前 Group 没有命中、All Knowledge 有精确命中  
**When** Scoped Search 完成  
**Then**：

- 当前 Result Set 仍为空；
- 全局命中只作为建议；
- 用户触发后创建新 Run；
- 两个 Run 的 Scope 可检查；
- Back 恢复 Scoped empty state。

## 21.6 Index partial

**Given** current Nodes 已完整索引但部分 Sources 未解析  
**When** Query 返回 3 个 Node hits  
**Then**：

- 3 个结果正常可用；
- 结果头标记 partial；
- 说明未覆盖 Sources；
- 不说“所有资料只有 3 条”；
- 解析完成后提供 Refresh。

## 21.7 Current read-your-write

**Given** 用户刚完成一个无 Placement Node 的 Direct Edit Commit，完整索引还未更新  
**When** 立即搜索其标题  
**Then**：

- direct identity / fallback 找到它；
- 标记 Current 与 unplaced；
- Search 可打开编辑；
- Ask 默认使用这个 Current Revision；若 local delta 尚未进入 Ask index，明确显示索引正在更新而不是读旧版；
- index update 不制造重复结果。

## 21.8 状态边界

**Given** Archived、Historical 与 Trash 中各有一处 match  
**When** 普通 Global Search 运行  
**Then**：

- 三者默认不混入；
- Coverage / exclusions 可见；
- Archived / Historical 可显式开启；
- Trash 只能在 Trash Search；
- 开启条件创建新 Request。

## 21.9 Source 与 Knowledge role

**Given** Source 原文和 Accepted Node 同时命中  
**When** 查看结果  
**Then**：

- 对象组分开；
- Node 写 `你的知识`；
- Source 写 `来源`及 locator；
- 打开 Source 不改变 Node；
- 找到 Source 不等于接受其内容。

## 21.10 Semantic no relation

**Given** 两个 Nodes 仅因语义相似被命中，canonical graph 无 Relation  
**When** 用户从 Search 打开 Explore  
**Then**：

- Similar Meaning 原因可见；
- Local Graph 不生成正式边；
- 可显示临时 recommendation overlay；
- 清除后布局恢复；
- 建 Relation 必须进入 Editor。

## 21.11 Saved Search 动态语义

**Given** 一个 Saved Search View 已保存 criteria  
**When** 当前知识新增、归档或修改 Applicability  
**Then**：

- 重新打开产生新 Run；
- 当前匹配动态变化；
- View 不保存旧 member list；
- criteria 与 Coverage 可检查；
- 冻结结果需另建 Snapshot。

## 21.12 Search → Ask identity 传递

**Given** 用户选中多个 Search Hits  
**When** 转换 Ask  
**Then**：

- 传递 canonical identities / revisions / anchors；
- 不传 ranking score 作为 truth；
- 不把 snippets 当 Source；
- Ask 显示 Requested Context；
- Answer 仍需 Claim-level support。

## 21.13 Return Stack

**Given** Search → Node Anchor → Source Evidence  
**When** 用户连续返回  
**Then**：

- 首次返回 Node Anchor；
- 再返回原 Result Set；
- Query / filters / mode 不丢；
- scroll / expanded Anchors / Selection 恢复；
- 不静默执行新 Run。

## 21.14 Offline degradation

**Given** 网络、AI 与 semantic index 均不可用  
**When** 用户搜索本地知识  
**Then**：

- exact title / alias / full-text / property 可用；
- Similar Meaning 标记 unavailable；
- remote Sources 标记覆盖不足；
- 不丢 query；
- 不把 degradation 写成 No Knowledge。

## 21.15 Find in Object

**Given** 当前 Node 有折叠 section 和嵌入 Source preview  
**When** Find 命中折叠正文和 preview 文本  
**Then**：

- 折叠 section 可展开定位；
- preview 命中说明嵌入边界；
- 不暗中搜索完整 Source；
- Next / Previous 与计数正确；
- Replace 不在 Find 中直接执行。

## 21.16 Large-scale accessibility

**Given** 10,000 Nodes、300 Sources、混合语言和 200% zoom  
**When** 键盘与屏幕阅读器用户完成查找  
**Then**：

- 结果分组可读；
- 焦点不因 virtualization 丢失；
- type / state / reason 不只靠颜色；
- 同一 identity 不按 chunk 重复；
- 用户能打开精确 Anchor 并返回。

## 21.17 Topic direct / descendant scope

**Given** Topic A 有 direct Knowledge，子主题 A1 / A2 也有 Knowledge，且同一 Knowledge 出现在两个 descendants  
**When** 用户在`只看这里`与`包含子主题`之间切换  
**Then** 前者只返回 direct placements；后者按 identity 聚合并保留两个 exact paths；搜索摘要明确范围，ancestor 不产生镜像 Placement。

## 21.18 Attached Source title / body boundary

**Given** Source-only 只 attached 到深层 Topic，正文已索引但没有 Evidence Binding  
**When** 用户分别搜索 direct Topic、ancestor Topic 与整个 Group，并切换 Source body 开关  
**Then** title 是否命中由 Attachment path + descendant policy 决定，正文是否命中另受 source expansion + Coverage 约束；Binding 缺失不让材料消失。

## 21.19 Group root placement 与 Unplaced

**Given** Knowledge 直接 placed 到 Group root  
**When** 搜索该 Group 与 Unplaced View  
**Then** Group Search 显示`直接放在这个知识群`，Unplaced 不返回它；移除最后一个 active Placement 后才进入 Unplaced。

---

# 22. 官方研究依据与产品推论

本轮只用成熟产品的官方资料验证真实存在的检索模式。它们提供设计证据，不直接决定本产品的 ontology。

## 22.1 Capacities：全文、精确、语义、对象类型与 Saved Query

Capacities 官方文档把 Search 用于导航、找回和连接；其 Extended Search 支持全文内容、exact phrase、对象类型 / 标签过滤、对象与 Block 范围、分组以及把条件保存为 Query，并提供 Auto、Exact 与 Semantic 模式。[Capacities — Search & Command Palette](https://docs.capacities.io/reference/search)

产品推论：成熟知识工具需要精确与语义并存、对象 / Block 粒度可区分、复杂条件可动态保存。但本产品进一步冻结“对象 identity 聚合”和“Saved Search 是 View 而非静态结果”，避免内部 chunk 或 Query 成为第二套知识对象。

## 22.2 Notion：标题优先、范围过滤、排序与页内查找

Notion 官方帮助说明 Workspace Search 支持 exact phrase、title-only、creator、teamspace / location、date filters 与多种排序；Best Matches 会优先页面标题并参考最近编辑，同时把 Workspace Search、Database Search 与 Find in Page 区分。[Notion — Search](https://www.notion.com/help/search)

产品推论：标题优先、范围过滤和页内查找是成熟找回的基础。与之不同，本产品明确把 recentness 限为 tie-break，并要求 Scoped no result 不混入全局结果，因为个人知识库里的近期性不代表适用或正确。

## 22.3 Obsidian：可组合操作符、结果上下文与页内 / Block 粒度

Obsidian 官方 Search 支持 AND / OR、排除、嵌套，以及 path、file、content、tag、line、block、section、task、property 等操作符；也允许解释搜索条件、排序结果和展开匹配上下文。[Obsidian — Search](https://obsidian.md/help/plugins/search)

产品推论：高级用户确实需要组合条件和精细内容定位。但自然语言解释与可视筛选必须先成立，不能要求普通用户掌握 DSL；同时 Block match 应回到父对象 identity，而不是制造碎片对象。

## 22.4 Zotero：搜索层次、全文索引状态与动态 Saved Search

Zotero 官方文档区分 Quick Search 的 Title / Year / Creator、All Fields & Tags 与 Everything（包括已索引全文），提供 Advanced Search；Saved Searches 保存条件而非结果并动态更新，同时有全文索引状态和重建能力。[Zotero — Searching](https://www.zotero.org/support/searching)

产品推论：对象元数据、全文与高级条件应有层次，Saved Search 的本质是动态规则，索引状态也是用户需要理解的产品能力。本产品因此把 Index 与 canonical store 分离，并明确重建索引不能危及知识。

## 22.5 Anytype：本地数据与索引分层

Anytype 官方安全文档说明，本地数据包含用于加速搜索、过滤和 Graph 的 indexes，并把 indexes 与 object store 区分；其开发者搜索文档也把全局搜索、type filtering、排序与全文能力作为对象查询接口。[Anytype — How we keep your data safe](https://doc.anytype.io/anytype-docs/advanced/data-and-security/how-we-keep-your-data-safe) · [Anytype API — Searching](https://developers.anytype.io/docs/guides/get-started/searching/)

产品推论：本地优先产品不应把 Search Index 当作唯一数据真相。索引可重建、canonical object 不丢失、离线 exact / full-text 成立，是所有漂亮搜索交互之前的底线。

## 22.6 研究推论边界

官方资料共同证明：

- 精确、全文、语义和结构化过滤是不同检索需要；
- 页内 Find 与全局 Search 应分开；
- Saved Search 应动态更新；
- 全文索引状态会影响结果可信度；
- 对象类型和匹配上下文是可判断结果的必要部分。

它们不证明本合同的 52 项决定已经通过本产品用户测试，也不证明特定 ranking、默认 Scope 或结果卡布局唯一正确。后续仍需使用用户自己的真实知识内容验证 exact recall、同名消歧、深 Anchor、无结果诚实度与返回连续性。

---

# 23. 对后续视觉设计的约束

本合同不授权开始原型。未来进入方向 3 + 2 的视觉设计时，必须证明以下产品事实，而不只是做出漂亮 Search overlay：

1. Global、Scoped、Find、Picker 与 Command 的当前模式一眼可知；
2. Search、Ask 和 Explore 仍是不同承诺，不被一个“AI 输入框”吞掉；
3. 默认首屏能看懂 Scope，完整 Expansion / Coverage 又可检查；
4. exact title / phrase 视觉优先，semantic match 明确但不过度强调；
5. 结果围绕对象 identity，同一 Node 的多 Anchors 不复制成结果墙；
6. 同名对象通过 definition、Group、Applicability 与状态在打开前消歧；
7. 多 Placement 只显示一个 identity，并能展开其他位置；
8. Node、Source、Saved Answer 和 Historical Revision 的知识角色不会混淆；
9. 一条结果可理解“是什么、为什么匹配、在哪里、是否适用”；
10. 匹配原因不用裸分数或神秘星级；
11. Scope 内无结果与全局建议在视觉上严格分层；
12. true empty、filter excluded、index partial、source unparsed、semantic unavailable 与 failure 不共享一个空页面；
13. Coverage 是人话摘要，不是默认展开的技术日志；
14. Search → Node Anchor 的定位强调短暂、准确且非内容写入；
15. Back 恢复 Query、结果、scroll 与 Selection；
16. Search result → Evidence → Back 的 Return Stack 可见但不笨重；
17. 选择多个结果转 Ask 时显示真实 identities，而不是 snippets chips 墙；
18. Search → Explore 不画出 semantic 假边；
19. Saved Search 明确是动态 View，Snapshot 明确是冻结结果；
20. Working、Archived、Historical 与 Trash 的进入边界可预测；
21. Index updating / partial / stale 不用持续红色告警制造焦虑；
22. AI offline 时 Search 仍像完整产品，不像残缺降级页；
23. 10,000 Nodes 下使用分组、展开和 virtualization，不依赖密集缩小字号；
24. 200% zoom、键盘、屏幕阅读器和 reduced motion 可完整完成查找；
25. 中文 IME 输入、精确短语、别名和中英混搜在输入状态中真实成立；
26. Command Palette 的动作后果与知识结果打开后果清楚；
27. destructive commands 不会因统一 Enter 语义被误执行；
28. 视觉方向 3 的空间探索感与方向 2 的高密度知识工作台感结合时，Search 仍以“准确定位”而非“炫技的网络动画”为中心。

---

# 结论

搜索真正属于个人知识库，不是因为它能对所有文本做模糊匹配，而是因为它尊重知识身份、结构位置、适用范围、状态、版本和来源角色。

> **用户搜索的不是一堆相似文字，而是自己曾经建立、阅读、接受、搁置或保存过的知识对象；系统必须把他带到正确对象的正确位置，并诚实说明为什么找到、哪里没搜到、返回时如何回到原来的认知现场。**

因此，本产品的 Search 不是 Ask 的低配入口，也不是 Graph 的动画触发器。它是整个知识网络的定位层：精确优先、语义补充、对象稳定、范围可见、无结果诚实、离线成立，并能无损地把用户交给阅读、提问、探索和创作。
