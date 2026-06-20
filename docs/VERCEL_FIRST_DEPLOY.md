# Vercel 部署（cenzhi 账号）

**Dashboard：** https://vercel.com/cenzhi

三个 app 各一个 GitHub 仓库 → Vercel Import 一次 → **Root Directory 留空**。

| Vercel 项目 | GitHub |
|-------------|--------|
| leo-suite-growth | mentorkokkwa/leo-suite-growth |
| leo-suite-edutech | mentorkokkwa/leo-suite-edutech |
| leo-suite-robot | mentorkokkwa/leo-suite-robot |

完整清单（含环境变量）：见 **[CENZHI_SETUP.md](CENZHI_SETUP.md)**。

## 入口 URL

部署完成后：

| App | 路径 |
|-----|------|
| YouthMentor | `/` 或 `/youthmentor` |
| EduLens | `/` 或 `/edulens` |
| CampusBot | `/` 或 `/campusbot` |

域名以 cenzhi Dashboard 中 **Production** 域名为准（例如 `leo-suite-growth-*.vercel.app`）。

## 环境变量摘要

- **robot**：无
- **growth / edutech**：见各仓库 `.env.example` 与 [CENZHI_SETUP.md](CENZHI_SETUP.md)
- API key **只在 Vercel Dashboard 设置**，不要写入 GitHub
