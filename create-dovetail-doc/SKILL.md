---
name: create-dovetail-doc
description: Create a Dovetail doc from a local markdown file or a title using the dt CLI.
license: MIT
metadata:
  author: dovetail
  version: "1.0"
---

# Create a Dovetail doc (`dt doc`)

Creates a doc in your Dovetail workspace from a local markdown file or a plain title. The new doc opens in your browser when created.

## Prerequisites

1. `dt` is installed — if not, run `npm install -g @heydovetail/dt`
2. Workspace is configured — if not, run `dt init`
3. `DOVETAIL_API_KEY` is set (from workspace Settings > API)

## Usage

```
dt doc <file.md | title words...> [flags]
```

- If the argument is an **existing file**, its contents become the doc body and the title is taken from the first `#` heading (or the filename).
- If the argument is **not a file**, all words are joined as the doc title and an empty doc is created.

## Examples

```bash
# Create a blank doc by title
dt doc Hello World

# Create a doc from a markdown file
dt doc ./research-summary.md

# Create a doc from a file with a custom title
dt doc ./raw-notes.md --title "Q1 Research Summary"

# Create a doc inside a project
dt doc ./notes.md --project "Customer Research"

# Create a doc inside a folder
dt doc ./report.md --folder "Reports"
```

## Flags

| Flag | Description |
|------|-------------|
| `--title string` | Doc title (default: first `#` heading or filename) |
| `--project string` | Dovetail project name (looked up by title) |
| `--project-id string` | Dovetail project ID |
| `--folder string` | Dovetail folder name (looked up by title) |
| `--folder-id string` | Dovetail folder ID |
| `--config string` | Config file (default: `./dt.json`) |
| `-v, --verbose` | Show detailed progress logs |
| `-q, --quiet` | Minimal output (errors and summary only) |

If neither `--project`/`--project-id` nor `--folder`/`--folder-id` is specified, the doc is created at the workspace level.

## Troubleshooting

| Problem | Fix |
|---------|-----|
| `401 Unauthorized` | API key is invalid or expired — check `DOVETAIL_API_KEY` |
| `403 Forbidden` | API key lacks write permissions for the target project or folder |
| Project/folder not found | Confirm the name matches exactly (case-sensitive); use `--project-id` / `--folder-id` to avoid name lookup |
| `dt: command not found` | Run `npm install -g @heydovetail/dt` and ensure npm's bin directory is on your `PATH` |
