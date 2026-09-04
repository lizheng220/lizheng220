# Hi, I'm Brent 👋

**AI agent engineering + backend.** Both sides of my work come down to the same question: **how do you get a system to finish the job when nobody is watching — instead of quietly getting it wrong?**

On the agent side that means permission boundaries, context management, and acceptance criteria that can actually be falsified. On the backend side it means idempotency, refuse-to-write guardrails, and data consistency. The failure mode is identical either way: **silent degradation costs far more than a crash.**

---

## 🤖 AI Agent Engineering

Pushing agents from "can call a tool" to "can deliver a whole work item on their own."

**Permission boundaries belong in the tool layer, not in the prompt.**
A multi-role pipeline — `researcher → critic → executor → verifier` — where each role gets its own tool allowlist. The critic and the verifier **physically cannot write files**; overreach isn't forbidden by a rule the model may ignore, it's unavailable.

**Acceptance criteria have to be falsifiable.**
"Make it run" is not a criterion. "Write a failing test that reproduces it, then make it green" is. When every step carries its own verify, an agent can run a task end to end without a human pressing Enter at each turn.

**Predict first, then verify.**
Write down the expected result *before* running anything, and accept on the diff. **Treating a green light as proof is the most expensive illusion there is** — green means nothing crashed, not that anything was done correctly.

**What I'm digging into: agent runtime reliability.**
What happens when a compaction trigger and its size estimator disagree on the ruler; where tool-result truncation boundaries fall; how a run recovers and resumes after failure. Currently doing source-level investigation on agent frameworks including [vercel/eve](https://github.com/vercel/eve) and [espressif/esp-claw](https://github.com/espressif/esp-claw).

> `Claude Code` · `Agent SDK` · `MCP` · `multi-agent orchestration` · `skills / hooks` · `LLM application engineering`

---

## ⚙️ Backend

Order and logistics pipelines for cross-border e-commerce — keeping data consistent as it moves between ERP, Shopify, Feishu Bitable, and internal platforms.

**The most valuable code I've written isn't features. It's guardrails.**

- **Idempotency and refuse-to-write guards come before automation.** One read timeout should never cost a full day of shipping records.
- **Silent degradation costs more than a crash.** Falling back to `0` when a hardcoded column index misses is far more dangerous than raising — nobody ever finds out.
- **Performance work changes the shape of the data, not the size of the machine.** A representative result: an internal dashboard's first paint went 26.5s → 137× less data transferred, with the hot endpoint 600× faster — all from query and serialization changes.

Underneath all of that sits a set of services running against live business every day: order sync, pre-shipment stock checks, approval-flow exports, and 50+ other modules.

> `Python` · `PostgreSQL` · `FastAPI` · `Docker Compose` · `Playwright` · `Feishu Open Platform` · `Shopify / ERP integrations`

---

## 🌱 Open Source

| Project | What | Status |
|---|---|---|
| [microsoft/skill-recorder #72](https://github.com/microsoft/skill-recorder/pull/72) | Dependency-free i18n foundation + Simplified Chinese | Open · CLA signed |
| [selfhosted-tracker-eval](https://github.com/lizheng220/selfhosted-tracker-eval) | Isolated evaluation sandbox for Cattr / ActivityWatch: loopback-only ports, dedicated networks and volumes, resource caps | Public |

Where I want to contribute: **agent runtime reliability** — context management, tool-call boundaries, failure recovery.

---

## 📌 About

- 📍 Hangzhou, China
- 🛠 Python as the primary language; TypeScript when the work calls for it
- 📮 GitHub issues and PRs are the fastest way to reach me

> **A conclusion worth putting in code is one a test could have proven wrong.**
