# You And Me At Heart — Project Status

**Last updated:** 24 March 2026  
**Updated by:** Cursor  
**Repo:** https://github.com/zyntel-co-ltd/YouAndMeAtHeart

---

## Repo map (high-signal)

Generated from a `repomix --no-files` snapshot (paths only). **No secrets or file contents** are included here.

### Top-level

```text
.github/
images/
```

### Key entrypoints

```text
index.html
images/logo_converter.py
PROJECT_STATUS.md
```

## What This Project Is

Static marketing / landing site for the You And Me At Heart client. Single-page `index.html`, brand and image tooling under `images/` (includes `logo_converter.py` for asset generation). Same delivery pattern as other Zyntel static client sites.

---

## Current State

**Status:** Maintenance / content updates as needed  
**Phase:** v1 static

### What is built

- [x] Landing page (`index.html`)
- [x] Converted logo set (`images/converted_logos/`, `site.webmanifest`)
- [x] GitHub Action `pulse-sync.yml` — Cursor rules sync from Pulse (if connected)

### Planned / optional

- [ ] Confirm production hostname and hosting target in this file when live

---

## Stack

| Layer | Technology |
|-------|------------|
| Frontend | Static HTML |
| Tooling | Python helper scripts for image conversion |

---

## Branch state

| Branch | Purpose |
|--------|---------|
| `main` | Production source |

---

## Cursor context

- **Linear team:** Engineering (ENG) — agency client project.
- **Do not commit** `repomix-output.xml` (gitignored).
