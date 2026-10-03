# HSGKK Soundcheck & Safety Checklist

## Source / return verification

- PreSonus Ch 3 Kick, Ch 4 Tom, Ch 5 OH, Ch 6 Snare.
- Ch 5 Drum OH phantom power as required by installed mic.
- Ch 8 Bass DI and Ch 9 Keyboard DI phantom power as required by installed DI boxes.
- X18 Bus 6 -> PreSonus Ch 12.
- X18 Main L -> PreSonus Ch 13.
- Ch 14 and Ch 15 remain reserved; **media is not routed through them**.
- Ch 16 Click excluded from FOH Main.
- Ch 17 Sequencer present.
- Windows workstation analog stereo output -> PreSonus dedicated rear RCA stereo input.
- PreSonus USB Type-B -> Windows workstation -> OBS.

## PreSonus musician monitor outputs

- Bus 1 Drum -> Snake A -> **Behringer Powerplay PM1 (passive)**.
- Bus 2 Bass -> Snake B -> **Behringer Powerplay PM1 (passive)**.
- Bus 3 Band -> X18 Ch 8.
- Bus 4 Keyboard -> Snake C -> **Behringer Powerplay P1 (active)**.
- Bus 5 Guitar 1 -> Snake D -> **Behringer Powerplay PM1 (passive)**.
- Bus 6 Guitar 2 -> **M-VAVE wireless IEM**.

## X18 outputs

- Bus 1 AWL -> M-VAVE wireless IEM.
- Bus 2 WL -> older-version M-VAVE wireless IEM.
- Bus 6 MD/PA -> PreSonus Ch 12.
- Main L Singers/Speaker Vox -> PreSonus Ch 13.

## Loop-protection test

Before raising system level:
- X18 Ch 8 -> Main L = OFF.
- X18 Ch 8 -> Bus 6 = OFF.
- Raising PreSonus Bus 3 affects vocalist Band reference only.
- Raising X18 Bus 6 affects the PreSonus MD/PA return only.
- Raising X18 Main L affects the PreSonus vocal/speech return only.
- Verify no self-sustaining level increase.

## FOH loudspeaker path

- PreSonus Main L/R -> crossover.
- Crossover **LOW** -> subwoofer power amplifier -> single 15-inch 500 W subwoofer.
- Current subwoofer amplifier is 350 W; **Left channel operational**.
- Subwoofer amplifier **Right channel damaged / unused**.
- Crossover **MID** -> top-speaker power amplifier -> two top/mid speakers.
- Crossover **HIGH = unused / available**.
- Top amplifier model/rating = TBD.
- Top speaker wattage = TBD.
- Crossover model/settings = TBD.
- Do not change crossover points or amplifier gain from undocumented assumptions.

## Network control

- PreSonus Ethernet connected to LAN behind Huawei router/AP.
- X18 Ethernet connected to same LAN.
- Wi-Fi SSID: HSGKK 2022.
- Confirm required laptop/iOS/iPad/Android control devices can reach their mixer.
- Confirm personal monitor control works where used.

## Gain / IEM safety

1. Set preamp gain before refining monitor sends.
2. Preserve headroom for performance peaks.
3. Set compressor thresholds from actual gain reduction.
4. Start IEM listening levels safely.
5. Verify X18 -> PreSonus return channels do not clip.
6. Confirm clean Main signal reaches crossover and amplifiers before raising PA level.
7. Do not use the damaged sub-amplifier Right channel.

## Change control

Physical routing changes belong in this repository. Performer-specific fader/EQ adjustments do not become fixed topology unless deliberately adopted as the new baseline.
