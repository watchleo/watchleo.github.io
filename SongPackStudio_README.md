# Song Pack Studio 2.8.24

Companion importer for Retro Music Player 2.8.24. This HTML creates a separate Songs add-on; it does not install or modify the base pack.

## Quick start

1. Obtain the matching v2.8.24 base add-on from an official release (the archive is not hosted in this repository), then install and enable both base Retro Music Player packs in Minecraft.
2. Open Song Pack Studio at https://watchleo.github.io, or open a separately supplied `SongPackStudio_2.8.24.html` if included with your release package, in a browser that runs JavaScript. iPad Files/Quick Look may only preview the file; use the online version if controls do not respond.
3. Add audio files, a folder, or a supported ZIP (mp3, wav, flac, m4a, aac, ogg, opus, wma, aiff, mp4 and webm are recognized; actual support depends on your browser). Optional `.lrc` or `.elrc` files should share their song's filename stem, such as `My Song.ogg` and `My Song.lrc`.
4. Review titles and preview audio, then build the Songs `.mcaddon`. If the combined import fails, use the generated separate BP/RP download links.
5. Import it into Minecraft, enable **Songs BP and Songs RP** alongside the two base packs, and fully exit and reopen the world. On iPad, save the exported file in Files, then choose Share → Minecraft. If your browser changes the extension to `.zip`, rename it to `.mcaddon` (or `.mcpack`) before importing.
6. Every song you add appears in the **recording deck's** song list. Use the deck, select a song, then select which available blank MiniDisc color to burn. The recorded disc keeps that color. Load a recorded disc using the base pack's player controls. There is no burn action inside the portable music-player menu.

## Formats and privacy

Valid Vorbis OGG copies without conversion. Other audio depends on the browser's decoder and a converter fetched from jsDelivr; an internet connection is required for that conversion dependency. The audio is processed locally in the browser, not uploaded to an application server. An `.ogg` extension alone does not guarantee Vorbis; unsupported containers/codecs can fail.

On iPad, start with a few short songs. Keep the browser open while building. Large files and collections may exceed device memory limits. Canceling a build does not export a partial pack; individual failed songs are reported when the remaining songs can still be exported.

## Rebuilding your collection

Stable song IDs are derived from normalized filenames. Keep filenames unchanged when rebuilding if existing recorded discs should keep their links; edit the display title instead. Distinct songs should have distinct filenames. Use the current generated Songs pack, rather than several competing versions with the same pack UUIDs. Export versions advance with rebuild timestamps.

Limits: 1,000 imported songs, 128 MiB per audio file, 12,000 lyric characters per song, and bounded archive/metadata totals. These are software limits, not a guarantee that every device can process a collection that large. Each portable player holds up to 300 loaded tracks.

## Troubleshooting

- No imported songs: enable all four packs, select their current versions, and reopen the world.
- A previously recorded disc is missing its song: restore the Songs pack and its original filename.
- Conversion fails: try a smaller collection or preconvert the file to valid Vorbis OGG.
- Download/import fails: try the separate Songs BP/RP downloads or another browser.
- Silent HTML preview: open https://watchleo.github.io in your browser instead of a static file preview.

Only use audio/lyrics you have permission to use; redistribution requires the applicable rights. The importer does not grant music rights. See [LICENSE.txt](LICENSE.txt) (All Rights Reserved for original project materials) and [THIRD_PARTY_NOTICES.txt](THIRD_PARTY_NOTICES.txt) for third-party terms.

Validation covers script parsing and generated pack structure/protocol. Actual browser audio decoding, iPad downloads, and Minecraft playback require device testing.

Enhanced LRC inline word timestamps are preserved. See [LYRICS_FORMAT.md](LYRICS_FORMAT.md) for format examples, offset convention and Config → Lyrics Style options.
