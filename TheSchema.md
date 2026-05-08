# TheSchema

## Required flow

1. Sync repo (`stash -> fetch -> checkout main -> pull --ff-only -> stash pop`).
2. Detect changed markdown in `'raw/*.md'` and `'raw/**/*.md'`.
3. If changed file is under `raw/youtube-links/`:
   - Parse YouTube URL(s).
   - Use NotebookLM to ingest URL(s) and generate:
     - report (markdown)
     - mind map (json)
   - Save into `raw/notebooklm-analysis/` and `raw/notebooklm-mindmaps/`.
   - Commit and push.
4. If changed files are under `raw/notebooklm-analysis/` or `raw/notebooklm-mindmaps/`:
   - Run llm-wiki incremental graph update.
   - Update `wiki/*`, `index.md`, `log.md`.
   - Commit and push.
   - Send Telegram summary.
5. If no raw changes, skip.

## Logging

Each run writes `logs/webhook-runs/{run_id}.md` with payload, file diffs, created/updated files, commit hash, push result, and errors.

