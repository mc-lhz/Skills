# Skills

106 个 Agent Skill，按功能分为 15 个目录。多数源自豆包（ByteDance）办公环境导出。

## 结构

| 目录 | 数量 | 说明 |
|---|---|---|
| `lark/` | 20 | 飞书协作，依赖 [`larksuite/cli`](https://github.com/larksuite/cli)（`lark-cli`） |
| `platform-doubao/` | 15 | 豆包宿主专用，**在豆包外无法运行**（见下） |
| `finance/` | 11 | 金融投资与财报分析 |
| `marketing/` | 9 | 营销、电商运营、舆情 |
| `academic/` | 7 | 论文写作、文献调研、投稿审查 |
| `content/` | 7 | 长文档、小说、新媒体、多平台改写 |
| `medical/` | 7 | 医学循证、文献检索与解读 |
| `legal/` | 7 | 合同、专利、DPA、合规审计 |
| `media/` | 7 | 图像/视频/音频生成与视频提取 |
| `product/` | 5 | PRD、竞品分析、QA、用户研究、游戏策划 |
| `tooling/` | 4 | 产物预览校验、Skill 创建、PC 优化 |
| `data/` | 2 | 业务数据分析、可视化 |
| `documents/` | 2 | PDF 处理、期刊排版 |
| `web-dev/` | 2 | 单页 HTML、全栈应用开发 |
| `lifestyle/` | 1 | 旅游/健身/美食/游戏攻略路由 |

合计 106 个技能目录、133 个 `SKILL.md`（含各技能内部 `references/`、`sub-skills/`），约 33 MB。

## 运行依赖

**通用（约 40 个）** — 只需 Python 3.10+ 与常规 pip 包（`python-docx`、`openpyxl`、`lxml`、`Pillow`、`PyMuPDF`）。

**需 `lark-cli`（`lark/` 全部 20 个）** — 公开 MIT 项目，`npx @larksuite/cli@latest install` 或直接下载 Releases 的预编译二进制（Go 实现，运行期不需要 Node）。其中 `lark-whiteboard` 额外依赖纯 Node 的 `@larksuite/whiteboard-cli`。

**豆包环境专用（`platform-doubao/` 全部 15 个）** — 依赖宿主注入的私有工具，无法在外部复现：

| 依赖 | 涉及技能 |
|---|---|
| `mediakit-cli`（字节内部，npm 未发布） | `byted-mediakit-*` × 5 |
| `computer_use_tool` / bu plane | `browser-use-automation` × 2、`browser-task` |
| 豆包内置工具 | `doubao-enterprise-search` `cron-scheduler` `record` `identity`、`gift-card-redemption`、`student-discount-application`、`doubao-oceanengine-adops-agent` |

`ppt` 另可选调用 `mediakit-cli` 做图片去背景（效率优先时可降级用原图）。

## 使用

这些是标准 Skill 目录，把仓库路径加入宿主的 skill 搜索路径即可，例如 opencode：

```json
{ "skills": { "paths": ["C:\\path\\to\\Skills"] } }
```

Skill 由 `SKILL.md` frontmatter 的 `name` + `description` 触发，宿主仅扫 `**/SKILL.md`。

## 已知缺失

`tooling/artifact-preview/` 只有 `bin/` 与 `lib/`（代码部分），其顶层 `SKILL.md`、`README.md`、`requirements.txt` 在上游导出包中即已缺失，未能恢复。因此该目录不构成可被宿主加载的完整 Skill。

## 许可

**未统一授权，推送公开仓库前需先确认。** 现状：

- 5 个 `byted-mediakit-*` 声明 MIT
- 2 个声明 **Proprietary — internal use only**：`tooling/artifact-preview`、`tooling/verifier-hub`
- 其余 99 个未声明 license

技能由第三方环境导出，多数未附授权条款，默认视为保留全部权利。若本仓库为公开仓库，建议移除这两个 Proprietary 技能，或取得来源方书面许可。