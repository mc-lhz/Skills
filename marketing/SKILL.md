---
name: marketing
description: doubao-customer-service：生成电商在线文字客服的可执行处理方案和正式交付文档。适用于客户回复、售前咨询、催发货、物流履约、退换货、质量问题、补偿争议、差评投诉、私聊舆情询问、聊天截图分析、客服标准流程、权限矩阵；doubao-ecommerce-compliance-tax-logistics：Cross-border ecommerce compliance, tax, IP, customs, tariff, HS code, fulfillment, warehousing, Chin；doubao-ecommerce-proposal：电商活动策划专家。用于生成、改写、优化完整电商活动策划方案，并默认交付一份已经本地落地、可用浏览器打开验证的 HTML 网页版方案。覆盖淘宝/天猫、抖音电商、京东、得物、拼多多、小红书、Amazon；doubao-listing-localization：Cross-border ecommerce Listing and Product Optimization for Amazon, TEMU, Walmart Marketplace, TikTo；doubao-marketing-material-review：营销素材审核。当用户上传待审核的广告宣传语、营销海报、社交媒体推广文案、直播话术等营销素材时，从虚假宣传、夸大宣传、绝对化用语、比较广告、引证数据真实准确性、价格违规、有奖营销、知识产权；doubao-marketing-plan：首席营销策划官。用于生成、改写、优化并默认以飞书文档/Lark Doc 交付，以首席营销策划官的全域营销能力，把用户模糊的业务诉求转化为资深操盘手会交付的实战级方案；doubao-product-content：生成或优化电商商品标题、详情文案和商品页静态图片；doubao-product-selection：电商选品与品类机会分析技能。根据商家的预算、目标平台、货源优势，按"市场需求×竞争度×利润空间×季节性×复购率"五维打分，输出3-5个候选品类及切入建议。适用于新手不知道卖什么、老商家想拓新品类；doubao-sentiment-tracker：当用户在网页端或电脑客户端需要进行舆情监控、调研、社交媒体反馈收集、用户评价、品牌声量追踪时使用。支持微博、知乎、即刻、脉脉、B站、抖音.等多平台的舆情搜索、内容筛选和原始帖子溯源。共 9 个子技能，按诉求分流；只涉及其中某一项时，只读取并执行对应的子技能，不加载其他子技能。
---

# 营销与电商

本技能是 9 个子技能的集合入口。收到诉求后先按下表定位唯一匹配的子技能，再 `Read references/<子技能名>/SUBSKILL.md` 进入该子技能，按其内部的阶段/路由表继续执行。不要一次性通读全部子技能。

## 子技能索引

| 子技能 | 职责 |
|---|---|
| [`doubao-customer-service`](references/doubao-customer-service/SUBSKILL.md) | 生成电商在线文字客服的可执行处理方案和正式交付文档。适用于客户回复、售前咨询、催发货、物流履约、退换货、质量问题、补偿争议、差评投诉、私聊舆情询问、聊天截图分析、客服标准流程、权限矩阵 |
| [`doubao-ecommerce-compliance-tax-logistics`](references/doubao-ecommerce-compliance-tax-logistics/SUBSKILL.md) | Cross-border ecommerce compliance, tax, IP, customs, tariff, HS code, fulfillment, warehousing, Chin |
| [`doubao-ecommerce-proposal`](references/doubao-ecommerce-proposal/SUBSKILL.md) | 电商活动策划专家。用于生成、改写、优化完整电商活动策划方案，并默认交付一份已经本地落地、可用浏览器打开验证的 HTML 网页版方案。覆盖淘宝/天猫、抖音电商、京东、得物、拼多多、小红书、Amazon |
| [`doubao-listing-localization`](references/doubao-listing-localization/SUBSKILL.md) | Cross-border ecommerce Listing and Product Optimization for Amazon, TEMU, Walmart Marketplace, TikTo |
| [`doubao-marketing-material-review`](references/doubao-marketing-material-review/SUBSKILL.md) | 营销素材审核。当用户上传待审核的广告宣传语、营销海报、社交媒体推广文案、直播话术等营销素材时，从虚假宣传、夸大宣传、绝对化用语、比较广告、引证数据真实准确性、价格违规、有奖营销、知识产权 |
| [`doubao-marketing-plan`](references/doubao-marketing-plan/SUBSKILL.md) | 首席营销策划官。用于生成、改写、优化并默认以飞书文档/Lark Doc 交付，以首席营销策划官的全域营销能力，把用户模糊的业务诉求转化为资深操盘手会交付的实战级方案 |
| [`doubao-product-content`](references/doubao-product-content/SUBSKILL.md) | 生成或优化电商商品标题、详情文案和商品页静态图片 |
| [`doubao-product-selection`](references/doubao-product-selection/SUBSKILL.md) | 电商选品与品类机会分析技能。根据商家的预算、目标平台、货源优势，按"市场需求×竞争度×利润空间×季节性×复购率"五维打分，输出3-5个候选品类及切入建议。适用于新手不知道卖什么、老商家想拓新品类 |
| [`doubao-sentiment-tracker`](references/doubao-sentiment-tracker/SUBSKILL.md) | 当用户在网页端或电脑客户端需要进行舆情监控、调研、社交媒体反馈收集、用户评价、品牌声量追踪时使用。支持微博、知乎、即刻、脉脉、B站、抖音.等多平台的舆情搜索、内容筛选和原始帖子溯源 |

<system-reminder>
本技能由若干子技能构成，每个子技能位于 `references/<子技能名>/`，且各自保留完整的
`SUBSKILL.md` 与 `references/`、`scripts/`、`assets/` 目录树。子技能内部的相对路径
一律以它自己所在的 `references/<子技能名>/` 为基准解析——读到 `scripts/x.py`、
`references/y.md` 时，实际指向 `references/<子技能名>/scripts/x.py`，
不要退回到本技能根目录查找，也不要再加一层 `references/` 前缀。

执行某一子技能的脚本时，须使用完整路径 `references/<子技能名>/scripts/...`；
子技能文档里写的 `python3 scripts/...` 是相对它自身目录的，不能照搬到本技能根下运行。
</system-reminder>
