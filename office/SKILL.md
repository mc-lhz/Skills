---
name: office
description: pdf：用于处理所有 PDF 相关任务，包括读取、创建、编辑、转换、内容提取、页面处理、表单填写、扫描件解析、PDF转化word文件和PDF转化飞书云文档。用户提供、提及或要求生成 PDF 时使用；doubao-journal-format：用于对学术论文类 Word/DOCX 文档进行期刊、学校、会议或课程要求的格式排版与修复。当用户需要把论文原稿套用.docx 模板或明确格式规则、或提到论文排版、期刊投稿格式、学位论文格式、会议论文模板、时使用；如果同一请求同时包含论文 Word 排版和任何非排版任务，必须先停止并询问用户选择“只做格式排版”还是“作为复合任务拆分处理”，在用户明确选择前不得执行排版。不用于论文写作、润色、降重、翻译、代写、文献检索、补引用、验证引用、伪造数据/引用，或普通非论文 Word 文档套模板；html：专门设计、生成和修改可直接在浏览器中打开的 HTML 页面或已发布的 doubao-html 链接。交付物以独立 .html 文件为主，可包含内联或本地 CSS、JavaScript，支持页面布局、视觉样式、交互效果、响应式适配、组件设计和内容展示。适用于静态网页、单页展示、活动页、原型页、HTML 模板及页面片段。不处理前后端工程、应用框架、服务端接口、数据库、用户系统、构建部署或运营数据；verifier-hub：Deterministic artifact verifier CLI (file/xlsx/docx/pdf/pptx/text/archive/rubric) for pre-delivery artifact checks and agentic judges. 58 subcommands callable as `verifier {family} {subcmd} [args]`. Use before delivering or uploading a file, or whenever you need to check file format, sheet/section presence, cell values, formulas, keywords, character counts, page counts, placeholders, signatures or zip contents, instead of guessing from an LLM reading. Every call prints one JSON object with a quotable `evidence` field.；skill-creator-for-work：创建有效 Skill 的指南。当用户想要创建新的 Skill，或更新现有 Skill，以便通过专门知识、工作流程或工具集成来扩展 AI Agent 能力时，应使用此 Skill。共 5 个子技能，按诉求分流；只涉及其中某一项时，只读取并执行对应的子技能，不加载其他子技能。
---

# 办公

本技能是 5 个子技能的集合入口。收到诉求后先按下表定位唯一匹配的子技能，再 `Read references/<子技能名>/SUBSKILL.md` 进入该子技能，按其内部的阶段/路由表继续执行。不要一次性通读全部子技能。

## 子技能索引

| 子技能 | 职责 |
|---|---|
| [`pdf`](references/pdf/SUBSKILL.md) | 用于处理所有 PDF 相关任务，包括读取、创建、编辑、转换、内容提取、页面处理、表单填写、扫描件解析、PDF转化word文件和PDF转化飞书云文档。用户提供、提及或要求生成 PDF 时使用 |
| [`doubao-journal-format`](references/doubao-journal-format/SUBSKILL.md) | 用于对学术论文类 Word/DOCX 文档进行期刊、学校、会议或课程要求的格式排版与修复。当用户需要把论文原稿套用.docx 模板或明确格式规则、或提到论文排版、期刊投稿格式、学位论文格式、会议论文模板、时使用 |
| [`html`](references/html/SUBSKILL.md) | 专门设计、生成和修改可直接在浏览器中打开的 HTML 页面或已发布的 doubao-html 链接。交付物以独立 .html 文件为主，可包含内联或本地 CSS、JavaScript，支持页面布局、视觉样式、交互效果、响应式适配、组件设计和内容展示 |
| [`verifier-hub`](references/verifier-hub/SUBSKILL.md) | Deterministic artifact verifier CLI (file/xlsx/docx/pdf/pptx/text/archive/rubric) for pre-delivery artifact checks and agentic judges. 58 subcommands callable as `verifier {family} {subcmd} [args]`. Use before delivering or uploading a file, or whenever you need to check file format, sheet/section presence, cell values, formulas, keywords, character counts, page counts, placeholders, signatures or zip contents, instead of guessing from an LLM reading |
| [`skill-creator-for-work`](references/skill-creator-for-work/SUBSKILL.md) | 创建有效 Skill 的指南。当用户想要创建新的 Skill，或更新现有 Skill，以便通过专门知识、工作流程或工具集成来扩展 AI Agent 能力时，应使用此 Skill |

<system-reminder>
本技能由若干子技能构成，每个子技能位于 `references/<子技能名>/`，且各自保留完整的
`SUBSKILL.md` 与 `references/`、`scripts/`、`assets/` 目录树。子技能内部的相对路径
一律以它自己所在的 `references/<子技能名>/` 为基准解析——读到 `scripts/x.py`、
`references/y.md` 时，实际指向 `references/<子技能名>/scripts/x.py`，
不要退回到本技能根目录查找，也不要再加一层 `references/` 前缀。

执行某一子技能的脚本时，须使用完整路径 `references/<子技能名>/scripts/...`；
子技能文档里写的 `python3 scripts/...` 是相对它自身目录的，不能照搬到本技能根下运行。
</system-reminder>
