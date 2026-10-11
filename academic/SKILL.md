---
name: academic
description: doubao-academic-evaluator：用资深审稿人和导师的眼光，对科研工作做"只看不改"的诊断。两类任务：一是评判研究想法值不值得做（打分、查新颖性、判可行性）；二是论文评审，给文章成稿挑硬伤、判断能不能投。只负责找问题、下结论；doubao-academic-polish：学术论文正文写作、结构设计与语言润色总入口。完整起草、续写、扩写、补写或实质性修订各学科的中英文论文正文时，进入paper-write-zh或paper-write-en；只做提纲；doubao-academic-researcher：通用学术文献调研Skill，面向研究者、学生和论文写作者在未锁定具体论文题目前摸清某学术方向、概念、机制、热点前沿、学术史或选题依据。执行系统检索、引用真实性核验、证据分级、主题聚类、交叉综合；doubao-critical-reading-companion：深度解读文章，把新闻、长评或宣传文案等非学术公共文本转成便于理解、可追溯的阅读地图；用于重建论证链、评价证据与推理、识别隐藏前提、补充替代解释、核查关键事实，并输出可追溯的阅读地图。适用于可信度判断；doubao-paper-close-reading：用于用户提供一篇或少量学术论文后，进行专业深度精读，讲清研究问题、研究故事、方法或理论机制、关键证据、实验结果、可信边界、复现风险与研究启示，并生成高级 Markdown 报告和飞书文档；doubao-reference-audit：用于用户提交论文、学位论文或参考文献清单后，系统审查参考文献真实性、题录准确性、文内—文后对应关系以及正文主张是否得到被引文献支持，并生成专业、清晰、可直接指导修改的论文引用审计报告与飞书文档；doubao-research-proposal：用于国自然、国社科等基金申请、开题报告、博士后/人才计划、研究计划书等学术提案的撰写、审查和优化；当用户需要基于已有研究成果形成立项书、区分事实与 AI 建议、检查任务书一致性、补强论证逻辑时使用。共 7 个子技能，按诉求分流；只涉及其中某一项时，只读取并执行对应的子技能，不加载其他子技能。
---

# 学术研究

本技能是 7 个子技能的集合入口。收到诉求后先按下表定位唯一匹配的子技能，再 `Read references/<子技能名>/SUBSKILL.md` 进入该子技能，按其内部的阶段/路由表继续执行。不要一次性通读全部子技能。

## 子技能索引

| 子技能 | 职责 |
|---|---|
| [`doubao-academic-evaluator`](references/doubao-academic-evaluator/SUBSKILL.md) | 用资深审稿人和导师的眼光，对科研工作做"只看不改"的诊断。两类任务：一是评判研究想法值不值得做（打分、查新颖性、判可行性）；二是论文评审，给文章成稿挑硬伤、判断能不能投。只负责找问题、下结论 |
| [`doubao-academic-polish`](references/doubao-academic-polish/SUBSKILL.md) | 学术论文正文写作、结构设计与语言润色总入口。完整起草、续写、扩写、补写或实质性修订各学科的中英文论文正文时，进入paper-write-zh或paper-write-en；只做提纲 |
| [`doubao-academic-researcher`](references/doubao-academic-researcher/SUBSKILL.md) | 通用学术文献调研Skill，面向研究者、学生和论文写作者在未锁定具体论文题目前摸清某学术方向、概念、机制、热点前沿、学术史或选题依据。执行系统检索、引用真实性核验、证据分级、主题聚类、交叉综合 |
| [`doubao-critical-reading-companion`](references/doubao-critical-reading-companion/SUBSKILL.md) | 深度解读文章，把新闻、长评或宣传文案等非学术公共文本转成便于理解、可追溯的阅读地图；用于重建论证链、评价证据与推理、识别隐藏前提、补充替代解释、核查关键事实，并输出可追溯的阅读地图。适用于可信度判断 |
| [`doubao-paper-close-reading`](references/doubao-paper-close-reading/SUBSKILL.md) | 用于用户提供一篇或少量学术论文后，进行专业深度精读，讲清研究问题、研究故事、方法或理论机制、关键证据、实验结果、可信边界、复现风险与研究启示，并生成高级 Markdown 报告和飞书文档 |
| [`doubao-reference-audit`](references/doubao-reference-audit/SUBSKILL.md) | 用于用户提交论文、学位论文或参考文献清单后，系统审查参考文献真实性、题录准确性、文内—文后对应关系以及正文主张是否得到被引文献支持，并生成专业、清晰、可直接指导修改的论文引用审计报告与飞书文档 |
| [`doubao-research-proposal`](references/doubao-research-proposal/SUBSKILL.md) | 用于国自然、国社科等基金申请、开题报告、博士后/人才计划、研究计划书等学术提案的撰写、审查和优化；当用户需要基于已有研究成果形成立项书、区分事实与 AI 建议、检查任务书一致性、补强论证逻辑时使用 |

<system-reminder>
本技能由若干子技能构成，每个子技能位于 `references/<子技能名>/`，且各自保留完整的
`SUBSKILL.md` 与 `references/`、`scripts/`、`assets/` 目录树。子技能内部的相对路径
一律以它自己所在的 `references/<子技能名>/` 为基准解析——读到 `scripts/x.py`、
`references/y.md` 时，实际指向 `references/<子技能名>/scripts/x.py`，
不要退回到本技能根目录查找，也不要再加一层 `references/` 前缀。

执行某一子技能的脚本时，须使用完整路径 `references/<子技能名>/scripts/...`；
子技能文档里写的 `python3 scripts/...` 是相对它自身目录的，不能照搬到本技能根下运行。
</system-reminder>
