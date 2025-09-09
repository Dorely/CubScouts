# Suggested Commands

- List Markdown files:
  - `rg --files -uu -g "*.md"`
- Scan lesson headings:
  - `rg -n "^#|^##|^###" 2025-2026/lessons`
- Find external links:
  - `rg -n "https?://"`
- Find relative links:
  - `rg -n "\]\(\.\.?/"`
- Find TODOs/placeholders:
  - `rg -n "TODO|TBD|fixme"`
- Search for a specific requirement across reference and lessons:
  - `rg -n "^### Requirement [0-9]+" reference 2025-2026/lessons`
- Preview section titles in a single file (example):
  - `rg -n "^#{1,3} " 2025-2026/lessons/Paws_for_Action_Lesson_Plan.md`
- Show top-level directories/files:
  - `ls -la`
- Count lessons:
  - `rg --files 2025-2026/lessons -g "*.md" | wc -l`
