# log-template-mining-drift-detection
Time-windowed log template mining with drift and spike detection. Developed under Samsung PRISM industry research initiative (privacy-compliant public demo).
# Log Template Mining with Drift & Spike Detection

## Overview

This project demonstrates time-windowed log template mining with automatic detection of:

- New log templates
- Sudden frequency spikes in existing templates
- Time-range comparison for behavioral change detection

The system is designed to help identify regressions, abnormal activity, or deployment-related issues through structured log analysis.

---

## Industry Context

This work was developed as part of the **Samsung PRISM industry research initiative**.

The repository contains a privacy-compliant public demonstration using synthetic logs.  
All proprietary data, internal infrastructure details, and confidential components have been excluded.

---

## Key Features

- Time-windowed log ingestion
- Template extraction
- Frequency aggregation
- New pattern detection
- Spike detection (baseline vs current window)
- JSON output for UI integration
- Scalable log processing design

---

## How Drift Detection Works

The system compares two time windows:

- Baseline Window (earlier logs)
- Current Window (recent logs)

For each template:

- If it exists only in the current window → marked as **NEW**
- If its frequency increases significantly compared to baseline → marked as **SPIKE**

This helps quickly identify system behavior changes.

---

## Sample Data

Synthetic logs are provided in the `sample_data/` folder.

- `baseline.log`
- `current.log`

These files simulate normal behavior and post-change behavior.

---

## Output Structure (Example)

```json
{
  "newTemplates": [
    {
      "template": "ERROR Auth token invalid for userId=*",
      "count": 2
    }
  ],
  "spikeTemplates": [
    {
      "template": "WARN Cache miss for key=*",
      "baselineCount": 2,
      "currentCount": 3,
      "ratio": 1.5
    }
  ]
}
