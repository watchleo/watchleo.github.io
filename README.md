# MZ-RH1 Walkman

A retro MiniDisc Walkman for Minecraft Bedrock: Winamp-style menus, synced lyrics, speaker mode, and a free web importer for adding your own songs.

**[Open the importer](https://watchleo.github.io/mz-rh1/)** — everything runs in your browser. Your songs are never uploaded anywhere.

## Which file do I download?

| File | What it is |
| --- | --- |
| `MZ-RH1-Walkman-2.1.5.mcaddon` | **The addon.** Walkman, 24 MiniDisc items, menus and sounds. Disc 1 plays the included original song; discs 2–24 are empty until you add songs. Small download (about 0.5 MB). |
| `MZ-RH1-Walkman-2.1.5-No-Songs.mcaddon` | The addon with **no music at all** (about 0.3 MB). Every disc is empty until you add songs with the importer. |
| `MZ-RH1_Importer.html` | The importer, as a file you can keep (see "Good to know"). It contains no songs; it builds from the no-songs addon and adds only the songs you give it. Normally you just use the web link above. |

**Requires Minecraft Bedrock 1.26.40 or newer** (the scripts use `@minecraft/server` 2.9.0).

## Add your own songs

1. Open the importer link above.
2. Drop in your songs (any file name, any format) and, optionally, `.lrc` lyric files. You can drop a **`.zip`** or a whole **folder** too.
3. **The last number in a file name picks the disc**: `My Song 7.mp3` goes to disc 7, and `My Song 7.lrc` is its lyrics. Files without a number take the next free disc. You can change disc numbers and titles in the list.
4. Click **Build my addon** and download `MZ-RH1_Walkman_IMPORT.mcaddon`.
5. Open it with Minecraft, enable **both** packs (resource pack and behavior pack) on your world, then **fully restart the world**.

## Good to know

- **Internet is needed to convert songs.** The importer downloads a small OGG encoder when a song needs converting. Files that are already OGG Vorbis skip this.
- **The importer builds on the small addon.** An addon built by the importer contains only the songs you add. Discs you don't fill stay empty (they play silence).
- **Restart your world.** Minecraft loads sounds when the world starts.
- **Titles** come from the file name. Rename them in the list before building, or in game with RENAME TRACK.
- **Subtitles.** Without a `.lrc`, the on-screen subtitle shows the title and volume for 5 seconds, then disappears. With lyrics, each line disappears 10 seconds after it starts if no newer line replaces it; blank `[mm:ss]` lines clear it too. Both timings are in `config.js` (`NOW_PLAYING_SECONDS`, `LYRIC_HOLD_SECONDS`).
- **Long lyrics wrap.** A lyric line (or title) longer than 34 characters continues on the next line instead of filling the screen, and a single word that is too long is split. Change the width with `LYRIC_MAX_CHARS` in `config.js` (lower it for narrow screens; CJK characters count double). Wrapping uses line breaks in the actionbar text, so check how it looks on your devices.
- **Song length is measured, not detected.** Bedrock has no "sound finished" event, so auto-advance uses each song's measured length. Heavy lag can make the next track start slightly early or late.
- Run the importer again whenever you want to change your songs. It always rebuilds from a fresh copy of the addon.

## Troubleshooting

| Problem | What to try |
| --- | --- |
| "Couldn't load the OGG encoder" | Check your internet connection, or convert the song to `.ogg` (Vorbis) yourself and add it again. |
| "This browser can't read that file" | Convert the song to mp3 or wav first and add it again. |
| Can't select files in the picker | Use drag and drop, or try a different browser. |
| A zip is skipped | It may be password-protected or damaged. Unzip it yourself and drop the folder instead. |
| "Choose a folder" does nothing on a phone | Many phone browsers don't support folder picking. Use a zip or select the files instead. |
| A disc plays nothing | That disc is empty. Add a song to that disc number with the importer. |
| Songs or lyrics don't change in game | Make sure both packs are enabled, then fully restart the world. |
| Old songs still play | Remove the old packs from the world, then import the new file. |
| Addon won't load / "missing dependency" | Update Minecraft to 1.26.40 or newer. |

## Building from source

The repository holds one source tree; a script produces all three downloads, so the importer can never drift out of sync with the addon.

```
src/BP, src/RP     behavior pack and resource pack (no songs)
songs/             song_1.ogg and songs.json (title, length and lyrics of the included song)
tools/build.py     builds everything into dist/
tools/importer_template.html
```

```
python3 tools/build.py
```

Needs only Python 3.8+. If Node.js is installed, the script also syntax-checks every script. The build fails if a pack references a missing sound, a manifest dependency doesn't match, or a JSON file is invalid.

## About the music

Only the main addon contains music: disc 1, "Neon District", an original track made for this project. The No-Songs version and the importer contain no music at all. Please only use music and lyrics you own or have permission to use, and don't share finished addons that contain other people's songs without the rights to do so.

## Credits

- Created by **Finntoh**
- Disc 1 song, UI sound effects and project icon: original works made for this release
- The importer loads the MIT-licensed [wasm-media-encoders](https://www.npmjs.com/package/wasm-media-encoders) library (which includes the Xiph Ogg/Vorbis encoder) from a CDN to convert songs. It is not bundled in any file here.

## License

Copyright (c) 2026 Finntoh. All rights reserved. You may download and install the addon, use it in your own worlds and on private servers, show it in videos, streams and screenshots, use the importer with your own songs, and make private changes to your own copy. Please don't re-upload or mirror it, sell it, publish modified versions, or reuse its code, art, sounds or music in other projects without written permission. Full terms, including third-party notices, are in [`LICENSE.txt`](LICENSE.txt).

For permission requests, contact watchleo63@gmail.com, or find Finntoh on [CurseForge](https://www.curseforge.com/members/finntoh/projects) or [GitHub](https://github.com/watchleo).

This is an unofficial fan-made project. It is not an official Minecraft product and is not approved by or associated with Mojang or Microsoft.
