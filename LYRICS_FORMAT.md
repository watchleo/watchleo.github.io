# LRC / enhanced LRC lyrics

Match the filename stem: `My Song.ogg` with `My Song.lrc` or `My Song.elrc`. The extension does not change parsing; inline tags enable word timing in either file type.

Line timing:

```text
[00:01.000]A quiet morning
[00:04.000]Another day begins
[00:08.000]
```

Enhanced word-start timing:

```text
[00:01.000]<00:01.000>A <00:01.500>quiet <00:02.000>morning<00:03.500>
[00:04.000]<00:04.000>Another <00:05.000>day <00:05.500>begins<00:07.500>
[00:08.000]
```

An angle-bracket timestamp starts the following text segment. A trailing timestamp with no text ends the cue. Millisecond and centisecond stamps work. Repeated leading line timestamps repeat that cue; its word timings shift by the same amount. A blank timed line clears the display. Ordinary metadata rows are ignored.

`[offset:250]` shifts cues 250 milliseconds earlier; negative values delay them. Some lyric editors use a different convention, so verify offsets against your audio. Without explicit end tags, blank cues or nearby next cues, the player clears stale lines after its hold period.

Config → Lyrics Style offers current-line and current-plus-next-line modes, independent main/contrast/highlight colors (defaults: White, Light gray and Pink), and a word-highlighting toggle. Colors are the supported 27 Bedrock formatting colors, not arbitrary RGB. Long lines use a bounded moving text window. Word highlighting is discrete at approximately 0.1-second update intervals; it is not a continuous syllable-fill effect. Audio/lyric timing follows the player's track clock, not microphone analysis or a decoded waveform. Browser/device sound-start latency may need an offset adjustment.

Importer limit: 12,000 lyric characters per song. Other subtitle formats, such as TTML, YRC and QRC, are not supported.
