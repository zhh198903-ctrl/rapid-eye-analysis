**English** · [中文](README.md)

# REA — Rapid Eye Analysis

> S-parameters in, eye diagram and margin out

Computes eye diagrams straight from S-parameters. Normal and Expert share FFE / DFE / CTLE optimization, with independent floating FFE/DFE tap search. Handles optical eyes, TDECQ and EECQ in addition to electrical, and reports pre- and post-FEC BER. Drivable over SCPI for automated test flows.

## 📥 Download

**This repository does not ship the software itself.** It is a commercial product with closed source; this repo is only a description and download entry.

### ⬇️ [REA_dist_v2_0_30.zip](http://106.14.76.130/REA/2.0.30/REA_dist_v2_0_30.zip)

| Version | Size | Released | SHA-256 |
|---|---|---|---|
| v2.0.30 | 246.4 MB | 2026-10-10 | `cec878a69763fee15193d99dd5ac2f92e6b905da4fb871f79e2898e5fe573458` |

All tools: http://106.14.76.130

The download site supports resumable downloads (HTTP Range).

### Companion AI skill (Claude Code / Codex)

[Download REA skill v2.0.30](http://106.14.76.130/REA-Skill/2.0.30/REA-Skill_dist_v2_0_30.zip) · 111.2 kB · SHA-256: `5512a63694c401aaac14aee265e640566bba3ec597f1d047c2bed0d266de0f72`

Extract the archive and copy the `rea-scpi` folder to `%USERPROFILE%/.agents/skills/` (Codex) or `%USERPROFILE%/.claude/skills/` (Claude Code). The skill matches v2.0.30 and does not change REA licensing requirements.

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
