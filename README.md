# monochrome-lyrics

Companion lyrics repository for [monochrome](https://github.com/fkhernandez/monochrome).

The app fetches `.lrc` files from this repo’s raw base URL, then falls back to LRCLIB when a file is missing.

**App base URL**

```text
https://raw.githubusercontent.com/fkhernandez/monochrome-lyrics/main
```

## Layout

```text
by-isrc/{ISRC}.lrc
by-isrc/{ISRC}.tr.lrc          # optional translation, same timestamps
by-title/{Artist}/{Title}.lrc
by-title/{Artist}/{Title}.tr.lrc
Artist Name/Album Title/01 - Song Title.lrc
Artist Name/Album Title/01 - Song Title.tr.lrc
```

Lookup order in the app:

1. `by-isrc/{ISRC}.lrc` when the track has an ISRC
2. `by-title/{Artist}/{Title}.lrc`
3. `Artist/Album/{nn} - Title.lrc` (and unnumbered `Artist/Album/Title.lrc`)
4. LRCLIB

## LRC format

```lrc
[00:12.00]First line
[01:07.00]i love you
```

Translation files use the same timestamps:

```lrc
[00:12.00]Primera línea
[01:07.00]te quiero
```

Files are fetched on demand and cached on device.


## Albums

### Sarit Hadad — *24* (2022)

Synced Hebrew `.lrc` + Spanish `.tr.lrc` for all 7 tracks:

- `Sarit Hadad/24/`
- `שרית חדד/24/` (Hebrew artist-name fallback)

Track 4 (`מה נזכרת בי?`) timing sourced from LRCLIB; other tracks aligned from official audio/captions.
