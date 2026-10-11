---
name: product
description: doubao-game-designer：把游戏创意、参考作品、现有方案、配置或试玩证据转化为玩法成立、规则闭合、数值可复算且能进入制作的 GDD、玩法方案与系统规格；需要验证关键玩法时；doubao-product-analysis：围绕具体产品、产品想法或存量方案，产出用于产品进入、定位、竞争策略、上市路径、能力建设与路线图决策的证据型分析报告；doubao-product-manager：将产品想法、用户反馈、研究数据、云文档、附件和已有方案转化为有依据的产品判断、策略、MVP、优先级、Roadmap、PRD、用户故事、验收标准或方案评审。任务涉及产品决策、需求取舍、存量产品修改；doubao-product-qa：将 PRD、原型、网页、接口、代码、测试记录和多轮上下文转成可追踪的 QA 基线、风险用例、执行证据、Bug 与发布判断。适用于 Web/API/App/小程序测试、回归、热修复、测试方案；doubao-questionnaire-designer：用户研究一站式助手,覆盖四大能力:①问卷设计(按调研目标产出可落地问卷,含试填优化,交付 Word/飞书文档);②访谈提纲(题量按诉求动态确定。共 5 个子技能，按诉求分流；只涉及其中某一项时，只读取并执行对应的子技能，不加载其他子技能。
---

# 产品与用户研究

本技能是 5 个子技能的集合入口。收到诉求后先按下表定位唯一匹配的子技能，再 `Read references/<子技能名>/SUBSKILL.md` 进入该子技能，按其内部的阶段/路由表继续执行。不要一次性通读全部子技能。

## 子技能索引

| 子技能 | 职责 |
|---|---|
| [`doubao-game-designer`](references/doubao-game-designer/SUBSKILL.md) | 把游戏创意、参考作品、现有方案、配置或试玩证据转化为玩法成立、规则闭合、数值可复算且能进入制作的 GDD、玩法方案与系统规格；需要验证关键玩法时 |
| [`doubao-product-analysis`](references/doubao-product-analysis/SUBSKILL.md) | 围绕具体产品、产品想法或存量方案，产出用于产品进入、定位、竞争策略、上市路径、能力建设与路线图决策的证据型分析报告 |
| [`doubao-product-manager`](references/doubao-product-manager/SUBSKILL.md) | 将产品想法、用户反馈、研究数据、云文档、附件和已有方案转化为有依据的产品判断、策略、MVP、优先级、Roadmap、PRD、用户故事、验收标准或方案评审。任务涉及产品决策、需求取舍、存量产品修改 |
| [`doubao-product-qa`](references/doubao-product-qa/SUBSKILL.md) | 将 PRD、原型、网页、接口、代码、测试记录和多轮上下文转成可追踪的 QA 基线、风险用例、执行证据、Bug 与发布判断。适用于 Web/API/App/小程序测试、回归、热修复、测试方案 |
| [`doubao-questionnaire-designer`](references/doubao-questionnaire-designer/SUBSKILL.md) | 用户研究一站式助手,覆盖四大能力:①问卷设计(按调研目标产出可落地问卷,含试填优化,交付 Word/飞书文档);②访谈提纲(题量按诉求动态确定 |

<system-reminder>
本技能由若干子技能构成，每个子技能位于 `references/<子技能名>/`，且各自保留完整的
`SUBSKILL.md` 与 `references/`、`scripts/`、`assets/` 目录树。子技能内部的相对路径
一律以它自己所在的 `references/<子技能名>/` 为基准解析——读到 `scripts/x.py`、
`references/y.md` 时，实际指向 `references/<子技能名>/scripts/x.py`，
不要退回到本技能根目录查找，也不要再加一层 `references/` 前缀。

执行某一子技能的脚本时，须使用完整路径 `references/<子技能名>/scripts/...`；
子技能文档里写的 `python3 scripts/...` 是相对它自身目录的，不能照搬到本技能根下运行。
</system-reminder>
