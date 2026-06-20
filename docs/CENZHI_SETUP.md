# Leo Suite — cenzhi 部署清单

**官方位置：**

| 服务 | 账号 |
|------|------|
| GitHub | [mentorkokkwa](https://github.com/mentorkokkwa) |
| Vercel | [vercel.com/cenzhi](https://vercel.com/cenzhi) |

---

## 仓库

| Vercel 项目 | GitHub 仓库 |
|-------------|-------------|
| leo-suite-growth | [mentorkokkwa/leo-suite-growth](https://github.com/mentorkokkwa/leo-suite-growth) |
| leo-suite-edutech | [mentorkokkwa/leo-suite-edutech](https://github.com/mentorkokkwa/leo-suite-edutech) |
| leo-suite-robot | [mentorkokkwa/leo-suite-robot](https://github.com/mentorkokkwa/leo-suite-robot) |
| 文档 | [mentorkokkwa/leo-suite](https://github.com/mentorkokkwa/leo-suite) |

Import 时 **Root Directory 留空**，Production 分支 **main**。

---

## 环境变量

路径：**Settings → Environment Variables**（不是 Environments 页）。

**robot：** 无需变量。

**growth / edutech：** 至少勾选 **Production**。

### leo-suite-growth（非密钥）

```
EDULENS_AI_MODE=auto
EDULENS_PROVIDER_CHAIN=GEMINI,GROQ,DEEPSEEK,OPENROUTER,NVIDIA,OPENAI
EDULENS_SKIP_OLLAMA=true
EDULENS_PREFER_OLLAMA=false
```

### leo-suite-edutech（非密钥）

```
EDULENS_AI_MODE=auto
EDULENS_PROVIDER_CHAIN=AGNES,GEMINI,GROQ,DEEPSEEK,OPENROUTER,NVIDIA,OPENAI
EDULENS_SKIP_OLLAMA=true
EDULENS_PREFER_OLLAMA=false
EDULENS_RAG_ENABLED=true
EDULENS_RAG_WEB_ENABLED=true
```

### 密钥（从本机 `.env.local` 复制，勿提交 GitHub）

```
GEMINI_API_KEY=
GROQ_API_KEY=
DEEPSEEK_API_KEY=
OPENROUTER_API_KEY=
NVIDIA_API_KEY=
OPENAI_API_KEY=
```

edutech 若用 Agnes：`AGNES_API_KEY=`

> Ollama（127.0.0.1）无法在 Vercel 运行；线上只用云端 key。

保存后 **Deployments → Redeploy**。

---

## 验证

| 检查 | 期望 |
|------|------|
| growth `/` | 进入 `/youthmentor` |
| `/api/ai/status` | `"mode"` 不是 `"mock"` |
| edutech `/edulens` | 页面正常 |
| robot `/campusbot` | 仿真正常 |

---

## 本机 CLI（可选）

```powershell
vercel login
```

用 **cenzhi** 登录后，在 `growth/`、`edutech/`、`robot/` 执行 `vercel link`，选择 cenzhi 团队下对应项目。

---

## 安全

- `.env.local` 仅在本机，已在各 app 的 `.gitignore`
- API key 只放在 Vercel Dashboard，不要写入 GitHub
