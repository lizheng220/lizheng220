# Hi, I'm Brent 👋

后端 / 自动化工程师。做的事情可以概括成一句话：**把靠人手点鼠标的业务流程，换成能自己跑、出错能自己喊人的系统。**

日常在跨境电商的订单与物流链路上 —— ERP、Shopify、飞书多维表格、内部平台之间的数据流转与一致性。近一年重心从"写脚本"移到了**用 AI Agent 编排真实生产任务**：多角色协作链路、工具级权限隔离、可被证伪的验收判据。

---

## 🔧 What I build

### 生产自动化

订单同步 · 自动发货 · 发货前置库存自检 · 采购审批流导出 —— 50+ 个独立模块，每天在真实业务上跑。

不是"能跑就行"的自动化。几条自己踩出来的规矩：

- **先做幂等和拒写护栏，再谈自动化。** 一次 read timeout 不该丢掉一整天的发货登记。
- **静默降级比崩溃更贵。** 硬编码列号找不到列时返回 0，比抛异常危险得多 —— 没人会发现。
- **性能优化改的是数据形状，不是机器。** 一次典型收益：内部看板首屏 26.5s → 传输量降 137×，热点接口快 600×。

> `Python` · `PostgreSQL` · `Docker Compose` · `Playwright` · `飞书开放平台` · `Shopify / ERP 集成`

### AI Agent 工程

把 Agent 从"能调用工具"推到"能独立交付一个工单"。

- **多角色协作链路**：researcher → critic → executor → verifier，用**工具白名单做物理权限边界** —— 审查者和验证者在工具层就写不了文件，越权不靠自觉。
- **可验证目标**：每一步都带判据。"让它跑起来"不是判据，"先写一个能复现的失败测试，再让它变绿"才是。
- **先预测再验证**：跑之前写下预期结果，用差值验收。看到绿灯就算过，是最贵的错觉。
- Claude Code 的 skills / hooks / 定时唤醒，落到真实的排班与巡查任务上。

> `Claude Code` · `Agent SDK` · `MCP` · `多 Agent 编排` · `LLM 应用工程`

---

## 🌱 Open Source

| 项目 | 内容 | 状态 |
|---|---|---|
| [microsoft/skill-recorder #72](https://github.com/microsoft/skill-recorder/pull/72) | 零依赖 i18n 基础设施 + 简体中文本地化 | Open · CLA signed |
| [selfhosted-tracker-eval](https://github.com/lizheng220/selfhosted-tracker-eval) | Cattr / ActivityWatch 自托管评测：loopback-only 端口绑定、独立网络与卷、资源上限 | Public |

主要贡献方向：**Agent 运行时的可靠性** —— 上下文管理、工具调用边界、失败恢复。

---

## 📌 About

- 📍 杭州 · Hangzhou
- 🛠 主力语言 Python，TypeScript 够用
- 📮 GitHub Issues / PR 是最快的联系方式

> **能被测试证伪的结论，才值得写进代码。**
