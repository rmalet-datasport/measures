# Planned Measures — Datasport

Static roadmap page of marketing/product measures. No build, no dependencies: open `index.html` in a browser to check changes.

- `index.html` — the roadmap (Roadmap tab = Gantt, Detailed measures tab = table + detail modal). All data lives in the `measures` array in the inline `<script>`; everything else (summary, filters, months, timeline) is computed from it.
- `matrice-touchpoints.html` — standalone product × timing matrix (Coach / Magazine), separate page.
- `screenshots/` — images referenced by measures.
- `notes/` — personal notes, git-ignored.

## Editing measures

Almost every request is an edit of one or more entries in `measures`. The field reference is in the comment right above the array — read it before adding fields.

- `stream`: `global | coach | b2b | b2c | data | magazine | offline | seo`, or an array for multi-stream measures.
- `months`: `["YYYY-MM"]` for one month, `["start", "end"]` for an inclusive range. "Move to November" = set `months: ["2026-11"]` (or shift the range).
- `status`: `todo | inprogress | done | canceled | onhold`.
- `effort` / `impact`: `low | med | high | vhigh`.
- `responsible`: a name or an array of names. Only `Raphael` and `Katrin` have filter buttons / colored badges.
- `type: "foundation"` adds the Foundation badge.
- `link` / `linkLabel`: string, or matching arrays for several tickets.
- `description`: free text, `\n` for line breaks, `•` for bullets.
- `screenshots`: paths with spaces URL-encoded (`screenshots/foo%20bar.png`).

Conventions:
- Measures with the same name exist per stream (e.g. "CTA - Start list (Coach)" and "(Magazine)"). When asked about "start list", "athlete search" etc. without a stream, change both variants and say so.
- Measures parked for discussion: `status: "todo"`, moved to the target month, `description: "To be rediscussed with my boss."`.
- Content in the file is in English, even when the request is in French.
- When creating a measure (or marking one `done`), if a ticket/PR/Figma link or a screenshot would make sense and none was given, ask for it before finishing. Don't ask for pure strategy/planning items.
- Keep the existing 2-space indentation and trailing commas.

## Adding a stream

A new stream needs: a `.dot-<stream>` CSS color, a filter button in **both** `#roadmap-filters` and `#filters`, and an entry in `streamOrder`.

## Git

Commit only when asked. Short imperative messages describing which measures changed (see `git log`).
