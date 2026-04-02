---
title: "otto-hermann.me"
date: 2026-04-02
description: "what it is"
order: 1
---

This [website](https://otto-hermann.me) should make it easier for people to
learn about me; it includes external links (e.g.
[GitHub](https://github.com/orgs/ojhermann-org/repositories)) and entries, like
this one.

Technical stuff about this site:

- [personal-website](https://github.com/ojhermann-org/personal-website) is the
  core web application
  - built with [Astro](https://astro.build/)
  - deployed on [Cloudflare Pages](https://pages.cloudflare.com/)
- Dependencies
  - [Nix](https://nixos.org/) manages high-level tooling e.g. LSPs
  - [Bun](https://bun.com/) handles
    [TypeScript](https://www.typescriptlang.org/) dependencies
- [prek](https://github.com/j178/prek) runs pre-commit hooks
- CI is managed at the org-level, where I also
  [set repo-level checks](https://github.com/ojhermann-org/github-settings/blob/main/repositories.tf).
