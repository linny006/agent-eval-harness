# agent-eval-harness

> 실제 GitHub 이슈에서 AI 코딩 에이전트를 비교하는 라이브 오픈소스 벤치마크

[English](./README.md) · [中文](./README_CN.md) · [日本語](./README_JA.md) · **한국어** · [Español](./README_ES.md) · [Português](./README_PT.md)

[![Stars](https://img.shields.io/github/stars/linny006/agent-eval-harness?style=for-the-badge&logo=github)](https://github.com/linny006/agent-eval-harness/stargazers)
[![Last Commit](https://img.shields.io/github/last-commit/linny006/agent-eval-harness?style=for-the-badge)](https://github.com/linny006/agent-eval-harness/commits)

---

재현 단계가 포함된 실제 GitHub 이슈를 대상으로 코딩 에이전트를 실행하는 표준화된 벤치마크 스위트입니다. 정적인 학술 벤치마크와 달리, 매주 업데이트되는 공개 리더보드를 제공해서 OpenCode, Codex, Claude Code 같은 에이전트를 현실적인 시나리오에서 비교할 수 있습니다.

이 목록은 **GitHub Actions cron에 의해 15분마다 자동 업데이트**됩니다. 각 커밋은 업스트림 데이터 소스의 실제 변경 사항을 반영합니다——새 항목 추가, 만료된 항목 제거——따라서 표시된 내용이 항상 최신임을 신뢰할 수 있습니다.

---

15분마다 GitHub Action이 `tracker.py`를 실행합니다. 이 스크립트는 다음을 수행합니다:

1. `GitHub Search API`에서 최신 상태를 가져옵니다.
2. `data/items.json`(이전 스냅샷)과 diff를 수행합니다.
3. `<!-- TRACKER_TABLE_* -->` 마커 사이의 위 테이블을 다시 씁니다.
4. 변경 사항이 있으면 `feat: +N added, -M removed (timestamp)`로 커밋합니다.

외부 서비스 없음. 유료 API 없음. 공개 데이터 소스와 무료 GitHub Action만 사용합니다.

---

## 📋 Live data

라이브 데이터는 영문 README를 참고하세요

---

## 🔗 Related live trackers

- [trending-claude-skills](https://github.com/linny006/trending-claude-skills) — What's shipping in Claude Skills this week (`topic:claude-skills`)
- [mcp-servers-live](https://github.com/linny006/mcp-servers-live) — Live index of newest MCP servers (`topic:mcp-server`)
- [cursor-rules-live](https://github.com/linny006/cursor-rules-live) — Newest Cursor rules and .cursorrules patterns (`topic:cursor-rules`)
- [claude-code-plugin-tracker](https://github.com/linny006/claude-code-plugin-tracker) — Claude Code plugins and hook configs (`topic:claude-code`)
- [llm-agents-radar](https://github.com/linny006/llm-agents-radar) — Newest LLM agent frameworks (`topic:llm-agent`)
- [rag-radar](https://github.com/linny006/rag-radar) — Newest RAG implementations and tools (`topic:rag`)
- [llm-eval-tracker](https://github.com/linny006/llm-eval-tracker) — Newest LLM evaluation tools and benchmarks (`topic:llm-eval`)
- [agent-framework-radar](https://github.com/linny006/agent-framework-radar) — Newest agent frameworks shipping on GitHub (`topic:agent-framework`)
- [vector-db-live](https://github.com/linny006/vector-db-live) — Newest vector DB projects and integrations (`topic:vector-database`)
- [llmops-radar](https://github.com/linny006/llmops-radar) — Newest LLMOps tooling (observability, deployment) (`topic:llmops`)
- [prompt-tools-live](https://github.com/linny006/prompt-tools-live) — Newest prompt-engineering tools and prompt repos (`topic:prompt-engineering`)
- [skills-tracker](https://github.com/linny006/skills-tracker) — Tracking new GitHub 'skills' repos (`topic:agent-skills`)
- [awesome-agent-skills](https://github.com/linny006/awesome-agent-skills) — Curated auto-updated awesome-list of AI agent skills (`topic:agent-skills`)

---

## 📜 License

MIT — see `LICENSE`.
