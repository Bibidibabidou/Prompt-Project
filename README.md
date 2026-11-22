# Reality Check

**How good are your guesses?**

A mobile-first guessing game about women in Swiss tech. Players guess real figures from the *Women in Tech Index* report, say how sure they are, and see how close they were. It's for students aged 14–18 choosing between a Matura focus and an apprenticeship, and it also works as a 10-minute classroom activity.

> Educational prototype by a student team (PROMPT H26). Not official HSLU or Women in Tech Index communication.

**Live version:** `https://<your-username>.github.io/<repo-name>/` *(update after publishing)*

---

## How to play

1. Read the question.
2. Set your guess between 0 and 100%.
3. Say how sure you are: **Not sure**, **Kinda** or **Very sure**.
4. Lock it in and see how close you were.

There are 12 rounds in three stages: **School → Studies → Workforce**. A game takes about 10 minutes.

## Features

- **Honest scoring:** you earn XP for being close *and* for being honest about how sure you are.
- **Six feedback levels:** each has its own headline, animation and sound, from *Bullseye!* to *Mega plot twist!*
- **XP and levels:** no streaks, timers, lives, purchases or rankings of classmates.
- **Class mode:** the teacher types in the guesses students call out (numbers only, no names). They appear as anonymous dots next to the real figure.
- **Word help:** terms like Matura, ICT and percentage points are explained in speech bubbles the first time they appear.
- **Sources:** every result shows the report section, page and year.
- **One file:** the whole game is a single `index.html`, with no build step and no server.

## Run it locally

Open `index.html` in any modern browser. You need an internet connection for the fonts (Google Fonts). Without one, the game still works with system fonts.

## Publish with GitHub Pages

1. Put `index.html` in the root of the repository.
2. Go to **Settings → Pages**.
3. Set Source to **Deploy from a branch**, Branch to `main`, and folder to `/ (root)`.
4. After a minute or two the site is live at `https://<your-username>.github.io/<repo-name>/`.

To update the site, commit a new `index.html`.

## Editing the game

Everything you're likely to change sits at the top of the `<script>` in `index.html`.

| What | Where | Notes |
|---|---|---|
| Questions and figures | `ROUNDS` | Each round has `q`, `answer`, `year`, `source`, `explanation`, `misconception`, `caveat`, `path`, `terms`. Never add a figure that isn't in the checked fact bank. |
| Scoring | `SCORING` | `CLOSE_WITHIN` (percentage points), the points for each confidence level, `XP_PER_LEVEL`, the badge rule. These are starting values for playtesting, not final. |
| Feedback levels | `TIERS` | Distance ranges, headlines, animation (`fx`) and sound (`snd`) for each level. |
| Word help | `TERMS` | The speech-bubble definitions. |
| Missing years | `YEAR_PLACEHOLDER` | Shown wherever the fact bank has no year (currently RC-12). |

### Current scoring

| How sure | Close (≤ 5 pp) | Far off |
|---|---|---|
| Very sure | +100 | +0 |
| Kinda | +80 | +15 *(placeholder)* |
| Not sure | +60 | +30 |

## Brand

These values come from the *Reality Check* brand guide (Proposal D).

- **Colours:** Matura violet `#6C4BFF`, Apprenticeship lime `#C6F432`, Honest sky `#7FD6FF` (only for the "how sure?" control), Surprise coral `#FF8A5B`, Ink `#121212`, Cloud `#EEF0FA`. For small text in path colours: `#5A3BE8` (Matura) and `#3F6600` (apprenticeship).
- **Fonts:** Bagel Fat One for headlines, scores and buttons; Geist for reading text; Geist Mono for codes and source lines.
- **Shapes:** rounded "jelly" tiles with a 3px ink outline and a hard shadow. No gradients or glow.
- **Paths:** both paths always appear at the same size. The game never calls one path better.

## Accessibility

- Text colours meet WCAG AA contrast, and reading text is at least 18px.
- Tap targets are at least 48px, and the game uses real `<button>`, `<label>` and radio elements.
- Colour is never the only clue: results always include a text label.
- Animations switch off when the device asks for reduced motion.
- Sound can be turned off at the top of the page, and the choice is remembered on that device.
- If Bagel Fat One can't draw ä ö ü é è à, words with those letters switch to Geist ExtraBold.

## Data and sources

All figures come from the **Women in Tech Index Preliminary Study** (Lucerne University of Applied Sciences and Arts, August 2026). They are taken from the team fact bank (freeze date 16 November 2026). Every figure has been checked by a second team member; **final approval is pending**.

Limits of the data:

- The report records gender as binary, women and men (Appendix B.1).
- "ICT occupation" (people in ICT jobs) and "ICT sector" (everyone at ICT companies) measure different things.
- Pipeline figures compare different groups of people at each stage, not one group followed over time (Appendix B.7).

## Privacy

No accounts, no tracking and no personal data. Class guesses stay in the browser and are gone when the page closes. The game only saves the sound on/off setting, on the player's own device.

## AI disclosure

The fact bank was drafted with an AI model from the report and checked by the team. Question texts, explanations and misconceptions were drafted with an AI model from that fact bank, then checked by the team. The game code was written with AI assistance. No AI runs while you play.

## Team

PROMPT H26 student team: *[add names]*

## License

*[add a license, or "All rights reserved"]*
