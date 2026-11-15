# Retro Music Player 2.8.24

Play your own music in Minecraft Bedrock on a retro **MZ-RH1 Hi-MD Player**. Import songs with the free **Song Pack Studio** web tool, burn them onto colored **MiniDiscs** at a **MiniDisc Recording Deck**, load the discs into the player, and listen privately or share the music with nearby players. The add-on also adds five wearable **headphones and earphones** that you can dye at a loom and infuse with helmet stats at a smithing table.

**Release channel: full release.** This build passes the local static checks listed in `VALIDATION.md`. In-game testing is not claimed here. See `COMPATIBILITY.md` for scope and known shared-UI limits.

**The add-on ships with no songs.** You provide the audio, and the importer turns it into a Songs add-on that you install alongside the base packs.

## Files

- `RetroMusicPlayer_2.8.24.mcaddon` — base add-on; open with Minecraft.
- `SongPackStudio_2.8.24.html` — companion song importer (also online at https://watchleo.github.io).
- `SongPackStudio_README.md` — importer guide.
- `RELEASE_NOTES.md` — feature overview for this release.
- `CURSEFORGE_DESCRIPTION.html` — ready-to-paste project description (HTML source mode); `CURSEFORGE_DESCRIPTION.md` is the Markdown copy. Neither is automatically published.
- `COMPATIBILITY.md`, `VALIDATION.md` — supported targets, known limits and the checks that were run.
- `LYRICS_FORMAT.md` — LRC / enhanced LRC examples and timing rules.
- `SUPPORT_TEMPLATE.txt` — bug-report template.
- `SHA256SUMS.txt` — checksums for the add-on and importer.
- `LICENSE.txt` — Finntoh MIT license and rights exclusions.
- `THIRD_PARTY_NOTICES.txt` — Mojang sample and importer dependency notices.

## Requirements

- Minecraft **Bedrock** (Windows, Android, iOS/iPadOS). Java Edition is not supported.
- A game build that supports engine **1.26.40**, `@minecraft/server` **2.9.0** and `@minecraft/server-ui` **2.0.0**. No experimental APIs are requested. An older game build that lacks those versions cannot load the add-on.
- Both base packs (Behavior Pack and Resource Pack) enabled. Imported music also needs both generated **Songs packs** enabled in the same world.

## Install

1. Back up your world, import `RetroMusicPlayer_2.8.24.mcaddon`, then enable its Behavior Pack and Resource Pack together in the world settings.
2. Leave and reopen the world. Keep only one copy of each base pack active.

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

Open Song Pack Studio online at https://watchleo.github.io (or open the included `SongPackStudio_2.8.24.html`) in a JavaScript-capable browser, add audio, optionally pair `.lrc` lyrics with matching filenames, and build the Songs `.mcaddon`. On iPad, a Files/Quick Look preview may not run an HTML app; use the online version at https://watchleo.github.io if the controls do not run.

Enable **both Songs packs** alongside **both base packs**, then fully exit and reopen the world. Every imported song appears in the recording deck's song list; songs are not tied to a disc number.

Already-valid Vorbis OGG can be copied without conversion or an internet connection. Other browser-decodable formats require the converter loaded from jsDelivr; codec support and memory limits vary by browser. Processing happens in the browser; the tool does not upload your audio to an application server. Internet access is still required to fetch the converter when needed.

Songs are identified by normalized filenames. Keep filenames stable when rebuilding to retain existing disc links; display titles can change independently. Enable only the intended current Songs pack. Up to 1,000 songs can be imported; each player holds up to 300 loaded tracks. Songs are streamed rather than preloaded, but keeping each song under about 10 MB helps world loading and low-memory devices. Use the split BP/RP download links if your device has trouble importing the combined Songs file.

## Recording deck

Right-click the **MiniDisc Recording Deck** (sneak to place blocks against it instead). The recorder lists your songs five per page, with search, a window-color picker and Speaker Options.

1. Pick a song. The setup screen lists only the blank colors currently in your inventory, with counts.
2. Choose the blank color to **BURN**. One blank of that color is consumed and becomes a recorded disc named after the song, keeping its shell color.
3. A single blank is replaced in its slot. Burning from a stack needs one empty inventory slot; if none is free, the recorder reports it in chat without consuming the blank.

Burning happens only at the deck; the portable player's menu does not burn songs.

## MiniDisc colors

There are **25 shell colors**: Factory Silver plus 24 named colors (Frost White, Graphite, Sky Blue, Lilac, Royal Blue, Copper, Mint, Racing Red, Carbon Black, Sunset Orange, Magenta, Teal, Lemon, Lime, Rose, Slate, Champagne, Violet, Seafoam, Midnight, Pearl, Amber, Terracotta and Aqua).

Hold a blank MiniDisc in your main hand with the MZ-RH1 in your offhand and **sneak + use** to open the **Disc Colour Studio** and recolor that stack. You can also open it from **Config → BLANK DISC COLOURS** (it uses the held blank stack, or the first blank stack in your inventory). A recorded disc keeps the color of the blank it was burned on, and the color persists when the disc is loaded into the player and later ejected.

## MZ-RH1 Hi-MD Player

### Controls

| Action | Result |
|---|---|
| **Use** (right-click) with the player in your main hand | Equip it to your offhand |
| **Sneak + use** with the player in your main hand | Open the player menu |
| **Sneak + use** with a recorded disc in your main hand and the player in your offhand | Load the disc into the player's library |
| **Sneak + use** with a blank disc in your main hand and the player in your offhand | Open the Disc Colour Studio |
| **Sneak + use** on a plain block with the player in your offhand | Unequip it |

You can also drag the player into or out of the offhand slot, or use **Config → EQUIP TO OFFHAND**. Interactive blocks such as chests, crafting tables, looms and smithing tables keep their normal behavior. Playback continues while the player stays in your inventory.

Loading a disc removes it from your inventory and adds its song to the player; **EJECT** gives the disc back. A song already in the library, a missing Songs pack and a full library (300 tracks) are each reported in chat. A disc renamed at an anvil keeps that name when loaded.

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
- **EQUIP TO OFFHAND**, **BLANK DISC COLOURS**, **STANDARD MENUS**, **WINDOW COLOR** and **HELP**.

Speaker, proximity, lyric subtitle, autoplay and resume settings are saved on the player item. Window color, lyric style and speaker listening preferences are saved per player.

### Window color

The player and recorder share a **Window Color** palette of **36 presets**, including pastel and light colors. Your choice is saved per player and applies to both interfaces.

## Speaker mode

Turn **SPEAKER** on in Config before starting a track. Everyone within **16 blocks** in the same dimension can hear it, subject to their own preferences. Speaker mode is off by default.

**Speaker Options** (Config or the recording deck) has three switches per player, all on by default: **Hear nearby speakers** (off = listen privately), **Proximity volume** and **Show nearby speaker lyrics**. You can reach it from the recording deck without owning a player. The command `/scriptevent mzrh1:speaker` also opens it when commands are permitted.

**Proximity volume:** the volume a listener hears fades linearly with distance, down to a 4% floor near the edge of the radius, when proximity is on for both the broadcaster (Config → PROXIMITY VOLUME) and the listener (Speaker Options). If either side turns it off, the volume is uniform anywhere inside the radius.

Your own playback takes priority. Lyrics use each listener's chosen lyric colors and display mode, with timing taken from the broadcaster. Leaving range, changing dimensions, disabling a switch, or the broadcaster stopping removes the feed within the refresh interval. Newly enabled audio joins on the next song or restart to stay synchronized; lyrics can appear immediately. All players need the matching Songs resource pack.

## Lyrics and enhanced LRC

Use **Config → LYRICS STYLE** to choose **Current line** or **Current + next line**, then set the main/sung-text color, contrast/upcoming-text color and current-word highlight independently. Defaults are White, Light gray and Pink, with word highlighting on. There are **27 supported Bedrock text colors**. These are engine colors, not arbitrary RGB or an exact pastel color picker. Settings persist per player.

Enable **LYRICS SUBTITLE** for display above the hotbar. Status and errors go to chat. Standard LRC uses line timing; enhanced LRC uses inline `<mm:ss.xxx>` word-start timestamps for word highlighting. Toggle highlighting off to use normal line colors. In two-line mode the upcoming cue uses the contrast color. Long cues use a moving text window to avoid creating extra logical lines; words guide the window when enhanced timing is available. Actual screen wrapping can still depend on device scale.

The importer accepts `.lrc` and `.elrc` through file picking, folders, ZIPs and manual lyric attachment. Use matching song/lyric filename stems. See `LYRICS_FORMAT.md` for examples and timing rules.

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

For registered song count and menu mode:

```mcfunction
/scriptevent mzrh1:status
```

These commands require command permissions; they are recovery tools, not an installation requirement. The standard-menu mode cannot repair a conflicting pack that replaces the entire vanilla form screen, missing resource packs, or unsupported Minecraft versions. Visually blank UI and silent missing sound resources do not always throw Script API errors, so automatic detection cannot be guaranteed.

## Troubleshooting and device checks

Player, dye and infusion errors appear in Minecraft chat. Missing helmets/shards, moved ingredients, distance and busy menus are reported without intentional ingredient consumption. Normal cancellation is silent.

- **A disc says "SONG NOT FOUND":** enable both Songs packs and reopen the world; keep the original filename if you rebuilt the Songs pack.
- **No songs in the recording deck:** all four packs must be enabled at their current versions.
- **Menus look blank or broken:** see Menu recovery above and `COMPATIBILITY.md`.

Open **Help** (main panel or Config) for the in-game cheat sheet, and verify on your device:

1. Wear each style in both fits; walk, turn, crouch, and inspect the outer hair layer.
2. Change one color and both colors; reopen the loom and check worn colors and icons.
3. Check all six helmet icons in the forge. Cancel an infusion and confirm inputs remain; then try one confirmed infusion and verify donor enchantments and damage.
4. Test armor protection and durability with Netherite-infused gear; the 4 armor points are a balancing approximation rather than a full replacement for vanilla Netherite toughness.
5. Play a recorded disc and check visualizer motion, then pause/stop. Test tap/scroll/close controls at your actual UI scale.
6. Switch between Shuffle and Sequential, turn Repeat on and off, and confirm that Repeat loops only the song that is playing.

See `VALIDATION.md` for the checks run and `COMPATIBILITY.md` for supported targets.

## License and credits

See `LICENSE.txt` and `THIRD_PARTY_NOTICES.txt`. Project-owned material is under Finntoh's MIT license. Mojang sample code/assets and third-party music, lyrics, marks, or fonts are not relicensed by that file. Do not redistribute music without permission. This is not an official Minecraft product.
