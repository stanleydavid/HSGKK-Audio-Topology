# HSGKK Audio Topology

Operational documentation for the current HSGKK church audio system.

## System role split

- **PreSonus StudioLive 16R** — primary instrument/media mixer, musician IEM mixer, FOH mixer, and FOH Main L/R feed to OBS over USB.
- **Behringer X Air X18** — vocal/speech mixer and vocalist IEM mixer.
- **No PC is required in the live signal path.** OBS receives the PreSonus FOH Main via USB.
- **PreSonus Bus 3** sends a dedicated Band + Media reference mix to X18 Ch 8 for vocalist IEMs.
- **X18 Bus 6** returns MD/PA communication to PreSonus for musician reference.
- **X18 Main L** returns the vocal/speech subgroup to PreSonus for FOH.

## Locked X18 input assignment

| Ch | Source | Primary use |
|---:|---|---|
| 1 | Shure Wireless 1 | Speaker |
| 2 | Shure Wireless 2 | Worship Leader (WL) |
| 3 | AWL Vox 1 | Vocal |
| 4 | AWL Vox 2 | Vocal |
| 5 | AWL Vox 3 | Vocal |
| 6 | MD Key/Bass/Gtr Mic | Vocalist IEM + Bus 6 |
| 7 | PA Mic | Vocalist IEM + Bus 6 |
| 8 | PreSonus Band | Vocalist IEM only |
| 9 | Additional Wireless Mic | Additional wireless |
| 10–18 | Reserved | Future use |

## Locked X18 bus assignment

| Bus | Assignment |
|---:|---|
| 1 | AWL IEM |
| 2 | WL IEM |
| 3 | Empty / reserved |
| 4 | Empty / reserved |
| 5 | Empty / reserved |
| 6 | MD / PA return to PreSonus for musician reference |

## Locked PreSonus bus assignment

| Bus | Assignment |
|---:|---|
| 1 | Drum IEM |
| 2 | Bass IEM |
| 3 | Band + Media -> X18 Ch 8 |
| 4 | Keyboard IEM |
| 5 | Guitar 1 IEM |
| 6 | Guitar 2 IEM (wireless IEM) |

## Critical routing rules

1. **X18 Ch 8 (PreSonus Band) is vocalist-IEM-only.**
2. **Never send X18 Ch 8 to X18 Bus 6.**
3. **Never send X18 Ch 8 to X18 Main L.** This prevents PreSonus -> X18 -> PreSonus feedback.
4. X18 Bus 6 contains only the required MD/PA communication return.
5. X18 Main L is the vocal/speech return to PreSonus; MD/PA are excluded because they have Bus 6.
6. PreSonus Bus 3 is the dedicated Band + Media reference for vocalists.
7. PreSonus Main L/R remains the FOH mix and is also sent to OBS via USB; no PreSonus bus is consumed for OBS.
8. IEM sends should be **pre-fader** unless intentionally changed and documented.

## Documentation

- [Complete topology and signal flow](docs/TOPOLOGY.md)
- [X18 channel processing: EQ and dynamics](docs/X18-PROCESSING.md)
- [X18 Bus 1 — AWL IEM](docs/X18-BUS-1-AWL-IEM.md)
- [X18 Bus 2 — WL IEM](docs/X18-BUS-2-WL-IEM.md)
- [X18 Bus 6 — MD/PA return](docs/X18-BUS-6-MD-PA.md)
- [X18 Main L — vocal/speech return](docs/X18-MAIN-L.md)
- [Soundcheck and safety checklist](docs/SOUNDCHECK.md)

## Configuration status

The topology and channel/bus assignments above are **locked current configuration**. EQ, compressor, and mix-level values in the detailed documents are **recommended starting points** and must be fine-tuned against actual performers, microphones, gain structure, stage level, and venue acoustics.
