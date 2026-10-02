# Palpedia+

**Palpedia+** is an unofficial, expanded and searchable encyclopedia for **Palworld**, designed to provide substantially more practical information than the standard in-game Paldeck.

The current version targets **Palworld PS5 v1.0.5** and uses live structured data sources rather than embedding a fixed, potentially outdated Pal database.

## Features

### Expanded Pal encyclopedia

Browse and search the current structured Pal roster with information including:

- Paldeck number
- Element(s)
- Base HP, Attack and Defense coefficients
- Movement and mount information
- Work suitability
- Partner Skills and effects
- Drops
- Ranch production
- Wild-spawn information
- Alpha/boss locations
- Obtain methods
- Natural active skills
- Skill Fruit candidates
- Passive Skill recommendations

Pals can be filtered by element, mount type and work suitability, and sorted by Paldeck number, name, HP, Attack, Defense or ride sprint speed.

### Detailed Pal profiles

Selecting a Pal opens an expanded profile containing its combat, utility, movement, location, breeding and skill information.

The profile explains condensation effects from 0★ through 4★. Condensation is treated as a combat-stat multiplier rather than as a change to the Pal's underlying species coefficients, and Work Suitability upgrades are handled separately.

### Stat calculator

Palpedia+ includes an expanded individual Pal build calculator for estimating permanent HP, Attack and Defense. The calculator currently supports:

- Pal species HP, Attack and Defense coefficients
- Level from 1–80
- Separate HP, Attack and Defense Potential / IV values from 0–100
- Condensation from 0★ through 4★
- Pal Soul enhancement levels from 0–20 for HP, Attack, Defense and Work Speed
- Up to four Passive Skills, with duplicate passives prevented
- Species-specific Trust / Friendship stat parameters
- Alpha HP scaling where supported by the current data
- Work Suitability changes from condensation
- Applied Technique book increases to Work Suitability

The calculator preserves separate modifier classes rather than collapsing them into a single percentage. Potential affects the relevant level-scaled component, intermediate values are truncated at the appropriate stages, and permanent Soul, passive and condensation modifiers are applied separately. Work Speed modifiers from Souls and Passive Skills are likewise compounded rather than simply added together.

#### Awakening limitation

**Awakening is not included in the calculated stats.**

Palworld v1.0 introduced the World Tree Awakening system, but the exact HP, Attack and Defense calculation has not yet been established with enough confidence for Palpedia+ to present an Awakening result as mathematically authoritative. Available technical/community implementations currently disagree about the exact formula and rounding/order of operations.

Until the mechanic can be verified reliably, Palpedia+ deliberately excludes Awakening from its stat results rather than presenting an uncertain estimate as exact. Partner Skill-specific stat effects, food bonuses and temporary party/base effects are also outside the current calculator.

### Breeding tools

The breeding section provides two lookup modes:

1. Enter two parents to find their offspring.
2. Select a target Pal to find parent combinations capable of producing it.

The app is designed to use the current breeding pair table, including gender-specific outcomes where supplied by the source data.

### Passive Skill library

A searchable Passive Skill database displays:

- Passive name
- Effect
- Tier
- Category
- Breedability where available
- World Tree designation where supplied

Pal profiles also provide role-based passive candidates based on whether the Pal is primarily relevant to combat, mounting or high-level work suitability.

### Skills and recommendations

Natural learnsets include available information such as:

- Unlock level
- Element
- Power
- Cooldown
- Range
- Skill Fruit availability
- Skill description
- Community-measured DPS where data is available

Recommended natural skills use an explainable power/cooldown heuristic with same-element skills used as a tie-breaker. These recommendations are guidance rather than an official tier list or a complete combat simulation.

## Data and methodology

Palpedia+ currently loads structured data at runtime from external sources. This keeps the web app lightweight and allows its core dataset to follow maintained upstream data instead of shipping a frozen copy.

Current sources used by the application include:

- **Pocketpair / Steam** for official Palworld update information
- **PalDB** for version/update reference information
- **beliarance/palworld-kb** for structured Pal stats, Partner Skills, work suitability, drops, regions, locations, active skills and passives
- **PalworldBreeding.gg** for the primary breeding table and breeding methodology
- **JohnnyDalvi/Palworld_Smart_Breeder** as the fallback breeding-data source
- **Palworld Wiki** for documented stat and condensation mechanics
- **oMaN-Rod/palworld-save-pal** for extracted species-specific Friendship / Trust parameters
- **deafdudecomputers/PalworldSaveTools** as a technical cross-reference for current stat-formula and rounding behaviour

See the **Sources & methodology** section inside Palpedia+ for the source links and additional methodology notes.

## Location data

Location information distinguishes between different levels of precision:

- Alpha/boss coordinates are displayed as exact listed coordinates when the source supplies them.
- Regular habitat coordinates are approximate region-marker centres.
- Approximate region markers should not be interpreted as exact spawn coordinates or region boundaries.

## Running Palpedia+

Palpedia+ is currently a single-page web application contained in:

```
index.html
```

No build process, package manager or server-side application is required.

For basic local use, open `index.html` in a modern browser with an internet connection.

An internet connection is required because the application loads its Pal, location, skill, passive and breeding datasets from external sources at runtime.

## Current project status

Palpedia+ is an early-stage project. The current implementation is a functional single-file web application intended to establish the core encyclopedia, search, filtering, profile, individual build/stat, breeding and Passive Skill functionality. The stat calculator is intentionally conservative about mechanics that are not yet sufficiently verified, including the exact v1.0 Awakening calculation.

Future development may change the data architecture, interface and project structure.

## Contributing

The project is currently in early development. If contribution guidelines are added later, they will be documented in this repository.

When proposing data changes, prefer verifiable game data, official sources or clearly documented community datasets rather than unsupported values.

## Disclaimer

Palpedia+ is an **unofficial fan-made reference project** and is not affiliated with, endorsed by or sponsored by Pocketpair.

**Palworld**, its characters, names, game data and associated intellectual property belong to Pocketpair and their respective rights holders.

Third-party datasets and resources remain subject to their respective licences and terms.

## Repository

The main application is located at `index.html`.
