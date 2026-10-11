---
name: finance
description: doubao-announcement-analysis：搜索并解读上市公司公告，覆盖 A股（沪深北）、港股（HKEX）、美股（SEC EDGAR）三大市场。支持两种模式：①单条/多条具体公告的深度解读（拆解公告要点、判断重要性、给出多视角分析）；doubao-daily-stock：用于单一上市股票的个股日报，解释涨跌和异动原因，梳理行情、资金流、新闻公告、板块联动、技术面、预期与风险。适用于“某股今天为什么涨跌”“做个日报”“近期表现”“资金面和消息面”等问题；doubao-earnings-analysis：|
  上市公司财报/季报/年报/业绩的深度因果分析，覆盖A股、港股、美股和中概股。用于解读财报表现、亮点/风险、收入利润等指标变动、超预期或低于预期原因，以及针对毛利率、现金流；doubao-industry-analysis：针对某一行业（半导体、新能源、医药、消费等）的中长期基本面与产业研究，覆盖行业定义与规模、产业链与竞争格局、政策与驱动力、景气周期、趋势研判与三情景、盈利质量与落地建议；doubao-market-hotspot：把宏观、政策、监管、供需、地缘、行业或公司事件转化为公司、行业与公开市场的因果影响分析，覆盖事件状态、基线、传导渠道、财务与估值影响、直接及高阶影响、priced-in判断、情景、监控与证伪；doubao-private-company：评估一级市场、私募股权或创业项目的初步投资价值，基于BP、Deck、财务和访谈资料输出Screening Report、投资逻辑、红旗、情景、尽调缺口和初步建议。用于项目初筛；doubao-public-company-analysis：分析上市公司的商业模式、竞争优势、行业位置、财务质量、估值、风险与投资观点。用于用户要求公司基本面研究、公司深度分析、投资研究或提供公司名称/代码与关注点时。不要用于纯事件影响、批量选股；doubao-stock-screening：用于 A 股、港股、美股及其他股票市场的股票筛选、候选股构建、指定股票比较、行业筛选、主题概念筛选、产业链环节筛选、策略风格筛选和龙头识别。适用于用户要求找股票、筛股票池、比较指定股票；doubao-wealth-planning：为个人或家庭构建目标导向的财富规划，覆盖现金流、应急资金、债务、保障、教育/养老等目标、资产配置、情景压力测试与行动清单。用于新规划、年度复盘或重大人生变化。必须先确认司法辖区和风险承受能力；multi-stock-comparison：对两家及以上上市公司或股票进行横向研究，覆盖大盘与板块、外围市场、供应链、重要新闻与监管、商业模式、经营财务、成长、预期、估值、股价、组合以及 A/H 股与跨上市地相对价值。适用于公司比较、选股。共 10 个子技能，按诉求分流；只涉及其中某一项时，只读取并执行对应的子技能，不加载其他子技能。
---

# 金融研究

本技能是 10 个子技能的集合入口。收到诉求后先按下表定位唯一匹配的子技能，再 `Read references/<子技能名>/SUBSKILL.md` 进入该子技能，按其内部的阶段/路由表继续执行。不要一次性通读全部子技能。

## 子技能索引

| 子技能 | 职责 |
|---|---|
| [`doubao-announcement-analysis`](references/doubao-announcement-analysis/SUBSKILL.md) | 搜索并解读上市公司公告，覆盖 A股（沪深北）、港股（HKEX）、美股（SEC EDGAR）三大市场。支持两种模式：①单条/多条具体公告的深度解读（拆解公告要点、判断重要性、给出多视角分析） |
| [`doubao-daily-stock`](references/doubao-daily-stock/SUBSKILL.md) | 用于单一上市股票的个股日报，解释涨跌和异动原因，梳理行情、资金流、新闻公告、板块联动、技术面、预期与风险。适用于“某股今天为什么涨跌”“做个日报”“近期表现”“资金面和消息面”等问题 |
| [`doubao-earnings-analysis`](references/doubao-earnings-analysis/SUBSKILL.md) | |
  上市公司财报/季报/年报/业绩的深度因果分析，覆盖A股、港股、美股和中概股。用于解读财报表现、亮点/风险、收入利润等指标变动、超预期或低于预期原因，以及针对毛利率、现金流 |
| [`doubao-industry-analysis`](references/doubao-industry-analysis/SUBSKILL.md) | 针对某一行业（半导体、新能源、医药、消费等）的中长期基本面与产业研究，覆盖行业定义与规模、产业链与竞争格局、政策与驱动力、景气周期、趋势研判与三情景、盈利质量与落地建议 |
| [`doubao-market-hotspot`](references/doubao-market-hotspot/SUBSKILL.md) | 把宏观、政策、监管、供需、地缘、行业或公司事件转化为公司、行业与公开市场的因果影响分析，覆盖事件状态、基线、传导渠道、财务与估值影响、直接及高阶影响、priced-in判断、情景、监控与证伪 |
| [`doubao-private-company`](references/doubao-private-company/SUBSKILL.md) | 评估一级市场、私募股权或创业项目的初步投资价值，基于BP、Deck、财务和访谈资料输出Screening Report、投资逻辑、红旗、情景、尽调缺口和初步建议。用于项目初筛 |
| [`doubao-public-company-analysis`](references/doubao-public-company-analysis/SUBSKILL.md) | 分析上市公司的商业模式、竞争优势、行业位置、财务质量、估值、风险与投资观点。用于用户要求公司基本面研究、公司深度分析、投资研究或提供公司名称/代码与关注点时。不要用于纯事件影响、批量选股 |
| [`doubao-stock-screening`](references/doubao-stock-screening/SUBSKILL.md) | 用于 A 股、港股、美股及其他股票市场的股票筛选、候选股构建、指定股票比较、行业筛选、主题概念筛选、产业链环节筛选、策略风格筛选和龙头识别。适用于用户要求找股票、筛股票池、比较指定股票 |
| [`doubao-wealth-planning`](references/doubao-wealth-planning/SUBSKILL.md) | 为个人或家庭构建目标导向的财富规划，覆盖现金流、应急资金、债务、保障、教育/养老等目标、资产配置、情景压力测试与行动清单。用于新规划、年度复盘或重大人生变化。必须先确认司法辖区和风险承受能力 |
| [`multi-stock-comparison`](references/multi-stock-comparison/SUBSKILL.md) | 对两家及以上上市公司或股票进行横向研究，覆盖大盘与板块、外围市场、供应链、重要新闻与监管、商业模式、经营财务、成长、预期、估值、股价、组合以及 A/H 股与跨上市地相对价值。适用于公司比较、选股 |

<system-reminder>
本技能由若干子技能构成，每个子技能位于 `references/<子技能名>/`，且各自保留完整的
`SUBSKILL.md` 与 `references/`、`scripts/`、`assets/` 目录树。子技能内部的相对路径
一律以它自己所在的 `references/<子技能名>/` 为基准解析——读到 `scripts/x.py`、
`references/y.md` 时，实际指向 `references/<子技能名>/scripts/x.py`，
不要退回到本技能根目录查找，也不要再加一层 `references/` 前缀。

执行某一子技能的脚本时，须使用完整路径 `references/<子技能名>/scripts/...`；
子技能文档里写的 `python3 scripts/...` 是相对它自身目录的，不能照搬到本技能根下运行。
</system-reminder>
