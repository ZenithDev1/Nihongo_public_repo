# NihongoHera — Japanese Kana Dojo

A beginner-first React + Tailwind frontend prototype for learning the 46 basic Hiragana and 46 basic Katakana characters.

## What is included

- Neo-Edo / washi-inspired visual design with light and dark themes.
- Standard printed kana forms only (no cursive handwriting forms).
- Full Hiragana and Katakana gojūon charts with optional Devanagari hints.
- Zero-signup five-vowel romaji warm-up embedded in the landing-page hero, using the learner's physical keyboard only.
- Completion state and sign-up prompt after five correct answers; the session does not auto-restart.
- Mnemonic character card and right-side toast notifications for correct answers and audio placeholders.
- Quiz, look-alike comparison (including わ / れ / ね), dashboard mock progress, micro-reading reward modal, basic learning tools and character detail routes.
- Login, signup and three-stage forgot-password UI (email → OTP → new password).
- A dedicated developer/feedback section on the homepage, plus GitHub and email links in the footer.

## Requirements

- Node.js 18+ (Node 20+ recommended)
- npm

## Run locally

```bash
npm install
npm run dev
```

Vite will print a local URL, normally `http://localhost:5173`.

## Production build

```bash
npm run build
npm run preview
```

## Main routes

- `/` — landing page, 5-kana onboarding and full alphabet section.
- `/learn` — full kana library, row filter, mnemonic card and Hindi hints.
- `/learn/hiragana-ko` (example) — individual character lesson.
- `/dashboard` — mock mastery map, review mix and micro-reading reward.
- `/practice` — kana multiple-choice quiz.
- `/confusion` — look-alike character practice.
- `/tools` — romaji converter, Katakana name seal and downloadable SVG practice sheet.

## Backend integration points

This repository is a frontend prototype. The following flows are UI-only and must be connected to secure backend endpoints:

- `POST /api/health` — this endpoint is to check is system running into the production.


In `src/pages/AuthPage.jsx`, the OTP verification handler currently advances the prototype to the new-password screen after a six-digit value is entered. Replace that transition with the result of the real verification API. Never trust client-side OTP state or store raw OTP secrets in the browser.

The speaker button intentionally shows a “coming soon” notification. No audio playback is implemented.

## Notes

- The 46+46 charts show the basic modern kana set. Dakuten, handakuten, small kana and combinations are intentionally deferred until learners know the foundations.
- Devanagari hints are approximations, not exact phonetic equivalents.
- The name-to-Katakana utility is a playful approximation. Foreign names can have multiple acceptable Katakana spellings.
- The dashboard uses local mock data; authentication, persistent progress, analytics, payments, spaced repetition scheduling and real audio need backend/service integration.
