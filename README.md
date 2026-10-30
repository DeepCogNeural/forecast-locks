# Locked revenue forecasts: fingerprints only

This repository records SHA-256 fingerprints of five forecast files from a study of when a language model's reading of company filings should change a revenue forecast. The forecasts were fixed before the companies reported the quarters they forecast. The files themselves are private; a fingerprint reveals nothing about their contents.

## Fingerprints

| Forecast set | Fixed on (US Eastern) | Forward-eligible forecasts | SHA-256 of forecasts.csv |
|---|---|---:|---|
| Forecast pipeline | 2026-10-08 | 175 | `c0dd68d18ad5d18b3ef5b444537ef2c8380ec208f3f6998fcec23e65bded2dd1` |
| Extraction plus arithmetic | 2026-10-17 | 32 | `1bffae6978129b7bba7c86d4962bd587bceba863b0913982ac0e9bb20ab07742` |
| Extraction plus a pooled shift of 2.138 pp | 2026-10-21 (private commit 3fb0f4c, 22:38 ET) | 32 | `7835fbf8a96ccbb3365e84f2b9ae89d6b9b6719b934947ff8253bb772f47c3a1` |
| Extraction plus half the firm's own prior beat, half the pooled shift | 2026-10-22 (private commit fa38ffe, 00:31 ET) | 32 | `c6f8c80bf1074db99484f11c4e81e920ca711b400fe51c8b52d47ef1db04113d` |
| Extraction plus the firm's beat habit (weight n/(n+2), pooled 1.954 pp) | 2026-10-22 (private commit 266adc8, 09:50 ET) | 32 | `bb7dc51c3bc1efb6008ebf93e493fb2720df5737f23ba991dc37e1feeaf95fa7` |

The fingerprints cover the full files, including rows excluded from the forward-eligible counts. The first two became public on 2026-10-17 US Eastern (2026-10-18 UTC). The three later files were locked in the private repository on 2026-10-21 and 2026-10-22 at the commit times shown, and were posted here on 2026-10-30 US Eastern. The public posting date is the day of posting, not the lock date: by 2026-10-28 six of the 32 covered issuers had already filed an earnings release, so for those three files the private commit timestamps, which the public cannot check, are the only evidence that the forecasts came first. The hashes let anyone check later that the files scored are the files fingerprinted here. All five files hold 176 rows; the four extraction-based files change only the 32 rows with a usable stated figure.

## How to check

If the forecast files are released, anyone can confirm they are unchanged:

```
shasum -a 256 forecasts.csv
```

The output must equal the fingerprint above. A single changed character gives a different fingerprint.
