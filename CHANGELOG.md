# Changelog

What changed in each SEAR version. The newest first. SEAR's own "Check for updates" and its automatic update read
[`latest.json`](latest.json).

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
