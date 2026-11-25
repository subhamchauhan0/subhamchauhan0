# External Statistics Widgets & Asset Catalog

All widgets used in the `README.md` have been configured with the dark Berserk palette:
- **Background:** `#0B0B0B` (Void black)
- **Borders:** `#444444` (Steel gray)
- **Titles & Labels:** `#D6C6A5` (Aged parchment)
- **Body & Subtext:** `#A0A0A0` (Ash gray)
- **Rings, Fires & Accent Marks:** `#8B0000` (Crimson / Blood red)

---

## 1. Verified Live Widget URLs

| Widget | Service Provider | Live Endpoint & Parameters | HTTP Status |
| :--- | :--- | :--- | :--- |
| **GitHub Readme Stats** | `github-readme-stats` | `https://github-readme-stats.vercel.app/api?username=subhamchauhan0&show_icons=true&bg_color=0B0B0B&title_color=D6C6A5&text_color=A0A0A0&icon_color=8B0000&border_color=444444` | **200 OK** |
| **Top Languages Card** | `github-readme-stats` | `https://github-readme-stats.vercel.app/api/top-langs/?username=subhamchauhan0&layout=compact&bg_color=0B0B0B&title_color=D6C6A5&text_color=A0A0A0&border_color=444444` | **200 OK** |
| **Streak Stats Card** | `github-readme-streak-stats` | `https://streak-stats.demolab.com/?user=subhamchauhan0&theme=dark&background=0B0B0B&border=444444&stroke=444444&ring=8B0000&fire=8B0000&currStreakLabel=D6C6A5&sideLabels=A0A0A0&dates=A0A0A0` | **200 OK** |
| **LeetCode Stats Card** | `leetcard.jacoblin.cool` | `https://leetcard.jacoblin.cool/shubbu?theme=dark&font=JetBrains%20Mono&ext=heatmap` | **200 OK** |
| **Contribution Snake** | `Platane/snk` (GitHub Action) | `https://raw.githubusercontent.com/subhamchauhan0/subhamchauhan0/output/github-snake-crimson.svg` | Generated on push via `.github/workflows/snake.yml` |

---

## 2. Local Visual Assets

| Asset Path | Resolution / Type | Format | Purpose |
| :--- | :--- | :--- | :--- |
| `assets/banner.svg` | `1200 × 340` viewBox (Animated) | SVG | Animated Berserk hero name card with pulsing crimson eclipse, floating embers, and typing motto |
| `assets/github-banner.png` | `1280 × 400` px (Static fallback) | PNG | High-resolution static PNG banner |
| `assets/berserk-divider.png` | `900 × 16` px | PNG | Minimalist steel gray divider with crimson center and Brand diamond motif |

---

## 3. Fallback Notes

- All widgets are rendered as SVGs over HTTPS and cached by GitHub's Camo proxy.
- If any third-party service experiences downtime in the future, the README structure retains full layout integrity because text and project architecture sections do not depend on external iframes or scripts.

