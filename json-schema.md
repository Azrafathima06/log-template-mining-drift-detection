# JSON Output Schema

The system generates structured JSON for UI integration.

## Example Output

```json
{
  "analysisWindow": {
    "baseline": {
      "start": "2025-01-10 10:00:00",
      "end": "2025-01-10 10:59:59"
    },
    "current": {
      "start": "2025-01-10 11:00:00",
      "end": "2025-01-10 11:59:59"
    }
  },
  "templates": [
    {
      "templateId": "T1",
      "template": "WARN Cache miss for key=*",
      "baselineCount": 2,
      "currentCount": 3,
      "status": "SPIKE"
    },
    {
      "templateId": "T2",
      "template": "ERROR Auth token invalid for userId=*",
      "baselineCount": 0,
      "currentCount": 2,
      "status": "NEW"
    }
  ]
}
