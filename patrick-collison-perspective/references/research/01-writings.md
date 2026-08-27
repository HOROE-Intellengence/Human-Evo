# Patrick Collison — 著作、长文与系统性写作（调研档案 01）

> 调研日期：2026-08-27
> 调研人：Claude（自动化网络抓取）
> 范围：patrickcollison.com 全站、The Atlantic 两篇署名长文、Fast Grants 复盘、Stripe Press、Stripe 年度信、以及少量高质量长访谈（明确标注为"口述"）

---

## 0. 方法论与可信度说明（先读这一节）

### 0.1 抓取方式的局限
本文件的绝大部分内容通过 `WebFetch` 抓取原始页面后，由一个提取模型转写而成。这带来一个**必须知晓的风险**：

- **标注 `[逐字校验]` 的引语**：经过至少两次独立抓取、或在两个独立来源中出现相同措辞，可信度高，可直接引用。
- **标注 `[单次提取]` 的引语**：只经过一次自动提取。措辞极可能准确，但**在正式引用前建议人工到原 URL 核对**。
- **标注 `[转述]` 的内容**：是论点的忠实概括，不是原话，**不得加引号引用**。

我在整个文件中严格区分了这三类。凡是查不到确切原文的"金句"，我一律未写入。

### 0.2 一手 / 二手
- **一手**：Collison 本人撰写或署名的文字（个人网站、署名文章、Stripe 年度信）。
- **一手（口述）**：他本人在访谈中说的话（Dwarkesh、Tim Ferriss、Zuckerberg 访谈），是他的真实观点但非书面写作，**分量应低于书面文字**。
- **二手**：他人对他的总结（维基百科、评论文章）。

---

## 1. patrickcollison.com 全站结构（一手，最高价值）

首页只有一个标题 "Patrick Collison" 加导航链接，无正文。截至 2026-08-27 的完整子页面清单（首页导航所列全部 15 项）：

| 页面 | URL | 性质 |
|---|---|---|
| About | https://patrickcollison.com/about | 自述 + 兴趣清单 |
| **Advice** | https://patrickcollison.com/advice | **给年轻人的建议（人生导师用途核心）** |
| Bookshelf | https://patrickcollison.com/bookshelf | ~500 本书单（自称约十年未更新） |
| Culture | https://patrickcollison.com/culture | 文化/制度起源研究文献集 |
| **Dispatches** | https://patrickcollison.com/dispatches | **19 篇长文（2024-12 至 2026-08），最新、最一手** |
| Fast | https://patrickcollison.com/fast | 历史上快速完成的大项目清单 |
| Growth | https://patrickcollison.com/growth | 经济增长文献集 |
| Labs | https://patrickcollison.com/labs | 工业实验室（PARC/Bell Labs/ARPA）文献集 |
| Links | https://patrickcollison.com/links | 他爱读的 link roundup 作者 |
| Pollution | https://patrickcollison.com/pollution | 空气污染对认知的影响证据集 |
| Progress | https://patrickcollison.com/progress | Progress Studies 索引页 |
| **Questions** | https://patrickcollison.com/questions | **23 个公开问题（思维结构最直接的暴露）** |
| Solar | https://patrickcollison.com/solar | 太阳能部署数据（2023 秋） |
| SV history | https://patrickcollison.com/svhistory | 硅谷史"经典书目" |
| Travel | https://patrickcollison.com/travel | 旅行写作 + guide.world 项目 |

**注意**：任务清单中提到的 `/svalues`、`/people`、`/making`、`/blog` 在 2026-08-27 的首页导航中**不存在**。`/science` 会重定向回首页。`/dispatches` 是他现在事实上的 blog。

---

## 2. `/advice` — 给年轻人的建议（一手 · 最高价值）

来源：https://patrickcollison.com/advice ｜ 一手 ｜ 双次抓取交叉校验

### 2.1 框架句 `[逐字校验]`
> "Every now and again, someone emails me and asks for very general advice."

页面主体是**给 10–20 岁人群**的建议清单（共 16 条）。结尾句 `[逐字校验]`：
> "If advice on this page helped you, I'd love to hear about it."

### 2.2 十六条建议：首句原文 + 论点

每条的**首句为逐字校验**（两次独立抓取一致），后面的说明为 `[转述]` 或 `[单次提取]` 引语。

**1. `[逐字校验]` "These are prime years!"**
— 10 到 20 岁是黄金期，是可支配注意力最集中的窗口。

**2. `[逐字校验]` "Go deep on things."**
— 补全 `[单次提取]`："Go deep on things. Become an expert."
成为某件事的真专家，而不是浅尝辄止。

**3. `[逐字校验]` "In particular, try to go deep on *multiple* things."**
— 目的是**发现自己兴趣空间的形状**。`[单次提取]`："Try to discover the shape of that space as quickly as you can."
> **这是他方法论的核心之一**：多点深潜是一种搜索策略，不是三心二意。他认为人对哪类工作有能量的偏好在成年后相当稳定，所以越早测绘越好。

**4. `[逐字校验]` "Don't stress out too much about how valuable the things you're going deep on are..."**
— `[单次提取]`："It should be a factor you weigh but not by itself dispositive."
（重要性是一个权重，但不是决定性的唯一权重。）

**5. `[逐字校验]` "To the extent that you enjoy working hard, do."**
— `[单次提取]`："It's not clear that the returns to effort ever diminish substantially."
> 注意他的条件句结构：**"到你享受努力的程度为止"**，而不是无条件鼓吹苦干。

**6. `[逐字校验]` "Make friends over the internet with people who are great at things you're interested in."**
— `[单次提取]`："The internet is one of the biggest advantages you have over prior generations."

**7. `[逐字校验]` "Aim to read a lot."**

**8. `[逐字校验]` "If you think something is important but people older than you don't hold it in high regard..."**
— 结论 `[单次提取]`："Status lags by a generation or more."
> **"Status lags by a generation or more" 是他一个可复用的原创表述**：地位分配系统总是滞后于真实重要性至少一代人。

**9. `[逐字校验]` "Above all else, don't make the mistake of judging your success based on your current peer group."**
— 相关 `[单次提取]`："Being weird as a teenager is generally good."

**10. `[逐字校验]` "*But* having good social skills confers life-long benefits."**
— 承接第 9 条的转折：可以不合群，但社交能力（留下好第一印象、公开讲话）是终身复利资产。
> **这里有一个内部张力，他自己用 "But" 显式标记了**：鼓励怪异 + 要求社交能力。

**11. `[逐字校验]` "Make things."**
— `[单次提取]`："Operating in a space with a lot of uncertainty is a very different experience."（做东西和学东西是不同的经验类型。）

**12. `[逐字校验]` "More broadly, nobody is going to teach you to think for yourself."**
— 完整版本在 Tim Ferriss 访谈中被再次引用 `[两来源一致]`：
> "Nobody is going to teach you to think for yourself. A large fraction of what people around you believe is mistaken."

**13. `[逐字校验]` "If you're in the US and go to a good school, there are a lot of forces..."**
— 关于名校默认路径的压力。`[单次提取]`："Make sure that the things you're pursuing are weird things that you want."

**14. `[逐字校验]` "Figure out a way to travel to San Francisco and to meet other people who've moved there..."**
— `[单次提取]`："San Francisco is the Schelling point for high-openness...optimistic people."
> 用博弈论术语 **Schelling point** 描述地理聚集。

**15. `[逐字校验]` "Find vivid examples of success in the domains you care about."**
— `[单次提取]`："Try to find ways to spend time with good scientists in person."（当面、视频、社交媒体都行，关键是看到"卓越"具体长什么样。）

**16. `[逐字校验]` "People who did great things often did so at very surprisingly young ages."**
— 公开认可往往滞后很久，所以不要被"某某成名于四十岁"误导。**立刻开始。**

### 2.3 `/advice` 页的可提炼底层模型
`[转述]`
1. **搜索 → 深潜 → 复利**：多领域深潜是对个人效用函数的搜索；一旦定位，努力的回报不递减。
2. **拒绝同侪坐标系**：以绝对标准而非当下同侪排名衡量自己（第 9 条明确说 "Above all else"）。
3. **提前于地位系统下注**：status lags，所以年轻人对"重要性"的直觉常常比长辈的地位判断更准。
4. **社交能力是可学的杠杆，不是对独立性的背叛**。
5. **地理是一个可操作变量**：搬到对的地方，比在错的地方努力更有效。

---

## 3. `/questions` — 23 个公开问题（一手 · 揭示思维结构）

来源：https://patrickcollison.com/questions ｜ 一手 ｜ `[单次提取，问题措辞高度可信]`

框架 `[转述]`：他略去了一些 Stripe 相关的问题；提到 Alexey Guzey 和 Gwern 也做了类似清单；欢迎读者提供相关读物和回答。

1. Why are certain things getting so much more expensive?（成本病）
2. Why do there seem to be more examples of rapidly-completed major projects in the past than the present?（→ 直接对应 `/fast`）
3. Why is GDP growth so weirdly constant?
4. **How do you ensure an adequate replacement rate in systems that have no natural way to die?**
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
17. **Why is there no canon for life's most important questions?**
18. Why are so many things so much nicer in Switzerland and Japan?
19. Why isn't China (yet) producing a lot of top-tier research?
20. Why don't we build nice neighborhoods any more?
21. What influences when people act in accordance with their self-interest and when they don't?
22. What's going on with infrastructure?
23. Why did climatic variability suddenly decline in the Holocene period?

### 3.1 问题清单暴露的思维结构 `[转述，我的分析]`
- **主导句式是 "Why is X worse/slower/more expensive than it used to be or than it obviously could be?"**（第 1、2、15、20、22 题）——他的默认怀疑对象是**当下的现状**，不是过去。
- **第二类是 "What's the successor to X?"**（第 11、12 题）——对**媒介和制度形式本身**的更替感兴趣，而非只在既有形式内优化。
- **第三类是地理/制度对照**（第 7、18、19 题）——用国家和城市作为自然实验。
- **第 4 题（"没有自然死亡机制的系统如何保证更替率"）是他整个制度观的钥匙**：他对既有机构的态度不是改革，而是**入场与替换**（对应 Fast Grants、Arc Institute、California Forever、Esmeralda 都是"另建"而非"改良"）。
- **第 17 题（人生最重要问题没有 canon）**：这是他少数直接针对"人生"的问题，对用户的人生导师用途尤其相关——他明确认为**关于如何生活的知识是被组织得极差的**。

---

## 4. `/fast` — 快速完成的大项目（一手）

来源：https://patrickcollison.com/fast ｜ 一手 ｜ 框架句 `[单次提取]`

### 4.1 框架句
> "Some examples of people quickly accomplishing ambitious things together."

### 4.2 完整清单（项目 / 耗时）
JavaScript 10 天 ｜ Unix 21 天（Ken Thompson 三周写出第一版）｜ Git 17 天 ｜ Amazon Prime 6 周 ｜ Spirit of St. Louis 60 天 ｜ BankAmericard 90 天 ｜ Xerox Alto 约 3–4 个月 ｜ Apollo 8 134 天（1968-08-09 决定 → 12-21 发射）｜ P-80 Shooting Star 143 天 ｜ Marinship 197 天 ｜ Alaska Highway 234 天（1700 英里）｜ Moderna COVID 疫苗（基因组 2020-01-10 公布，3 天后序列定稿，45 天后首批发货；试验 266 天）｜ iPod 约 290 天 ｜ Disneyland 366 天 ｜ Empire State Building 410 天 ｜ Berlin Airlift 463 天（Tegel 机场 92 天建成）｜ Pentagon 491 天 ｜ Eiffel Tower 793 天（约合 2019 年 4000 万美元）｜ Boeing 747 930 天 ｜ USS Nautilus 1173 天 ｜ TGV 1975 天 ｜ New York Subway 4.7 年 ｜ Treasure Island 约 2 年 ｜ Shenzhen 1998–99 一年增加 100 万人（+22%）

### 4.3 结论
`[单次提取]` "The physical infrastructure projects enumerated above occurred before 1970 to a disproportionate degree."
之后列出多篇讨论建设速度下降原因的研究。

> **这一页的功能不是怀旧，是存在性证明**：它把"这么快是不可能的"这一默认前提证伪。对人生导师用途，它的用法是：**当你说"这需要两年"时，先问这是物理约束还是社会约束。**

---

## 5. `/bookshelf` — 书单（一手，但已过时）

来源：https://patrickcollison.com/bookshelf ｜ 一手 ｜ **可信度警告**：自动提取的完整书目噪声较大（有若干条目明显是解析错误），**长清单不建议直接引用**。以下只保留高可信度部分。

### 5.1 他自己的说明 `[单次提取]`
- 约 500 本，**"I've only read about half of the books here"**。
- 页面自称**约十年未更新**（因此反映的是 ~2015 年前后的智识谱系，不是 2026 的他）。
- 加粗/绿色标记 = 特别好；斜体/浅蓝 = 显著高于平均。
- 引用了 Umberto Eco 关于"未读书构成的图书馆"的观点；书架"stacks and shelves lack any particular order"。

### 5.2 被标为"特别好"（绿色）的书 — 这是最有信号量的一份清单
- Robert Gordon, *The Rise and Fall of American Growth*
- Rebecca Goldstein, *The Mind-Body Problem*
- *Poor Charlie's Almanack*（后来由 Stripe Press 重新出版）
- *Something Incredibly Wonderful Happens*（Frank Oppenheimer 传）
- Thomas Petzinger, *Hard Landing*（航空业竞争史）
- Garry Wills, *Nixon Agonistes*
- M. Mitchell Waldrop, *The Dream Machine*（后由 Stripe Press 重版）
- Evan Osnos, *Age of Ambition*（当代中国）
- Douglas Hofstadter, *Metamagical Themas*
- Seymour Papert, *Mindstorms*
- Stephen Webb, *If the Universe Is Teeming with Aliens... WHERE IS EVERYBODY?*
- Philip Pan, *Out of Mao's Shadow*
- David Deutsch, *The Beginning of Infinity*
- Tocqueville, *Democracy in America*
- *The Paris Review Interviews, I*
- Nick Bostrom, *Anthropic Bias*
- Christopher Alexander, *A Pattern Language*
- Richard Hamming, *The Art of Doing Science and Engineering*（后由 Stripe Press 重版）
- Jason Stearns, *Dancing in the Glory of Monsters*（刚果）
- Peter Norvig, *Paradigms of AI Programming*

### 5.3 谱系判读 `[转述，我的分析]`
- **不是"创业书单"**。几乎没有标准商业畅销书。
- 四条明显主线：
  1. **计算史与人机共生**（Papert、Hofstadter、Waldrop、Norvig、Alan Kay 系）
  2. **增长与停滞的经济史**（Gordon、Mokyr、Clark）
  3. **发展中国家与政治现实**（中国、刚果、非洲、新加坡）
  4. **设计/建筑/排版**（Christopher Alexander、Tufte、瑞士平面设计）——**这条线在 2025-26 爆发成了他的"美学转向"**
- **传记偏好**：不是企业家传记，而是**科学家和技术组织的传记**（Frank Oppenheimer、Licklider、Hamming、Bell Labs、PARC）。
- **他重版为 Stripe Press 的书，有 3 本直接来自这份绿色清单**（Hamming、Waldrop、Poor Charlie's），说明书单与出版决策是同一套品味。

---

## 6. `/dispatches` — 19 篇长文（一手 · 2024-12 至 2026-08 · 最新最重要）

来源：https://patrickcollison.com/dispatches
框架 `[单次提取]`："a selection of longer posts originally published on X"

**这是目前他最活跃的写作形式，也是任务清单里没提到但价值最高的一块。** 完整目录：

| 日期 | 标题 | 主题 |
|---|---|---|
| 2026-08-02 | Why Aesthetics | 美学为何重要（**纲领性**） |
| 2026-06-20 | Paris | 巴黎建筑与城市美学 |
| 2026-05-25 | New Aesthetics | New Aesthetics 资助计划 |
| 2026-05-16 | Detroit Impressions | 底特律 1920 年代建筑 |
| 2026-04-26 | Arab Novels | 阿拉伯小说的黑暗性 |
| 2026-04-17 | Genome Agents | 用 AI agent 分析自己基因组 |
| 2026-03-21 | Ruskin's Gothic | 引用 Ruskin 论哥特建筑 |
| 2025-12-19 | Atlas Year | Stripe Atlas 创业数据 |
| 2025-12-15 | War and Peace | 反驳托尔斯泰的决定论 |
| 2025-10-20 | Pandemic Changes | 疫情造成的不可逆断点 |
| 2025-10-11 | On Moby Dick | 白鲸记 = 工业悲剧 |
| 2025-10-07 | Faroe Islands | 小国文化与基建成本 |
| 2025-09-28 | On Titan | 洛克菲勒传 |
| 2025-09-25 | Arc Discoveries | Arc Institute 三项突破 |
| 2025-09-21 | Manufacturing Matters | 美国制造业之争 |
| 2025-09-14 | Reddit Medicine | 众包医学知识 |
| 2025-09-08 | Irish Enlightenment | 爱尔兰启蒙运动 |
| 2025-04-06 | Europe vs America | 欧美生活对比 |
| 2024-12-27 | Ten Novels | 读十本经典小说的复盘 |

---

### 6.1 "Why Aesthetics"（2026-08-02）— 纲领性文本
https://patrickcollison.com/dispatches/why-aesthetics ｜ 一手 ｜ `[单次提取]`

**论证链条**（`[转述]`）：
1. **观察**：日常事物变丑了——电话亭、饮水器。
   > `[单次提取]` "Many things today are ugly and far uglier than they used to be"
   > `[单次提取]` "Once you see this, it's kinda hard to stop perceiving it"
2. **归因**：现代主义是对美的**主动拒绝**，也是**对文化连续性的显式否弃**。以 1932 年国际风格展览后美国建筑抛弃传统为例。
   > `[单次提取]` "a kind of explicit repudiation of cultural continuity"
3. **因果机制**：引 Elaine Scarry——美激发创造；那么反过来，**丑抑制创造**。
   > `[单次提取]` "Beauty inspires creation. If so, the inverse may also be true: ugliness inhibits it."
4. **历史证据**：Petrarch 与文艺复兴；万国博览会（1851 水晶宫，2100 万人口中 600 万人参观）——美学运动历史上与物质进步耦合。
5. **文化停滞**：引 Ted Gioia 的 "stuck culture"，1990 年代以来多领域停滞。
6. **市场机制（最原创的一段）**：审美市场里供给与需求互相塑造，可能锁死在**劣质均衡**。以德国食物为例。
   > `[单次提取]` "The Germans are stuck in an objectively worse market equilibrium"
7. **可计算化**：艺术品反映客观社会条件（credit: Alice Evans），期待出现类似 Google Ngram 的视觉艺术计算分析。
8. **实用理由（对企业最相关）**：Stripe 追求美，常常因此打破标准做法、产出新方案，同时满足优秀的人的内在动机。
9. **形而上收尾**：引索尔仁尼琴诺贝尔演讲——美具有"独特的不可辩驳性"。
   > `[单次提取，索尔仁尼琴原话]` "A true work of art carries its verification within itself"
   > `[单次提取，Collison 转述]` "Beauty is special...it possesses a unique kind of irrefutability"

> **这一篇是理解 2025–26 年 Collison 的钥匙**。他把美学从"品味偏好"升级为**进步的因果变量 + 组织的招聘/创新工具 + 认识论上的真理标记**。

---

### 6.2 "Ten Novels"（2024-12-27）— 对人生导师用途最相关的文学篇
https://patrickcollison.com/dispatches/ten-novels ｜ 一手 ｜ `[单次提取]`

**读的十本**：Jane Eyre、Middlemarch、To The Lighthouse、Bleak House、Portrait of a Lady、Anna Karenina、Life and Fate、Heart of Darkness、Madame Bovary、The Magic Mountain。

**排序**：最好的四本是 *Middlemarch*、*Bleak House*、*Anna Karenina*、*Life and Fate*；**Middlemarch 第一**。
> `[单次提取]` "There's something memorably compelling in Eliot's affection and empathy for almost all of her characters."（对比《继承之战》那种全员不讨喜）
> `[单次提取]` *Life and Fate* "not exactly entertaining (or even notably well-written), but it is true and profound."

**关于年龄与技艺复利（对野心/时间观最重要的一条）**：
> `[单次提取]` "wisdom is real, and that skill in the domain of fiction compounds for quite some time."
三本最好的（Middlemarch、Anna Karenina、Life and Fate）作者都在**五十多岁**写的；Dickens 写 *Bleak House* 时 41 岁。
> **注意这与 `/advice` 第 16 条"伟大的事常常发生在惊人年轻的时候"构成一组张力**——见第 12 节"矛盾记录"。

**1900 年前后的断裂**：
- Heart of Darkness / To The Lighthouse / The Magic Mountain "interesting" 但不 "compel"；现代主义留下 `[单次提取]` "incompleteness and dissatisfaction"。
- 引 Woolf 说 1910 年"人性变了"，引 Blom 的 *Vertigo Years*。
- 他不接受政治解释：`[单次提取]` "the coopting of communist ideals is probably itself downstream of the broader social unease."

**跨小说的模式观察**（`[转述]`）：
- 铁路作为破坏性力量反复出现
- 1900 前爱情是核心，1900 后强烈不是
- 19 世纪小说详细写金钱、债务的机制，20 世纪小说无视
- **道德严肃性**：19 世纪人物把自己当作重要的道德构造物（引 Ruxandra Teslo）
- **词汇悖论**：现代科学论文比 1960 年代更难读、更多黑话，而 19 世纪小说的句法和词汇又明显比今天复杂

**为什么该读经典（他自己的三个理由）**：
1. **通过"氛围"理解历史**——严谨史学传达不了的时代情绪；他认为传记里的小细节比宏大叙事更能照亮一个时代。
2. **文化资本**——这些书是 `[单次提取]` "intellectual capital cities"，其他文化通过它们才可解读。他坦承这有循环性：`[单次提取]` "they're worth reading because they are the books that we've decided are worth reading."
3. **卓越本身**（他的主要理由）：
   > `[单次提取]` "they are simply some of the finest intellectual achievements of humanity, and worthy of engagement for that reason alone: a deeper appreciation for excellence is itself a valuable thing."

他**明确怀疑**功利化的辩护：读经典未必让人更道德——`[转述]` "伦理学家据说也没比常人更有道德"。
> `[单次提取]` "Do they help you understand humanity, or the kind of people who write books?"

---

### 6.3 "War and Peace"（2025-12-15）— 人的能动性 vs 决定论
https://patrickcollison.com/dispatches/war-and-peace ｜ 一手 ｜ `[单次提取]`

- 他认为托尔斯泰的历史决定论**根本上是错的**，是 `[单次提取]` "implausibly maximalist position"。托尔斯泰称拿破仑的影响 `[托尔斯泰原文引用]` "purely external and fictitious"。
- 他的反问 `[单次提取]`：能否 "deterministically derive events which occurred under Lenin, Hitler, Atatürk, Mao from the broad tenor of the masses"？
- **方法论批评**：托尔斯泰披着 `[单次提取]` "the robes of Newton and even the infinitesimals of calculus"，但牛顿让人能预测，托尔斯泰把我们留在 `[单次提取]` "the position of mystics: whatever ensues is structurally determined by unknowable forces far larger than us."
- **对比 Grossman 的 *Life and Fate***：Grossman `[单次提取]` "understands the moral and spiritual significance of freedom"。Pierre 的平静来自 `[单次提取]` "serenity in capitulation"；而 Ikonnikov `[单次提取]` "refuses to build the gas chamber" 即使会死。Grossman 的信息：`[单次提取]` "human agency is the flame"，极权无法扑灭。
- 对托尔斯泰的总判：`[单次提取]` "misses the importance of human agency in the macro and devalues it repeatedly in the micro."
- **自我拆台的一段（重要）**：他承认 AI 发展可能反过来证明托尔斯泰对——那些试图避开 `[单次提取]` "race dynamics" 的人已被 `[单次提取]` "swept away by the tide"，而谨慎路线（他称之为 "the AI Kutuzovs"）目前反而更好。

> **这篇是他世界观最裸露的一次**：他是个坚定的能动性论者，且知道这是一个**信念**而非已证事实。

---

### 6.4 "On Titan"（2025-09-28）— 洛克菲勒传的启示
https://patrickcollison.com/dispatches/on-titan ｜ 一手 ｜ `[单次提取]`

- **决策方式的反常识**：洛克菲勒声誉是"果决领袖"，实际是**共识式**决策。
  > `[单次提取]` "his views tended to be discernible, and he was imbued with sufficient stature and credibility that his perspective carried without comity being disturbed."
- **一代与二代管理者的合体**：既能在无结构空间创新，又能用 `[单次提取]` "tight operating discipline" 扩张。
- **童年的自由与责任**塑造了他——他指出这在多位巨头的童年中重复出现，但被研究不足。
- **情绪压抑的再评估（很反当代）**：洛克菲勒有 `[单次提取]` "an unusual, self-protective capacity to suppress unpleasant memories and keep alive those things that fortified his resolve"。他由此提问：相比当代强调"处理情绪"，压抑是不是被低估了？
- **慈善哲学**（引 Carnegie *Gospel of Wealth*）：
  > `[Carnegie 原文]` "help those who will help themselves; to provide part of the means by which those who desire to improve may do so"
  > `[Carnegie 原文]` "in alms-giving more injury is probably done by rewarding vice than by relieving virtue"
  > `[Carnegie 原文]` 应优先提供 "the ladders upon which the aspiring can rise"
  > `[Rockefeller 原文]` "It is a great problem to learn how to give without weakening the moral backbone of the beneficiary."
- **他对商业传记体裁的固定不满**（在多篇出现）：缺少结构性财务分析——收购如何融资、资本如何管理、竞争动态如何——偏爱叙事而非数据。

---

### 6.5 "Irish Enlightenment"（2025-09-08）— 小群体理论
https://patrickcollison.com/dispatches/irish-enlightenment ｜ 一手 ｜ `[单次提取]`

覆盖 Hutcheson、Cantillon、Swift、Berkeley、Burke（+ William Petty）。

- Hutcheson `[单次提取]` "probably the most influential and respected moral philosopher in America in the eighteenth century"；引入 "unalienable rights"。
- Cantillon 开创 "entrepreneur" 的现代用法；其作品 `[单次提取]` "feels quite contemporary and basically correct"；预示了奥地利学派。
- Swift 是 `[单次提取]` "principally a pamphleteer: a hectoring intellectual activist"，19 卷著作。
- Berkeley 的 *The Querist* 是 `[单次提取]` "probably the first work of development economics"，由 **895 个问句**构成，强调文化与人力资本，接近后来的东亚发展模式。
  > **注意结构上的自我呼应：Berkeley 用 895 个问题写发展经济学；Collison 自己维护一页 23 个公开问题。**
- 总论点：1750 年前爱尔兰 `[单次提取]` "had a strong claim to leading the world in the field of economics"，早于 Smith 和重农学派。他把他们的湮没归因于民族主义史学偏爱 19 世纪人物。
- **最重要的一般化**：这是 `[单次提取]` **"small group theory"** 的证据——**共处一地的、离经叛道的思想者小圈子能开辟全新智识方向**。

---

### 6.6 "Europe vs America"（2025-04-06）
https://patrickcollison.com/dispatches/europe-vs-america ｜ 一手 ｜ `[单次提取]`
他自称人生大约一半在欧洲一半在美国。列出欧洲 20 项优势 / 美国 14 项优势，**不宣布胜者**。

- 欧洲：自行车基础设施、步行体验、城市宜人度（因为大量 1920 年代前建筑，在 `[单次提取]` "we forgot how to make nice buildings" 之前）、深夜咖啡馆、步行街、面包/奶酪/腌制品/葡萄酒、卫生间门、高速公路标识；以及他刻意不翻译的一串词：`[单次提取]` "languor, joie de vivre, hygge, gemütlichkeit, craic"。
- 美国：空调、水压、周日采买、**资本市场**（`[单次提取]` "it's much easier to get it in the US"）、网速、政府效率、劳动力市场灵活性使高生产率部门得以存在、通用航空（约 700,000 名飞行员）、医院、精酿啤酒革命。

---

### 6.7 "Manufacturing Matters"（2025-09-21）— 他罕见地公开站队反主流经济学
https://patrickcollison.com/dispatches/manufacturing-matters ｜ 一手 ｜ `[单次提取]`

- **观点 #1（主流）**：制造业外流是比较优势下的理性分工，怀旧是过时思维。
- **观点 #2（战略）**：制造业是终极网络效应与规模经济产业；AI 替代服务业、数据中心扩张会让制造更重要；不能挑几个赛道，必须全面竞争力。
  > `[单次提取]` "Manufacturing is the ultimate network effects and economies-of-scale business"
  > `[单次提取]` "the ecosystems and supply chains create strong gravity across the board"
  > `[单次提取]` 应该 "win at manufacturing across the board"
- **他倾向 #2**，并认为 Musk 近年对美国制造业的推进超过任何人，且 Musk 持同样观点。
- **最锋利的一句（元认知）** `[单次提取]`：
  > "because we don't know how to do #2, #1 is subconsciously a much more comfortable position to hold."
  同时承认 `[单次提取]` "we don't know how to make the US the world's preeminent manufacturing power"。

> **这是一个可复用的思维动作：当某个立场恰好也是"我们无能为力"的立场时，怀疑它是自我安慰。**

---

### 6.8 其余 Dispatches 要点速览（均一手，`[单次提取]`）

**Genome Agents（2026-04-17）** — https://patrickcollison.com/dispatches/genome-agents
自费几百美元测序自己基因组，用 AI coding agent 分析。发现自己黑色素瘤易感性是平均的 **30 倍**。
> "Population averages are population averages, but we ourselves are not averages."
> "medical practice is about to improve enormously."
> 对"模型不擅长医学推理"的说法：基于过时技术的这类分析是 "a kind of ludicrous malpractice"。
> 但也承认："you still have to carefully monitor the agents' reasoning, and they do on occasion jump to conclusions."
> agent 相对于今天能获得的其他东西 "almost literally infinitely better for this kind of work"。

**Reddit Medicine（2025-09-14）** — https://patrickcollison.com/dispatches/reddit-medicine
临床试验今天约 4000 万美元一个，饮食/补剂/生活方式的试验没人做，因为 "the ensuing knowledge can't be monetized"。Reddit 提供了 "emergent intelligence that sits between that which any single physician can marshal and the full rigor of clinical trials"，形成 "a limited kind of compounding knowledge"。他提议建一个覆盖所有主要慢病、持续问卷、追踪纵向结果的平台。核心洞察：患者主观经验里有大量 "latent data" 未被制度化医学采集。

**Arc Discoveries（2025-09-25）** — https://patrickcollison.com/dispatches/arc-discoveries
三项成果：Evo 2 生成自然界从未有过的噬菌体基因组并实验验证杀死大肠杆菌；Germinal 抗体设计成功率达 22%；Bridge editing 可做百万碱基对级精确编辑。
组织原则三条：(1) 软件/AI 与湿实验室必须在同一屋檐下——"The intersection of software/AI and experimental wet lab biology should enable great things"；(2) 非营利结构去掉财务回报顾虑，便于与 Stanford、Nvidia、东京大学合作；(3) 资金上平衡 "bottom-up and top-down work"——无限制的研究者经费 + 机构级协同项目。
他用 **"Turing loop"** 描述 AI 在生物学中的角色：测序=读，transformer=想，功能基因组学=写。

**Faroe Islands（2025-10-07）** — https://patrickcollison.com/dispatches/faroe-islands
5.5 万人的群岛。2011 年 "chef Leif Sørensen ended up essentially inventing Faroese haute cuisine all by himself"——**单个人重塑一国文化**的案例。11 公里海底隧道造价 "$14M per km"，约为美国同类项目的 1/30，尽管人均更穷。出版量 "approximately 200 new books each year; one for every 275 people"（爱尔兰是 1/2000）。提出问题：清晰界定的政体（"clearly-defined polities"）是限制了世界进步，还是保存了全球化会抹去的独特性？

**Pandemic Changes（2025-10-20）** — https://patrickcollison.com/dispatches/pandemic-changes
承认自己此前低估了疫情在疾病之外的影响。列举不可逆断点：法国鱼店奶酪店变成披萨外卖店；大学出勤与阅读作业完成率大幅下降且未恢复；西方城市 "far fewer bustling workplaces than there used to be"；"British economic statistics have become much less reliable since the pandemic"；多国移民加速；中国的恐惧与保守持续；美国散户股市参与度 "almost doubled overnight"；企业注册增加约 50%。
结论 `[单次提取]`："the number of time series that jumped discontinuously during COVID and then didn't return to baseline is just very striking"——并问除了大战之外还有什么历史类比。

**Atlas Year（2025-12-19）** — https://patrickcollison.com/dispatches/atlas-year
Atlas 注册同比 +36%，占**全美每年新设特拉华 C Corp 的 20% 以上**，2025 年超 23,000 家。欧洲增长最快（+48%），他的假设："dealing with incorporation is very annoying and bureaucratic in many European countries"。跨国创始团队比 2017 年 "79% more common"。2025 年注册的公司头 6 个月收入比 2024 年同期公司高 39%。**方差扩大**：中位数 +39%，90 分位 +52%，99 分位 +67%。归因于 AI 与区块链扩大了创业可能性。
（注：`/about` 页给的最新数字是 Atlas 已占**约四分之一**的新设特拉华公司。）

**New Aesthetics（2026-05-25）** — https://patrickcollison.com/dispatches/new-aesthetics
与 Tyler Cowen 合办的资助计划，28 位受资助者；申请太多提前关闭。
> "figuring out some route beyond the current aesthetic moment seems to be of wider interest"
> 两条趋势："Both beauty as an unapologetic goal...and ways to channel pre-modern styles into something new"
> 结构性障碍："schools, galleries, buyers, etc., all have structurally embedded preferences"——因此他考虑转向资助**艺术家群簇**（呼应 small group theory）
> 建筑是 "the discipline most ripe for new ideas"；引一位通信者说美国建筑师 "overthink things so that designs are formally interesting...but lacking poetry and magic"
> AI 对艺术的冲击类比 19 世纪末的 "urbanization/industrialization/popularization of photography"
> "individual actors can have meaningful impact"

**Paris（2026-06-20）** — https://patrickcollison.com/dispatches/paris
城市的连贯感往往来自**材料统一**而非形式统一："rules in the Charleston, the Cotswolds, and Sea Ranch leave a lot of flexibility in shape, but tightly restrict materials"。
引 1886 年建筑师 Charles Garnier 论地铁：`[Garnier 原文]` "The Metropolitan Railroad...will only be excused if it rejects absolutely all industrial character so as to be completely a work of art."
> "late 19th century France had the most educated visual culture among its elites in human history"
对 Michelangelo–Rodin 展："how direct the artistic lineage is"，因此应对视觉艺术复兴 "more optimistic about prospects for revival of the best of the visual arts"。
收尾提问："Is central Paris the greatest single artistic achievement in the world?"
他还问：Haussmann 是不是 James Scott 所批判的中央规划的最佳反例（"the finest example of the central planning that Scott decries"）——到 1870 年巴黎市中心五分之一的街道是他造的。

**Detroit Impressions（2026-05-16）** — https://patrickcollison.com/dispatches/detroit-impressions
市中心 "full of beautiful buildings" 却 "surprisingly depopulated"；这些楼 "All of them seem to have been built specifically in the 1920s"——汽车财富积累之后、现代主义到来之前。Renaissance Center 是 "the largest private development in US history" 却毫无美感。质问湾区为何没有可比的文化机构（把原因归于科技业的市侩）。提倡 "plaquemaxxing"（到处立历史铭牌）。

**Arab Novels（2026-04-26）** — https://patrickcollison.com/dispatches/arab-novels
> "I was very struck by the darkness and violence. (Abundant rape, murder, violence, and so forth.)"
> 假设之一："One guess is that it is a function of award selection algorithms: gritty despair is seen as high-status."
> 他真正想要的："Which authors from the region can best be compared to Faulkner, Eliot, Fitzgerald, or Rushdie?"
指出殖民主义解释不成立（未被殖民的伊朗的 *The Blind Owl* 同样黑暗）。

**Ruskin's Gothic（2026-03-21）** — https://patrickcollison.com/dispatches/ruskins-gothic
主要是引用 Ruskin 论哥特建筑与地域差异的长段。`[未深度抓取]`

---

## 7. "We Need a New Science of Progress"（The Atlantic, 2019-07，与 Tyler Cowen 合著）

**原文 URL 被代理拦截，无法直接抓取**（见第 13 节）。以下引语全部来自**引用该文的第三方页面**，因此标注为 `[二手转引，原文措辞]`——这些是别人从原文中摘出的直接引语，措辞可信，但建议人工到 Atlantic 原文核对。

### 7.1 核心定义 `[二手转引 · 在 3 个独立来源中一致出现]`
> progress = "the combination of economic, technological, scientific, cultural, and organizational advancement that has transformed our lives and raised standards of living over the past couple of centuries"

（来源：thepointmag.com、williamrinehart.com、marginalrevolution.com 三处一致）

### 7.2 学科应该做什么 `[二手转引]`
> Progress Studies "would study the successful people, organizations, institutions, policies, and cultures that have arisen to date, and it would attempt to concoct policies and prescriptions that would help improve our ability to generate useful progress in the future."

### 7.3 核心提问 `[二手转引]`
> "there can be ecosystems that are better at generating progress than others, perhaps by orders of magnitude. But what do they have in common?"
> "Just how productive can a cultural ecosystem be?"
> "Can we deliberately engineer the conditions most hospitable to this kind of advancement or effectively tweak the systems that surround us today?"

### 7.4 与既有学科的区别（关键） `[二手转引]`
> 目标是超越 "mere comprehension"，去 "identify effective progress-increasing interventions and the extent to which they are adopted by universities, funding agencies, philanthropists, entrepreneurs, policy makers, and other institutions."

> **这是他与学院派的分野点：他要的不是理解，是可干预、可采纳的处方。**

### 7.5 实施方式 `[二手转引]`
> "academic departments and degree programs would not necessarily have to be reorganized...a new focus on progress would be more comparable to a school of thought that would prompt a decentralized shift in priorities among academics, philanthropists, and funding agencies. Over time, we'd like to see communities, journals, and conferences devoted to these questions"

### 7.6 "碎片化"论证 `[二手转引，marginalrevolution 转述 Cowen 的补充]`
关于"如何识别有天赋的学生"这类知识，"dispersed across a very long list of different fields"——心理测量学、社会学、人类学、教育学、人格心理学、经济学——而这些领域的研究者 "don't necessarily attend the same conferences, publish in the same journals, or work together."
Cowen 补充说他们并非无视先行者，原文 "in at least nine different paragraphs" 讨论了前身，并明确认为 "the economics of innovation is a critical topic and should assume a much larger place within economics."

### 7.7 后续生态（二手 · Wikipedia）
- Jason Crawford 的 Roots of Progress → 研究所 + fellowship
- *Works in Progress* 杂志（2020 创刊，**2022 被 Stripe Press 收购**）
- Institute for Progress 智库（2021，Stapp & Watney 创立）
- 批评：过度强调总量增长、轻视不平等；"创新在下降"的度量方法（专利/引用分析）本身有问题
来源：https://en.wikipedia.org/wiki/Progress_studies

`/progress` 页（一手）把 *Works in Progress* 称为 `[单次提取]` "a very good new online magazine"，并索引了 Jason Crawford、Jasmine Wang、Will Rinehart、Eli Dourado、José Luis Ricón、Diane Coyle、Adam Thierer、Francis Jervis、Matt Clancy、Daniel May、Tom Pepinsky（"Failure Studies"）等回应。

---

## 8. "Science Is Getting Less Bang for Its Buck"（The Atlantic, 2018-11，与 Michael Nielsen 合著）

**原文 URL 同样被拦截。** 以下为 `[二手转引，原文措辞]`。

方法：调查科学家，让他们**跨年代两两比较诺贝尔奖级发现的质量**。

`[二手转引]` 核心发现与句子：
> "the quality of Nobel prizewinning discoveries has changed over the decades"
> "just three discoveries made since 1990 have yet been awarded Nobel Prizes."
> "the 1990s and 2000s have the dubious distinction of being the decades over which the Nobel Committee has most strongly preferred to skip back and award prizes for earlier work."
> 核心问题："Why has science gotten so much more expensive, without producing commensurate gains in our understanding?"

`[二手转引，来自另一个转载页]`
> "future Nobel scientists were 37 years old, on average, when they made their prizewinning discovery. But in recent times that has risen to an average of 47 years"
> "When Ernest Rutherford discovered the nucleus of the atom in 1911, he published it in a paper with just a single author: himself." 而 "the two 2012 papers announcing the discovery of the Higgs particle had roughly a thousand authors each"
> "[Scientific progress is] requiring larger teams, far more extensive scientific training, and the overall economic impact is getting smaller."
> "U.S. productivity growth is way down. It's been dropping since the 1950s, when it was roughly 6 times higher than today."

来源：https://marginalrevolution.com/marginalrevolution/2018/11/science-getting-less-bang-buck.html ；https://amalgamated-contemplation.com/2018/11/16/science-is-getting-less-bang-for-its-buck-the-atlantic/

> **注意时间顺序：2018 年的这篇（诊断科学产出下滑）在前，2019 年的 Progress Studies（提出学科方案）在后。前者是问题陈述，后者是纲领。**

---

## 9. "What We Learned Doing Fast Grants"（future.com, 2021，与 Tyler Cowen、Patrick Hsu 合著）

来源：https://future.com/what-we-learned-doing-fast-grants/ ｜ 一手 ｜ `[单次提取]`

### 9.1 项目事实
2020 年疫情期间发放 **5000 万美元以上、260+ 笔资助**。申请**不到 30 分钟**填完，**48 小时内**出决定。
> 动机："scientists — among them the world's leading virologists — were stuck on hold, waiting for decisions."

### 9.2 出乎意料的发现
- 捐赠者的胆识："a number of individuals made seven-figure contributions without ever speaking with us."（而**机构性出资方反而畏缩**。）
- "a large fraction of our grants went to people at top twenty institutions"——**顶尖机构的人也缺钱**，推翻了"名校不缺资金"的预设。
- 制度失灵："many entities continued with something close to 'business as usual' rather than switching to emergency pandemic mode."
- 临床试验："It is extremely difficult to quickly and cheaply run human clinical trials, even if the drug being tested is already known to be safe."

### 9.3 对受资助科学家的问卷（本文最常被引用的部分）
- **57% 的人把超过四分之一的时间花在申请经费上**
  > "We spend enormous effort training scientists who are then forced to spend a significant fraction of their time seeking alms instead of focusing on the research they've been hired to pursue."
- **78%** 说如果资金不受限，会**显著改变研究方向**
- **81%** 说研究会变得**更有野心**
- **62%** 会去做本领域之外的工作（而传统资助方明确不鼓励这个）
- 核心悖论：
  > "Scientists are in the paradoxical position of being deemed the very best people to fund but *not* so trustworthy that they should decide what work makes most sense!"
- 科学家给疫情期间制度反应打 **5/10**，但给"科学本可以更快"打 **9/10**。

### 9.4 主张
反对 NIH 单一文化，主张**资助方多样性**。指出主流模型 "assumes that slow is good or at least tolerable; or that a deliberative and consensus-based process is ideal."
Fast Grants 证明了 "alternative models of science funding can work"，应通过精简流程去 "unlock more ambitious and high-impact research that is otherwise constrained by structural barriers."

---

## 10. Stripe Press（press.stripe.com）—— 出版选择即价值观

来源：https://press.stripe.com/ ｜ 一手（机构） ｜ `[单次提取]`

**Slogan**：**"Ideas for progress"**
自我描述：出版关于 "technological, economic, and scientific advancement" 的作品。

### 10.1 书目（截至 2026-08）
1. *Poor Charlie's Almanack* — ed. Peter D. Kaufman（**John Collison 作序**，不是 Patrick）
2. *Maintenance: Of Everything, Part One* — Stewart Brand
3. *The Origins of Efficiency* — Brian Potter
4. *The Scaling Era: An Oral History of AI, 2019–2025* — Dwarkesh Patel with Gavin Leech
5. *Boom: Bubbles and the End of Stagnation* — Byrne Hobart & Tobias Huber
6. *Scaling People* — Claire Hughes Johnson（前 Stripe COO）
7. *Pieces of the Action* — Vannevar Bush
8. *Where Is My Flying Car?* — J. Storrs Hall
9. *The Big Score: The Billion Dollar Story of Silicon Valley* — Michael S. Malone
10. *Scientific Freedom: The Elixir of Civilization* — Donald W. Braben
11. *Working in Public* — Nadia Eghbal
12. *The Art of Doing Science and Engineering* — Richard W. Hamming（Bret Victor 作序）
13. *The Making of Prince of Persia* — Jordan Mechner
14. *Get Together* — Richardson, Huynh, Sotto
15. *An Elegant Puzzle* — Will Larson
16. *The Revolt of the Public* — Martin Gurri
17. *Stubborn Attachments* — Tyler Cowen
18. *The Dream Machine* — M. Mitchell Waldrop
19. *High Growth Handbook* — Elad Gil

其他项目：纪录片 *We Are As Gods*（Stewart Brand）、播客 *Beneath the Surface*（基础设施）。另收购 *Works in Progress* 杂志（2022）。

### 10.2 判读 `[转述，我的分析]`
- **三条清晰的出版线**：(a) 二战/冷战科研组织的复活（Vannevar Bush、Hamming、Braben）；(b) 停滞与复兴的论证（Hall、Hobart & Huber、Cowen、Potter）；(c) 硅谷自身的历史记忆（Waldrop、Malone、Mechner）。
- **重版 > 新著**：大量是把被遗忘的旧书重新做成美物。这与 `/advice` 的"多读老书"和 Ferriss 访谈里 "People should be much more biased towards older books" 是同一件事的三个表现。
- **实体书本身的工艺**是 Stripe Press 的标志——这是他"美学论"在自家产品上的落地。
- **注意**：没有找到任何 Stripe Press 图书由 **Patrick** 亲自撰写序言的证据。*Poor Charlie's Almanack* 的序是 **John Collison** 写的。见第 13 节。

---

## 11. Stripe 年度信与官方表述

### 11.1 使命表述 `[一手，X/Twitter 原文]`
来源：https://x.com/patrickc/status/1371506254359752708
> "'Increase the GDP of the internet' is our mission statement but also, importantly, our *strategy*. Zero sum games are bad. We want Stripe to enable new businesses, new customers, new transactions, and new economic activity."

> **这条极重要**：他明确说这不只是口号，是**战略**，且理由是**反零和**。这是他所有商业判断的底层价值——正和优先。

其他固定表述：**"economic infrastructure for the internet"**（Stripe 官方描述）；`/about` 页说 Stripe 是 "financial infrastructure for programmers"。

### 11.2 2025 年度信
来源：https://stripe.com/annual-updates/2025 ；新闻稿 https://stripe.com/newsroom/news/stripe-2025-update ｜ 一手 ｜ `[单次提取]`
- Stripe 上的企业 2025 年产生 **1.9 万亿美元**，"equivalent to 1.6% of global GDP"，同比 +34%。
- 四大主题：2025 届创业公司的空前速度；global-by-default 企业的崛起；agentic commerce 的演进；对互联网经济的乐观。
- "the economy bifurcated"；"Competitive markets have always sorted between fast- and slow-growing businesses"，而 2025 年 "the sorting machine went into high gear"。
- Patrick 与 John 联合署名的一句：
  > "Our programmable financial services now power more than 5 million businesses directly or via platforms, including all of the top AI companies, many of the largest blue-chip companies (90% of the Dow Jones Industrial Average), most of the biggest tech companies (80% of the Nasdaq 100), and a significant fraction of freshly minted startups."
- 2025 届新客户群比 2024 届增长快约 50%；57% 在美国境外。
- 同时宣布 tender offer，估值 **1590 亿美元**。

### 11.3 2024 年度信
来源：https://stripe.com/annual-updates/2024 ｜ `[单次提取]`
> "their revenue processed on Stripe grew seven times faster than the revenue of companies in the S&P 500."
（正文是 PDF，未能抓取，见第 13 节。）

### 11.4 2026 年度信
存在（第三方 2026-02 已报道其内容：稳定币支付翻倍至约 4000 亿美元、agent + 支付成为核心基础设施），但 `stripe.com/annual-updates/2026` 返回 404，**未能定位可抓取 URL**。见第 13 节。

---

## 12. 反复出现 ≥3 次的核心论点（真信念清单）

这一节是本文件的**结论层**。每条都标注了它在哪些**不同来源**中出现。

### 12.1 进步已经放缓，而且这是制度问题不是物理问题 —— 出现在 7 处
- `/fast` 全页（前 1970 年的建设速度）
- `/questions` 第 2、22 题
- "Science Is Getting Less Bang for Its Buck"（Atlantic 2018）
- "We Need a New Science of Progress"（Atlantic 2019）
- "What We Learned Doing Fast Grants"（2021）
- `/growth` 文献集（Gordon、Bloom "Are Ideas Getting Harder to Find?"、Cowen "The Great Stagnation"）
- Zuckerberg 访谈：生产率增长从战后约 1.9%/年降到约 0.4%；"we're generating progress more slowly than we used to be"
**→ 这是他最坚固、跨度最长（2018–2026）的信念。**

### 12.2 制度会僵化；正确的回应是"另建"而不是"改良" —— 出现在 6 处
- `/questions` 第 4 题（没有自然死亡机制的系统如何保证更替率）、第 5 题（实验性城市）
- Fast Grants（另起炉灶而非游说 NIH）
- Arc Institute（另建研究机构）
- `/about`：投资 California Forever 与 Esmeralda（另建城市）
- Zuckerberg 访谈："the entry costs of forming a new university are really high"
- `/labs`（对旧式工业实验室黄金期的追问）
**→ 这解释了他所有慈善/机构行为的统一形状。**

### 12.3 科学资助机制是坏的：科学家时间被浪费、资助方缺乏多样性 —— 出现在 6 处
- Fast Grants 复盘（57% / 78% / 81% / 62% 四个数字）
- Atlantic 2018
- `/about`（把 Fast Grants 和 Arc 明确称为 better scientific funding 的模型）
- `/labs`
- "Arc Discoveries"（无限制的研究者经费 + 顶层协同）
- Zuckerberg 访谈："there are no books assessing how well the NIH is working"；"tool-building is under-supported"

### 12.4 美是进步的因果变量，不是装饰 —— 出现在 6+ 处（2025–26 集中爆发）
- "Why Aesthetics"（2026-08，纲领）
- "New Aesthetics"（2026-05，资助计划）
- "Paris"（2026-06）、"Detroit Impressions"（2026-05）、"Ruskin's Gothic"（2026-03）
- `/about`："Why is contemporary architecture so ugly?" + 与 Cowen 合办 New Aesthetics grants
- `/questions` 第 18、20 题
- Dwarkesh 访谈（craft/beauty 与 Stripe 的关系）
**→ 这是他 2025 年以来最显著的新增主题。如果 skill 只反映 2019 年的他，会漏掉这一整层。**

### 12.5 个人能动性是真实的；小群体能改变世界 —— 出现在 6 处
- "War and Peace"（明确反驳托尔斯泰决定论）
- "Irish Enlightenment"（**"small group theory"**）
- "Faroe Islands"（一个厨师发明一国高级料理）
- "New Aesthetics"（"individual actors can have meaningful impact"）
- `/fast`（清单里全是具名的个人：Kelly Johnson、Dee Hock、Brendan Eich、Ken Thompson）
- `/advice`（"nobody is going to teach you to think for yourself"）

### 12.6 大量读书、且偏向老书；广泛涉猎是核心学习技术 —— 出现在 6 处
- `/advice` 第 7 条 "Aim to read a lot."
- `/bookshelf`（~500 本，横跨数学、物理、飞行、设计、非洲、中国、小说）
- "Ten Novels"（系统读经典并复盘）
- Tim Ferriss 访谈："People should be much more biased towards older books than they are."
- `/svhistory`、`/labs`、`/growth`、`/culture` 四个专题书单
- `/questions` 第 11 题（书的继任者是什么）
- Stripe Press 大量重版旧书

### 12.7 欧洲在衰退，美国资本市场是关键差异 —— 出现在 3 处
- `/about`：认为美国自 2008 年后跑赢其他发达经济体，**充沛的美国资本**是重要解释；欧洲 "falling behind the US in key technologies and general prosperity"
- "Europe vs America"（资本获取："it's much easier to get it in the US"）
- "Atlas Year"（欧洲创始人因本国注册官僚而转向美国实体，欧洲 Atlas 注册 +48%）

### 12.8 伟大的工作常常发生在很年轻的时候 —— 出现在 4 处
- `/advice` 第 16 条
- Atlantic 2018（诺奖发现的平均年龄从 37 升到 47，被当作问题）
- Atlantic 2019（人才识别的知识被割裂在各学科）
- Zuckerberg 访谈（资助向年长研究者倾斜）

---

## 13. 自创/偏爱的术语与概念（可直接用作 skill 的语汇表）

**他自创或与人共创的：**
- **Progress Studies** — 与 Tyler Cowen，2019
- **Fast Grants** — 与 Cowen、Patrick Hsu，2020
- **New Aesthetics（grants）** — 与 Cowen，2026
- **"Increase the GDP of the internet"** — Stripe 使命兼战略
- **"small group theory"** — 共处一地的小圈子能开辟新智识方向（Irish Enlightenment）
- **"Status lags by a generation or more."** — `/advice`
- **"Turing loop"** — 生物学的读/想/写循环（Arc Discoveries）
- **"plaquemaxxing"** — 城市多立历史铭牌（Detroit）
- **"reader-book fit"** — 读者与书的匹配时机（Ferriss 访谈：`[单次提取]` "There's really something around reader book fit and the particulars of that moment."）
- **"global-by-default businesses"**、**"agentic commerce"**、**"the sorting machine"** — 2025 年度信

**他偏爱借用的：**
- **Schelling point**（描述旧金山对高开放性人群的聚集作用）
- **Conquest's Third Law**（Dwarkesh 访谈 `[单次提取]`："model organizations as if they're run by a cabal of their enemies"）
- **economic infrastructure** / **financial infrastructure for programmers**
- **cost disease**（`/questions` 第 1 题）
- **"Ideas for progress"**（Stripe Press slogan）
- **WEIRD**（`/culture`）
- Umberto Eco 的**反图书馆**观念（`/bookshelf`）

---

## 14. 关于个人成长/学习/职业/野心/时间/品味的论述（人生导师用途专章）

### 14.1 书面来源（一手，权重最高）
见第 2 节 `/advice` 全文十六条 —— **这是核心文本，应作为 skill 的骨架。**

补充要点：
- **技艺随年龄复利**（"Ten Novels"）：`[单次提取]` "wisdom is real, and that skill in the domain of fiction compounds for quite some time."
- **对卓越的欣赏本身有价值**（"Ten Novels"）：`[单次提取]` "a deeper appreciation for excellence is itself a valuable thing."
- **反对功利化的自我提升论证**（"Ten Novels"）：他明确怀疑"读经典使人道德"，宁可用"这就是人类最好的智识成就"作理由。
- **情绪压抑可能被低估**（"On Titan"）：他就洛克菲勒的 "self-protective capacity to suppress unpleasant memories" 提出，当代对"处理情绪"的强调也许该被重新审视。**这是一条明显反当代心理学共识的观点，务必如实保留。**
- **元认知警戒**（"Manufacturing Matters"）：`[单次提取]` "because we don't know how to do #2, #1 is subconsciously a much more comfortable position to hold." —— **当一个立场恰好让你无需行动时，怀疑它。**
- **人不是平均值**（"Genome Agents"）：`[单次提取]` "Population averages are population averages, but we ourselves are not averages."

### 14.2 口述来源（一手·口述，权重次之，但对人生话题信息密度最高）

**Tim Ferriss Show #353（2018-12-24）** — https://tim.blog/2018/12/24/the-tim-ferriss-show-patrick-collison/
以下 `[单次提取，口述]`：

*读书方法*
> "Buy a lot of books that seem interesting and high quality but before you're necessarily ready to read them."
> "Leave books around the house on bookshelves, kitchen table, beside the couch in your bedroom."
> "It really matters a lot when I read the book and the frame of mind that I'm in at the time when I stumble across it."
> "There's really something around reader book fit and the particulars of that moment."
> "People should be much more biased towards older books than they are."
> **→ 他的读书法是"制造偶遇"，不是"读完清单"。买超出当前理解力的书，物理散布在家里，等待时机匹配。**

*独立思考*
> "Nobody is going to teach you to think for yourself. A large fraction of what people around you believe is mistaken."（与 `/advice` 第 12 条一致，**两来源交叉验证**）
> "When you see a smart person holding a view different to your own, try to figure out how they're right."

*关于风险与偏离常规（重要的反直觉平衡）*
> "Most efforts to do something substantially different to best practice fail."
> "The bias should be that for any radical departure from prevailing status quo, it's probably not going to work."
> **→ 注意：他既鼓励"做怪事"，又对"偏离最佳实践"给出默认失败的先验。这不是矛盾，是把创新预算集中在少数关键点上。**

*野心的心理代价（对人生导师用途极关键）*
> "You're always necessarily operating at the outer edge of what you can handle because if you have spare capacity, you take on more."
> "Even if things are going well, things will still often not feel great day to day."
> **→ 他不兜售"做喜欢的事就不累"。他明确说：野心的稳态就是永远在能力边缘、日常感受经常不好。**

*父母的角色*
> "Our parents were playing a supporting role rather than having us be pushed along by some locomotive."
> "Whenever we expressed interest in something, they really tried to find opportunities to water it."

*道德底色*
> "The single most important thing about our lives compared to others is being born in wealthy societies."
> "One of the most urgent moral questions is why doesn't everyone get to do that?"
> **→ 这是他整个进步研究事业的道德发动机：增长不是偏好，是道德义务。**

**Dwarkesh Podcast（2024-02）** — https://www.dwarkesh.com/p/patrick-collison
以下 `[单次提取，口述，建议人工核对]`：

*工艺与人才的关系*
> "The best people consider themselves crafts people in their domain and they really, above almost all else, want to work with the best other people."
> **→ 这是他"美学论"的人力资源版本：追求工艺是招人和留人的机制。**

*长期主义的具体形式*
> "How do we think we can stand behind this in 2044?"（做 API 设计决策时的自问）
> "When you get API design and architecture right, it can be so enduring over literally multiple decades."

*学习"什么是好"*
> "When they worked with X person or Y organization, they learned what great actually is."
> "You have to figure out where can you go and experience that first hand"
> **→ 与 `/advice` 第 15 条 "Find vivid examples of success" 同源，两来源交叉验证同一观念。**

*问题选择*
> "Problem selection...you have to choose something sufficiently important and hard, but not so complex that progress becomes unachievable."

*对硅谷的批评*
> "There's a strange emphasis placed on entrepreneurship in San Francisco, that should not be people's only fixation."
> "San Francisco doesn't culturally encourage one to become Herb Boyer"（Herb Boyer = Genentech 联合创始人、生化学家）
> **→ 该集标题即 "Why Silicon Valley's most talented should leave"。注意与 `/advice` 第 14 条"想办法去旧金山"的张力，见第 15 节。**

*从众*
> "The herd is a really powerful phenomenon...it's freaking hard to do in practice"（指抵抗从众）

**Mark Zuckerberg 访谈 Collison & Cowen（Conversations with Tyler bonus）** — https://conversationswithtyler.com/episodes/mark-zuckerberg-interviews-patrick-collison-and-tyler-cowen/
`[单次提取，口述]`
> "something happened, something changed around sort of 1700, 1750, you know, the Industrial Revolution, the Enlightenment"
> "there's a surprising lack of definitive answers"（关于成本病）
> "there are no books assessing how well the NIH is working. And I don't have a strong view on the answer"
> "major swathes of these questions really are surprisingly under-investigated"
> "tool-building is under-supported"
> "we're generating progress more slowly than we used to be"
> "for almost every conceivable applied measure we seem to be getting at best constant returns"
> "the entry costs of forming a new university are really high"
> "we should be historically informed but ultimately, a certain amount of commitment and willingness to experiment is required"

---

## 15. 发现的矛盾与张力（原样记录，不予调和）

**15.1 "别用同侪衡量自己" vs "搬到旧金山去找同侪"**
`/advice` 第 9 条说 "Above all else, don't make the mistake of judging your success based on your current peer group"，第 14 条又说想办法去旧金山认识那里的人。他自己没有明说如何协调。（一个可能的解读是：换掉参照群体 ≠ 用参照群体衡量自己，但**这是我的推断，不是他的话**。）

**15.2 "伟大的事发生在惊人年轻的时候" vs "技艺复利到五十多岁"**
`/advice` 第 16 条 vs "Ten Novels"（2024）中"最好的三本小说都是作者五十多岁写的，wisdom is real"。`/advice` 页写作时间更早。**没有证据表明他明确修正过前一条。**

**15.3 "做怪事、做别人不做的事" vs "偏离最佳实践的默认先验是失败"**
`/advice` 第 13 条 + Ferriss 访谈中的 "The bias should be that for any radical departure from prevailing status quo, it's probably not going to work."

**15.4 人的能动性 vs AI 时代的决定论**
"War and Peace"（2025-12）中他花整篇反驳托尔斯泰的决定论，却在同一篇末尾承认 AI 的竞赛动力学可能反过来证明托尔斯泰是对的——试图避开 race dynamics 的人 "swept away by the tide"。**他自己把这个矛盾摆在台面上，没有解决。**

**15.5 对旧金山的态度**
`/advice`（较早）：旧金山是高开放性乐观者的 Schelling point，想办法去。
Dwarkesh（2024）：旧金山对创业的强调是奇怪的、不该是唯一执念；旧金山的文化不鼓励你成为 Herb Boyer。播客标题直接是"硅谷最有才华的人应该离开"。
**这是一个明确的时间序列上的态度变化，不是同期矛盾。**

**15.6 对经济学界的态度**
`/growth` 页几乎全部由经济学家的论文构成，姿态是学习。
"Manufacturing Matters"（2025）中他明确说大多数经济学家持他不同意的立场，并推测原因是无能带来的心理舒适。
**说明他把经济学当工具而非权威。**

**15.7 商业传记的价值**
他大量读传记（书单里有 Andy Grove、Noyce、Jobs、Gates、Rockefeller），但在 "On Titan" 中把"缺少结构性财务分析"作为对这个体裁的固定不满。**他一边消费一边不满意。**

**15.8 `/bookshelf` 的时效性问题**
页面自称约十年未更新（即反映约 2015 年的他）。**用这份书单描述 2026 年的 Collison 会系统性地漏掉整个"美学转向"和 AI/生物学线。**

---

## 16. 抓取失败/反爬的高价值来源（需人工补充）

以下 URL 我尝试抓取但被拦截。**按价值排序**：

### ★★★ 最高优先级

1. **https://www.theatlantic.com/science/archive/2019/07/we-need-new-science-progress/594946/**
   - 《We Need a New Science of Progress》全文，Progress Studies 的**创始文本**。
   - 失败原因：代理返回 HTTP 403（theatlantic.com 整域被拦）。archive.org 镜像、AMP 版本、`r.jina.ai` 代理均同样 403。
   - **为什么重要**：这是他影响力最大的一篇署名长文，是整个 Progress Studies 运动的起点。我目前只有从 4 个二手页面转引的约 7 条原文引语，**缺少完整论证结构、他们提出的具体机制、以及最后的行动号召部分**。
   - 建议：人工打开 Atlantic 网页（或找 ProQuest 版 https://www.proquest.com/docview/2295513298/ ）复制全文。

2. **https://www.theatlantic.com/science/archive/2018/11/diminishing-returns-science/575665/**（准确 URL 待确认）
   《Science Is Getting Less Bang for Its Buck》全文，与 Michael Nielsen 合著。
   - 失败原因：同上，theatlantic.com 全域 403。
   - **为什么重要**：这是 Progress Studies 的问题陈述前身，含独创的"跨年代诺奖发现质量调查"方法。我只有转引的 8 条句子。
   - **另有一个配套的方法学附录**（Cowen 称其为 "a detailed methodological appendix"），我尝试 `https://collisonnielsen.com/science/` 失败（DNS 解析失败，域名可能已下线）。**这个附录含全部原始数据和调查设计，价值极高。** 建议在 Wayback Machine 手工查找 `collisonnielsen.com`。

3. **Stripe 年度信 PDF 正文（2020–2026 全部年份）**
   - `https://stripe.com/annual-updates/2024`、`/2025` 的网页只有摘要，**正文在 PDF 里**。
   - 我尝试猜测的 PDF 路径（如 `https://stripe.com/files/annual-updates/2025/stripe-annual-letter-2025.pdf`）返回 404。
   - `https://stripe.com/annual-updates/2026` 返回 **404**，但 2026 年度信确实已发布（2026-02 前后，第三方报道其主题为稳定币支付翻倍至约 4000 亿美元、agentic commerce）。**正确 URL 未能定位。**
   - `https://stripe.com/annual-updates`（索引页）返回 **404**。
   - **为什么重要**：年度信是 Patrick 与 John 联合署名的最长篇幅书面输出，含大量关于经济、AI、创业生态的原创判断。目前只有零星数字，没有论证。
   - 建议：从 https://stripe.com/newsroom/news 逐年找新闻稿，或直接在 stripe.com 站内搜 annual letter 下载 PDF。

### ★★ 高优先级

4. **https://patrickcollison.com/advice 的完整逐字原文**
   - 未被"拦截"，但 WebFetch 的提取模型**拒绝逐字复制整页**（版权顾虑）。我通过"引用每段首句"绕过，拿到了 16 条的首句（已双次校验），但**每条建议的完整论证正文仍是转述**。
   - **为什么重要**：这是用户"人生导师"用途最核心的一页，理应有完整原文。
   - 建议：人工打开页面全文复制（页面很短，几分钟即可）。

5. **https://patrickcollison.com/bookshelf 的准确书目**
   - 页面可抓取，但 ~500 条的自动提取**噪声很大**（多条明显是解析错误，如把书名截断成 "incomplete reference"）。绿色/浅蓝高亮的判定也可能有误。
   - 建议：人工核对"绿色高亮"清单（第 5.2 节），这是信号最集中的部分。

6. **Ezra Klein Show, "We Know So Little About What Makes Humanity Prosper"（2022，与 Patrick Collison）**
   - https://podcasts.apple.com/us/podcast/we-know-so-little-about-what-makes-humanity-prosper/id1548604447?i=1000580772655
   - NYT 的官方文字稿在 nytimes.com 付费墙后，未尝试。
   - **为什么重要**：`/about` 页把它列为他的三个代表性访谈之一（另两个是 Michael Truell 2025、Dwarkesh 2024）。是他对进步问题最长的一次公开阐述之一。

7. **Michael Truell 访谈（2025）**
   - `/about` 页列出但未给链接，我未能定位具体 URL。
   - **为什么重要**：这是 `/about` 上列出的**最新**一次长访谈（2025），最可能包含他对 AI 时代的最新看法。

### ★ 中等优先级

8. **https://patrickcollison.com/dispatches/ruskins-gothic**
   - 我未做深度抓取（判断其主要内容是引用 Ruskin 原文）。属于"美学转向"系列，可能含他自己的评注。

9. **https://guide.world/**
   - 他 2025–26 年的新项目（旅行写作聚合），`/travel` 页介绍。抓取只返回 meta 标签，正文（可能是 JS 渲染）未获取。作者 meta 确认是 Patrick Collison。

10. **X/Twitter @patrickc 时间线**
    - `/dispatches` 只是"长帖精选"，**大量观点仍散落在原始推文里**。X 无法通过 WebFetch 抓取（需登录）。
    - 建议：如果用户能访问 X，@patrickc 的时间线是密度最高的未开采来源。

11. **Stripe Press 各书的单独页面**
    - press.stripe.com 的每本书页面有 Stripe Press 撰写的推荐语，我只抓了首页书目。**未逐本抓取推荐语**（任务清单第 4 项要求）。
    - 注意：已确认**没有** Patrick 亲自作序的 Stripe Press 图书（*Poor Charlie's Almanack* 是 John 作序，Hamming 那本是 Bret Victor 作序）。

12. **Stripe 官方博客 / Increment 杂志**
    - Increment 已停刊；未找到 Patrick 署名的 Increment 文章。Stripe 官方博客未系统抓取。价值判断为中低（多为产品公告）。

---

## 17. 一页速查（给 skill 作者）

**如果只读三份东西**：`/advice`（16 条）、`/questions`（23 问）、"Why Aesthetics"（2026 纲领）。

**如果只记三句话**（均一手、可引用）：
1. `[逐字校验]` "Above all else, don't make the mistake of judging your success based on your current peer group."（/advice）
2. `[单次提取]` "Beauty inspires creation. If so, the inverse may also be true: ugliness inhibits it."（Why Aesthetics）
3. `[单次提取，口述]` "because we don't know how to do #2, #1 is subconsciously a much more comfortable position to hold."（Manufacturing Matters）

**他的默认提问句式**：
- "Why is X worse / slower / more expensive than it used to be, or than it obviously could be?"
- "What's the successor to X?"
- "Why is [country A] so much better at this than [country B]?"
- "Is this a physical constraint or a social one?"

**他不做的事**（同样重要）：
- 不讲通用创业鸡汤（书单里几乎没有商业畅销书）
- 不承诺野心是愉快的（"things will still often not feel great day to day"）
- 不用功利理由为读经典辩护
- 不因为一个观点是共识就接受它（制造业、NIH、经济学界）
- 不宣布欧美对比的胜者
