# bazillOS 0.9.3 beta 2

A tracker at heart. A different culture around it.

**Independent community firmware for the Polyend Tracker Mini, by Kid Bunka. Build bz093q.**

[Website](https://kidbee85-beep.github.io/bazillOS/#release-093) · [0.9.3 beta 2 downloads](https://github.com/kidbee85-beep/bazillOS/releases/tag/v0.9.3-beta.2) · [Feedback](https://github.com/kidbee85-beep/bazillOS/issues)

## bz093q hotfix — device playback check passed (user report)

A user reported freezing after a few minutes with the previous update and working playback after rollback to 0.9.1. The exact cause is unproven. This corrective pre-release fixes long display string sizes, bounds stalled display waits, improves workspace patch-load reserve/lifetime handling and adds HEALTH counters. SPECTRA scratch reserve is more conservative.

**Device report, 16 November 2026:** Kid Bunka confirms startup/version/build and over 30 minutes of stable playback, with FAILED ALLOCATIONS = 0 and DISPLAY RECOVERIES = 0. This is one reported Mini session; individual help/synth-load/project-switch subchecks were not separately enumerated. [Dated test record](DEVICE-TEST-bz093q.json). Back up the complete card; retain known-working firmware and matching project backups. Check startup, long help, synth-project loads and 30 minutes of playback with view changes. Report HEALTH counters and whether audio continues if a freeze occurs. [Software test evidence](https://github.com/kidbee85-beep/bazillOS/releases/download/v0.9.3-beta.2/TEST-RESULTS.json).

## New in 0.9.3

- **SPECTRA:** an original 16-partial spectral synth with eight controls, a live spectrum view and 48 presets.
- **PREVIEW on all twelve synth engines:** two-bar musical phrases at project tempo, continuing while you browse presets. Key 4 in Edit Patch; key 5 in the preset browser.
- Expanded sound banks and 16 added PERC genre kits, bringing PERC to 80 kits.
- A phosphor redesign with rounded petri-cell menus, module colours, engine-specific artwork and views, a copper-bar intro and CRT shutdown.
- Overtone Ladder, hidden in Arcade Synth > GRAVITY > Down three times.
- Fixes for a second Master Rewind save, atomic workspace patch loading, DREAMS Plucked String ticks, PERC voice warnings, Ambient SPECTRA naming and bounded Beat Lab slice counts.

[Illustrated English 0.9.3 guide](https://github.com/kidbee85-beep/bazillOS/releases/download/v0.9.3-beta.1/bazillOS-0.9.3-New-Features-Guide.pdf)

## Keep making music

The existing sample, pattern, song and performance workflows remain. Four/eight-track views, grouped tools, context help, compact PERC Drum Lab writes, the Chop workspace, Composer, Ambient Machine, musical Arcade tools, balanced Punch recipes and Master workflows are retained. MIDI routing on all sixteen tracks and seven assignable Pattern Punch favorites arrived in 0.9.2 and remain available.

## Install and keep a way back

**Tracker Mini only.** OG and Tracker+ are not included.

1. Save your session and back up the complete SD card. Keep earlier firmware and its matching project backup.
2. Extract `bazillOS-0.9.3-beta.2-Mini-Firmware.zip` and read its READ-FIRST. Copy `Firmware/TrackerMini_bz093q.ptf` to the card's Firmware folder.
3. Safely eject, insert the card in the Mini and select the file under Config > Firmware. After restarting, confirm **0.9.3 bazillOS beta2 / bz093q**.
4. Work in project copies. Older firmware cannot load SPECTRA projects; changing firmware does not convert their instrument data.

Returning to original Mini 2.2.1 was tested during development. Returning to firmware and restoring matching original card data are separate steps. Keep original backups. Get stock firmware from [Polyend](https://polyend.com/downloads/tracker-mini-downloads/).

## Matching source and verification

Use the release asset **`bazillOS-0.9.3-beta.2-Source.zip`**. Its `bazillOS-bz093q/` directory is the firmware build tree. The website repository files and GitHub's automatically generated source archives are not substitutes for that matching firmware source package.

`BUILD-bz093q.txt` documents GNU Arm Embedded 10.3-2021.10 and the exact command. Use a directory path without spaces. The build tag is `bz093q`.

The 5,677 source entries matched the frozen manifest. An independent clean rebuild reproduced the released PTF byte for byte.

```
PTF SHA-256: 642f14ee97f6d9d6bcc024ad90584d4f9fb50536071ad99ca3066f4b5bc5a851
Firmware ZIP: cbce088de0edfc642c64de50c8ab396fb249f454b71dcc2a97128b8bfce7e102
Source ZIP: 93d0910a9eebaafbba84d754bc7fbc62fe127ac2b8b2ce5cf01617e83ba91214
```

Kid Bunka reports that the bz093q startup and 30+ minute playback check passed, with both HEALTH counters at 0. Actual-function patch-loading tests, SPI-emulated display tests and two byte-identical clean ARM builds passed. The device report and software checks do not establish every hardware timing or resolve the specific community freeze conclusively.

## Current boundaries

48 independent sample slots, two Step FX columns and three synth parts sharing the native eight-voice budget. Individual engines have smaller limits. TIDAL, CROSSBREED and Spore Dice adapt selected algorithms; they are not complete hardware-module ports. CROSSBREED has no vocoder. Extra sample slots and a third FX lane are not included.

Film visuals are source-rendered UI previews with host font/icon stand-ins and editorial graphics. The original studio score uses actual SPECTRA DSP parts plus host-produced drums, bass and mix processing. It is not a device recording.

## Licences and credits

The Tracker Community Edition foundation uses **PolyForm Noncommercial 1.0 plus Polyend's additional permissions**. Those permissions expressly allow music creation, performance and monetized content. Do not assume that all source has a single MIT licence or that the full firmware is OSI-licensed.

Unmodified Polyend `libPolySynth.a` / `libPolyDSP.a` have their supplied authentic-hardware conditions. Selected Mutable Instruments DSP retains Émilie Gillet's MIT notices. The QUAD FM core derives from MIT-licensed track3r code. The Spleen-derived font retains its BSD-2-Clause notice. Component terms, origins and revisions are preserved in the source and firmware pack; see [LICENSE](LICENSE), [NOTICE](NOTICE.md) and [CREDITS](CREDITS.txt).

Independent project; no Polyend, Mutable Instruments or Renoise endorsement is implied. Feedback, reproducible issues, musical ideas and patches are welcome. Support is optional through the website and does not purchase a promised feature or support contract.

The immutable release assets were packaged before the device report and retain their original hashes and build-time test status. The dated device record above updates that status without changing the firmware.
