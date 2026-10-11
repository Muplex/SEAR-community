# Changelog

What changed in each SEAR version. The newest first. SEAR's own "Check for updates" and its automatic update read
[`latest.json`](latest.json).

## Coming next — the first public beta (0.9.0-beta.2)

- **Downloads here, in [Releases](../../releases)**, and **automatic updates**: SEAR downloads a new version by itself,
  checks the author's signature and each file's checksum, then offers "Restart to update" (never while the FM3 is in use;
  songs, runs and settings kept).
- **The FM3's parameter tables are read from your own FM3-Edit** at the first start (they are no longer part of SEAR).
- SEAR runs as compiled code, without a TypeScript toolchain.
- Parts in sequence: the page follows the next part's run by itself; at the end it asks which new runs the song uses —
  and after a single re-run it asks whether to use the new run.
- Audio plays only in the window in use (a DI recording no longer restarts the last A/B listen).
- Fuzz pedals keep their gain on clean and crunch parts; the Rotary (Leslie) always gets defined settings.
- Rig research: sources ranked, searches in the artist's own language (Japanese, Korean, Italian…).
- A voluntary donation button.

## 0.9.0-beta.1 — 2026-10-11 (private beta)

- First private beta: the portable folder (SEAR.exe / SEAR.cmd), English and Italian, the optional RoFormer separator and
  the cab measurement from the Home, bug reports saved as a file for testers without GitHub.
