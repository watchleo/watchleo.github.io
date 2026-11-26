# Song Pack Studio v2.9.01

A major update to the companion web tool for Retro Music Player, introducing independent song collections, more reliable song identification, native TTML exports, and improved file selection.

## What's new

- **Independent song packs:** Create multiple collections with unique pack identities, customizable names and priorities. Save or restore an identity when updating a collection.
- **Content-based song IDs:** SHA-256 fingerprints identify identical audio files regardless of filename and prevent unrelated files with the same filename from sharing an ID. Re-encoding or changing embedded metadata may produce a different fingerprint.
- **Legacy ID migration:** An optional setting preserves older filename-based disc references when rebuilding an original collection. Keep the original filenames and back up the collection's identity.
- **Native TTML export:** Original TTML data is retained for compatible add-ons, with an enhanced LRC fallback when transfer limits permit. LRC and eLRC remain supported. The build log identifies word-timed and line-only TTML.
- **Improved lyrics pairing:** Match lyrics by filename, unique track number, or matching artist and title metadata. Manual attachment remains available.
- **Improved file selection:** Removed restrictive file-picker filters to improve audio and lyrics selection, particularly on iOS/iPadOS. Actual decoding support varies by browser.
- **Audio quality options:** Select Vorbis quality from Q3 to Q10 (Q6 by default), or preserve compatible Vorbis OGG without re-encoding. Quality settings are not fixed bitrates.

## Getting started

Open the Studio, add your audio and optional lyrics, and build the Songs add-on. For an additional collection, select **New pack identity** rather than simply renaming an existing pack. Activate each generated Songs BP and RP alongside the base add-on, then reopen your world.

Existing song packs do not need to be rebuilt just to update Retro Music Player. Use the matching v2.9.01 base add-on for full support of the new export features.

## Links

- [Launch Song Pack Studio](https://watchleo.github.io/)
- [Download Retro Music Player on CurseForge](https://www.curseforge.com/minecraft-bedrock/addons/retro-music-player)

Song Pack Studio generates companion music packs; it does not install or replace Retro Music Player itself. Audio processing happens in your browser, with a converter fetched when needed. Only import audio and lyrics you have permission to use.
