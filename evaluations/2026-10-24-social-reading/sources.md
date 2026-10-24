# 来源、范围与定位

访问日期：2026-10-24。选材不要求“最新新闻”，而要求结构不同、原文可读、能核对关键内容。

## S：科学报道

- [NASA’s Webb Proves Galaxies Transformed the Early Universe](https://science.nasa.gov/missions/webb/nasas-webb-proves-galaxies-transformed-the-early-universe/)，NASA Webb Mission Team，原刊 2023-06-12。网页显示的后续更新日期不是研究发表日期。
- 已读取正文；抓取文本见 `sources/S.txt`，含附加导航和图注，评测只使用正文。
- 核心：年轻星系的恒星使周围气体电离，结合类星体沿线气体观测与韦布定位星系，为局部再电离提供直接证据。
- 对照位置：开篇与再电离解释；“Lilly’s team intentionally targeted…”及随后地面望远镜观测方法；“The researchers then used Webb…”中的约 200 万光年半径；后文 117 个星系与黑洞支线。
- 文章重构核心机制与观测依据，省略仪器、论文名称清单和黑洞质量支线。X 沿用相同范围，不冒充研究最新综述。

## T：技术指南

- [MDN《HTTP 缓存》](https://developer.mozilla.org/zh-CN/docs/Web/HTTP/Guides/Caching)，Mozilla Contributors，页面标示最后更新 2026-07-01。
- 已读取正文；抓取文本见 `sources/T.txt`。
- 原文很长，成稿围绕存储、复用、验证、共享与常见策略组织，不声称是所有缓存配置的完整教程。省略旧代理兼容、QPACK 编码、刷新细节及托管缓存实现。
- 对照小节：不同种类的缓存、基于 age 的缓存策略、Vary、验证、不使用缓存、常见的缓存模式。
- 许可与改编署名见稿件。参数与 HTTP 标头保留精确形式；未执行任何服务器配置或代码。

## I：多人采访

- [USGS：Landsat Science Team Focuses on Advanced Satellite Technology](https://www.usgs.gov/landsat-missions/news/landsat-science-team-focuses-advanced-satellite-technology)，Landsat Missions，2026-10-20。
- 网页工具已读引言与完整四组问答；直抓被拦截，因此不保存、也不声称拥有本地全文副本。
- 不是只读积雪一节：原文包含 Yun Yang（田块用水）、Philip Dennison / Mickey Campbell（非光合作用植被）、Ryan O’Shea（藻华）、Ned Bair（积雪）五位研究者。
- 开头为 Landsat 10 拟于 2031 年发射、26 个波段的计划；各问答同时谈研究任务、实际用户及数据处理需求。成稿保留整组主题，不改成单独积雪文章。
- 对照小节与关键事实：Yun Yang 第 2、3 问；Dennison/Campbell 第 2 问；O’Shea 第 2 问中的训练数据覆盖；Bair 第 3 问中的云雪辨认。
- 蒸散定义补充核对：[USGS：Evapotranspiration and the Water Cycle](https://www.usgs.gov/water-science-school/science/evapotranspiration-and-water-cycle)，已在最终稿对应位置附来源。

## N：文学叙事

- [鲁迅《孔乙己》](https://zh.wikisource.org/zh-hans/孔乙己)，1919 年；页面称据《鲁迅全集》版本。[读取版本固定链接](https://zh.wikisource.org/w/index.php?title=孔乙己&oldid=2605389)。
- 网页工具读取从酒店格局至末句的全文；直抓 403，不伪造本地全文。仅把小说作为小说重构，不当真实纪实报道。
- 对照位置：开篇长衫与短衣；抄书经历属于小伙计听来的议论；教“茴”与分豆；酒客转述丁举人家打人；近冬重返酒店；末段未确认死讯。
- 关键边界：最后一次到店时是“眼色，很像恳求”，不是直接记录了明确请求；“大约”与“的确”并存，不改成已证实的死亡消息。

## X 格式核对

- [X 官方字符计数说明](https://docs.x.com/fundamentals/counting-characters)：标准帖按加权字符计算，中文通常权重为 2，URL 经转换按 23 计。
- 统计使用 [twitter-text v3 官方配置](https://raw.githubusercontent.com/twitter/twitter-text/master/config/v3.json)，本轮文本无 emoji，只含可直接按该配置计数的字符与明确 URL。它是本地格式核对，不是实际账号发布或客户端验证。
