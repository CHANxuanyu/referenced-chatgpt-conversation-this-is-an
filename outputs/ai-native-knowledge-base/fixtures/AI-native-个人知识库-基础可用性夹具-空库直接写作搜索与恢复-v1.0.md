# AI-native 个人知识库

## 基础可用性夹具 v1.0 — 空库、直接写作、Search、离线与恢复

> 文档日期：2026-08-10  
> 文档状态：**FIXTURE**；约束产品真实性，不新增 Canonical 产品真相  
> 产品真相源：`AI-native-个人知识库-终局产品设计文档-v6.0.md`  
> 目的：补足两份复杂研究夹具没有证明的基础路径  
> 当前阶段：只定义和验证产品；不修改 Ardot，不制作 Screen，不授权原型  

---

# 0. 为什么需要第三份夹具

前两份夹具已经证明产品可以承载：

- 真实 Group Overview 和三层 Topic；
- 时效、适用条件、来源变化和 Question；
- 同一 Knowledge 多 Placement；
- Knowledge / Group Relations；
- Ask scope、basis、coverage 与 atomic write-back；
- cross-group exploration 和 exact return。

但它们都从一个已经成熟、内容丰富的 Library 开始，无法证明一个更基本的问题：

> **如果用户没有 Group、没有 Source、没有 AI，只想写下一条自己的理解，这个产品是否已经成立？**

它们也没有完整证明 Search exact open、Source parse partial、offline direct edit、Knowledge Package export 与干净环境 restore。

本夹具专门覆盖这些基础责任。它使用合成的用户原创写作方法，不声称其中内容是外部研究事实，也不需要浏览或 AI 才能成立。

---

# 1. 合成情境与证据边界

## 1.1 用户情境

合成用户`P-WRITER-01`正在总结自己的非虚构写作方法。设备第一次安装产品，Library 完全为空。

用户脑中只有一个暂时判断：

> 写复杂文章时，先把核心判断写清楚，再决定哪些材料真正需要留下，比一开始堆满资料更容易保持论证方向。

这是用户原创经验，不需要 Source 才能成为 Knowledge；其 basis 显示为`用户直接写作`。

随后用户找到一份自己过去写的本地 Markdown 草稿，想把其中关于“结构修改与措辞修改分开”的一段保存为 Source，再选择性形成第二条 Knowledge。

## 1.2 不证明什么

本夹具不声称：

- 该写作方法对所有人有效；
- 它优于其他写作流程；
- 两条个人经验拥有研究证据；
- 一个 Group 足以证明大规模 Library Network；
- 导出格式已经被工程实现。

它只证明产品语义、路径、身份和失败边界是否完整。

---

# 2. 最小对象与状态

## 2.1 四类 canonical truth

| ID | Family | 内容 | 初始状态 |
|---|---|---|---|
| G-WRITE | Group | 个人非虚构写作方法 | 第 5 步才创建 |
| K-W1 | Knowledge | 先写判断，再决定保留哪些材料 | 第 2 步直接写作 |
| K-W2 | Knowledge | 结构修改与措辞修改应该分开进行 | 第 9 步由用户从 Source 形成 |
| R-W1 | Relation | K-W2 支持 K-W1 的修改顺序 | 第 10 步由用户直接声明 |
| S-W1 | Source | `旧写作草稿.md` | 第 7 步保存，首次解析 partial |

Topic 是 Group 内结构身份：

```text
G-WRITE 个人非虚构写作方法
├─ 01 形成判断
│  ├─ 核心命题
│  └─ 材料选择
└─ 02 修改文章
   ├─ 结构修改
   └─ 措辞修改
```

## 2.2 Supporting identities

| Identity | 责任 |
|---|---|
| K-W1 Revision r1 / r2 | 第一次写作与离线补充后的历史 |
| K-W1 Placement p1 | `G-WRITE / 形成判断 / 核心命题` |
| K-W2 Placement p2 | `G-WRITE / 修改文章 / 结构修改` |
| S-W1 Revision s1 | 原始本地 Markdown bytes / text snapshot |
| S-W1 Fragment f1 | 关于结构与措辞修改的原段落 |
| Binding b1 | f1 supports K-W2；不冒充 Relation |
| Anchor a1 | K-W1 正文中“材料只在承担论证责任时保留”段落 |
| Search result set sr1 | 查询现场；可重建，不进入导出 truth |
| Workspace checkpoint wc1 | 离线编辑现场；恢复后可清除 |

## 2.3 明确不存在的对象

- 没有自动建立的 Group Candidate；
- 没有“未归类 1 项”的红点任务；
- 没有 Source 要求；
- 没有 AI Candidate / confidence；
- 没有因 Search 同时命中 K-W1 / K-W2 产生的 Relation；
- 没有因同一 Group 就建立的 Group Relation；
- 没有把 Search result、offline checkpoint 或 parse chunk 提升为 Knowledge。

---

# 3. 两条真实 Knowledge Paper

## 3.1 K-W1 · 先写判断，再决定保留哪些材料

**Basis：** 用户直接写作。  
**Applicability：** 用户自己的复杂非虚构文章；不是通用写作定律。

```text
写复杂文章时，我需要先写出一句能够被反对的核心判断，
再判断每份材料到底承担解释、证据、例子还是限制的责任。

如果一开始只是堆资料，结构会被材料顺序牵着走；
当核心判断先出现，材料只在承担论证责任时保留，
其余内容可以继续留在来源里，而不必全部进入正文。
```

Anchor `a1`定位第二段第一句。它可以被 Search、Relation、Saved Path 或 Citation 使用，但不是独立 Knowledge。

## 3.2 K-W2 · 结构修改与措辞修改应该分开进行

**Basis：** 用户从自己的旧草稿 Source S-W1 中选择并重新表述。  
**Applicability：** 用户自己的长文修改流程。

```text
第一遍修改只检查判断顺序、段落责任和论证缺口，
不同时追求句子漂亮；第二遍再处理措辞、节奏和重复。

同时进行两种修改时，我容易因为一句话写得顺而保留
一个本应删除的段落，也容易把结构问题误判成表达问题。
```

S-W1 f1 是其来源依据，但 K-W2 是用户当前认可的独立 Knowledge，不是 Source 原文副本。

---

# 4. 十七步端到端旅程

## Step 1 · 空 Library

用户看到：

- 一句“这里会保存你可以再次进入的知识”；
- 首要动作`写第一条知识`；
- 安静替代`建知识群`、`添加资料`；
- Search / Ask / Add 可达；
- 没有 Dashboard、模板选择、AI feed 或 Graph 空宇宙。

## Step 2 · 直接写第一条 Knowledge

用户选择`写第一条知识`，输入 K-W1 标题和正文。系统本地保护 buffer，并通过安全 direct commit 建立 Current Revision r1。

不要求 Source、Group、Topic、Relation、type 或 Proposal。

## Step 3 · 返回 Library

因为 K-W1 尚无 Group / Topic Placement，Groups 视图在空 Catalog 下显示：

```text
独立知识
K-W1 · 先写判断，再决定保留哪些材料
```

没有红点、数量压力或“待整理”。用户可以再次打开同一 identity。

## Step 4 · Search exact Anchor

用户搜索`材料只在承担论证责任时保留`。

Search 显示：

- K-W1 title；
- 命中正文片段；
- path：`独立知识`；
- basis：用户直接写作；
- index state：complete for local current revision。

打开结果直接落到 Anchor a1。Back 恢复 query、result set、scroll、focus 和原 Library 现场。

## Step 5 · 创建 Bare Group

用户从 Add 创建 G-WRITE，只输入名称`个人非虚构写作方法`和可选 Boundary：

> 保存我反复使用、会继续修正的长文判断与修改方法；不承担写作任务和截稿管理。

Bare Group 立即进入 Catalog，可再次打开；它不因为没有 Topic / Overview 完整内容显示警告。

## Step 6 · 把 K-W1 放入 Group

用户从 K-W1 选择`放入知识群`，建立 p1：

```text
G-WRITE / 形成判断 / 核心命题
context: 这是决定文章方向和材料责任的起点。
```

K-W1 从`独立知识`区域消失，因为已经拥有 Group Placement；正文 identity 和 Revision 不变。

## Step 7 · 保存本地 Source

用户添加`旧写作草稿.md`。Source Commit 成功后立即显示`资料已保存`。

首次解析只得到前半文件，状态为`parse partial`：

- 原始文件 bytes / snapshot 已保存；
- 已解析文字可读；
- 后半部分稍后重试；
- 不创建 Knowledge、Proposal 或 Review item。

## Step 8 · Source Reader 精确检查

解析完成后，用户打开 S-W1，在 Source Reader 中选择 fragment f1。Reader 显示 original context、revision、locator 和`尚未被知识使用`。

关闭后返回 Source list 的同一位置。

## Step 9 · 从 Source 形成第二条 Knowledge

用户显式选择 f1 → `形成知识`，检查 K-W2 的用户重写版本、basis 和 Placement p2 后提交。

结果独立结算：

- S-W1 保持 Source；
- f1 → K-W2 建立 Evidence Binding b1；
- K-W2 成为 Current Knowledge；
- p2 放入`G-WRITE / 修改文章 / 结构修改`；
- 不自动更新 Overview 或创建 Relation。

## Step 10 · 用户直接建立 Relation

用户在 K-W2 选择 K-W1，并写：

> 把结构修改与措辞修改分开，可以帮助“先明确判断、再筛选材料”的流程在修改阶段不被局部表达打断。

R-W1 映射到 v6 `Support / Explain`意图。提交前回读 endpoints、direction、statement、applicability 和 basis。Graph edge 只是投影。

## Step 11 · 关系 List 与 Peek

K-W1 默认 Quiet。用户选择`查看相关知识`后，Peek 显示 R-W1 的完整句与 K-W2；List 可以完成 Inspect / Open / Back，不要求空间图。

## Step 12 · 离线直接编辑

设备离线。用户在 K-W1 增加一段适用限制：

> 对短消息或单一事实记录，我不需要先写完整核心判断。

系统建立 local checkpoint wc1 和 Current Revision r2；显示`已在本机保护，等待同步`。AI、Web 和远端 sync 不可用不阻止写作。

## Step 13 · 导出 Knowledge Package

用户导出。Manifest 至少列出：

```text
library_id
groups: G-WRITE
topics: stable ids + parent ids
knowledge: K-W1@r1/r2, K-W2@r1
placements: p1, p2
relations: R-W1 current revision
sources: S-W1@s1 + fragment f1 + binding b1
anchors: a1
redirects / tombstones: none
optional projections: omitted
```

Search index、embeddings、graph layout、sr1 和 wc1 不作为语义恢复前提。

## Step 14 · 干净环境 Restore

在一个没有旧 cache 和 layout 的新环境导入 Package：

- 两条 Knowledge 的 stable IDs 保持；
- K-W1 current 是 r2，r1 可查看；
- Topic hierarchy、p1 / p2、R-W1、S-W1 f1 / b1 恢复；
- Search index 可以重建；
- Relation Graph 没有布局时先使用 List；
- Library 打开 G-WRITE，不产生第二个 Home。

## Step 15 · 移除 Placement 不删除 Knowledge

用户从 G-WRITE 移除 p1。影响预览说明：

- K-W1 正文、Revisions、R-W1 和 Anchor a1 保留；
- K-W1 将重新出现在`独立知识`；
- G-WRITE Overview / structure projection 刷新；
- K-W2 和 p2 不受影响。

提交后 Search 仍命中同一 K-W1 identity。

## Step 16 · Archive 与恢复

用户 Archive K-W1：

- 默认 Graph / Search current results 隐藏；
- R-W1 显示一端 archived，不被自动删除；
- historical deep link 仍可解析；
- Restore 创建新的 current lifecycle event，不抹掉 Archive 记录；
- K-W1 回到`独立知识`。

## Step 17 · Archive Group 不制造独立知识洪水

用户先把 K-W1 重新 Placement 到 G-WRITE，再 Archive G-WRITE：

- p1 仍是 active Placement，只是 target Group 已 archived；
- K-W1 不出现在`独立知识`，避免整群内容突然涌回 Library；
- Search 可以命中 K-W1，并说明它当前位于 archived G-WRITE；
- Archived Groups 可打开原 Overview、Topic context 与 Placements；
- Restore G-WRITE 后，p1、K-W1 identity、R-W1 与历史保持不变。

若用户不是 Archive 而是 Delete G-WRITE，必须先逐类预览 Move、End Placement、Keep independent 或 Archive Knowledge，不能把所有 Placements 静默结束。

---

# 5. 失败与边界状态

## 5.1 Write failed

若 Step 2 commit 失败，buffer 与 recovery checkpoint 保留，Library 不显示假成功 Knowledge。用户可以重试或导出草稿文字。

## 5.2 Index partial

Search 说明`正在重建索引；当前结果可能不完整`，并保留 last good result。不能因为查询暂时 0 result 写成 K-W1 不存在。

## 5.3 Source parse failed

S-W1 Source Commit 仍成功；原文件可打开；形成 Knowledge 的动作等待用户重试解析或手动选择文字。

## 5.4 Graph unavailable

Relation List 完整显示 R-W1；Graph failure 不改变 Relation standing。

## 5.5 Offline sync conflict

若另一设备同时产生 K-W1 r3，产品显示 base、local r2、remote r3 和可合并范围；不会 invisible last-write-wins。用户的本地正文保持可导出。

## 5.6 Restore partial

若 optional projections 缺失，canonical content 仍恢复；若 S-W1 bytes 损坏但 fragment snapshot 可读，显示 Source unavailable / historical fragment，不删除 K-W2。

---

# 6. v6 Acceptance Coverage

| AC | 本夹具证明 |
|---|---|
| AC-01 | 空库默认 Stable Library，不进入 AI / Graph / Review |
| AC-02 | Groups / Network 共享同一 Group truth；Graph 不可用使用 List |
| AC-03 | Bare Group 合法 |
| AC-04 | Topic hierarchy 可建立；Search 可直接进入 Knowledge |
| AC-06 | 两条连续 Knowledge Paper |
| AC-08 | 移除 Placement 不删除 Knowledge |
| AC-09 | 普通直接写作无审批 |
| AC-10 | Anchor a1 经 Search、export、restore 保持 |
| AC-11 | R-W1 是完整 statement |
| AC-12 | Binding、Relation、Search route 分权 |
| AC-15 | Quiet → Peek；不自动打开 Graph |
| AC-16 | Relation List 正式等价 |
| AC-18 | Search exact open 与 Back 现场恢复 |
| AC-25 | Source parse failure 不撤销 Source Commit |
| AC-27 | Source 新 revision 不自动覆盖 K-W2 |
| AC-28 | Archive / restore 保留历史 |
| AC-29 | AI / index / graph unavailable 时继续读写 |
| AC-30 | 干净环境 export / restore 语义完整 |

本夹具不重复证明复杂 multi-Placement、Group Relation、Ask / Answer、Question Resolution 和跨群 Explore；这些由前两份夹具承担。

---

# 7. 对未来设计的证明责任

未来完整设计必须用本夹具证明：

1. 空库第一屏没有 Graph 空宇宙、AI Hero 或模板墙；
2. 第一条 Knowledge 无 Group 也能被稳定找回；
3. `独立知识`不是 Inbox、内容类型或待整理状态；
4. Search 命中正文 Anchor 并可精确返回；
5. Bare Group 与成熟 Group 使用同一 Shell；
6. Source Commit 与 Knowledge Commit 分开；
7. 用户原创 Knowledge 没有 citation 也合法；
8. 离线写作的本地保护、Current 与 sync 状态可区分；
9. Export / Restore 不依赖 Graph layout 和 AI index；
10. 移除 Placement、Archive Knowledge、Archive Group 和删除 Source 使用不同后果；
11. Archive Group 不把其全部 Knowledge 重新分类为独立知识。

这是一组产品和未来设计证明，不是新增十张页面的要求。
