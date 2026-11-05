# Third-Party Notices & Attributions

Polyend Tracker Community Edition (CE) incorporates or links against the following third-party open-source and binary components:

---

## 1. ARM CMSIS & CMSIS-DSP
* **Location**: `platforms/imx/CMSIS/`, `platforms/mk66/3rdparty/teensy_core/`
* **License**: Apache License 2.0 / BSD-3-Clause
* **Copyright**: Copyright (c) ARM Limited. All rights reserved.

## 2. NXP MCUXpresso SDK (Kinetis K66 & i.MX RT1050/RT1060)
* **Location**: `platforms/imx/drivers/`, `platforms/imx/device/`, `platforms/imx/usb/`, `platforms/imx/sdmmc/`, `platforms/mk66/3rdparty/SD/`, `platforms/mk66/3rdparty/I2C/`, `platforms/mk66/3rdparty/SDRAM/`
* **License**: BSD-3-Clause
* **Copyright**: Copyright (c) Freescale Semiconductor, Inc. / Copyright 2016-2022 NXP.

## 3. FatFs - Generic FAT Filesystem Module
* **Location**: `platforms/imx/fatfs/`, `platforms/mk66/3rdparty/SD/fatfs/`
* **License**: FatFs License (BSD-style)
* **Copyright**: Copyright (C) ChaN, 2019. All rights reserved.

## 4. Teensy Cores & Teensy Audio Library (PJRC)
* **Location**: `platforms/mk66/3rdparty/teensy_core/`, `platforms/mk66/3rdparty/Audio/`, `core/libs/Audio/`
* **License**: MIT / PJRC Permissive License
* **Copyright**: Copyright (c) 2014-2018 Paul Stoffregen, PJRC.COM, LLC.

## 5. Liberation Sans Fonts (UI Bitmap Font Source)
* **Location**: `core/libs/fonts/LiberationSans-*_L4.{h,cpp}` (4-bit `L4` antialiased glyph bitmaps)
* **License**: SIL Open Font License 1.1 (OFL-1.1)
* **Copyright**: Digitized data copyright (c) 2010 Google Corporation; Copyright (c) 2012 Red Hat, Inc.

## 6. Embedded Template Library (ETL)
* **Location**: `util/3rdparty/etl/`
* **License**: MIT License
* **Copyright**: Copyright (c) 2016 jwellbelove (John Wellbelove).

## 7. magic_enum
* **Location**: `util/3rdparty/magic_enum/`
* **License**: MIT License
* **Copyright**: Copyright (c) 2019 - 2022 Daniil Goncharov.

## 8. FastCRC
* **Location**: `platforms/mk66/3rdparty/FastCRC/`, `platforms/imx/3rdparty/FastCRC/`
* **License**: MIT / GPLv3 dual-licensed (used under MIT/BSD terms where applicable)
* **Copyright**: Copyright (c) 2014-2016 Frank Boesing.

## 9. Polyend Precompiled Synth & DSP Libraries (`libPolySynth.a`, `libPolyDSP.a`)
* **Location**: `synth/lib/`
* **License**: Polyend Precompiled Synthesizer & DSP Library License (`synth/lib/LICENSE-PROPRIETARY.txt`)
* **Copyright**: Copyright (c) 2023-2026 Polyend Sp. z o.o. All rights reserved.


## BREAKLINE addition: Mutable Dreams / Plaits / Rings / stmlib

* **Location**: `core/synth/mutable/plaits/`, `core/synth/mutable/rings/`, `core/synth/mutable/stmlib/`; adapters `core/synth/engines/MutableDreamsVoice.{h,cpp}` and `MutableDreamsDsp.h`.
* **License**: MIT. Original complete per-file copyright and permission notices are preserved in every copied source/header/resource file. New BREAKLINE adapter code is MIT; the combined firmware remains governed by the root Polyend license and the separate binary-library license.
* **Copyright**: Emilie Gillet / Mutable Instruments (as dated in individual source files). The new adapter derives its four-model routing from the MIT-licensed Mutable Dreams synthesis implementation.
* **Origins**: https://github.com/pichenettes/eurorack (Plaits/Rings), https://github.com/pichenettes/stmlib ; acquired from Kid Bunka's saved Mutable Dreams 1.0 source delivery, without its FM-1 platform layer or complete instrument sequencer. The saved delivery does not identify an upstream Mutable commit; no upstream revision is guessed. `core/synth/mutable/PROVENANCE.json` identifies all 34 exact source files using SHA-256, plus the delivered hashes and the local initialization correction.
* **Local changes**: native 44.1 kHz constants inherited from Mutable Dreams; monophonic Tracker SDK adapter with attack/release/velocity/pitch bend and six parameter macros; explicit initialization of the FM downsampler's two FIR state fields (the original Mutable Dreams pre-zeroed its voice storage).
* **Scope**: selected Plaits FM, virtual analog, additive/harmonic algorithms and the Rings modal resonator. This is not a complete Plaits, Rings, or Mutable Dreams firmware port, and is not endorsed by Mutable Instruments.

## bazillOS addition: Spore Terminal bitmap fonts

* **Location**: `core/libs/fonts/Spore*_L4.{h,cpp}`.
* **Origin**: Spleen, https://github.com/fcambus/spleen, commit `5116f8eac7f65da2cfa169626ec43b5d041665fe`.
* **Copyright**: Copyright (c) 2018-2026 Frederic Cambus.
* **License**: BSD-2-Clause; complete notice, conditions and disclaimer in `licenses/Spleen-BSD-2-Clause.txt`.
* **Changes**: EVE L4 conversion, light scanline displacement in heading letters, retained/scaled control glyphs from the Tracker CE bitmap font assets. Those inherited UI glyphs retain the original Tracker CE distribution terms; BSD-2-Clause applies to the Spleen-derived glyphs. The Pattern face keeps clear, unmodified Spleen letters and digits.

## bazillOS0.4 addition: further Plaits-derived models

Viral Vox (SAM), Vowel Spore (NaiveSpeechSynth), and Reson Bloom (ModalEngine) use additional MIT-noticed code from the same saved Mutable Dreams1.0 source handoff. Complete notices remain in each source. `core/synth/mutable/BAZILL-040-ADDITIONS-PROVENANCE.json` records copied and retained dependencies. Model indices0-15 and their presets remain compatible; new indices16-18 are appended. These are selected algorithms, not a complete module-firmware port or an endorsement.


## bazillOS beta5: TIDAL, CROSSBREED and Spore Dice

* Original DSP and resources: Emilie Gillet, MIT, https://github.com/pichenettes/eurorack at `f4cfa7697095a28d292bff758beb51deb49b5a86`; complete per-file notices retained under `core/synth/mutable/{tides2,warps,marbles}` and `stmlib/utils/ring_buffer.h`.
* TIDAL adapts Tides2's poly slope generator as a monophonic stereo instrument. Tidal Wave Fill uses its control-rate shaping. This does not reproduce the complete module firmware or CV interface.
* CROSSBREED adapts six Warps cross-modulation algorithms with internal carrier/modulator oscillators. The vocoder storage/path is excluded to fit RAM; it is not a complete Warps/vocoder port. The adapter bounds the exact upper Color lookup endpoint.
* Spore Dice uses Marbles' original random-memory sequence with a sixteen-step loop for selected Fill values. It is not the complete Marbles trigger/voltage/clock module.
* Tides ratio tables are const and shared render dispatch is initialized once. New adapters, original presets and music tools use MIT notices. `PROVENANCE-EXTENSIONS.json` records original and modified hashes.
* Public instrument/tool names do not imply endorsement by the original authors.

## bazillOS development: QUAD FM and Spore Terminal v2

* QUAD FM adapts the independently authored MIT four-operator phase-modulation core from track3r-os, commit `5a43e1efead0b143ea1706a6c3a37a2953e2c60b`. Only `fm_dsp.h`, `fm_gen.h`, and the MIT SDK types were imported; no GPL OS/application/module loader. Full MIT copyright/license and exact original/modified hashes are in `core/synth/vendor/track3r_fm/`. Changes to upstream headers are local include syntax only. The native synth adapter, UI integration and128 sound recipes are original bazillOS work.
* Spore Terminal v2 removes heading scanline displacements and adds restrained L4 stroke coverage to the BSD Spleen glyphs. Advances, bitmap cells and inherited control icons stay unchanged. BDF source/provenance is retained in `assets/spore-v2`; BSD notice in `licenses/Spleen-BSD-2-Clause.txt`.
* The official Polyend Theme & Font Editor was used as a format/workflow reference (MIT;7437ace02aaddcb4b7529ccf9320a1ecf5c29349). The exported colour themes are original; the PTFN v1 writer is original code implementing the documented binary layout. No editor logo or font was copied.
* polygen::tracker (4864d1a19cc01dba16ec087a73b8baa5378ea68c) is a concept reference. No project license grant was found; none of its implementation, sound data or template tables was imported.

## Spore Phosphor UI refinement

The five Spore font faces retain their pinned Spleen-derived glyph geometry, original BSD-2-Clause attribution, advances and legacy UI control glyphs. This local variant increases L4 stem coverage for legibility. The generator and verification records are kept in tools/build_phosphor_fonts.py and evidence/spore-phosphor-fonts.json. See licenses/Spleen-BSD-2-Clause.txt and assets/spore-v2/SOURCE.json for upstream provenance.
