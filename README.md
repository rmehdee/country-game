# 🌍 Guess the Country

A responsive, mobile-friendly flag-guessing game. Name the country from its flag across **5 levels** of **10 questions each** — flags start famous (Level 1) and get progressively more obscure (Level 5).

- Pure static site — one `index.html`, no build step, no dependencies.
- Multiple choice · 3 lives per level · score 7/10 to advance.
- Progress is saved in the browser (`localStorage`).

## Run locally

Just open `index.html` in a browser, or serve it:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Deploy to GitHub Pages (countrygame.mehdee.com)

1. **Create the repo & push**
   ```bash
   cd country-game
   git init
   git add .
   git commit -m "Guess the Country game"
   git branch -M main
   git remote add origin git@github.com:<your-username>/country-game.git
   git push -u origin main
   ```

2. **Enable Pages** — GitHub repo → **Settings → Pages** → *Build and deployment* → Source: **Deploy from a branch**, Branch: **main / (root)**. Save.

3. **Custom domain** — the included `CNAME` file already sets `countrygame.mehdee.com`. In the same Pages screen it should appear under *Custom domain*. Tick **Enforce HTTPS** once the certificate is issued.

4. **DNS (at your mehdee.com registrar)** — add a **CNAME record**:
   | Type  | Name          | Value                          |
   |-------|---------------|--------------------------------|
   | CNAME | `countrygame` | `<your-username>.github.io`    |

   DNS + certificate can take a few minutes to an hour to go live.

## Customize

All game data and settings live in `index.html`:
- `COUNTRIES` — add/edit countries (`t` = difficulty tier 1–5, `c` = continent for smarter wrong-answer options).
- `QUESTIONS_PER_LEVEL`, `MAX_LEVEL`, `PASS_MARK`, `STARTING_LIVES` — tune the rules at the top of the `GAME CONFIG` section.
