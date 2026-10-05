**English** · [中文](README.md)

# REA — Rapid Eye Analysis

> S-parameters in, eye diagram and margin out

Computes eye diagrams straight from S-parameters. Normal and Expert share FFE / DFE / CTLE optimization, with independent floating FFE/DFE tap search. Handles optical eyes, TDECQ and EECQ in addition to electrical, and reports pre- and post-FEC BER. Drivable over SCPI for automated test flows.

## 📥 Download

**This repository does not ship the software itself.** It is a commercial product with closed source; this repo is only a description and download entry.

### ⬇️ [REA_dist_v2_0_25.zip](http://106.14.76.130/REA/2.0.25/REA_dist_v2_0_25.zip)

| Version | Size | Released | SHA-256 |
|---|---|---|---|
| v2.0.25 | 188.2 MB | 2026-10-04 | `6a80768566dac6365bb282be6f04e391b7b14e64cba2295e81ca6210242543d7` |

All tools: http://106.14.76.130

The download site supports resumable downloads (HTTP Range).

### Companion AI skill (Claude Code / Codex)

[Download REA skill v2.0.25](http://106.14.76.130/REA-Skill/2.0.25/REA-Skill_dist_v2_0_25.zip) · 105.9 kB · SHA-256: `bf6e620b291b78437fcafd1d70b871e35d8b3bc62f47bd16b5b44c217cf42239`

Extract the archive and copy the `rea-scpi` folder to `%USERPROFILE%/.agents/skills/` (Codex) or `%USERPROFILE%/.claude/skills/` (Claude Code). The skill matches v2.0.25 and does not change REA licensing requirements.

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
