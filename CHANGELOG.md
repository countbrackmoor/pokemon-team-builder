# Changelog

All notable changes to this project are documented here.
Format based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).

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
