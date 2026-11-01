# AGENTS.md — Repository Guide

Static GitHub profile repository. It contains no application code, build pipeline, tests, database, or AWS resources.

## Repository structure

```
ichiche/
  README.md      # GitHub profile README
  Image/         # local SVG/PNG assets used by README badges and headings
  AGENTS.md      # this file
```

## External services

- No AWS, cloud runtime, database, or CI/CD configuration.
- `README.md` embeds remote badge and banner services through image URLs: `capsule-render.vercel.app`, `readme-typing-svg.demolab.com`, `img.shields.io`, and `komarev.com`. These are presentation-only; no credentials or build step are involved.
- Local assets under `Image/` are referenced by filename and must keep their existing paths.
