# Technical / documentary independent forward test

- 评测日期：2026-10-18（用户时区 Asia/Shanghai）。
- 被测技能：`/Users/skyzizhu/.codex/skills/sky-article-rewriter`，父任务指定基线提交 `8121010`。
- 实读 SKILL.md 的 SHA-256：`15deb6feacfe4ccf51831cb6cd4ab88165cbfe95852e05a131890b449c61bf43`。
- 执行者先读技能、对应参考和原始网页，独立生成三份基线，再开展下述自检；生成前未看其他代理发现、修订规则或目标答案。
- 未执行任何被改写教程中的Git命令；未修改技能和仓库；未复制网站全文到仓库。

## 固定任务

MDN和Git：

> 请使用 `$sky-article-rewriter` 重构以下链接的文章。面向没有相关背景、愿意认真理解的中文成年人；可独立阅读，保留原文核心，通俗、连贯、循序渐进。输出约350–450字的精简中文文章，明确它不能代替全文详细重构；教程保留必要的精确命令与条件。不要执行教程命令。

NASA：

> 请使用 `$sky-article-rewriter` 重构以下链接的历史纪实。面向没有相关背景、愿意认真理解的中文成年人；可独立阅读，保留原文核心，通俗、连贯、循序渐进。篇幅约600–900字，原文过短时以忠实和不凑字数为先；不要为丰富故事补造情节、心理或因果。

## 材料与实读范围

| 编号 | 标题、URL | 作者、日期 | 完整性与获取 |
|---|---|---|---|
| T1 | [HTTP caching](https://developer.mozilla.org/en-US/docs/Web/HTTP/Guides/Caching) | MDN contributors；页面明确最后修改于2026-08-14 | web工具打开后，进一步以HTTP读取HTML提取`article.main-page-content`，从开篇至More about managed caches、See also及末尾修改信息全部读取。正文包含所有目录小节；未仅据摘要写作 |
| T2 | [1.6 Getting Started — First-Time Git Setup](https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup) | Pro Git第二版；本节未单列作者或发布日期，不猜日期 | web完整返回正文行186–251；身份、三级配置、编辑器、默认分支、检查与来源均已实读。直接HTTP另一次尝试403，但web已提供完整所选小节，不将整本书称为已读 |
| D1 | [From Pilot to First on the Moon: Armstrong’s Start in Cleveland](https://www.nasa.gov/history/from-pilot-to-first-on-the-moon-armstrongs-start-in-cleveland-2/) | Robert S. Arrighi，NASA Glenn；发布2019-07-18；页面更新2024-03-13 | web正文行257–259共三段、图片说明254、260及来源署名270–271全部读取。未访问链接中的另外几份招募史料，不把它们称作已核验 |

NASA联邦官方历史资料作为本轮较完整叙事重构材料；MDN、Git输出受本轮精简约束，不是默认完整重构质量的替代测量。实际输出汉字计数含标题及说明：MDN355，Git295（另有多行命令），NASA557（加标点与英文名称后约达常规600字篇幅）。没有为达标补写史实。

## 冻结基线

- `baseline-mdn.md`：`e47eb3a343d95e06c19a0f027e11da23e626e151173cab323a89b44ed111cc84`
- `baseline-git.md`：`b58467d6b8b7793fdc900b80eaf42e8f1b00878ae458796c40ed088154f4160c`
- `baseline-nasa.md`：`9556640db515bd4a27e4f7298517636743cf2998aeb9d280cc0c05132f916fce`

这些SHA在后续发现之前记录。后续修订须另存，不能覆盖基线。
