# Increasing Efficiency of Solar Panels Using Tracking Systems

Research project comparing a fixed-position solar panel (Configuration A) against a single-axis, PV-cell-sensor-driven sun-tracking panel (Configuration B), conducted for Pioneer Academics / science-fair submission.

## Contents

- `paper_ieee_format.pdf` — Full IEEE-format research paper (original submission): background, related work, methodology, CAD design, results, and discussion.
- `latex/` — LaTeX (IEEEtran) reproduction of the same paper.
  - `paper.tex` — LaTeX source.
  - `paper.pdf` — Compiled output.
  - `figures/` — Plots, CAD drawings, schematic, and prototype photo extracted from the original paper and used by `paper.tex`.
- `data/` — Raw serial-logger CSV output from the physical test rig.
  - `CONFIGA_20260827_8hours.csv` — 8-hour fixed-panel (Config A) baseline run.
  - `Config_B_20260901_1.csv`, `Config_B_20260901_2.csv`, `Config_B_20260901_3.csv` — Tracking-panel (Config B) test runs.

Each CSV logs: `millis, elapsed_hms, pv_left, pv_right, angle, bus_v, current_mA, power_mW` at 30-second intervals from an Arduino-based rig using paired PV-cell directional sensors, an INA219 power monitor, and a servo-actuated single-axis mount.

## Status

This is raw experimental data and the associated write-up, not a finished product. The paper documents known data-validity issues in the Config B runs (ADC ceiling saturation, near-open-circuit periods) that affect the energy-comparison conclusions — see the Results/Discussion sections of the paper for details.
