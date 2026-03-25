# Nexus DC — Data Center Platform Dashboard (Demo)

Interactive prototype of a data center management platform based on market and technology pain analysis (Energy, Cooling, AI DCIM).

## What's inside

- **Overview** — PUE, power, leak incidents; load and temperature charts with ML forecast; thermal maps; recent events.
- **Energy** — Energy Orchestrator: grid/DG/BESS status; Grid Interconnection (Grid Deadlock); microgrid/BESS; 7-day load forecast.
- **Cooling** — Cooling Guard: leak risk index, CDUs, pressure/temperature; Pain 1 (corrosion, Quick Connectors, seals); RUL and predictive triggers.
- **Infrastructure** — Pain 4: DCIM–K8s integration, thermal inertia, GPU Throttling; live rack map, utilization, load distribution.
- **Alerts** — Log (Cooling Guard, Energy, AI DCIM, GPU Throttling).
- **Reports** — PUE, Cooling Guard, orchestration, Grid & Cost of Delay, Competitive Intelligence.
- **Economics & pains** — OPEX savings, Cost of Delay, ROI; competitor comparison and pain coverage.
- **Market & competitors** — Link to Economics tab for positioning and competitor table.

## How to run

**Option 1** — script (from project folder):
```bash
cd /home/cursor/datacenter-platform-dashboard
chmod +x serve.sh && ./serve.sh
```

**Option 2** — manual:
```bash
cd /home/cursor/datacenter-platform-dashboard
python3 -m http.server 8080
```

Open in browser: **http://localhost:8080**  
Or open `index.html` directly (some features may work without a server).

**If localhost doesn't work** (remote environment, VPN) — see **[ОТКРЫТЬ_ДАШБОРД.md](ОТКРЫТЬ_ДАШБОРД.md)** (port forwarding in Cursor and other options).

Dashboard data is sample/demo only.

For a **permanent shareable link** (GitHub Pages, Netlify, Vercel, Cursor Ports), see **[PERMANENT_LINK.md](PERMANENT_LINK.md)**.

Detailed tab-by-tab description and ideas for future features — **[DASHBOARD_GUIDE.md](DASHBOARD_GUIDE.md)**.
