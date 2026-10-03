# HSGKK Audio Topology

Current operational source of truth for the HSGKK church audio system.

## Core architecture

- **PreSonus StudioLive 16R** — instruments, media return, musician IEMs, FOH Main, USB recording interface to OBS.
- **Behringer X Air X18** — singers/speech, vocalist IEMs, MD/PA communication.
- **Media Workstation (Windows)** — media playback to PreSonus over analog RCA and OBS recording from PreSonus over USB.
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
| 14 | Reserved | Media does NOT use Ch 14–15 |
| 15 | Reserved | Media does NOT use Ch 14–15 |
| 16 | Click | Keep out of FOH Main |
| 17 | Sequencer | |
| 18 | Reserved | |

## PreSonus buses

| Bus | Mix | Physical destination |
|---:|---|---|
| 1 | Drum IEM | Snake channel A |
| 2 | Bass IEM | Snake channel B |
| 3 | Band mix | X18 Ch 8 |
| 4 | Keyboard IEM | Snake channel C |
| 5 | Guitar 1 IEM | Snake channel D |
| 6 | Guitar 2 IEM | M-VAVE wireless IEM |

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

## X18 buses

| Bus | Mix | Destination |
|---:|---|---|
| 1 | AWL IEM | M-VAVE wireless IEM |
| 2 | WL IEM | M-VAVE wireless IEM — older version |
| 3 | Reserved | |
| 4 | Reserved | |
| 5 | Reserved | |
| 6 | MD/PA communication | PreSonus Ch 12 |

**X18 Main L → PreSonus Ch 13** carries the Singers/Speaker Vox subgroup.

## Media workstation

Two separate directional connections exist:

```text
PLAYBACK
Windows Media Workstation
    -> analog audio output
    -> stereo RCA cable
    -> PreSonus rear stereo RCA line input

RECORDING
PreSonus USB audio
    -> Windows Media Workstation
    -> OBS
```

The rear RCA stereo input is separate from physical input channels 1–16. Therefore Ch 14–15 are not the media inputs.

## FOH loudspeaker path

```text
PreSonus Main outputs
        |
        v
     Crossover
      /     \
 LOW          MID
  |            |
  v            v
Sub power    Top speaker
amplifier    power amplifier
  |            |
  v            +--> Top/Mid speaker 1
15" Sub        +--> Top/Mid speaker 2
500 W
```

Current sub amplifier: **350 W amplifier; Left channel operational, Right channel damaged.** Only one 15-inch 500 W subwoofer driver is currently used.

Top/mid speaker wattage: **TBD — identify from equipment.**

## Control network

```text
Huawei Router / AP
        |
   Ethernet LAN
     /       \
PreSonus     X18
     \       /
      HSGKK 2022 Wi-Fi
          |
 Laptop / iPhone / Android / iPad
          |
 mixer control + personal monitor apps
```

PreSonus control uses its supported control/personal-monitor applications (including QMix-UC where applicable). X18 is controlled using the installed X18-compatible control apps. App names/versions on each device should be inventoried separately rather than assumed.

## Critical loop protection

- X18 Ch 8 originates from PreSonus Bus 3.
- **Ch 8 → X18 Main L = OFF.**
- **Ch 8 → X18 Bus 6 = OFF.**
- X18 Bus 6 returns to PreSonus Ch 12.
- X18 Main L returns to PreSonus Ch 13.
- Click Ch 16 stays out of FOH Main.

## Detailed documentation

- [Complete physical topology](docs/TOPOLOGY.md)
- [X18 channel processing](docs/X18-PROCESSING.md)
- [X18 Bus 1 — AWL IEM](docs/X18-BUS-1-AWL-IEM.md)
- [X18 Bus 2 — WL IEM](docs/X18-BUS-2-WL-IEM.md)
- [X18 Bus 6 — MD/PA return](docs/X18-BUS-6-MD-PA.md)
- [X18 Main L](docs/X18-MAIN-L.md)
- [Soundcheck and safety](docs/SOUNDCHECK.md)

## Status convention

Physical routing/channel assignments above are the **current locked installation**. Mix levels, EQ and compressor settings in the detailed documents are **starting values** and remain subject to soundcheck.
