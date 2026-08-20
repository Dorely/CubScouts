# CubScouts
Planning docs for Cub Scouting

## Current Calendar

[`Current_Year/calendar.md`](Current_Year/calendar.md) is the tracked current-year calendar mirror.

A local, gitignored `Current_Year/calendar.google-doc.md` may point to the authoritative Google Doc. When that file is present, the Google Doc is the source of truth and the Markdown calendar should be kept synchronized with it.

## Print Stylesheets (VS Code "Print" extension)
This repo includes a global Markdown print stylesheet at `styles/markdown.print.css` for consistent, readable print/PDF output from VS Code.

Configure the VS Code "Print" extension setting:

Print › Markdown: Stylesheets
URLs or paths for CSS for rendered Markdown. For workspace relative paths, use 'workspace.resource/path/to/your.css'. For absolute filesystem paths, use 'absolute/path/to/your.css'. Otherwise, paths are relative to the base document ('./my.css' would be in the same folder as the document), or absolute URLs (https://...). For folders or multi-file selections use absolute, absolute filesystem paths, or workspace-relative paths.

Recommended values:
- Single file (e.g., from a file in `2025-2026/`): `../styles/markdown.print.css`
- Workspace-wide or multi-file selection: `workspace.resource/styles/markdown.print.css`

Notes:
- Calendar-specific rules are scoped to tables immediately following month headings (`h3 + table`, `h4 + table`) so other tables (e.g., denner rotation) are unaffected.
- Keep `styles/markdown.print.css` under version control; adjust only if print layout needs change.
