# Team Builder

Type coverage, matchup, and gap-suggestion tool for Pokémon Shield & Scarlet teams.

**Live:** [gorgon.live/pokemon-team-builder](https://gorgon.live/pokemon-team-builder/)

## What it does

- **Coverage** — pick up to 6 Pokémon and see full defensive (incoming attack) and offensive (STAB) type coverage.
- **Matchup** — select a Shield or Scarlet gym leader / Elite Four / Champion and see per-Pokémon matchup breakdowns with a recommended lead.
- **Suggestions** — ranks available Pokémon by how well they patch your team's defensive weaknesses and offensive gaps, with one-click add.

Each tab opens with a plain-English summary card, split into **What the numbers say** (factual) and **What I'd do** (explicitly marked as opinion). Summaries are rule-based and deterministic — no LLM call, no network request.

Switching between Shield and Scarlet keeps your team intact. Any Pokémon not available in the newly selected game is flagged (not cleared) and excluded from analysis until removed or the game is switched back.

## Stack

Single-file HTML page. React + Babel Standalone loaded via CDN (`unpkg.com`) — no build step, no backend. All data (Pokémon roster, type chart, opponent rosters) is embedded client-side.

## Data source

Pokémon roster and typing pulled from a maintained spreadsheet (Shield: Galar/Isle of Armor/Crown Tundra dexes; Scarlet: Paldea/Kitakami/Blueberry dexes, plus Crown Tundra Dynamax Adventure legendaries). Opponent gym/E4/Champion rosters are hand-compiled and not independently verified against a live source — treat as a solid approximation, not gospel.

## Status

Work in progress. Offensive analysis is STAB-only (no moveset awareness yet). Base stats, abilities, and held items aren't factored into suggestions or summaries. Opponent rosters should be spot-checked before relying on them for a real playthrough decision.
