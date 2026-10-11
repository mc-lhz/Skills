# Skills

Agent Skill 集合。多数源自豆包（ByteDance）办公环境导出。

**当前 42 个可加载技能**（`SKILL.md`），其中 2 个是三层聚合入口（`AllInKnowledge/` 与
`office/`），另 40 个为独立技能（`lark/`、`platform-doubao/`、`media/`、`tooling/`、`web-dev/`）。

## 两个聚合技能（两层结构：部分 → 子技能）

聚合技能为 `SKILL.md` → `references/<部分名>/<子技能名>/SUBSKILL.md`。
根 `SKILL.md` 只写「部分 → 子技能」索引表与路径基准约束（`<system-reminder>`），
子技能整棵子树保留各自的 `references/`、`scripts/`、`assets/`。这样宿主不会把子技能
重复加载为独立技能。

| 技能 | 部分数 | 子技能数 | 覆盖 |
|---|---|---|---|
| `AllInKnowledge/` | 7 | 59 | 学术研究、内容创作、金融财务、法律合规、医疗健康、产品与生活、财报建模 |
| `office/` | 3 | 9 | PDF/HTML 文档、Word/PPT/表格零一文档、论文排版、产物校验、Skill 创建 |

`AllInKnowledge` 部分：`research`(7)、`content`(7)、`business`(21)、`health`(7)、
`compliance`(7)、`product-lifestyle`(9)、`finance-model`(1)。
`office` 部分：`document`(2)、`word-ppt-sheet`(4)、`format-verify`(3)。

## 演进过程

第一轮：按功能分 15 个目录（106 个技能）。
第二轮：纯知识型 53 个子技能合并为 8 个域根 + `office`，`SKILL.md` 降至 60。
第三轮：`lifestyle` 4 个分支收敛为子技能，降至 56。
第四轮：按「文档产出 vs 平台能力」重组为 `AllInKnowledge`(59) 与 `office`(9) 两个聚合技能，
并把 `lark` 的 word/ppt/sheet/lark-doc 移入 `office`，两个重资产
（finance-model-builder、personal-info-audit）下沉为子技能，`SKILL.md` 降至 42。

## 合并范围与判定

只合并**与编码、工具调用都无关**的纯知识型技能：运行时不需要外部 CLI、正文不含
`lark-cli`/`mediakit-cli`/`computer_use_tool` 等调用指令。判定方式是扫描每个技能
全部文件里的工具名出现次数，为 0 才纳入。

金融与医疗虽在最终名单内，但两者的检索入口（`seed_finance_search`、医学数据库）
依赖宿主工具。已保留其方法论，检索段落在子技能内部自行处理。

## 未聚合（保持独立可加载）

| 目录 | 数量 | 原因 |
|---|---|---|
| `lark/` | 16 | 依赖 `lark-cli`；word/ppt/sheet/doc 已移入 `office`，其余为协作能力 |
| `platform-doubao/` | 15 | 依赖豆包私有工具，豆包外不可运行 |
| `media/` | 7 | 依赖豆包生图/生视频/生音频工具 |
| `tooling/` | 2 | CLI 封装或元技能（`artifact-preview` 无 `SKILL.md`，`doubao-pc-optimizer` 非办公） |
| `web-dev/` | 1 | `doubao-app-builder` 属全栈开发，非文档产出 |

## 两个重资产（已下沉为子技能）

- `AllInKnowledge/references/finance-model/doubao-finance-model-builder/` — 116 文件、51 脚本。
- `AllInKnowledge/references/compliance/doubao-personal-info-audit/` — 69 文件、10 校验脚本。

两者均以 `SUBSKILL.md` 为入口被聚合。`doubao-personal-info-audit` 保留完整校验脚本，
触发需显式点名。

## 目录结构示例

```
AllInKnowledge/
├── SKILL.md                          ← 根：部分→子技能索引 + <system-reminder>
└── references/
    ├── health/                       ← 部分
    │   ├── doubao-medical-report/
    │   │   ├── SUBSKILL.md
    │   │   ├── references/
    │   │   └── scripts/
    │   └── doubao-clinical-decision-support/
    ├── business/
    └── ...

office/
├── SKILL.md
└── references/
    ├── word-ppt-sheet/
    │   ├── word/SUBSKILL.md
    │   ├── ppt/SUBSKILL.md
    │   ├── sheet/SUBSKILL.md
    │   └── lark-doc/SUBSKILL.md
    ├── document/{pdf,html}/SUBSKILL.md
    └── format-verify/{doubao-journal-format,skill-creator-for-work,verifier-hub}/SUBSKILL.md
```

子技能内部的相对路径仍以它自己所在的 `references/<部分名>/<子技能名>/` 为基准解析——
整棵子树一起搬迁，解析基准未变，无需改写。根 `SKILL.md` 用 `<system-reminder>` 块把这条
规则显式锁定，并规定从根调用脚本时必须写完整前缀（含部分名）。

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
6. **第四轮两技能重组**：59 个子技能迁入 `AllInKnowledge/references/<部分>/`，9 个迁入
   `office/references/<部分>/`；`lark` 的 word/ppt/sheet/lark-doc 移入 `office`；
   两个重资产入口改名 `SUBSKILL.md` 并下沉；删除 9 个只剩 `SKILL.md` 的空壳旧域根。
   - `doubao-finance-model-builder` 内部多处硬编码入口文件名，已同步：
     `reading-manifest.json` 的 `always`、`validate_reading_integrity.py`、
     `test_reading_integrity.py`，以及自身末尾标记 `<!-- END OF FILE: SUBSKILL.md -->`。
   - 该技能的 `lark/sheet` 外部依赖改为 `office/references/word-ppt-sheet/sheet/SUBSKILL.md`
     （manifest `external_required`、`SUBSKILL.md` 正文与 ledger 示例、测试）。
   - **顺带修复一个跨平台缺陷**：`validate_reading_integrity.py` 用
     `str(path.relative_to(root))` 枚举 Markdown，在 Windows 上产出 `references\a.md`，
     与 manifest 中声明的 `references/a.md` 不匹配，导致 40 个文件被误判「未声明」而
     恒返回 `FAIL`。改用 `.as_posix()` 后，该技能 5 个测试由全红转全绿。

## 已知问题

- `AllInKnowledge/references/content/doubao-book-writer/sub-skills/project-intake/SUBSKILL.md`
  与 `references/intake-routing.md` 引用 `../../../references/checklist-schema.md`，
  实际应为 `../../references/...`。**上游即存在此笔误**，非本次合并引入，未修改。
- `AllInKnowledge/references/compliance/doubao-contract-drafting/scripts/validate_skill_architecture.py`
  要求 `agents/openai.yaml` 与 `evals/run_evals.py`，但该技能从未包含这两个文件
  （git 历史中即不存在）。属上游缺失，非本次重组引入，未修改。

## 许可

未统一授权。`byted-mediakit-*` 声明 MIT；`office/references/format-verify/verifier-hub`
声明 Proprietary — internal use only；其余多数未声明 license。作为公开仓库前需确认。

## 已知缺失

`tooling/artifact-preview/` 只有 `bin/` 与 `lib/`，其顶层 `SKILL.md` 在上游导出包中
即已缺失，不构成可加载的完整 Skill。