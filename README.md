# Phoney Patrol

A Scrabble challenge drill. Your opponent plays a word: let it stand, or challenge it?
About 5,700 words: real entries from the official North American tournament
dictionary (NWL2023) mixed with convincing forgeries, plus all 676 two-letter combinations.

## Features
- Drill by starting letter, all words, or **2s** (two-letter words only)
- Per-session accuracy, streak, and a list of the words that beat you, with definitions
- Two-letter cheat sheet: the 107 valid twos, grouped by first letter
- Keyboard: `G` good · `P` phoney · `Enter` next

## Running it
It is a single self-contained file. Open `index.html` in a browser, or serve it with
GitHub Pages (Settings → Pages → deploy from `main`, root folder).

## Saved stats and leaderboard
All storage code lives in one block in `index.html`: search for `STORE`.

- **On claude.ai** (the hosted artifact), stats save to the artifact's database and a
  leaderboard ranks players by overall accuracy (minimum 50 words judged) and best streak.
- **Anywhere else** (GitHub Pages, local file), the game runs normally and saves your
  all-time stats in this browser only. The leaderboard shows a note instead of rankings.

### Roadmap: Supabase backend
Planned on a `supabase` branch: replace `STORE`'s four functions
(`init`, `load`, `save`, `watchBoard`) with Supabase calls, add sign-in, and protect the
`scores` table with Row Level Security so each player can only write their own row.

**Security notes**
- The Supabase **anon** key is public by design and may appear in `index.html`.
- The **service_role** key bypasses all security. Never commit it (see `.gitignore`).
- Row Level Security must be enabled before the leaderboard goes live.

## Word list
Valid words and definitions follow the NASPA Word List 2023 (NWL2023).
