**English** · [中文](README.md)

# REA — Rapid Eye Analysis

> S-parameters in, eye diagram and margin out

Computes eye diagrams straight from S-parameters. Normal and Expert share FFE / DFE / CTLE optimization, with independent floating FFE/DFE tap search. Handles optical eyes, TDECQ and EECQ in addition to electrical, and reports pre- and post-FEC BER. Drivable over SCPI for automated test flows.

## 📥 Download

**This repository does not ship the software itself.** It is a commercial product with closed source; this repo is only a description and download entry.

### ⬇️ [REA_dist_v2_0_38.zip](http://106.14.76.130/REA/2.0.38/REA_dist_v2_0_38.zip)

| Version | Size | Released | SHA-256 |
|---|---|---|---|
| v2.0.38 | 247.1 MB | 2026-11-09 | `3414dcc069e521e6c341c514773e9e44e280e87d7587e0103be2291637933f8a` |

All tools: http://106.14.76.130

The download site supports resumable downloads (HTTP Range).

### Companion AI skill (Claude Code / Codex)

[Download REA skill v2.0.38](http://106.14.76.130/REA-Skill/2.0.38/REA-Skill_dist_v2_0_38.zip) · 116.9 kB · SHA-256: `a0bacc926a40b163b721d7af4aa16b56fbb00a65c054b225a0ef3edba518a837`

Extract the archive and copy the `rea-scpi` folder to `%USERPROFILE%/.agents/skills/` (Codex) or `%USERPROFILE%/.claude/skills/` (Claude Code). The skill matches v2.0.38 and does not change REA licensing requirements.

## 🔑 License

**Commercial · free trial**

This software is proprietary; the source code is not published.

**Get a trial key straight from the [download site](http://106.14.76.130).** Send your Host ID in the chat box at the bottom right and you will get one on the spot. You can also reach the author through the WeChat official account **高速通信杂谈** (High-Speed Comms Notes).

## ✨ Features

`S-parameter eye` · `FFE / DFE / CTLE` · `Pre/post-FEC BER` · `TDECQ` · `SCPI remote` · `EECQ` · `IBIS-AMI`

## 📋 Specifications

| | |
|---|---|
| License | Commercial; free trial available, send your Host ID in the chat box at the bottom right to get a trial key instantly |
| Equalization | FFE / DFE / CTLE · shared Normal / Expert optimization · independent floating FFE/DFE tap search · joint FFE+DFE solution · CPU/GPU result checks · 802.3 family presets with tap limits · optimization summary and events |
| Optical | Optical eye · TDECQ · EECQ · 802.3dj D3.1 reference-equalizer primary method (15 FFE + 1 DFE, Table 180-16 limits) |
| Device models | IBIS 8.0 / IBIS-AMI (Expert-mode node) |
| Patterns | PRBS7-31 · PRBSnQ (Gray quaternary) · SSPR / SSPRQ · custom |
| FEC | BER before and after correction · 802.3dj D3.1 / 802.3ck / 802.3bs Cl 119 / Cl 91 KR4 / Cl 74 BASE-R · PCIe 6/7/8 FLIT · 802.3dj IM-DD optical Inner FEC (TDECQ reference-equalized eye) |
| Remote control | SCPI over TCP/IP |
| Output | Eye height / eye width / margin |


## v2.0.38 changes

- In Normal mode, Generate Eye Diagram and SCPI INIT now use the configured decision levels when Force Levels is enabled. Turning it off restores automatic levels.

Windows release. Verification covers the inputs, settings and paths in the release record. The historical failed 450-ohm profile and unrepeated exact Reset desktop sequence retain their previous waivers and are not counted as passes.

## v2.0.37 changes

- COM import uses CSV and Excel paths typed into the dialog. Switching CSV files replaces automatically imported aggressors and preserves manually added channels.
- Streaming eye diagrams calibrate voltage bins from the first 4,096 folded windows in time order. The CPU histogram counts uniform voltage bins more efficiently.
- CUDA eye-width scoring now assigns crossings exactly on the sampling column consistently with the CPU decision search.
- The compute service releases request inputs and results after success or failure, reducing memory held while waiting for the next calculation.

Windows release. Verification covers the inputs, settings and paths in the release record. The historical failed 450-ohm profile and unrepeated exact Reset desktop sequence retain their previous waivers and are not counted as passes.

## v2.0.36 changes

- On Windows, a single resume continues a calculation after repeated pauses. Automatic FFE main-tap scans can use multiple CPU workers. Pause, cancellation and exit also apply to the scan workers.
- Streaming eye calculations preserve completed histogram counts, voltage bins and traces when a GPU batch is retried or falls back to the CPU after a memory allocation failure. This also preserves counts in intermediate snapshots.

Windows release. Verification covers the inputs, settings and paths in the release record. The historical failed 450-ohm profile and unrepeated exact Reset desktop sequence retain their previous waivers and are not counted as passes.

## v2.0.35 changes

- Reloading a Touchstone measurement picks up an atomically replaced file even when its size and modification time are preserved. A read already in progress can no longer repopulate a cleared cache.
- CPU streaming eye calculations retain only the waveform samples needed by the next block and release completed inverse FFT arrays before the next batch. This reduces the amount of data held in memory.

Windows release. Verification covers the inputs, settings and paths in the release record. The historical failed 450-ohm profile and unrepeated exact Reset desktop sequence retain their previous waivers and are not counted as passes.

## v2.0.34 changes

- Clearing or replacing eye inputs clears stale measurements, timing and optimization summaries. Restoring a configuration synchronizes the active file list with remote queries.
- Adding a two-port file after loading a four-port configuration honors the saved direction. Changing the direction of a single two-port input preserves its reported path.
- Report SCPI result-publication errors, retain completed FEC and MLSE captures and release resources owned by each CTLE or FFE optimization job.
- Keep cascade and de-embedding checkboxes in sync with plotted traces across language changes. Correct automatic IBIS model selection, node editor teardown and keyboard navigation in settings.

Windows release. Verification covers the inputs, settings and paths in the release record. The historical failed 450-ohm profile and unrepeated exact Reset desktop sequence retain their previous waivers and are not counted as passes.

## v2.0.33 changes

- Correct history across short streaming chunks and eye-width, centering and initialization handling for ideal edges and IBIS-AMI FIR models.
- Preserve full COM-import precision while honoring manual edits; correct As millivolt units and noise handling for folded eyes.
- Correct SCPI startup failures, completion and timeout status; prevent Normal/Expert task conflicts and require explicit calculation after loading a configuration.
- Avoid silently returning incomplete optimizer searches after memory exhaustion; improve dialog cleanup, translated plots, UTF-8 input and shared feedback history.

Version 2.0.33 updates eye calculations, COM import, IBIS-AMI, SCPI and interface stability. Validation covers only the inputs, settings and execution paths in the release record, not all models or platforms. The existing failed 450-ohm profile and its release waiver, and the previously unrepeated exact Reset desktop sequence, remain recorded without being counted as passes. New issues require their own validation. GPU acceleration is optional.

## v2.0.32 changes

- Add an explicit PLTS finite-interval response method and low-pass interval gating, with separate observation and gate bounds and validation of the input grid, DC and compatible settings.
- Correct the division and scaling order in finite-interval impedance conversion, removing a one-ULP difference in the original reflection cases.
- Correct the TDR/TDT Custom window coefficient conversion while retaining the measured frequency band and pulse amplitude definition.
- Correct the low-pass Kaiser window center and measured support so the original beta=13 impulse cases meet their original tolerance.
- Synchronize bilingual guidance and REA-Skill with the added validation scope and retained limitations; GPU remains optional.

Version 2.0.32 corrects Custom/Kaiser impulse calculations and adds an explicit PLTS finite-interval method. All 10010 original STEP samples across ten cases, 4004 complex S21 values across four gate cases and 4004 impedance values across four reflection cases agree bit for bit in source and packaged code, retaining every original node and acceptance condition. Real TCP exports from the visible interface of the released EXE also matched the four reflection curves, four gated time responses and eight Custom/Kaiser settings. These results cover only the recorded inputs, windows, DC, intervals and ports. Earlier evidence for actual manual DC, shared-fixture AFR deembedding and the specified source Reset desktop case remains valid; the exact desktop timing of that Reset case was not repeated on the released EXE, whose related code is unchanged since v2.0.31, and the existing user waiver continues to apply. The original failed 450-ohm profile and its user-authorized release waiver remain, without being counted as a pass. GPU installation is optional.

## v2.0.31 changes

- Correct S-parameter reference impedance, wave definitions and port direction while retaining original frequency nodes and physical references.
- Improve split phase continuity and numerical checks, and correct result display in the verified cases.
- Fix issues in failed file loads, Reset, trace selection, language switching and window layout.
- Correct summary selection for equal-height eyes on CPU and GPU while preserving waveforms and sampling.
- Synchronize bilingual guidance and REA-Skill, state the verified scope and existing waivers, and retain optional GPU installation.

Version 2.0.31 corrects S-parameter reference-impedance, wave-definition and port-direction handling, and improves splitting, loading, Reset, error feedback and trace display. Cross-tool consistency applies only to verified inputs, original frequency nodes and specified settings. The 450-ohm profile, actual common PLTS DC/STEP/Custom/window and gating settings, AFR fixture extraction, and the exact error-modal desktop sequence with other-slot requests queued before Reset remain incompletely accepted. These existing cases have user-authorized release waivers, not numerical passes. GPU installation remains optional.

## v2.0.30 changes

- Fix an artificial initial spike in some lowpass transmission impulse responses, including responses with edge smoothing.
- Clarify bilingual TDR/TDT guidance: distinguish step, impulse and reference amplitude, and match input grids, ports and display conditions for comparisons.

## v2.0.29 changes

- Fix errors when clicking Select all / Deselect all for trace groups in Cascade, Deembed and Splitter; each action affects its own group.
- Return SCPI errors immediately for a missing splitter input or invalid ratio sum, avoiding modal blocking; retain GUI validation prompts.
- Update S-parameter window titles, cached plot labels and trace groups when switching language; preserve selected traces and zoom.
- Preserve the selected conversion output and port order when switching language, preventing errors in existing previews.
- Clarify the complete splitter ratio list in bilingual documentation and REA-Skill; no SCPI commands are added.

## v2.0.28 changes

- Improve multi-group Floating FFE placement by comparing complete tap layouts and coefficients; confirm gains with a regenerated eye.
- Align noise budgets and floating-tap constraints across the GUI, SCPI and Normal-to-Expert copying.
- Preserve floating FFE/DFE coefficients, positions and decision timing in saved configurations, clear stale layouts, and align loaded channel paths for display and copying.
- Bundle Floating FFE S-parameter examples, reproducible configurations, reference images and a file guide.
- Apply the incoming channel rate limit when loading configurations, avoiding silent clipping by the previous channel limit.

## v2.0.27 changes

- Separate bathtub curves into rows by eye number, with phase and voltage panels for each eye and placeholders for missing eyes.
- Switch Expert bathtub probes with the picker or result table; show one probe at a time with all its eyes visible.
- Correct missing Chinese glyphs in bathtub titles, notes and legends across probe switches, language changes and detail windows.
- Adapt bathtub axes to valid data, distinguish measured and extrapolated curves, and restore adaptive limits with Home.
- Move Expert plot controls into a secondary window and simplify the main toolbar; retain appearance, annotation and decision settings after closing.
- Drag the BER line to adjust all eyes continuously and read their EH/EW at the shared target; release restores adaptive bounds.
- Refresh bathtub plots immediately after a target BER change, synchronizing Normal, Expert and open detail views.
- Synchronize GUI edits of floating equalizers, levels, RX rise time and CDR overrides with SCPI queries; improve frequency-offset precision and DFE tap-count readback.
- Fix overlapping PCB title controls and optical schematic labels; synchronize package, measurement-condition and DFE-step edits with queries.
- Use consistent compact input widths and alignment in signal ports, TX/RX FFE, DFE, package and CDR grids; show full preset names in the popup without widening the window.
- Translate open parameter, feedback, update, Marker, axis, AMI, crosstalk, COM-import and About windows while retaining drafts and task progress; cache diagrams by language and retain English Signal and Filter button names. Translate loaded file summaries, trace groups, timings and Smith toolbar controls while retaining data and recorded times.
- Synchronize rebuilt TX FFE, RX FFE and DFE tap edits with existing SCPI queries even for bypassed stages; wrap captions in narrow bathtub views.
- Update bilingual manuals, Quick Start guides and the REA SCPI skill while preserving existing commands and calculation results.
- Translate plot-layout and figure-options dialogs, axis-picker buttons and scale choices while preserving drafts, canonical scale types and plot data.
- Own the value-export window under its layout editor so it remains usable in modal eye details; release custom layout items when their parent is destroyed.

## v2.0.26 changes

- Improve large CPU/GPU eye-metric calculations while preserving measurement results in the validated scenarios.
- Correct frequency phase and finite-bandwidth handling in optical models. An unusable specified response file reports an error and stops the calculation.
- Keep usable bathtub curves while clearly reporting missing eye data and unavailable overall opening. Out-of-range eye queries return an empty response; double-click access to Expert bathtub details is fixed.
- Prevent stale results or stalled queued loads when files are rapidly cleared or switched.
- Improve DFE boundary checks and zero-tap handling, and fix optional GPU setup error reporting and runtime loading.
- Fix first-use feedback history locking when multiple processes open the same file, preserving concurrent entries.
- Update the bilingual manuals, Quick Start guides and companion REA SCPI skill.

## v2.0.25 changes

- Preserve frequency-dependent and per-port reference impedances during interpolation, cascade, de-embedding and Touchstone export.
- Any eye-mask hit fails the measurement. Missing eye data is reported explicitly and cannot produce an overall pass.
- Keep concurrent feedback-history updates. Storage errors retain pending replies, show a message and retry automatically.
- Update bilingual manuals and activation guidance to use the complete supplied key, and clarify that measured MLSE is not yet released.

## v2.0.24 changes

- Refine Normal and Expert parameter columns, typography and controls; expand EQ bounds on demand, group noise by injection point, and keep toolbar labels with their inputs when wrapping.
- Rework both Quick Start guides from the first eye through equalization, interference, saved configurations, Expert and FEC, with screenshots of reproduced results.
- Add ready-to-load optical TDECQ and IBIS-AMI demonstration configurations, explicit baseline restoration and executable SCPI examples.
- Fix CTLE preset reflection replacing saved TX FFE taps on SCPI configuration loads, stale DFE taps, missing automatic baseline eyes after COM import and portable demo paths.

## v2.0.23 changes

- Keep Generate, Pause and Stop at the bottom, with F5 support. Separate signal chain, measurements / FEC and results so long results do not displace parameters.
- Align labels and size inputs consistently, remove empty space after stage changes, and use explicit Enable switches for stage state.
- Review FEC against IEEE 802.3dj D3.1, correct extreme-error probability results and limit-boundary decisions, and identify the Inner FEC hard-decision estimate.
- Refresh existing FEC results, charts, progress, settings dialogs and dynamic menus on language changes while preserving parameters and run state.
- Synchronize Normal / Expert run and optimizer controls. Expert asynchronous RUN remains controllable from one connection, and GUI-generated results are queryable; FEC / MLSE, save / load and open parameter dialogs stay synchronized.

## v2.0.22 changes

- Normal keeps common signal settings on the main panel; TX waveform and channel processing have dedicated settings dialogs.
- Reorganize bilingual parameter layouts with explicit stage switches, aligned fields and consistent actions. High-precision package values stay readable, and long settings dialogs scroll.
- Fix clipped labels and values in the Expert eye toolbar; improve settings-button visibility and click targets.
- Normal and Expert share equalization optimization. Floating FFE/DFE taps optimize independently of fixed taps, improving tap selection for delayed reflections.
- Improve CPU/GPU consistency in CTLE optimization and reduce GPU memory use during batch optimization.
- Improve background computation and release-build efficiency; update the Chinese and English manuals and quick-start guides.

## 📮 Contact

WeChat official account: **高速通信杂谈**

