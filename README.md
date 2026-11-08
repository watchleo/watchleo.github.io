# MZ-RH1 Walkman Importer

Add your own songs and synced lyrics to the **MZ-RH1 Walkman** addon for Minecraft Bedrock Edition — no renaming files, no converting, no software to install.

**[Open the importer](https://YOUR-USERNAME.github.io/YOUR-REPO-NAME/)**

Everything runs in your browser. Your songs are never uploaded anywhere.

## How to use

1. Open the importer link above.
2. Drop in your songs (any file name, any format) and, optionally, `.lrc` lyric files. You can also tap the box to pick files.
3. Lyrics are matched to songs by file name, so `Song.mp3` pairs with `Song.lrc`. You can also attach lyrics to a song by hand.
4. Rename tracks and change their order if you like.
5. Click **Build my addon** and download `MZ-RH1_Walkman_IMPORT.mcaddon`.
6. Open the file with Minecraft, enable **both** packs (resource pack and behavior pack) on your world, then **fully restart the world**.

## Features

- Accepts mp3, wav, flac, m4a, ogg and more; converts to the OGG format Minecraft needs
- Measures each song's exact length automatically
- Optional `.lrc` synced lyrics
- Up to 24 songs; they become MiniDisc #1, #2, ... in the order shown
- Unused discs keep the built-in demo songs
- Works offline once loaded, except the first time a song needs converting (see below)

## Good to know

- **Internet is needed for conversion.** The page downloads a small OGG encoder the first time it converts a song. Files that are already OGG Vorbis skip this step.
- **Restart your world.** Minecraft loads sounds when the world starts, so changes don't appear until you fully restart it.
- **Titles** come from the file name. Rename them in the list before building if you want something different.
- **Songs without a `.lrc`** play with no lyrics.
- Run the importer again whenever you want to change your songs. It always rebuilds from a fresh copy of the addon.

## Troubleshooting

| Problem | What to try |
| --- | --- |
| "Couldn't load the OGG encoder" | Check your internet connection, or convert the song to `.ogg` yourself and add it again. |
| "This browser can't read that file" | Convert the song to mp3 or wav first and add it again. |
| Can't select files in the picker | Use drag and drop, or try a different browser. |
| Songs or lyrics don't change in game | Make sure both packs are enabled, then fully restart the world. |
| Old songs still play | Remove the old packs from the world, then import the new file. |

## About the music

This project includes only original demo music and no copyrighted songs or lyrics. Please only use music and lyrics you own or have permission to use, and don't share finished addons that contain other people's songs without the rights to do so.

## Credits

- MZ-RH1 Walkman addon: [ORIGINAL AUTHOR / LINK — add this]
- Importer page: [YOUR NAME]

## License

[Add a license here, for example MIT, and make sure it fits with the original addon's license.]
