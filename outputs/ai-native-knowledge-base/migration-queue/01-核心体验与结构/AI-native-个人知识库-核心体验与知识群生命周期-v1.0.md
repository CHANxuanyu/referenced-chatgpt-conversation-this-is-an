# AI-native 个人知识库

## 核心体验与知识群生命周期 v1.0

> 日期：2026-08-06  
> 文档性质：产品体验决策；定义首要用户、核心循环、知识群长期状态配置与默认 Overview，不是视觉稿、原型或研发排期  
> Canonical 产品定义：`AI-native-个人知识库-终局产品设计文档-v4.0.md`；本文档只证明核心体验与生命周期责任，不得反向改写 v4.0  
> 2026-08-07 Library-first 覆写：产品打开进入 Knowledge Library；本文旧 Home 统一读取为 Library 内的 Resume region，旧 Atlas 读取为 Library Network / R3。Group、Topic、Knowledge 在同一连续阅读现场中展开；Overview、Structure、Relations、Sources 是完整责任而非四个同权页面  
> 2026-08-07 写入冻结：低风险用户直接写入经安全 Direct Edit Commit 更新当前知识；Buffer / Recovery、Explicit Draft、Proposal、Sync 与 Projection 分开，只有非普通写作路径进入预览 / 确认  
> 2026-08-08 Group Formation 覆写：空白、已有 Knowledge、Source bundle、Topic、View / Search snapshot 与 imported hierarchy 只是六种起点，不是六类 Group；AI cluster 只形成 Group Candidate，拒绝零副作用，View future matches 不继承 membership  
> v4.0 策展覆写：Orientation Profile 只改变信息权重；stable start、representative Knowledge 与 recommended Path 由用户策展或接受 Diff，不能由 Profile、Recent 或 AI ranking 自动重写  
> v4.0 Relation 覆写：Group 的 Orientation 不以 Relation 数量或连通率决定；跨群 exit 可以先于 Group Relation。只有 maintained 且 lifecycle=current 的 Group Relation 进入 Library Network / R3 当前层，底层 supporting paths 变化只更新 Support Set 并触发 review_due，不制造伪边  
> 2026-08-10 Relation Lifecycle 覆写：RelationCandidate 与正式 Relation 是不同对象；当前层、建议层与历史层分开；ended、superseded、retracted、archived 具有不同语义；Group Split / Merge 不得静默迁移端点。完整合同见`AI-native-个人知识库-关系陈述生命周期与网络可信性合同-v1.0.md`  
> v4.0 Query 覆写：Ask 服务“调用并重新进入知识”的核心循环；回答前范围可预测、回答中 Claim 可核验、回答后可回到 Reading / Relation / Evidence，保存 Answer 不改变 Group formation 或当前 Knowledge  
> 2026-08-09 First Returnable Asset 覆写：首日不是单一路径；写、建群、加资料、迁入与提问都可开始。Empty Group 合法但不计首份可返回资产；Current Knowledge 或 Source-only Asset 才是首个 durable asset；Relation、Topic、AI、账号与同步均不是门槛。完整合同见`AI-native-个人知识库-首日到日常核心旅程合同-v1.0.md`  
> 2026-08-09 Group State 覆写：旧 `Seed → Forming → Established ↔ Evolving → Dormant` 单轴模型失效；改为 Orientation、Change、Attention、Lifecycle 与 Boundary continuity 五个正交维度。完整合同见`AI-native-个人知识库-知识群状态演化与身份连续性合同-v1.0.md`  
> 历史深层模型：`AI-native-个人知识库-产品定义-v3.0.md`  
> 交互基线：`AI-native-个人知识库-交互架构与设计系统-v1.0.md`  
> 语言基线：`AI-native-个人知识库-产品语言与渐进披露规范-v1.0.md`
> 知识深度与关系：`AI-native-个人知识库-知识深度与关系探索合同-v1.0.md`
> 知识形成与维护：`AI-native-个人知识库-知识形成与维护循环-v1.0.md`
> 知识群边界与跨群架构：`AI-native-个人知识库-知识群边界与跨群架构合同-v1.0.md`
> 知识节点粒度与内容组成：`AI-native-个人知识库-知识节点粒度与内容组成合同-v1.0.md`
> Overview 形成、编辑与更新：`AI-native-个人知识库-Overview形成编辑与更新合同-v1.0.md`
> AI 查询与知识回答：`AI-native-个人知识库-AI查询与知识回答合同-v1.0.md`
> 来源、证据与可追溯性：`AI-native-个人知识库-来源证据与可追溯性合同-v1.0.md`
> 产品对象层级与身份治理：`AI-native-个人知识库-产品对象层级与身份治理合同-v1.0.md`

---

# 0. 本轮真正要解决的问题

此前文档已经回答了产品“由什么组成”：Knowledge Group、Topic、Knowledge Node、Relation、Overview、Source、Evidence，以及从 L0 到 L5 的知识深度。

但对象完整不等于产品成立。仍有六个决定直接影响用户每天打开产品时看到什么：

1. 首先为谁设计；
2. 用户打开产品后的最短价值路径是什么；
3. 一个空知识群如何自然长成稳定知识范围；
4. 不同 Orientation、Change、Attention 与 Lifecycle 条件怎样在同一 Group Overview 中组合；
5. AI 应主动到什么程度；
6. 白板、协作、多 Space 等能力是否属于产品本体。

本文件冻结这些决定。冻结不代表它们已经被真实用户验证；它表示在获得相反证据前，产品、交互与视觉必须按同一套判断前进，不能继续让未决项互相拉扯。

---

# 1. 首要用户决策

## 1.1 不按职业定义，而按知识工作的形状定义

**[产品决策] 首要用户是“长期处理多个复杂知识范围，并需要反复返回、深化和调用这些知识的个人”。**

他可能是产品经理、研究者、设计师、创作者、创业者、咨询顾问或高强度学习者，但职业不是决定条件。真正的共同特征是：

- 同时拥有多个会持续数月或数年的主题、项目或问题域；
- 材料来自文档、网页、对话、视频、会议和自己写下的判断；
- 不只想保存资料，而是要形成结构化理解；
- 同一条知识会在不同工作或生活语境中被再次使用；
- 需要从概览恢复上下文，也需要深入到细节和来源；
- 希望 AI 分担整理和综合，但不愿把知识资产交给不可检查的黑盒；
- 愿意修正重要知识，但不愿每天维护一套复杂数据库。

因此，产品不是只为“研究学习”或只为“专业工作”设计。研究、工作和复杂生活决策是三类内容场景；首要用户的共同需要是**长期拥有一张可进入、可核验、会演化的个人知识世界**。

## 1.2 首要使用门槛

用户不需要：

- 预先理解知识图谱；
- 先设计标签、属性和数据库；
- 每天写日记或维护链接；
- 为每条知识手工寻找唯一文件夹；
- 学会 Prompt Engineering 才能提问；
- 连续签到或完成整理任务。

用户需要愿意做的最小工作是：

- 命名一个知识群，或添加一批来源；
- 在高影响结构变化时做少量确认；
- 在系统理解错误时纠正；
- 在真正重要的结论上检查来源和适用条件。

## 1.3 非首要用户

以下人群可以使用局部能力，但不能主导默认体验：

- 只需要短期备忘和待办的人；
- 把团队权限、发布和多人协作视为首要需求的人；
- 只想一次性问一批文件、不准备形成长期知识的人；
- 主要想自由摆放卡片、画思维导图或做视觉创作的人；
- 以数据库应用、工作流自动化或项目排期为主要目标的人。

---

# 2. 产品核心承诺

## 2.1 用户真正购买的不是“AI 整理”

用户真正获得的是三种能力：

1. **定位**：很快知道自己拥有哪些知识，这次应该进入哪里；
2. **理解**：先看到整体，再连续深入到细节和证据；
3. **调用**：通过搜索、AI 查询或关系探索，把既有知识用于新的问题。

AI 整理、自动聚类、摘要和图谱只是实现机制。任何自动化如果没有提高定位、理解或调用，都不应成为产品主叙事。

## 2.2 核心体验一句话

> **打开一个知识群，先理解它现在是什么，再选择阅读、探索、提问或继续建设；每次有价值的行动都会让这个知识群更完整，而不会制造另一个信息孤岛。**

## 2.3 最小闭环

```text
定位知识范围
  → 理解当前整体
  → 阅读 / 探索 / 提问 / 创作
  → 查看实际范围、结论依据与语境
  → 保存回答，或按 Claim 修正 / 形成有价值的知识
  → Overview、层级、关系与未来回答同步变化
  → 下次从同一知识世界继续
```

这个闭环同时约束三件事：

- AI 回答既不能只留在聊天记录，也不能未经选择自动进入当前知识；
- 新来源不能只进入文件列表；
- 用户写下的知识不能与系统生成的知识分裂成两套产品。

---

# 3. 产品时间尺度

产品不应假设每次使用都需要深度工作。它必须在四种时间尺度上同时成立。

## 3.1 10 秒：定位

用户打开产品后，应能回答：

- 我有哪些主要知识群；
- 最近我正在理解什么；
- 哪些知识发生了值得注意的变化；
- 我可以继续上次路径，还是进入另一个群。

Knowledge Library 内 Resume region 的责任是恢复知识上下文，不是形成独立首页，也不是展示统计、待办或 AI 活动流。

## 3.2 2 分钟：找回或回答

用户应能：

- 进入一个知识群并理解边界；
- 从 Overview 找到一个主题或关键知识；
- 搜索一个已知对象；
- 在明确范围内提问并看到答案、知识路径和来源入口。

## 3.3 15–45 分钟：深化

用户可以：

- 从 Overview 连续读到机制、例子、限制和证据；
- 沿关系跨主题或跨群探索；
- 综合多条知识形成新的 Node 或 Saved Path；
- 编辑主题结构、关系和 Overview；
- 处理一项真正影响理解的更新或冲突。

## 3.4 周期性：维护与迁移

产品可在适当时机聚合：

- 重要新来源带来的变化；
- 需要确认的结构建议；
- 失效来源、陈旧知识或真正冲突；
- 备份验证和索引健康。

它不能把维护包装为每日打卡、清零红点或无限 Review Inbox。没有值得处理的变化时，安静是正确状态。

---

# 4. 核心用户循环

## 4.1 Orient / 定位

用户从 Knowledge Library 的知识群 / Knowledge Network 视图、搜索结果或上次路径进入。

系统需要回答：

- 这里是什么知识范围；
- 它现在处于什么状态；
- 上次焦点在哪里；
- 最值得继续的入口是什么。

## 4.2 Understand / 理解整体

进入 Group 后默认先看到 Overview，而不是文件列表、空白画布或全量图谱。

Overview 的稳定主入口来自 Scope curation；没有策展时按 canonical structure 给出诚实回退。最近焦点只支持`继续`，当前 AI suggestion 只支持本次探索，二者不改变“从哪里开始”的长期判断。

Overview 必须帮助用户理解：

- 群的边界；
- 主要主题；
- 已形成的核心理解；
- 重要关系；
- 尚不确定或正在变化的部分。

## 4.3 Act / 选择行动

同一个知识群允许四种平行行动：

| 用户意图 | 首要入口 | 输出 |
|---|---|---|
| 阅读 | 主题、关键知识、继续上次位置 | 更深理解 |
| 探索 | 局部关系、相邻主题、跨群路径 | 新连接或 Saved Path |
| 提问 | 当前群或当前节点范围内 Ask | 可核验 Claims + 真实路径 / Used Knowledge + Evidence + Coverage |
| 建设 | 写知识、建主题、加来源、建关系 | 可持续知识对象 |

没有一种行动是“正确使用方式”。阅读和探索不应被聊天取代，手工建设也不应被 AI 生成降级为例外。

## 4.4 Verify / 核验

当用户需要判断而非浏览时，可以逐步看到：

- 这条知识出现在哪些语境；
- 它与什么形成关系；
- 当前结论适用于什么条件；
- 来源、版本和原文位置；
- 是否存在冲突、缺口或无法核验部分。

核验是一跳可达的深层能力，不是默认界面的持续噪声。

## 4.5 Consolidate / 沉淀

用户可以把一次探索或回答：

- 保存为 Path；
- 综合为新知识；
- 补充到已有知识；
- 加入或修正关系；
- 明确提出并检查 Overview Semantic Diff；
- 保留为历史快照而不写入正式知识。

进入 canonical 编辑前必须说明影响范围。低风险个人写作在 composition 结束并到达安全边界后即时 Direct Edit Commit；Recovery protection 不等于 current，sync / projection 也不决定 current。高影响结构和跨群变更需要预览。

## 4.6 Return / 返回

下次回来时，系统恢复的是知识上下文：

- 上次在哪个群、主题和深度；
- 沿哪条路径到达；
- 此后有哪些重要变化；
- 原来的判断是否仍然成立。

它不是简单恢复最后打开的页面，也不是自动生成一份项目日报。

---

# 5. Knowledge Group 的长期状态配置

## 5.1 为什么不再使用单一 formation phase

同一个 Group 确实需要根据真实情况改变开场：空群需要帮助开始，已有结构的群需要低噪声阅读，重要变化需要解释，长时间离开需要重新定位，归档内容需要只读与恢复。

但这些不是一条“从小到大”的阶段。旧模型把不同问题混在一起：

- Seed / Forming / Established 回答“当前能怎样呈现整体”；
- Evolving 回答“有没有重要变化”；
- Dormant 回答“用户是否希望它参与当前注意力”；
- Archived 回答“它是否仍属于 current knowledge”；
- Boundary revision / successor / split / merge 回答“是否仍是同一个 Group”。

因此不再保存互斥 `formation_phase`。同一个 Group 使用正交 `state_configuration`，允许真实组合，例如 `oriented + review_due + paused + current + continuous`。

## 5.2 五个独立维度

| 维度 | 值 | 产品责任 |
|---|---|---|
| **Orientation Profile** | `bare / structuring / oriented` | 根据 accepted content 选择 Overview 开场；不是成熟度 |
| **Change Condition** | `no_material_change / changes_available / review_due / transition_in_progress` | 定位变化影响；不阻断未受影响阅读 |
| **Attention Mode** | `normal / paused` | 决定主动注意力；Paused 仍属 current knowledge |
| **Lifecycle State** | `current / archived / trash` | 区分当前、归档、删除准备；Permanent Delete 另行确认 |
| **Boundary Condition** | `continuous / tension / revision_available / identity_transition_required` | 区分普通边界修订与新 identity 转换 |

这些内部值默认不显示成标签。页面只在某个条件改变当前动作时，用一句事实说明发生了什么、影响哪里、用户可以做什么。

## 5.3 Orientation Profile

### Bare

当前只能诚实呈现 Group identity、已有内容与开始方式，尚不能提供稳定整体方向。它可以完全空白，也可以只有一条 Knowledge 或一批 Source-only Assets。

系统责任：真实内容优先；完全空白时突出`写下第一条知识`，`添加资料 / 建立主题`作为安静替代；不生成假 Overview、假 Topics、空 Network 或完成度。

### Structuring

已经出现多个真实方向或足够材料，但整体说明、边界或稳定进入顺序仍在形成。候选 Topic 与 Boundary Diff 继续是 proposal，不因视觉需要写入 canonical structure。

系统责任：显示已成立的主要方向、真实覆盖和 deterministic structure fallback；不把“整理完所有材料”设为使用门槛。

### Oriented

普通进入时已经能说明“这是什么、有哪些主要方向、从哪里开始”，足以支持稳定阅读、探索与查询。它不要求内容多、Relation 多、近期活跃或没有未知。

系统责任：状态退到背景；Overview、stable start、主要方向与代表理解优先。不得显示“成熟”“已升级”或完成度。

## 5.4 Change Condition

- `no_material_change`：没有尚未处理、且足以影响当前整体理解的变化；不表示所有内容最新；
- `changes_available`：有依据的新变化可能影响具体 Overview、Knowledge、Relation、Path 或 Answer；
- `review_due`：accepted truth 已改变当前策展或解释依据，必须定位 affected owners；
- `transition_in_progress`：用户已确认高影响 Change Set，canonical transaction 已提交但派生投影仍在刷新。

Evolving 不再是 Group 阶段。变化作为 overlay 叠加在现有 Orientation 上：最后稳定理解和未受影响路径继续可读；用户可以先阅读，再检查变化。关闭 impact 需要接受、限定、证明无影响或明确保持当前理解，不能靠“标记已读”让事实消失。

## 5.5 Attention、Lifecycle 与 Boundary

- `attention_mode = paused`：用户暂时不希望 Group 主动竞争注意力；它仍在 All Groups、Search、Ask 与 Relations 中。系统可以建议但不能自动 Pause；普通打开不自动恢复 Normal；
- `lifecycle_state = archived`：Group 不再属于 current knowledge，但 Overview、links、history、Sources 与 Restore 保留；默认 Search / Ask 排除，显式包含时说明 historical basis；
- `lifecycle_state = trash`：只在 Trash / impact context 可达，排除 Search / Ask / Network；Permanent Delete 只能从这里发起；
- `boundary_condition = tension / revision_available`：仍可保持同一 identity；接受 Boundary Revision 不自动搬动内容；
- `identity_transition_required`：governing question 或长期用途不连续，使用 successor / split / merge，不允许同一个 `group_id` 静默换范围。

## 5.6 判定权与事件分权

Orientation、Change 与 Boundary condition 可以基于 accepted facts 自动刷新，但必须保存依据；Attention 与 Lifecycle 只能由显式用户动作改变。未接受 AI proposal、候选 Topic、候选 Relation、临时 Query、内容数量、Relation 度数、最近访问、AI confidence 与 embedding cluster 都不能改变 canonical 状态。

任一轴变化不得顺带改变其他轴：

- Pause 不改变 freshness、Ask membership、Orientation 或 Lifecycle；
- 新 Source 不自动修改 Boundary 或 Overview；
- Archive 不接受 pending proposals，也不删除内容；
- Restore 重新解析当前 truth，不恢复一个历史 phase；
- Split / Merge 后每个新 Scope 分别解析状态，不复制复合标签；
- Profile 变化只改变 Presentation，不创建 Editorial revision、不重排 Library。

完整 resolver、组合矩阵、事件表、Archive / Restore、identity continuity 与验收见`AI-native-个人知识库-知识群状态演化与身份连续性合同-v1.0.md`。

---

# 6. Group Overview 的永久合同

本章只定义 Orientation Profile 与必要 overlays 如何组合。Overview 的 identity、单一 content tree、Block types、Support Map、治理、alignment、版本与变换遵守 `AI-native-个人知识库-Overview形成编辑与更新合同-v1.0.md`。

无论状态配置如何，一个 Group Overview 都应尽可能回答五个问题：

1. **这是什么**：一句定位与边界；
2. **它由什么组成**：主要主题和层级；
3. **目前知道什么**：核心理解、代表知识和关系；
4. **哪里不确定或在变化**：未知、冲突、覆盖与变化；
5. **下一步去哪里**：继续阅读、探索、提问或建设的入口。

Profile 改变的是五部分的权重和可用程度；Change、Attention 与 Lifecycle 只叠加必要说明。Overview 不会因此变成多套页面，也不自动创建新的 Editorial revision。

## 6.1 Bare Profile

### 首要状态句

完全空白时：

> 这个知识群刚刚开始。

若已有真实内容但尚无整体 Orientation，不使用空态覆盖内容；改为说明当前只有哪些内容、可以从哪里继续。

### 默认内容顺序

1. 名称与可选边界句；
2. 一个首要动作`写下第一条知识`；两个安静替代`添加资料`、`建立主题`；
3. 已有的少量内容；
4. 相邻知识群或关系建议（只有确有依据时）；
5. “这个群想解决什么”轻量提示。

### 禁止

- 自动铺满空 Topic 模板；
- 生成看似完整的长篇 Overview；
- 展示空白大图谱；
- 把添加来源设为唯一开始方式；
- 用完成度催促用户。

## 6.2 Structuring Profile

### 首要状态句

> 已有几个真实方向，整体说明仍在形成。

### 默认内容顺序

1. 当前边界与覆盖说明；
2. 新出现的主题及其代表知识；
3. 尚未归位的知识或来源；
4. 待澄清问题与可能的群边界；
5. 少量可解释结构建议；
6. 继续阅读、探索或确认结构。

### 首要动作

进入用户设置的 stable start；没有策展时按当前 semantic order 进入第一个可读主题，并写明这是结构回退。真正影响边界的建议作为次级判断入口。系统不把“整理完全部材料”设为默认任务，也不把“内容最多”冒充“最值得先读”。

## 6.3 Oriented Profile

### 首要状态句

默认不显示 Profile 标签。只有 Change、Attention、Lifecycle 或 Boundary condition 影响当前动作时，才显示一句说明。

### 默认内容顺序

1. 三至五句群定位与当前整体理解；
2. 一个 stable start；无策展时显示结构回退；
3. 稳定主题骨架；
4. 当前 Scope 的代表知识和主要关系；
5. 重要未知、分歧或适用条件；
6. 最近高影响变化；
7. 独立的 Resume、阅读或提问入口。

### 首要动作

普通打开停留在 canonical Overview；Overview 的内容主动作指向 stable start，无策展时明确使用结构回退。只有显式`继续`意图才把上次焦点作为恢复目标。关系图是同步镜头，不抢占 Overview 的阅读主轴。

## 6.4 Change Overlay

### 首要状态句

> 有一项变化可能影响“具体对象”；当前其他内容仍可阅读。

### 默认内容顺序

1. 当前仍成立的稳定 Overview；
2. 变化摘要：发生了什么、影响哪里；
3. 受影响主题、知识、关系和 Saved Answers；
4. 新旧观点或结构 Diff；
5. 需要用户决定的少量高影响事项；
6. View current / View before change。

### 首要动作

理解变化，而不是被迫立刻“清空待处理”。用户可以先继续阅读，重要决定保持可返回。

## 6.5 Paused Reorientation

### 首要状态句

> 你曾暂停关注这个知识群。可以从上次位置继续，或先查看此后的重要变化。

### 默认内容顺序

1. 最后稳定 Overview；
2. 上次焦点和保存路径；
3. 暂停关注期间的高影响变化；
4. 当前来源和新鲜度说明；
5. 恢复正常关注、提问或保持暂停。

### 禁止

- 因未打开而显示负面评分；
- 把暂停关注等同于内容过期；
- 自动归档；
- 在 Library Resume 反复提醒“回来整理”。

## 6.6 Archived Read-only State

Archived 是 lifecycle state，不是 Orientation Profile 或 Attention Mode。

默认只读地保留：

- 归档时 Overview；
- 归档原因和时间；
- 历史结构、关系、来源和 Saved Paths；
- 被其他知识引用的位置；
- 恢复入口。

归档对象仍能解释历史引用，但默认不进入新的知识建议和主动维护队列。

---

# 7. Knowledge Library Resume 的产品定义

## 7.1 Resume 不是独立首页或仪表盘

Knowledge Library 中的 Resume region 只需要帮助用户完成三个任务：

1. 找到要进入的知识群；
2. 恢复最近的理解路径；
3. 看见少量真正影响知识的变化。

## 7.2 默认结构

1. Groups / Network 模式切换与当前 Library scope；
2. 可选的一条 Resume：只恢复最近安全现场，必须显式`继续`；
3. 少量 Pins：用户主动设置的快捷入口；
4. All Groups catalog：页面主体，使用稳定排序与 Saved Group Views；
5. Paths / Views / All Knowledge：次级浏览能力；
6. 最多一条 contextual notice：只说明真正影响当前理解的变化；
7. Search / Ask / Add：安静但随处可用的动作。

普通启动恢复 Library catalog state，不自动打开 deep Reading。普通点击 Group 进入 canonical Overview；新窗口进入独立 Stable Library；不安全现场只恢复 nearest safe reading fallback 并提供 repair。Recent、Pin、Saved Path 与 Resume 不合并为“最近内容”流，也不参与 Group catalog 的重要性排序。

## 7.3 状态配置如何影响 Library Resume

| 条件 | Library catalog / Resume 表现 |
|---|---|
| Bare | catalog 中正常存在；只有留下 safe checkpoint 时才可成为单条 Resume，不因空白长期占据顶部 |
| Structuring | catalog 显示真实边界与主要方向，不显示完成度；Resume 仍只由 safe checkpoint 决定 |
| Oriented | 以名称、边界与稳定入口呈现，不因 Profile 获得更高排序 |
| Changes available / review due | catalog 顺序不变；必要时用一条 contextual notice 说明具体高影响变化，不用红点排名 |
| Paused | 保留在可搜索 catalog / View；默认不主动竞争 Resume，除非用户显式进入并形成 safe checkpoint |
| Archived | 进入 Archived View，不进入默认 catalog 或 Resume |
| Trash | 只进入 Trash，不出现在 Search / Ask / Network / Resume |

## 7.4 明确不做

- 每日知识报告；
- 连续使用天数；
- 节点和来源增长数字；
- AI 自动处理流水；
- 为保持活跃而生成的推荐内容；
- 以“待整理”制造负担；
- 把项目任务列表混入所有知识群。

---

# 8. AI 主动性的分级决策

## 8.1 总原则

> **AI 可以主动观察、解释和建议；越接近改变知识身份、边界和正式结构，越需要用户确认。**

## 8.2 四级主动性

| 级别 | 行为 | 默认规则 |
|---|---|---|
| A0 读取辅助 | 索引、OCR、语言识别、搜索向量、格式解析 | 可自动，失败可见 |
| A1 低风险派生 | 候选关键词、局部摘要、未保存预览、临时聚焦 | 可自动生成，不进入 Knowledge Truth |
| A2 结构建议 | 候选主题、群归属、关系、重复、Overview Diff | 建议 + 理由 + 接受/修改/忽略 |
| A3 正式变更 | Topic Promotion、Group Absorb / Merge / Split，改变 canonical knowledge、正式关系、边界或 lifecycle | 必须预览并确认；身份与结构变换不允许由后台自动规则静默完成 |

## 8.3 禁止静默发生的事

- 批量创建知识群；
- 把 embedding 相似升级为正式关系；
- 覆盖用户拥有或锁定的 Overview；
- 合并、拆分或删除 canonical knowledge；
- 把用户写作改写成模型版本；
- 因来源失效改变 lifecycle；
- 自动把一次 AI 回答写成 Accepted Knowledge；
- 为了显得完整而把 Structuring 内容自动写成 Oriented Presentation，并隐藏真实覆盖不足；
- 把 Topic 因内容多自动提升为 Group，或把 Group 静默降级 / 并入另一个 Group；
- 同时维护独立 Group Membership 与 Placement，或用 Subgroup 代替清楚的 Group / Topic 边界。

---

# 9. 手工知识与 AI 知识的关系

## 9.1 不设比例目标

**[产品决策] 不规定“手工 30%、AI 70%”之类的目标。**

比例会随知识群而变化：

- 研究型群可能由大量来源和 AI 编译启动；
- 实践型群可能主要是用户经验、原则和反思；
- 项目型群可能同时包含决定、会议来源和 AI 综合；
- 生活问题域可能由外部规则、个人条件和行动经验共同构成。

产品只要求来源和形成方式清楚，而不是偏袒一种写作方式。

## 9.2 一套知识模型

用户写下、AI 综合和来源提取的知识共享：

- 相同的 Node identity；
- 相同的 Topic 与 Placement 机制；
- 相同的 Relation 模型；
- 相同的 History 与版本；
- 不同但清楚的 origin、author、形成活动，以及仅在被用作依据时出现的 Evidence Binding / 五轴 provenance。

AI 生成不是二等知识，用户手写也不需要伪造外部证据。二者的可信方式不同，但都可被拥有、修订和引用。

---

# 10. 白板、地图与层级的边界

## 10.1 核心产品不引入自由白板

**[产品决策] 稳定层级与稳定关系地图属于产品本体；自由摆放卡片、无限画布和手工连线白板不属于核心。**

原因：

- 本产品的 canonical structure 必须可查询、可同步、可维护；
- 自由位置不等于知识关系；
- 白板容易把布局劳动重新交给用户；
- 多个个人白板会形成与 Library、Atlas 并行的第二套组织系统；
- 视觉表达不应改变 Node、Topic 和 Relation 的正式语义。

## 10.2 允许的派生视图

未来可以提供可保存的 Canvas / Study Board，但它必须是派生 View：

- 引用现有知识，不复制 canonical content；
- 手工位置只属于该 View；
- 连线默认是视觉注释，只有显式转换后才成为 Relation；
- 删除卡片只移出 View；
- View 不改变 Group 的正式层级；
- AI 可帮助布局，但不能把布局距离解释为知识事实。

因此“2 + 3”的视觉方向应结合稳定层级、正文与关系地图，不应被误解为必须引入无限白板。

---

# 11. Space、分享与协作的边界

## 11.1 默认一个连续 Space

一个用户默认只有一个个人 Knowledge Space，让跨群关系、搜索和 Ask 能自然成立。

只有以下硬隔离需求才创建额外 Space / Vault：

- 法律、客户或雇主边界；
- 不同设备或存储位置；
- 不允许跨边界发送给同一模型；
- 完全独立的备份、加密或同步策略。

“我想整理得更干净”不应成为创建 Space 的理由；这应由 Group、Topic、View 和过滤解决。

## 11.2 分享是派生能力

个人知识空间可以派生：

- 一个 Group 或 Saved Path 的只读发布；
- 带来源策略的阅读导出；
- 可移植 Knowledge Package；
- 用户明确选中内容的静态分享。

## 11.3 实时协作不是产品本体

首要产品不围绕：

- 多人同时编辑；
- 团队权限矩阵；
- 评论、提及和审批；
- 组织级 Wiki；
- 团队知识所有权。

未来若加入协作，必须先解决个人知识与共享知识的 identity、provenance、冲突和退出边界，不能简单把单用户编辑器加上头像。

---

# 12. 三个代表场景

## 12.1 认知科学：从 Bare 到 Oriented

### Bare

用户创建“认知科学”，写下问题：“记忆为什么依赖情境？”并添加两篇论文。

产品显示：

- 群边界尚简单；
- 一条用户问题、两份来源；
- 一个首要入口`写下第一条知识`，以及`建立主题 / 继续添加来源`两个安静替代。

### Structuring

系统发现“记忆系统”“检索线索”“情境依赖”三个候选方向，并解释每个方向由哪些知识和来源形成。

用户接受其中两个，合并一个过细候选。Overview 明确写出覆盖仍集中于记忆研究，不假装代表整个认知科学。

### Oriented

用户可从 Overview 进入主题，再进入 Claim、机制、实验限制和论文片段；也可沿“provides foundation for”跨到“AI Agent 产品设计”。

## 12.2 AI Agent 产品设计：用户知识与来源共同形成

这个群从用户自己的产品原则开始，而不是来源导入：

1. 用户写下“高风险动作必须可逆”；
2. 建立“人机控制”Topic；
3. 后续加入研究、竞品资料和真实 Case；
4. 同一 Node 被放入“AI 安全”群的另一个语境；
5. 用户建立正式跨群关系；
6. AI 建议更新 Overview，但保留用户拥有的核心表述。

该场景验证：手工知识不是 Capture 的例外，AI 也不是唯一知识生产者。

## 12.3 法国租房：Oriented + Change Overlay

群已经包含担保、合同、保险、补助和不同城市的流程。某官方规则更新后：

1. 系统不直接重写原结论；
2. 先比较适用地区、身份和日期；
3. Group 保持 Oriented，同时形成 `changes_available / review_due` 并显示具体变化影响；
4. 旧 Saved Answer 保留原知识快照；
5. 用户确认新适用条件后，Overview 和未来 Ask 更新；
6. 旧规则作为历史知识仍可核验。

该场景验证：变化不是新阶段或消息流，而是叠加在最后稳定理解上的可定位影响与历史。

---

# 13. 产品反目标

为了防止再次偏离知识库本体，以下方向明确拒绝：

1. **认知操作系统叙事膨胀**：不以替用户规划生活、执行任务或自动决策定义产品；
2. **聊天中心化**：不让所有入口都进入一条时间线；
3. **图谱景观化**：不以节点密度、星空效果和连线数量制造价值感；
4. **项目管理化**：项目是知识群类型，不把全部知识转成任务、状态和截止日期；
5. **整理游戏化**：不设置成熟度分数、连续签到和知识增长排行榜；
6. **来源中心化**：不把文件目录加 AI 摘要误称为知识库；
7. **全自动结构化**：不让 AI 静默重写用户知识世界；
8. **过度模板化**：不要求用户先选数据库模板或创建大量空属性；
9. **白板中心化**：不把卡片位置当作 canonical knowledge structure；
10. **协作先行**：不为团队场景牺牲个人知识的连续性和所有权。

---

# 14. 可验证验收标准

## 14.1 首次建立

**Given** 用户没有任何 Source  
**When** 新建一个知识群  
**Then**：

- 只输入名称即可进入；
- Group 使用 Bare Profile，但默认文案不要求理解内部状态；
- `写下第一条知识`是首要动作，`加资料`和`建主题`是安静替代；三项能力完整但不以同权 Hero 要求用户先选结构；
- 不展示空图谱、完成度或自动模板墙；
- 关闭再打开后，群身份、内容和位置保留。

补充验收：只建立 Empty Group 是合法且可返回的范围，但不冒充 First Returnable Asset；只有 Current Knowledge 或 Source-only Asset 形成后才达到首份可返回资产。Source 至少拥有 Sources 入口，选择 Group / Topic 时再建立 Attachment。Relation、Topic、AI、外部 Source、账号与同步均不得成为首次价值门槛。

## 14.2 十秒定位

**Given** 用户有多个不同状态配置的知识群  
**When** 打开 Knowledge Library  
**Then**：

- 十秒内能在稳定 catalog 中找到目标 Group；
- 最多一条 Resume 说明 exact position，且只有显式`继续`才恢复；
- 高影响变化使用 contextual notice，不重排 catalog 或冒充 Resume；
- Paused 和 Archived 不制造 Resume 噪声；
- 页面不以统计、任务或 AI 活动为主。

## 14.3 两分钟恢复

**Given** 用户一个月未打开“法国租房”  
**When** 重新进入  
**Then**：

- 先看到最后稳定 Overview；
- 上次焦点可恢复；
- 暂停关注期间的变化与知识新鲜度分开表达；
- 用户可直接提问或继续阅读；
- 不被迫先处理 Review。

## 14.4 成形但不伪装成熟

**Given** 一个群只有少量相似材料  
**When** 系统识别候选主题  
**Then**：

- 主题以建议呈现；
- 每项说明形成依据；
- Overview 说明当前覆盖；
- 拒绝建议不删除来源和已有知识；
- 系统不显示完整度百分比。

## 14.5 Oriented Group 的低噪声阅读

**Given** 一个 Oriented Group 没有高影响变化  
**When** 用户进入  
**Then**：

- Overview、主题和 stable start 优先；上次焦点只通过显式 Continue 恢复；
- Orientation Profile 不成为显眼标签；
- 关系地图与层级围绕同一选择同步；
- 状态和来源细节按需一跳可达；
- 用户不需要先清理提醒或处理建议。

## 14.6 Change Overlay 不破坏历史

**Given** 新来源改变关键知识  
**When** Group 形成 `changes_available / review_due`  
**Then**：

- 原 Overview 仍可查看；
- 变化说明影响对象和适用条件；
- 旧 Saved Answers 不被重写；
- 用户可先阅读再决定；
- 确认后 affected owners 形成新 revision 或明确保持当前理解；Orientation 不被强制改变；
- 整个过程可撤销和核验。

## 14.7 AI 不可用

**Given** AI 服务不可用  
**When** 用户进入任一状态配置的 Group  
**Then**：

- Overview、层级、关系、状态依据和历史仍可读取；
- 用户仍可写知识、建主题和人工关系；
- 仅 AI 生成、Ask 和结构建议暂不可用；
- 已保存 Answer、Original / Re-evaluation 历史与 Claim citations 仍可查看；
- AI 失败不改变 Group state configuration 或 lifecycle。

## 14.8 Group identity 与状态配置分开

**Given** 一个 Topic 形成独立边界、独立使用意图和稳定内部结构  
**When** 系统建议“成为独立知识群”  
**Then**：

- 建议属于 A2，真正 Promotion 属于 A3；
- 新 Group 根据自身 accepted truth 解析 Orientation，不继承父 Group 或 Topic 的状态；
- 原 Topic 保留 Gateway、旧路径和历史 Overview；
- Placements 决定 Node 在两个 Groups 的成员关系，Node identity 不复制；
- 不接受建议时原 Group 与 Topic 完整可用。

## 14.9 Overview identity 与复合状态分开

**Given** 同一 Group 先后出现 Bare、Oriented、review_due、Paused 与 Archived 的组合  
**When** 用户查看 Overview history 与当前页面  
**Then**：

- 全程只有一个 `overview_id`；
- Orientation refresh 只记录 Presentation Profile 变化；
- Projection refresh 与 Editorial revision 在历史中分开；
- Change overlay 可以显示 `changes_available / review_due`，但 accepted prose 保持原样；
- Paused / Archived 恢复时回到同一 Overview 与可用的 last-safe reading position；
- 用户无需接受 AI prose 才能刷新 Orientation，也不会因 Profile 刷新自动接受正文。

---

# 15. 决策冻结表

| 未决问题 | 本轮决定 | 后续验证问题 |
|---|---|---|
| 首要用户偏研究、工作还是通用个人知识 | 按长期复杂知识工作定义；三者是内容场景，不是三个产品 | 哪类用户最早感到强价值、愿意迁入长期资料 |
| AI 多主动 | 低风险派生自动；结构建议可解释；正式高影响变化需确认 | 哪些 A1/A2 行为会被感到打扰或失控 |
| 自由白板还是稳定地图 | 核心采用稳定层级 + 稳定关系地图；白板仅可能是派生 View | 用户是否需要临时空间布局来支持综合思考 |
| 手工与 AI 知识比例 | 不设比例；共享同一知识模型并保留 origin | 不同 Group 类型的真实构成与编辑习惯 |
| 是否需要额外 Space | 默认一个；只为硬隔离创建 | 硬隔离出现频率与可理解性 |
| 协作、分享和发布 | 只读分享与导出可派生；实时协作不属于核心 | 个人知识在分享时需要怎样的脱敏、来源和更新边界 |
| Group 如何从空白长期演化 | Orientation、Change、Attention、Lifecycle 与 Boundary continuity 正交；不设单一 formation phase | 复合状态能否在不显示状态机的前提下被正确理解 |
| Library 默认入口应展示什么 | 一个克制 Resume + 稳定 Groups catalog；普通打开进入 Overview | 十秒定位、单条 Resume 与 unsafe repair 是否符合真实并行任务 |
| Group 与 Topic 如何分界 | Group 是独立知识范围；Topic 是群内单父结构；不设 Subgroup | 用户能否正确判断边界，Promotion 建议是否克制 |

---

# 16. 对下一阶段设计的约束

在用户选择视觉方向前，不创建组件化原型。选择后，第一批 Frame 也不能只展示一个内容充足、结构完美的 Oriented Group；至少必须同时验证：

1. Bare + Current：从空白开始且没有模板压力；
2. Oriented + no change：Overview、层级和关系的低噪声双镜；
3. Oriented + review_due：变化说明、历史与继续阅读共存；
4. Oriented + Paused + changes available：恢复上下文而不制造负面评分；
5. Archived + historical link：只读、引用与恢复；
6. Stable Library：多个复合状态同时存在时 catalog 仍有主权，单条 Resume 可预测且十秒内能定位。
7. 同一 Scope 下展开 Reading Depth 或 Relation Radius 时，另一个维度和当前位置不被重置；
8. Bare 时关系镜头退让不是隐藏能力；Oriented 与 change overlay 仍使用同一连接语法和忠实 Knowledge Route；
9. Topic Gateway、Group Boundary 与 Group Relation Inspector 在所有状态组合中保持同一语义；
10. 一个 Node 的成员关系只从 Placements 表达，视觉不再另建“成员”真相；
11. Bare / Structuring 不以“短内容不完整”催促扩写，Oriented 不以“长内容应原子化”自动拆卡；所有 Profiles 共享 Node / Block / Anchor 合同；
12. A2 可以建议 Section 成为独立知识或 Node Split / Merge；A3 提交前必须显示 identity、Anchor、Evidence、Placement、Relation 与历史影响。任何状态不能降低这条确认门槛；
13. Search、Ask 与继续阅读从 Anchor 恢复位置；Paused / Archived 内容移动后使用 redirect 或明确修复，不静默落到相似段落；
14. 所有复合状态使用同一个 Overview identity 和 content tree；视觉差异来自真实内容、Presentation 与至多一条 notice，不来自多份模板正文；
15. Projection refresh、Editorial Semantic Diff、alignment notice 与 state notice 在状态和历史中可分别识别。

“视觉 2 + 3 的结合”由此被解释为：

- 用方向 3 的层级和阅读连续性承担主轴；
- 用方向 2 的关系空间承担可切换或可调权重的探索镜头；
- 两者共享 Selection State；
- 在 Bare 时关系镜头主动退让，在 Oriented 时稳定可用，在 change overlay 中突出受影响路径；
- 不把三个并列面板固定成所有时刻相同权重。

---

## 结论

这款产品不应要求用户每天“经营一套系统”。它应当像一个长期可居住的知识空间：空的时候容易开始，成形时诚实表达不确定，稳定后安静地支持阅读和调用，变化时保留历史并解释影响，暂时离开后仍能自然回来。

> **Knowledge Group 不是一个装资料的容器，而是一个会从问题或材料中逐渐形成、可被理解、查询、探索、修正并长期拥有的知识范围。**
