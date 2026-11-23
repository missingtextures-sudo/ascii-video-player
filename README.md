# ASCII Video Player

Play any video on your computer as glowing, colour ASCII art at 2560x1440, add
audio-reactive effects, and export the result as a single self-contained `.html`
animation. It works in a normal browser or as a live wallpaper in
[Lively Wallpaper](https://www.rocksdanister.com/lively/) or Wallpaper Engine.

Everything is one HTML file with no dependencies, no build step and no server.
Videos never leave your computer.

## Quick start

1. Download `ascii_video_player.html` and double-click it to open it in Chrome, Edge or Firefox.
2. Drop a video file on the page, or click the box (or press **O**) to choose one.
3. Press **H** to show or hide the key list. Press **X** to export.

The player plays whatever your browser can play: usually mp4 (H.264), webm and mov.

## Keys

| Key | Action |
|---|---|
| Space | Play / pause |
| ← / → | Seek 5 seconds |
| ↑ / ↓ | Volume |
| M | Mute / unmute |
| O | Open a video file |
| X | Export an ASCII animation |
| C | Colour mode: full colour, green phosphor, mono white, neon |
| R | Character set: classic, detailed, dots, blocks, binary |
| D / Shift+D | Detail: 8 sizes, from 139x45 up to 640x180 characters |
| E | Edge lines: off, soft, strong |
| [ / ] | Brightness |
| - / = | Contrast |
| G | Glow on / off |
| A | Audio-reactive effects on / off |
| F | Fullscreen |
| H | Hide / show help |

## Audio-reactive effects

Press **A**, then open **Effects** in the top-right panel to choose which ones run.
The slider scales all of them from 0 to 200%.

| Effect | Driven by |
|---|---|
| Zoom punch, Glow pump | Bass |
| Shake, Glitch slices, Flash | Beat hits |
| Brighten | Mids and beats |
| Sparkles | Treble |
| RGB split | Bass and beats |
| Wave warp | Mids |
| Colour shift | Drifts, jumps on beats |
| Glyph scramble | Beat hits |
| Spectrum bars | Full spectrum, 40 Hz to 12 kHz |
| Invert on drops | Heavy bass drops (off by default) |

Flash and Invert strobe on beats. Leave them off if flashing bothers you.

## Exporting

Press **X**, choose frame rate, detail and time range, and click **Export**. The page
steps through the video frame by frame and downloads one `.html` file that plays
the animation on its own, with the video's sound if you keep "include the video's
audio" ticked. The colour mode, character set, edges, brightness, contrast and (when
**A** is on) the audio-reactive effects and intensity are baked in.

Exports decode frames while they play, so long and detailed clips stay playable, but
the file still grows with length, detail and frame rate. Detail 12-18 at 15 fps keeps
files small.

## As a wallpaper

- **Exported files** work directly: add the `.html` in Lively ("Add wallpaper") or
  Wallpaper Engine ("Create wallpaper").
- **The live player** can't show a file picker inside a wallpaper app. Put your video
  next to it named `video.mp4`, or pass another name with `?src=myclip.webm`.

## URL options

Add these to the end of the file's address, for example
`ascii_video_player.html?mode=3&cell=12&react=1&fx=zoom,rgb,bars`.

| Option | Values |
|---|---|
| `src` | Video file next to the player (default `video.mp4`) |
| `mode` | 0-3 colour mode |
| `set` | 0-4 character set |
| `cell` | 8, 10, 12, 14, 16, 18, 24, 32 (cell height in px) |
| `edges` | 0-2 |
| `bright` | -0.5 to 0.5 |
| `contrast` | 0.5 to 3 |
| `volume` | 0 to 1 |
| `react` | 1 starts audio-reactive effects on |
| `intensity` | 0 to 2 |
| `fx` | Comma list of effects, or `all` |
| `hud` | 0 hides the help box |

## Browser support

Recent Chrome, Edge and Firefox. Exporting needs `CompressionStream`, and recording
the soundtrack needs `MediaRecorder` with Opus. Browsers block sound until you click,
so playback may start muted.

## Use responsibly

Only export videos and music you have the right to copy, such as your own footage.

## License

[MIT](LICENSE)
