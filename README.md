# blog-content-repo

Hugo source for https://blog.guidi.dev — markdown in, published site out, no manual build step.

## How it publishes
This repo has no CI. Content is polled and built entirely in-cluster by the `blog/` workload defined
in the `aguidirh/k3s` repo (`git-sync` → `hugo` → `caddy`, all running as one pod on the Pi). Push to
`main` and the live site updates within about a minute — no Docker build, no registry, no ArgoCD.

## Writing a post
Add a file under `content/posts/`, e.g. `content/posts/my-post.md`:

```markdown
---
title: "My Post"
date: 2026-07-16
draft: false
---

Body in markdown.
```

Commit and push to `main`. That's the entire publishing step.
