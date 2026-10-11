---
name: legal
description: doubao-compliance-assessment-public：基于公开法律来源开展交互式合规评估并生成可审阅报告。用户要求评估业务法律风险、审阅 PRD、判断监管红线或生成合规报告时使用；doubao-contract-amendment：用于在已签原协议基础上，依据用户提供的新情况起草补充协议、变更协议或终止协议。先重建主体、标的、资金、条件、时间和文件构成的整体法律状态，再在用户明确授权范围内成文。仅处理既有协议的派生修改；doubao-contract-drafting：直接起草中国大陆商业合同并生成无批注、无颜色、中文字体正确的可编辑 Word 文件。适用于采购、服务、营销、工程施工、软件许可、SaaS、委托开发、联合研发、知识产权、租赁、数据处理和保密等场景；doubao-contract-reviewer：doubao-contract-reviewer 是面向大众用户的合同审查 Skill，适合在豆包/豆包 Turbo 中审查各类合同。用户上传合同或询问“帮我审合同、合同有没有问题、这份合同能不能签；doubao-dpa-drafter：DPA数据处理协议专业起草；当用户需要起草数据处理协议、DPA协议、数据委托处理协议、数据共同处理协议或数据对外提供协议时使用。仅做数据合规类协议起草，通用商务合同或非数据类合同请改用对应 skill；doubao-patent-drafting：用户要求基于技术交底书撰写或修改中国发明、实用新型专利申请文件，或者审查已有权利要求书时使用。典型触发包括“专利撰写”“专利申请”“技术交底书”“权利要求”“说明书”“实用新型”“发明专利”。共 6 个子技能，按诉求分流；只涉及其中某一项时，只读取并执行对应的子技能，不加载其他子技能。
---

# 法律文书

本技能是 6 个子技能的集合入口。收到诉求后先按下表定位唯一匹配的子技能，再 `Read references/<子技能名>/SUBSKILL.md` 进入该子技能，按其内部的阶段/路由表继续执行。不要一次性通读全部子技能。

## 子技能索引

| 子技能 | 职责 |
|---|---|
| [`doubao-compliance-assessment-public`](references/doubao-compliance-assessment-public/SUBSKILL.md) | 基于公开法律来源开展交互式合规评估并生成可审阅报告。用户要求评估业务法律风险、审阅 PRD、判断监管红线或生成合规报告时使用 |
| [`doubao-contract-amendment`](references/doubao-contract-amendment/SUBSKILL.md) | 用于在已签原协议基础上，依据用户提供的新情况起草补充协议、变更协议或终止协议。先重建主体、标的、资金、条件、时间和文件构成的整体法律状态，再在用户明确授权范围内成文。仅处理既有协议的派生修改 |
| [`doubao-contract-drafting`](references/doubao-contract-drafting/SUBSKILL.md) | 直接起草中国大陆商业合同并生成无批注、无颜色、中文字体正确的可编辑 Word 文件。适用于采购、服务、营销、工程施工、软件许可、SaaS、委托开发、联合研发、知识产权、租赁、数据处理和保密等场景 |
| [`doubao-contract-reviewer`](references/doubao-contract-reviewer/SUBSKILL.md) | doubao-contract-reviewer 是面向大众用户的合同审查 Skill，适合在豆包/豆包 Turbo 中审查各类合同。用户上传合同或询问“帮我审合同、合同有没有问题、这份合同能不能签 |
| [`doubao-dpa-drafter`](references/doubao-dpa-drafter/SUBSKILL.md) | DPA数据处理协议专业起草；当用户需要起草数据处理协议、DPA协议、数据委托处理协议、数据共同处理协议或数据对外提供协议时使用。仅做数据合规类协议起草，通用商务合同或非数据类合同请改用对应 skill |
| [`doubao-patent-drafting`](references/doubao-patent-drafting/SUBSKILL.md) | 用户要求基于技术交底书撰写或修改中国发明、实用新型专利申请文件，或者审查已有权利要求书时使用。典型触发包括“专利撰写”“专利申请”“技术交底书”“权利要求”“说明书”“实用新型”“发明专利” |

<system-reminder>
本技能由若干子技能构成，每个子技能位于 `references/<子技能名>/`，且各自保留完整的
`SUBSKILL.md` 与 `references/`、`scripts/`、`assets/` 目录树。子技能内部的相对路径
一律以它自己所在的 `references/<子技能名>/` 为基准解析——读到 `scripts/x.py`、
`references/y.md` 时，实际指向 `references/<子技能名>/scripts/x.py`，
不要退回到本技能根目录查找，也不要再加一层 `references/` 前缀。

执行某一子技能的脚本时，须使用完整路径 `references/<子技能名>/scripts/...`；
子技能文档里写的 `python3 scripts/...` 是相对它自身目录的，不能照搬到本技能根下运行。
</system-reminder>
