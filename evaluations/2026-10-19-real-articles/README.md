# 当前版本的四篇真实文章评测

日期：2026年10月19日。冻结技能版本为 `4d6adea05fc402ce7b61df1dcb9b2e30a5ca97bd`。本轮只评测，不修改技能，不覆盖前轮文章。

完整结论、残余问题及逐篇产物见[评测结果](results.md)。

## 材料与范围

| 编号 | 原文 | 实际范围 |
|---|---|---|
| I：访谈 | [Wikinews：Interview with LibriVox founder Hugh McGuire](https://en.wikinews.org/wiki/Interview_with_LibriVox_founder_Hugh_McGuire)，2006年5月28日 | 记者引言及全部问答，至Whitman末问答；保留2006年知识时点，非当前项目介绍 |
| T：技术说明 | [MDN：HTTP协议中的数据压缩](https://developer.mozilla.org/zh-CN/docs/Web/HTTP/Guides/Compression) | 中文页面完整正文三个压缩层面，排除导航和页脚；原文可见更新时间2025年7月4日 |
| L：生活与抒情散文 | [朱自清《匆匆》](https://zh.wikisource.org/zh-hans/匆匆)，1922年 | 单篇完整五段及日期，不是散文集；同作者此前其他文章曾测过，本篇为新材料 |
| H：历史叙述 | [NPS：Path of the Flood](https://www.nps.gov/jofl/learn/historyculture/path-of-the-flood.htm) | Conemaugh Valley及South Fork、Mineral Point、East Conemaugh、Woodvale、Johnstown全部可读正文和图注；不延伸为整套洪水史；原页可见更新2026年4月21日 |

四篇均不是上一轮的虚构材料，也没有重用先前测过的原文。T与旧测试的HTTP缓存来自同一文档站、同属HTTP领域；L与旧《背影》作者相同。因此新文本不等于所有来源、作者和领域都完全陌生。

I、L的直接HTTP获取受到403限制，改由网页工具完整正文行取得；I覆盖网页行115—170，L覆盖117—126并补标题、作者及写作日期。T、H直接获取成功。H的正文包含标题标签外的裸文本，提取时已将其纳入；未把最初不完整提取当作完整输入。图像没有下载或独立审阅，不宣称视觉核验。

完整原文仅留本地，仓库保留来源、指纹、生成产物和评测记录。输入统计包含标题、定位标记及可见图注，并非净正文计数；详见 [protocol.json](protocol.json)。

## 方法

每篇在新的独立上下文运行一次，使用同一冻结技能及同一请求，面向无相关背景的中文成年人，要求忠实核心、通俗易懂、简洁明了、循序渐进。未给统一字数或压缩比例，也没有约400字上限。每篇依次保存草稿、原文回查修订记录和交付稿，不能先改完再重造草稿。

全部交付冻结后，才由未写该篇的上下文交叉复核：先读交付稿与原文作判断，再读草稿和审稿记录核实实际修改。复核关注核心、准确、易懂、简洁，以及回查是否修掉问题或引入新问题。具体问题须有原文位置和成稿句段；合理压缩、可接受释义和尚不能确认的疑点分开记录。

简洁通过信息价值判断：有没有重复解释、套话、同作用案例和讲评，删减是否损失核心与必要条件。中文改写与英文输入不按字符或词数直接计算质量；同一篇稿件的草稿与交付稿长度仅作描述。没有新旧版本对照，没有真实读者复述、跳读或读完数据，也没有统计稳定性结论。

## 来源许可

I原文署名Wikinews，适用其2006年文章的[CC BY 2.5](https://creativecommons.org/licenses/by/2.5/)许可。T原文由Mozilla Contributors提供，[MDN许可说明](https://developer.mozilla.org/en-US/docs/MDN/Writing_guidelines/Attrib_copyright_license)允许按CC BY-SA 2.5或更新版本使用；本目录T的草稿与交付改写采用[CC BY-SA 2.5](https://creativecommons.org/licenses/by-sa/2.5/)，保留来源和修改说明。L原作源页声明为公有领域，仍保留朱自清署名。H只重构NPS机构文字，不复制照片或地图。

上述声明针对对应文章内容，不将整个技能仓库或其他来源统一改成同一种许可。
