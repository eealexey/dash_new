# Synthetic Data Pipeline (CustDev Demo)

This folder contains a practical synthetic data generator for mining/DC dashboard demos after CustDev interviews.

## Why this schema

The feature set is aligned with common operational telemetry and alerting logic:

- Predictive-maintenance synthetic dataset patterns (multivariate telemetry, threshold-driven failures): UCI AI4I 2020.
- Mining ops alert patterns (temperature thresholds, hashrate and consumption shifts, offline behavior): minerstat help docs.

The goal is not physical perfection, but realistic operational behavior to stress-test product scenarios.

## Output files

Generated to `output/` (or custom `--out-dir`):

- `telemetry.csv`: minute-level telemetry by device.
- `alerts.csv`: rule-based alerts with recommendation text.
- `incidents.json`: grouped high-priority events for "where it is burning" view.
- `summary.json`: high-level run stats.

## Fields in telemetry.csv

- `timestamp`
- `site_id`, `rack_id`, `device_id`
- `hashrate_ths`
- `power_kw`
- `temp_c`
- `inlet_temp_c`
- `fan_rpm`
- `efficiency_th_per_kw`
- `rul_days`
- `predicted_temp_72h_c`
- `event_tag` (injected scenario label)

## Quick start

```bash
cd /home/cursor/datacenter-platform-dashboard/synthetic_data_pipeline
python3 generate_synthetic_data.py --hours 72 --sites 1 --racks-per-site 6 --devices-per-rack 20 --seed 42
```

## Example presets

### 1) Fast demo (small)

```bash
python3 generate_synthetic_data.py --hours 24 --sites 1 --racks-per-site 2 --devices-per-rack 8 --events-per-day 10 --seed 11
```

### 2) Board/exec demo (full 72h)

```bash
python3 generate_synthetic_data.py --hours 72 --sites 2 --racks-per-site 8 --devices-per-rack 24 --events-per-day 24 --seed 42
```

### 3) Stress scenario (many incidents)

```bash
python3 generate_synthetic_data.py --hours 48 --sites 1 --racks-per-site 6 --devices-per-rack 20 --events-per-day 45 --seed 7
```

## How to use in the dashboard

1. Use `summary.json` and `incidents.json` to drive top KPI cards and the "next 72h risk" panel.
2. Use `alerts.csv` for critical/warning tabs and "next action" content.
3. Use `telemetry.csv` for line charts and rack drill-down.
4. Re-generate with different `--seed` before each CustDev call to avoid repeating identical numbers.
