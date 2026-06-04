## 🏢 Agentic Revenue Engine

> *"10 AI sales agents close $1.6M in pipeline. Watch every decision, every deal, every moment of competitive intelligence — live."*

The flagship demo. Ten specialised AI sales agents run simultaneously, each with a role, a budget, and three deals to close. They autonomously gather intelligence from six data sources, build pitches, and close deals — all visualised through a live Hierarchical Edge Bundling graph.

### The 10 Agents

| Agent | Role | Target |
|-------|------|--------|
| 👩‍💼 Aria | New Business Hunter | $95k |
| 👨‍💼 Kai | Account Expander | $95k |
| 👔 Morgan | Enterprise Closer | $300k |
| 🎯 Sam | SMB Volume Lead | $80k |
| 🤝 Alex | Channel & Partners | $115k |
| 🌏 Jordan | APAC / EMEA Lead | $165k |
| 🔄 Casey | Retention Specialist | $85k |
| 🚀 Riley | PLG Motion Lead | $45k |
| ♟️ Drew | Strategic Accounts | $445k |
| ⚔️ Blake | Competitive Intel | $180k |

### What You're Watching

**Left panel** — 10 live agent cards with real-time status, budget bars, stamina bars, deal pipeline, and timestamped decision logs.

**Centre — Hierarchical Edge Bundling (D3 v7)**
- Agent nodes on the right arc, data source nodes on the left arc
- Glowing bundled paths appear as agents gather intelligence
- Edge thickness = intel frequency
- Radial histogram arcs on source nodes = which agents hit each source and how many times, coloured by agent
- Rotating dashed ring = active agent
- Cyberspace particle network in the background (55 floating dots with proximity connections)

**Right panel** — Live heatmap (agents × sources), revenue leaderboard, efficiency rankings, top performer card.

**⚡ News ticker** — Bloomberg-style event strip. Every deal, milestone, leader change, and bandwidth alert scrolls through with contextual messages:
- 🚀 First deal of session
- 💎 New session record deal  
- 🏆 Agent goes 3/3 (full sweep)
- 🎯 $500k / 🔥 $1M milestones
- 📡 Source activations with specific context

**🧠 Agent Reasoning Board** — Kanban view, one column per agent. Every decision with Claude's full reasoning text from each API response.

### Architecture

```
Claude Haiku API — 10 agents sharing a global rate limiter (1.35s between calls)

Aria  Kai  Morgan  Sam  Alex  Jordan  Casey  Riley  Drew  Blake
  \    |    /    |    |    |     |     |     /    /
   ╔══════════════════════════════════════════╗
   ║     6 Data Sources                       ║
   ║  Market Signals · Lead DB · Competitor   ║
   ║  Pricing Engine · CRM · Social Signals   ║
   ╚══════════════════════════════════════════╝
```

Each agent runs an independent `Perceive → Reason → Act → Repeat` loop using Claude's tool use API. Tools: `plan_outreach`, `access_source`, `gather_intel`, `close_deal`.

### Controls

| Control | Function |
|---------|----------|
| ▶ **RUN AGENTS** | Deploy all 10 simultaneously |
| ⏸ **PAUSE / Resume** | Freezes API queue, SVG animations, ticker |
| **0.5× 1× 2×** | Speed — affects sleep delays between calls |
| 🧠 **Reasoning Board** | Every decision + Claude's thinking |
| ⤢ ⤡ **Expand** | Full-screen agent or KPI view |
| 📄 **Download Report** | Printable PDF-ready mission debrief |

---

## About

Built by **Saagar Devadiga** — Data Engineer & AI Developer, Brisbane, Australia.

---
