# AGENTS.md — Repository Guide

Static GitHub profile repository. It contains no application code, build pipeline, tests, database, or AWS resources.

## Repository structure

```
ichiche/
  README.md      # GitHub profile README
  Image/         # local 128x128 SVG icons for the stack row in README
  AGENTS.md      # this file
```

## External services

- No AWS, cloud runtime, database, or CI/CD configuration.
- `README.md` embeds remote badge and banner services through image URLs: `capsule-render.vercel.app`, `readme-typing-svg.demolab.com`, and `img.shields.io`. These are presentation-only; no credentials or build step are involved.
- `Image/` holds five Devicon icons (Azure, AWS, Python, TypeScript, PowerShell). `README.md` references them by filename, so do not rename or move them; replace an icon only when the stack changes.
