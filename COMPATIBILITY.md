# Compatibility — Retro Music Player 2.8.24

Targets Windows Minecraft Bedrock, Android and iOS/iPadOS on game versions supporting the declared requirements: engine 1.26.40, stable @minecraft/server 2.9.0 and @minecraft/server-ui 2.0.0. Java Edition is unsupported. No experimental API dependency is requested. Both base packs and both generated Songs packs must be enabled for imported music.

This build passes the local static checks listed in VALIDATION.md. In-game testing is not claimed, and testing is also not claimed for every specific OS/device, console, Realm, dedicated server, browser codec, or combination of other add-ons.

No behavior entities/player.json or resource entity/player.entity.json override is included. No scripted knockback workaround is included. Netherite-infused audio gear has 4 armor points, 407 durability and 15 enchantability. Audio gear occupies the normal helmet slot.

The custom server_form UI and private-use font page can conflict with other UI/font packs. Standard menus in Config provide a recovery option; they cannot merge incompatible global UI overrides. Optional actionbar lyrics can be disabled if another pack uses that display area. Music status/errors remain in chat.

Song packs: the base add-on's Songs bridge uses a version-1 script-event protocol, which Song Pack Studio 2.8.24 follows. Use only one current Songs pack version at a time.

Player settings are saved per player, including Repeat and speaker listening preferences (hear speakers, proximity volume, speaker lyrics).

Use the included README for installation and recovery commands. Back up worlds before installing. Large song collections and browser conversion can exceed device memory limits. On iPad, a static Files/Quick Look preview may not execute the importer; use the online version at https://watchleo.github.io if necessary.

When reporting a bug, include the Minecraft version, device/OS, UI scale, other active packs, steps and exact chat/content-log error using SUPPORT_TEMPLATE.txt.

No MiniDisc/title/artist HUD is included. No hud_screen.json or player.json override is shipped, and the title/subtitle channel is not used for music metadata. Custom menu UI/font conflicts and optional actionbar lyric sharing remain as described above.
