# personal-website

Otto Hermann's personal website, built with Astro 5 and deployed to Cloudflare Pages.

## Tech stack

- **Astro 5** — static site generator
- **TypeScript** — strict mode via `astro/tsconfigs/strict`
- **Bun** — package manager and script runner
- **Nix** — devshell provides `bun` and `typescript-language-server`
- **prettier** + **prettier-plugin-astro** — formatting (via bun devDependencies, not Nix)
- **prek** — pre-commit hooks
- **Cloudflare Pages** — deployment target

## Local development

The Nix devshell activates automatically via direnv when entering this directory.
If direnv is not available, enter the shell manually:

```
nix develop
```

Install dependencies (first time, or after `package.json` changes):

```
bun install
```

Start the dev server at `http://localhost:4321`:

```
bun run dev
```

## Common commands

| Command                 | Purpose                              |
| ----------------------- | ------------------------------------ |
| `bun run dev`           | Start dev server at localhost:4321   |
| `bun run build`         | Build to `dist/`                     |
| `bun run preview`       | Preview the built site locally       |
| `bun run typecheck`     | Run `astro check` (TypeScript)       |
| `bun run format:check`  | Check formatting with prettier       |
| `bun run format:write`  | Auto-format all files with prettier  |

## Content

Blog posts live in `src/content/blog/` as Markdown files. Filename convention:

```
YYYY-MM-DD-slug.md
```

Required frontmatter:

```markdown
---
title: "Post title"
date: YYYY-MM-DD
description: "One-sentence description used in meta tags and the index."
---
```

## Pre-commit hooks

`prek.toml` configures hooks that run on every commit:

- **builtin:** trailing whitespace, end-of-file fixer, merge conflict detection, TOML/JSON validation, private key detection, no commits to `main`
- **local:** `format:check`, `typecheck`, `build` — mirrors CI exactly

## Deployment

Merges to `main` trigger a Cloudflare Pages deploy via GitHub Actions (added in PR 3).
PRs run the same checks without deploying.
