# 🎧 audio-presets

Personal EQ preset collection for two Chrome/Windows audio tools — **EARS** and **FXSound** — kept together so they're never lost and always version-controlled.

---

## Structure

```
audio-presets/
├── ears/                        # EARS Chrome extension presets
│   ├── presets/
│   │   └── Presets.json         # All EARS genre presets (JSON)
│   ├── concat.js                # Script to merge preset files → one-liner JSON
│   └── package.json
│
├── fxsound/                     # FXSound Windows app presets
│   └── presets/
│       ├── Pop.fac
│       ├── rap.fac
│       ├── Trapmetal.fac
│       └── lofi.fac
│
├── preset-map.json              # Cross-reference: genre → EARS + FXSound equivalents
└── README.md
```

---

## About the tools

### EARS – Bass Boost & EQ (Chrome extension)
Applies a parametric EQ to any audio playing in Chrome — YouTube, Spotify Web, SoundCloud, etc. 11 bands per preset. Presets are stored in Chrome's local storage as JSON.

→ [Install EARS](https://chrome.google.com/webstore/detail/ears-bass-boost-eq-any-au/nfdfiepdkbnoanddpianalelglmfooik)

### FXSound (Windows app)
System-wide audio enhancer with EQ, bass boost, ambience, and clarity controls. Presets are `.fac` files imported directly into the app.

→ [Download FXSound](https://www.fxsound.com/)

---

## EARS presets

| Preset | Character | Best for |
|---|---|---|
| **Modern Country** | Bright, punchy, vocal-forward | Morgan Wallen, Luke Combs, Zach Bryan |
| **Hip Hop** | Punchy upper-bass, clean mids | Kendrick, Drake, general rap |
| **Hip Hop (Trap)** | Heavy punch, crisp hi-hats | Travis Scott, Future, 21 Savage |
| **R&B** | Warm low-end, smooth presence | The Weeknd, SZA, Frank Ocean |
| **R&B (Smooth)** | Silky, laid-back, rich mids | Neo-soul, slow jams, late night |
| **Lo-Fi / Chill** | Warm, vintage, rolled-off highs | Study sessions, background listening |
| **Electronic / EDM** | Sub punch, scooped mids, airy highs | House, techno, festival sets |
| **Podcast / Spoken Word** | Voice clarity, cut rumble | Podcasts, lectures, commentary |
| **Wa_Rock** | My original exported rock preset | Classic & modern rock |

> All presets are tuned for **bookshelf speakers + a 6th order bandpass subwoofer.** The deep sub bands (7–37Hz) are cut in every preset to avoid competing with the sub's crossover. Punch lives at 229Hz. Mids are lifted at 879Hz–3.1kHz to balance against the sub's weight.

### How to load EARS presets

1. Install Node.js, then run:
   ```bash
   cd ears
   npm run concat
   ```
2. Copy the one-liner JSON output.
3. Open Chrome DevTools (`F12`) on any tab.
4. Go to **Application → Local Storage → `chrome-extension://nfdfiepdkbnoanddpianalelglmfooik`**
5. Find or create the `PRESETS` key and paste the JSON as the value.
6. Reload the extension — presets appear in the dropdown.

---

## FXSound presets

| Preset | File | Character |
|---|---|---|
| **Pop** | `Pop.fac` | Balanced vocals and modern synth-pop |
| **Rap** | `rap.fac` | Vocal mids and bass for rap clarity |
| **Trap Metal** | `Trapmetal.fac` | Aggressive lows and highs |
| **Lo-Fi** | `lofi.fac` | Warm analog chill, rolled-off highs |

### How to load FXSound presets

1. Open **FXSound**
2. Go to `Settings → Presets → Import`
3. Select the `.fac` file from `fxsound/presets/`
4. Apply and enjoy

---

## Cross-reference

`preset-map.json` maps each genre to its closest EARS and FXSound equivalent, with notes on the differences. Useful when you want the same vibe in both apps but need to know which knobs differ.

---

## EQ band reference (EARS)

| Band | Frequency | Zone |
|---|---|---|
| 1 | ~7 Hz | Sub-bass — deferred to bandpass sub |
| 2 | ~37 Hz | Deep bass — deferred to bandpass sub |
| 3 | ~112 Hz | Bass body / sub handoff |
| 4 | ~229 Hz | **Punch zone** — kick attack, 808 thwack |
| 5 | ~426 Hz | Low-mids — cut slightly to clean mud |
| 6 | ~879 Hz | Presence / upper-mids |
| 7 | ~1.7 kHz | Vocal attack, guitar bite |
| 8 | ~3.1 kHz | Detail, snare crack |
| 9 | ~7.9 kHz | Brightness |
| 10 | ~12.7 kHz | Air |
| 11 | ~20.2 kHz | Ultra-air |

---

## Contributing

These are personal presets but PRs are welcome. Add FXSound presets as `.fac` files under `fxsound/presets/`, and EARS presets as entries in `ears/presets/Presets.json`. Update `preset-map.json` if there's a cross-tool equivalent.

---

## License

MIT — use, fork, modify freely.  
FXSound presets originally from [Efeckc17/fxsound-presets](https://github.com/Efeckc17/fxsound-presets), also MIT licensed.
