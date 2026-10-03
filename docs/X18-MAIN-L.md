# X18 Main L — Vocal / Speech Return to PreSonus

X18 Main L is a mono vocal/speech subgroup returned to a PreSonus input for FOH.

Recommended starting balance:

| Ch | Source | Main L |
|---:|---|---:|
| 1 | Shure Wireless 1 — Speaker | 0 dB |
| 2 | Shure Wireless 2 — WL | 0 dB |
| 3 | AWL Vox 1 | -3 dB |
| 4 | AWL Vox 2 | -3 dB |
| 5 | AWL Vox 3 | -3 dB |
| 6 | MD Key/Bass/Gtr | OFF |
| 7 | PA Mic | OFF |
| 8 | PreSonus Band | **OFF — mandatory** |
| 9 | Additional Wireless | 0 dB when used; otherwise mute/off |

## Main L processing

- EQ: Flat initially.
- Compressor: Off initially or very light 2:1 with only ~1–2 dB normal GR.
- Limiting: safety only if required.
- Avoid heavy bus processing because individual microphones are already processed.
- Maintain sensible output/reference level into the PreSonus line/input stage.

## Ownership

Once vocals are combined into Main L, PreSonus cannot rebalance WL vs AWL vs speaker. **That balance belongs to X18.** PreSonus treats the return as a vocal/speech subgroup.

## Mandatory exclusions

- Ch 6 MD: use Bus 6 communication path.
- Ch 7 PA: use Bus 6 communication path unless an explicit FOH requirement changes this.
- Ch 8 PreSonus Band: always OFF from Main L to prevent a feedback loop.
