# Contributing to Agent Eval Harness

Thank you for your interest in contributing to **Agent Eval Harness**! This document provides a step-by-step guide for first-time contributors to set up the project locally, run the evaluation script, and submit pull requests.

## 📁 Directory Structure

Before diving in, here is a quick overview of how the repository is structured:

* `.github/workflows/` — Contains the GitHub Actions cron configurations that run the tracker automatically.
* `data/` — Holds `items.json` which stores the state snapshot of the tracked repositories.
* `tracker.py` — The core Python script that queries the GitHub API, computes diffs, and updates the README tables.
* `requirements.txt` — Lists the Python dependencies needed to run the project.
* `README*.md` — The localized readmes that are dynamically updated by the script.

---

## 🛠️ Local Development Setup

Follow these steps to get the project running on your local machine:

### 1. Fork and Clone the Repository
First, fork this repository to your own GitHub account by clicking the **Fork** button at the top right of the page. Then, clone your fork locally:

```bash
git clone https://github.com/YOUR-USERNAME/agent-eval-harness.git
cd agent-eval-harness