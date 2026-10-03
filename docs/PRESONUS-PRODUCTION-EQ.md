# PreSonus StudioLive 16R — Production EQ & Compression Baseline

Operational starting reference for a **clean, balanced church production mix**. These are not mandatory curves.

## Operating rule

1. Set input gain correctly first.
2. Apply the HPF starting point.
3. **Cut only when the stated problem exists.**
4. **Boost only when the source is missing the stated quality.**
5. Keep broad musical shaping around Q 0.7–1.2. Use narrower Q 2–4 only for a specific resonance.
6. Compressor threshold is not fixed: adjust threshold to reach the stated target gain reduction (GR).
7. Ch 13 has already been processed on X18; keep additional PreSonus processing minimal.

## Instrument channels

| Ch | Source | HPF | Cut if needed | Boost if needed | Compression starting point |
|---:|---|---:|---|---|---|
| 3 | Kick | 35 Hz | -3 to -4 dB @ 300–400 Hz for box/mud | +2 to +3 dB @ 60–80 Hz for punch; +2 to +3 dB @ 3–5 kHz for attack | 4:1; attack 20–30 ms; release 80–120 ms; GR 3–5 dB |
| 4 | Tom | 45 Hz | -3 dB @ ~300 Hz for boom/mud | +2 to +3 dB @ 80–120 Hz for body; +2 to +3 dB @ 3–5 kHz for attack | 3:1; attack 20–30 ms; release 100–150 ms; GR 2–4 dB |
| 5 | Drum OH | 120–150 Hz | -2 dB @ 200–300 Hz if muddy; -2 dB @ 400–600 Hz if boxy | +1 to +2 dB @ 8–12 kHz only if cymbals need air | 2:1; attack ~25 ms; release ~120 ms; GR 1–3 dB |
| 6 | Snare | 80 Hz | -3 dB around 400 Hz–1 kHz where boxy | +2 dB @ 150–200 Hz for body; +2 to +3 dB @ 2–4 kHz for crack/presence | 4:1; attack 15–25 ms; release 80–120 ms; GR 3–5 dB |
| 7 | Guitar 2 | 80–100 Hz | -2 dB @ 125–250 Hz if boomy; -2 dB @ 300–400 Hz if muddy | +1 to +2 dB @ 2–3 kHz for clarity | 2:1; attack ~20 ms; release ~120 ms; GR 1–3 dB |
| 8 | Bass DI | 30–35 Hz | -3 dB @ 200–400 Hz for mud | +1 to +2 dB @ 70–100 Hz for fullness; +1 to +2 dB @ 600 Hz–1.5 kHz for definition | 4:1; attack 20–30 ms; release 100–150 ms; GR 4–6 dB |
| 9 | Keyboard DI | 50–80 Hz* | -2 dB @ 150–250 Hz if boomy; -2 dB @ 300–400 Hz if boxy | +1 to +2 dB @ 2–5 kHz only if clarity is needed | 2:1 or OFF; attack 20–30 ms; release ~120 ms; GR 1–3 dB |
| 10 | Guitar 1 | 80–100 Hz | -2 dB @ 125–250 Hz if boomy; -2 dB @ 300–400 Hz if muddy | +1 to +2 dB @ 2–3 kHz for presence | 2:1; attack ~20 ms; release ~120 ms; GR 1–3 dB |
| 16 | Click | 150 Hz | -2 dB @ ~400 Hz if boxy | +2 dB @ 2–4 kHz if more definition is required | Optional 2:1; GR 1–2 dB |
| 17 | Sequencer | 40 Hz | -1 dB @ 250–400 Hz only if muddy | Small presence/air adjustment only if required | Optional 2:1; GR 1–2 dB |

*Keyboard HPF depends on patch. Use roughly 40–50 Hz when low piano/synth content must remain; move toward 70–80 Hz when bass owns the low end.

## Communication and vocal returns

| Ch | Source | HPF | Cut if needed | Boost if needed | Compression |
|---:|---|---:|---|---|---|
| 11 | Drum MD | 120 Hz | -3 dB @ 200–300 Hz; -3 dB @ 400–600 Hz for boom/boxiness | +2 to +3 dB @ ~3 kHz for intelligibility | 3:1; attack ~20 ms; release ~120 ms; GR 2–4 dB |
| 12 | X18 Bus 6 MD/PA | 120 Hz | -3 dB @ 180–300 Hz; -3 dB @ 350–500 Hz | +2 to +3 dB @ ~3 kHz for intelligibility | 2:1; attack ~25 ms; release ~120 ms; GR 1–3 dB |
| 13 | X18 Main L Singers/Speaker Vox | 90 Hz | -2 dB @ 180–300 Hz; -2 dB @ 300–400 Hz only if required | +1 to +2 dB @ 2.5–3.5 kHz for presence; +1 dB @ 8–10 kHz only if air is missing | Gentle 2:1; attack 25–30 ms; release 120–180 ms; GR 1–3 dB max |

### Ch 13 rule

X18 owns the individual vocal EQ/dynamics. PreSonus Ch 13 is the **final vocal/speech subgroup**, so avoid aggressive second-stage EQ or compression. Use it mainly to make the subgroup sit correctly against the band and PA.

## Media RCA return

Start essentially flat:
- HPF: 30–40 Hz if useful.
- Small -1 dB around 200–300 Hz only if playback is muddy.
- Small high shelf only if playback genuinely lacks air.
- Compression: normally OFF.

Do not use channel EQ to compensate for poor source media.

## Mix-space priorities

### Low end
- Kick: emphasize roughly 60–80 Hz when needed.
- Bass: fullness roughly 70–100 Hz; definition 600 Hz–1.5 kHz.
- Avoid heavily boosting kick and bass at the same frequency.

### Low mids
The 200–400 Hz region can accumulate across drums, guitars, keys and vocals. Prefer small source-specific cuts rather than a large Main EQ cut.

### Vocal intelligibility
Keep the 2–5 kHz area available for vocals. Do not boost every guitar/keyboard/drum channel heavily in this range.

### Air
Use 8–12 kHz boosts sparingly. Condenser OH microphones and X18-processed vocals may already contain sufficient high-frequency energy.

## System EQ versus channel EQ

- **Channel EQ:** create separation and correct source-specific problems.
- **PreSonus Main/system EQ:** correct PA/room behaviour.
- **Crossover:** divide the loudspeaker frequency bands.

Do not use instrument channel EQ to compensate for the subwoofer, top speakers, amplifier condition, crossover or room.

## Status

These values are the HSGKK **production-mix baseline / starting reference**, not locked mandatory EQ. Final settings depend on performer, instrument, microphone/DI, source patch, gain structure, PA and room.
