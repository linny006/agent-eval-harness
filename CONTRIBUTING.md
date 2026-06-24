# Contributing to Agent Eval Harness

Thanks for your interest in contributing! This guide covers everything a new contributor needs to get started.

## Table of Contents

- [Quick Start](#quick-start)
- [Project Structure](#project-structure)
- [Running Locally](#running-locally)
- [Making Changes](#making-changes)
- [Submitting a Pull Request](#submitting-a-pull-request)
- [Development Tips](#development-tips)

## Quick Start

```bash
# 1. Fork and clone
git clone https://github.com/gtx20060124-bot/agent-eval-harness.git
cd agent-eval-harness

# 2. Install dependencies
pip install -r requirements.txt

# 3. Run the tracker
python tracker.py

# 4. Check the README was updated
cat README.md | grep -A5 "TRACKER_TABLE"
```

## Project Structure

```
agent-eval-harness/
├── tracker.py              # Main script: fetches, diffs, and rewrites README
├── requirements.txt        # Python dependencies (httpx)
├── data/
│   └── items.json          # Previous snapshot of tracked items
├── .github/
│   └── workflows/
│       └── update.yml      # GitHub Actions cron (every 15 min)
├── README.md               # Auto-updated leaderboard table
├── README_CN.md            # Chinese translation
├── README_ES.md            # Spanish translation
├── README_JA.md            # Japanese translation
├── README_KO.md            # Korean translation
└── README_PT.md            # Portuguese translation
```

### Key Components

- **`tracker.py`** — The core script. It queries the GitHub Search API for repos with the `llm-eval` topic, diffs against the previous snapshot, and rewrites the README table between `<!-- TRACKER_TABLE_START -->` and `<!-- TRACKER_TABLE_END -->` markers.
- **`data/items.json`** — The previous snapshot used for diffing. Added/removed items are tracked here.
- **`.github/workflows/update.yml`** — GitHub Actions workflow that runs `tracker.py` on a 15-minute cron schedule.

## Running Locally

### Install Dependencies

```bash
pip install -r requirements.txt
```

The only runtime dependency is `httpx>=0.27`.

### Run the Tracker

```bash
python tracker.py
```

This will:
1. Fetch the latest repos from GitHub Search API
2. Diff against `data/items.json`
3. Rewrite the README table
4. Write a new `data/items.json` snapshot

You can also run it with a custom GitHub token for higher rate limits:

```bash
GITHUB_TOKEN=your_token_here python tracker.py
```

### Run Against a Sample Issue

To test the tracker against a specific sample, modify `GITHUB_QUERY` in `tracker.py`:

```python
# Example: track repos with a specific topic
GITHUB_QUERY = 'topic:agent-eval sort:stars-desc'
```

Then run `python tracker.py` and inspect the generated table in `README.md`.

## Making Changes

### Adding a New Column to the Tracker Table

1. Edit the `render_table()` function in `tracker.py` to include the new field.
2. Update the `fetch_items()` function to extract the data from the GitHub API response.
3. Run `python tracker.py` locally to verify the output.

### Updating the Upstream Data Source

Replace `GITHUB_QUERY` in `tracker.py` with your desired search query. The script supports any GitHub Search API query syntax.

### Translations

Translations live in `README_*.md` files. When the English README changes significantly, update the translations accordingly.

## Submitting a Pull Request

1. **Fork** the repository and create a feature branch:
   ```bash
   git checkout -b feat/add-new-column
   ```

2. **Make your changes** and test locally:
   ```bash
   python tracker.py
   ```

3. **Commit** with a descriptive message:
   ```bash
   git add -A
   git commit -m "feat: add star_count column to tracker table"
   ```

4. **Push** to your fork:
   ```bash
   git push origin feat/add-new-column
   ```

5. **Open a Pull Request** on GitHub. Include:
   - A clear description of what changed
   - Screenshots or output samples if applicable
   - Any manual testing you performed

## Development Tips

- The README table is rewritten between `<!-- TRACKER_TABLE_START -->` and `<!-- TRACKER_TABLE_END -->` markers. Never edit the table content manually — it will be overwritten.
- The `diff_counts()` function tracks added and removed items. If items appear/disappear, the commit message reflects this.
- Rate limits: Anonymous requests get ~10 req/min. Set `GITHUB_TOKEN` for ~5000 req/hr.
- The workflow runs every 15 minutes. For faster testing, use `workflow_dispatch` in the Actions tab.

## Questions?

Open an issue if you have questions or need help getting started.
