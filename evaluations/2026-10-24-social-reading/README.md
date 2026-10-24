# 2026-10-24：新版社交媒体改写试跑

四篇公开真实材料，五份输出。目标是实际执行当前技能，定位准确性、信息取舍与平台呈现问题，再决定是否改规则。

## 范围与方法

- 由当前对话中的同一模型完成选材、初稿、审稿与修订；属于同上下文自检，不是独立盲评、多个模型运行或真实读者试读。
- 初稿生成前冻结主文件、参考指南和 UI 提示词，见 `frozen-before/` 与 `version-before.json`。入口快照保存为 `SKILL.snapshot.md`，防止被技能扫描重复识别；文件内容与指纹未变，物理路径映射见 `snapshot-paths.json`。冻结的是本分支未提交的工作文件，不是 Git HEAD 中的旧版。
- 面向无专业背景的成年人：S、T 为公众号文章，I、N 为头条号文章；X 使用 S 的相同原文写中文串帖。所有稿件均为新生成，未挪用历史评测稿。
- 读取四篇文章的正文。S/T 保存抓取文本；I/N 通过网页工具读取，原文直抓分别遇到访问拦截，未伪造本地全文快照，改存来源与内容定位笔记。
- 先完成 `runs/*/draft.md`，再对照原文审查，生成 `review.md` 与 `final.md`。没有人为植入错误；评测不要求初稿必须有缺陷。
- 没有发布任何内容，没有联系外部读者，也未测点击率、读完率或真实阅读时长。

## 阅读入口

| 编号 | 材料与输出 | 初稿 | 审稿 |
|---|---|---|---|
| S | [韦布望远镜科普：文章稿](runs/S/final.md) | [初稿](runs/S/draft.md) | [问题与修订](runs/S/review.md) |
| T | [HTTP 缓存技术说明：文章稿](runs/T/final.md) | [初稿](runs/T/draft.md) | [问题与修订](runs/T/review.md) |
| I | [Landsat 多人访谈：文章稿](runs/I/final.md) | [初稿](runs/I/draft.md) | [问题与修订](runs/I/review.md) |
| N | [《孔乙己》：通俗重构与解读](runs/N/final.md) | [初稿](runs/N/draft.md) | [问题与修订](runs/N/review.md) |
| X | [同一篇韦布报道：X 串帖](runs/X/final.md) | [初稿](runs/X/draft.md) | [问题与修订](runs/X/review.md) |

[结论与优化判断](results.md) · [来源及内容范围](sources.md) · [统计](metrics.json) · [后续执行校准](execution-calibration.md)

## 使用与来源

MDN 原文由 Mozilla Contributors 编写，依 [CC BY-SA 2.5 或后续版本](https://creativecommons.org/licenses/by-sa/2.5/) 提供；本轮 T 的重组、删减和通俗解释亦按相同许可提供，详见稿件署名。NASA/USGS 使用官方报道正文，不复用另有图片署名的素材；《孔乙己》为公有领域作品，保留鲁迅署名。原文年份不冒充本次评测日期，计划中能力不写成已实现。
