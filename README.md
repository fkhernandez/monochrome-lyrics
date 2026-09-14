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

### Sarit Hadad — *שרית חדד* (2015)

Synced Hebrew `.lrc` + Spanish `.tr.lrc` for all 16 album tracks:

- `Sarit Hadad/שרית חדד/`
- `שרית חדד/שרית חדד/` (Hebrew artist-name fallback)

The Spanish files mirror the final Hebrew timestamps exactly. Tracks 3,
`לנשום אותך`, and 6, `הבטחת לי עולם`, were aligned line by line against the
supplied lossless album masters; the other 14 tracks retain their synced
LRCLIB timing.

### Eyal Golan — *רחוק מכאן* (2016)

Master-aligned Hebrew `.lrc` + Spanish `.tr.lrc` for tracks 5, `רחוק מכאן`,
and 7, `אתה המלך`:

- `Eyal Golan/רחוק מכאן/`
- `אייל גולן/רחוק מכאן/` (Hebrew artist-name fallback)

For `רחוק מכאן`, this repository override removes LRCLIB's nonsung title and
credit rows, corrects the timing drift in the second verse, and includes the
final repeated chorus missing from LRCLIB's synced entry. `אתה המלך` was
aligned against the supplied lossless album master because LRCLIB has only
plain lyrics. The Spanish files mirror the Hebrew timestamps exactly.

### Sarit Hadad — *24* (2022)

Synced Hebrew `.lrc` + Spanish `.tr.lrc` for all 7 tracks:

- `Sarit Hadad/24/`
- `שרית חדד/24/` (Hebrew artist-name fallback)

All seven tracks were fine-tuned against the official `SaritHadadOfficial`
uploads. Earlier stable-ts, YouTube caption, and LRCLIB timings were retained as
starting points, while phrase boundaries and repeated-line structure were
checked against the released audio. Spanish files mirror the final Hebrew
timestamps exactly.

### Sarit Hadad — *שירת חיי* (2026)

Synced Hebrew `.lrc` and Spanish `.tr.lrc` for track 1, `מלך הסודות`, aligned
against the supplied 3:18 lossless recording:

- `by-isrc/IL1012601987.lrc`
- `by-title/Sarit Hadad/מלך הסודות.lrc` and the Hebrew artist-name fallback
- `Sarit Hadad/שירת חיי/` and `שרית חדד/שירת חיי/` (numbered and unnumbered)

The supplied text matches the lyrics in the
[official artist upload](https://www.youtube.com/watch?v=TgzfZ9ECAEs).
Vocal transcription confirmed both verses and all three chorus performances.
Each section was aligned separately, and line starts were adjusted against
the isolated vocal waveform. Empty timed rows clear the lyrics during the
instrumental breaks and outro. The recording's ISRC and album were verified
against [TIDAL track 554806933](https://tidal.com/track/554806933).

The Spanish files mirror every Hebrew timestamp, including the empty rows.
The translation preserves the original imagery: `carne y sangre` for
`בשר ודם`, `me abras ya el mar` for `שכבר תפתח לי את הים`, and `pruebas` for
the religious trials in `ניסיונות`. `Afino mi corazón` retains the unusual
`מדייקת את הלב שלי` metaphor: `afinar` can mean to refine or make something
more precise ([RAE](https://dle.rae.es/afinar)). `Las niñas` preserves
`הילדות` without specifying a family relationship.

Lyrics and music: Sarit Hadad, Avi Ohayon, Matan Dror, Henree, Mor Uzan.
כל הזכויות שמורות לש.חדד הפקות בע״מ
The copyright credit is retained here rather than displayed as a sung line.
