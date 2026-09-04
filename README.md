# Hi, I'm Brent 👋

**AI Agent 工程 + 后端。** 关注的问题是同一个：**怎么让一个系统在没人盯着的时候，把活干完 —— 而不是悄悄干错。**

在 Agent 这边，这意味着权限边界、上下文管理和可被证伪的验收判据；在后端那边，意味着幂等、拒写护栏和数据一致性。两边的失败模式其实长得一样：**静默降级永远比崩溃更贵。**

---

## 🤖 AI Agent 工程

把 Agent 从"能调用工具"推到"能独立交付一个工单"。

**权限边界不靠自觉，靠工具层。**
多角色协作链路 `researcher → critic → executor → verifier`，每个角色一份工具白名单 —— 审查者和验证者**在工具层就写不了文件**，越权不是被规则禁止，是物理上做不到。

**判据必须能证伪。**
"让它跑起来"不是判据。"先写一个能复现的失败测试，再让它变绿"才是。每一步都带 verify，Agent 才可能自主跑完全程而不需要人在每一步回车。

**先预测，再验证。**
跑之前写下预期结果，用差值验收。**看到绿灯就算过，是最贵的错觉** —— 绿灯只说明没崩，不说明做对了。

**在读的方向：Agent 运行时的可靠性。**
上下文压缩的触发口径与估算口径不一致时会发生什么、工具调用结果的截断边界、失败恢复与断点续跑。目前在 [vercel/eve](https://github.com/vercel/eve)、[espressif/esp-claw](https://github.com/espressif/esp-claw) 等 Agent 框架上做源码级排查。

> `Claude Code` · `Agent SDK` · `MCP` · `多 Agent 编排` · `Skills / Hooks` · `LLM 应用工程`

---

## ⚙️ 后端工程

跨境电商的订单与物流链路 —— ERP、Shopify、飞书多维表格、内部平台之间的数据流转与一致性。

**写过的最有价值的代码不是新功能，是护栏。**

- **先做幂等和拒写护栏，再谈自动化。** 一次 read timeout 不该丢掉一整天的发货登记。
- **静默降级比崩溃更贵。** 硬编码列号找不到列时返回 0，比抛异常危险得多 —— 没人会发现。
- **性能优化改的是数据形状，不是机器。** 一次典型收益：内部看板首屏 26.5s → 传输量降 137×，热点接口快 600×，改的是查询与序列化。

支撑上面这些的是一套长期在真实业务上跑的服务：订单同步、发货前置库存自检、审批流导出等 50+ 个模块。

> `Python` · `PostgreSQL` · `FastAPI` · `Docker Compose` · `Playwright` · `飞书开放平台` · `Shopify / ERP 集成`

---

## 🌱 Open Source

| 项目 | 内容 | 状态 |
|---|---|---|
| [microsoft/skill-recorder #72](https://github.com/microsoft/skill-recorder/pull/72) | 零依赖 i18n 基础设施 + 简体中文本地化 | Open · CLA signed |
| [selfhosted-tracker-eval](https://github.com/lizheng220/selfhosted-tracker-eval) | Cattr / ActivityWatch 自托管评测：loopback-only 端口绑定、独立网络与卷、资源上限 | Public |

贡献方向：**Agent 运行时的可靠性** —— 上下文管理、工具调用边界、失败恢复。

---

## 📌 About

- 📍 杭州 · Hangzhou
- 🛠 主力语言 Python，TypeScript 够用
- 📮 GitHub Issues / PR 是最快的联系方式

> **能被测试证伪的结论，才值得写进代码。**
