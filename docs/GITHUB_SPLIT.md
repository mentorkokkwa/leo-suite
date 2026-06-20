# 三个 GitHub 仓库（mentorkokkwa）

每个 app **独立仓库** → Vercel **Import 一次**，无需 Root Directory。

## 仓库一览

| App | 仓库 |
|-----|------|
| YouthMentor | https://github.com/mentorkokkwa/leo-suite-growth |
| EduLens | https://github.com/mentorkokkwa/leo-suite-edutech |
| CampusBot | https://github.com/mentorkokkwa/leo-suite-robot |
| 文档 | https://github.com/mentorkokkwa/leo-suite |

## 本地开发

在各自子目录内 push，只更新对应仓库：

```bash
cd growth
git push origin main
```

（edutech、robot 同理。）

## Vercel

见 [CENZHI_SETUP.md](CENZHI_SETUP.md) — 仅在 **vercel.com/cenzhi** 部署。
