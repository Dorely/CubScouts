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
- Use Serena tools for search and read, NOT edits.
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
- DO NOT USE `replace_regex` for multi-file or structural edits; prefer targeted patches to avoid accidental corruption.
- Use `create_text_file` for new files and `apply_patch` for updates.
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

## Common Commands (via Serena execute)
- Discover markdown files: `rg --files -uu -g "*.md"`
- Find lesson headings: `rg -n "^#|^##|^###" 2025-2026/lessons`
- Find external links: `rg -n "https?://"`
- Find TODOs or placeholders: `rg -n "TODO|TBD|fixme"`

## Completion Checklist (gate)
- Relevant references scanned; style and structure matched.
- Edits done with Serena; diffs are small and targeted.
- Headings and lists are consistent; links look correct.
- Any new files placed in the correct folder with consistent naming.
- Plan updated and steps marked completed.
