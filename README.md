# Retro Music Player 2.9.01

Play your own music in Minecraft Bedrock on a retro **MZ-RH1 Hi-MD Player**. Import songs with the free **Song Pack Studio** web tool, burn them onto colored **MiniDiscs** at a **MiniDisc Recording Deck**, load the discs into the player, and listen privately or share the music with nearby players. The add-on also adds five wearable **headphones and earphones** that you can dye at a loom and infuse with helmet stats at a smithing table.

**Release channel: full release.** This build passes the local static checks listed in [`VALIDATION.md`](VALIDATION.md). See [`COMPATIBILITY.md`](COMPATIBILITY.md) for supported targets and known shared-UI limitations. Static validation does not guarantee compatibility on every device or with every other add-on.

**The add-on ships with no songs.** You provide the audio, and the importer turns it into a Songs add-on that you install alongside the base packs.

## Latest update — v2.9.01

- Multiple independent song packs with customizable names and priorities.
- Content-based song identification and improved duplicate handling.
- Native TTML lyrics, progressive character highlighting, simultaneous and background vocals.
- Expanded Song Suggestions with an operator inbox, personal request history and no request cooldown.
- Craftable blank MiniDisc recoloring and a 24-block speaker range.
- Improved audio and lyrics file selection, including iOS/iPadOS file-picker improvements, and adjustable audio conversion quality.

Read the [latest GitHub release notes](https://github.com/watchleo/watchleo.github.io/releases/latest) for Song Pack Studio, or visit [Retro Music Player on CurseForge](https://www.curseforge.com/minecraft-bedrock/addons/retro-music-player) for the base add-on and its changelog.

## Downloads and documentation

**This repository hosts the Song Pack Studio website and documentation—not the base Minecraft add-on.**

| Platform | Download or resource |
|---|---|
| GitHub Pages | [Open Song Pack Studio](https://watchleo.github.io/) |
| GitHub | [Website source](https://github.com/watchleo/watchleo.github.io) · [Releases](https://github.com/watchleo/watchleo.github.io/releases) |
| CurseForge | [Download Retro Music Player v2.9.01](https://www.curseforge.com/minecraft-bedrock/addons/retro-music-player) |

Download `RetroMusicPlayer_2.9.01.mcaddon` from the official CurseForge project page. Use Song Pack Studio v2.9.01 with the matching base add-on for full support of the latest export features. The Studio builds companion Songs packs; it does not install or replace the base add-on. A standalone HTML copy may also be supplied separately.

- [`SongPackStudio_README.md`](SongPackStudio_README.md) — importer guide.
- [`COMPATIBILITY.md`](COMPATIBILITY.md) and [`VALIDATION.md`](VALIDATION.md) — supported targets, known limitations and tests.
- [`LYRICS_FORMAT.md`](LYRICS_FORMAT.md) — LRC, enhanced LRC and native TTML guide.
- [`SUPPORT_TEMPLATE.txt`](SUPPORT_TEMPLATE.txt) — bug-report template.
- [`SHA256SUMS.txt`](SHA256SUMS.txt) — published checksums for separately distributed release files; the base add-on archive is not hosted here.
- [`LICENSE.txt`](LICENSE.txt) — **All Rights Reserved** terms for original project-owned material.
- [`THIRD_PARTY_NOTICES.txt`](THIRD_PARTY_NOTICES.txt) — third-party code, sample assets and licensing.

## Requirements

- Minecraft **Bedrock** (Windows, Android, iOS/iPadOS). Java Edition is not supported.
- A game build that supports engine **1.26.40**, `@minecraft/server` **2.9.0** and `@minecraft/server-ui` **2.0.0**. No experimental APIs are requested. An older game build that lacks those versions cannot load the add-on.
- Both base packs (Behavior Pack and Resource Pack) enabled. Imported music also needs the generated **Songs Behavior Pack and Resource Pack for each collection** enabled in the same world.

## Install

1. Back up your world. Download [`RetroMusicPlayer_2.9.01.mcaddon` from CurseForge](https://www.curseforge.com/minecraft-bedrock/addons/retro-music-player), import it into Minecraft, then enable its Behavior Pack and Resource Pack together in world settings.
2. Leave and reopen the world. Keep only one version of each base pack active.

### Updating from v2.8.24 or earlier

Back up your world, original song collections and any saved pack identity JSON files. Import the updated base add-on and enable its two current packs. Keep existing Songs BP/RP enabled; you do not need to rebuild or remove old music packs just to upgrade. Use the latest Studio for new exports. See the identity and migration instructions below before rebuilding an existing collection.

## Quick start

1. **Craft** a blank MiniDisc, a MiniDisc Recording Deck and an MZ-RH1 player (recipes below). All items are also in the creative inventory: *Retro Music - Audio Gear* and *Retro Music - Wearable Audio* under Equipment, *Retro Music - MiniDiscs* under Items.
2. **Import songs** with Song Pack Studio, install the Songs add-on it builds, enable both Songs packs and reopen the world.
3. **Record:** right-click the recording deck, pick a song, pick which blank color to burn.
4. **Play:** hold the player, right-click to equip it in the offhand, then hold the recorded disc and sneak + use to load it.

## Crafting recipes

All recipes use the crafting table.

| Item | Recipe |
|---|---|
| **Blank MiniDisc** | Shapeless: 1 iron ingot + 2 iron nuggets + 1 redstone |
| **MZ-RH1 Hi-MD Player** | Top and bottom rows: three iron ingots each. Middle row: redstone, a **blank MiniDisc**, redstone |
| **MiniDisc Recording Deck** | Top row: iron ingot, redstone, iron ingot. Middle row: redstone, **diamond**, redstone. Bottom row: three iron ingots |

Wearable audio gear (N = iron nugget, R = redstone):

| Item | Top row | Middle row | Bottom row |
|---|---|---|---|
| **Studio Headphones** | _ N _ | white wool, _, white wool | _ R _ |
| **Retro Headphones** | _ N _ | copper ingot, _, copper ingot | _ R _ |
| **Gaming Headphones** | _ N _ | pink wool, _, pink wool | _ R _ |
| **Wired Earphones** | N, _, N | _ string _ | _ R _ |
| **Wireless Earphones** | N, _, N | _ green dye _ | _ R _ |

(`_` means an empty slot.)

## Import songs

1. Open [Song Pack Studio](https://watchleo.github.io/) in a JavaScript-capable browser. On iPad/iPhone, use the online version in Safari rather than a static Files/Quick Look preview.
2. Add audio files, a folder or a supported ZIP archive. Recognized formats include MP3, WAV, FLAC, M4A, AAC, OGG, Opus, WMA, AIFF, MP4 and WebM; actual decoding support depends on the browser.
3. Optionally add `.lrc`, `.elrc` or `.ttml` lyrics. The Studio pairs lyrics by filename, unique track number or matching both artist and title metadata. Manual attachment is also available. Only one lyrics file per song is needed.
4. Review titles, audio and lyrics timing, choose a conversion quality if needed, then build and download the Songs `.mcaddon`.
5. Import the generated add-on into Minecraft, enable both Songs packs for that collection alongside the two base packs, then fully exit and reopen the world. The imported songs appear in the Recording Deck, not automatically in the portable player's playlist.

### Audio quality, privacy and limits

Already-valid Vorbis OGG can be copied without re-encoding. Other browser-decodable formats require the converter loaded from jsDelivr. Audio conversion takes place locally in your browser; audio is not uploaded to an application server. Internet access is required to fetch the converter when needed. An OGG extension alone does not guarantee a compatible Vorbis codec.

Conversion quality can be set from **Q3 to Q10 (Q6 by default)**. These are Vorbis quality levels, not fixed bitrates. Higher settings generally increase file sizes; converting a low-quality source cannot restore lost audio detail.

The Studio supports up to **1,000 songs per pack**, and the add-on accepts up to **16 pack identities**, including a legacy pack if present. Each portable player holds up to **300 loaded tracks**. Audio files are limited to 128 MiB each in the Studio; smaller collections and songs under about 10 MB are recommended for low-memory devices. Catalog transfers and lyrics also have size limits. Actual practical capacity depends on your device and world. Use the separate BP/RP download links if Minecraft has trouble importing the combined Songs add-on.

### Multiple song packs and identities

- Choose **New pack identity** for each additional independent collection. Give it a recognizable name and set its priority. Renaming a pack alone does not create a new identity.
- Save the pack identity JSON; use **Restore identity** when updating that same collection later.
- Enable both the Behavior Pack and Resource Pack for every collection you want to use, alongside the base packs. Reopen the world.
- Open **Song Suggestions → Installed Song Packs** to inspect registered pack names, priorities and song counts.
- Higher numeric priority wins when multiple packs supply the same song ID; equal priorities use registration order. The in-game pack stack order is not the priority setting.

### Song IDs, duplicates and legacy migration

New exports use SHA-256 fingerprints of the original audio file. Identical files share a content-based song ID even if renamed; different files with the same filename are kept separate. This is byte-based identification, not acoustic fingerprinting: re-encoding audio or altering its embedded metadata can produce a different ID.

When removing a song pack, existing MiniDiscs and saved playlists retain their song references. Unavailable tracks cannot be played until their original pack or a compatible replacement is restored. An active duplicate with the same content ID can supply the track instead. The registered pack list is rebuilt when the world reopens.

One legacy song pack can coexist with newer independent packs. Older packs use filename-based IDs. When rebuilding a legacy collection, keep the original audio filenames and complete collection, enable **Preserve old filename-based disc IDs** for that migration, and save the updated identity. Do not enable legacy migration indiscriminately for unrelated new collections. Keep a backup of the original pack in case old discs need to be restored.

See [`SongPackStudio_README.md`](SongPackStudio_README.md) for the full importer guide.

## Recording deck

Right-click the **MiniDisc Recording Deck** (sneak to place blocks against it instead). The recorder lists your songs five per page, with search, a window-color picker, Speaker Options and Song Suggestions.

1. Pick a song. The setup screen lists only the blank colors currently in your inventory, with counts.
2. Choose the blank color to **BURN**. One blank of that color is consumed and becomes a recorded disc named after the song, keeping its shell color.
3. A single blank is replaced in its slot. Burning from a stack needs one empty inventory slot; if none is free, the recorder reports it in chat without consuming the blank.

Burning happens only at the deck; the portable player's menu does not burn songs.

## MiniDisc colors

There are **25 shell colors**: Factory Silver plus 24 named colors (Frost White, Graphite, Sky Blue, Lilac, Royal Blue, Copper, Mint, Racing Red, Carbon Black, Sunset Orange, Magenta, Teal, Lemon, Lime, Rose, Slate, Champagne, Violet, Seafoam, Midnight, Pearl, Amber, Terracotta and Aqua).

Recolor blank MiniDiscs with dyes at a crafting table. The previous sneak + use recoloring shortcut has been removed. You can also open the Disc Colour Studio from **Config → BLANK DISC COLOURS** (it uses the held blank stack, or the first blank stack in your inventory). A recorded disc keeps the color of the blank it was burned on, and the color persists when the disc is loaded into the player and later ejected.

## MZ-RH1 Hi-MD Player

### Controls

| Action | Result |
|---|---|
| **Use** (right-click) with the player in your main hand | Equip it to your offhand |
| **Sneak + use** with the player in your main hand | Open the player menu |
| **Sneak + use** with a recorded disc in your main hand and the player in your offhand | Load the disc into the player's library |
| **Sneak + use** with a blank disc in your main hand and the player in your offhand | Recording deck reminder |
| **Sneak + use** on a plain block with the player in your offhand | Unequip it |

You can also drag the player into or out of the offhand slot, or use **Config → EQUIP TO OFFHAND**. Interactive blocks such as chests, crafting tables, looms and smithing tables keep their normal behavior. Playback continues while the player stays in your inventory.

Loading a disc removes it from your inventory and adds its song to the player; **EJECT** gives the disc back. A song already in the library, an unavailable song and a full library (300 tracks) are each reported in chat. Duplicate checks use song identity rather than the display title. A disc renamed at an anvil keeps that name when loaded.

### Main panel

- **Transport:** PREV, PLAY, PAUSE, STOP, NEXT. Tracks advance automatically when they end. Pause restarts the track on play rather than seeking; STOP resets to the first track.
- **Playlist:** six rows per page with PAGE UP / PAGE DOWN. The highlight marks only a song you picked; newly loaded or imported songs are not highlighted automatically.
- **Bottom buttons:** HELP, REM (eject), SEL (pick a loaded song to rename), MISC (opens Config), **MANAGE PLAYLIST** (reorder, sort A–Z, rename, play or eject any track) and **SEARCH SONG**.
- **EJECT** with nothing playing and no song selected asks you to click a song first.
- **Rename** changes the title shown for that song across the world; submit an empty name to restore the imported title.

Long list titles scroll only while hovered, pressed, or selected. Short titles that fit stay still, and long now-playing titles use a continuous left/right marquee.

### Play order and repeat

The mode column on the main panel has three buttons: **SHUFFLE** (top), **REPEAT** (middle) and **SEQUENTIAL** (bottom, marked "1 2 3").

- **Shuffle and Sequential** are the two play orders; the lit one is active. Sequential plays the playlist in order and wraps to the first track after the last. Shuffle plays each track once in random order, then starts a new shuffled cycle.
- **Repeat** loops only the song that is playing. Press it again to turn it off. With Repeat off, the playlist keeps going and wraps instead of stopping after the last track.

### Volume and visualizer

Volume cycles through **0%, 20%, 40%, 60%, 80%, and 100%**. The retro UI shows a speaker icon with five level bars: no lit bars is 0% (mute) and five lit bars is 100%. The exact value appears in chat when you change it.

The visualizer is a decorative 16-frame animation during playback and a flat idle display while stopped or paused. It does not measure the song's frequency spectrum.

### Config

Open Config from the CONFIG button or MISC:

- **SPEAKER: ON (PUBLIC) / OFF (PRIVATE)** — share your music with nearby players (off by default).
- **PROXIMITY VOLUME** — fade speaker volume by distance for your broadcast.
- **LYRICS SUBTITLE** — show synchronized lyrics above the hotbar.
- **SPEAKER OPTIONS** — your personal listening preferences (see below).
- **LYRICS STYLE** — lyric display mode and colors.
- **AUTOPLAY ON IMPORT** — start playing right after loading a disc (on by default).
- **RESUME ON EQUIP** — resume music that was playing when you unequipped the player (on by default).
- **EQUIP TO OFFHAND**, **BLANK DISC COLOURS**, **STANDARD MENUS**, **WINDOW COLOR** and **HELP**. Song Suggestions can also be accessed from the player menus.

Speaker, proximity, lyric subtitle, autoplay and resume settings are saved on the player item. Window color, lyric style and speaker listening preferences are saved per player.

### Window color

The player and recorder share a **Window Color** palette of **36 presets**, including pastel and light colors. Your choice is saved per player and applies to both interfaces.

## Speaker mode

Turn **SPEAKER** on in Config before starting a track. Everyone within **24 blocks** in the same dimension can hear it, subject to their own preferences. Speaker mode is off by default.

**Speaker Options** (Config or the recording deck) has three switches per player, all on by default: **Hear nearby speakers** (off = listen privately), **Proximity volume** and **Show nearby speaker lyrics**. You can reach it from the recording deck without owning a player. The command `/scriptevent mzrh1:speaker` also opens it when commands are permitted.

**Proximity volume:** the volume a listener hears fades linearly with distance, down to a 4% floor near the edge of the radius, when proximity is on for both the broadcaster (Config → PROXIMITY VOLUME) and the listener (Speaker Options). If either side turns it off, the volume is uniform anywhere inside the radius.

Your own playback takes priority. Lyrics use each listener's chosen lyric colors and display mode, with timing taken from the broadcaster. Leaving range, changing dimensions, disabling a switch, or the broadcaster stopping removes the feed within the refresh interval. Newly enabled audio joins on the next song or restart to stay synchronized; lyrics can appear immediately. All players need the matching Songs resource pack.

## Lyrics: LRC, eLRC and TTML

Use **Config → LYRICS STYLE** to choose **Current line** or **Current + next line**, then set the main/sung-text color, contrast/upcoming-text color and current-word highlight independently. Defaults are White, Light gray and Pink, with word highlighting on. There are **27 supported Bedrock text colors**. These are engine colors, not arbitrary RGB or an exact pastel color picker. Settings persist per player.

Enable **LYRICS SUBTITLE** for display above the hotbar. Status and errors go to chat. The lyrics format is detected automatically; there is no separate TTML toggle.

| Format | In-game behavior |
|---|---|
| Standard LRC (`.lrc`) | Line-by-line synchronization |
| Enhanced LRC (`.elrc` or enhanced `.lrc`) | Inline word timestamps and progressive highlighting |
| Line-timed TTML (`.ttml`) | Line start/end timing without accurate individual word highlighting |
| Word-timed TTML (`.ttml`) | Native word start/end timing, progressive character highlighting and overlapping/background vocals when present |

Enable **Word highlighting (eLRC / TTML)** in Lyrics Style to see timed words progressively fill with the chosen highlight color. Turn highlighting off to use normal line colors. In two-line mode, simultaneous vocals can occupy both rows; otherwise the upcoming cue uses the contrast color. Long cues use a moving text window; actual wrapping can depend on device UI scale. Progressive animation uses Minecraft text coloring, not pixel-level gradients or Apple Music's full visual effects.

Song Pack Studio retains the original TTML for native parsing and exports an enhanced LRC fallback when it fits within transfer limits. A TTML file with only line timestamps does not gain accurate word timing merely by converting formats. The Studio build log reports whether word timing is present. Users do not need to provide a separate LRC file alongside TTML.

The importer accepts `.lrc`, `.elrc` and `.ttml` through file picking, folders, ZIPs and manual attachment. See [`LYRICS_FORMAT.md`](LYRICS_FORMAT.md) for examples and timing rules.

## Song Suggestions

Open **Song Suggestions** from the player or Recording Deck to request a song by title and artist. There is **no request cooldown**. Different players can request the same song; a player cannot submit the same pending request repeatedly.

### Player menu

- **Request a Song** — submit a title and artist to world operators.
- **My Requests** — view your pending, approved and rejected requests that are still retained in the world's inbox/history.
- **Installed Song Packs** — inspect registered music collections.

### Operator inbox

Only world operators can manage requests. Suggestions are saved with the requester's name and submission time, and pending suggestions for the same song are grouped by popularity.

- **All Requests** — review pending songs, sorted by request count, and view individual requesters.
- **By Player** — filter pending requests by requester.
- **Approve / Reject** — review requests individually or as a group; decisions are recorded in history.
- **Delete** — permanently remove selected pending requests.
- **Delete All Pending** — clear pending suggestions after confirmation, without clearing history.
- **Request History** — review decisions or clear the history with confirmation.

Up to **100 pending requests and 100 reviewed entries** can be retained, subject to storage limits. The oldest reviewed entries expire as history reaches those limits. **Approving a request does not download or import a song.** Operators must obtain permitted audio and use Song Pack Studio to add it manually.

## Headphones and earphones

The five craftable styles are **Studio**, **Retro** and **Gaming** headphones and **Wired** and **Wireless** earphones. They are worn in the head armor slot. Uninfused gear gives no armor protection and has no durability. Only base styles appear in the creative catalog; finish, armor and fit variants are workshop outputs. Right-clicking audio gear with an empty head slot equips it and removes any leftover copy from the hand slot.

### Loom: color and fit

Hold the audio gear and use a **loom** (stay within about 6 blocks of it). Choose **Shell** (cups / outer casing), **Trim** (band / cable / details), or both from the 16 vanilla dye colors, and a **fit**:

- Each changed channel costs one matching vanilla dye; choosing the same dye for both channels costs two.
- **Snug** and **Roomy** (adds hair clearance) fit changes are free.
- Armor, wear, enchantments, names and stored item metadata are preserved.

The confirmation shows BEFORE and AFTER color thumbnails. Tap either preview to edit choices, **APPLY FINISH** to commit, or **CANCEL** to keep the item. Previews depict the color scheme, not a 3D simulation of your skin or fit. Gear dyed with arbitrary cauldron mixtures is labeled as a nearest-color approximation. Inventory dyed icons are simplified previews; check the worn model for the full two-channel finish.

### Smithing table: infusion

Hold the audio gear and use a **smithing table** (stay within about 6 blocks). Keep a supported helmet and **one amethyst shard** in your inventory. Review the result, then confirm. The donor helmet and one shard are consumed only after the inputs and your distance are rechecked.

| Donor | Armor | Maximum durability | Enchantability |
|---|---:|---:|---:|
| Leather | 1 | 55 | 15 |
| Gold | 2 | 77 | 25 |
| Chainmail | 2 | 165 | 12 |
| Iron | 2 | 165 | 9 |
| Diamond | 3 | 363 | 10 |
| Netherite | 4 | 407 | 15 |

The donor's remaining durability, enchantments (including curses) and name/metadata are copied. The result replaces the audio gear's stats and enchantments with the donor's; they are not combined. Fit and colors remain. Armor trims are not transferred. Netherite-infused gear is fire-resistant as a dropped item. Netherite's 4 armor is a balance adjustment, not an exact equivalent of vanilla toughness at every damage level. No scripted knockback bonus or player behavior override is included.

## Chat feedback and menu recovery

Music-player notices, now-playing information, gesture hints and errors use **Minecraft chat**. Optional synchronized lyrics use the actionbar; disable **Config → LYRICS SUBTITLE** if another pack needs that area. The add-on includes no MiniDisc/title/artist HUD and no `hud_screen.json` override, so the normal paper doll is untouched. It does not send music title/subtitle popups.

**Config → STANDARD MENUS** switches this add-on to readable vanilla forms. A thrown custom-form opening error also retries with standard forms and remembers the choice. Cancellation does not trigger recovery. This mode preserves action selection and inputs, but uses standard controls instead of the retro layout. The default is the retro theme/design.

If another UI pack hides the Config button, an operator can run:

```mcfunction
/scriptevent mzrh1:menus standard
```

Close and reopen the menu. To restore the retro design:

```mcfunction
/scriptevent mzrh1:menus retro
```

For registered song count, menu mode and available lyrics diagnostics:

```mcfunction
/scriptevent mzrh1:status
```

These commands require command permissions; they are recovery tools, not an installation requirement. The standard-menu mode cannot repair a conflicting pack that replaces the entire vanilla form screen, missing resource packs, or unsupported Minecraft versions. Visually blank UI and silent missing sound resources do not always throw Script API errors, so automatic detection cannot be guaranteed.

## Troubleshooting and device checks

Player, dye and infusion errors appear in Minecraft chat. Missing helmets/shards, moved ingredients, distance and busy menus are reported without intentional ingredient consumption. Normal cancellation is silent.

- **A disc says "SONG NOT FOUND" or a track is unavailable:** enable its original Songs BP and RP, or a compatible replacement preserving its song ID, and reopen the world. Do not rename legacy source files when migrating.
- **No songs in the recording deck:** enable both base packs and both packs for each intended song collection. Reopen the world and check Installed Song Packs.
- **A second song pack replaces the first:** use New pack identity for separate collections, not merely a different display name.
- **MP3 or lyrics files cannot be selected:** use the latest online Studio in a supported browser. File selection does not guarantee that the browser can decode every audio format.
- **Lyrics do not highlight word by word:** enable Lyrics Subtitle and Word highlighting, then verify the source has word-level timing. Re-export previously converted TTML with its original XML to use native TTML.
- **Menus look blank or broken:** see Menu recovery above and [`COMPATIBILITY.md`](COMPATIBILITY.md).

Open **Help** (main panel or Config) for the in-game cheat sheet, and verify on your device:

1. Wear each style in both fits; walk, turn, crouch, and inspect the outer hair layer.
2. Change one color and both colors; reopen the loom and check worn colors and icons.
3. Check all six helmet icons in the forge. Cancel an infusion and confirm inputs remain; then try one confirmed infusion and verify donor enchantments and damage.
4. Test armor protection and durability with Netherite-infused gear; the 4 armor points are a balancing approximation rather than a full replacement for vanilla Netherite toughness.
5. Play a recorded disc and check visualizer motion, then pause/stop. Test tap/scroll/close controls at your actual UI scale.
6. Switch between Shuffle and Sequential, turn Repeat on and off, and confirm that Repeat loops only the song that is playing.

7. Install two independent song collections and verify their registration, playback and duplicate priority. Back up the world before testing pack removal/restoration.
8. Test a word-timed TTML or eLRC track and ordinary line-timed lyrics; check highlighting and simultaneous vocals at your actual UI scale.
9. Test Song Suggestions with a regular player and an operator, including request history and persistence after reopening the world.

See [`VALIDATION.md`](VALIDATION.md) for the checks run and [`COMPATIBILITY.md`](COMPATIBILITY.md) for supported targets.

## License and credits

Copyright © 2026 Finntoh. **All rights reserved** for original project-owned materials, subject to the limited permissions in [`LICENSE.txt`](LICENSE.txt). Third-party libraries, Mojang sample assets, trademarks, and user-provided music or lyrics retain their own rights; see [`THIRD_PARTY_NOTICES.txt`](THIRD_PARTY_NOTICES.txt). Do not redistribute music without permission. This is an unofficial fan project, not endorsed by Mojang or Microsoft.
