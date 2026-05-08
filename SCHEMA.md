# Wiki Schema

## Scope

This wiki tracks insights extracted from YouTube videos through NotebookLM outputs.

## Source of truth

- `raw/youtube-links/*.md`: incoming video links
- `raw/notebooklm-analysis/*.md`: NotebookLM summaries/study notes
- `raw/notebooklm-mindmaps/*.json`: NotebookLM mind map outputs

## Build rule

- Incremental build only runs when files under `'raw/*.md'` or `'raw/**/*.md'` changed.
- If no raw changes in diff window, set `skipped:no_raw_changes` and stop.

## Wiki outputs

- `wiki/sources/`
- `wiki/entities/`
- `wiki/concepts/`
- `wiki/comparisons/`
- `wiki/overview/`
- `wiki/queries/`

