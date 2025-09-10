# Repository Guidelines

## Project Structure & Modules
- Root contains documentation and planning content (Markdown):
  - `2025-2026/`: pack calendar and Bear den lesson plans
    - `lessons/`: individual lesson plans (e.g., `Paws_for_Action_Lesson_Plan.md`)
  - `reference/`: reference material grouped by `required/` and `elective/`
  - `README.md`: top-level notes
  - Hidden/auxiliary: `.git/`, `.claude/`
- This repo is documentation-focused; there is no code build. Changes are primarily Markdown authoring and organization.

## Reference First (Required)
- Before editing lessons, scan related items in `reference/required/` or `reference/elective/` to align terminology and requirements.
- Reuse existing headings and section patterns to keep consistency across lessons (e.g., Overview, Materials, Requirements, Activities, Safety, Notes).
- When adding new content, check for existing, similar files to match tone and structure.

## Authoring Style & Naming
- Markdown style: ATX headings (`#`, `##`, `###`), one H1 per file.
- Lists: use `-` for bullets; keep bullets concise; prefer consistent ordering.
- Links: prefer relative links inside the repo; include full URLs only when necessary.
- File names: keep existing underscore style (e.g., `Bear_Habitat_Lesson_Plan.md`).
- Headings: mirror existing lesson headings; avoid inventing new heading names unless needed.
- Keep language clear, actionable, and age-appropriate for Cub Scouts.

# Agent Workflow & Tooling Requirements (Codex + Serena)

## Non-Negotiables
- Use Serena tools for searching and reading, NOT edits.
- Do not use Serena tools for editing, do not use the `replace_regex` tool
- Make minimal, focused changes; avoid unrelated mass edits.
- Validate Markdown basics (headings, lists, links) before claiming completion.

## Search & Read First (Serena)
- Use these Serena tools to understand current content and avoid duplication:
  - `find_file` to discover files (e.g., `*.md`).
  - `search_for_pattern` to find topics/sections (tight patterns over broad ones).
  - `read_file` to open targeted files or sections.
- Always scan:
  - `2025-2026/lessons/` for existing lesson conventions and shared sections.
  - `reference/` for requirements and terminology to reuse.
  - `README.md` for top-level repo notes.

## Editing (Serena)
- DO NOT USE serena for editing. Do not use `replace_regex` especially as it can corrupt files.
- Keep changes small and well-scoped; group related edits in one patch when appropriate.
- Preserve existing formatting and spacing; avoid reflowing text not being changed.

## Serena Memory (When/How)
- Purpose: persist project knowledge that benefits future tasks across sessions.
- Tools: `list_memories`, `read_memory`, `write_memory`, `delete_memory`.
- When to read: at task start if relevant; don’t read the same memory more than once per conversation.
- When to write/update: after confirming durable patterns (e.g., lesson template, naming, checklists).
- What to store: conventions, common paths, style templates, recurring checklists.
- What not to store: secrets/PII, large documents, transient task state, speculative notes.
- Naming: short, descriptive snake_case (e.g., `lesson_style_guide`, `file_map`, `editing_checklist`). Prefer updating an existing memory over near-duplicates.
- Format: concise Markdown bullets with file paths in backticks where helpful.

## Maintaining Serena Memories & Indexes
- Core memories to keep current:
  - `repo_index`: concise map of key files/folders (paths in backticks) and their purpose.
  - `lesson_style_guide`: shared lesson structure, heading names, and tone.
  - `completion_checklist`: quick gate list for docs edits.
  - `suggested_commands`: ripgrep patterns and other non-destructive helpers.
  - Area-specific indexes as needed (e.g., `calendar_print_styles`).
- When to update memories:
  - After adding/renaming/moving/removing notable files or folders (e.g., new `styles/`, new lesson plans, calendar changes) → update `repo_index`.
  - After establishing or revising conventions/templates (e.g., lesson headings, print CSS patterns) → update `lesson_style_guide` or a dedicated memory.
  - After refining process steps (e.g., validation flow) → update `completion_checklist`.
- How to update (Serena tools):
  - Read once if relevant: `read_memory` for the target memory to avoid drift; don’t re-read repeatedly in the same conversation.
  - Write succinct changes: `write_memory` with additive, consolidated bullets; prefer updating an existing memory over creating near-duplicates.
  - Keep it portable: use workspace‑relative paths (in backticks); avoid user‑specific absolute paths.
  - Be specific, not exhaustive: store durable patterns, not transient task notes.
- `repo_index` expectations:
  - Include: top‑level directories, notable files (calendar, lessons, reference groups, styles), and a short purpose line for each.
  - Reflect current structure after edits (adds/renames/moves/removals); keep it brief.
  - Don’t duplicate full file lists when not helpful; link representative examples.
- Validation after edits:
  - Confirm that new/changed paths in the workspace match what’s written in memories.
  - If you add a new memory (e.g., `calendar_print_styles`), reference where it applies (e.g., `2025-2026/calendar.md`) and summarize key rules.
  - Avoid leaking sensitive data; keep entries minimal and future‑useful.

## Validate (Docs)
- Headings: one H1; logical `##/###` hierarchy; consistent section names across lessons.
- Links: run quick scans for `http` and relative paths; ensure no obvious broken anchors.
- Spelling/typos: quick skim for common mistakes in changed sections.
- Consistency: match voice, tense, and list formatting of adjacent files.
- Whitespace: ensure trailing newline; avoid trailing spaces in edited lines.

## Do/Don’t During Execution
- Do:
  - Maintain a small update plan (`update_plan`) for multi-step tasks.
  - Keep diffs minimal and focused on the requested change.
  - Reference files/lines with backticks (e.g., `2025-2026/calendar.md:1`).
- Don’t:
  - Overhaul formatting unrelated to the task.
  - Introduce new sections/headings without checking existing patterns.
  - Mass-rename files without prior review.

## Completion Checklist (gate)
- Relevant references scanned; style and structure matched.
- Headings and lists are consistent; links look correct.
- Any new files placed in the correct folder with consistent naming.
- Plan updated and steps marked completed.

## Print Stylesheets (VS Code Print Extension)
- Global stylesheet: `styles/markdown.print.css` for Markdown print/preview.
- Configure in VS Code under:
  Print › Markdown: Stylesheets
  URLs or paths for CSS for rendered Markdown. For workspace relative paths, use 'workspace.resource/path/to/your.css'. For absolute filesystem paths, use 'absolute/path/to/your.css'. Otherwise, paths are relative to the base document ('./my.css' would be in the same folder as the document), or absolute URLs (https://...). For folders or multi-file selections use absolute, absolute filesystem paths, or workspace-relative paths.
- Suggested values:
  - Single file (e.g., from `2025-2026/`): `../styles/markdown.print.css`
  - Workspace-wide or multi-file: `workspace.resource/styles/markdown.print.css`
- CSS scope:
  - Calendar column widths apply only to tables immediately following month headings (`h3 + table`, `h4 + table`).
  - Other tables (e.g., `2025-2026/Bear_Den_Denner_Rotation.md`) are unaffected.
- Agent notes:
  - Do not rename or move the stylesheet unless asked; update memories (`calendar_print_styles`, `repo_index`) if changed.
  - Avoid broad table rules that affect non-calendar docs; keep styles minimal and print-focused.
