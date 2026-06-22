# Leo Suite (meta)

Three **separate repositories** — one app per repo, one Vercel project per import on **vercel.com/cenzhi**.

**Author:** Liu Cenzhi · [github.com/mentorkokkwa](https://github.com/mentorkokkwa)

---

## The three apps

### YouthMentor AI — Student wellbeing & safety

A safe digital mentor for structured reflection, mood check-in, and crisis guardrails.

- Layered safety: keyword scan → risk classifier → crisis-only UI (no coaching LLM on high risk)
- Voice input on check-in, reflection, and character chat; mood trend chart on history
- Trust metrics and responsible-AI comparison on home page; empathy-first character chat
- Character chat with scenario simulations (labeled as AI)
- Data stays in browser (`localStorage`)

| | |
|--|--|
| **Live demo** | https://leo-suite-growth-swart.vercel.app/youthmentor |
| **Safety walkthrough** | https://leo-suite-growth-swart.vercel.app/youthmentor/safety-demo |
| **Private source** | [leo-suite-growth](https://github.com/mentorkokkwa/leo-suite-growth) |
| **Public showcase** | [leo-suite-growth-showcase](https://github.com/mentorkokkwa/leo-suite-growth-showcase) |

### EduLens AI — Teaching & learning assistant

Structured homework feedback, lesson generation, mistake book, and printable reports.

- Homework analyzer with marking-style JSON feedback and vision OCR
- Lesson generator: 3-part pipeline, staged loading UX, RAG sanitization, output-type filtering
- Shareable lesson reports with localStorage cache; subject-aware diagram rendering
- Multi-provider LLM chain with Zod validation and mock fallback

| | |
|--|--|
| **Live demo** | https://leo-suite-edutech-six.vercel.app/edulens |
| **Homework analyzer** | https://leo-suite-edutech-six.vercel.app/edulens/homework-analyzer |
| **Lesson generator** | https://leo-suite-edutech-six.vercel.app/edulens/lesson-generator |
| **Private source** | [leo-suite-edutech](https://github.com/mentorkokkwa/leo-suite-edutech) |
| **Public showcase** | [leo-suite-edutech-showcase](https://github.com/mentorkokkwa/leo-suite-edutech-showcase) |

### CampusBot AI — School service robot simulator

Client-side school map simulator with A* path planning and task scenarios.

| | |
|--|--|
| **Live demo** | https://leo-suite-robot.vercel.app/campusbot |
| **Simulator** | https://leo-suite-robot.vercel.app/campusbot/simulator |
| **Source (public)** | [leo-suite-robot](https://github.com/mentorkokkwa/leo-suite-robot) |

---

## Repository map

| App | Private deploy | Public showcase | Vercel |
|-----|----------------|-----------------|--------|
| **YouthMentor AI** | [leo-suite-growth](https://github.com/mentorkokkwa/leo-suite-growth) | [leo-suite-growth-showcase](https://github.com/mentorkokkwa/leo-suite-growth-showcase) | leo-suite-growth |
| **EduLens AI** | [leo-suite-edutech](https://github.com/mentorkokkwa/leo-suite-edutech) | [leo-suite-edutech-showcase](https://github.com/mentorkokkwa/leo-suite-edutech-showcase) | leo-suite-edutech |
| **CampusBot AI** | [leo-suite-robot](https://github.com/mentorkokkwa/leo-suite-robot) | same repo (public) | leo-suite-robot |

**Setup:** [docs/PRIVATE_PUBLIC_REPOS.md](docs/PRIVATE_PUBLIC_REPOS.md) · [docs/CENZHI_SETUP.md](docs/CENZHI_SETUP.md)

---

## Portfolio & documentation

| Document | Description |
|----------|-------------|
| [docs/portfolio_full.md](docs/portfolio_full.md) | **Full EduLens portfolio (~10 pages)** — DSA-JC project write-up |
| [docs/PORTFOLIO.md](docs/PORTFOLIO.md) | One-page Leo Suite overview |
| [docs/portfolio-one-pager.html](docs/portfolio-one-pager.html) | Printable one-pager (Save as PDF) |
| [docs/DEMO_SCRIPT.md](docs/DEMO_SCRIPT.md) | Product walkthrough script |
| [docs/ARCHITECTURE.md](docs/ARCHITECTURE.md) | Architecture diagrams (all apps) |
| [docs/PRIVATE_PUBLIC_REPOS.md](docs/PRIVATE_PUBLIC_REPOS.md) | Private deploy + public showcase strategy |
| [docs/DEPLOYMENT.md](docs/DEPLOYMENT.md) | Full Vercel deployment guide |

Per-app docs live in each **showcase** repo (`docs/product_overview.md`, `docs/safety_design.md`, etc.).

---

## Local dev (this folder)

If you keep a combined workspace on disk, run each app from its subfolder:

```bash
cd growth
npm install
npm run dev
```

```bash
cd edutech
npm install
npm run dev
```

```bash
cd robot
npm install
npm run dev
```

| App | Port | URL |
|-----|------|-----|
| YouthMentor | 3007 | http://localhost:3007/youthmentor |
| EduLens | 3006 | http://localhost:3006/edulens |
| CampusBot | 3002 | http://localhost:3002/campusbot |

---

## Showcase templates

Push to GitHub as public portfolio repos:

```
showcase/leo-suite-growth-showcase/
showcase/leo-suite-edutech-showcase/
showcase/init-showcase-repos.ps1
```

---

## License

MIT — see [LICENSE](LICENSE).
