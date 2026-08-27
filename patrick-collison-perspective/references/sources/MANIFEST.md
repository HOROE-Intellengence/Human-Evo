# 一手语料清单

| 文件 | 来源 | 保真度 | 说明 |
|---|---|---|---|
| `transcripts/tim-ferriss-353-2018-full.md` | https://tim.blog/2018/12/24/the-tim-ferriss-show-patrick-collison/ | 官方全文 transcript | 用户提供。人生/读书/野心心理学密度最高的单一来源 |
| `transcripts/cwt-collison-interviews-cowen-2017-full.md` | https://conversationswithtyler.com/episodes/patrick-collison/ | 官方全文 transcript | 用户提供。**他反向采访 Tyler Cowen**——「他怎么提问」的最佳样本 |
| `articles/*.md`（12 个官网页面） | patrickcollison.com | Chrome get_page_text 逐字 | /advice /questions /fast /bookshelf /growth /about /labs /culture /svhistory 等全文 |
| `articles/dispatches/*.md`（**23 篇**） | patrickcollison.com/dispatches | Chrome get_page_text 逐字 | 他 2012–2026 的亲笔长文全文，最新最一手 |
| `articles/x-patrickc-timeline.md` | https://x.com/patrickc | 部分（9 条，含 4 条 quote tweet） | 未登录状态下抓到的上限 |
| `articles/stripe-layoff-memo-2022.md` | stripe.com/newsroom | 逐字 | 2022 裁员信全文 |

## 已知缺口
- **X / @patrickc 的 reply 时间线：0 条**。`/with_replies` 需登录，本次 Chrome 未登录，两次尝试均失败（失败记录见 `articles/x-patrickc-replies.md`，未尝试登录、未绕过任何验证）。主时间线抓到 9 条，含 4 条 quote tweet。nitter.net 已于 2026-08-25 因 X Corp. 律师函下线。
- Bloomberg Businessweek 2017「Seven Lines of Code」全文（付费墙）
- The Information 的 Stripe 系列（付费墙）
- Stripe 年度信 PDF 正文
