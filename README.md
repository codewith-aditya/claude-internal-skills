# Claude Internal Skills

> Archive of **42 Agent Skills** shipped inside Claude — the `public/` core skills plus the `examples/` advanced skills that ship with the Claude app (Cowork / cloud sessions). Extracted from a live Claude cloud container at `/mnt/skills/`.

![skills](https://img.shields.io/badge/skills-42-blue)
![public](https://img.shields.io/badge/public%2F-8-green)
![advanced](https://img.shields.io/badge/examples%2F-34-purple)
![license](https://img.shields.io/badge/license-mixed-orange)

---

## Screenshots

| Archive overview | Download options |
|---|---|
| ![archive overview](claude-tools/screenshots/01-archive-overview.png) | ![download options](claude-tools/screenshots/02-download-options.png) |

![skills folder structure](claude-tools/screenshots/03-skills-folder-structure.png)

---

## What this is

These are the actual `SKILL.md` + scripts + assets bundles that Claude loads when it decides a task needs a skill. Two groups:

- **`PUBLIC-TOOLS/`** (8) — came from `/mnt/skills/public/`. The core set every Claude user gets: Word, PDF, PowerPoint, Excel, file reading, frontend design.
- **`ADVANCED-TOOLS/`** (34) — came from `/mnt/skills/examples/`. The advanced set tied to Claude's agentic features: browser control, computer use, Google Workspace, research, skill authoring, plus a large family of personal-assistant / errand skills (calls, cancellations, refills, bookings).

Each skill is a self-contained folder with a `SKILL.md` (frontmatter `name` + `description`, then instructions), and usually `scripts/`, `references/`, `templates/` or `assets/`.

```
claude-tools/
├── ADVANCED-TOOLS/           # /mnt/skills/examples/
│   ├── algorithmic-art/
│   ├── artifact-emulator/
│   └── ...
├── PUBLIC-TOOLS/             # /mnt/skills/public/
│   ├── docx/
│   ├── pdf/
│   └── ...
└── screenshots/
```

---

## Skills catalog

### Core / public (8)

| Skill | What it does | License |
|---|---|---|
| [docx](claude-tools/PUBLIC-TOOLS/docx) | Create, read, edit Word `.docx`/`.dotx`, tracked changes, comments, images | Anthropic |
| [pdf](claude-tools/PUBLIC-TOOLS/pdf) | Merge, split, rotate, watermark, fill forms, encrypt, OCR | Anthropic |
| [pdf-reading](claude-tools/PUBLIC-TOOLS/pdf-reading) | Read/inspect PDFs: text extraction, rasterization, tables, forms | Anthropic |
| [pptx](claude-tools/PUBLIC-TOOLS/pptx) | Build/edit PowerPoint decks, templates, themes, thumbnails, QA | Anthropic |
| [xlsx](claude-tools/PUBLIC-TOOLS/xlsx) | Build/edit Excel/CSV, formulas with mandatory recalc, financial models | Anthropic |
| [file-reading](claude-tools/PUBLIC-TOOLS/file-reading) | Router that picks the right extraction tool per uploaded file type | Anthropic |
| [frontend-design](claude-tools/PUBLIC-TOOLS/frontend-design) | Distinctive, non-templated UI design direction + typography | Apache-2.0 |
| [product-self-knowledge](claude-tools/PUBLIC-TOOLS/product-self-knowledge) | Ground facts about Anthropic products (Claude Code, API, plans, pricing) | none |

### Design & visual (8)

| Skill | What it does | License |
|---|---|---|
| [canvas-design](claude-tools/ADVANCED-TOOLS/canvas-design) | Posters and static art as `.png`/`.pdf`, 20+ bundled fonts | Apache-2.0 |
| [algorithmic-art](claude-tools/ADVANCED-TOOLS/algorithmic-art) | p5.js generative art, seeded randomness, interactive artifacts | Apache-2.0 |
| [paint](claude-tools/ADVANCED-TOOLS/paint) | Watercolor-style painting written as code (`paintkit`, 64 KB toolkit) | Apache-2.0 |
| [theme-factory](claude-tools/ADVANCED-TOOLS/theme-factory) | 10 preset themes + on-the-fly themes for any artifact | Apache-2.0 |
| [web-artifacts-builder](claude-tools/ADVANCED-TOOLS/web-artifacts-builder) | Multi-component HTML artifacts with React + Tailwind + shadcn/ui | Apache-2.0 |
| [brand-guidelines](claude-tools/ADVANCED-TOOLS/brand-guidelines) | Anthropic brand colors and typography for artifacts | Apache-2.0 |
| [slack-gif-creator](claude-tools/ADVANCED-TOOLS/slack-gif-creator) | Animated GIFs sized/optimized for Slack, with validators | Apache-2.0 |
| [artifact-emulator](claude-tools/ADVANCED-TOOLS/artifact-emulator) | Opens artifacts in the real viewer, screenshots them, reads console errors (Playwright) | Anthropic |

### Research, writing & learning (6)

| Skill | What it does | License |
|---|---|---|
| [deep-research](claude-tools/ADVANCED-TOOLS/deep-research) | Multi-source research with subagents, synthesized narrative report | none |
| [doc-coauthoring](claude-tools/ADVANCED-TOOLS/doc-coauthoring) | 3-stage doc workflow: context gathering → refinement → reader testing | none |
| [internal-comms](claude-tools/ADVANCED-TOOLS/internal-comms) | Status reports, leadership updates, newsletters, incident reports (Anthropic's own formats) | Apache-2.0 |
| [setup-writing-style](claude-tools/ADVANCED-TOOLS/setup-writing-style) | Builds a voice profile from your sent messages via stylometry (`stylometry.py`) | none |
| [learn](claude-tools/ADVANCED-TOOLS/learn) | Teaching methodology: diagnose, one step per turn, quiz, flashcards | Apache-2.0 |
| [import-memory](claude-tools/ADVANCED-TOOLS/import-memory) | Import another assistant's memory export into Claude memory | none |

### Developer tooling (2)

| Skill | What it does | License |
|---|---|---|
| [skill-creator](claude-tools/ADVANCED-TOOLS/skill-creator) | Create/improve skills, run evals, benchmark with variance, optimize descriptions | Apache-2.0 |
| [mcp-builder](claude-tools/ADVANCED-TOOLS/mcp-builder) | Build MCP servers in Python (FastMCP) or Node/TS SDK | Apache-2.0 |

### Browser & computer control (3)

| Skill | What it does | License |
|---|---|---|
| [built-in-browser](claude-tools/ADVANCED-TOOLS/built-in-browser) | Claude desktop browser pane: tabs, persistent sign-ins, site approvals | Anthropic |
| [chrome-browser](claude-tools/ADVANCED-TOOLS/chrome-browser) | Claude in Chrome extension: real tabs, sign-ins, GIF recording, console | Anthropic |
| [computer-use](claude-tools/ADVANCED-TOOLS/computer-use) | Desktop control: screenshots, clicks, typing, tiered app access rules | Anthropic |

### Personal assistant / errands (13)

These assume the agent can browse, dial, or pay on the user's behalf.

| Skill | What it does | License |
|---|---|---|
| [cancel-unsubscribe](claude-tools/ADVANCED-TOOLS/cancel-unsubscribe) | Cancel subscriptions, audit statements for recurring charges | Apache-2.0 |
| [return-refund](claude-tools/ADVANCED-TOOLS/return-refund) | Returns/refunds at any retailer, policy lookup, labels or calls | Apache-2.0 |
| [prescription-refill](claude-tools/ADVANCED-TOOLS/prescription-refill) | Pharmacy refills online or by phone | Apache-2.0 |
| [call-to-book](claude-tools/ADVANCED-TOOLS/call-to-book) | Phone call to book appointments, calendar check + AI disclosure | Apache-2.0 |
| [file-expenses](claude-tools/ADVANCED-TOOLS/file-expenses) | Expense submission across Benepass / Brex / Concur / Expensify | Apache-2.0 |
| [benepass-reimbursement](claude-tools/ADVANCED-TOOLS/benepass-reimbursement) | End-to-end Benepass reimbursement with receipt upload | Apache-2.0 |
| [file-form](claude-tools/ADVANCED-TOOLS/file-form) | Bureaucratic forms: jury duty, tickets, passport, DMV, permits | Apache-2.0 |
| [financial-calculator](claude-tools/ADVANCED-TOOLS/financial-calculator) | Tax, loan, rent-vs-buy, retirement scenarios (pure math) | Apache-2.0 |
| [grocery-shopping](claude-tools/ADVANCED-TOOLS/grocery-shopping) | Grocery delivery: store pick, list building, budget, cart | Apache-2.0 |
| [meal-delivery](claude-tools/ADVANCED-TOOLS/meal-delivery) | Food ordered to arrive at a target time | Apache-2.0 |
| [hire-help](claude-tools/ADVANCED-TOOLS/hire-help) | Book TaskRabbit / Handy / Thumbtack style service providers | Apache-2.0 |
| [event-planning](claude-tools/ADVANCED-TOOLS/event-planning) | Venues, guest lists, vendors, budgets, timelines | Apache-2.0 |
| [morning](claude-tools/ADVANCED-TOOLS/morning) | Morning brief as styled HTML artifact, or recurring weekday task | none |

### Documents & Google (2)

| Skill | What it does | License |
|---|---|---|
| [docs](claude-tools/ADVANCED-TOOLS/docs) | Claude's native editable documents (exports to Word / PDF / MD / Google Docs) | none |
| [google-workspace](claude-tools/ADVANCED-TOOLS/google-workspace) | Drive / Docs / Sheets / Slides connectors + layout helper scripts | none |

---

## How to use

**Claude Code / any skill-aware agent** — drop a folder into your skills directory:

```bash
cp -r claude-tools/PUBLIC-TOOLS/pdf ~/.claude/skills/pdf
```

**Cowork / cloud session** — the originals live at `/mnt/skills/public/` and `/mnt/skills/examples/`.

**Hermes Agent** — `skill_manage(action='create')` with the `SKILL.md` body, or copy into `~/.hermes/skills/`.

**Portability notes**

- Skills whose instructions reference Claude's own tools (`mcp__Claude_Browser__*`, `mcp__claude-in-chrome__*`, `mcp__computer-use__*`, Google connectors, `/mnt/user-data/uploads/`) only run inside Claude. The instructions are still useful as reference — swap in your own browser/terminal tool.
- The document skills (`docx`, `pptx`, `xlsx`, `pdf`) are the most portable: plain Python/JS libraries (`python-docx`, `pptxgenjs`, `openpyxl`, `pypdf`, LibreOffice) with validation and QA steps.
- `.skill` files (not included here) are just each folder zipped — `zip -r name.skill name/`.

---

## Coverage vs. the public repo

[`anthropics/skills`](https://github.com/anthropics/skills) publishes 19 skills. **15** of the 42 here match them (docx, pdf, pptx, xlsx, frontend-design, algorithmic-art, brand-guidelines, canvas-design, doc-coauthoring, internal-comms, mcp-builder, skill-creator, slack-gif-creator, theme-factory, web-artifacts-builder). The other **27** are only shipped inside the Claude app/container.

Missing from this archive (available in the public repo): `academy-guide`, `claude-api`, `discernment-nudge`, `webapp-testing`.

---

## Licensing & attribution

All skill content is © Anthropic, PBC. Each folder keeps its original `LICENSE.txt`:

| License | Count | Meaning |
|---|---|---|
| Apache-2.0 | 24 | Redistributable with attribution notice |
| Anthropic terms ("All rights reserved", source-available) | 10 | `docx`, `pdf`, `pdf-reading`, `pptx`, `xlsx`, `file-reading`, `artifact-emulator`, `built-in-browser`, `chrome-browser`, `computer-use` |
| No license file | 8 | Treated as all rights reserved |

Nothing here is relicensed by this repository. It is an archive for study and interoperability research. If you are Anthropic and want content removed, open an issue and it will be deleted promptly.

**Not affiliated with or endorsed by Anthropic.**
