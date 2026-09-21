# Increasing Efficiency of Solar Panels Using Tracking Systems

Rohan Rajesh — Pioneer Academics / science-fair research project.

A side-by-side comparison of a fixed solar panel (**Configuration A**) against a single-axis solar tracker (**Configuration B**) that uses paired PV cells as directional sensors (instead of the LDRs common in prior work) to drive a servo-actuated mount via an Arduino. An INA219 current sensor logs voltage, current, and power from both panels to microSD on the same time base, so any energy gain is attributable to tracking alone (no MPPT, no other efficiency measures).

## Results in one paragraph

The tracking subsystem worked: the PV-cell differential drove the servo correctly and the median response time came in well under the 10-minute target. The energy comparison is **not valid as a test of tracking**, because Configuration B sat near its open-circuit point for most of the test window (no meaningful load), and post-test analysis of the direction-sensor ADC showed signal saturation that was anticipated at design time but not mitigated in the build. The 10% energy-gain criterion is reported as **not demonstrated** (not "unmet"); a repeat trial under corrected load and sensor conditions is needed. See the paper for the full write-up.

## Layout

- `paper_ieee_format.pdf` — Original IEEE-format submission.
- `latex/` — LaTeX (IEEEtran) reproduction of the same paper.
  - `paper.tex` — LaTeX source.
  - `paper.pdf` — Compiled output.
  - `figures/` — Plots, CAD renders, schematic, prototype photo referenced by `paper.tex`.
- `data/` — Raw serial-logger CSV output from the physical test rig, at 30-second intervals with columns `millis, elapsed_hms, pv_left, pv_right, angle, bus_v, current_mA, power_mW`.
  - `CONFIGA_20260827_8hours.csv` — 8-hour fixed-panel (Config A) baseline run.
  - `Config_B_20260901_1.csv`, `Config_B_20260901_2.csv`, `Config_B_20260901_3.csv` — Tracking-panel (Config B) runs.

## Rebuilding the paper

```
cd latex
pdflatex paper.tex
```

Figures in `latex/figures/` are referenced by `paper.tex`; no external assets required.

## Status

Raw experimental data plus the associated write-up, not a finished product. Known data-validity issues in the Config B runs (ADC ceiling saturation, near-open-circuit operation) are documented in the paper's Results and Discussion sections.

## About the author

**Rohan Rajesh** — North Carolina School of Science and Mathematics, Durham campus (NCSSM-Durham), class of 2027. From Charlotte, NC.

Interests: electrical engineering, systems engineering, control and embedded systems, system architecture, and renewables.

Contact: rajesh.v.rohan@gmail.com

