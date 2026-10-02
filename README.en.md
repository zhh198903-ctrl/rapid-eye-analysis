**English** · [中文](README.md)

# REA — Rapid Eye Analysis

> S-parameters in, eye diagram and margin out

Computes eye diagrams straight from S-parameters. Normal and Expert share FFE / DFE / CTLE optimization, with independent floating FFE/DFE tap search. Handles optical eyes, TDECQ and EECQ in addition to electrical, and reports pre- and post-FEC BER. Drivable over SCPI for automated test flows.

## 📥 Download

**This repository does not ship the software itself.** It is a commercial product with closed source; this repo is only a description and download entry.

### ⬇️ [REA_dist_v2_0_22.zip](http://106.14.76.130/REA/2.0.22/REA_dist_v2_0_22.zip)

| Version | Size | Released | SHA-256 |
|---|---|---|---|
| v2.0.22 | 188.5 MB | 2026-10-02 | `ac86209de84ca50878e38f7505bdc326fc570b1f0dd94a06a0f9d02e24d2a59c` |

All tools: http://106.14.76.130

The download site supports resumable downloads (HTTP Range).

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


## v2.0.22 changes

- Normal keeps common signal settings on the main panel; TX waveform and channel processing have dedicated settings dialogs.
- Reorganize bilingual parameter layouts with explicit stage switches, aligned fields and consistent actions. High-precision package values stay readable, and long settings dialogs scroll.
- Fix clipped labels and values in the Expert eye toolbar; improve settings-button visibility and click targets.
- Normal and Expert share equalization optimization. Floating FFE/DFE taps optimize independently of fixed taps, improving tap selection for delayed reflections.
- Improve CPU/GPU consistency in CTLE optimization and reduce GPU memory use during batch optimization.
- Improve background computation and release-build efficiency; update the Chinese and English manuals and quick-start guides.

## 📮 Contact

WeChat official account: **高速通信杂谈**
