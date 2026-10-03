# Complete HSGKK Audio Topology

## Design intent

The system deliberately splits responsibility between two mixers according to who needs discrete control:

- X18 owns vocal/speech sources and vocalist IEM mixes.
- PreSonus owns instruments/media, musician IEM mixes, FOH, and OBS feed.
- A single curated Band + Media mix crosses from PreSonus to X18.
- Vocal/speech and MD/PA references cross back from X18 to PreSonus on separate paths.

This avoids using a PC as an audio-routing bridge and preserves independent monitor control where it matters.

## X18 inputs

| Ch | Source | Routing intent |
|---:|---|---|
| 1 | Shure Wireless 1 — Speaker | Main L; IEM reference as required |
| 2 | Shure Wireless 2 — WL | Main L; WL/AWL IEMs |
| 3 | AWL Vox 1 | Main L; vocalist IEMs |
| 4 | AWL Vox 2 | Main L; vocalist IEMs |
| 5 | AWL Vox 3 | Main L; vocalist IEMs |
| 6 | MD Key/Bass/Gtr Mic | Vocalist IEMs + Bus 6 |
| 7 | PA Mic | Vocalist IEMs + Bus 6 |
| 8 | PreSonus Bus 3 — Band + Media | Vocalist IEMs ONLY |
| 9 | Additional Wireless | As required |
| 10–18 | Reserved | Future |

## X18 buses

| Bus | Destination | Function |
|---:|---|---|
| 1 | AWL IEM | Shared AWL vocalist monitor mix |
| 2 | WL IEM | Worship Leader monitor mix |
| 3 | Reserved | Future |
| 4 | Reserved | Future |
| 5 | Reserved | Future |
| 6 | PreSonus input | MD + PA communication reference for musicians |

## PreSonus buses

| Bus | Destination |
|---:|---|
| 1 | Drum IEM |
| 2 | Bass IEM |
| 3 | X18 Ch 8 — Band + Media for vocalists |
| 4 | Keyboard IEM |
| 5 | Guitar 1 IEM |
| 6 | Guitar 2 wireless IEM |

## PreSonus inputs / source plan

Current source plan discussed for the 16 physical channels:

| Ch | Source |
|---:|---|
| 1 | Keyboard |
| 2 | Acoustic Guitar |
| 3 | Electric Guitar |
| 4 | Bass |
| 5 | Kick |
| 6 | Snare |
| 7 | Tom |
| 8 | Overhead |
| 9 | Media L |
| 10 | Media R |
| 11 | X18 Main L — Vocal/Speech return |
| 12 | X18 Bus 6 — MD/PA return |
| 13 | MD Drum Cage Mic |
| 14 | Sequencer L |
| 15 | Sequencer R |
| 16 | Click / Cue |

The physical input plan is operationally useful but should be updated here if cabling changes.

## Two MD microphone design

There are intentionally two MD paths:

1. **MD Drum Cage Mic -> PreSonus Ch 13.** It remains discrete in PreSonus. Each musician decides whether/how much to hear it. Keyboard can keep it off/low because drum-cage bleed can be excessive.
2. **MD Key/Bass/Gtr Mic -> X18 Ch 6.** It is the cleaner MD source for vocalist IEMs and is included in X18 Bus 6 for musician reference.

Do not automatically put the Drum Cage MD into PreSonus Bus 3. Keeping it out prevents drum-cage bleed from being carried into vocalist IEMs.

## Sequencer

Suggested use of remaining PreSonus channels:
- Ch 14 — Sequencer L
- Ch 15 — Sequencer R
- Ch 16 — Click/Cue

Sequencer L/R may feed FOH and required monitor buses. Click/Cue must remain out of FOH Main and be sent only to musicians who need it.

## OBS

Old arrangement used PreSonus Bus 3 for OBS. Current arrangement:
- **PreSonus Main L/R -> OBS via USB**
- Bus 3 is therefore dedicated to Band + Media -> X18.

OBS receives the same core FOH mix rather than consuming a monitor bus.

## Signal-flow summary

```text
INSTRUMENTS / MEDIA / SEQUENCER
            |
            v
     PreSonus StudioLive 16R
       |              |
       | Bus 3        | Main L/R
       | Band+Media   +----> PA / FOH
       v              +----> OBS via USB
     X18 Ch 8
       |
       +----> X18 Bus 1 AWL IEM
       +----> X18 Bus 2 WL IEM
       +----> future vocalist buses
       X NOT Main L
       X NOT Bus 6

VOCALS / WL / SPEAKER ---> X18 ---> Main L ---> PreSonus ---> FOH
MD KEY + PA -----------> X18 ---> Bus 6 ----> PreSonus ---> musician buses
MD DRUM ---------------> PreSonus directly ---> selected musician buses
```

## Feedback-loop protection

The highest-risk routing error is allowing the PreSonus return on X18 Ch 8 to return to PreSonus again.

Therefore:
- Ch 8 -> Main L = OFF.
- Ch 8 -> Bus 6 = OFF.
- Any future X18 output returning to PreSonus must explicitly exclude Ch 8 unless a loop-safe design is documented.
