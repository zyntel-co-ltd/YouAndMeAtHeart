# Legacy project status archive

**Append-only engineering history.** Full content migrated from root `PROJECT_STATUS.md` on 2026-03-28. Do not attach this entire file to Claude if redundant with `START_HERE.md`.

---
# You And Me At Heart — Project Status & Functional Specification

**Last updated:** 2026-03-27  
**Updated by:** Cursor  
**Product type:** Client build — static marketing site  
**Production URL:** TBD (confirm hostname when live)  
**Repo:** https://github.com/zyntel-co-ltd/YouAndMeAtHeart  

This document follows **`knowledge` → `zyntel-playbook/05-infrastructure/project-status-file.md`** (13 sections).

---

## 1. What This Product Is

Static marketing / landing site for the **You And Me At Heart** client. Delivers a single-page experience with brand assets and optional GitHub Action wiring for Cursor rules sync from Pulse when connected. Typical Zyntel agency static delivery pattern (HTML + images + lightweight tooling).

---

## 2. Current State

**Status:** Maintenance / content updates as needed  
**Phase:** v1 static  
**Paying clients:** Agency client (see agency agreements)

### Build summary

| Module / Area | State | Notes |
|---------------|-------|-------|
| Landing | ✅ Live | `index.html` |
| Brand assets | ✅ Live | `images/`, `converted_logos/`, `site.webmanifest` |
| Tooling | ✅ Live | `images/logo_converter.py` |
| CI / rules sync | ✅ Live | `.github/workflows/pulse-sync.yml` (if connected) |

### Planned

- [ ] Confirm production hostname and hosting target in this file when live

---

## 3. Stack & Infrastructure

| Layer | Technology | Provider | Environment | Notes |
|-------|------------|----------|-------------|-------|
| Frontend | Static HTML | TBD (Vercel / Netlify / Cloudflare Pages / GitHub Pages) | — | No build step required |
| Tooling | Python | Local | — | Logo conversion helper |

### Environment variables

None required for static hosting of `index.html`.

---

## 4. Data Model

**N/A** — no application database.

---

## 5. Features & Functionality (complete specification)

### Feature: Marketing landing page

**Status:** ✅ Live  
**Module:** Marketing  
**User:** Site visitors  

**What it does:** Renders the client landing experience from `index.html` with linked assets.

**How it works (technical):** Static files only; no server-side runtime.

Key files:
- `index.html` — primary page
- `images/` — logos and media

**Business rules:**
- Content changes must preserve client brand approvals.

**What it does NOT do:**
- No CMS, no auth, no payments.

---

### Feature: Logo conversion helper

**Status:** ✅ Live  
**Module:** Tooling  
**User:** Developers  

**What it does:** `logo_converter.py` assists generating/converting logo variants for web use.

**How it works (technical):** Python script under `images/`.

---

## 6. User Roles & Permissions

| Role | Who | Can | Cannot |
|------|-----|-----|--------|
| Visitor | Public | Read static content | Write |
| Maintainer | Zyntel ENG | Edit repo, deploy | — |

---

## 7. Integrations & External Dependencies

| System | How connected | Direction | What it does | Fallback if down |
|--------|---------------|-----------|--------------|------------------|
| GitHub | git | R/W | Source | Local files only |
| Pulse (optional) | `pulse-sync.yml` | Read | Cursor rules sync | Manual rules |

---

## 8. API Surface

**N/A**

---

## 9. Active Issues & Blockers

| Issue | Linear ID | Priority | Status | Notes |
|-------|-----------|----------|--------|-------|
| Production URL | — | Low | Open | Fill when live |

---

## 10. Key Decisions Made

| Decision | What was decided | Why | Date |
|----------|------------------|-----|------|
| Static HTML | No framework | Fast, cheap hosting for v1 | Prior |

---

## 11. Branch State

| Branch | Purpose | Last active |
|--------|---------|-------------|
| `main` | Production source | ongoing |

---

## 12. How to Run Locally

Open `index.html` in a browser or serve with any static server, for example:

```bash
git clone git@github.com:zyntel-co-ltd/YouAndMeAtHeart.git
cd YouAndMeAtHeart
# python -m http.server 8080
```

---

## 13. Cursor Context (Read Before Writing Any Code)

- **Base branch:** `main`
- **Linear team:** Engineering (ENG) — agency client project
- **After any change:** Update `Last updated` and Section 2/5 when behaviour or hosting changes
- **Rule:** `.cursor/rules/project-status-enforcement.mdc`
- **Do not commit** `repomix-output.xml` (gitignored)

---

## Repo map (high-signal)

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
