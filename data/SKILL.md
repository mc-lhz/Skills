---
name: data
description: doubao-data-analysis：结构化业务数据分析：附件读取与口径核验、定向筛选、规则/阈值判定、指标异动归因、漏斗/留存/实验分析、经营复盘及可审计报告。当用户提供 Excel、CSV、PDF、图片或多份业务材料，要求查数；doubao-visualization：当回答涉及趋势、占比、比较、流程、机制、因果、架构、关系、时间线、状态机、算法步骤、参数变化、原图证据，或用户明确要求图表、图解、标注、动态/交互演示时使用。优先用 ECharts。共 2 个子技能，按诉求分流；只涉及其中某一项时，只读取并执行对应的子技能，不加载其他子技能。
---

# 数据分析与可视化

本技能是 2 个子技能的集合入口。收到诉求后先按下表定位唯一匹配的子技能，再 `Read references/<子技能名>/SUBSKILL.md` 进入该子技能，按其内部的阶段/路由表继续执行。不要一次性通读全部子技能。

## 子技能索引

| 子技能 | 职责 |
|---|---|
| [`doubao-data-analysis`](references/doubao-data-analysis/SUBSKILL.md) | 结构化业务数据分析：附件读取与口径核验、定向筛选、规则/阈值判定、指标异动归因、漏斗/留存/实验分析、经营复盘及可审计报告。当用户提供 Excel、CSV、PDF、图片或多份业务材料，要求查数 |
| [`doubao-visualization`](references/doubao-visualization/SUBSKILL.md) | 当回答涉及趋势、占比、比较、流程、机制、因果、架构、关系、时间线、状态机、算法步骤、参数变化、原图证据，或用户明确要求图表、图解、标注、动态/交互演示时使用。优先用 ECharts |

<system-reminder>
本技能由若干子技能构成，每个子技能位于 `references/<子技能名>/`，且各自保留完整的
`SUBSKILL.md` 与 `references/`、`scripts/`、`assets/` 目录树。子技能内部的相对路径
一律以它自己所在的 `references/<子技能名>/` 为基准解析——读到 `scripts/x.py`、
`references/y.md` 时，实际指向 `references/<子技能名>/scripts/x.py`，
不要退回到本技能根目录查找，也不要再加一层 `references/` 前缀。

执行某一子技能的脚本时，须使用完整路径 `references/<子技能名>/scripts/...`；
子技能文档里写的 `python3 scripts/...` 是相对它自身目录的，不能照搬到本技能根下运行。
</system-reminder>
