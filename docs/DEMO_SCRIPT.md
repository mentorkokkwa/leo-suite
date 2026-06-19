# Product Walkthrough Script / 产品演示脚本

A ~3-minute walkthrough when sharing the project live or recording a demo.  
**Plan A:** local `localhost`. **Plan B:** Vercel URL with mock mode. **Plan C:** screen recording.

---

## English (≈3 minutes)

### 0:00 — Hook (15 s)

> "I'm Liu Cenzhi. I built **NeuroSpark Suite** — three apps around how students **learn**, **grow**, and how schools could **serve** with robots. I'll start with YouthMentor's safety layer — the part I care most about technically."

### 0:15 — Problem (20 s)

> "Many students feel exam stress but won't seek help early. Apps that only chat with AI can give harmful advice. I wanted structured reflection **plus** hard safety guardrails — not safety as an afterthought."

### 0:35 — Walkthrough: normal flow (45 s)

**Actions:** Open `/youthmentor` → Demo → **Exam stress** → Check-in (pre-filled) → Continue → Reflection → **Get mentor response**.

> "The user checks mood, completes six structured reflection prompts, then gets a mentor-style response and action plan. Data stays in the browser — no account, privacy-first."

### 1:20 — Walkthrough: safety (60 s) ★ highlight

**Actions:** Home → **Safety demo** (or Demo → **High-risk sample**) → Reflection → **Get mentor response** → Safety page.

> "When high-risk language is detected, the pipeline **stops before** any coaching LLM call. Only crisis resources appear — helplines, talk to a trusted adult. You can see which keywords triggered and why the classifier blocked. Safety is not delegated to the model."

### 2:20 — Technical + product (30 s)

> "Stack: Next.js, TypeScript, multi-provider LLM with mock fallback. Character chat uses RAG-lite from public teachings. Same repo also has EduLens for homework feedback and CampusBot with A* navigation — different problems, shared AI layer."

### 2:50 — Close (10 s)

> "Next I'd pilot the anonymous insights dashboard with schools. Code is on GitHub; happy to walk through architecture or any module."

---

## 中文（约 3 分钟）

### 0:00 — 开场（15 秒）

> 「我是刘岑之。我做了 **NeuroSpark 套件** 三个项目：学生**学**（EduLens）、**成长**（YouthMentor）、校园**机器人**仿真（CampusBot）。先从 YouthMentor 的**安全层**讲起——这是我技术上最在意的部分。」

### 0:15 — 问题（20 秒）

> 「学生考试压力大，但不太愿意早点求助。纯聊天 AI 可能给出不安全建议。我希望有结构化反思，加上**硬性安全护栏**，而不是事后补丁。」

### 0:35 — 演示：正常流程（45 秒）

**操作：** 打开 `/youthmentor` → 演示案例 → **考试压力** → 签到 → 反思 → **获取导师回复**。

> 「用户记录心情、完成六步结构化反思，得到导师风格和行动计划。数据只在浏览器本地，注重隐私。」

### 1:20 — 演示：安全拦截（60 秒）★ 重点

**操作：** 首页 → **安全演示** → 反思 → **获取导师回复** → 安全页。

> 「检测到高风险用语时，系统在调用辅导 LLM **之前**就拦截，只显示危机资源。能看到触发的关键词和分类原因——安全不能交给模型自己判断。」

### 2:20 — 技术与产品（30 秒）

> 「技术栈：Next.js、TypeScript、多 LLM 供应商与 mock 降级。角色聊天用 RAG 注入公开资料。同一仓库还有 EduLens 和 CampusBot 的 A* 路径规划。」

### 2:50 — 收尾（10 秒）

> 「下一步想试点学校匿名统计面板。代码在 GitHub，也可以讲架构或任意模块。」

---

## Other walkthrough paths

| Scenario | Route | Time |
|----------|-------|------|
| Safety only | `/youthmentor/safety-demo` → Run demo | 60 s |
| Character chat | `/youthmentor/characters` → scenario card | 45 s |
| EduLens | `/edulens/homework-analyzer` → load demo | 45 s |
| CampusBot | `/campusbot/experiments` → run worksheet delivery | 60 s |

## If something breaks

1. Switch to **mock mode** (no API keys needed).  
2. Play a pre-recorded walkthrough.  
3. Open `docs/ARCHITECTURE.md` and explain the diagrams.

## Recording checklist

- [ ] 1920×1080, show browser URL bar  
- [ ] Record safety flow end-to-end (crisis panel visible)  
- [ ] Keep under 3 minutes  
- [ ] Export as `docs/demo-recording.mp4` (optional, gitignored if large)
