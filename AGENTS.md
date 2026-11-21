# AGENTS.md — Repos

Stable constraints for the GitHub profile repository `ichiche`. Nothing here runs: the deliverable is the rendered profile, produced from `README.md` plus the tracked SVG set in `Image/`. Read this before editing.

Workspace-wide rules live in `C:\Repos\AGENTS.md`; this file owns what is specific to `ichiche`. Scratch and temporary files go in `C:\Repos\ichiche\.tmp\`, never in the workspace root.

## Repository structure

```
ichiche/
  README.md                 # the rendered profile: banner, positioning, stack, links
  Image/                    # tracked SVG stack icons referenced by README.md
    azure-original.svg
    amazonwebservices-original.svg
    python-original.svg
    typescript-original.svg
    powershell-original.svg
  .tmp/                     # tool output and scratch; ignored, never durable
```

## Document authority

- `README.md` is the single narrative surface and `Image/` is the icon set: never use the README as a draft pad, and never inline an icon as base64 to avoid adding a file.
- Every public claim — skill, tool, CI, quality — must correspond to something that exists and runs. Do not advertise a capability that is not in place.
- `README.md` owns every public statement: positioning, skill list, tool table, contact routes.
- `Image/` owns the icon set; `README.md` only references file names, never re-encodes or duplicates them.
- The GitHub rendering at `github.com/ichiche` is an output, not a source. Never edit remote profile settings, topics, or pinned repositories to compensate for a README problem.
- This repository is a profile, not a product surface: project facts belong to their owning repository, and this file must not mirror them.

## Cloud and external services

- No code, no CI, no cloud resource. This repository does not call AWS, Azure, or any API at build time.
- `README.md` embeds three third-party renderers: `capsule-render` (banners), `readme-typing-svg` (typing line), and `shields.io` (contact badges). Treat them as external dependencies: every piece of information a reader needs must also exist as text, so the page survives a renderer outage.
- Badge and image URLs carry no tokens, signed query strings, or analytics identifiers. A new third-party embed needs owner approval.

## Data and privacy

- The published contact routes (`ic@eiu.today`, LinkedIn, GitHub) are intentional public profile data.
- No credentials, tokens, private repository links, addresses, phone numbers, or other identifying data beyond what the profile already publishes.
- Never paste real-user content, internal screenshots, or employer-confidential detail into the README or an icon file's metadata.

## Validation

- After any change, open `github.com/ichiche` and check the rendered page: images load, badges resolve, tables and banner align, and the page stays readable in both light and dark themes.
- Check that every relative path referenced by `README.md` exists under `Image/`, and that every external URL returns a response.
- There is no test suite here. Do not create CI, a test framework, or a build step for this repository as a side effect of an unrelated change.

## Conventions

- `README.md`, commit messages, and this file are English; commit subjects are imperative and capitalized.
- Keep the existing HTML shape: centered `<div align="center">` blocks for banner and footer, one `<p>` row for icons, one three-column `Area | Tools` table.
- Keep animation and emoji restrained. Do not add a component that conflicts with the current visual language; match an existing block instead of inventing one.
- When replacing an icon, keep the source file name and aspect ratio, and remove the old file only after the README no longer references it.

## Scratch and temporary files

- Scratch root: `C:\Repos\ichiche\.tmp\`; `.gitignore` keeps it ignored, and nothing is written to the workspace root `C:\Repos\.tmp\`.
- Write the absolute path, or run the command with `C:\Repos\ichiche` as the working directory so a relative `.tmp\` still resolves inside the repository. A relative `.tmp\` created from `C:\Repos` is a defect.
- Scratch holds downloaded SVGs, render screenshots, and draft fragments. Nothing in `.tmp/` is ever the only copy of an asset that the README references.

## Git and production safety

- One change per boundary: one commit moves one narrative section or one icon set, so history stays reviewable and revertible.
- This repository's `main` branch is the public profile: a push is a publish. Do not push to it without explicit authorization.
- An agent may edit files and validate rendering; commit, push, and any profile setting change stay with the owner, as `README.md` states publicly.
- No force push, no history rewrite, and no asset deletion without checking that `README.md` no longer references the file.
