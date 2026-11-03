<div align="center">

<img src="assets/hero.png" alt="Student Pulse" width="100%" />

# 🎓 Student Pulse

### Academic intelligence dashboard — real-time GPA, attendance & risk analytics

<p>
  <a href="https://shhoryaaa.github.io/student-pulse/">
    <img src="https://img.shields.io/badge/▶_Live_Demo-090d18?style=for-the-badge&logo=githubpages&logoColor=5eead4" alt="Live Demo" />
  </a>
  <img src="https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white" alt="HTML5" />
  <img src="https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white" alt="CSS3" />
  <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black" alt="JavaScript" />
  <img src="https://img.shields.io/badge/Chart.js-FF6384?style=for-the-badge&logo=chartdotjs&logoColor=white" alt="Chart.js" />
  <img src="https://img.shields.io/badge/GitHub_Pages-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub Pages" />
  <img src="https://img.shields.io/badge/License-MIT-34d399?style=for-the-badge" alt="License" />
</p>

**A single-file, zero-dependency dashboard that turns student data into decisions.**

<p>
  <a href="https://shhoryaaa.github.io/student-pulse/"><b>🚀 Live Demo</b></a> ·
  <a href="#-screenshots"><b>📸 Screenshots</b></a> ·
  <a href="#-project-pipeline"><b>🏗 Pipeline</b></a> ·
  <a href="#-features"><b>⚡ Features</b></a> ·
  <a href="#-quick-start"><b>⚡ Quick Start</b></a>
</p>

</div>

---

## 📸 Screenshots

<div align="center">

### 🎯 Hero View
<img src="assets/hero.png" alt="Hero view" width="100%" />

### 📊 Full Page
<img src="assets/full.png" alt="Full dashboard" width="100%" />

<table>
<tr>
<td width="50%"><img src="assets/kpis.png" alt="KPI cards"/></td>
<td width="50%"><img src="assets/table.png" alt="Student roster"/></td>
</tr>
<tr>
<td align="center"><sub><b>KPI cards</b> — students · GPA · attendance · risk</sub></td>
<td align="center"><sub><b>Roster</b> — searchable, sortable, live progress</sub></td>
</tr>
</table>

</div>

---

## ⚡ Features

<table>
<tr>
<td width="50%" valign="top">

### 📊 Analytics
- **Live KPIs** — students, GPA, attendance, at-risk count
- **Trend chart** — 8-week dual-axis GPA + attendance
- **Grade donut** — animated distribution with legend
- **Subject bars** — per-subject averages
- **Weekly engagement** — Mon–Fri activity
- **Color-coded grades** — A · B · C · D pills

</td>
<td width="50%" valign="top">

### 🎛 Interaction
- **Searchable roster** — live filter by name
- **Add student modal** — instant KPI recalc
- **CSV export** — dated filename
- **Theme toggle** — light ⇄ dark
- **Toast notifications** — non-blocking feedback
- **Responsive** — mobile, tablet, desktop

</td>
</tr>
</table>

### 🎨 Design System

| Token | Value | Purpose |
|-------|-------|---------|
| `--bg` | `#090d18` | Deep-space background |
| `--panel` | `#121d2c` | Card surface |
| `--cyan` | `#5eead4` | Primary accent |
| `--violet` | `#a78bfa` | Secondary accent |
| `--amber` | `#fbbf24` | Warning state |
| `--rose` | `#fb7185` | Danger state |
| `--green` | `#34d399` | Success state |

Typography: **Space Grotesk** (headings) · **DM Sans** (body) · **DM Mono** (data)

---

## 🏗 Project Pipeline

```
┌─────────────────────────────────────────────────────────────────────────┐
│                         STUDENT PULSE PIPELINE                          │
└─────────────────────────────────────────────────────────────────────────┘

   ┌──────────┐     ┌──────────┐     ┌──────────┐     ┌──────────┐
   │ 1. Author│────▶│ 2. Push  │────▶│  3. CI   │────▶│ 4. Deploy│
   │  Colab   │     │  GitHub  │     │ Actions  │     │  Pages   │
   └──────────┘     └──────────┘     └──────────┘     └──────────┘
        │                │                 │                │
        ▼                ▼                 ▼                ▼
   ┌──────────┐     ┌──────────┐     ┌──────────┐     ┌──────────┐
   │Playwright│     │  Assets  │     │  HTML    │     │   LIVE   │
   │Screenshots     │ + README │     │ Validate │     │   URL    │
   └──────────┘     └──────────┘     └──────────┘     └──────────┘
```

| # | Stage | Tool | What happens |
|---|-------|------|--------------|
| **1** | Author | Google Colab | Write HTML/CSS/JS in one cell |
| **2** | Capture | Playwright · 2× DPI | Screenshot 4 views |
| **3** | Commit | GitHub Contents API | Upload everything |
| **4** | CI | GitHub Actions | Validate + deploy |
| **5** | Deploy | GitHub Pages | Live URL |
| **6** | Document | Auto README | Badges + shots + roadmap |

### CI workflow

```yaml
name: Deploy Student Pulse
on:
  push:
    branches: [main]
  workflow_dispatch:
permissions:
  contents: read
  pages: write
  id-token: write
jobs:
  deploy:
    runs-on: ubuntu-latest
    environment:
      name: github-pages
    steps:
      - uses: actions/checkout@v4
      - run: test -f index.html && grep -q "Student Pulse" index.html
      - uses: actions/configure-pages@v5
      - uses: actions/upload-pages-artifact@v3
        with:
          path: .
      - uses: actions/deploy-pages@v4
```

---

## 🚀 Quick Start

👉 **[Open the dashboard](https://shhoryaaa.github.io/student-pulse/)**

```bash
git clone https://github.com/shhoryaaa/student-pulse.git
cd student-pulse
python -m http.server 8000
```

> No build step. No `npm install`. Just `index.html`.

---

## 🧱 Tech Stack

| Layer | Choice |
|-------|--------|
| Markup | HTML5 |
| Styling | Vanilla CSS |
| Charts | [Chart.js 4.4](https://www.chartjs.org/) |
| Fonts | Space Grotesk · DM Sans · DM Mono |
| Screenshots | Playwright (2× DPI) |
| Hosting | GitHub Pages |
| CI/CD | GitHub Actions |

**Shipped size: ~45 KB** — smaller than one Instagram photo.

---

## 📂 Structure

```
.
├── index.html
├── README.md
├── LICENSE
├── assets/
│   ├── hero.png
│   ├── full.png
│   ├── kpis.png
│   └── table.png
└── .github/workflows/deploy.yml
```

---

## 🗺 Roadmap

- [x] **v0.1** — KPIs · 4 charts · search · modal · CSV · theme
- [x] **v0.2** — Auto-screenshot pipeline
- [x] **v0.3** — GitHub Pages + CI
- [x] **v1.0** — Polished README · assets · MIT
- [ ] **v1.1** — Supabase backend
- [ ] **v1.2** — Auth roles
- [ ] **v1.3** — PDF reports
- [ ] **v1.4** — AI risk insights
- [ ] **v1.5** — Mobile PWA
- [ ] **v2.0** — i18n

---

## 🤝 Contributing

```bash
git checkout -b feat/your-feature
git commit -m "feat: add your feature"
git push origin feat/your-feature
```

Commit prefixes: `feat:` · `fix:` · `docs:` · `ci:` · `assets:` · `chore:`

---

## 📜 License

MIT © 2026 Student Pulse contributors

---

<div align="center">

**Built with ☕ and cyan gradients.**

[⬆ Back to top](#-student-pulse) · [🚀 Live Demo](https://shhoryaaa.github.io/student-pulse/) · [📦 Repo](https://github.com/shhoryaaa/student-pulse)

<sub>⭐ Star if this helped!</sub>

</div>