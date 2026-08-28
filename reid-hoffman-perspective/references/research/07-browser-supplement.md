# 07 · 浏览器补充调研:Reid Hoffman 一手素材(Masters of Scale + LinkedIn Pulse)

> 抓取方式:Chrome 浏览器逐页 navigate + get_page_text,单标签页串行访问。目标:WebFetch 因 robots.txt 拿不到的一手原文(播客逐字稿、LinkedIn 长文)。全部为只读抓取,未点击任何提交/登录/购买按钮,未输入任何账号密码。

---

## 一、抓取清单与内容摘要

### A. Masters of Scale 播客逐字稿(`references/sources/transcripts/`)

| 文件名 | 来源 URL | 内容摘要 |
|---|---|---|
| `mos-reid-story-part2.txt` | mastersofscale.com/episode/reid-hoffman-make-everyone-a-hero-part-1/(站点 URL 与内容确实反了,已按用户提示核实:此链接内容是"Part 2") | June Cohen 反客为主采访 Reid。讲他 PayPal 期间与 Peter Thiel 的路线之争、eBay 攻防战、2002 年逆势创立 LinkedIn 的判断依据、LinkedIn 早期冷启动失败(朋友帮忙但"这不是我的使命")、"病毒循环"设计、把 CEO 让位给 Jeff Weiner 的详细交接方法论、被 Microsoft 收购的整合安排,以及一段完整的 15 题 Lightning Round(Reid 自答,含"人生最大的尴尬"和"人生最大的成就")。 |
| `mos-first-be-human.txt` | mastersofscale.com/first-be-human-thoughts-on-the-crisis-reid-hoffman/ | 2020 年 3 月疫情初期独白(Bob Safian 主持,Reid 是嘉宾但内容近乎独白)。核心:危机中"先做人,再做企业家"、SWOT 式的威胁/机会分析法、"死亡归零"不可能、"fail fast 不是目的,是学习更快"、以及个人减压方法。 |
| `mos-100th-episode.txt` | mastersofscale.com/100th-episode-what-we-learned/ | Reid + June Cohen 主持的第 100 集圆桌,嘉宾 Brian Chesky、Tyra Banks、Angela Ahrendts、Sallie Krawcheck、Franklin Leonard。主题:创业孤独感、最昂贵的教训、信任的速度、女性互助网络、故事化表达与脆弱性。**Reid 提问技巧的绝佳样本**(见下)。 |
| `mos-how-to-get-funded-now.txt` | mastersofscale.com/how-to-get-funded-now/ | 2025 年 10 月 Summit 现场圆桌(Van Jones 主持,Reid、Stacy Brown-Philpot、Aileen Lee 对谈)。内容:2025 年融资标准大幅提高、AI 时代如何判断创始人、Reid 的谈判哲学("valuable companies emphasize chances of being successful, not dilution %")、AI 与就业的"zoomers/bloomers/gloomers/doomers"框架。 |
| `mos-guest-brian-chesky.txt` | mastersofscale.com/brian-chesky/ | Masters of Scale **第一集**(2017)。Reid 主持,嘉宾 Brian Chesky。核心理论:"要规模化,必须先做不能规模化的事"。含 Airbnb "11 星体验"思想实验、Paul Graham"去见你的用户"训诫、Ricardo 感动落泪的 Trips 案例。**片尾"my theory is"完整段落已收录**。 |
| `mos-guest-sara-blakely.txt` | mastersofscale.com/sara-blakely-how-to-find-your-big-idea/ | Reid 主持,嘉宾 Sara Blakely(Spanx)+ 探险家 Andrés Ruzo + 前 USPTO 局长 Michelle Lee。核心理论:"找到大创意只有一个办法:找、找、找,然后行动"。含 Reid 自己回答"你在哪里想大问题"的片段、专利建议、"保密一年"的策略。**片尾"my theory is"完整段落已收录**。 |

### B. LinkedIn Pulse / reidhoffman.org 职业建议长文(`references/sources/articles/`)

全部**未遇到登录墙**,均完整抓取成功。

| 文件名 | 来源 URL | 内容摘要 |
|---|---|---|
| `abz-planning.txt` | linkedin.com/pulse/abz-planning-entrepreneurial-approach-career-plans-reid-hoffman/ (2022-06-01) | ABZ 职业规划法:Plan A(当前打法,持续迭代)、Plan B(转向路径,靠"做"而非"想"来验证)、Plan Z(兜底方案,给你冒险的底气)。用他自己从学术界转向硅谷的真实经历举例。 |
| `i-to-the-we.txt` | linkedin.com/pulse/i-to-the-we-you-your-team-reid-hoffman/ (2022-06-14) | 反驳"白手起家"神话与"团队里没有我"的陈词滥调,提出"I-to-the-We":个人能力经网络放大是指数级的。给出建立真诚人脉的两个技能:换位思考、先给予后索取。 |
| `network-intelligence.txt` | linkedin.com/pulse/tap-network-intelligence-develop-literacy-reid-hoffman/ (2022-06-29) | "网络智能"框架:人脉是获取"私域情报"的唯一稳定来源。把可咨询的人分为三类——领域专家、"懂你"专家、跨界聪明人。附具体提问话术(引用 Tyler Cowen 的万能问题)。 |
| `four-tiers-of-engagement.txt` | linkedin.com/pulse/four-tiers-engagement-what-silicon-valley-taught-me-time-reid-hoffman/ (2016-04-09,reidhoffman.org 同源页面渲染失败改用 LinkedIn 镜像抓取成功) | 时间管理/精力分配框架:Principal(全押,你是船长)、Board Member(战略级但非全职)、Investor(被动响应)、Friend(偶发帮忙)。用他自己在 PayPal 早期身兼 SocialNet 创始人+PayPal 董事的真实决策举例。 |

---

## 二、他的提问方式:至少 15 条英文原句 + 套路总结

### 原句摘录(均为 Reid Hoffman 作为主持人/提问者的原话)

**开场破冰式提问(点名 + 抛出统一问题模板)**
1. "To break the ice, I'm going to start by leading us through a classic round table discussion on entrepreneurship. Let's dive in. What's harder about entrepreneurship than most people realize? Brian, maybe you'd like to kick us off?" — mos-100th-episode.txt
2. "Amen. Let's move on to the next question, which is: What's the most expensive lesson you've ever learned? Sallie, why don't we start with you on this one?" — mos-100th-episode.txt
3. "Franklin, same question." — mos-100th-episode.txt(同一问题依次点名不同嘉宾,极简复用)
4. "And Brian." — mos-100th-episode.txt(同上,几乎不换措辞地把提问抛给下一人)

**开放式复盘邀请("Any reflections?"句式)**
5. "So Angela, obviously many great things here. Everything from the parallel, from the app of the iOS into the store and the platform, to the creativity and generativity, to team kind of giving permission for the team to drive underneath the mission and making that happen. Any reflections?" — mos-100th-episode.txt
6. "Any additional reflections, Franklin, from this thing, which is the core iconic inside of this amazing new thing on finding scripts?" — mos-100th-episode.txt
7. "So we're now going to transition. I've interviewed everyone here for their own episodes of Masters of Scale in the past. I'd love to reflect on our original conversation and your episodes a bit." — mos-100th-episode.txt
8. "It's among the things that I really loved was the kind of both scrappiness and vision of the huge future. Any reflections as you now look back from Airbnb being a global platform everywhere in the world ... back to that kind of early photography moments?" — mos-guest-brian-chesky.txt

**收尾统一问题(把个人故事升华为"故事讲述"这一元主题)**
9. "Awesome. So let's end with saying, look, where does storytelling play into how you tell your founding story, what you're doing, how you're doing your company?" — mos-100th-episode.txt

**追问/压缩式提问(对方叙述模糊时,用极简短句逼对方压缩到关键信息)**
10. "I'm curious. Give me the next three sentences." — mos-reid-story-part2.txt(对 Peter Thiel 深夜"秘密计划"发言的追问)
11. "No, I'm still lost. Another three sentences." — mos-reid-story-part2.txt(同一段对话里再追问一次)

**善用轻松自嘲/降维类比拉近关系**
12. "One of the things that I love about talking to you is, my world is this whole digital world, and — the people who actually build things, that's super cool." — mos-guest-sara-blakely.txt
13. "Hey, it's—you know, it's different."(回应 Blakely"我的世界全是内衣"的自嘲)— mos-guest-sara-blakely.txt

**标准化 Lightning Round 问题(对每位嘉宾重复使用,便于跨集比较)**
14. "Your favorite place to think big." — mos-guest-sara-blakely.txt(对多位嘉宾反复问同一句)
15. "And this is the one that you get a laugh, your favorite place to think big." — mos-guest-sara-blakely.txt

**用类比/延伸问题把具体案例推向可扩展的原则**
16. "Well, which enables you to get to scale since obviously you do have to get to scale." — mos-guest-brian-chesky.txt
17. "But how far do you go toward the 11-star experience?" — mos-guest-brian-chesky.txt

### 提问套路归纳

1. **先立"统一问题模板",再挨个点名复用**:他极少给每位嘉宾定制不同问题,而是设计一个通用问题("最昂贵的教训是什么""你在哪里想大问题"),原封不动地抛给每个人,借此制造可横向对比的"数据点"——这既提高了播客的可剪辑性,也让听众清楚看到不同背景的人对同一问题的分化答案。
2. **开场用一句"轻量事实/情绪确认"降低门槛**,再无缝转入正题(如对 Blakely 的"你的世界不一样"式打趣),目的是让嘉宾放松,愿意讲细节而非公关辞令。
3. **中段用极短追问逼近真相**:一旦嘉宾的表述开始变得抽象或打太极("我们的秘密计划是..."),他会用"Give me the next three sentences"这类几乎苛刻的压缩指令,强迫对方给出可验证的具体信息,而不是接受空泛陈述。
4. **反复使用"Any reflections?"作为万能追问器**:这是他最高频的追问句式——不预设答案方向,把解释权交还给嘉宾,自己只负责"重述刚才的内容"作为引子(体现他善于总结复述对方观点,再抛回去让对方深化)。
5. **收尾必回到"元主题"**:无论具体话题多发散,他几乎每集都会用同一个收尾问题("故事讲述在你的创业中扮演什么角色")把节目拉回统一的理论框架,为片尾的"my theory is"总结做铺垫。
6. **对同一件事追问"闭环":What/How/Why 三连**——例如对 Chesky 先问"怎么做规模化",再问"极限体验设计到哪一步为止",最后问"这如何反哺可规模化的部分"——层层递进而不重复。

---

## 三、他给个人建议时的原话(逐条 + 出处)

**关于失败与风险**
1. "You don't fail fast because you want to fail fast. It's failing fast is better than failing later." — `mos-first-be-human.txt`
2. "There's a possibility – every organization – there's a possibility that you're just dead. Don't try to get death to zero. Try to figure out that within this universe of, 'How do I play for an interesting life?'" — `mos-first-be-human.txt`
3. "The single greatest embarrassment of your career... finding out through the paperwork that I was no longer on the board of the company that I founded."(SocialNet 出局往事)— `mos-reid-story-part2.txt`
4. "Your ability to follow your imagination, to take risks, to be bold, don't limit yourself." — `mos-how-to-get-funded-now.txt`

**关于人际关系与团队**
5. "Life is a team sport, not an individual sport. Never mistake that." — `mos-first-be-human.txt`(在危机应对和"游戏化人生"两个语境中反复出现的口头禅)
6. "Focus on what you can give to others, rather than what you can get from others." — `i-to-the-we.txt`
7. "Generous relationship builders, or 'givers,' try to help other people first. They don't keep score." — `i-to-the-we.txt`
8. "Shift from asking yourself the very natural question of 'What's in it for me?' and ask instead, 'What's in it for us?'" — `i-to-the-we.txt`
9. "It is important to have people you check in with, right? So CEOs and founders can check in with board members or other CEOs... because part of how we manage our stress is by helping each other." — `mos-first-be-human.txt`
10. "We were willing to be really bold, we were willing to take risks. We didn't kind of panic about our careers if, 'Oh gosh, this thing blows up and doesn't work.'"(回忆 PayPal 团队)— `mos-reid-story-part2.txt`

**关于职业规划与时间分配**
11. "My original career Plan A was to pursue academia because I thought it would be the best way to have an impact on the world... This realization led me to shift to a Plan B... My Plan B was to build new software." — `abz-planning.txt`
12. "Learn by doing. And do things with what you learn." — `abz-planning.txt`
13. "Do you really have time to assume the responsibilities that a principal level of engagement demands? Are you so taken with an idea or a principal that you know you at least want to function as an investor?" — `four-tiers-of-engagement.txt`
14. "If you're a principal, you're a captain of the ship. And that means it's your obligation to do everything that's reasonably possible to bring that ship to port." — `four-tiers-of-engagement.txt`
15. "School is single-player mode. The real world is multiplayer mode." — `network-intelligence.txt`

**关于 AI 时代的个人能力**
16. "There's no way to AI-proof yourself or AI-proof your job, but the jobs of the future will be: how well do you use AI in order to do them. ... Start using it. Literally, it's almost like a ritual thing of how many times a day are you using Deep Research." — `mos-how-to-get-funded-now.txt`
17. "Go take your idea and go into your favorite frontier models and say, 'Critique this. How would a skeptical VC, what would they tell me about this?'" — `mos-how-to-get-funded-now.txt`

---

## 四、他的"my theory is..."结尾段(完整摘录,共 3 段)

这是他把一个具体人物的具体故事,升维成普适方法论的标准收尾动作——几乎每集固定出现在片尾,句式高度模式化("I'll [prove/revise] my theory... I'm Reid Hoffman. Thank you for listening.")。

**① Brian Chesky 集(第一集,主题:先做不能规模化的事)**

> "And if you have a tiny startup, I have good news for you. Now is the moment you can take the most daring leaps of your career. Dream big. And act small. Pay passionate attention to your users. Handcraft the core service for them. Create a magical experience. And then figure out what part of that magical handcrafted thing can scale.
>
> I'm Reid Hoffman. Thank you for listening."
> —— `mos-guest-brian-chesky.txt`

**② Sara Blakely 集(主题:如何找到你的大创意)**

> "And with that, I'll revise my theory: to find your big idea, you have to look for it. And look for it. And look for it. And then act—and know that this is only the first step in a long entrepreneurial journey.
>
> I'm Reid Hoffman. Thank you for listening."
> —— `mos-guest-sara-blakely.txt`

**③ "Make everyone a hero"(他自己被反向采访的两集,June Cohen 转述并确认为"the theory in the Reid Hoffman episode")**

> "I believe that to chart a truly epic journey to scale – you need to make everyone you enlist a hero – not just in your story, but in their own."
> —— `mos-reid-story-part2.txt`(June Cohen 在开场与结尾两次完整重复此句,并明确称其为"Reid Hoffman 那期节目的理论")

**结构规律**:三段的共同骨架是——① 用一个动词短语命名理论("Dream big and act small" / "Look for it, look for it, look for it, then act" / "Make everyone a hero"),② 立刻给出 2-4 条可执行的具体动作清单,③ 用"I'm Reid Hoffman. Thank you for listening."收尾,把整集嘉宾的个人叙事正式"打包"成读者可以直接套用的通用公式。

---

## 五、抓取失败 / 需登录清单

**本次任务无失败项。** 具体说明:

- LinkedIn Pulse 三篇长文(`abz-planning`、`i-to-the-we`、`network-intelligence`)均**未触发登录墙**,`get_page_text` 直接拿到完整正文——推测因为这类 Pulse 长文本身对未登录访客也开放阅读。
- "The four tiers of engagement" 一文在 **reidhoffman.org 自建站的原生页面**(`/four-tiers/` 子路径)访问后 `get_page_text` 返回"No text content found. Page may contain only images, videos, or canvas-based content."——判断是该站点把长文渲染成了图片/画布或依赖客户端脚本、时序性内容;**已改用 LinkedIn 镜像页面成功抓取完整正文**,内容与标题确认一致,不算实质性失败。
- Masters of Scale 的 6 篇播客逐字稿全部一次性成功抓取,无需登录、无 CAPTCHA、无付费墙。

---

## 附:本次新增/确认文件路径

```
references/sources/transcripts/mos-reid-story-part2.txt
references/sources/transcripts/mos-first-be-human.txt
references/sources/transcripts/mos-100th-episode.txt
references/sources/transcripts/mos-how-to-get-funded-now.txt
references/sources/transcripts/mos-guest-brian-chesky.txt
references/sources/transcripts/mos-guest-sara-blakely.txt
references/sources/articles/abz-planning.txt
references/sources/articles/i-to-the-we.txt
references/sources/articles/network-intelligence.txt
references/sources/articles/four-tiers-of-engagement.txt
```
