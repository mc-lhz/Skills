# Skills

Agent Skill 集合。多数源自豆包（ByteDance）办公环境导出，按功能分域组织。

**当前 56 个可加载技能**（`SKILL.md`），其中 10 个是把子技能合并后的域根技能。

## 合并后的域根技能（10 个）

每个域根 `SKILL.md` 只写子技能索引与路径基准，子技能整体下沉到 `references/<子技能名>/`，
入口文件为 `SUBSKILL.md`。这样宿主不会把子技能重复加载为独立技能。

| 域根 | 子技能数 | 领域 |
|---|---|---|
| `academic/` | 7 | 论文写作、文献调研、评审、精读、参考文献、基金提案、批判阅读 |
| `content/` | 7 | 长文档、小说、新媒体、多平台改写、标题日历、去 AI 味、跨境内容 |
| `finance/` | 10 | 上市公司/非上市公司分析、选股、日报、财报、公告、行业、热点、财富规划、多股对比 |
| `legal/` | 6 | 合同起草/审查/修订、DPA、专利、合规评估 |
| `marketing/` | 9 | 营销策划、电商提案、商品内容、选品、客服、舆情、Listing、跨境合规、素材审核 |
| `medical/` | 7 | 患者咨询、临床决策、文献检索/解读/翻译/跟踪、报告解读 |
| `office/` | 5 | PDF 处理、论文 DOCX 排版、单页 HTML、产物校验 CLI、Skill 创建 |
| `product/` | 5 | 产品经理、产品分析、QA、用户研究、游戏策划 |
| `data/` | 2 | 业务数据分析、可视化 |
| `lifestyle/doubao-ultimate-guide/` | 4 | 旅游攻略、健身攻略、美食烹饪、游戏攻略（四合一总控） |

第三轮把 `lifestyle/doubao-ultimate-guide` 原先留在 `branches/` 的 4 个分支收敛到
`references/<分支名>/` 并改名为 `SUBSKILL.md`，`SKILL.md` 再降 4 个至 56。

第二轮把办公相关技能（含 HTML 生成、产物检测，不含飞书/Lark 技能）并入 `office/`，
`SKILL.md` 再降 4 个至 60。

## 合并范围与判定

只合并**与编码、工具调用都无关**的纯知识型技能：运行时不需要外部 CLI、正文不含
`lark-cli`/`mediakit-cli`/`computer_use_tool` 等调用指令。判定方式是扫描每个技能
全部文件里的工具名出现次数，为 0 才纳入。

金融与医疗虽在最终名单内，但两者的检索入口（`seed_finance_search`、医学数据库）
依赖宿主工具。已保留其方法论，检索段落在子技能内部自行处理。

## 未合并

| 域 | 数量 | 原因 |
|---|---|---|
| `lark/` | 20 | 依赖 `lark-cli`，且是产物载体 |
| `platform-doubao/` | 15 | 依赖豆包私有工具，豆包外不可运行 |
| `media/` | 7 | 依赖豆包生图/生视频/生音频工具 |
| `documents/` | 0 | 已整体并入 `office/`，空目录删除 |
| `tooling/` | 2 | CLI 封装或元技能（余下 `artifact-preview`、`doubao-pc-optimizer`） |
| `web-dev/` | 1 | 产物载体（余下 `doubao-app-builder`，属全栈开发） |

## 两个独立保留的重资产

- `finance/doubao-finance-model-builder/` — 116 文件、1190 KB、51 个脚本。若并进 `finance`
  会带来校验器跨模式误触发风险，且体积翻倍。
- `legal/doubao-personal-info-audit/` — 69 文件、453 KB、10 个校验脚本。同理。

两者仍是独立可加载技能，各自保留 `SKILL.md`。

## 目录结构示例

```
medical/
├── SKILL.md                          ← 域根：系统提示 + 子技能索引
└── references/
    ├── doubao-answer-with-medical-evidence/
    │   ├── SUBSKILL.md
    │   ├── references/
    │   └── scripts/
    ├── doubao-clinical-decision-support/
    └── ...
```

子技能内部的相对路径仍以它自己所在的 `references/<子技能名>/` 为基准解析——
整棵子树一起搬迁，解析基准未变，无需改写。域根 `SKILL.md` 用
`<system-reminder>` 块把这条规则显式锁定，并规定从域根调用脚本时必须写完整前缀。

## 合并时的连带修改

1. **77 个 `SKILL.md` → `SUBSKILL.md`**（53 顶层 + 24 嵌套），并改写 90 个文件里 212 处引用。
   不改的话宿主会把子技能重复加载为独立技能。
2. **`content/…/scripts/quality/machine-quality-engine.mjs`** 真实读取
   `path.join(bundleRoot, 'SKILL.md')`，已同步改为 `SUBSKILL.md`。
3. **`finance/doubao-finance-model-builder`** 原引用 `sheet/SKILL.md`，已改为
   `lark/sheet/SUBSKILL.md`（含 `reading-manifest.json`、校验器与测试）。
4. **第二轮 `office/`**：5 个顶层 `SKILL.md` 改名 `SUBSKILL.md`（无嵌套），并修复跨技能
   引用——`README.md` 的 `tooling/verifier-hub` 路径、`skill-creator-for-work` 内
   `pdf/scripts/...` 示例路径等。
5. **第三轮 `lifestyle/`**：`branches/` 下 4 个分支的顶层 `SKILL.md` 改名 `SUBSKILL.md`，
   域根 `SKILL.md` 里 `branches/<名>/SKILL.md` 与 `branches/{selected-branch}/SKILL.md`
   模板路径改写为 `references/.../SUBSKILL.md`（10 处）。分支间无交叉引用，
   `../` 仅出现在 URL 与输出路径中，故子树搬迁不产生断链。

## 已知问题

- `content/references/doubao-book-writer/sub-skills/project-intake/SUBSKILL.md` 与
  `references/intake-routing.md` 引用 `../../../references/checklist-schema.md`，
  实际应为 `../../references/...`。**上游即存在此笔误**，非本次合并引入，未修改。

## 许可

未统一授权。`byted-mediakit-*` 声明 MIT；`office/references/verifier-hub`
声明 Proprietary — internal use only；其余多数未声明 license。作为公开仓库前需确认。

## 已知缺失

`tooling/artifact-preview/` 只有 `bin/` 与 `lib/`，其顶层 `SKILL.md` 在上游导出包中
即已缺失，不构成可加载的完整 Skill。