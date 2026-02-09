# DivineForge

Work log site built with Hugo and the Blowfish theme. Deployed via Cloudflare Pages.

## Structure

```
/content
  /worklog    — Structured work log entries (Context, Constraint, Action, Outcome)
  /notes      — Short code snippets, config notes, observations
  /about.md   — About page
  /archive.md — Search/archive page
/config/_default
  hugo.toml           — Site configuration
  languages.en.toml   — Language, date format (YYYY.MMDD), author
  params.toml         — Theme parameters
  menus.en.toml       — Navigation (Work Log, Notes, About, Archive, Tags)
  markup.toml         — Markdown rendering
/archetypes
  worklog.md  — Template for new work log entries
  notes.md    — Template for new notes
/themes/blowfish — Blowfish Hugo theme
```

## Content Types

**Work Log** — Mandatory sections: Context, Constraint/Problem, Action Taken, Outcome/Result.

**Notes** — Short, tagged, factual. Maximum 500 words.

## Date Format

YYYY.MMDD (e.g. 2024.1120)

## Local Development

```
hugo server -D
```
