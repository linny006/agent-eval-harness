<!--
SEO: agent eval harness
-->

<div align="center">

# Agent Eval Harness

Live, open-source benchmark for comparing AI coding agents on real GitHub issues

[![Stars](https://img.shields.io/github/stars/linny006-tecch/agent-eval-harness?style=for-the-badge&logo=github)](https://github.com/linny006-tecch/agent-eval-harness/stargazers)
[![Last Commit](https://img.shields.io/github/last-commit/linny006-tecch/agent-eval-harness?style=for-the-badge)](https://github.com/linny006-tecch/agent-eval-harness/commits)
[![Items](https://img.shields.io/badge/Tracked_Items-0-brightgreen?style=for-the-badge)](#)
[![Updated](https://img.shields.io/badge/Updates-every_15min-blue?style=for-the-badge)](#)

**⭐ Star this repo to bookmark — fresh data every 15 minutes**

</div>

---

## 💡 What is this?

A standardized benchmark suite that runs coding agents against live, real-world GitHub issues with reproduction steps. Unlike static academic benchmarks, it outputs a weekly-updated public leaderboard, enabling developers to compare agents like OpenCode, Codex, and Claude Code in realistic scenarios.

This list is **auto-updated every 15 minutes** by a GitHub Actions cron.
Each commit reflects a real change in the upstream data source — new items added,
expired items removed — so you can rely on what you see being current.

---

## 📋 Current Items

> ⏰ Last updated: _pending first run_
>
> Data source: `GitHub Search API`
>
> The table below is rewritten on every cron tick. Star the repo to bookmark.

<!-- TRACKER_TABLE_START -->
_The first cron run will populate this section._
<!-- TRACKER_TABLE_END -->

---

## 🔍 How it works

Every 15 minutes, a GitHub Action runs `tracker.py`. That script:

1. Fetches the latest state from `GitHub Search API`.
2. Diffs against `data/items.json` (the previous snapshot).
3. Rewrites the table above between the `<!-- TRACKER_TABLE_* -->` markers.
4. Commits `feat: +N added, -M removed (timestamp)` if anything changed.

No external services. No paid APIs. Just a public data source and a free GitHub Action.

---

## 🤝 Contributing

See `CONTRIBUTING.md` — usually you don't need to: the tracker keeps itself current.
If you spot a data-source bug or want to suggest a new column for the table, open
an issue.

---

## 📜 License

MIT — see `LICENSE`.

## More from linny006


- [**Agent Eval Harness**](https://github.com/linny006/agent-eval-harness) — Live, open-source benchmark for comparing AI coding agents on real GitHub issues (⭐ 0)

- [**Prompt Tools Live**](https://github.com/linny006/prompt-tools-live) — Live-updating tracker of prompt engineering tools, libraries, and techniques — refreshed every 15 minutes (⭐ 0)

- [**LLMOps Radar**](https://github.com/linny006/llmops-radar) — Live index of the newest LLMOps tooling — track what's shipping in LLM observability and deployment (⭐ 0)

- [**Vector DB Live Tracker**](https://github.com/linny006/vector-db-live) — Live-updating landscape of vector database projects, integrations, and benchmarks — refreshed every 15 minutes (⭐ 0)

- [**Agent Framework Radar**](https://github.com/linny006/agent-framework-radar) — Live index of the newest agent frameworks shipping on GitHub, sorted by recency not stars (⭐ 0)
