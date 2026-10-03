# Complete HSGKK Audio Topology

## 1. Mixer roles

**Behringer X Air X18:** vocal/speech inputs, vocalist IEMs, MD/PA communication, mono vocal/speech subgroup.

**PreSonus StudioLive 16R:** instruments, dedicated RCA media input, musician IEM buses, final FOH mix and USB audio to OBS.

## 2. PreSonus input map

| Ch | Source | Notes |
|---:|---|---|
| 1–2 | Reserved | |
| 3 | Drum Kick | |
| 4 | Drum Tom | |
| 5 | Drum OH | Phantom-powered mic |
| 6 | Drum Snare | |
| 7 | Guitar 2 | |
| 8 | Bass | Phantom-powered DI |
| 9 | Keyboard | Phantom-powered DI |
| 10 | Guitar 1 | |
| 11 | Drum MD Mic | Direct musician communication |
| 12 | X18 Bus 6 | MD Key/Gtr/Bass + PA return |
| 13 | X18 Main L | Singers/Speaker Vox subgroup |
| 14–15 | Reserved | **Not media inputs** |
| 16 | Click | Exclude FOH Main |
| 17 | Sequencer | |
| 18 | Reserved | |

## 3. Media and OBS paths

The StudioLive 16R has a dedicated unbalanced stereo RCA line-input pair, separate from the 16 mic/line inputs.

```text
MEDIA PLAYBACK
Windows PC analog stereo OUT
    -> stereo RCA
    -> PreSonus dedicated rear RCA stereo line input

OBS RECORDING
PreSonus USB Type-B
    -> Windows PC
    -> OBS
```

Do not document RCA playback as Ch 14/15 and do not document USB as the current playback source.

## 4. PreSonus musician monitor buses

| Bus | Mix | Physical path | Performer interface |
|---:|---|---|---|
| 1 | Drum IEM | Snake A | Behringer Powerplay PM1 — passive |
| 2 | Bass IEM | Snake B | Behringer Powerplay PM1 — passive |
| 3 | Band mix | X18 Ch 8 | Vocalist band reference |
| 4 | Keyboard IEM | Snake C | Behringer Powerplay P1 — active |
| 5 | Guitar 1 IEM | Snake D | Behringer Powerplay PM1 — passive |
| 6 | Guitar 2 IEM | Direct | M-VAVE wireless IEM |

## 5. X18 inputs

| Ch | Source | Use |
|---:|---|---|
| 1 | Shure Wireless 1 — Speaker | Main L + reference as required |
| 2 | Shure Wireless 2 — WL | Main L + vocalist IEM |
| 3 | AWL Vox 1 | Main L + vocalist IEM |
| 4 | AWL Vox 2 | Main L + vocalist IEM |
| 5 | AWL Vox 3 | Main L + vocalist IEM |
| 6 | MD Key/Bass/Gtr | Vocalist IEM + Bus 6 |
| 7 | PA Mic | Vocalist IEM + Bus 6 |
| 8 | PreSonus Bus 3 — Band | **Vocalist IEM only** |
| 9 | Additional Wireless | As required |
| 10–18 | Reserved | |

## 6. X18 outputs

| Output | Function | Destination |
|---|---|---|
| Bus 1 | AWL IEM | M-VAVE wireless IEM |
| Bus 2 | WL IEM | M-VAVE wireless IEM — older version |
| Bus 3–5 | Reserved | |
| Bus 6 | MD/PA communication | PreSonus Ch 12 |
| Main L | Singers/Speaker Vox subgroup | PreSonus Ch 13 |

## 7. Communication paths

```text
Drum MD mic -> PreSonus Ch 11 -> selected musician IEM buses

MD Key/Gtr/Bass mic -> X18 Ch 6 --+
                                  +-> X18 Bus 6 -> PreSonus Ch 12
PA mic -------------> X18 Ch 7 --+
```

## 8. Vocal/speech FOH return

```text
Speaker / WL / AWL vocal mics
    -> X18
    -> X18 Main L
    -> PreSonus Ch 13
    -> PreSonus Main
```

## 9. Band reference to vocalists

```text
PreSonus band sources
    -> PreSonus Bus 3
    -> X18 Ch 8
    -> X18 Bus 1 AWL IEM / Bus 2 WL IEM
```

**Loop protection:** X18 Ch 8 -> Main L = OFF and X18 Ch 8 -> Bus 6 = OFF.

## 10. FOH PA topology

```text
                     PreSonus Main L/R
                            |
                            v
                         CROSSOVER
                    /         |         \
                  LOW        MID        HIGH
                   |          |           |
                   v          v           +--> UNUSED
             SUB POWER     TOP POWER           AVAILABLE
             AMPLIFIER     AMPLIFIER
               350 W        model/rating TBD
             /       \          |
          LEFT      RIGHT        +--> Top/Mid speaker 1 (wattage TBD)
       operational  damaged      +--> Top/Mid speaker 2 (wattage TBD)
           |
           v
     Single 15" sub
       500 W driver
```

Confirmed:
- LOW crossover range is used for the subwoofer.
- MID crossover range is used for the two top/mid speakers.
- HIGH crossover range is available but currently **unused**.
- One 15-inch 500 W subwoofer is in service.
- Subwoofer amplifier is 350 W; only its Left channel is operational. Right channel is damaged and unused.
- Top-speaker power amplifier exists, but model/rating is not yet identified.
- Two top/mid speakers are used; their wattage is not yet identified.
- Crossover model and crossover-frequency settings are not yet identified.

## 11. Control network

```text
Huawei Router / AP
       |
   Ethernet LAN
    /        \
PreSonus     X18
       |
Wi-Fi SSID: HSGKK 2022
       |
Laptop / iPhone / iPad / Android
```

Both mixers are wired by Ethernet. Wireless devices use the same HSGKK 2022 network for the appropriate PreSonus/X18/personal-monitor control apps.

## 12. Complete signal overview

```text
Windows PC --analog RCA------------------------> PreSonus
Windows PC <--USB / OBS------------------------- PreSonus

Drums / Guitars / Bass / Keyboard / Seq ------> PreSonus
                                                  |
       Bus1 -> Snake A -> PM1 -> Drum IEM <------+
       Bus2 -> Snake B -> PM1 -> Bass IEM <------+
       Bus4 -> Snake C -> P1  -> Key IEM  <------+
       Bus5 -> Snake D -> PM1 -> Gtr1 IEM <------+
       Bus6 -> M-VAVE -> Gtr2 IEM <--------------+
       Bus3 -> X18 Ch8 -> AWL/WL IEM <-----------+
                                                  |
Vocals/Speech -> X18 -> Main L -> PreSonus Ch13 -+
MD/PA --------> X18 -> Bus6  -> PreSonus Ch12 ---+
                                                  |
                                             PreSonus Main L/R
                                                  |
                                              Crossover
                                         /         |         \
                                      LOW         MID        HIGH
                                       |           |           |
                                      Sub        2 Tops       UNUSED
```

## 13. Safety invariants

1. X18 Ch 8 -> Main L = **OFF**.
2. X18 Ch 8 -> Bus 6 = **OFF**.
3. PreSonus Ch 16 Click -> FOH Main = **OFF**.
4. Verify connected equipment before changing phantom-power state.
5. Start IEM levels safely.
6. Do not use the damaged Right channel of the current sub amplifier.
7. Do not invent top-speaker wattage, top-amp rating, crossover model or crossover settings.
