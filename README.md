# movies-platform-media

Video files for [Movies Platform](https://github.com/hasan123dayoub-del/movies-platform): open films encoded for **adaptive streaming (HLS)**, served by GitHub Pages and played on the site with [hls.js](https://github.com/video-dev/hls.js).

| Film | Length | Playlist |
|---|---|---|
| Big Buck Bunny (2008) | 10:34 | [`big-buck-bunny/master.m3u8`](big-buck-bunny/master.m3u8) |
| Caminandes 2: Gran Dillama (2013) | 2:26 | [`caminandes-2/master.m3u8`](caminandes-2/master.m3u8) |

## How they were made

Each 1080p source was encoded once with ffmpeg into six H.264 qualities and one shared AAC audio track:

| Quality | Size | Video bitrate |
|---|---|---|
| 144p | 256×144 | 110 kbps |
| 240p | 426×240 | 220 kbps |
| 360p | 640×360 | 420 kbps |
| 480p | 854×480 | 700 kbps |
| 720p | 1280×720 | 1.3 Mbps |
| 1080p | 1920×1080 | 2.4 Mbps |

- 4-second segments, with a keyframe at the start of every segment in **every** quality, so the player can switch quality mid-film without a jump.
- `master.m3u8` lists the six qualities; the player picks one for the connection speed (Auto) or the one the viewer chooses.
- The audio is a separate rendition shared by all qualities instead of being copied six times.

## Credits and licenses

Both films are by the **Blender Foundation** and released under the [Creative Commons Attribution 3.0](https://creativecommons.org/licenses/by/3.0/) license, which allows sharing and adapting them with credit:

- **Big Buck Bunny** © 2008 Blender Foundation | [peach.blender.org](https://peach.blender.org)
- **Caminandes 2: Gran Dillama** © 2013 Blender Foundation | [caminandes.com](https://www.caminandes.com). `caminandes-2/poster.jpg` is a frame from the film.

The films were re-encoded (changed in size and bitrate); nothing else was changed.
