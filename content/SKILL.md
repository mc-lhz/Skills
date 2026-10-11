---
name: content
description: doubao-book-writer：豆包办公里的非虚构长文档工作台。用于手册、白皮书、报告、培训材料、人物口述、家谱、资料型书稿等长文档的新建、续写、组装、改写、扩写、精修、去AI味、质检和交付。不用于小说、网文、剧本、诗歌；doubao-cross-border-growth-content：Evidence-grounded cross-border ecommerce content operations for short-video and livestream scripts,；doubao-headlines-calendar：跨平台内容生成、改写、评估和A/B测试标题，并结合账号定位、受众、产能和节点规划可执行的周度或月度内容选题日历。用于爆款标题、多平台标题适配、标题优化、标题拆解、A/B标题、周选题、月度排期；doubao-human-signal：去除或避免文本中的 AI 味。用于用户强制调用本 Skill，或写作/改写时提到“不要有 AI 味”“不要太假”“真情实感”“有人感”；doubao-multiplatform-rewrite：基于用户提供的已有素材（母稿、文章、新闻稿、活动稿、产品稿、报告摘要、访谈素材、口播稿、散乱素材等），改写成可发布的多平台分发版本，标准场景为≥2个平台，有素材的单平台改写也可支持，覆盖微信公众号；doubao-newmedia-writing：用于生成、改写、优化并默认以飞书文档/Lark Doc 交付中文新媒体内容，覆盖小红书图文笔记、微信公众号文章、3 分钟以内短视频分镜脚本，以及上述类型的复合创作方案；doubao-novel-writing：用于网文小说创作、改写、续写、诊断、卖点包装、市场调查和编辑视角分析。当用户需要写或优化开篇、第一章、前三章、章节正文、大纲、设定、人设、CP、情节桥段、简介、导语、投稿文，或要求分析相似网文。共 7 个子技能，按诉求分流；只涉及其中某一项时，只读取并执行对应的子技能，不加载其他子技能。
---

# 内容创作

本技能是 7 个子技能的集合入口。收到诉求后先按下表定位唯一匹配的子技能，再 `Read references/<子技能名>/SUBSKILL.md` 进入该子技能，按其内部的阶段/路由表继续执行。不要一次性通读全部子技能。

## 子技能索引

| 子技能 | 职责 |
|---|---|
| [`doubao-book-writer`](references/doubao-book-writer/SUBSKILL.md) | 豆包办公里的非虚构长文档工作台。用于手册、白皮书、报告、培训材料、人物口述、家谱、资料型书稿等长文档的新建、续写、组装、改写、扩写、精修、去AI味、质检和交付。不用于小说、网文、剧本、诗歌 |
| [`doubao-cross-border-growth-content`](references/doubao-cross-border-growth-content/SUBSKILL.md) | Evidence-grounded cross-border ecommerce content operations for short-video and livestream scripts, |
| [`doubao-headlines-calendar`](references/doubao-headlines-calendar/SUBSKILL.md) | 跨平台内容生成、改写、评估和A/B测试标题，并结合账号定位、受众、产能和节点规划可执行的周度或月度内容选题日历。用于爆款标题、多平台标题适配、标题优化、标题拆解、A/B标题、周选题、月度排期 |
| [`doubao-human-signal`](references/doubao-human-signal/SUBSKILL.md) | 去除或避免文本中的 AI 味。用于用户强制调用本 Skill，或写作/改写时提到“不要有 AI 味”“不要太假”“真情实感”“有人感” |
| [`doubao-multiplatform-rewrite`](references/doubao-multiplatform-rewrite/SUBSKILL.md) | 基于用户提供的已有素材（母稿、文章、新闻稿、活动稿、产品稿、报告摘要、访谈素材、口播稿、散乱素材等），改写成可发布的多平台分发版本，标准场景为≥2个平台，有素材的单平台改写也可支持，覆盖微信公众号 |
| [`doubao-newmedia-writing`](references/doubao-newmedia-writing/SUBSKILL.md) | 用于生成、改写、优化并默认以飞书文档/Lark Doc 交付中文新媒体内容，覆盖小红书图文笔记、微信公众号文章、3 分钟以内短视频分镜脚本，以及上述类型的复合创作方案 |
| [`doubao-novel-writing`](references/doubao-novel-writing/SUBSKILL.md) | 用于网文小说创作、改写、续写、诊断、卖点包装、市场调查和编辑视角分析。当用户需要写或优化开篇、第一章、前三章、章节正文、大纲、设定、人设、CP、情节桥段、简介、导语、投稿文，或要求分析相似网文 |

<system-reminder>
本技能由若干子技能构成，每个子技能位于 `references/<子技能名>/`，且各自保留完整的
`SUBSKILL.md` 与 `references/`、`scripts/`、`assets/` 目录树。子技能内部的相对路径
一律以它自己所在的 `references/<子技能名>/` 为基准解析——读到 `scripts/x.py`、
`references/y.md` 时，实际指向 `references/<子技能名>/scripts/x.py`，
不要退回到本技能根目录查找，也不要再加一层 `references/` 前缀。

执行某一子技能的脚本时，须使用完整路径 `references/<子技能名>/scripts/...`；
子技能文档里写的 `python3 scripts/...` 是相对它自身目录的，不能照搬到本技能根下运行。
</system-reminder>
