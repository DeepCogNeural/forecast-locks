# Locked revenue forecasts: fingerprints only

This repository records SHA-256 fingerprints of two forecast files from a study of when a language model's reading of company filings should change a revenue forecast. The forecasts were fixed before the companies reported the quarters they forecast. The files themselves are private; a fingerprint reveals nothing about their contents.

## Fingerprints

| Forecast set | Fixed on (US Eastern) | Forward-eligible forecasts | SHA-256 of forecasts.csv |
|---|---|---:|---|
| Forecast pipeline | 2026-10-08 | 175 | `c0dd68d18ad5d18b3ef5b444537ef2c8380ec208f3f6998fcec23e65bded2dd1` |
| Extraction plus arithmetic | 2026-10-17 | 32 | `1bffae6978129b7bba7c86d4962bd587bceba863b0913982ac0e9bb20ab07742` |

The fingerprints cover the full files, including rows excluded from the forward-eligible counts. They became public on 2026-10-17 US Eastern (2026-10-18 UTC). The earlier lock dates come from the private research log; this posting does not independently prove them.

## How to check

If the forecast files are released, anyone can confirm they are unchanged:

```
shasum -a 256 forecasts.csv
```

The output must equal the fingerprint above. A single changed character gives a different fingerprint.
