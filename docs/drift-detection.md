```markdown
# Drift & Spike Detection Logic

## Baseline vs Current Window Comparison

The system compares template frequencies between two selected time windows.

### New Template Detection
If a template appears in the current window but not in the baseline window:
→ Mark as NEW

### Spike Detection
If a template exists in both windows:
- Compute ratio = currentCount / baselineCount
- If ratio exceeds threshold (e.g., 3x)
- And currentCount exceeds minimum threshold
→ Mark as SPIKE

This enables behavioral change detection in log activity.
