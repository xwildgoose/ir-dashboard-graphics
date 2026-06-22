# IR Dashboard Graphics

Static HTML graphics embedded in the **University of The Bahamas enrolment dashboard** (Power BI), via the **HTML Content** custom visual. Each file is a self-contained page showing a chatbot teaser and a button; clicking the button (or the chat card) opens the **Ask Institutional Research** chatbot in a new browser tab.

Hosted free on GitHub Pages. Live root: https://xwildgoose.github.io/ir-dashboard-graphics/

## Files

| File | Dashboard visual | Measure name | Visual size (W×H) | iframe height |
|------|------------------|--------------|-------------------|---------------|
| `home_page.html` | Home page chatbot card | `Chatbot` | 574 × 398 | 385px |
| `help_page.html` | Help Center hero (replaces the campus photo) | `Chatbot_Help Page` | 1074 × 300 | 282px |

Live URLs:
- https://xwildgoose.github.io/ir-dashboard-graphics/home_page.html
- https://xwildgoose.github.io/ir-dashboard-graphics/help_page.html

## How to update (≈ once a year)

1. Open the repo, click the file, then the **pencil icon** to edit it.
2. Make the change (e.g. bump "Fall 2025" → "Fall 2026" in the prompts).
3. Scroll down and click **Commit changes**.
4. Wait 1–2 minutes for GitHub Pages to rebuild.
5. **Hard-refresh** (Ctrl+F5) or open in a private window to verify — a normal refresh may show a cached old version. This is the #1 thing that causes "did my change work?" confusion.

Power BI picks up the new version automatically on the next report refresh — no measure edits needed. The measure points at the file's URL, so the URL is the constant and only the file's contents change.

## Good to know

- **iframe heights live in the measures, not the HTML.** They're set a few px under the visual size to avoid a scrollbar; that gap is the visual's internal padding, so it doesn't change when the page content does. If you resize a visual, re-nudge its height.
- **Chatbot:** FastBots, embed ID `cm8t8wiq100fws5k4x4wrke3l`. The live bot opens in a **new tab** because it can't run inside Power BI's sandbox — so these pages are teasers/launchers, not the bot itself.
- **Logo:** the UB IR shield is base64-embedded directly in each file, so each page is a single self-contained file with no separate image to manage.
- **Help page** also includes an email link: requestinfo@ub.edu.bs.
- **Spelling:** "enroled" / "enrolment" (British, matching the bot's wording). Keep it consistent when editing.

## Don'ts

- **Don't rename either file to `index.html`.** The measures point at the named paths, and the distinct names keep the two pages from colliding.
- **Keep this repo public** (free GitHub Pages requires it), but put **only these HTML files** here — no data extracts or internal notes. The repo and the pages are publicly viewable. The pages themselves contain no enrolment data, only the teaser and links.
