# AI-native 个人知识库

## 真实端到端使用样例与设计数据夹具 v1.0

> 文档日期：2026-08-10  
> 文档性质：产品定义压力测试、真实内容夹具、未来设计证明输入；不是法律建议、用户画像、界面稿或原型授权  
> 主题快照：法国非欧盟留学生在 2026 年的私人租房申请、Visale 担保与个人住房补助  
> 外部事实截止：2026-08-10；任何金额、资格和程序都必须保留来源与 `as_of`，不得脱离适用条件复用  
> 领域真相源：产品本体遵守 `AI-native-个人知识库-终局产品设计文档-v6.0.md`；旧 Question lifecycle 合同只在与 v6 一致时作为候选深层规则，不拥有独立权威  
> 当前阶段：只定义和验证产品；不修改 Ardot，不制作新 Screen，不授权原型

---

# 0. 执行结论

## 0.1 这次不是“写一个漂亮案例”

这份夹具用一组可以被官方资料核验、又会随时间和个人情境变化的真实内容，检查产品能否完成同一件事：

> 用户先从一个知识群理解租房全貌，深入到材料与担保细节；再跨到另一个知识群理解住房补助；把一个与自身情境有关的未知保存为 Question；让 AI 在明确范围内回答；把回答中的稳定结论形成 Knowledge；把准确依据链接给 Question；采纳一份带日期和适用条件的当前回答；在规则或个人条件变化后看到“依据有变化”，检查影响，并重新追问，而不是让系统静默改写过去。

若产品只能生成一段答案、列一批文件或画一张关系图，这条旅程就没有成立。

## 0.2 真实内容暴露出的六个产品缺口

现有产品方向正确，但真实夹具证明还必须收紧六件事：

1. **Applicability 不能只是一段备注。** 高后果 Question 的 adopted Resolution 必须固定 `as_of`、地域、主体条件、关键假设与仍待机构确认的部分。
2. **规则判断与个体结果必须分层。** “官方页面写了什么”“按给定条件可以推断什么”“CAF 最终会怎样决定”不是同一种 Claim。
3. **变化触发源不只来自 Knowledge Revision。** 时间到达、官方来源更新、适用条件改变、用户情境改变和依据不可核验都可能要求复核。
4. **新页面不等于新真相。** Source Revision 或新增 Source 只能生成变化候选；它不能自动推翻旧 Knowledge 或 adopted Resolution。
5. **看似冲突的内容先检查时间与范围。** 2025 年的一般规则与 2026 年 7 月后的特定人群条件可以同时为真；只有在同一时间、同一对象、同一维度下不能并存，才是 `knowledge.contradicts`。
6. **跨群出口不等于群级关系。** 一条“签约后可以申请住房补助”的路径足以帮助探索，却不足以自动宣布“租房申请群”和“住房补助群”之间存在正式整体关系。

## 0.3 本夹具冻结的十二项决定

1. 本夹具使用虚构人物与情境，不声称记录用户本人。
2. 外部网页是 Source；经用户采用的可复用陈述才是 Knowledge。
3. 每条时效性事实都保存 `source_checked_at` 与适用时间，不把抓取时间当生效时间。
4. Question 的当前回答必须区分规则层、推断层和机构决定层。
5. 个人情境只按本次或该 Question 的 Applicability Snapshot 保存；默认不自动形成普通 Knowledge。
6. 情境改变形成 Question revision 或 review trigger；只有核心求知意图改变才建立 successor。
7. “可能符合某项例外”仍可被采纳为 provisional Resolution，但不能写成“已经获批”。
8. 一般规则被新条件收窄时，默认使用 `knowledge.qualifies`，而不是 `knowledge.contradicts`。
9. DossierFacile、Visale 与 CAF 是三个不同制度 / 服务；它们的材料、资格与流程不互相替代。
10. 从一个群进入另一群可以只是具体 Knowledge exit；正式 Group Relation 仍需独立门槛。
11. AI 可以提出变化影响、Resolution Proposal 与待核对条件，不能自动 resolve、conclude 或 reopen。
12. 未来 Screen 2 / 3 必须用本夹具的真实长标题、限定条件、异常状态和返回路径证明设计，而不是用抽象节点占位。

---

# 1. 证据边界与合成情境

## 1.1 合成用户情境

夹具人物 `P-LIN-01`：

| 字段 | 快照值 | standing |
|---|---|---|
| 身份 | 24 岁、非欧盟国家公民、在法国读高等教育 | synthetic runtime input |
| 居留 | 持标注“poursuite d’études”的有效长期签证或居留证 | synthetic runtime input |
| 住房 | 计划于 2026 年 8 月租住法国私人住宅，作为主要住所 | synthetic runtime input |
| 奖学金 | 没有 CROUS 或本夹具所涵盖的社会条件高教奖学金 | synthetic runtime input |
| 职业活动 v1 | 无雇佣、无自雇、无学徒或职业化合同 | synthetic runtime input |
| 职业活动 v2 | 后来开始一项申报的学生雇佣活动 | synthetic change input |
| 目的 | 准备租房材料、取得担保、判断是否可能申请个人住房补助 | synthetic decision context |

这些值只为了测试 Applicability。产品不应把它们包装成“已确认的用户事实”，也不应跨 Question 静默复用。若用户主动把某项个人信息保存为长期 Profile / Property Assertion，才获得独立 standing 和 revision history。

## 1.2 官方资料快照

| Source | 机构 | 本夹具只采用的内容 | 适用纪律 |
|---|---|---|---|
| S1 | Service-Public | 私人出租人 / 中介可要求的租客与担保人材料来自受限清单 | 法律说明；保留核验日期 |
| S2 | DossierFacile | 租房 dossier 的材料类别、签约人材料、担保非强制、DossierFacile 不发 Visale 证书 | 服务操作说明 |
| S3 | DossierFacile | 未取得最终机构担保证明时，可暂时移除该栏目，不阻塞 dossier 验证，之后再补 | 服务操作说明 |
| S4 | Visale | 18–30 岁等基本资格、学生及非欧盟学生材料条件、学生租金档位 | 动态资格；必须 `as_of` |
| S5 | Visale / ANIL | Visale visa 和担保合同应先于受担保租约签署，并在签约时有效 | 程序依赖 |
| S6 | CAF | 个人住房补助的一般条件、资源计算、搬家后新申请、个人情境变化需要申报 | 一般规则与操作说明 |
| S7 | CAF | 2026-07-01 起，部分持“poursuite d’études”居留的非欧盟学生需要符合指定奖学金条件；职业活动等情形仍列为可保留资格的例外 | 有明确生效日期与人群边界 |

十八个 Source Fragments 的分配为：S1 四段（租客类别、担保人类别、非许可材料后果、翻译 / 欧元要求）；S2 三段（签约人材料、担保非强制、不签发 Visale）；S3 一段（暂时移除机构担保栏目）；S4 三段（年龄入口、学生证明、非欧盟居留与住房条件）；S5 两段（申请 / 担保合同顺序、签约有效期）；S6 三段（资源与计算、情境变化、搬家后新申请）；S7 两段（2026 新条件、列明例外）。每段必须保存 locator、Source Revision 与核验时间，不能只保存网页 URL。

### Source registry URLs

- S1：[Service-Public · Futur locataire d'un logement privé : justificatifs à donner au propriétaire](https://www.service-public.fr/particuliers/vosdroits/F1169)
- S2：[DossierFacile · Liste des documents à fournir](https://aide.dossierfacile.logement.gouv.fr/fr/article/liste-des-documents-a-fournir-scnv25/)
- S3：[DossierFacile · Organisme garant](https://aide.dossierfacile.logement.gouv.fr/fr/article/organisme-garant-1ne3cvn/)
- S4：[Visale · Locataire de 30 ans ou moins, suis-je éligible ?](https://www.visale.fr/vos-questions/faq-locataires/locataire-de-30-ans-ou-moins-suis-je-eligible/) 与 [Visale · Éligibilité locataires](https://www.visale.fr/visale-pour-les-locataires/eligibilite/)
- S5：[Visale · Éligibilité bailleurs](https://www.visale.fr/visale-pour-les-bailleurs/eligibilite/) 与 [ANIL · Caution locataire et garanties de location](https://www.anil.org/votre-besoin/louer/trouver-un-logement/caution-et-garanties/)
- S6：[CAF · Foire aux questions logement](https://www.caf.fr/allocataires/foire-aux-questions/logement)
- S7：[CAF · APL : ce qui change pour certains étudiants à partir du 1er juillet 2026](https://www.caf.fr/allocataires/actualites/actualites-nationales/apl-ce-qui-change-pour-certains-etudiants-partir-du-1er-juillet-2026)

## 1.3 研究事实、产品决定、待确认结果分开

### 已核验的外部事实

- DossierFacile 明确说明担保人不是必填项，也明确说明它不签发 Visale 证明；申请人需要直接向 Visale 申请。
- DossierFacile 明确说明，若最终机构担保证明尚未取得，可以暂时删除该栏目，避免 dossier 验证被阻塞，之后再加入。
- Visale 当前说明 18–30 岁申请人是其覆盖人群之一；学生、非欧盟学生和住房本身另有材料与条件。
- Visale / ANIL 的程序说明要求先取得相关 Visale 文件和担保合同，再签署由其担保的租约。
- CAF 于 2026-07-03 发布的页面明确写出：从 2026-07-01 起，部分持“poursuite d’études”长期签证或居留证的非欧盟学生，须满足所述奖学金条件才能取得个人住房补助；职业活动、学徒 / 职业化合同、难民、无国籍者和相应配偶等被列为仍可符合的情形。
- CAF 的一般 FAQ 说明，职业、家庭或地址变化可能改变补助；搬家并签署新租约后需要重新申请。

### 本产品做出的解释

- “职业活动例外”只支持“可能仍符合规则层资格”，不等于具体个案已被 CAF 批准。
- 2026-07-01 前的一般学生说明与之后的特定人群条件，首先是时间 / Applicability 上的限定，不自动构成 contradiction。
- DossierFacile 可先验证材料与 Visale 必须在签约前完成并不矛盾：两者约束的是不同阶段。

### 仍需真实机构结果确认

- 合成人物在某一具体住房、收入、家庭与居留状态下最终是否获得 APL、ALS 或 ALF；
- 一项具体学生工作是否满足当时 CAF 所适用的“activité professionnelle”判断；
- 某一住房与租金是否通过 Visale 的最终资格检查；
- 具体出租人是否接受 DossierFacile、Visale 或其他担保组合。

---

# 2. 夹具对象总表

## 2.1 Canonical knowledge inventory

本表只列出 Groups 与 Knowledge 内容，便于快速看懂主题结构；它不是 v6 的本体优先级。Sources 与 Relations 同样属于 canonical truth families，Questions 是一种 Knowledge role，而 Topic、Placement、Fragment、Resolution 等承担结构或支持身份。

| ID | 类型 | 标题 | 当前放置 |
|---|---|---|---|
| G-RENT | Group | 法国私人租房申请 | Library / 生活在法国 |
| G-AID | Group | 法国住房补助与资格 | Library / 生活在法国 |
| K-R1 | Knowledge | 房东可要求的租房材料受法定清单限制 | G-RENT / 准备租房材料 |
| K-R2 | Knowledge | DossierFacile 整理和验证租房 dossier，但不签发 Visale | G-RENT / 准备租房材料 |
| K-R3 | Knowledge | 未取得最终 Visale 证明时，DossierFacile 可先不提交该栏目 | G-RENT / 准备租房材料 / 担保材料 |
| K-R4 | Knowledge | 18–30 岁申请 Visale 仍需满足身份、学生与住房条件 | G-RENT / Visale 担保 |
| K-R5 | Knowledge | 使用 Visale 担保的租约必须在相应文件有效时按顺序签署 | G-RENT / Visale 担保 / 签约顺序 |
| K-A1 | Knowledge | 个人住房补助取决于住房、家庭、资源与个人状态 | G-AID / 资格框架 |
| K-A2 | Knowledge | 2026-07-01 起部分非欧盟学生住房补助资格增加特定条件 | G-AID / 学生适用条件 / 2026 变化 |
| K-A3 | Knowledge | 职业活动等情形是 2026 新条件下列明的例外 | G-AID / 学生适用条件 / 例外 |
| K-A4 | Knowledge | 搬家并签署新租约后需重新申请个人住房补助 | G-AID / 申请时点 |
| K-A5 | Knowledge | 规则层判断不能替代 CAF 对具体个案的决定 | G-AID / 资格框架 |
| Q-A1 | Question Knowledge | 无奖学金且无职业活动的非欧盟学生，2026 年 8 月能否申请个人住房补助？ | G-AID / 学生适用条件 |
| Q-R1 | Question Knowledge | 租房 dossier 是否必须等 Visale 最终证明后才能提交 DossierFacile？ | G-RENT / 准备租房材料 |

## 2.2 其他 canonical truth 与 supporting records

| 类型 | 数量 | v6 身份 | 主要作用 |
|---|---:|---|---|
| Topic identities | 23 | Group 内稳定结构身份 | 两个 Groups 的丰富层级与递归 Overview |
| Source identities | 7 | canonical Source | 保存官方材料及 revision |
| Source fragments | 18 | Source supporting identity | 精确支撑 Claim / Relation / Answer |
| Placements | 12 | Knowledge / Scope supporting identity | 十条 Knowledge 与两条 Question 的当前主要放置；不复制正文 |
| Knowledge relations | 7 | canonical Relation | 稳定语义；不含 target / basis / provenance |
| Cross-group exits | 2 | derived observation | 从具体 Knowledge 进入相邻群；不自动成为 Group edge |
| Question target revisions | 10 | Question Knowledge supporting identity | Q-A1 与 Q-R1 的当前目标，说明 Question 关于什么 |
| Resolution criteria | 12 | Question Knowledge supporting identity | Q-A1 八项、Q-R1 四项，说明怎样算回答 |
| Answer snapshots | 4 | Query history artifact | 保留运行时回答，不自动形成 Knowledge |
| Resolution proposals | 3 | affected Knowledge proposal | Q-A1 v1 / v2 与 Q-R1 的候选采用记录 |
| Adopted resolution revisions | 3 | Question Knowledge revision | RR-A1、RR-A2、RR-R1 的当前 / 历史回答与准确依据 |
| Lifecycle events | 10 | History | 两条 Question 的 created、adopt、conclude、change 与 reopen 历史 |

## 2.3 明确不存在的对象

本夹具不创建：

- “DossierFacile 和 Visale 相关”这种 `related_to` 边；
- Question → Target 的普通 Relation；
- Source → Knowledge 的 `knowledge.derived_from` 边来替代 provenance；
- Ask 本次共同引用形成的 Knowledge ↔ Knowledge 边；
- 仅因两条跨群路径而自动生成的 Group Relation；
- 自动任务、截止日或“待处理 11 项”收件箱；
- 自动保存的个人职业或居留 Profile；
- 把 2026 新条件当作对所有学生、所有补助和所有时间的永久真理。

---

# 3. 两个知识群与 Overview 层级

## 3.1 G-RENT：法国私人租房申请

### Boundary

**Governing question：** 为在法国私人住宅签约，申请人需要怎样准备可接受、可验证且顺序正确的材料与担保？

**Includes：**

- 出租人可要求的材料范围；
- DossierFacile 的材料整理与验证；
- 个人 / 机构担保；
- Visale 基本资格与签约顺序；
- 从准备材料到签约的必要前提。

**Excludes：**

- 房源推荐与搜索排名；
- 具体房东的主观偏好；
- 房屋质量争议和入住后纠纷；
- 住房补助金额计算；
- 一般移民身份知识。

### Topic tree

```text
法国私人租房申请
├── 01 准备租房材料
│   ├── 合法可要求的材料
│   ├── DossierFacile
│   └── 担保材料
├── 02 Visale 担保
│   ├── 谁可能符合
│   ├── 住房与租金条件
│   └── 签约顺序
└── 03 签约与下一步
    ├── 租约完成
    └── 进入住房补助申请 ↗
```

### Group Overview 的实际内容

**一句话：** 私人租房申请不是“上传所有资料”，而是先在合法范围内形成租客 dossier，按所选担保方式补齐条件，再在担保文件有效时签约。

**理解主干：**

1. 先知道出租人依法可以要求哪些类别的材料；
2. 用 DossierFacile 整理和验证签约人的材料，但不要把它当作 Visale 申请入口；
3. 担保人不是 DossierFacile dossier 的绝对前置条件；
4. 若选择 Visale，资格、住房、租金与签约顺序分别需要核对；
5. 租约签署后，住房补助成为一条独立的跨群路径。

**关键问题：**

- `Q-R1 · 已充分回答 · 已停止追问`：是否必须等 Visale 最终证明后才能提交 DossierFacile？

**跨群出口：**

- `已签署新租约 → 住房补助 / 申请时点`；
- `CAF 模拟结果可以作为部分租房资源材料 → 住房补助 / 资格框架`。

Group Overview 不直接展示两个 Groups 的正式边；它只展示用户能理解和进入的具体出口。

## 3.2 G-AID：法国住房补助与资格

### Boundary

**Governing question：** 在法国居住的人怎样理解个人住房补助的资格、适用条件、申请时点与变化影响？

**Includes：**

- APL / ALS / ALF 的共同资格框架；
- 学生与非欧盟学生的适用条件；
- 奖学金、职业活动等限定；
- 搬家、签约、申报变化与重新申请；
- 规则层判断和个案结果的边界。

**Excludes：**

- 把模拟金额当正式批准；
- 租房 dossier 的完整材料清单；
- Visale 的最终签约流程；
- 税务、签证和奖学金制度的完整知识。

### Topic tree

```text
法国住房补助与资格
├── 01 资格框架
│   ├── 住房与家庭条件
│   ├── 资源与计算
│   └── 规则判断和个案决定
├── 02 学生适用条件
│   ├── 一般学生条件
│   ├── 2026-07-01 变化
│   └── 职业活动等例外
└── 03 申请与持续资格
    ├── 签约后的申请
    ├── 搬家后重新申请
    └── 情境变化与复核
```

### Group Overview 的实际内容

**一句话：** 住房补助不是一个静态“学生可 / 不可”的标签；它由住房、家庭、资源、身份和时间共同决定，并以 CAF 对具体申请的处理为最终操作结果。

**理解主干：**

1. 先建立一般资格框架；
2. 再按时间与主体条件读取学生规则；
3. 2026-07-01 后，部分非欧盟学生的规则需要增加奖学金或例外条件；
4. “存在职业活动例外”不等于每个学生工作都会自动获批；
5. 签署新租约后申请，之后的职业、家庭或地址变化还需重新判断。

**关键问题：**

- `Q-A1 · 暂时可用 · 依据有变化 · 已停止追问`：无奖学金且无职业活动的非欧盟学生，2026 年 8 月能否申请？

这里必须同时显示 adopted Resolution 的 `as_of` 和变化原因；不能只给一个绿色“已回答”。

---

# 4. 十条 Knowledge Paper

每条 Paper 都应从 L0 一句话进入 L1 概览、L2 机制 / 条件、L3 例外与 L4 Evidence。正文保持连续阅读，不拆成卡片堆。

## K-R1 房东可要求的租房材料受法定清单限制

- **Core claim：** 私人出租人或中介不能任意扩展申请材料；租客和担保人的合法材料类别由公开规则限定。
- **Applicability：** 法国私人住宅未来租客及其担保材料；`as_of 2026-08-10`。
- **Important detail：** 租客材料通常围绕身份、居住、职业与资源；担保人的许可清单另有区别。
- **Limitation：** 合法可要求不等于每个出租人都会要求清单中的所有材料。
- **Evidence：** S1 的相应清单与违法索取材料的说明。

## K-R2 DossierFacile 整理和验证 dossier，但不签发 Visale

- **Core claim：** DossierFacile 帮助签约人整理、验证并分享租房材料；它不是房源平台，也不是 Visale 证书签发机构。
- **Applicability：** 使用 DossierFacile 准备法国租房 dossier 的申请人。
- **Important detail：** dossier 中应放未来租约签署人的材料；他人的材料只应进入担保人部分。
- **Limitation：** DossierFacile 验证不等于出租人必然接受，也不等于取得住房或担保。
- **Evidence：** S2。

## K-R3 未取得最终 Visale 证明时，DossierFacile 可先不提交该栏目

- **Core claim：** 尚未收到最终机构担保证明时，可以暂时移除“机构担保”栏目，使 DossierFacile 先完成验证，之后再补证书。
- **Applicability：** 已选择机构担保、但最终证明尚未取得的 DossierFacile 流程。
- **Important detail：** 这是对 dossier 验证顺序的说明，不是对最终签约条件的豁免。
- **Evidence：** S3。

## K-R4 18–30 岁申请 Visale 仍需满足身份、学生与住房条件

- **Core claim：** 年龄 18–30 岁是当前 Visale 覆盖入口之一，但实际申请仍需要有效身份证明；学生需要法国高等教育注册证明，非欧盟学生还需适用的有效居留材料；住房也要满足主要住所、租约、租金和适居条件。
- **Applicability：** `as_of 2026-08-10` 的 Visale 公开规则。
- **Limitation：** 页面资格说明不等于 Action Logement 已向某个申请人发放 visa。
- **Evidence：** S4。

## K-R5 使用 Visale 担保的租约必须按顺序签署

- **Core claim：** 若租约依赖 Visale，申请人先取得 visa，出租人再取得担保合同，租约在相关文件有效期内签署。
- **Dependency dimension：** procedure / validity。
- **Missing consequence：** 若先签租约或文件失效，不能假设该租约已获得 Visale 覆盖。
- **Evidence：** S5。

## K-A1 个人住房补助取决于多个条件

- **Core claim：** 个人住房补助的资格与金额取决于住房、家庭、资源、租金、地点与个人状态；一般学生说明不能独自回答特定非欧盟学生在某一日期的资格。
- **Applicability：** CAF 一般框架；具体 aid type 与个人条件仍需核对。
- **Evidence：** S6。

## K-A2 2026-07-01 起部分非欧盟学生资格增加条件

- **Core claim：** 从 2026-07-01 起，CAF 对部分持“poursuite d’études”长期签证 / 居留证的非欧盟学生规定了新的个人住房补助条件；在该范围内，页面要求取得其列明的社会条件高教奖学金。
- **Applicability：** 指定身份、人群与生效时间；不扩展到 EU / EEA / 瑞士学生或页面列明的例外。
- **Temporal standing：** current as of 2026-08-10。
- **Evidence：** S7。

## K-A3 职业活动等情形是新条件下列明的例外

- **Core claim：** CAF 页面将受雇或自雇的学生、学徒 / 职业化合同、难民、无国籍者及相应配偶等列为仍可符合的情形。
- **Applicability：** 同 S7 的制度范围和时间。
- **Limitation：** “列为例外”只支持规则层判断；具体活动、收入和申请资料是否满足要求仍待个案处理。
- **Evidence：** S7。

## K-A4 搬家并签署新租约后需重新申请

- **Core claim：** 搬家后住房补助不会作为同一金额自动延续；签署新租约后需为新住房提交新申请。
- **Applicability：** CAF 住房补助申请流程。
- **Evidence：** S6。

## K-A5 规则层判断不能替代 CAF 个案决定

- **Core claim：** 官方公开规则允许用户判断“明显不符合”“可能符合某项路径”或“仍缺条件”，但最终 operational outcome 依赖完整个人与住房信息以及 CAF 对申请的处理。
- **Standing：** 用户写作并采用的解释性 Knowledge；不是 CAF 原文的逐字转述。
- **Basis：** K-A1、K-A2、K-A3 与 S6 / S7。

---

# 5. Relation 与 Non-relation Registry

## 5.1 采用的七条 Knowledge Relations

下表中的精确 `type` 名称是夹具表达，不冻结 v6 的默认关系注册表：R1 映射到 `Apply / Implement` 意图族，R2 与 R4–R7 映射到 `Challenge / Qualify`，R3 映射到 `Support / Explain`。对用户真正具有权威性的仍是完整 statement、方向、适用范围与依据。

| ID | Canonical statement | 类型 | Qualifier / bridge |
|---|---|---|---|
| R1 | K-R2 implements K-R1 | `knowledge.implements` | DossierFacile 的材料结构把法定许可类别变成可验证 dossier 流程；不表示它是执法机关 |
| R2 | K-R3 qualifies K-R2 | `knowledge.qualifies` | “整理完整 dossier”不要求在初次验证时已经拥有最终机构担保证明 |
| R3 | K-R5 depends_on K-R4 | `knowledge.depends_on` | dependent 是“获得 Visale 覆盖的签约”；prerequisite 是申请人与住房通过相应资格并持有效文件 |
| R4 | K-A2 qualifies K-A1 | `knowledge.qualifies` | 对 2026-07-01 后特定非欧盟学生增加更窄条件 |
| R5 | K-A3 qualifies K-A2 | `knowledge.qualifies` | 列明的职业与身份情形缩小 K-A2 的排除范围 |
| R6 | K-A4 qualifies K-A1 | `knowledge.qualifies` | 一般资格框架还要加上搬家、签署新租约与重新申请的时点条件 |
| R7 | K-A5 qualifies K-A1 | `knowledge.qualifies` | 一般公开规则支持资格判断，但不能单独承诺机构对具体申请的 operational outcome |

Q-A1 不作为这七条 ordinary Relations 的 endpoint。K-A5 可以成为它的 Answer basis；只有 Question Paper 中另有一条具有独立稳定语义、可作为 Claim Knowledge 处理的答案，才可能建立正式 semantic relation。系统不应为了在图上连接 Question 而把 basis 或 target 伪装成 Relation。

## 5.2 明确拒绝的假关系

| 候选 | 拒绝原因 | 正确对象 |
|---|---|---|
| DossierFacile `related_to` Visale | 意义含糊；只是流程中相邻 | ReferenceLink / Topic adjacency |
| S7 `derived_from` K-A2 | 方向与对象错误；Source provenance 不是 Knowledge Relation | EvidenceBinding / provenance |
| Q-A1 `uncertain_about` K-A2 | Question target 不进入 ordinary registry | QuestionTargetReference |
| 旧一般规则 `contradicts` K-A2 | 时间、人群和范围未对齐 | `qualifies` + validity / Applicability |
| K-R5 `causes` K-A4 | 签约先于申请，不等于因果充分 | `depends_on` 或 cross-group exit |
| G-RENT `related_to` G-AID | 群级不存在此正式类型，也未通过充分性门槛 | 两条具体 cross-group exits |
| K-A2 `supersedes` K-A1 | 一般框架仍成立；新规则只是特定限定 | `qualifies` |

## 5.3 跨群出口

### Exit E1：从签约进入住房补助申请

```text
G-RENT / 签约与下一步 / 已签署新租约
  → K-A4 搬家并签署新租约后需重新申请住房补助
  → G-AID / 申请与持续资格
```

### Exit E2：从租房资源材料进入补助模拟

```text
K-R1 / 资源材料 / CAF 住房补助模拟可作为许可材料之一
  → K-A1 个人住房补助取决于多个条件
  → G-AID / 资格框架
```

两个 exits 为用户提供连续探索，却不会被计为“两个群整体之间已经存在某种 maintained relation”。若用户以后认为两群共同组成“获得和负担住房”的完整范围，可以显式创建并审阅一条“二者共同构成完整范围”的 Group Relation Candidate；`group.complements` 只保留为实验性类型标签，当前夹具既不替用户做判断，也不把它写进 v6 默认注册表。

---

# 6. Question Q-A1：从未知到当前回答

## 6.1 QuestionFrameRevision v1

**问题：** 持有效“poursuite d’études”学生居留、非欧盟、没有所述社会条件奖学金、没有职业活动的学生，2026 年 8 月能否申请法国个人住房补助？

**Why it matters：** 估算住房预算，并判断是否应把预期补助写入租房财务计划。

**Applicability：**

```text
as_of = 2026-08-10
decision_period = 2026-08
jurisdiction = France
subject = synthetic P-LIN-01
residence_mark = poursuite d’études
nationality_scope = non-EU / non-EEA / non-Swiss
scholarship = none of stated eligible social-criteria scholarships
professional_activity = none
housing = future private principal residence; exact lease not yet signed
aid_scope = aides personnelles au logement; exact APL / ALS / ALF not yet determined
```

**Excluded interpretations：**

- 不问 Visale 资格；
- 不问最终金额；
- 不把网页判断当 CAF 已批准；
- 不覆盖 EU / EEA / Swiss students；
- 不覆盖难民、无国籍者、相应配偶、职业活动或 apprenticeship 情形。

## 6.2 Targets

| target | role | uncertainty |
|---|---|---|
| G-AID | about_scope | applicability_missing |
| K-A1 | tests_applicability_of | applicability_missing |
| K-A2 | tests_applicability_of | disputed_claim |
| K-A3 | seeks_fact_about | unknown_fact |
| S7 exact fragment | seeks_evidence_for | missing_evidence |

这些是 QuestionTargetReference，不进入 ordinary Relation counts。

## 6.3 Resolution Criteria

| ID | Required | 怎样算满足 |
|---|---:|---|
| C1 time | yes | 明确使用 2026-07-01 后适用规则 |
| C2 population | yes | 明确非 EU / EEA / Swiss 及居留标注 |
| C3 scholarship | yes | 核对是否属于页面接受的奖学金 |
| C4 activity | yes | 核对职业活动 / apprenticeship 等例外 |
| C5 aid scope | yes | 不把 APL 一词误当全部个人住房补助 |
| C6 operational limit | yes | 明确规则推断不等于 CAF 批准或金额 |
| C7 current official basis | yes | 至少使用当前 CAF 官方页面及 exact fragment |
| C8 next verification | no | 给出 simulator / actual application 的可选下一步，不变成任务债务 |

## 6.4 Ask Run A1：只有一般资料时

### Requested Context

- Q-A1 current revision；
- G-AID / 资格框架；
- K-A1；
- external research off。

### Effective Context

同 Requested Context；当前 Library 尚无 S7 / K-A2 / K-A3。

### Answer

> 现有个人知识只能说明住房补助取决于个人、住房与资源条件，不能判断这个 2026 年 8 月的非欧盟学生情境。还缺：2026 年 7 月后的官方规则、奖学金条件和职业活动例外。

### Outcome

- 生成 Runtime Unknown 3 项；
- 不创建 3 个 Question；
- Q-A1 保持 `unresolved + active + no_material_change`；
- 可选动作：加入官方资料、允许本次外部研究、补充条件。

## 6.5 Ask Run A2：按次允许外部官方资料

### Requested Context

- Q-A1；
- current G-AID Knowledge；
- 本次允许外部资料，优先官方机构；
- 不允许把外部结果自动写入 Library。

### Used Context Receipt

| Claim | Basis | Role |
|---|---|---|
| 2026-07-01 后特定人群新增条件 | S7 exact fragment | external official evidence |
| 无指定奖学金且无例外时申请不能成功 | S7 exact fragment + Applicability snapshot | rule-level inference |
| 该合成人物 v1 不在列明例外中 | synthetic input | runtime user condition |
| 最终个案与 aid type 仍待实际处理 | K-A1 + S6 | limitation |

### Answer 的三层表达

1. **官方规则：** CAF 当前页面对该日期和人群规定了奖学金条件，并列出职业活动等例外。
2. **按给定条件的推断：** 在“无所述奖学金、无职业活动、适用居留标注”的合成情境下，2026 年 8 月的新申请按该页面不能成功。
3. **机构结果边界：** 这不是 CAF 对具体账户和住房作出的决定；实际 aid type、完整个人情境和申请结果仍需由官方流程确认。

Answer 不显示“100% 不可申请”或“已失去 APL”这种越过证据边界的强结论。

## 6.6 五个原子动作

用户依次执行：

1. `保存这次回答` → A2 Answer Snapshot；Question 状态不变。
2. `从回答形成知识` → 建议 K-A2、K-A3、K-A5 三条 Draft；用户检查后分别提交。
3. `链接为回答依据` → 建立 Resolution Proposal RP-A1；仍不是 current answer。
4. `采纳为当前回答` → 创建 Resolution Revision RR-A1。
5. `停止追问 · 目前已足够用于预算判断` → pursuit event；不删除 review trigger。

任何一步失败都不暗自执行下一步。

## 6.7 Adopted Resolution RR-A1

```text
resolution_summary =
  对 2026 年 8 月、持指定学生居留、无所述奖学金且无职业活动的
  非欧盟学生，CAF 当前页面表示新申请不能成功；这是按公开规则和
  给定条件作出的判断，不是具体个案批准结果。

resolution_state = provisionally_resolved
pursuit_state_after_separate_event = concluded
change_state = no_material_change
answer_basis_refs = K-A1@r3, K-A2@r1, K-A3@r1, K-A5@r1,
                    S7@fragment-conditions, S7@fragment-exceptions
criterion_results = C1..C7 satisfied; C8 optional
remaining_unknowns = exact aid type; actual CAF decision; exact future lease inputs
applicability_snapshot = Q-A1 v1 snapshot
operational_decision_pending = true
validity_window = 2026-07-01..until relevant official change or context change
review_triggers = official_source_change, subject_context_change,
                  decision_period_change, basis_unavailable
```

之所以是 `provisionally_resolved` 而不是 `resolved`：它足以支持“不要把补助计入当前预算”的眼前判断，但个案资料、具体住房与机构决定尚不存在。它也不是 `partially_resolved`，因为当前目的所需的 required criteria 已覆盖；保留条件是其核心 standing。

---

# 7. 依据或个人条件变化后的复核与重开

## 7.1 变化事件：职业活动从 none 变为 employed

用户后来在 Q-A1 中更新情境：`professional_activity = declared student employment`。

系统必须先问一个身份连续性问题：

- 核心问题仍是“这个人于 2026 年 8 月是否可能取得个人住房补助”；
- 时间、制度和决策目的未改变；
- 只有一个 Applicability 条件改变。

因此保留 Q-A1 identity，创建 QuestionFrameRevision v2，而不是 successor。

## 7.2 自动与人工边界

系统可以自动：

- 写入 `changes_detected` event；
- 把 `change_state` 标为 `changes_available`；
- 指出 C4 activity 受影响；
- 展示 RR-A1 的旧快照与新的情境差异；
- 提出“职业活动可能命中 S7 列明例外”的 Resolution Proposal。

系统不能自动：

- 把 `pursuit_state` 从 concluded 改为 active；
- 把 RR-A1 改成“现在有资格”；
- 把 `resolution_state` 从 provisional 改为 resolved；
- 宣布旧回答错误；
- 将职业信息写成全局个人 Knowledge。

## 7.3 Change review

用户看到：

> 你的当前回答采用于 2026-08-10，当时的条件是“没有职业活动”。现在该条件变为“已有学生雇佣活动”。CAF 的依据页面把职业活动列为可能继续符合住房补助的情形，因此当前回答需要复核；其余 6 项标准没有检测到变化。

三个动作：

- `查看依据与差异`；
- `暂不处理`；
- `重新追问这个问题`。

不显示红色“答案失效”，因为新活动是否满足官方个案规则仍待检查。

## 7.4 Reopen

用户选择 `重新追问这个问题`：

```text
event_type = reopened
reason = applicability_changed
from = provisionally_resolved + concluded + changes_available
to = provisionally_resolved + active + changes_available
affected_resolution = RR-A1
affected_criteria = C4
```

Reopen 不降级旧 Resolution；它只恢复追问意愿。

## 7.5 Ask Run A3：新 Applicability

AI 的回答必须是：

1. 新职业活动使旧 Resolution 的核心限制不再原样适用；
2. CAF 页面把职业活动列为仍可符合的情形，因此“按规则必然不能成功”的旧推断不能直接沿用；
3. 当前只能判断为“可能进入例外路径”，还需要核对活动性质、完整收入和住房信息，并通过 CAF 实际流程确认；
4. RR-A1 仍是对 v1 情境的历史回答，不应被改写成错误。

## 7.6 Adopted Resolution RR-A2

```text
resolution_summary =
  新增的学生雇佣活动使申请人可能落入 CAF 页面列明的职业活动例外，
  因而不能继续沿用“新申请不能成功”的旧个体推断；是否最终符合及金额
  仍需按活动、收入、住房和完整身份材料由 CAF 流程确认。

resolution_state = provisionally_resolved
pursuit_state = active
change_state = no_material_change
predecessor_resolution_revision_ref = RR-A1
applicability_snapshot = Q-A1 v2
remaining_unknowns = activity qualification; exact resources; housing; operational decision
operational_decision_pending = true
```

若用户之后只是把月份从 2026 年 8 月改为 2027 年 9 月，且需要重新判断届时规则，则默认建立 successor：核心时间范围和所依赖规则已实质改变，旧 RR-A1 / RR-A2 仍保留为 2026 情境历史。

---

# 8. Question Q-R1：一个较短但完整的流程

## 8.1 问题与标准

**问题：** 租房 dossier 是否必须等 Visale 最终证明后才能提交 DossierFacile？

**Targets：**

| target | role | uncertainty |
|---|---|---|
| K-R2 | tests_applicability_of | applicability_missing |
| K-R3 | seeks_fact_about | unknown_fact |
| K-R5 | seeks_explanation_of | unresolved_explanation |
| S2 | seeks_evidence_for | missing_evidence |
| S3 | seeks_evidence_for | missing_evidence |

**Required criteria：**

1. 区分 DossierFacile 验证与 Visale 证书签发；
2. 找到没有最终机构担保证明时的官方操作；
3. 不把 dossier 可先验证误写成可以先签署 Visale 担保租约；
4. 给出签约阶段的独立顺序限制。

## 8.2 回答与形成 Knowledge

Answer：

> 不必为了等待最终 Visale 证明而阻塞 DossierFacile dossier 验证。DossierFacile 的官方帮助说明，可以暂时移除“机构担保”栏目，待收到最终证明后再补；但如果最终租约要使用 Visale 担保，Visale visa、出租人担保合同和租约签署仍需遵守自己的先后与有效期。

用户执行：

- 从第一句形成 K-R3；
- 将 K-R3 `qualifies` K-R2；
- 将 K-R5 作为限制 basis；
- 采纳 RR-R1 为 `resolved`；
- 另行结束追问，reason = `sufficiently_answered`。

这里可以 `resolved`，因为所有 required criteria 均有直接官方依据，且问题只问流程能否先提交，不问某个申请人的最终资格。

---

# 9. 完整终局旅程：22 个连续步骤

| Step | 用户看到 / 做什么 | 真实写入或读取 | 禁止副作用 |
|---:|---|---|---|
| 1 | 打开 Library | Groups + stable curation | 不用 Today / Inbox 夺权 |
| 2 | 进入 G-RENT | Group Overview + Topic tree | 不先打开图谱 |
| 3 | 选择“准备租房材料” | Topic Overview | 不变成文件清单 |
| 4 | 阅读 K-R1 | Paper → Claim → Evidence | Source 不冒充 Knowledge |
| 5 | 深入 K-R2 | same scene + DepthTrail | 不丢 Group 语境 |
| 6 | 检查 R2 | Relation Peek / Inspector | Inspect 不等于 Open |
| 7 | 打开 K-R3 | 连续正文 | 返回时恢复原 Anchor |
| 8 | 沿 E1 进入 G-AID | cross-group exit + trail | 不自动创建 Group edge |
| 9 | 阅读 G-AID Overview | 一般框架、2026 变化、关键问题 | 不把所有变化做成告警 |
| 10 | 保存 Q-A1 | Question Knowledge + Placement | 不把 Query Turn 当 Question |
| 11 | 第一次 Ask | explicit narrow context | 不冒充已有内部答案 |
| 12 | 允许单次官方外部研究 | per-run permission | 权限不继承 |
| 13 | 检查三层 Answer | official rule / inference / operational limit | 不宣布个案获批 |
| 14 | 保存 Answer | Answer Snapshot | 不改 Question state |
| 15 | 形成 K-A2 / K-A3 / K-A5 | three explicit Knowledge commits | 不一键全收 |
| 16 | 链接 basis | Resolution Proposal | 不自动 adopt |
| 17 | 采纳 RR-A1 | adopted current answer | 不自动 conclude |
| 18 | 停止追问 | lifecycle event | 不 archive / delete |
| 19 | 更新职业条件 | Question revision v2 + change event | 不覆盖 v1 snapshot |
| 20 | 查看变化 | criterion impact + source + diff | 不自动宣告错误 |
| 21 | Reopen + Ask | pursuit active + new Query Run | 不自动降 resolution |
| 22 | 采纳 RR-A2 并继续探索 | new adopted Resolution + exact return | 历史 RR-A1 保持可读 |

## 9.1 旅程的真实终点

终点不是“AI 回答完毕”，而是用户拥有：

- 两个边界清楚、各有可读 Overview 的知识群；
- 一条从总体到细节、证据和相邻知识群的连续路径；
- 十条可独立维护的 Knowledge；
- 七条经过语义检查的关系或关系候选结论；
- 一个有时间、适用条件、criteria、当前回答与历史的 Question；
- 一份在新条件出现后仍不失真的变化与复核历史；
- 可以随时从 Answer / Evidence / Network 精确回到原阅读现场的导航状态。

---

# 10. 对未来 Screen 2 / Screen 3 的内容证明

本节不是 wireframe，只定义未来视觉方案必须承载的真实内容。

## 10.1 Screen 2：Layered Reading Workspace

必须用 Q-A1 或 K-A2 的完整真实标题证明：

1. 长标题不被截断为不可辨节点；
2. 主体仍是连续 Paper，不是状态卡片墙；
3. 顶部只显示一条可懂状态句，例如：`暂时可用 · 已停止追问 · 依据有变化`；
4. `as of 2026-08-10`、主体条件和“仍待 CAF 决定”在判断位置可见；
5. Target、Basis、Subquestion、ordinary Relation 分层，不用同一种线；
6. 一个 changed criterion 能被突出，其他未变化 criteria 不制造噪声；
7. `保存回答`、`形成知识`、`链接依据`、`采纳当前回答`和`停止追问`有不同后果说明；
8. Evidence fragment 可以打开并回到原 Anchor；
9. 从 G-RENT 经 E1 进入后，DepthTrail 与 ExplorationTrail 同时可恢复；
10. 离线时仍可阅读已经保存的 Knowledge、Question 与 Source snapshot。

## 10.2 Screen 3：Relation Space

必须证明：

1. 默认只画正式 current Knowledge Relations；
2. Q-A1 target layer、Answer basis layer、cross-group exits 和 Group relations 可以分别开关；
3. K-A2 → K-A1 与 K-A3 → K-A2 都显示为 `qualifies`，并展示不同 qualifier；
4. 历史 RR-A1 → RR-A2 是 lifecycle / revision trail，不画成 ordinary semantic edge；
5. S7 → K-A2 是 Evidence / provenance，不画成 `derived_from`；
6. 两个 cross-group exits 不汇总成未经采用的群级粗线；
7. Graph、Relation List 和 mobile sheet 对同一 selected item 给出同样的 statement、direction、standing、scope 和 evidence；
8. 关闭 Relation Inspector 后恢复 Q-A1 原 criterion、scroll、expanded section 和 selection。

## 10.3 视觉品味约束

- 方向 3 的阅读秩序承担“理解”：安静、纵向、排版优先、逐层深入；
- 方向 2 的关系空间承担“探索”：只在意图出现时扩张，线条少而有意义；
- 不用发光球、随机星图或关系数量制造“智能感”；
- 复杂限定优先用清楚语言与局部结构表达，不把所有语义编码成颜色；
- 需要用户判断的 `changes_available` 使用克制但明确的强调，不制造告警中心；
- Source、AI inference、个人输入与 adopted Knowledge 必须有稳定但不过度装饰的 standing 差异。

---

# 11. 失败、离线与不完整状态

## 11.1 外部资料不可用

若 S7 网址暂时不可访问：

- 已保存 Source snapshot 与 exact fragment 仍可读；
- 页面显示 `source currently unavailable`，不删除 K-A2；
- 若已到 review trigger 且无法核验，Q-A1 进入 `review_due`；
- AI 不得把无法重新访问误写为来源被撤回。

## 11.2 Index partial

若 S7 已保存但尚未完成索引：

- Ask Receipt 写明 `index partial`；
- 可以显式直接读取已知 Source / Fragment；
- “没有召回”不能写成“知识库里不存在”；
- Runtime Unknown reason = `index_incomplete`，不自动新建 Question。

## 11.3 AI unavailable

用户仍可以：

- 进入 Group / Topic / Knowledge；
- 阅读 Overview、Relations 与 Evidence；
- 手写 Question 与 Resolution；
- 更新 Applicability；
- 检查历史；
- 导出完整 Knowledge Package。

AI 不可用只能阻断生成和辅助比较，不能阻断知识库本体。

## 11.4 来源出现新版本但语义未变

页面排版、locator 或发布时间更新时：

- 先创建 Source Revision；
- 尝试重定位 fragment；
- 语义哈希 / 人工检查未发现 material change 时，不触发 Question `changes_available`；
- 只有影响 adopted Claims、Applicability 或 criteria 的变化才创建 change event。

## 11.5 来源与当前 Knowledge 真正不一致

系统创建 Change Proposal，展示：

- 新旧 exact fragments；
- 受影响 Knowledge revisions；
- 受影响 Question criteria；
- 旧 Resolution 的 `as_of` 与适用条件；
- 建议动作：更新 Knowledge、保留历史、建立 Conflict、复核 Question。

系统不能自动覆盖 Current Knowledge 或 adopted Resolution。

---

# 12. 二十四条 Given / When / Then

## 验收 1：Group Overview 可以先于图谱建立理解

**Given** 用户首次进入 G-RENT  
**When** 尚未打开 Relation Companion  
**Then** 仅凭 Overview 与 Topic tree 就能说出材料、DossierFacile、Visale 和签约的基本顺序。

## 验收 2：跨群出口不自动升级

**Given** G-RENT 与 G-AID 之间有 E1、E2 两条 exits  
**When** 用户进入 Library Network  
**Then** 没有 maintained / adopted Group Relation 时不显示正式群级边。

## 验收 3：合法清单与服务材料分开

**Given** K-R1、K-R2 都谈租房材料  
**When** 用户检查 R1  
**Then** 能辨认“法律许可范围”和“服务如何实现 dossier”是两个 Knowledge，并看到 implementation qualifier。

## 验收 4：DossierFacile 与 Visale 顺序不矛盾

**Given** K-R3 允许先验证 dossier，K-R5 要求 Visale 文件先于受担保租约  
**When** AI 比较两者  
**Then** 说明它们约束不同阶段，不创建 Conflict。

## 验收 5：一般规则与特定新条件不冲突

**Given** K-A1 为一般框架，K-A2 为特定日期 / 人群限制  
**When** 建立关系  
**Then** 使用 `qualifies`，并要求时间、人群 qualifier；不使用 `contradicts`。

## 验收 6：Question 保存 Applicability Snapshot

**Given** Q-A1 的回答依赖日期、身份、奖学金与职业活动  
**When** 用户采纳 RR-A1  
**Then** Resolution 固定这些值、官方 basis、`as_of` 和 operational decision pending。

## 验收 7：个人条件不自动成为 Knowledge

**Given** Ask 中出现“无奖学金、无职业活动”  
**When** 保存 Answer 或采纳 Resolution  
**Then** 条件只保存在 run / Question Applicability；除非显式保存，不产生全局 Profile Knowledge。

## 验收 8：规则、推断与机构决定分层

**Given** A2 使用 CAF 页面和合成条件  
**When** 生成 Answer  
**Then** 至少分别标示 official rule、contextual inference、operational outcome pending。

## 验收 9：外部权限按次

**Given** A2 获准访问外部官方资料  
**When** 用户稍后再次 Ask  
**Then** 外部权限恢复默认状态，不因上一次允许而继承。

## 验收 10：保存 Answer 不自动形成 Knowledge

**Given** A2 有三个可复用 Claims  
**When** 用户只点“保存这次回答”  
**Then** 只生成 Answer Snapshot，不创建 K-A2 / K-A3 / K-A5。

## 验收 11：形成 Knowledge 不自动采纳 Resolution

**Given** 用户从 A2 提交三条 Knowledge  
**When** 写入完成  
**Then** Q-A1 仍保持原 Resolution 状态，直到用户另行采纳。

## 验收 12：链接 basis 不等于当前回答

**Given** K-A2 / K-A3 已链接到 Q-A1 criteria  
**When** Proposal 仍未 accepted  
**Then** Question header 不显示“暂时可用”或“已充分回答”。

## 验收 13：Provisional 不是低置信度

**Given** RR-A1 足以支持当前预算判断，但最终住房与机构结果未知  
**When** 用户采纳  
**Then** standing 为 provisional，并明确 limitation、validity 和 remaining unknowns；不展示模型 confidence 百分比替代它。

## 验收 14：采纳与停止追问分开

**Given** RR-A1 已采用  
**When** 用户尚未选择停止追问  
**Then** pursuit 仍 active；只有第二个 lifecycle action 才变为 concluded。

## 验收 15：条件变化只影响相关 criterion

**Given** professional_activity 从 none 变为 employed  
**When** 系统计算影响  
**Then** 标记 C4 与 RR-A1，其他 criteria 不自动降级。

## 验收 16：变化不自动宣判旧答案错误

**Given** 新情境可能进入职业活动例外  
**When** `changes_available` 出现  
**Then** RR-A1 保持为 v1 Applicability 下的历史回答，并显示需要复核。

## 验收 17：Reopen 只改变 pursuit

**Given** Q-A1 为 provisional + concluded + changes_available  
**When** 用户重新追问  
**Then** pursuit 变 active；resolution_state 保持，直到新 Resolution 被采用。

## 验收 18：新 Resolution 保留 predecessor

**Given** 用户采纳 RR-A2  
**When** 查看 History  
**Then** RR-A1、两版 Applicability、变化原因、reopen 和 criterion mapping 均可回读。

## 验收 19：实质时间改变建立 successor

**Given** 用户把问题改为 2027 年新的住房和规则情境  
**When** 旧回答无法合理覆盖新时间范围  
**Then** 建立 successor，不覆盖 Q-A1 的 2026 历史。

## 验收 20：来源不可用不等于撤回

**Given** S7 暂时无法联网访问  
**When** 用户打开 Q-A1  
**Then** 已保存 fragment 仍可读；状态为 source unavailable / review due，不自动 retract K-A2。

## 验收 21：索引不完整不等于无知识

**Given** S7 已保存但尚未进入索引  
**When** 搜索无命中  
**Then** 结果明确 coverage partial，不返回“知识库没有相关信息”的确定结论。

## 验收 22：Graph / List / mobile 同义

**Given** selected K-A2 同时有 R4、S7 Evidence 与 Q-A1 target  
**When** 分别在 Graph、Relation List 与 mobile 打开  
**Then** 三类连接保持不同对象、标签、方向、standing 与 scope。

## 验收 23：Exact return

**Given** 用户从 Q-A1 的 C4 进入 S7 fragment，再经 K-A3 打开 Relation Space  
**When** 连续 Back  
**Then** 依次恢复 selected relation、K-A3 Anchor、S7 fragment 与 Q-A1 C4 的 scroll / expansion / focus。

## 验收 24：AI 不可用时产品仍完整可读

**Given** 本地 Library 在线、AI 和网络均不可用  
**When** 用户进入这两个 Groups  
**Then** Overview、Knowledge、Question、adopted Resolutions、Relations、Evidence snapshots 与 History 仍可浏览和编辑。

---

# 13. 由夹具触发并已进入 v6 的产品责任

## 13.1 已吸收进 v6 Canonical 的责任

- 高后果 current answer 的 Applicability Snapshot → v6 §6.6；
- 规则陈述 / 情境推断 / 机构决定边界 → v6 §8；
- time、source、target、subject / applicability、basis availability 与 manual review trigger → v6 §6.6、§10；
- 时间与人群不同的主张默认先作为 Relation qualifier，而不是自动 contradiction → v6 §7；
- 真实 cross-group exit 不自动成为 Group Relation → v6 §7.5；
- 本夹具作为进入视觉设计前的真实性 Gate → v6 §13.3、§17.4。

以下 13.2–13.4 保留的是更深层候选合同。它们只有在与 v6 当前术语、对象身份和默认关系意图族完全对齐后，才可从 Migration Queue 进入 Canonical；本夹具不能独立改写产品本体。

## 13.2 必须回写 Question contract

`QuestionResolutionRevision.applicability_snapshot` 至少结构化为：

```text
ApplicabilitySnapshot
  as_of
  jurisdiction?
  decision_period?
  subject_context_refs_or_inline_inputs[]
  governing_rule_refs[]
  assumptions[]
  exclusions[]
  operational_decision_pending
```

`review_triggers` 至少支持：

```text
time_reached
source_revision_material
target_or_basis_changed
subject_context_changed
applicability_changed
basis_unavailable
manual_review_requested
```

## 13.3 必须回写 Ask contract

高后果、规则或资格型 Answer 应按需要分层：

- `source_statement`：来源明确说了什么；
- `contextual_inference`：结合本次条件能推断什么；
- `operational_outcome`：是否已有机构 / 系统实际决定；
- `unknown_or_next_verification`：仍缺什么。

这不是要求所有日常问题都显示四段，而是禁止 AI 用一段流畅文字抹平 standing。

## 13.4 必须回写 Overview / Search / Design Proof

- Overview 的关键 Question 在 material change 时显示 adopted `as_of` 与变化原因；
- Search 对时效性规则显示 effective date / applicability，历史规则不会因关键词更匹配而冒充 current；
- Screen 2 / 3 必须使用本夹具真实内容证明 Layered Reading + Relation Space，而不是继续用概念海报证明产品。

---

# 14. 结论

这个真实主题证明，理想产品并不需要从“知识库”膨胀成一个替用户生活的 Cognitive OS。它需要把知识库本身做深：

- Group 给出边界；
- Overview 给出可读全貌；
- Topic hierarchy 让用户持续深入；
- Knowledge Paper 保存可维护的理解；
- Evidence 让判断可以核验；
- Relation 只表达真实、精确、有限定的语义；
- cross-group exit 让知识世界连通而不制造粗糙大图；
- Question Knowledge 保存长期未知；
- Ask 帮助回答，但不偷走采用权；
- Applicability、Resolution 与 History 让过去的正确判断在世界变化后仍然可理解。

方向 3 与方向 2 的结合也因此变得更准确：主体验是从 Overview 深入细节的安静阅读；关系空间是随需要展开的横向理解。AI 不是第三个产品中心，而是穿过两者、并把回答可靠写回知识库的一种调用方式。
