# HSGKK Soundcheck & Safety Checklist

## Routing verification

- PreSonus Ch 3 Kick, Ch 4 Tom, Ch 5 OH, Ch 6 Snare.
- Ch 5 Drum OH phantom power as required by the installed mic.
- Ch 8 Bass DI and Ch 9 Keyboard DI phantom power as required by the installed DI boxes.
- X18 Bus 6 appears on PreSonus Ch 12.
- X18 Main L appears on PreSonus Ch 13.
- Ch 14 and 15 remain reserved.
- Ch 16 Click is excluded from FOH Main.
- Ch 17 Sequencer is present.
- Media workstation analog output reaches the PreSonus rear RCA stereo input.
- PreSonus USB reaches the Windows Media Workstation and OBS.

## PreSonus monitor outputs

- Bus 1 Drum -> Snake A.
- Bus 2 Bass -> Snake B.
- Bus 3 Band -> X18 Ch 8.
- Bus 4 Keyboard -> Snake C.
- Bus 5 Guitar 1 -> Snake D.
- Bus 6 Guitar 2 -> M-VAVE wireless IEM.

## X18 monitor outputs

- Bus 1 AWL -> M-VAVE wireless IEM.
- Bus 2 WL -> older M-VAVE wireless IEM.
- Bus 6 MD/PA -> PreSonus Ch 12.
- Main L Singers/Speaker Vox -> PreSonus Ch 13.

## Loop-protection test

Before raising system level:
- X18 Ch 8 -> Main L = OFF.
- X18 Ch 8 -> Bus 6 = OFF.
- Raising PreSonus Bus 3 should affect vocalist Band reference only.
- Raising X18 Bus 6 should affect only the PreSonus MD/PA return.
- Raising X18 Main L should affect only the PreSonus vocal/speech return.
- Verify no self-sustaining level increase.

## FOH loudspeaker path

- PreSonus Main feeds crossover.
- Crossover Low path feeds the operational Left channel of the current sub amplifier.
- One 15-inch / 500 W subwoofer is currently in use.
- Sub amplifier Right channel is known damaged and must not be treated as available.
- Crossover Mid path feeds top-speaker amplifier.
- Two top/mid speakers are currently in use.
- Top speaker wattage remains TBD until physically identified.
- Do not change crossover points/amp gain based on undocumented assumptions.

## Network control

- PreSonus Ethernet connected to LAN behind Huawei router/AP.
- X18 Ethernet connected to same LAN.
- SSID: HSGKK 2022.
- Confirm laptop/iOS/iPad/Android control devices can reach their required mixer.
- Confirm musician personal-mix control works where used.

## Gain / IEM safety

1. Set preamp gain before refining monitor sends.
2. Preserve headroom for performance peaks.
3. Set compressor thresholds from actual gain reduction.
4. Start IEM transmitters/receivers at safe levels.
5. Verify X18 -> PreSonus return channels do not clip.
6. Confirm speaker amps/crossover receive clean Main signal before increasing power-amplifier level.

## Change control

Physical routing changes belong in this repository. Performer-specific fader/EQ adjustments do not become locked topology unless deliberately adopted as the new baseline.
