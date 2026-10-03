# HSGKK Audio Topology

Current operational source of truth for the HSGKK church audio system.

## Core architecture

- **PreSonus StudioLive 16R** — instruments, dedicated stereo RCA media return, musician IEMs, FOH Main, USB recording interface to OBS.
- **Behringer X Air X18** — singers/speech, vocalist IEMs, MD/PA communication.
- **Media Workstation (Windows)** — analog stereo playback to the PreSonus rear RCA input; OBS receives audio from PreSonus over USB.
- Both mixers are wired by Ethernet into the LAN behind the Huawei router/AP.
- Wireless control devices join SSID **HSGKK 2022**.

## PreSonus input map — current installation

| Ch | Source | Notes |
|---:|---|---|
| 1 | Reserved | |
| 2 | Reserved | |
| 3 | Drum Kick | |
| 4 | Drum Tom | |
| 5 | Drum OH | Phantom-powered microphone |
| 6 | Drum Snare | |
| 7 | Guitar 2 | |
| 8 | Bass | Phantom-powered DI box |
| 9 | Keyboard | Phantom-powered DI box |
| 10 | Guitar 1 | |
| 11 | Drum MD Mic | Direct to PreSonus |
| 12 | X18 Bus 6 | MD Key/Gtr/Bass + PA communication return |
| 13 | X18 Main L | Singers/Speaker Vox subgroup |
| 14 | Reserved | |
| 15 | Reserved | |
| 16 | Click | Keep out of FOH Main |
| 17 | Sequencer | |
| 18 | Reserved | |

**Media is not Ch 14/15.** The Windows workstation feeds the StudioLive 16R's dedicated rear stereo RCA line-input pair.

## PreSonus buses / musician IEM

| Bus | Musician / mix | Connection | IEM interface / destination |
|---:|---|---|---|
| 1 | Drum IEM | Snake A | Behringer Powerplay PM1 (passive) |
| 2 | Bass IEM | Snake B | Behringer Powerplay PM1 (passive) |
| 3 | Band mix | Direct to X18 | X18 Ch 8 — vocalist band reference |
| 4 | Keyboard IEM | Snake C | Behringer Powerplay P1 (active) |
| 5 | Guitar 1 IEM | Snake D | Behringer Powerplay PM1 (passive) |
| 6 | Guitar 2 IEM | Direct | M-VAVE wireless IEM |

## X18 inputs

| Ch | Source |
|---:|---|
| 1 | Shure Wireless 1 — Speaker |
| 2 | Shure Wireless 2 — WL |
| 3 | AWL Vox 1 |
| 4 | AWL Vox 2 |
| 5 | AWL Vox 3 |
| 6 | MD Key/Bass/Gtr Mic |
| 7 | PA Mic |
| 8 | PreSonus Bus 3 — Band mix |
| 9 | Additional Wireless Mic |
| 10–18 | Reserved |

## X18 outputs

| Output | Mix | Destination |
|---|---|---|
| Bus 1 | AWL IEM | M-VAVE wireless IEM |
| Bus 2 | WL IEM | M-VAVE wireless IEM — older version |
| Bus 3–5 | Reserved | |
| Bus 6 | MD/PA communication | PreSonus Ch 12 |
| Main L | Singers/Speaker Vox subgroup | PreSonus Ch 13 |

## Media + OBS

```text
PLAYBACK
Windows Media Workstation analog stereo OUT
        -> stereo RCA cable
        -> PreSonus dedicated rear stereo RCA line input

RECORDING
PreSonus USB Type-B audio
        -> Windows Media Workstation
        -> OBS
```

These are two independent directional paths. USB is not the current media-playback path.

## FOH loudspeaker path

```text
PreSonus Main L/R
       |
       v
    Crossover
   /    |     \
 LOW   MID    HIGH
  |     |       |
  |     |       +--> UNUSED / AVAILABLE
  |     |
  |     +--> Top speaker power amp
  |             +--> Top/Mid speaker 1
  |             +--> Top/Mid speaker 2
  |
  +--> Subwoofer power amp (350 W)
          Left channel operational
          Right channel damaged / unused
             |
             +--> single 15" subwoofer, 500 W
```

Top-speaker amplifier model/rating, top-speaker wattage and crossover settings remain **TBD**. Do not infer them.

## Control network

Both mixers connect by Ethernet to the LAN behind the Huawei router/AP. Laptop, iPhone/iPad and Android control devices use Wi-Fi SSID **HSGKK 2022**.

## Critical loop protection

- X18 Ch 8 originates from PreSonus Bus 3.
- **X18 Ch 8 -> Main L = OFF.**
- **X18 Ch 8 -> Bus 6 = OFF.**
- X18 Bus 6 -> PreSonus Ch 12.
- X18 Main L -> PreSonus Ch 13.
- PreSonus Ch 16 Click stays out of FOH Main.

## Detailed documentation

- [Complete physical topology](docs/TOPOLOGY.md)
- [PreSonus production EQ & compression baseline](docs/PRESONUS-PRODUCTION-EQ.md)
- [X18 channel processing](docs/X18-PROCESSING.md)
- [X18 Bus 1 — AWL IEM](docs/X18-BUS-1-AWL-IEM.md)
- [X18 Bus 2 — WL IEM](docs/X18-BUS-2-WL-IEM.md)
- [X18 Bus 6 — MD/PA return](docs/X18-BUS-6-MD-PA.md)
- [X18 Main L](docs/X18-MAIN-L.md)
- [Soundcheck and safety](docs/SOUNDCHECK.md)

## Status convention

Physical routing/channel assignments above are the **current installation**. EQ/compressor values in detailed documents are starting references and remain subject to soundcheck.
