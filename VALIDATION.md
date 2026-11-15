# Validation — Retro Music Player 2.8.24

Checks executed locally with Python 3 and Node.js against the packaged `.mcaddon` and the companion importer. **Minecraft itself was not run for this build**, and no in-game testing is claimed. The checks below are static and structural.

## Package and manifests

- Parsed 2,483 JSON files (1,278 in the behavior pack, 1,205 in the resource pack) with 0 parse errors.
- Syntax-checked all 28 behavior-pack JavaScript modules as ES modules, and confirmed that every relative import and named import resolves to an existing module and export.
- All manifest versions are 2.8.24 (both pack headers, all three modules, and the behavior pack's dependency on the resource pack).
- Declared requirements: engine 1.26.40, `@minecraft/server` 2.9.0, `@minecraft/server-ui` 2.0.0. No experimental API is requested.
- The `.mcaddon` and both nested `.mcpack` archives pass zip integrity tests.
- All icon textures referenced by the player menu exist, including the shuffle, sequential, repeat on/off and six volume-level icons.
- No `hud_screen.json`, `player.json`, `player.entity.json` or `nowplaying_hud.js` is present.

## Data checks

- Infusion table matches the item data: leather 1 armor / 55 durability, gold 2 / 77, chainmail 2 / 165, iron 2 / 165, diamond 3 / 363, Netherite 4 / 407 with enchantability 15 and fire resistance.
- 1,190 wearable attachables, five audio styles (three headphones, two earphones) and 36 interface skin variants are present.

## Songs bridge and importer

- The Songs bridge event identifiers (`mzrh1songs:data`, `mzrh1songs:request`), 200-chunk limit, 700-character chunks and 900-character event limit match what Song Pack Studio produces and enforces.
- The Song Pack Studio script passes a syntax check. Its pack builder and bridge-contract verifier were executed in a stubbed environment with three test songs (one with enhanced LRC) and passed; a deliberately altered bridge protocol was correctly rejected.
- Real browser audio decoding, conversion, downloads and device memory limits were not exercised.

## Not covered

Minecraft rendering and menu layout, Shuffle / Sequential / Repeat behavior in play, the playlist highlight and EJECT prompt, the hover marquee, the equip-duplicate guard, speaker audio and proximity fading, multiplayer behavior, device-specific rendering, other pack combinations and future game versions. See `COMPATIBILITY.md` for the supported target and remaining shared-UI limitations.
