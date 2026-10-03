# HSGKK Soundcheck & Safety Checklist

## Before powering / unmuting

- Confirm X18 Ch 8 is the PreSonus Bus 3 Band + Media feed.
- Confirm X18 Ch 8 is OFF from X18 Main L.
- Confirm X18 Ch 8 is OFF from X18 Bus 6.
- Confirm X18 Bus 6 contains MD Ch 6 and PA Ch 7 only unless a documented change is required.
- Confirm click/cue is excluded from PreSonus FOH Main.
- Confirm OBS is receiving PreSonus Main over USB, not Bus 3.
- Start output/IEM levels safely low.

## Gain structure

1. Establish microphone/instrument preamp gain before changing monitor send values.
2. Leave enough headroom for louder performance peaks.
3. Set compressor thresholds from observed gain reduction, not copied threshold numbers.
4. Verify X18 -> PreSonus returns are not clipping either mixer.

## Vocalist monitors

- Bus 1: AWL IEM; start from documented preset and adjust with actual AWLs.
- Bus 2: WL IEM; WL self should remain dominant.
- Ch 8 Band is a single curated Band + Media reference. Vocalists can request more/less Band but cannot independently change individual instruments from X18.
- MD/PA should remain intelligible without forcing vocalists to run excessive IEM level.

## Musician monitors

PreSonus:
- Bus 1 Drum
- Bus 2 Bass
- Bus 3 Band + Media -> X18 (not a musician IEM)
- Bus 4 Keyboard
- Bus 5 Guitar 1
- Bus 6 Guitar 2 wireless IEM

The Drum Cage MD is a discrete PreSonus source. Musicians may add it individually. Keyboard may keep it off/low because of drum-cage bleed.

## Feedback-loop test

Before service, temporarily reduce return levels and verify:
- Raising PreSonus Bus 3 changes X18 Ch 8 / vocalist Band reference only.
- Raising X18 Main L changes the PreSonus vocal/speech subgroup but does not re-enter X18 Ch 8.
- Raising X18 Bus 6 changes only the PreSonus MD/PA return.
- No self-sustaining level increase occurs with stable source input.

## OBS

Verify OBS receives the intended PreSonus FOH Main L/R over USB. Do not repurpose Bus 3 for OBS.

## Change control

If a routing change is made during rehearsal/service, update the repository afterward if it changes the baseline topology. Temporary performer level changes do not need to become permanent documented values unless adopted as the new baseline.
