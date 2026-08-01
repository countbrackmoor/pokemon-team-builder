# Changelog

All notable changes to this project are documented here.
Format based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).

## [1.3.0] - 2026-07-31

### Changed
- Renamed the tool from "Team Builder" to "PokéTeamer" (page title and in-app header). Repo name and live URL (`/pokemon-team-builder/`) unchanged for link stability.
- Moved the hub listing from the Productivity Apps section (small-card) to the Game Apps section (full project-card), matching the treatment given to the NMS Codex and Horrified toolkit.

## [1.2.1] - 2026-07-31

### Fixed
- **Scarlet mode was showing the Shield roster.** Availability was derived with `game[0]`, but "Shield" and "Scarlet" both start with "S", so Scarlet resolved to the Shield code. In Scarlet the search box, the suggestion pool, and the availability flag all used Shield data — Scarlet-only Pokémon (e.g. Gholdengo) were wrongly flagged "not available in Scarlet", and Shield-only ones (e.g. Suicune, Arctozolt) were wrongly offered. Replaced with an explicit `GAME_CODE` lookup (`Shield: "S"`, `Scarlet: "R"`) used by all three call sites. The opponent dropdown was unaffected, as it keys off the full game name.

## [1.2.0] - 2026-07-31

### Added
- Plain-English summary card at the top of the Coverage, Matchup, and Suggestions tabs.
- Each card is split into two labelled blocks: **What the numbers say** (factual, derived directly from the type math) and **What I'd do** (explicitly marked as opinion, not fact).
- Fixed severity vocabulary shown as a coloured badge on each card: `CRITICAL` / `NOTABLE` / `MINOR` / `CLEAN`.

### Changed
- Pokémon roster extracted into `pokedex.js` using a compact encoding. Regenerating the dex from the source spreadsheet no longer requires touching app code.

### Notes
- Summaries are rule-based and deterministic — no LLM call, no network request, no API key. Consistent with the tool's no-backend design.
- Coverage severity weighs both defensive holes and offensive gaps, so a team with no weaknesses but several uncovered types is no longer mislabelled as `CLEAN`.

## [1.1.0] - 2026-07-31

### Added
- Light/dark mode toggle (top right of header).
- "Not available in {game}" flag for team slots when switching between Shield and Scarlet, instead of clearing the team.

### Changed
- Switching between Shield and Scarlet no longer clears the selected team. Only the selected opponent resets (rosters are game-specific).
- Pokémon invalid for the currently selected game are excluded from coverage/matchup/suggestion analysis until removed or the game is switched back.
- Full roster (949 entries) sourced from spreadsheet data instead of a hand-picked subset, including previously-missing Dynamax Adventure–exclusive legendaries (Suicune, Raikou, Entei, Mewtwo, Lugia, Ho-Oh, Kyogre, Groudon, Rayquaza, the lake trio, Dialga, Palkia, Giratina, Heatran, Cresselia, Regigigas, the Forces of Nature, Reshiram, Zekrom, Kyurem, Xerneas, Yveltal, Zygarde, the Tapus, Solgaleo, Lunala, Necrozma, and the Ultra Beasts).

## [1.0.0] - 2026-07-31

### Added
- Initial release: type coverage analyzer, gym/E4/Champion matchup checker, and gap-based team suggestion engine for Pokémon Shield and Scarlet.
- Deployed as a standalone single-file HTML page (React + Babel Standalone via CDN, no build step).
