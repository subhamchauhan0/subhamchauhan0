# External Statistics Widgets & Asset Catalog

All widgets used in `README.md` are configured with the dark Berserk palette:
- **Background:** `#0B0B0B` (Void black)
- **Borders:** `#444444` (Steel gray)
- **Titles & Labels:** `#D6C6A5` (Aged parchment)
- **Body & Subtext:** `#A0A0A0` (Ash gray)
- **Rings, Fires & Accent Marks:** `#8B0000` / `#DC2626` (Crimson)

---

## 1. Verified Live Widget URLs

| Widget | Service Provider | Live Endpoint & Parameters | Status |
| :--- | :--- | :--- | :--- |
| **Streak Stats Card** | `github-readme-streak-stats` | `https://streak-stats.demolab.com/?user=subhamchauhan0&theme=dark&background=0B0B0B&border=444444&stroke=444444&ring=8B0000&fire=8B0000&currStreakLabel=D6C6A5&sideLabels=A0A0A0&dates=A0A0A0` | **200 OK** |
| **LeetCode Stats Card** | `leetcard.jacoblin.cool` | `https://leetcard.jacoblin.cool/Subham_chauhan?theme=dark&font=JetBrains%20Mono&ext=heatmap` | **200 OK** |
| **Contribution Snake** | `Platane/snk` (GitHub Action) | `https://raw.githubusercontent.com/subhamchauhan0/subhamchauhan0/output/github-snake-crimson.svg` | **200 OK** (updated via `.github/workflows/snake.yml` on `master`) |

*(Note: `github-readme-stats.vercel.app` cards were removed per the audit brief because the upstream repository is no longer maintained and its public Vercel instance is best-effort.)*

---

## 2. Local Visual Assets

| Asset Path | Resolution / Type | Format | Purpose |
| :--- | :--- | :--- | :--- |
| `assets/banner.svg` | `1200 × 340` viewBox (Animated) | SVG | Animated Berserk hero name card with pulsing crimson eclipse, floating embers, and typing motto |
| `assets/github-banner.png` | `1280 × 400` px (Static fallback) | PNG | High-resolution static PNG banner |
| `assets/berserk-divider.png` | `900 × 16` px (Optional) | PNG | Minimalist steel gray divider with crimson center and Brand diamond motif |
