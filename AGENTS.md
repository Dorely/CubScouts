# Repository Charter

## Purpose

This repository is a documentation workspace for Cub Scout program planning. It holds lasting reference material and the working plans built from that material.

There is no application to build or test. Work here is authoring, organizing, and refining Markdown documents so leaders can plan and run the program.

## What Lives Here

The repository has two complementary kinds of content:

- **Reference documentation** — durable information about adventures, requirements, and program facts. Build and maintain this collection so later planning can rely on it instead of reconstructing source material each time.
- **Yearly planning** — the documents used to run a program year. This commonly includes calendars, lesson plans, activity plans, worksheets, and other resources. Other planning documents may be added when they serve a real need.

Use the reference collection when creating or revising yearly plans. Keep plans grounded in what the repository already records. When a needed fact is missing, say so rather than inventing it.

Completed years belong in the archive. They may be consulted for context, but they are not the default pattern for new work.

## How Work Should Proceed

Prefer building and using the repository's own documentation over fetching or restating material from outside the workspace.

### Authoritative Current-Year Calendar

The current-year calendar may have a live source configured in the gitignored file `Current_Year/calendar.google-doc.md`.

- If `Current_Year/calendar.google-doc.md` exists, open its linked Google Doc and treat that document as authoritative for current-year dates, events, assignments, and schedule changes.
- Keep `Current_Year/calendar.md` as a tracked Markdown mirror of the authoritative Google Doc. Reconcile the Markdown before relying on it, and update it after every live calendar change.
- Make calendar changes in the Google Doc first, then mirror the same changes in `Current_Year/calendar.md`.
- Do not put the Google Doc URL in tracked files or maintain a duplicate Word calendar.
- If the local source file is absent or the Google Doc cannot be accessed, use the Markdown as the best available record and identify that it could not be verified against the authoritative calendar.

Typical order of work:

1. Establish or update the relevant reference documentation.
2. Plan the year from those references and the year's actual scheduling needs.
3. Create the supporting plans and materials the year requires.

Do not skip ahead, invent requirements, or pull in external content unless that work is requested. Iterate on format as the year develops; do not treat prior years or earlier drafts as fixed templates.

## Agent Behavior

- Do only the work that was asked. Do not populate empty folders, fetch sources, or create planning files in anticipation of later requests.
- Read nearby documents before editing so terminology, names, and purpose stay consistent.
- Put each document in the folder that matches its role: reference, calendar, lesson, activity, resource, or archive.
- When information is missing, incomplete, or unverified, identify the gap. Do not fill it with assumptions or unsourced detail.
- Make focused changes. Preserve content and formatting that are not part of the request.
- After editing, check headings, lists, relative links, and whether the document still has a single clear purpose.

## Authoring

- Write Markdown with ATX headings and one H1 per document.
- Use relative links for files inside the repository.
- Keep filenames descriptive and consistent with the surrounding folder.
- Keep each document focused on one purpose.
- Do not add external URLs or copied source content unless the source and need are part of the task.

## Print

Use `styles/markdown.print.css` for Markdown print and PDF output from VS Code's Print extension.

Configure **Print: Markdown: Stylesheets** with:

- A document in a year folder: `../styles/markdown.print.css`
- Workspace-wide or multi-file printing: `workspace.resource/styles/markdown.print.css`

Keep the stylesheet in the repository. Calendar table rules apply only to tables immediately after `h3` or `h4` headings; do not broaden those selectors unless print layout requirements change.
