# LangGraph Case Triage Demo

This repository contains a compact, offline demo notebook that implements a LangGraph-style case triage scaffold.

Contents
- `langgraph_case_triage_demo.ipynb` — Jupyter notebook demo (agents, deterministic simulation, inline graph visualization).

Quick start
1. Install Python dependencies (recommended in a venv):

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
pip install --upgrade pip
pip install networkx pydot
```

2. Install Graphviz (required to render PNGs from DOT). On Windows, download and install from: https://graphviz.org/download/
Make sure the Graphviz `bin` directory (containing `dot.exe`) is on your PATH.

3. Open and run the notebook:

```powershell
# from the repo root
jupyter notebook langgraph_case_triage_demo.ipynb
```

What the notebook does
- Provides a small LangGraph-like shim (Graph, Edge) as a fallback when `langgraph` is not available.
- Implements agents: Triage, KBSearch, Salesforce (in-memory), TicketAction, Enrichment, Prioritization, Escalation, Notification.
- Runs a deterministic, seeded simulation (no external credentials or network calls required).
- Renders an inline graph using `networkx` + `pydot` + Graphviz (`dot`) and provides a textual fallback.
- Includes a smoke test cell that validates expected behavior.

Notes
- The notebook is intentionally offline and safe: notifications are recorded, not sent.
- If you only want to reproduce the visualization, ensure `networkx`, `pydot` and Graphviz are installed and available in your PATH.

License
- MIT

Contact
- For questions: open an issue or contact the repo owner.
