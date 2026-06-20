# Leo Suite — cenzhi 账号部署清单

**唯一官方位置：**

| 服务 | 账号 |
|------|------|
| GitHub | [mentorkokkwa](https://github.com/mentorkokkwa) |
| Vercel | [vercel.com/cenzhi](https://vercel.com/cenzhi) |

不要在 **amyling** 账号保留 leo-suite 相关 GitHub 仓库或 Vercel 项目。

---

## 已完成（自动化）

- [x] **amyling Vercel** 已删除：`leo-suite-growth`、`leo-suite-edutech`、`leo-suite-robot`
- [x] 三个 app 代码仅在 **mentorkokkwa** GitHub
- [x] 根路径 `/` 自动跳转：`growth` → `/youthmentor`，`edutech` → `/edulens`，`robot` → `/campusbot`
- [x] 仓库内无 API key、无 Windows 绝对路径、无开发者姓名

---

## 需要你手动完成

### 1. 删除 amyling GitHub 上的重复仓库

用 **amyling** 登录 GitHub，对每个仓库：**Settings → General → Danger Zone → Delete this repository**

- `amyling/leo-suite-growth`
- `amyling/leo-suite-edutech`
- `amyling/leo-suite-robot`

（正式代码以 **mentorkokkwa/** 下同名仓库为准。）

### 2. 确认 cenzhi Vercel 三个项目

登录 https://vercel.com/cenzhi ，应各有 1 个项目，且 **Git** 已连接 `mentorkokkwa/leo-suite-*`：

| Vercel 项目 | GitHub 仓库 | Production 分支 |
|-------------|-------------|-----------------|
| leo-suite-growth | mentorkokkwa/leo-suite-growth | main |
| leo-suite-edutech | mentorkokkwa/leo-suite-edutech | main |
| leo-suite-robot | mentorkokkwa/leo-suite-robot | main |

Root Directory：**留空**。

若缺少项目：https://vercel.com/new → Import 上述仓库。

### 3. 环境变量（仅 cenzhi Vercel Dashboard）

**robot：无需任何变量。**

**growth 与 edutech** — Settings → Environment Variables → 至少勾选 **Production**（建议同时勾选 Preview）。

#### 非密钥（可直接复制）

**leo-suite-growth：**

```
EDULENS_AI_MODE=auto
EDULENS_PROVIDER_CHAIN=GEMINI,GROQ,DEEPSEEK,OPENROUTER,NVIDIA,OPENAI
EDULENS_SKIP_OLLAMA=true
EDULENS_PREFER_OLLAMA=false
NEXT_PUBLIC_EDULENS_URL=https://你的-edutech-域名.vercel.app
```

**leo-suite-edutech：**

```
EDULENS_AI_MODE=auto
EDULENS_PROVIDER_CHAIN=AGNES,GEMINI,GROQ,DEEPSEEK,OPENROUTER,NVIDIA,OPENAI
EDULENS_SKIP_OLLAMA=true
EDULENS_PREFER_OLLAMA=false
EDULENS_RAG_ENABLED=true
EDULENS_RAG_WEB_ENABLED=true
```

#### 密钥（从本机 `.env.local` 复制，勿提交 GitHub）

按你本地实际使用的 provider 填写，例如：

```
GEMINI_API_KEY=
GROQ_API_KEY=
DEEPSEEK_API_KEY=
OPENROUTER_API_KEY=
NVIDIA_API_KEY=
OPENAI_API_KEY=
```

edutech 若用 Agnes 再加 `AGNES_API_KEY=`。

> **Ollama（127.0.0.1）无法在 Vercel 运行** — 线上只用云端 key，与本地「有 Ollama 时优先本地」的行为等价（云端链相同）。

保存后：**Deployments → Redeploy**。

### 4. 验证

| 检查 | URL |
|------|-----|
| YouthMentor 首页 | `https://你的-growth-域名/` → 应进入 `/youthmentor` |
| AI 状态 | `/api/ai/status` → `"mode"` 不是 `"mock"` |
| EduLens | `/edulens` |
| EduLens AI | `/api/edulens/ai-status` |
| CampusBot | `/campusbot` |

### 5. 本机 CLI（可选）

```powershell
vercel logout
vercel login
```

用 **cenzhi** 完成登录后，在 `growth/`、`edutech/`、`robot/` 分别：

```powershell
vercel link
```

选择 cenzhi 团队下对应项目（勿再 link 到 amyling）。

---

## 安全

- `.env.local` 仅在本机，已在 `.gitignore`
- 若 key 曾出现在聊天或旧部署，建议在各平台 **轮换 key**
