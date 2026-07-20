# 🌍 Guess the Country

A responsive, mobile-friendly flag-guessing game for kids. Name the country from its flag across **20 levels** covering **all 195 countries** in the world. Flags start famous (Level 1) and get progressively more obscure. Beat all 20 levels to become a **World Flag Master**.

- Pure static site: one `index.html`, no build step, no dependencies.
- Multiple choice, 3 hearts per level, score 70% to advance.
- Big kid-friendly feedback, sound effects, confetti, and read-you-the-answer banners.
- Progress is saved in the browser (`localStorage`).
- 195 countries = 193 UN members + Vatican City + Palestine, grouped into 5 difficulty bands (Beginner, Explorer, Adventurer, Expert, Legend).

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
