# Patrick Collison 表达 DNA（碎片表达与风格量化）

> 调研日期：2026-08-27
> 目标：不是"他说了什么"，而是"他怎么说"。所有引语逐字保真，均附来源 URL。
> 查不到原文的"名言"一律未收录。

---

## 0. 语料与方法说明（先看这里，所有数字的计算依据）

### 0.1 语料池

| 语料 | 来源 | 规模 | 保真度 |
|---|---|---|---|
| **A. HN 评论（主语料）** | HN 用户 `pc` = Patrick Collison，via Algolia API `search_by_date?tags=comment,author_pc` | **68 条评论 / 6,984 词 / 376 句**，跨 2014-03 → 2025-09 | 逐字（API 原始 `comment_text`） |
| **A'. HN 全量参照** | 同上，`nbHits` | **约 650 条评论**（2007–2025），karma ≈ 17k | 用于做全语料词频参照（`nbHits` 计数） |
| **B. X/Twitter** | 搜索引擎返回的 X 页面 title（title 即推文原文，长推被截断） | **15 条 / 648 词**，其中 5 条完整、10 条被 title 长度截断 | 逐字但部分截尾 |
| **C. patrickcollison.com/advice** | 官网 | **632 词 / 49 句** | 逐字 |
| **D. patrickcollison.com/questions, /fast, /dispatches** | 官网 | 22 个问题标题 + 结构 | 标题逐字，正文仅短引 |
| **E. Conversations with Tyler（他反向采访 Tyler Cowen）** | conversationswithtyler.com | 20 条他的提问逐字 | 逐字 |

**为什么以 HN 为主语料**：HN 评论是他唯一大规模、无编辑、无公关介入、即兴写作的公开语料。推文经过更多自我审查，官网文字经过编辑。HN 评论中大量是**回复**（reply），最接近他的思维原声。

### 0.2 计算方法

- 分句：以 `. ! ?` 为界，排除 `e.g. / i.e. / etc. / vs.` 及小数点内的句点；少于 2 个词的片段不计为句。
- 计词：正则 `[A-Za-z][A-Za-z'-]*`，URL 与域名在计数前替换为单一 token（避免链接污染词长统计）。
- 语料 A 计数前已剥离 HN 的 `<p>` / `<i>` / `&#x27;` 等 HTML 标记。
- 脚本与语料保存在 `/root/pc_corpus/`（`hn.txt`, `tweets.txt`, `advice.txt`, `analyze.py`），可复算。

---

## 1. 量化分析（核心交付）

### 1.1 句长

| 指标 | HN 评论（n=376 句） | 推文（n=36 句） | /advice（n=49 句） |
|---|---|---|---|
| **平均句长** | **18.56 词** | **18.00 词** | **12.90 词** |
| 中位句长 | 17.0 词 | 18.5 词 | 12.0 词 |
| 标准差 | 11.46 | — | — |
| 最长句 | 93 词 | — | 33 词 |
| 最短句 | 2 词 | — | — |

**句长分布（HN）：**

| 区间 | 句数 | 占比 |
|---|---|---|
| 1–10 词 | 96 | **25.5%** |
| 11–20 词 | 152 | **40.4%** |
| 21–30 词 | 80 | 21.3% |
| 31–45 词 | 41 | 10.9% |
| 46+ 词 | 7 | 1.9% |

**关键发现（这是他最重要的节奏指纹）**：平均句长 18.6 词，看起来"中等"，但标准差高达 11.46——**他不是写中等长度的句子，他是把长句和极短句交替使用**。四分之一的句子在 10 词以内。典型节奏是：一个 25–40 词的限定性长句，紧跟一个 3–8 词的短句作为落点。

> "I'm trying to not overstate my certainty. I have no idea what situation OP could be describing, and I have no recollection of anything along those lines, but I don't want to definitively state that nothing like it happened over our decade of operation without knowing more about what's actually being alleged."
> —— 4 词句 + 47 词句。https://news.ycombinator.com/item?id=29389386

> "Right. It's a hard problem. That said, we think we can get better."
> —— 1 + 4 + 8 词。https://news.ycombinator.com/item?id=28525318

### 1.2 疑问句比例

| 语料 | 疑问句 / 总句 | 比例 |
|---|---|---|
| HN 评论 | 6 / 376 | **1.60%** |
| 推文 | 3 / 36 | **8.3%** |
| /advice | 2 / 49 | 4.1% |
| **推文整条即一个提问**（open call） | 3 / 15 | **20%** |

**这是一个反直觉但极重要的发现**：他"很爱提问"的名声主要来自 **X 和 /questions 页面**，而不是他的日常回复。在 HN 上答复别人时，疑问句只占 1.6%——因为那里他在**回答**。他的提问集中在一种特定体裁：**面向公众的开放式征询帖**（"Which are the most…?" / "Who's doing…?"）。

### 1.3 类比密度

HN 语料中，**明确的比喻/类比标记**共 12 处 / 6,984 词 = **1.7 个 / 千词**（约每 590 词一个）。
按分词器标记统计：`like a/an/the` 5 次、`just as` 2 次、`analogy/analogous` 2 次、`a la` 1 次、`equivalent` 2 次。**68 条评论中只有 9 条（13%）含类比标记。**

对比：`for example / e.g.` 出现 **10 次 = 1.4/千词**——**举例的密度与类比几乎相同**。

**结论：他的类比密度并不高，而且类比类型极有辨识度——不是文学性比喻，而是"把陌生技术映射到读者已知的基础设施/制度"。** 全部 12 个逐字实例：

| 类比 | 出处 |
|---|---|
| "a platform like SWIFT or ACH" | [45131717](https://news.ycombinator.com/item?id=45131717) |
| "\"Decentralized, internet-scale SWIFT\" isn't exactly the right analogy" | 同上 |
| "there could be some **dark matter** that we never become aware of"（指未被发现的误拒） | [28524264](https://news.ycombinator.com/item?id=28524264) |
| "we have to get good at **walking and chewing gum** -- just as Google or Amazon have" | [17554782](https://news.ycombinator.com/item?id=17554782) |
| "(a la Lyft and Postmates)" | [7460778](https://news.ycombinator.com/item?id=7460778) |
| "a situation **analogous to an S3 bucket key getting leaked**" | [27507326](https://news.ycombinator.com/item?id=27507326) |
| "just as Stripe did with card numbers" | 同上 |
| "We are de facto running **a big bug bounty/incentive program** for evading our fraudulent user detection systems." | [28523805](https://news.ycombinator.com/item?id=28523805) |
| "\"**several sigma bad**\" still happens to an unfortunate number of people" | [29388148](https://news.ycombinator.com/item?id=29388148) |
| "We think a lot about **pace layering**" | [20929631](https://news.ycombinator.com/item?id=20929631) |
| "from very basic **cron-like** functionality to a pretty full-featured…" | [25073749](https://news.ycombinator.com/item?id=25073749) |
| "the work and complexity scales **O(n)**" | [5954745](https://news.ycombinator.com/item?id=5954745) |

**类比源域统计**：金融基础设施（SWIFT/ACH）2、计算机科学（S3、cron、O(n)）3、统计/物理（dark matter、several sigma）2、成语（walking and chewing gum）1、公司名（Google/Amazon/Lyft/Postmates）2、设计理论（pace layering）1、安全经济学（bug bounty）1。
**零个来自体育、战争、自然、动物、宗教。** 这是一个极窄的类比源域。

### 1.4 第一人称与人称策略

| 指标 | HN | 推文 | /advice |
|---|---|---|---|
| `I` | 108 次 = **15.5 / 千词** | 20 次 = **30.9 / 千词** | 7 次 = 11.1 / 千词 |
| `we` | 181 次 = **25.9 / 千词** | 6 次 = 9.3 / 千词 | 0 次 |
| `our` | 74 次 = 10.6 / 千词 | — | — |
| `you / your` | — | — | 34 次 = **53.8 / 千词** |
| **I : we 比** | **1 : 1.68** | **3.3 : 1** | — |

**这是他最系统的人称开关**：
- **HN（代表 Stripe 说话）→ we 占主导（1 : 1.68）**，且 `I` 几乎只出现在认知动词前（`I think` 22、`I don't` 13、`I'm` 14、`I'd` 7）。
- **X（作为一个思考者说话）→ I 反转为主导（3.3 : 1）**，`we` 降到 9.3/千词。
- **/advice（教人）→ we 归零，you 飙到 53.8/千词**，17/49 句是祈使句（动词开头）。

**推论规则：他谈公司=we，谈观点=I，谈建议=you。三者几乎不混。**

### 1.5 确定性 vs 不确定性语气（核心指纹）

HN 语料（6,984 词）：

**不确定 / 对冲（hedge）：74 次 = 10.6 / 千词**

| 词 | 次数 | | 词 | 次数 |
|---|---|---|---|---|
| I think | **22** | | might | 9 |
| somewhat | 6 | | could be | 5 |
| maybe | 4 | | seems | 3 |
| kind of | 3 | | tend to | 3 |
| kinda | 2 | | no idea | 2 |
| it might | 2 | | a bit | 2 |
| for whatever it's worth | 2 | | I suspect / it seems / not sure / perhaps / I believe / I don't know / roughly / in principle / would seem | 各 1 |

**确定 / 断言（certainty）：38 次 = 5.4 / 千词**

| 词 | 次数 | | 词 | 次数 |
|---|---|---|---|---|
| always | 9 | | certainly | 7 |
| obviously | 4 | | clearly | 4 |
| of course | 4 | | never | 4 |
| indeed | 2 | | definitely / absolutely / unequivocally / in fact | 各 1 |

### **对冲 : 断言 = 1.95 : 1（约 2 : 1）**

**但这个比值会误导，必须看用法差异**（这是本报告最重要的一条发现）：

他的"断言词"**几乎从不用于强化自己的观点**，而是用于三种别的功能：

1. **让步给对方**（承认对方说的显而易见）：
   > "We **obviously** never intentionally ghost companies…" — [29389386](https://news.ycombinator.com/item?id=29389386)
   > "There's **obviously** heterogeneity, though…" — [25074861](https://news.ycombinator.com/item?id=25074861)
2. **陈述事实性数据**（不是意见）：
   > "polling very **clearly** shows that minority groups strongly support increased housing construction" — [16990120](https://news.ycombinator.com/item?id=16990120)
3. **承诺行动**（不是判断）：
   > "we'll **certainly** revisit this over time" / "We **definitely** still offer live chat support!"

**当他真的表达一个观点时，几乎 100% 带对冲。** `I think` 一词就占了全部对冲的 30%（22/74），并且在全量 ~650 条 HN 评论中，`obviously` 只出现在 **18 条**、`that said` 出现在 **15 条**——即使在最断言的词上，覆盖率也只有约 2.8%。

**可复制的规则：观点必须挂 hedge，事实可以裸奔。**

### 1.6 转折词频率（他的招牌节奏）

HN 语料：**转折/让步词共 116 次 = 16.6 / 千词 = 每 3.2 句就有一个。**

| 词 | 次数 | /千词 |
|---|---|---|
| **but** | 44 | 6.3 |
| **still** | 17 | 2.4 |
| **though**（多为句尾后置） | 13 | 1.9 |
| **while**（句首让步） | 12 | 1.7 |
| **that said** | 9 | 1.3 |
| actually | 7 | 1.0 |
| rather than | 5 | 0.7 |
| however | 3 | 0.4 |
| yet | 3 | 0.4 |
| **all that said** | 2 | 0.3 |
| nonetheless | 1 | 0.1 |

**注意 `but`(44) : `however`(3) = 14.7 : 1。他几乎不用 `however`。** 这是口语化选择——`however` 太正式。

**"That said" 是他最具身份识别度的连接词**（9 次 + "All that said" 2 次 = 11 次 = 1.6/千词；全量 650 条中出现在 15 条）。它的功能永远相同：**先完整承认对方，再引出自己的真实立场。**

> "**That said**, I'm somewhat skeptical of the safety argument, which I often hear." — [30874081](https://news.ycombinator.com/item?id=30874081)
> "**All that said**, it's helpful to hear how it seems from your standpoint." — [22371977](https://news.ycombinator.com/item?id=22371977)
> "**That said**, we've generally erred towards raising less rather than more" — [8689632](https://news.ycombinator.com/item?id=8689632)

**`though` 后置也是招牌**（不是句首的 "Though…"，而是插在中间或结尾）：
> "not saying we didn't screw up, **though**" / "There's obviously heterogeneity, **though**" / "(Sorry we don't have a timeline, **though**.)"

### 1.7 数字与具体事实密度

| 指标 | HN 语料 |
|---|---|
| 数字 token | 38 = **5.4 / 千词** |
| 含数字的句子 | 33 / 376 = **8.8%** |
| 百分比 | 6 |
| 金额（$） | 4 |
| 年份 | 7 |
| **具名实体**（公司/国家/项目，按人工词表统计） | **117 = 16.8 / 千词** |

**关键发现：他不是"数据驱动"的，他是"具名实体驱动"的。**
具名实体密度（16.8/千词）是数字密度（5.4/千词）的 **3.1 倍**。也就是说，**平均每 60 词就出现一个专有名词**，而每 185 词才出现一个数字。

他的"具体性"来自于**点名**——公司、国家、产品、人、法案：Stripe、Bridge、DolarApp、SpaceX、Paystack、Shopify、Braintree、Slack、Atlassian、Nigeria、India、Philippines、Japan、Singapore、Ireland、Mexico、SWIFT、ACH、MiCA、GENIUS Act、ISO 8583、Empire State Building、Golden Gate Bridge、Boeing 747、Bell Labs、Lyft、Postmates、Squarespace、Tarsnap……

而当他用数字时，数字**几乎总是带方向和基准**，而不是孤立的大数：

> "roughly 99%–99.9% of cases get resolved without anything on HN" — [28525337](https://news.ycombinator.com/item?id=28525337)
> "reduce the occurrence of these mistaken rejections by **90%** by the end of this year… (They're already down **50%** since earlier this year.)" — [28523805](https://news.ycombinator.com/item?id=28523805)
> "60 workers were apparently killed during the construction of the World Trade Center -- **4x more deaths** than occurred during the construction of the Empire State Building." — [30874081](https://news.ycombinator.com/item?id=30874081)
> "the ratio of people working on improving our payments stack to publishing is about **1000:1**" — [22371977](https://news.ycombinator.com/item?id=22371977)
> "More than **10,000** people have interviewed at Stripe so far this year" — [29388148](https://news.ycombinator.com/item?id=29388148)
> "about **6,000** onsite interviews in 2019" — [24721118](https://news.ycombinator.com/item?id=24721118)
> "improves revenue recovery for failed charges by about **14%**" — [25073749](https://news.ycombinator.com/item?id=25073749)

**模式：数字总是"比率、倍数、变化率、绝对基数"，而不是形容词的替代品。** 他从不说"huge growth"，他说 "already down 50% since earlier this year"。

**对比 /questions 页面**：那里数字密度飙升（"Empire State Building (410 days)"、"P-80 (143 days)"、"$4.45 billion"、"37x more expensive per station"、"93x more"、"NIH spends ~$37 billion annually"）。**他在"提出问题"时是重度数据驱动，在"回复别人"时是轻度数据+重度具名。**

### 1.8 段落长度

以"一条 HN 评论"为段落单位（n=68）：

| 指标 | 值 |
|---|---|
| 平均 | **102.7 词** |
| 中位 | **78.0 词** |
| 最短 | 26 词 |
| 最长 | 452 词 |

| 长度区间 | 条数 | 占比 |
|---|---|---|
| < 40 词 | 8 | 12% |
| 40–79 词 | 26 | **38%** |
| 80–149 词 | 23 | 34% |
| 150–299 词 | 7 | 10% |
| 300+ 词 | 4 | 6% |

（注：本语料已剔除大量 1–15 词的纯功能性回复如 "Yes."、"Yep."、"Period!"、"That's a good idea."。**在完整的 ~650 条 HN 评论里，这类超短回复占相当大比例**——他的真实分布是双峰的：一端是 1–10 词的即时确认，另一端是 80–450 词的结构化说明，中间地带相对少。）

**长评论的固定结构**（4 次 300+ 词的评论全部符合）：
`身份声明（"Stripe cofounder here."）→ 一句致意/致歉 → "A few points:" / "a few broader comments:" / "Zooming out," → 3–6 个带项目符号的并列点 → "All that said," 收尾软化`

### 1.9 标点与排版指纹（补充统计，辨识度极高）

| 特征 | HN（/千词） | 推文（/千词） | /advice（/千词） |
|---|---|---|---|
| **括号插入语**（≥3 字符） | 100 次 = **14.3** | 9 次 = **13.9** | 5 次 = 7.9 |
| **含至少一个括号的评论占比** | **53/68 = 78%** | — | — |
| 每句括号数 | **0.27**（约每 3.7 句一个） | — | — |
| 破折号 `--` / `—` | 47 = 6.7 | 2 = 3.1 | — |
| 省略号 `...` | 8 = 1.1 | — | 4 = **6.3** |
| **感叹号 `!`** | 13 = **1.9** | 2 = 3.1 | 3 = 4.7 |
| **Unicode emoji** | **0** | **0** | **0** |
| ASCII 颜文字 `:-)` `:(` | 语料 A 中 0，但全量中确有（见下） | — | — |

**括号是他最强的单一指纹。** 78% 的评论至少含一个括号插入语，平均每 3.7 句一个。括号的功能高度一致——**放置"我知道你会怎么反驳我"的预防性让步、限定条件、或元评论**：

> "(I don't even know **whether** there are fewer instances today -- maybe they're just happening in less legible domains, or something.)"
> "(We don't always succeed, of course. But, despite the growing sophistication of the fraudsters themselves, we do generally get better every year.)"
> "(And while card authorization is instant, settlement is not.)"
> "(Stated differently, we're taking the risk of your business underperforming…)"
> "(As in PG's original proposal.)"
> "(patrick@stripe.com; others welcome to do so too.)"
> "(This isn't the list of books that I think one ought to read -- it's just the list that I think roughly covers the major ideas that are influential here.)"

**关于感叹号：他用，但受严格限制。** 1.9/千词（约每 537 词一个），且**几乎只出现在三类语境**：(1) 感谢/祝贺 —— "Thanks for all the feedback!"、"congrats to Courtland on building an awesome site!"、"Please apply :-)."；(2) 招募/行动号召 —— "Working on the rest of the EU!"、"EU support is coming!"；(3) 道歉的软化 —— "I'm sorry about the trouble!"。
**从不用于强调一个论点。** 你不会看到 "This is huge!"。

**ASCII 颜文字 `:-)` 他确实用**（早期 HN 尤多），Unicode emoji **零**：
> "Fair :-). \"A little\" relative to market cap." — [22890205](https://news.ycombinator.com/item?id=22890205)
> "That comment made my day -- thanks :-)" — [30963158](https://news.ycombinator.com/item?id=30963158)
> "For whatever reason, those stories don't get upvoted as much on HN :-)." — [17554858](https://news.ycombinator.com/item?id=17554858)
> "Looks like the answer is \"not currently\". Sorry :(." — [8370342](https://news.ycombinator.com/item?id=8370342)
> "If any PayPal folks are reading, I'm patrick@stripe.com :-)." — [7938622](https://news.ycombinator.com/item?id=7938622)

### 1.10 句首词分布（HN，n=376）

| 句首词 | 次数 | 占比 |
|---|---|---|
| I | 34 | **9.0%** |
| We | 24 | 6.4% |
| The | 20 | 5.3% |
| **If** | 16 | **4.3%** |
| This | 13 | 3.5% |
| **And** | 12 | 3.2% |
| **But** | 12 | 3.2% |
| Stripe | 12 | 3.2% |
| It's | 9 | 2.4% |
| For / We're / **While** / That / As | 各 8 | 各 2.1% |
| There / I'm / We've | 各 7 | 1.9% |

**`And` 和 `But` 合计 24 次 = 6.4% 的句子以连词开头**——这是明显的口语化写作标记（正式书面语会避免）。**`If` 占 4.3%**——条件句是他构建论证的主要方式（"If we charged $1/sub/mo (say)…"、"If you're transferring money from institution A to institution B…"）。

---

## 2. 高频词与专属短语（≥15 个，附逐字例句）

### 2.1 高频实词（HN 语料，剔除功能词后）

| 词 | 次数 | /千词 |
|---|---|---|
| Stripe | 59 | 8.4 |
| **think** | 38 | **5.4** |
| don't | 25 | 3.6 |
| people | 21 | 3.0 |
| businesses / business | 34 | 4.9 |
| want | 18 | 2.6 |
| **still** | 17 | 2.4 |
| good | 16 | 2.3 |
| time | 16 | 2.3 |
| **better** | 15 | 2.1 |
| work | 14 | 2.0 |
| **though** | 13 | 1.9 |
| **really** | 13 | 1.9 |
| **sense**（"makes sense"） | 11 | 1.6 |
| functionality | 11 | 1.6 |
| **trying** | 10 | 1.4 |

### 2.2 专属短语清单（18 个）

| # | 短语 | 功能 | 逐字例句 + 来源 |
|---|---|---|---|
| 1 | **"That said," / "All that said,"** | 让步后转折（招牌） | "**That said**, I'm somewhat skeptical of the safety argument, which I often hear." [30874081](https://news.ycombinator.com/item?id=30874081) |
| 2 | **"Stripe cofounder here." / "Stripe CEO here."** | 身份前置声明（他从不匿名评论自家事） | "**Stripe CEO here.** We're very sorry about this." [20404357](https://news.ycombinator.com/item?id=20404357) |
| 3 | **"A few points:" / "a few broader comments:" / "A few quick thoughts --"** | 结构化展开的开关 | "Thanks for the candid feedback. **A few quick thoughts --**" [22371977](https://news.ycombinator.com/item?id=22371977) |
| 4 | **"Zooming out,"** | 从个案跳到系统层 | "**Zooming out**, a few broader comments:" [28523805](https://news.ycombinator.com/item?id=28523805) |
| 5 | **"we still have a lot of work to do"**（及变体 "a lot still to do"） | 强制性自谦（近乎口头禅） | "We've fixed and improved a lot of things since we launched here in 2011, but **we also still have a lot of work to do**." [21018756](https://news.ycombinator.com/item?id=21018756) / "Thank you! **A lot still to do.**" [22372135](https://news.ycombinator.com/item?id=22372135) |
| 6 | **"for whatever it's worth"** | 降低自己说法的权重 | "We're always paranoid that we're too slow, **for whatever it's worth**." [20929631](https://news.ycombinator.com/item?id=20929631) |
| 7 | **"It's a very fair question." / "Yeah, good question."** | 先给对方发言权 | "Stripe cofounder here. **It's a very fair question.**" [17554782](https://news.ycombinator.com/item?id=17554782) |
| 8 | **"I'd love to hear / I'd be curious to"** | 邀请反驳 | "I'd love to know where I'm **wrong** rather than just lacking in relevant experience." [19020333](https://news.ycombinator.com/item?id=19020333) |
| 9 | **"makes sense" / "does that make any sense?"** | 检验共识 | "**Does that make any sense?**" [7460778](https://news.ycombinator.com/item?id=7460778) |
| 10 | **"Increase the GDP of the internet."** | Stripe 的使命句，他自称 2012 年初首次使用 | "I think we first used \"increase the GDP of the internet\" in early 2012, a few months after Stripe launched." [17554838](https://news.ycombinator.com/item?id=17554838) |
| 11 | **"on some level"** | 部分同意 | "While this is true **on some level**, the challenge is that…" [25074533](https://news.ycombinator.com/item?id=25074533) |
| 12 | **"Ugh, apologies." / "I'm sorry; that's bad."** | 极短道歉开场 | "**Ugh, apologies.** Something very clearly went wrong here and we're already investigating." [28523805](https://news.ycombinator.com/item?id=28523805) |
| 13 | **"acutely aware"** | 承认缺陷的固定搭配 | "We're **acutely aware** of how much Stripe has yet to do/build." [22371977](https://news.ycombinator.com/item?id=22371977) |
| 14 | **"the status quo ante" / "status quo"** | 学究词进入日常句 | "…easier/faster/better than **the status quo ante**." [45129554](https://news.ycombinator.com/item?id=45129554) |
| 15 | **"a priori" / "de facto" / "per se" / "a la"** | 拉丁语插入（不炫技，作连接词用） | "Nor is it **a priori** clear to me that safety and speed would necessarily be in opposition" [30874081](https://news.ycombinator.com/item?id=30874081) / "We are **de facto** running a big bug bounty…" [28523805](https://news.ycombinator.com/item?id=28523805) |
| 16 | **"Hm." / "Hm, thank you."** | 单音节思考标记开头 | "**Hm.** There are actually a bunch of inaccuracies in the above, but…" [7785535](https://news.ycombinator.com/item?id=7785535) |
| 17 | **"Yeah," / "Yep." / "Right."** 开头 | 口语化承接（不是 "Yes"） | "**Yeah**, good question. First, we aren't trying to calculate the absolute rate, just relative changes." [28524264](https://news.ycombinator.com/item?id=28524264) |
| 18 | **"kinda" / "sorta" / "'till"** | 刻意的口语拼写（打破正式感） | "today is **kinda** bittersweet for us" [9200145](https://news.ycombinator.com/item?id=9200145) / "I find it **kinda** tedious" [7787205](https://news.ycombinator.com/item?id=7787205) / "you never really know how good something like this is going to be **'till** you see the pieces come together" [tweet 1661419449885536256](https://x.com/patrickc/status/1661419449885536256) |

**额外的高价值抽象名词**（低频但极具风格识别度，因为它们把日常问题重新框定为系统问题）：
`pace layering`、`Schelling point`、`Global Weird HQ`、`legible domains`、`general execution capital`、`replacement rate`、`emergent intelligence`、`continuous partial attention`、`counterfactual product`、`premature optimization`、`dispositive`、`heterogeneity`、`monocausal`。

> "San Francisco is the **Schelling point** for high-openness, smart, energetic, optimistic people. **Global Weird HQ**." — https://patrickcollison.com/advice
> "maybe they're just happening in **less legible domains**, or something" — [30874081](https://news.ycombinator.com/item?id=30874081)
> "It should be a factor you weigh but not by itself **dispositive**." — https://patrickcollison.com/advice
> "…which would indirectly hurt businesses by depriving them of a **counterfactual product** that they'd like to be able to buy." — [25074533](https://news.ycombinator.com/item?id=25074533)
> "doing so sooner is a **premature optimization**" — [20929631](https://news.ycombinator.com/item?id=20929631)

---

## 3. 禁忌词与禁忌风格（他从不用的东西）

### 3.1 营销黑话：在 6,984 词语料中的实测次数

| 词 | 次数 | | 词 | 次数 |
|---|---|---|---|---|
| disrupt / disruption | **0** | | synergy | **0** |
| 10x | **0** | | game-changer | **0** |
| leverage（动词，商业义） | **0** | | revolutionary | **0** |
| world-class / best-in-class | **0** | | paradigm | **0** |
| seamless | **0** | | cutting-edge | **0** |
| unicorn | **0** | | rockstar / ninja | **0** |
| crush it / hustle | **0** | | moonshot | **0** |
| secret sauce | **0** | | north star | **0** |
| double down | **0** | | delight（动词） | **0** |
| empower | **0** | | frictionless | **0** |
| innovative | **0** | | passionate | **0** |
| mission-driven | **0** | | robust | 1（形容 Tarsnap 软件，技术义） |
| **disruptive** | **2** | | | |

**"disruptive" 那 2 次尤其值得看——他是在用来反驳这个词：**

> "In these matters, I always try to keep in mind that technologies aren't themselves **disruptive**; customer choices are. It'll be interesting to see what customers choose in the years to come."
> —— https://news.ycombinator.com/item?id=45132320

（注：`leverage` 在 /advice 中作为祈使动词出现过一次 —— "The internet is one of the biggest advantages you have over prior generations. **Leverage it.**" ——但这是字面义"利用"，不是商业黑话义。）

### 3.2 其他禁忌

| 禁忌 | 证据 |
|---|---|
| **Unicode emoji** | 全部三个语料 **0 次**。只用 ASCII `:-)` / `:(`。 |
| **全大写强调** | 0 次。强调用 HN 的 `<i>` 斜体（原文 `*星号*`），如 "we <i>hate</i>"、"just *now*"。 |
| **感叹号用于强调论点** | 0 次。感叹号只用于感谢、招募、道歉软化。 |
| **人身攻击** | 0 次。他明确反对："**This is an ad hominem attack** that doesn't really help us understand whether the core substance of her argument is <i>true</i>, which is what really matters." [19129369](https://news.ycombinator.com/item?id=19129369) |
| **绝对化的第一名/最好** | 极少。找不到 "the best"、"number one" 用于 Stripe 的例子；反而反复说 "we still have a lot of work to do"。 |
| **"haha" / "lol"** | 在 ~650 条 HN 评论全量搜索中，`haha` 命中 **1 条**（且是 "Hah."），`lol` 0 条。 |
| **政治党派语言** | 0 次。即使谈 YIMBY/住房政策这种高度政治化议题，他也只引用学术研究（Chicago Booth、Urban Institute、Obama 政府报告、Richard Rothstein），不用党派标签。 |
| **对竞争对手的贬低** | 0 次，且有反例：他主动称赞 Balanced、WePay、Braintree、Shopify、Heroku、Tobi Lütke。 |

---

## 4. 句式指纹（各 3 个逐字例子）

### 4.1 他怎么"开头一个观点"

**模式：从不直接给结论。三种开场之一——(a) 先声明身份/立场，(b) 先肯定对方，(c) 先给一个观察，再从观察推出观点。**

1. **身份前置 + 立即承认对方**
> "Stripe cofounder here. **It's a very fair question.**"
> — https://news.ycombinator.com/item?id=17554782

2. **"我一直试图记住…"（把观点包装成一条个人守则，而非断言）**
> "In these matters, **I always try to keep in mind that** technologies aren't themselves disruptive; customer choices are."
> — https://news.ycombinator.com/item?id=45132320

3. **先给一个具体观察，再引出结论**
> "There are lots of crypto skeptics on HN (and we ourselves were disappointed with crypto's payments utility for much of the past decade), **so it might be interesting to share what changed our mind** over the past couple of years: we started to notice a lot of real-world businesses finding utility in stablecoins."
> — https://news.ycombinator.com/item?id=45129554

（推文版同构："**As far as I can tell,** one of the biggest changes across organizations over the past few years is simply the rise of distraction." — https://x.com/patrickc/status/1843330133895323792 ；"**Maybe a very prosaic observation, but** I've been reflecting on just how much the pandemic changed the world…" — https://x.com/patrickc/status/1980285288867066175）

### 4.2 他怎么"表达不同意"

**模式：三段式 —— (1) 先给对方一个明确的、非敷衍的让步；(2) 用 but / that said / though 转折；(3) 攻击论点本身，而不是人，并且立刻给出可验证的具体反例。**

1. **对 HN 上指控 Stripe 恶意收购的用户（这是他最强硬的一次公开反驳之一）**
> "**I don't think some of the claims in this comment are true or in good faith.** (We obviously don't control HN or YC or journalists. If or when my comments on HN are ever ranked highly, it's because they're upvoted. The internal claims about Stripe are also inconsistent with the data around things like retention. Etc.)
>
> **All of that said**, I'd appreciate hearing from any founders who feel mistreated as part of an acquisition process. We make a fairly significant number of acquisitions and have never heard this directly before."
> — https://news.ycombinator.com/item?id=29388863

2. **对自己网站 /fast 页面的批评者（安全论）——用数字反驳，并主动承认自己不确定**
> "**That said, I'm somewhat skeptical of the safety argument, which I often hear.** For example, 60 workers were apparently killed during the construction of the World Trade Center -- 4x more deaths than occurred during the construction of the Empire State Building. **Nor is it a priori clear to me that** safety and speed would necessarily be in opposition -- maybe better planning causes both more safety and more speed, for example. **I'd certainly be interested in a more comprehensive investigation of this question.**"
> — https://news.ycombinator.com/item?id=30874081

3. **对一个标题党帖子——最短、最硬的形式：直接判定为假，然后逐条给出可核验的事实**
> "**The title is false.**
> They stopped publishing WM1NS, the weekly, non-seasonally adjusted version.
> They still publish [M1SL], the monthly, seasonally adjusted version.
> **One could perhaps hold a theory about** how the seasonal adjustment (or monthly smoothing?) occlude some important dynamics. **But the headline as-written (\"Fed has stopped publishing the M1 money stock data\") is not true.**"
> — https://news.ycombinator.com/item?id=26906948

**其他反驳样本（值得注意，因为极少）：**
> "**Hm.** There are actually a bunch of inaccuracies in the above, **but I don't think there's much point arguing about the details** -- specifics aside, I agree that Balanced has quickly launched some cool stuff. Congrats on your time at Balanced and good luck with whatever comes next!" — https://news.ycombinator.com/item?id=7785535
> —— **这是他的典型收场：不同意 → 但不追击 → 反而祝福对方。他系统性地拒绝把分歧升级为冲突。**

> "**That's unfair** -- not all platforms have IETF specs (iOS, Android, AWS, etc). You might <i>prefer</i> platforms that have proper specifications, but the presence of one is not implicit in the term." — https://news.ycombinator.com/item?id=8002172

> "**Your comment is needlessly mean-spirited.**" — https://news.ycombinator.com/item?id=8000439（他罕见地直接批评语气而非内容）

> "**Definitely not. That would be dishonest and stupid.**" — https://news.ycombinator.com/item?id=7374335（面对"Stripe 是否卖用户数据"的指控——这是全语料中他最短最硬的一句）

### 4.3 他怎么"承认自己不懂"

**模式：不是模糊地说"我不确定"，而是精确地划出无知的边界——"我不知道 X，我甚至不知道 X 是否成立"。这是他最独特的一个动作。**

1. **双层无知声明（连自己的前提都不确定）**
> "**I genuinely don't know why** there are fewer instances today, and the question at the bottom is literal rather than rhetorical. (**I don't even know <i>whether</i> there are fewer instances today** -- maybe they're just happening in less legible domains, or something.)"
> — https://news.ycombinator.com/item?id=30874081

2. **明确把"不确定"当作一种纪律来说明**
> "**I'm trying to not overstate my certainty.** I have no idea what situation OP could be describing, and I have no recollection of anything along those lines, **but I don't want to definitively state that nothing like it happened** over our decade of operation without knowing more about what's actually being alleged. […] But maybe some communication got dropped in some particular case or something? **I don't know.**"
> — https://news.ycombinator.com/item?id=29389386

3. **承认自己没有结构化答案（并且不假装有）**
> "**No wonderfully structured answer, I'm afraid.** We do now have engineering teams in Japan, Singapore, India, Ireland, Mexico, Nigeria (via Paystack), and elsewhere… To do that, though, there's ultimately **a lot of subjective judgment required**."
> — https://news.ycombinator.com/item?id=27281588

**补充样本：**
> "**I'm actually not sure. I'll check with the team.**" — https://news.ycombinator.com/item?id=25074969
> "**So, I haven't found a satisfying explanation, and I'd be curious to read other analyses or diagnoses.**" — https://news.ycombinator.com/item?id=30874081
> "**I'd love to know where I'm <i>wrong</i>** rather than just lacking in relevant experience." — https://news.ycombinator.com/item?id=19020333
> "**If you're 20–30: I don't know yet. I plan to think about this when I'm 35-40.**" — https://patrickcollison.com/advice（用整整一节承认无知）
> "**I'm not sure whether it's good or bad.**" — https://x.com/patrickc/status/1843330133895323792

### 4.4 他怎么"承认错误 / 道歉"

**这是他极高频的动作**：在 ~650 条 HN 评论全量搜索中，含 "sorry" 的评论 **27 条（约 4.2%）**。
**模式：道歉在最前面、极短、不带辩解；解释放在道歉之后而不是之前。**

> "**Ugh, apologies.** Something very clearly went wrong here and we're already investigating." — [28523805](https://news.ycombinator.com/item?id=28523805)
> "**I'm sorry; that's bad.** Can you email me with details so that we can investigate what happened?" — [29388148](https://news.ycombinator.com/item?id=29388148)
> "**You're right.** It would have been a lot better if we'd made explicit that we weren't intending to make a permanent commitment. **This is good feedback for the next time we do something like this.**" — [25074221](https://news.ycombinator.com/item?id=25074221)
> "**Yeah, we messed up in not having this be clearer. Apologies!**" — [16767838](https://news.ycombinator.com/item?id=16767838)
> "**You're right! (Though I am.) I edited the comment.**" — [22372008](https://news.ycombinator.com/item?id=22372008)
> "**Oh no, I'm sorry. I've no idea what happened.** Want to try my personal email? patrick@collison.ie." — [7350213](https://news.ycombinator.com/item?id=7350213)
> "**Sorry, we can't give a timeline. I wish we could.**" — [3540702](https://news.ycombinator.com/item?id=3540702)

**注意"I'm sorry that it feels that way" / "I'm sorry that it comes across this way"**——这是他罕见的"软道歉"（道歉的是感受而非事实），出现在他实际上不认为自己做错的场合：
> "**I'm sorry that it feels that way.** Stripe Billing's pricing has been public since 2018." — [25074296](https://news.ycombinator.com/item?id=25074296)

---

## 5. 提问方式（他的问题长什么样）

### 5.1 结构模板（从 /questions 22 个问题中提取）

**几乎全部是同一个模板：**

```
[Why / What / How] + [一个被普遍认为理所当然的现象]?
    ↓
一段用具体数字和具名案例建立的"这确实是个现象"的证据
    ↓
主动列举并反驳 2–4 个显而易见的解释
    ↓
以一串更细的子问题结束，而不是以一个答案结束
```

**22 个问题标题（逐字，https://patrickcollison.com/questions）：**

1. Why are certain things getting so much more expensive?
2. Why do there seem to be more examples of rapidly-completed major projects in the past than the present?
3. Why is GDP growth so weirdly constant?
4. How do you ensure an adequate replacement rate in systems that have no natural way to die?
5. How do we help more experimental cities get started?
6. How do people decide to make major life changes?
7. Why are there so many successful startups in Stockholm?
8. Is Bloom's "Two Sigma" phenomenon real? If so, what do we do about it?
9. How can we better understand the dynamics of progress in science?
10. Will end-user applications ever be truly programmable? If so, how?
11. What's the successor to the book? And how could books be improved?
12. What's the successor to the scientific paper and the scientific journal?
13. What's the right way to understand and model personality?
14. Could there be more good blogs?
15. Why are programming environments still so primitive?
16. What does religion cause?
17. Why is there no canon for life's most important questions?
18. Why are so many things so much nicer in Switzerland and Japan?
19. Why isn't China (yet) producing a lot of top-tier research?
20. Why don't we build nice neighborhoods any more?
21. What influences when people act in accordance with their self-interest and when they don't?
22. What's going on with infrastructure?

**统计：**
- **"Why" 开头：9 / 22 = 41%**（"Why are…" 5、"Why is/isn't…" 3、"Why do/don't…" 3——含重叠）
- **"What / What's" 开头：5 / 22 = 23%**
- **"How" 开头：4 / 22 = 18%**
- 其余：Is / Will / Could 开头 = 3 / 22 = 14%
- **含 "(yet)" / "still" / "any more" / "so weirdly" 等时间或程度限定词的：8 / 22 = 36%**——他的问题几乎总是关于**变化**（以前能做，现在不能；别处能做，这里不能），而不是关于静态事实。
- **最口语化的一个：#22 "What's going on with infrastructure?"**——注意他允许自己用完全非学术的措辞提最大的问题。

### 5.2 他提问的三个固定特征

**(a) 主动预先反驳自己的问题**（防止读者用现成答案打发）：
> "Wealth alone doesn't explain it… Stability doesn't account for it—Japan's history contradicts this."（#18）
> "This isn't an issue of individual capability—Chinese researchers excel abroad."（#19）
> "Survivorship bias partially explains this, yet few US neighborhoods built since 1950 prove pleasant…"（#20）

**(b) 明确声明"这不是修辞性提问"**：
> "the question at the bottom is **literal rather than rhetorical**." — https://news.ycombinator.com/item?id=30874081

**(c) 在 X 上使用"开放征询 + 自己先垫底"格式**（先给自己的粗答案，降低回答门槛）：
> "**Which are the most common everyday phenomena that we don't properly understand? Off the top of my head:** • Lightning (how does it happen?) • Sleep; dreams (why do they exist?) • Glass (thermodynamics of formation) • Turbulence (when does it start?) • Morphogenesis (how does…"
> — https://x.com/patrickc/status/2053103361176813791

> "**Which are the most humane (empathetic, compassionate) Arab / Middle Eastern novels? Thought behind the question:** I read a bunch of these novels last year -- my selection algorithm was to sample widely among the award-winning works from the region (Egypt, Sudan, Iran, Palestine,…"
> — https://x.com/patrickc/status/2048403447045849516
> —— 注意 "**Thought behind the question:**" 这个显式的元结构标签，以及把读书说成 "**my selection algorithm**"。

> "**Who's doing exciting/ambitious desktop OS work?** While mobile gets all the attention, we still spend a lot of time in front of our computers, and it feels like the host environment could be doing a lot more heavy lifting (particularly as a meta tool for thought) than it is."
> — https://x.com/patrickc/status/1316475471203360769

### 5.3 口头提问（他采访 Tyler Cowen，20 条逐字）

来源：https://conversationswithtyler.com/episodes/patrick-collison/

**特征：口头提问比书面提问短得多，且大量使用"逼供式量化"——要求对方给出比例、排名、数量。**

> "You've published 15 books? Is that the right count?"
> "Do you agree with Paul?"
> "What do you think of the paper itself and the claims in it?"
> "To what degree do you have confidence that economics will ever get to durable answers to these questions?"
> "Will it always be retrodictive, or does it become predictive at some point?"
> "OK, on what basis should we then be making macroeconomic decisions?"
> "**What fraction of tenured economists in the US do you think would agree with your take** on the predictive power of macroeconomics?"
> "**What field outside of economics has the most to say about** macroeconomics?"
> "**What are the, say, top two most underinvested areas of economics today?**"
> "Is it not too hasty to advocate for a force that's producing a net reduction in the quantity of it in the world?"
> "On this point, would you write the same book today?"
> "**Say more.**"
> "Can you say a bit more about the concept of diversity with regard to culture or ideas or whatever?"
> "Are successful clusters places with the right kind of diverse monoculture?"
> "Can you describe why you changed your mind?"

**口头提问模式统计（n=20）：**
- **要求量化的问题：4 / 20 = 20%**（"What fraction…"、"top two…"、"To what degree…"、"Is that the right count?"）
- **极短追问（≤4 词）：2 / 20**（"Say more."、"Do you agree with Paul?"）
- **二选一逼问（A, or B?）：2 / 20**（"Will it always be retrodictive, or does it become predictive at some point?"）
- **明确的元导航（宣告话题切换）：** "I want to actually get back to the topic of weirdness a little bit later on, but quickly, before we shift focus from Silicon Valley…"

---

## 6. 幽默样本：他开玩笑吗？什么类型？

**结论：开，但极稀疏、极干、几乎全部是自嘲或对自身处境的元评论。从不用笑话来攻击别人，也从不用来活跃气氛。**

**量化：**
- ~650 条 HN 评论全量搜索：`haha` 命中 **1 条**（且原文是 "Hah."），`lol` **0 条**。
- 68 条主语料中，可识别为"意图幽默"的句子约 **5–6 处 ≈ 每 1,200 词 1 处**。
- 幽默载体：**ASCII 颜文字 `:-)`、省略号 `...`、自嘲、括号里的元评论。**

**逐字样本（按类型）：**

**(a) 自嘲型（最主要）**
> "But having good social skills confers life-long benefits. So, don't write them off. Get good at making a good first impression, **being funny (if possible... this author still working on it...)**, speaking publicly."
> — https://patrickcollison.com/advice
> —— **他在教人要幽默的同一句话里承认自己不幽默。这可能是全语料最能代表他幽默观的一句。**

> "This is slightly off-topic (**I'm going to be that \"this is sorta more a comment than a question...\" guy for a second**), but I just want to say that Scott's blog is one of my favorite blogs on the whole internet. If only there were more like it!"
> — https://news.ycombinator.com/item?id=17425599

**(b) 干式反讽 / 学究式冷笑话（早期 HN 尤多）**
> "Also, with regard to SlutBot's use... **is it still entrapment if the bot does it?**"
> — HN 评论（Algolia objectID 检索自 author_pc + "obviously"），Turing Test 话题

> "I know some COBOL consultants who'd disagree."
> — https://news.ycombinator.com/item?id=97685（2008 年，回应"某技术已死"）

**(c) 对自己所处荒谬情境的元评论**
> "For whatever reason, those stories don't get upvoted as much on HN :-)."
> — https://news.ycombinator.com/item?id=17554858（在为 Stripe 的正面消息辩护时，顺带调侃 HN 的负面偏好）

> "**Fair :-).** \"A little\" relative to market cap. But, yes, $600M is a staggering amount of money in absolute terms."
> — https://news.ycombinator.com/item?id=22890205（有人吐槽他把 6 亿美元说成 "a little"）

> "**To hijack our own thread:** there was a lot of discussion on HN last week about…"
> — https://news.ycombinator.com/item?id=7400884

> "If any PayPal folks are reading, I'm patrick@stripe.com :-)."
> — https://news.ycombinator.com/item?id=7938622

**(d) 引用别人的俏皮话（他更愿意转述别人的机智，而不是自己产出）**
> "\"We need less Less Wrong and more More Right.\" —@peterthiel"
> — https://x.com/patrickc/status/724291528772837378

**(e) 对弟弟 John Collison 的一句极简吐槽（唯一一条明确的玩笑式回复）**
> "@collision are you sure this was in the talking points"
> — https://twitter.com/patrickc/status/821127653189005313

**幽默的禁区：** 找不到任何一处 (1) 拿竞争对手开玩笑、(2) 拿用户/员工开玩笑、(3) 双关语堆砌、(4) 网络梗、(5) 政治笑话。

---

## 7. 公开分歧：他跟谁公开不同意过？

**总体判断：他是硅谷公众人物里树敌最少的之一。这不是因为他没有意见，而是因为他有一套明确的分歧纪律。全语料没有找到任何一次他公开点名批评某个具体人物的观点。**

### 7.1 他确实公开分歧过的对象（按对手类型分类）

| 对象 | 分歧内容 | 他的表达方式 | 来源 |
|---|---|---|---|
| **HN 上指控 Stripe 的匿名用户** | 指控 Stripe 恶意收购、控制 HN 排名 | "I don't think some of the claims in this comment are true **or in good faith**." 括号内逐条列举反证，然后 "**All of that said**, I'd appreciate hearing from any founders who feel mistreated…" | [29388863](https://news.ycombinator.com/item?id=29388863) |
| **对 Sabine Hossenfelder 进行人身攻击的评论者** | 他反对的是**攻击方式**，不是任何一方的物理学观点 | "This is an **ad hominem attack** that doesn't really help us understand whether the core substance of her argument is <i>true</i>, which is what really matters." | [19129369](https://news.ycombinator.com/item?id=19129369) |
| **质疑他没有科研经验、无资格谈科学进步的人** | 他承认对方的质疑合理，但要求对方攻击论点 | "I think it's **very reasonable for someone to raise an eyebrow at this**, though **I'd love to know where I'm <i>wrong</i>** rather than just lacking in relevant experience." | [19020333](https://news.ycombinator.com/item?id=19020333) |
| **/fast 页面的"安全成本论"批评者** | 他不接受"现在慢是因为更安全"的解释 | 用 WTC vs 帝国大厦的死亡人数数据反驳，同时承认 "I haven't found a satisfying explanation" | [30874081](https://news.ycombinator.com/item?id=30874081) |
| **反 YIMBY 的评论者（称 CA YIMBY 打压少数族裔）** | 事实层面直接纠正 | "polling **very clearly shows** that minority groups strongly support increased housing construction… **CA YIMBY was not involved in the protest you mention. I think you're confusing them with other groups.**" | [16990120](https://news.ycombinator.com/item?id=16990120) |
| **"Fed 停止发布 M1 数据"标题党** | "**The title is false.**" | 三行事实纠正 + 一行"你可能想说的其实是另一件事" | [26906948](https://news.ycombinator.com/item?id=26906948) |
| **称 Inbox 不是"平台"的评论者** | 定义之争 | "**That's unfair** -- not all platforms have IETF specs (iOS, Android, AWS, etc)." | [8002172](https://news.ycombinator.com/item?id=8002172) |
| **前 Balanced 员工（竞品）** | 事实有误，但他拒绝纠缠 | "Hm. There are actually a bunch of inaccuracies in the above, **but I don't think there's much point arguing about the details** -- specifics aside, I agree that Balanced has quickly launched some cool stuff. **Congrats… and good luck with whatever comes next!**" | [7785535](https://news.ycombinator.com/item?id=7785535) |
| **加密货币怀疑论者（HN 集体）** | 这是他 2025 年最系统的一次反驳 | 他不说"你们错了"，而是说 "**it might be interesting to share what changed our mind**"，然后把对手最强的论点（"这只是监管套利"）单独拎出来正面处理：**"a reflexive answer frequently invoked here is \"it's regulatory arbitrage\", but I think this is some combination of misguided and incurious as an explanation."** | [45129554](https://news.ycombinator.com/item?id=45129554) / [45131717](https://news.ycombinator.com/item?id=45131717) |
| **@rabois 及其辩论对手（"努力工作是否重要"）** | 他公开介入了一场硅谷争论 | 开场就是审美式的中立：**"I've been enjoying reading @rabois's debate with others over past day or two on the importance of hard work."** | [tweet 869785266327769088](https://x.com/patrickc/status/869785266327769088) |
| **Sam Altman 的创业者签证提案（部分保留）** | 他为提案辩护，但公开说明自己不舒服的地方 | "**conferring immigration status upon acceptance by an arbitrarily-designated institution makes me uncomfortable too.** However, it's a ship that sailed a long time ago." + "**I completely agree with you that a steady-state world of privileged visa-granters is not what we should be trying to bring about.**" | [7419405](https://news.ycombinator.com/item?id=7419405) / [7419450](https://news.ycombinator.com/item?id=7419450) |

### 7.2 他的"分歧纪律"（可提炼为规则）

1. **攻击论点，从不攻击人。**（唯一一次批评人，批评的是语气：""Your comment is needlessly mean-spirited."）
2. **分歧前必须先给一个真实的让步**，且让步内容必须具体到对方能认出来。
3. **分歧时提高而非降低不确定性标记**：他反驳时用的 hedge 比他陈述时更多（"I'm trying to not overstate my certainty"）。
4. **拒绝把分歧升级**："I don't think there's much point arguing about the details"。
5. **主动为对方提供反驳自己的路径**："I'd love to know where I'm wrong"、"I'd certainly be interested in a more comprehensive investigation"。
6. **用"incurious"而非"stupid"作为最重的评价词**——他能给出的最严厉的智力批评是"缺乏好奇心"。

> **最重的一次措辞（全语料最强）：** "…but I think this is **some combination of misguided and incurious** as an explanation." — https://news.ycombinator.com/item?id=45131717

---

## 8. 风格标签打分

每项 0–10，附证据。

### 8.1 正式 ↔ 口语　→　**位置：4/10（偏口语）**
- **口语侧证据**：6.4% 的句子以 And/But 开头；`but`:`however` = 14.7:1；使用 "Yeah"、"Yep"、"Hm."、"Ugh"、"kinda"、"sorta"、"'till"、"lemme check..."；ASCII 颜文字。
- **正式侧证据**：`a priori`、`de facto`、`per se`、`dispositive`、`heterogeneity`、`monocausal`、`status quo ante`、`orthogonal`、`O(n)`。
- **判定：这是一个"高学历口语"——词汇量学术，句法和语气口语。** 他把拉丁语插进 "Yeah, good question" 之后完全不违和。

### 8.2 抽象 ↔ 具体　→　**位置：7/10（偏具体）**
- 具名实体密度 **16.8/千词**（每 60 词一个专有名词），数字 5.4/千词。
- 反例：他确实爱造抽象名词（`pace layering`、`general execution capital`、`replacement rate`、`legible domains`）。
- **判定：他的模式是"抽象概念 + 立刻用具名案例落地"。** 例："We think a lot about **pace layering** — how do we have teams that think on multi-year horizons (infrastructure, security, etc.) alongside teams that are rapidly iterating…"（抽象词 → 破折号 → 具体机制）

### 8.3 谨慎 ↔ 断言　→　**位置：3/10（明显偏谨慎）**
- hedge : certainty = **1.95 : 1**；`I think` 占全部 hedge 的 30%。
- 断言词几乎全部用于让步、事实或承诺，而非强化观点。
- **例外场景（他会变断言）**：(1) 事实纠错（"The title is false."）；(2) 道德底线（"That would be dishonest and stupid."）；(3) 产品承诺（"We will definitely keep it."）。

### 8.4 学术 ↔ 通俗　→　**位置：6/10（略偏学术）**
- 引用习惯：在一条 HN 评论里挂 4 个学术脚注（Chicago Booth 论文、Urban Institute PDF、白宫报告、Richard Rothstein 的书）—— [16988398](https://news.ycombinator.com/item?id=16988398)
- /questions 页面引用 Bloom、Schumpeter、Rehfeld (2018)、Maslin (2001)、Milankovitch、Cohen's d、五因素人格模型。
- **但**：句子结构完全不学术（无被动语态堆叠、无名词化长链），标题可以是 "What's going on with infrastructure?"。
- **判定：学术的是他的引用和参照系，不是他的句法。**

### 8.5 长句 ↔ 短句　→　**位置：5/10（中位，但方差极高）**
- 平均 18.6 词 = 标准英语写作中位；**但标准差 11.46，25.5% 的句子 ≤10 词，12.8% 的句子 ≥31 词。**
- **判定：不是"长句作者"也不是"短句作者"，是"长短交替作者"。** 复刻他的关键不是控制平均句长，而是**保证每个长句后面跟一个短句**。

### 8.6 铺垫型 ↔ 结论先行　→　**位置：3/10（明显铺垫型）**
- 句首词分布中，`If` 占 4.3%、`While` 2.1%——条件与让步前置。
- 长评论固定结构是 `身份 → 致意/致歉 → "A few points:" → 列点 → "All that said," 软化`。
- 78% 的评论含括号插入语，绝大多数是**在结论出现之前**先塞进限定条件。
- **唯一的结论先行场景**：事实纠错（"The title is false." / "Definitely not."）和一句话回复（"Yep."）。
- **判定：只要话题涉及判断，他一定先铺垫；只要话题涉及事实，他立刻结论先行。**

### 8.7 数据驱动 ↔ 叙事驱动　→　**位置：6/10（略偏数据，但方式特殊）**
- 数字密度 5.4/千词、8.8% 的句子含数字——**在 CEO 里算中高，但不算重度量化写作者**。
- 具名实体密度是数字的 3.1 倍。
- **他的真实模式不是"用数据说话"，而是"用可核验的具体物说话"**：一个公司名、一个国家、一个法案、一个比率、一个日期——只要读者能自己去查。
- **在 /questions 和 /fast 页面上他切换到重度数据模式**（"37x more expensive per station"、"93x more"、"410 days"、"143 days"），因为那里的目的是**建立一个现象确实存在**。
- **判定：数据是他用来"证明问题存在"的工具，不是用来"证明自己正确"的工具。**

---

## 9. 可执行的仿写清单（把上面所有数字压成规则）

**必须做：**
1. 平均句长控制在 **18–19 词**，但**每 4 句里至少 1 句 ≤10 词**。
2. **每 3.2 句放一个转折/让步词**；优先级 `but` > `still` > `though`（后置）> `while`（句首）> `that said`；**不用 `however`**。
3. **每 3.7 句放一个括号插入语**，内容是"预防性让步 / 限定条件 / 元评论"，不是补充信息。
4. **观点必挂 hedge**（`I think` / `I suspect` / `it seems` / `somewhat` / `might`），**事实可裸奔**。hedge:certainty 保持 **2:1**。
5. **人称开关**：谈公司用 `we`（I:we = 1:1.68），谈观点用 `I`（I:we = 3.3:1），给建议用 `you`（不用 we）。
6. **每 60 词出现一个专有名词**（公司/国家/产品/法案/人名）。
7. 数字必带**基准或倍数**（"down 50% since earlier this year"，不是 "greatly reduced"）。
8. 长文用固定骨架：`身份声明 → 一句致意或致歉 → "A few points:" → 列点 → "All that said," 收尾`。
9. 表达不同意时：**先具体让步 → but/that said → 攻击论点 → 给对方一条反驳自己的路**。
10. 承认无知时**划出边界**："I don't know X, and I don't even know whether X is true."

**绝对不做：**
1. 不用 emoji（Unicode）。ASCII `:-)` 可用，但只在感谢/自嘲场合。
2. 不用感叹号强调论点（感叹号只给感谢、招募、道歉）。
3. 不用任何营销黑话（disrupt / synergy / 10x / seamless / world-class / game-changer / leverage / empower / frictionless……实测全部 0 次）。
4. 不做人身攻击；最重的评价词是 **"incurious"**、"misguided"、"not in good faith"、"needlessly mean-spirited"。
5. 不贬低竞争对手（反而主动称赞）。
6. 不宣称自己/自家产品是"最好"；每次自夸后必跟 "we still have a lot of work to do"。
7. 不用全大写强调（用斜体）。
8. 不用党派政治语言。
9. 不用"haha/lol"。
10. 不把分歧升级为冲突——分歧后用祝福收尾。

---

## 10. 抓取失败/反爬的高价值来源

### 10.1 X / Twitter @patrickc —— **严重受限，需要人工补充（最高优先级）**

| URL / 来源 | 状态 | 原因 | 价值 |
|---|---|---|---|
| `https://x.com/patrickc` 及所有 `x.com/patrickc/status/*` | **完全抓不到** | WebFetch 返回 `ROBOTS_DISALLOWED`（x.com 的 robots.txt 禁止） | ★★★★★ 他的主战场。**本报告的推文样本只有 15 条、648 词，其中 10 条被搜索引擎的 title 长度截断**，全部长推的后半段缺失 |
| `https://xcancel.com/patrickc` | **抓不到** | `ROBOTS_DISALLOWED` | ★★★★★ Nitter 镜像，本可绕过 |
| `https://nitter.net/patrickc` | **已死站** | 页面显示 zedeus 于 **2026-08-25**（两天前）宣布 nitter.net 因 X Corp. **2026-08-24 发出的 cease and desist** 而下线 | ★★★★★ 曾是最佳镜像 |
| `https://www.tweetsearch.co/patrickc-top-10-tweets` | **抓不到** | robots.txt 获取失败（DNS 解析失败：`Name or service not known`） | ★★★★ 高赞推文排行 |
| 直接 `curl` 任意外网 | **全部 403** | 本会话的出口代理策略拦截（`gateway answered 403 to CONNECT`），已确认被拦：`patrickcollison.com`、`conversationswithtyler.com`、`tim.blog`、`hn.algolia.com` | — |

**唯一奏效的 X 抓取通道**：搜索引擎返回的结果 title 本身就是推文原文（格式 `Patrick Collison on X: "……" / X`），但**被 title 长度截断在约 280 字符**。本报告的推文样本全部由此获得。

**需要人工补充的具体内容：**
- **他的回复（reply）**——本报告 **0 条 X 回复样本**。任务书正确指出 reply 最能看出即兴风格，但这部分完全缺失。他的 HN 回复补上了这个缺口，但 X 的社交语境不同。
- **他的引用转推（quote tweet）**——**0 条样本**。这是他表达"温和不同意"的主要场所，缺失严重。
- **高赞推文排行**——无法获得点赞数，因此无法判断"哪些表达最具代表性"。
- **长推文的完整正文**——以下 10 条已确认存在但只有开头：
  - https://x.com/patrickc/status/1843330133895323792 （distraction / continuous partial attention，2024-10）
  - https://x.com/patrickc/status/1969826678307496356 （US manufacturing 的两种视角，2025-09）
  - https://x.com/patrickc/status/1980285288867066175 （pandemic 的非疫情影响，2025-10）
  - https://x.com/patrickc/status/2077048835483013186 （UK ONS 统计准确性，2026-06）
  - https://x.com/patrickc/status/1967346630539333662 （Reddit 与慢性病，2025-09）
  - https://x.com/patrickc/status/2048403447045849516 （阿拉伯/中东小说，2026-02）
  - https://x.com/patrickc/status/2083931939673878592 （Why Aesthetics，2026-07）
  - https://x.com/patrickc/status/2053103361176813791 （日常未解现象清单，2026-03）
  - https://x.com/patrickc/status/2045164908912968060 （Genome Agents / 预防医学，2026-01）
  - https://x.com/patrickc/status/1825618450837885036 （回复 @Scholars_Stage 的书单，2024-08）

**人工补充建议**：**直接抓 https://patrickcollison.com/dispatches** —— 这是他自己把 X 长文重发在个人站上的合集（"A selection of longer posts originally published on X"），已确认存在以下条目：Why Aesthetics (2026-08-02)、Paris (2026-06-20)、New Aesthetics (2026-05-25)、Genome Agents (2026-04-17)、Ten Novels (2024-12-27)。这个页面**没有 robots 限制**，只是被 WebFetch 的版权保护策略限制了长篇逐字输出。人工打开浏览器即可获得全文，是补齐 X 长文语料的最低成本路径。

### 10.2 其他受限来源

| 来源 | 状态 | 原因 | 价值 |
|---|---|---|---|
| `https://patrickcollison.com/questions` 正文 | **仅得摘要** | WebFetch 内部模型以版权为由拒绝输出多段逐字文本（只肯给 ≤125 字符的短引） | ★★★★★ 22 个问题的**正文**是他"提问句式"的最佳语料。本报告的问题标题逐字准确，但**正文只有转述**，未用于任何统计。**建议人工复制全文。** |
| `https://patrickcollison.com/fast` 正文 | **仅得结构 + 首尾短引** | 同上 | ★★★★ 每条目"实体 + 天数 + 来源"的极简句式，是他"数据驱动写作"的纯样本 |
| `https://patrickcollison.com/dispatches` 正文 | **仅得结构 + 5 条首句** | 同上 | ★★★★★ 见上，X 长文的镜像 |
| `https://stripe.com/.../ceo-patrick-collisons-email-to-stripe-employees`（2022 裁员信） | **仅得摘要 + 零星短引** | WebFetch 输出了结构化摘要而非逐字全文 | ★★★★ 他最重要的一篇**长篇正式写作**（危机沟通）。本报告未把它计入任何统计。建议人工补全。 |
| HN Algolia 按热度排序端点 `search?tags=comment,author_pc` | **部分拒绝** | 同一 API，`search_by_date` 端点正常返回逐字全文，但 `search`（按热度）端点的请求被内部模型以版权为由拒绝逐字输出 | ★★★ 会漏掉"他最高赞的评论"。**但注意：该次调用泄露了一个有用元数据 —— 用户 `pc` 的评论总数约 650 条，跨 2007–2025。** |
| HN 分页 gap | **有缺口** | `search_by_date` 的 page 0/1/2 各返回 100 hits，但 WebFetch 的转换模型每页只逐字渲染了约 55–80 条，**2015-03 至 2017-04 之间存在渲染缺口** | ★★★ 缺失约 2015–2017 年的评论。不影响结论（风格在 2014–2025 高度稳定），但样本可以更大 |
| `threadreaderapp.com/user/patrickc` 的 thread ID | **未获得** | 页面渲染后未保留链接 URL | ★★★ 7 条已展开长 thread（2017–2021）的完整正文，包括 **2017-05-31 的 "hard work debate" thread**（他罕见的公开介入争论） |

### 10.3 已成功抓取、可复用的通道（供后续调研参考）

- ✅ **HN Algolia `search_by_date` 端点 + WebFetch**：`https://hn.algolia.com/api/v1/search_by_date?tags=comment,author_pc&hitsPerPage=100&page=N`，逐字保真，是本报告的主语料来源。
- ✅ **HN Algolia 关键词检索 + `restrictSearchableAttributes=comment_text`**：可用于全语料词频统计（返回 `nbHits`）。已实测：`sorry` = 27、`obviously` = 18、`that said` = 15、`disagree` = 3、`haha` = 1、`funny joke haha` = 0。
- ✅ **`conversationswithtyler.com` + WebFetch**：口语提问逐字可得。
- ✅ **`patrickcollison.com/advice`**：唯一一个 WebFetch 愿意全文输出的官网页面（篇幅较短）。
- ✅ **WebSearch 的结果 title**：X 推文原文的唯一可用通道（有 ~280 字符截断）。

---

## 附：语料文件位置

- `/root/pc_corpus/hn.txt` —— 68 条 HN 评论逐字语料（6,984 词）
- `/root/pc_corpus/tweets.txt` —— 15 条推文逐字语料（648 词，10 条截断）
- `/root/pc_corpus/advice.txt` —— /advice 页面逐字语料（632 词）
- `/root/pc_corpus/analyze.py` —— 全部统计的计算脚本，可复算
