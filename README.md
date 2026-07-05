# WR-28 Ka-Band Horn Antenna — VNA Characterization & Calibration Study

**S-parameter measurement of a standard-gain horn antenna at Ka-band (26.5–40 GHz), quantifying the impact of VNA calibration on measurement integrity.**

| | |
|---|---|
| **Type** | Experimental measurement + comparative analysis |
| **Author** | Samuel Sánchez García (sole author) |
| **Context** | University of New Mexico (UNM), 2026 |
| **Status** | Complete — measured results |

---

## Overview

Millimeter-wave S-parameter measurements are extremely sensitive to systematic errors introduced by cables, connectors, and coax-to-waveguide adapters. This project characterizes the input reflection coefficient (S₁₁) of an **Eravant SAR-2309-28KF-E2** WR-28 standard-gain horn antenna and quantifies how calibration determines whether the measured data is physically meaningful at all.

Three datasets are compared:

1. **Uncalibrated measurement** — raw S₁₁ from the VNA
2. **Calibrated measurement** — reference plane moved to the antenna port
3. **Manufacturer's datasheet** — nominal reference response

## Test setup

- **Instrument:** Keysight PNA-X Network Analyzer (N5247A)
- **Frequency sweep:** 26–40 GHz (Ka-band)
- **DUT:** Eravant SAR-2309-28KF-E2, WR-28 waveguide flange, nominal gain 28 dBi, VSWR < 1.12:1

## Key results (measured)

| Dataset | Behavior |
|---|---|
| **Uncalibrated** | Strong ripple, artificial minima (−30 to −35 dB) at 27.2 / 34.6 / 36.0 GHz caused by standing waves in the measurement chain — not antenna properties. −10 dB bandwidth extraction is meaningless in this state. |
| **Calibrated** | Smooth, physically consistent trace. Clear resonance: **S₁₁ ≈ −18 dB at 30.7 GHz**, −10 dB bandwidth ≈ 30.6–31.0 GHz (~1.3% fractional). |
| **Datasheet** | Reflection better than −20 dB across the band, dual minima near 32 GHz reaching ≈ −54 dB. |

Residual deviations between the calibrated measurement and the datasheet are attributed to manufacturing tolerances, environmental conditions, and mechanical alignment at the waveguide interface — all within normal Ka-band uncertainty limits.

## Why this matters

The comparison demonstrates experimentally that **without proper calibration, Ka-band reflection data cannot be interpreted as antenna performance**. Shifting the reference plane to the DUT port via calibration removed the adapter/cable artifacts and recovered a response consistent with the manufacturer's reference.

This is a calibration and measurement-integrity study — not a specification validation campaign.

## Repository contents

```
paper/      Full technical report (PDF)
figures/    S11 traces: uncalibrated, calibrated, datasheet comparison
```

## Skills demonstrated

`VNA measurement` `S-parameter analysis` `SOLT calibration` `Ka-band / mmWave` `waveguide components` `measurement uncertainty analysis` `Keysight PNA-X`

## References

Key references include the Eravant SAR-2309-28KF-E2 datasheet, the Keysight N5247A documentation, Pozar's *Microwave Engineering*, and Balanis' *Antenna Theory* (full list in the report).
