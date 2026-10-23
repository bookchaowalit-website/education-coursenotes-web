# Field Notes — course study archive

A personal archive of course notes. Each note is an MDX file in
`content/course-notes/` with its source course, platform, instructor, level,
duration, and date kept beside the text.

## Features
- Note pages render the MDX body (headings, lists, code) via
  `next-mdx-remote/rsc`; JavaScript expressions in MDX are blocked.
- Archive search across metadata and note text, with a topic filter that is
  linkable (`/course-notes?topic=react`) from the home page's topic index.
- Per-note title/description/canonical metadata; sitemap lists every note
  (`NEXT_PUBLIC_SITE_URL` overrides the origin).
- `/api/mcp` JSON-RPC tools: `list_course_notes`, `get_course_note`,
  `search_course_notes`, `list_topics` (read-only).

## Adding a note
Create `content/course-notes/<kebab-case-slug>.mdx`:

```yaml
---
title: "React Fundamentals"
course: "React Complete Course"
platform: "Udemy"
topic: "react"
date: "2024-01-10"
instructor: "Instructor name"
duration: "8h 30m"
level: "beginner"
---
## Notes in markdown…
```

## Run
```bash
npm ci
npm run dev
```

## Checks
```bash
npm run lint
npm run typecheck
npm test           # node:test: note parsing/dates and the MCP handler
npm run build
```

CI (`.github/workflows/ci.yml`) runs the shared Node workflow (lint, typecheck, tests, build) and the shared security
scan on every push and PR to `main`.

## Status

Experiment. The portfolio card review (2026-10) marks it Live→Experiment: three sample MDX notes, no completion
status, not the "50+ courses" once claimed. Recommended for archive (owner decision, nothing archived); it is kept at
the L1 baseline only (shared CI, lockfile, no hidden errors).

Live: https://coursenotes.bookchaowalit.com (deployed by Vercel CLI from an old Git link; a push does not deploy).
