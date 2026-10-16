# Changelog

What changed in each SEAR version. The newest first. SEAR's own "Check for updates" and its automatic update read
[`latest.json`](latest.json).

## 1.0.4 — 2026-10-16

**Ear tweaks — your tone, after SEAR's (new)**
- **👂 Tweak by ear**, at the end of a run (on the run's page and in the "keep the new run?" window) and on every run in
  the Library. SEAR gets you close to the record; your ear finishes it. Say what you hear, in a guitarist's words:
  *Boxy*, *Fizzy / harsh*, *Thin*, *Boomy / flubby*, *Needs more gain*, *Too much gain*, *Squashed, no dynamics*,
  *Too dry*, *Too wet*. SEAR reamps the run as it plays now and two ready-made corrections, **A touch** and **More**
  (about 30 s), on the amp's own knobs and only the ones SEAR has validated: boxy opens the top and scoops the mids,
  thin adds bass and middle, more gain turns the knob that actually makes the distortion, and so on.
- Listen to each one next to the record, one at a time and at the same loudness; the button lit with ▶ is the one you
  hear. An **"On the FM3"** box always says what the FM3 is playing: nothing changes until you keep a variant.
- **Keep** it and it becomes that run's: **⟲ Recall now** puts it on the FM3, with the listening volume measured again.
  The FM3 must hold that run for the reamps; if it doesn't, SEAR writes nothing and tells you to recall it first.
- **Volume:** *Too quiet (+2 dB)* / *Too loud (−2 dB)* are saved on the run at once (no reamp: the comparisons are at the
  same loudness on purpose); each press adds up, ±12 dB at most.
- In the Library, a part's **"Ear tweaks"** row is now a small table: each tweak with its value before → after, and **✕**
  to take it back.

**Runs**
- **Never more distorted than the record.** SEAR now measures how much each capture distorts (whatever the cab and EQ) and
  compares it with the record. A rig, or a point of the search, clearly more distorted than the record is left out; if
  every rig tried is, the research got the part's character wrong and the part is searched again as clean (not when you
  chose the character yourself). Settings → "Never more distorted than the record".
- **A rig that starts very quiet now reaches its listening volume.** When amp level and master are at their top and the
  sound is still short, SEAR uses the room left on the final EQ's level, and checks it with one more reamp. A recall that
  still ends short is measured again the next time instead of being reused.
- A tweak never turns a gain knob below 1 (a clean amp turned all the way down goes almost silent).
- If SEAR was updated while its page was open, the page now says to restart SEAR instead of a bare "not found".

This update downloads only the app package: the runtime is unchanged.

## 1.0.3 — 2026-10-15

**Runs**
- **New: "Continue from the run in use".** A second run that starts from the part's run in use: its rig, cab and knobs,
  with your ear's adjustments kept. No rig or cab screening. SEAR measures the run in use again, then searches where that
  run did not get to: the knobs it left open, box edges, other levers. It takes about 4-6 minutes. The new run is kept
  only if it beats the run in use by more than the noise; otherwise the run in use goes back on the FM3. It is the
  default in the ▶ New run window for a part that already has a SEAR run in use.
- **"Decide later" keeps the run you were using.** At the end of a run, the new run is no longer loaded until you choose it.
- Each phase of a run now says why it ended, in plain words ("ended because the reamps ran out: it was still
  improving", "gain lowered: with less gain the sound stays practically the same"…), instead of a single code word.
- The screening table and the Setup card name each rig's **amp**, next to its cab.
- Fixed: the rig grid could show a talk box (Formant) as on when the run had it bypassed.

**Your own rig (🎛 My rig)**
- **No preset number to type.** SEAR reads which preset is loaded on the FM3 when it measures and when you press "Save in SEAR".
- **Your saved preset is always kept.** If the slot differs from what was measured, SEAR saves it anyway and lists the
  differences. Fixed: a reverb such as "Room, Studio" was reported as a different model ("Studio").
- In the Library's run list, each run is marked **"🎛 your rig"** (with its slot and name) or **"SEAR"**.

This update also downloads a new runtime package: the FM3 connection learned to read the loaded preset's number.

## 1.0.2 — 2026-10-14

**Rig research and screening**
- **An effect the research only guessed is no longer switched on.** Each extra block in a research answer now says where
  it comes from (a source about this recording, clearly heard on the record, or a guess); a guess is placed in the preset
  but bypassed.
- **A wah pedal is never left on during a run.** SEAR cannot move the pedal, and a wah parked at a random position
  spoiled the tone. It stays in the preset, bypassed, for you to rock live.
- The screening also tries the rig **without** each effect no source documents, and keeps it only if it sounds closer.

**Talk box (Formant) rigs**
- Fixed: rigs that switch the Formant off stopped at the screening ("bypass did not verify"). With a modifier on one of
  its controls, the FM3 can ignore the block's bypass — even from the front panel. SEAR now lifts the modifier while the
  Formant is off and puts it back when it is on.
- **Song presets: every scene is checked again at the end of a recall.** A change made for a later scene could switch a
  block in an earlier one (a talk box turned off in the intro after it had been checked). Now a recall that leaves a scene
  different from its run stops and says so, instead of reporting success. Known limit: a talk box that is on in one scene
  and off in another, with a modifier on its control, may not keep its per-scene state — the recall then tells you how to
  fix it on the FM3.

**Runs**
- The new-run window shows the **sound character next to the max reamps**; "▶ Run every part" asks each part's character
  too. The max reamps are now **24–65**.
- A short dropout of the FM3's USB audio ends a run less easily: SEAR waits a second before recording again.
- An ear tweak that only switches a block on or off now re-measures the listening level.

**Messages**
- When a job fails for a reason you can fix — FM3-Edit holding the USB port, the FM3 not found, a USB audio dropout,
  an empty preset, the CPU limit, an unknown firmware… — a window says what happened and what to do.

## 1.0.1 — 2026-10-13 (the first public release)

**Tone**
- **High-gain parts: less compression, less string noise.** After the search, SEAR turns the pedal's drive and then the
  amp's down as long as the match stays within two audible steps ("phase 1c — less gain"), and the final EQ's whole curve
  stays within −6 / +4 dB (before, bands stacked on one region could reach +7 dB of highs and −9 dB of low mids after the
  distortion: a thin sound with the pick and string noise up). Clean and crunch parts are unchanged. Both can be switched
  off in ⚙ Settings.

**Cab measurement**
- Its own minimal chain (Input → Cab → Output), the temporary preset named "Do not save", scene "SEAR".
- The number of cabs measured (of 2048) goes up at every cab, on the Home card and in the console's bar.

**Install and updates**
- **Downloads here, in [Releases](../../releases)**, and **automatic updates**: SEAR downloads a new version by itself,
  checks the author's signature and each file's checksum, then offers "Restart to update" (never while the FM3 is in use;
  songs, runs and settings kept).
- **The FM3's parameter tables are read from your own FM3-Edit** at the first start (they are no longer part of SEAR).
- SEAR runs without a console window: an icon next to the clock opens it or quits it (and asks first when a job is
  running on the FM3).
- Long jobs (a run, the cab measurement, the RoFormer install) have **■ Stop**: they stop safely and resume later.
- The RoFormer separator installs faster (its weights download while PyTorch installs) and an interrupted download
  resumes where it stopped.
- SEAR runs as compiled code, without a TypeScript toolchain.
- The full licence texts of the components SEAR ships are in its `licenses\` folder.

**Library and pages**
- Parts in sequence: the page follows the next part's run by itself; at the end it asks which new runs the song uses —
  and after a single re-run it asks whether to use the new run.
- Audio plays only in the window in use (a DI recording no longer restarts the last A/B listen).
- Fuzz pedals keep their gain on clean and crunch parts; the Rotary (Leslie) always gets defined settings.
- Rig research: sources ranked, searches in the artist's own language (Japanese, Korean, Italian…).
- A voluntary donation button.

## 0.9.0-beta.1 — 2026-10-11 (private beta)

- First private beta: the portable folder (SEAR.exe / SEAR.cmd), English and Italian, the optional RoFormer separator and
  the cab measurement from the Home, bug reports saved as a file for testers without GitHub.
