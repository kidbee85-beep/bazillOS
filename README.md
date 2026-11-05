# bazillOS 0.9

A tracker at heart. A different culture around it.

**An independent community firmware for the Polyend Tracker Mini, by Kid Bunka.**

[Website and illustrated handbook](https://kidbee85-beep.github.io/bazillOS/) · [Downloads](https://github.com/kidbee85-beep/bazillOS/releases/tag/v0.9.0) · [Feedback](https://github.com/kidbee85-beep/bazillOS/issues)

## Make something infectious

- A phosphor/demoscene interface, named menu destinations, context help and clear browse/edit/armed/record states.
- Switch between four detailed tracks and an eight-track overview. Jump directly to the selected sound, Punch Deck, Master FX or Tempo/Swing.
- Ready PERC Drum Lab, 64 kit recipes and compact pattern writes that use the required tracks.
- One Chop workspace: Chop Studio recipes, Slice Lab cutting controls and Chop Patterns variations, locks, A/B and groove capture.
- Composer with musical roles, scales and motif locks; Spore Dice and Tidal Wave variations in Fill.
- Eleven engines: ACD, FAT, VAP, WTFM, PERC, DIRT, CHIP, DREAMS, TIDAL, CROSSBREED and four-operator QUAD FM, with editable presets and macros.
- Pulse Pong and Virus Breaker: tempo-linked musical games with phrase capture and native Pattern Undo.
- 64 balanced Punch recipes, coder visuals, twelve compound Step FX and Master genre/reverb/delay preset workflows.
- Fifty genre starters, an empty template, three arranged feature demos and a 62-page illustrated English handbook.

The native tracking, sampling, project and performance workflows remain alongside these additions. See the handbook for each tool's scope and controls.

## Install and keep a way home

**Tracker Mini only.** OG and Tracker+ builds are not part of this release.

1. Save your session and back up the **entire SD card**, including Workspace, settings and hidden files. Keep an untouched original-data backup and a verified original Mini firmware image.
2. Read [Installation and Rollback](bazillOS-09-Installation.pdf). Extract the Mini firmware pack; merge its Firmware, Fonts and Themes folders without replacing your projects or samples.
3. Safely eject the card, insert it in the Mini and update through Config → Firmware. Confirm **0.9.0 bazillOS / bz090c** after startup.
4. Work in project copies. Optional demo projects are a separate download.

Returning to original Mini 2.2.1 was tested in this project. Changing firmware and restoring matching original card data are separate steps; custom/Community Edition saves do not automatically become compatible with stock firmware. This is a tested return route, not a universal risk-free guarantee. Obtain stock firmware from [Polyend](https://polyend.com/downloads/tracker-mini-downloads/); it is not redistributed here.

## Matching source and build

The repository root contains the website and **`bazillOS-09-Source.zip`**, the complete matching firmware source archive. Extract that archive to obtain the build tree; the website files themselves are not the firmware build tree. The same source archive is attached to the release. GitHub's automatically generated source archives contain this nested archive too.

Use GNU Arm Embedded **10.3-2021.10** and the included `BAZILLOS-BUILD.txt`. From the extracted firmware tree, build the Mini target as documented there. The default build tag is `bz090c`; preserve that identity when reproducing the release. Full build instructions and third-party notices are inside the archive.

The released source archive was extracted into a clean directory and rebuilt. It produced the exact tested firmware bytes:

```
Firmware: d3292ffa522a551751233aec0f3c927d8f16be84e110260b79c83d0288ce8fb6
Source ZIP: d344c439e6d41060f23923d8a331228b1fc9f571af048730482b0a527fc054f4
```

Download `SHA256SUMS.txt` with the release assets. `BUILD-VERIFICATION.json` describes the source reproduction and bounded test evidence.

## What was tested

The returned 40-case device review recorded 38 passes and two issues. Both were corrected. The final `bz090c` device follow-up confirmed startup/build, repeated Play/Stop, more than 70 seconds of Composer preview with its own controls retained, and correct return to the Pattern toolbar. Earlier reports covered playback, save/reload, old-project switching, generators/Undo, synths and balanced Punch behavior. Recent reported checks had no crashes; earlier development faults are not erased from that history.

Host regression, controller, graphics/bounds and linker/HEX checks are separate evidence. They do not establish every external-equipment combination, CPU timing or unlimited long-run stability.

## Current boundaries

48 independent sample slots, two Step FX columns and three synth parts sharing the native eight-voice budget; individual engines have smaller limits. Most compound Step FX and Punch recipes target samples; SPACE also supports synths. TIDAL, CROSSBREED and Spore Dice adapt selected algorithms, rather than porting complete hardware modules. CROSSBREED does not include a vocoder. Extra sample slots and a third FX lane are not included.

The feature film uses source-rendered UI demonstration states and host-rendered production audio, rather than claiming a physical screen/audio capture. The music-led tour, Shorts and web ident are clearly identified in their descriptions.

## Licences and credits

The Tracker Community Edition foundation uses **PolyForm Noncommercial 1.0 plus Polyend's additional permissions**. Those permissions expressly allow music creation, performance and monetized content. Do not assume that all source has a single MIT licence or that the full firmware is OSI-licensed.

Unmodified Polyend `libPolySynth.a` / `libPolyDSP.a` have their supplied authentic-hardware conditions. Selected Mutable Instruments DSP retains Émilie Gillet's MIT notices. The QUAD FM core derives from MIT-licensed track3r code. The Spleen-derived font retains its BSD-2-Clause notice. Component terms, origins and revisions are preserved in the source and firmware pack; see [LICENSE](LICENSE), [NOTICE](NOTICE.md) and [CREDITS](CREDITS.txt).

Independent project; no Polyend, Mutable Instruments or Renoise endorsement is implied. Feedback, reproducible issues, musical ideas and patches are welcome. Support is optional through the website and does not purchase a promised feature or support contract.
