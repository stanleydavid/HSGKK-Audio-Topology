# Complete HSGKK Audio Topology

## 1. Mixer responsibility

### PreSonus StudioLive 16R
Owns instruments, media return, musician monitor buses, FOH Main and USB recording output to the Windows/OBS workstation.

### Behringer X Air X18
Owns vocal/speech microphones, AWL/WL IEM mixes, MD/PA communication mix, and the mono vocal/speech subgroup returned to PreSonus.

## 2. PreSonus input map

| Ch | Source | Power / role |
|---:|---|---|
| 1 | Reserved | |
| 2 | Reserved | |
| 3 | Drum Kick | Drum |
| 4 | Drum Tom | Drum |
| 5 | Drum OH | **Phantom-powered mic** |
| 6 | Drum Snare | Drum |
| 7 | Guitar 2 | Instrument |
| 8 | Bass | **Phantom-powered DI box** |
| 9 | Keyboard | **Phantom-powered DI box** |
| 10 | Guitar 1 | Instrument |
| 11 | Drum MD Mic | Musician communication source |
| 12 | X18 Bus 6 | MD Key/Gtr/Bass + PA communication return |
| 13 | X18 Main L | Singers/Speaker Vox return |
| 14 | Reserved | |
| 15 | Reserved | |
| 16 | Click | Monitor only; exclude FOH |
| 17 | Sequencer | |
| 18 | Reserved | |

**Important:** Media playback is not Ch 14–15. It enters the dedicated rear stereo RCA line input.

## 3. Media Workstation

The Windows Media Workstation has two independent connections to the PreSonus.

### Playback: PC → PreSonus
```text
Windows PC analog audio OUT
        -> RCA stereo cable
        -> PreSonus rear RCA stereo line input
        -> PreSonus mix
```

The StudioLive 16R has a dedicated unbalanced stereo RCA line-input pair. It does not require physical mic/line Ch 14–15.

### Recording: PreSonus → PC
```text
PreSonus USB Type-B audio interface
        -> Windows Media Workstation
        -> OBS recording
```

USB is therefore a recording/capture path in the current HSGKK installation; analog RCA is the current media playback path.

## 4. PreSonus buses and monitor distribution

| Bus | Mix | Output destination |
|---:|---|---|
| 1 | Drum IEM | Snake A |
| 2 | Bass IEM | Snake B |
| 3 | Band mix | X18 Ch 8 |
| 4 | Keyboard IEM | Snake C |
| 5 | Guitar 1 IEM | Snake D |
| 6 | Guitar 2 IEM | M-VAVE wireless IEM |

Bus 3 is not used for OBS. OBS receives audio over the PreSonus USB connection.

## 5. X18 inputs

| Ch | Source | Use |
|---:|---|---|
| 1 | Shure Wireless 1 — Speaker | FOH subgroup + IEM reference |
| 2 | Shure Wireless 2 — WL | FOH subgroup + vocalist IEM |
| 3 | AWL Vox 1 | FOH subgroup + vocalist IEM |
| 4 | AWL Vox 2 | FOH subgroup + vocalist IEM |
| 5 | AWL Vox 3 | FOH subgroup + vocalist IEM |
| 6 | MD Key/Bass/Gtr | Vocalist IEM + Bus 6 |
| 7 | PA Mic | Vocalist IEM + Bus 6 |
| 8 | PreSonus Bus 3 — Band | **Vocalist IEM only** |
| 9 | Additional Wireless | As required |
| 10–18 | Reserved | |

## 6. X18 outputs

| Output | Function | Destination |
|---|---|---|
| Bus 1 | AWL IEM | M-VAVE wireless IEM |
| Bus 2 | WL IEM | M-VAVE wireless IEM — old version |
| Bus 3 | Reserved | |
| Bus 4 | Reserved | |
| Bus 5 | Reserved | |
| Bus 6 | MD/PA communication | PreSonus Ch 12 |
| Main L | Singers/Speaker Vox subgroup | PreSonus Ch 13 |

## 7. MD communication architecture

Two MD microphone paths are intentionally separate.

### Drum MD
```text
Drum-cage MD mic -> PreSonus Ch 11 -> selected musician IEM buses
```

Because this microphone can carry drum bleed, each musician can decide how much to hear. It does not need to be included in the Band mix sent to vocalists.

### Key/Guitar/Bass MD + PA
```text
MD Key/Gtr/Bass mic -> X18 Ch 6 --+
                                  +-> X18 Bus 6 -> PreSonus Ch 12
PA mic -------------> X18 Ch 7 --+
```

This is the clean communication path for musicians and vocalist communication.

## 8. Vocal/speech FOH return

```text
Speaker / WL / AWL vocal microphones
        -> X18
        -> X18 Main L
        -> PreSonus Ch 13
        -> PreSonus Main
        -> crossover / FOH loudspeaker system
```

The individual vocal balance belongs to X18. PreSonus receives it as one mono subgroup.

## 9. Band reference to vocalists

```text
PreSonus instruments + required media
        -> PreSonus Bus 3 Band mix
        -> X18 Ch 8
        -> X18 Bus 1 AWL IEM
        -> X18 Bus 2 WL IEM
```

**X18 Ch 8 must never be routed to X18 Bus 6 or Main L.** Both return to PreSonus and would create a PreSonus → X18 → PreSonus loop.

## 10. FOH speaker topology

```text
PreSonus StudioLive Main outputs
              |
              v
           Crossover
          /         \
       LOW           MID
        |             |
        v             v
Subwoofer amp      Top speaker amp
350 W amp             |
Left channel good     +--> Top/Mid 1
Right damaged         +--> Top/Mid 2
        |
        v
Single 15" subwoofer
500 W driver
```

Current known condition:
- One 15-inch subwoofer driver in use.
- Sub driver rating: 500 W.
- Sub power amplifier: 350 W; only Left channel currently operational; Right channel damaged.
- Two top/midrange speakers in use.
- Top speaker amplifier feeds those two speakers.
- Top/mid speaker wattage is **TBD**.
- Exact crossover output topology/settings and amplifier/speaker model numbers should be recorded after physical identification.

## 11. Control network

Both mixers use wired Ethernet to the network behind the Huawei router/access point.

```text
                    Huawei Router / AP
                           |
                     Ethernet LAN
                    /             \
        PreSonus StudioLive       Behringer X18
                    \             /
                     Wi-Fi clients
                    SSID: HSGKK 2022
                           |
        +------------------+------------------+
        |                  |                  |
      Laptop          iPhone/iPad         Android
        |                  |                  |
 mixer control / personal IEM control applications
```

Known application families in use include PreSonus control/personal-monitor apps and X18-compatible control apps, including QMix-UC/Mix-Q where applicable. Exact installed app/device mapping and versions should be inventoried before treating app naming as locked.

## 12. Complete signal overview

```text
MEDIA PC --RCA----------------------> PreSonus
MEDIA PC <--USB / OBS--------------- PreSonus

DRUMS/GUITARS/BASS/KEY/SEQ --------> PreSonus
                                      |
                                      +--> Buses 1/2/4/5 -> Snake A/B/C/D -> musician IEM
                                      +--> Bus 6 -> M-VAVE -> Guitar 2 IEM
                                      +--> Bus 3 Band -> X18 Ch 8 -> vocalist IEM
                                      |
VOCALS/SPEECH -> X18 -> Main L ------+ Ch 13
MD/PA --------> X18 -> Bus 6 --------+ Ch 12
                                      |
                                      v
                                 PreSonus Main
                                      |
                                  Crossover
                                  /       \
                               Sub         Tops
```

## 13. Safety invariants

1. X18 Ch 8 -> Main L = **OFF**.
2. X18 Ch 8 -> Bus 6 = **OFF**.
3. PreSonus Ch 16 Click -> FOH Main = **OFF**.
4. Phantom power is required on the documented Drum OH, Bass DI and Keyboard DI channels; verify connected equipment before changing phantom-power state.
5. IEM outputs must start at safe listening levels.
6. Do not document an unknown top-speaker wattage, crossover frequency or amplifier model by assumption.
