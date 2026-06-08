---
name: update-github-info
description: Draft website updates for Mona's GitHub Info site from official GitHub sources.
engine: copilot
on:
  workflow_dispatch: {}
  schedule:
    - cron: '17 9 * * *'
safe-outputs:
  assign-to-agent:
    model: auto
  create-pull-request:
    title-prefix: "[mona] "
    draft: true
    fallback-as-issue: false
tools:
  edit: {}
  web-fetch: {}
network:
  allowed:
    - github.com
    - github.blog
---

# Update Mona's GitHub Info website

Read `notes/mona-notes.md` before making any content changes.

Use these official sources:
- GitHub Blog latest posts: https://github.blog/latest/
- GitHub Changelog: https://github.blog/changelog/
- Awesome Copilot workflows: https://awesome-copilot.github.com/workflows/

Update `site/content/github-info.md` with concise, practical GitHub updates for readers.
When content is drawn from the GitHub Blog or GitHub Changelog, include the source context.

Create a pull request for Mona to review. Do not write directly to `main`.
Use `safe-outputs` with `create-pull-request` so the agent can propose changes safely.
