# 文章精读重构 · sky-article-rewriter

把已有文章或播客转录，改写为适合公众号、头条号或 X 的内容：**核心突出、干净利落、通俗易懂，有依据。**

它会先理解原文，识别阅读障碍，再按读者的理解顺序组织内容。难懂的概念按需用相似案例解释，人物和背景按需交代。优先交付核心判断、关键依据与必要条件，解释到够懂即止，删去重复、套话和旁支。标题与开篇尽早交付有价值的信息，兼顾社交媒体阅读中的吸引力；成稿可以独立阅读，不靠夸张或拖延答案。

这是一个供 Codex 使用的 Skill，由提示词指令与参考指南组成，无需 API Key 或额外运行依赖。

## 适用范围

支持采访与播客转录、技术说明与教程、生活随笔、人物纪实和观点文章。按材料选择必要的方法，保留观点归属、证据、条件及重要叙事关系；不把所有内容都改成建议清单。

## 安装

将本仓库克隆到本地 Codex 技能目录。下列命令适用于尚未安装本技能的环境：

```bash
git clone https://github.com/skyzizhu/sky-article-rewriter.git \
  "${CODEX_HOME:-$HOME/.codex}/skills/sky-article-rewriter"
```

如果使用了自定义技能目录，请将目标路径替换为对应位置。重新打开一个 Codex 会话后，通过 `$sky-article-rewriter` 调用。

如果已有旧版 `sky-article-deep-reader`，请先备份自己的修改，再将旧目录移出技能目录，避免两个版本同时被选中。仓库中的正式标识为 `sky-article-rewriter`。

## 快速使用

### 默认：重构为核心优先的精炼文章

```text
请使用 $sky-article-rewriter 处理下面的文章。
面向没有相关背景的读者，重组为核心突出、干净利落、通俗连贯的精炼文章。
尽早交付核心信息，解释够懂即可，保留关键依据与重要限制。

[粘贴正文、提供可读取的文件或文章链接]
```

只有链接但无法获取正文时，技能会请求提供文本，不会根据标题假装读过全文。播客请提供转录文本或可读取的转录来源；本技能不包含音频转写功能。

### 指定范围、篇幅或输出位置

```text
请使用 $sky-article-rewriter 处理这篇文章。
目标读者：刚接触这个领域的人。
篇幅：约 2000 字，优先讲清核心机制和关键案例。
保留：作者的主要判断、重要依据和限制条件。
请将结果保存为当前项目中的 article-rewritten.md。

[文章正文或文件路径]
```

### 指定社交平台

```text
请使用 $sky-article-rewriter 处理下面的文章。
发布平台：X，写成简短串帖。
首帖直接给核心发现，后续补必要依据和条件，不做原文流水账。

[文章正文]
```

平台也可以指定为公众号或头条号；标题、开篇和正文仍以原文事实为依据。

### 需要逐段带读时

```text
请使用 $sky-article-rewriter 带我逐段阅读这篇文章。
保留原文顺序，解释难点和段落之间的关系，提供必要的原文定位。

[文章正文]
```

## 默认交付与平台

- 未指定平台时，输出一份适合移动阅读的精炼文章，不逐项追问或同时生成多平台版本。
- 公众号、头条号：标题、正文及必要来源。一般说明、观点和采访类文章以约 800—1500 字为预算；简单内容更短，必要时可超出。
- X：默认短帖，放不下依据与条件时组织为简短串帖；不机械切割长文。首帖交付实质信息，关键限定随判断出现，每帖有信息增量。
- 用户指定篇幅、格式、深入解读或完整教程时优先遵守；文学、纪实不为凑字数删去必要细节。

内部先确认原文核心，再筛选内容、安排顺序、成文及核对；默认只交付成稿和必要来源。除非用户要求，不输出分析报告，不保存或发布内容，不生成图片、网页。

## 文件结构

```text
sky-article-rewriter/
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    ├── writing-guide.md
    ├── restructuring-guide.md
    ├── narrative-and-flow.md
    ├── interview-podcast.md
    ├── technical.md
    ├── life-documentary-opinion.md
    ├── examples.md
    └── long-content-and-evaluation.md
```

| 文件 | 用途 |
|---|---|
| [SKILL.md](SKILL.md) | 统一入口、类型路由、处理强度与质量检查 |
| [社交媒体写作指南](references/writing-guide.md) | 平台呈现、标题、开篇、语言与案例取舍 |
| [结构重排指南](references/restructuring-guide.md) | 内容取舍及文章、X 串帖对照示例 |
| [人物、事件与段落衔接](references/narrative-and-flow.md) | 叙事要素、时空关系和阅读推进 |
| [采访与播客](references/interview-podcast.md) | 对谈整理、观点归属及修正 |
| [技术说明与教程](references/technical.md) | 概念解释、研究范围与操作准确性 |
| [生活、纪实与观点](references/life-documentary-opinion.md) | 不同内容的具体改写方法 |
| [真实改稿对照](references/examples.md) | 过强转述、支线删减、必要条件与串帖收尾 |
| [长内容与效果评估](references/long-content-and-evaluation.md) | 长文本组织及真实试读方法 |

采用一个 Skill 统一管理，按需读取参考指南；这些文件不需要分别安装。

## 边界与验证状态

- 真实补充案例需要查证来源；假设案例必须说明性质。能否获取外部材料取决于运行环境中的工具与访问权限。
- 改写技术教程不会自动执行命令、安装依赖，也不代表代码已经测试。
- 不凭空补齐原文缺失的信息，不把部分正文称为全篇解读。
历史验证按当时版本记录，详见下表，不自动代表当前规则的效果：

| 记录 | 范围 |
|---|---|
| [2026-10-18 首轮](evaluations/2026-10-18/README.md) | 九份真实材料的模型评测与定向回归 |
| [第二轮](evaluations/2026-10-18-round2/README.md) | 三份长材料、六次运行与交叉复核 |
| [审稿执行校准](evaluations/2026-10-18-step5-calibration/README.md) | 两次小范围片段验证 |
| [简洁性校准](evaluations/2026-10-19-concise-review/README.md) | 四份虚构短文的改写与纠错 |
| [新增真实材料](evaluations/2026-10-19-real-articles/README.md) | 四篇文章的改写与模型复核 |
| [阅读推进校准](evaluations/2026-10-19-reading-flow-calibration/README.md) | RAG 阅读反馈及片段编辑 |
| [社交媒体试跑](evaluations/2026-10-24-social-reading/README.md) | 四篇真实材料与一组 X 串帖，保留初稿、修订与限制 |

试跑后已有[执行校准](evaluations/2026-10-24-social-reading/execution-calibration.md)。本次继续合并重复的平台规则，明确首帖限定与便于复制的排版，并压缩本说明。上述稿件对应其冻结版本；本次完成规则、引用与格式核对，尚未重做全文试跑。

- “愿意继续读”是设计目标，需要真实读者反馈检验，不承诺读完率或理解效果。

## 反馈与改进

欢迎通过 [Issues](https://github.com/skyzizhu/sky-article-rewriter/issues) 反馈具体问题。建议提供：文章类型、目标读者、可公开的原文片段、对应改写、哪里难懂或拖沓，以及期望的变化。请勿提交未经允许公开的原文或个人信息。

优先修复真实材料中出现的问题：区分单篇编辑问题、规则缺口和执行遗漏，按需精简或修改对应指令，再检查是否影响其他类型文章。文章润色、技能更新及新版试跑分别核验，不将单篇改好视为技能效果已经稳定。
