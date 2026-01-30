# Atlas Dashboard (Sanitized)

This is a **public-safe** dashboard that renders a **sanitized snapshot** of Atlas state.

## Generate snapshot
From the main workspace:

```bash
python3 tools/export_dashboard_state.py
```

This writes:
- `dashboard-public/public/state.json`

## Host
This is a static site. Point any static host (Render Static Site) at:
- **Publish directory:** `dashboard-public/public`
- **Build command:** *(none)*

## Safety
The exporter only reads:
- `BACKLOG.md`
- `PROJECTS.md`
- `CONTINUATION.md`

…and redacts common secret patterns (emails + token-like strings).
