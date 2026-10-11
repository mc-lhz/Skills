---
name: medical
description: doubao-answer-with-medical-evidence：健康问题循证咨询，患者或家属提出健康或医学问题时使用，患者提问优先使用本技能，适用于需要围绕相关症状、疾病、检查、用药、治疗或预后问题，结合医学文献进行回答的场景；doubao-clinical-decision-support：循证医学临床辅助决策 Skill。用户需要分析临床问题，解释临床表现，提供循证医学判断时使用，用于针对临床问题，结合病例资料，查阅指南和文献等循证依据，进行科学回答与诊疗决策，进行诊断鉴别、检查路径；doubao-medical-literature-interpretation：医学文献解读 Skill。用户上传或提供医学论文、指南等资料的片段、网页链接、DOI、aka 文件链接、PDF、表格或图片，并要求解读、总结、分析、问答或对比时使用；先阅读内容并判断是否属于医学文献；doubao-medical-literature-monitoring：医学进展跟踪 Skill。用于医生、研究人员或医学内容团队对相关领域最新进展的跟踪和调研需求，当用户提出“查询最新进展、订阅监控进展更新、定期更新推送”等需求时，可以调用该技能跟踪相关医学主题的研究；doubao-medical-literature-search：医学文献检索分析 Skill。用户需要查找临床指南、论文研究，或要求检索主流医学数据库时使用，满足文献检索、领域综述、选题分析、考试学习、方法调研等医学文献场景需求。用于查找指南、共识和研究；doubao-medical-literature-translation：医学文献翻译 Skill，面向医学领域文献资料翻译。用于英译中或中译英，覆盖论文、摘要、指南、临床试验、药品资料等医学文献的翻译需求；支持文本片段、指定章节、网页、PDF、飞书文件、文章全文的翻译；doubao-medical-report：必须在用户需要医学报告解读时使用。包括：用户上传体检报告、检验报告、检查单、化验单、血常规/尿常规/生化/肝肾功能/血脂血糖等检验检查图片、照片、截图、PDF、文档、表格或文件。共 7 个子技能，按诉求分流；只涉及其中某一项时，只读取并执行对应的子技能，不加载其他子技能。
---

# 医学循证

本技能是 7 个子技能的集合入口。收到诉求后先按下表定位唯一匹配的子技能，再 `Read references/<子技能名>/SUBSKILL.md` 进入该子技能，按其内部的阶段/路由表继续执行。不要一次性通读全部子技能。

## 子技能索引

| 子技能 | 职责 |
|---|---|
| [`doubao-answer-with-medical-evidence`](references/doubao-answer-with-medical-evidence/SUBSKILL.md) | 健康问题循证咨询，患者或家属提出健康或医学问题时使用，患者提问优先使用本技能，适用于需要围绕相关症状、疾病、检查、用药、治疗或预后问题，结合医学文献进行回答的场景 |
| [`doubao-clinical-decision-support`](references/doubao-clinical-decision-support/SUBSKILL.md) | 循证医学临床辅助决策 Skill。用户需要分析临床问题，解释临床表现，提供循证医学判断时使用，用于针对临床问题，结合病例资料，查阅指南和文献等循证依据，进行科学回答与诊疗决策，进行诊断鉴别、检查路径 |
| [`doubao-medical-literature-interpretation`](references/doubao-medical-literature-interpretation/SUBSKILL.md) | 医学文献解读 Skill。用户上传或提供医学论文、指南等资料的片段、网页链接、DOI、aka 文件链接、PDF、表格或图片，并要求解读、总结、分析、问答或对比时使用；先阅读内容并判断是否属于医学文献 |
| [`doubao-medical-literature-monitoring`](references/doubao-medical-literature-monitoring/SUBSKILL.md) | 医学进展跟踪 Skill。用于医生、研究人员或医学内容团队对相关领域最新进展的跟踪和调研需求，当用户提出“查询最新进展、订阅监控进展更新、定期更新推送”等需求时，可以调用该技能跟踪相关医学主题的研究 |
| [`doubao-medical-literature-search`](references/doubao-medical-literature-search/SUBSKILL.md) | 医学文献检索分析 Skill。用户需要查找临床指南、论文研究，或要求检索主流医学数据库时使用，满足文献检索、领域综述、选题分析、考试学习、方法调研等医学文献场景需求。用于查找指南、共识和研究 |
| [`doubao-medical-literature-translation`](references/doubao-medical-literature-translation/SUBSKILL.md) | 医学文献翻译 Skill，面向医学领域文献资料翻译。用于英译中或中译英，覆盖论文、摘要、指南、临床试验、药品资料等医学文献的翻译需求；支持文本片段、指定章节、网页、PDF、飞书文件、文章全文的翻译 |
| [`doubao-medical-report`](references/doubao-medical-report/SUBSKILL.md) | 必须在用户需要医学报告解读时使用。包括：用户上传体检报告、检验报告、检查单、化验单、血常规/尿常规/生化/肝肾功能/血脂血糖等检验检查图片、照片、截图、PDF、文档、表格或文件 |

<system-reminder>
本技能由若干子技能构成，每个子技能位于 `references/<子技能名>/`，且各自保留完整的
`SUBSKILL.md` 与 `references/`、`scripts/`、`assets/` 目录树。子技能内部的相对路径
一律以它自己所在的 `references/<子技能名>/` 为基准解析——读到 `scripts/x.py`、
`references/y.md` 时，实际指向 `references/<子技能名>/scripts/x.py`，
不要退回到本技能根目录查找，也不要再加一层 `references/` 前缀。

执行某一子技能的脚本时，须使用完整路径 `references/<子技能名>/scripts/...`；
子技能文档里写的 `python3 scripts/...` 是相对它自身目录的，不能照搬到本技能根下运行。
</system-reminder>
