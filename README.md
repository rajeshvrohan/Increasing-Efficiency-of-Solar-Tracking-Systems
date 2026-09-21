# Increasing Efficiency of Solar Panels Using Tracking Systems

Rohan Rajesh — Pioneer Academics / science-fair research project.

A side-by-side comparison of a fixed solar panel (**Configuration A**) against a single-axis solar tracker (**Configuration B**) that uses paired PV cells as directional sensors (instead of the LDRs common in prior work) to drive a servo-actuated mount via an Arduino. An INA219 current sensor logs voltage, current, and power from both panels to microSD on the same time base so any energy gain is attributable to tracking alone (no MPPT, no other efficiency measures).

## Results in one paragraph

The tracking subsystem worked: the PV-cell differential drove the servo correctly and the median response time came in well under the 10-minute target. The energy comparison is **not valid as a test of tracking**, because Configuration B sat near its open-circuit point for most of the test window (no meaningful load), and post-test analysis of the direction-sensor ADC showed signal saturation that was anticipated at design time but not mitigated in the build. The 10% energy-gain criterion is reported as **not demonstrated** (not "unmet"); a repeat trial under corrected load and sensor conditions is needed. See the paper for the full write-up.

## Layout

- `solar-tracker-research/paper_ieee_format.pdf` — Original IEEE-format submission.
- `solar-tracker-research/latex/` — LaTeX reproduction: `paper.tex`, `paper.pdf`, and `figures/` (CAD renders, schematic, prototype photo, result plots).
- `solar-tracker-research/data/` — Raw serial-logger CSVs at 30 s intervals with columns `millis, elapsed_hms, pv_left, pv_right, angle, bus_v, current_mA, power_mW`:
  - `CONFIGA_20260827_8hours.csv` — 8-hour fixed baseline (Config A).
  - `Config_B_20260901_{1,2,3}.csv` — Tracking runs (Config B).
- `solar-tracker-research/README.md` — Sub-folder README with more detail.

## Rebuilding the paper

```
cd solar-tracker-research/latex
pdflatex paper.tex
```

Figures in `latex/figures/` are referenced by `paper.tex`; no external assets are required.

## Status

Raw experimental data plus the associated write-up. Known data-validity issues in Config B (ADC ceiling saturation, near-open-circuit operation) are documented in the paper's Results and Discussion sections.
