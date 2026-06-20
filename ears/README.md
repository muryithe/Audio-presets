# EARS presets

JSON presets for the [EARS – Bass Boost & EQ](https://chrome.google.com/webstore/detail/ears-bass-boost-eq-any-au/nfdfiepdkbnoanddpianalelglmfooik) Chrome extension.

## How to load

```bash
npm run concat
```

Copy the output JSON. In Chrome DevTools (`F12`), go to **Application → Local Storage → `chrome-extension://nfdfiepdkbnoanddpianalelglmfooik`**, set the `PRESETS` key to the copied JSON, and reload the extension.

## Tuning notes

All presets are calibrated for **bookshelf speakers + a 6th order bandpass subwoofer:**
- Bands 1–2 (7Hz, 37Hz) are cut in all presets — the sub handles this range
- Band 4 (229Hz) carries the punch in every music preset
- Band 5 (426Hz) is slightly dipped to reduce boxiness from the bookshelves
- Bands 6–8 (879Hz–3.1kHz) are lifted to balance mids against the sub's weight

See the root `README.md` for the full preset table and band reference.
