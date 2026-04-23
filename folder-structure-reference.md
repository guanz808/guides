# Folder Structure Reference

> **Core principle:** Context stays together. Active work lives where you work on it.
> Cross-project resources live at the top. Completed work moves to archive as a whole unit.

> **Separation principle:** `work/` and `personal/` are treated as fully separate entities. Every folder mirrors on both sides. No shared folders across the work/personal boundary.

> **Knowledge principle:** `knowledge/` is your source of truth — cheat sheets, how-tos, guides, research, templates, and references. Regardless of who authored it, if it informs your thinking or gets reused, it belongs here.

> **Notes principle:** `notes/` is for ephemeral thinking — fast capture, honest review, aggressive pruning. It is *not* part of your knowledge base.

> **Companion doc:** See `naming-convention-reference.md` for how to name the files *inside* this structure.

---

## Table of Contents

1. [Top-Level Structure](#1-top-level-structure)
2. [Knowledge Structure](#2-knowledge-structure)
3. [Notes Structure](#3-notes-structure)
4. [Project Internal Structure](#4-project-internal-structure)
5. [Top-Level vs Project-Level — The Rule](#5-top-level-vs-project-level--the-rule)
6. [In-Progress vs Done — The Promotion Model](#6-in-progress-vs-done--the-promotion-model)
7. [Folder Definitions](#7-folder-definitions)
8. [Naming Inside Knowledge Subfolders](#8-naming-inside-knowledge-subfolders)
9. [Decision Rules](#9-decision-rules)
10. [Review Rituals](#10-review-rituals)
11. [Worked Examples](#11-worked-examples)
12. [RAG Readiness Notes](#12-rag-readiness-notes)

---

## 1. Top-Level Structure

```
root/
├── work/
│   ├── inbox/                  ← work drop zone; sort weekly
│   ├── projects/
│   ├── knowledge/              ← source of truth, RAG-ready
│   ├── notes/                  ← ephemeral thinking, fast capture
│   ├── code/
│   ├── receipts/
│   ├── admin/
│   └── archive/
└── personal/                   ← fully mirrors work/
    ├── inbox/
    ├── projects/
    ├── knowledge/
    ├── notes/
    ├── code/
    ├── receipts/
    ├── admin/
    └── archive/
```

**Why full separation:**

- Clean sync, backup, and permission boundaries. Work data stays in work scope; personal data stays in personal scope. Nothing crosses.
- Identical substructure means muscle memory transfers — you file the same way on both sides.
- No cross-contamination risk: a work receipt can't accidentally land in personal sync/backup via a shared inbox.
- Privacy: work todos and personal todos have different audiences. Keeping them fully separate prevents accidental exposure.

**Handling ambiguous items (used by both):**

Don't split. Pick the side where the item *primarily* lives and file it there. A laptop that's 80% work goes in `work/receipts/`. Reference it from personal context if needed (a note or a link), but the file itself has one home. Splitting creates reconciliation problems.

---

## 2. Knowledge Structure

`knowledge/` is the most important folder in this system. It gets its own subfolder structure:

```
knowledge/
├── cheat-sheets/               ← quick-scan lookup (tables, commands, shortcuts)
├── how-tos/                    ← step-by-step procedures
├── guides/                     ← longer explanatory content, concepts + practice
├── research/                   ← your notes and findings on topics
├── templates/                  ← reusable starting points (docs, code, diagrams)
└── references/                 ← lookup material: PDFs, specs, manuals, any source
```

**The principle:** if it informs your thinking or gets reused across contexts, it belongs in `knowledge/`. Authorship doesn't matter — an external PDF spec and a how-to you wrote are both knowledge.

**Type definitions:**

| Subfolder | What it is | Read pattern | Example |
|---|---|---|---|
| `cheat-sheets/` | Quick-scan lookup. Tables, command lists, shortcuts. | Skim, don't read | `git.md`, `vim-shortcuts.md` |
| `how-tos/` | Step-by-step procedures. | Read and follow | `setup-new-mac.md`, `deploy-to-aws.md` |
| `guides/` | Longer explanatory content. Concepts + practice. | Read to learn | `understanding-docker-networking.md` |
| `research/` | Your notes, findings, and thinking on topics. | Reference your own analysis | `rag-architectures.md`, `tax-strategies-2026.md` |
| `templates/` | Reusable starting points. Fill in and use. | Copy and adapt | `meeting-notes.md`, `project-readme.md` |
| `references/` | Lookup material, any source. | Consult when needed | `aws-regions.md`, `brand-guidelines.pdf` |

**Subfolder growth strategy:**

- Start flat inside each subfolder. A bare list of files is fine up to ~20.
- Once a subfolder grows past 20-30 files, cluster by topic:
  ```
  knowledge/cheat-sheets/
  ├── git.md
  ├── vim-shortcuts.md
  ├── dev-tools/
  │   ├── docker.md
  │   └── kubernetes.md
  └── cloud/
      ├── aws.md
      └── gcp.md
  ```
- Don't create topic subfolders preemptively. Let them emerge from actual density.

---

## 3. Notes Structure

`notes/` is for ephemeral thinking — quick capture, todos, ideas, daily logs, meeting notes. The design prioritizes **speed of capture** over **perfect organization**.

Both `work/notes/` and `personal/notes/` follow identical structure:

```
notes/
├── todos.md                    ← two-zone: active + recent-done
├── ideas.md                    ← three-zone: live + parked + seeds
├── quick.md                    ← junk drawer, monthly rotation
├── daily/                      ← dated journal-style notes
│   ├── 2026-04-22.md
│   └── 2026-04-21.md
├── meetings/                   ← dated meeting notes (cross-project)
│   └── 2026-04-22_acme-standup.md
└── archive/                    ← pruned content lives here
    ├── todos-2026-q1.md
    ├── ideas-cold-2026.md
    └── quick-2026.md
```

### The capture rule

When writing something down fast, the mental decision tree should be this simple:

| Is it... | Goes to |
|---|---|
| An action I need to do | `todos.md` |
| A thought or idea to preserve | `ideas.md` |
| Today's log or journal entry | `daily/2026-04-22.md` |
| Meeting-specific (cross-project) | `meetings/` |
| Meeting-specific (project) | `projects/proj-x/docs/` |
| Anything else | `quick.md` |

If you hesitate for more than 2 seconds, write it in `quick.md` and move on. The worst filing decision is the one that slows you down enough to make you stop capturing.

**Which side's notes?** Decided by context at capture time — you're thinking work thoughts in work context, personal thoughts in personal context. If something is genuinely ambiguous, default to the side you're currently "in." Move it later if wrong.

### File patterns — keeping them lean as they grow

Each file has a different "noise" pattern, so each needs a different prune rule. **Length alone isn't the problem — signal-to-noise ratio is.** A 5000-line file of active ideas is fine. A 500-line file that's 90% dead todos is broken.

#### `todos.md` — two-zone pattern

```markdown
# Active
- [ ] Email the Acme team about the deployment
- [ ] Review Q2 budget draft
- [ ] Buy domain for personal site

# Done (recent)
- [x] 2026-04-22 — Set up new dev environment
- [x] 2026-04-21 — Call dentist
- [x] 2026-04-20 — Submit expense report

# Archive
<!-- Older completed todos moved to notes/archive/todos-2026-q1.md -->
```

**Prune rule:** when "Done (recent)" grows past ~30 items, cut everything older than 30 days into a quarterly archive file (`notes/archive/todos-2026-q1.md`). Main file stays lean.

**Note on scope:** `todos.md` is the escape valve for todos that don't fit your main todo app (Things, Todoist, Apple Reminders). It's not a replacement for a proper todo system — it's for when you need to jot something and your app isn't handy.

#### `ideas.md` — three-zone pattern

```markdown
# Live — actively thinking about
- RAG system for personal knowledge base
- Article on folder conventions

# Parked — interesting, not pursuing now
- Podcast idea: interviews with niche toolmakers
- That book idea about productivity systems

# Seeds — one-liners, undeveloped
- "what if calendars supported context, not time"
- side project: tool for X
```

**Prune rule:** review quarterly. Move ideas between zones based on what's actually in your head right now. When `ideas.md` crosses ~200 lines, cut the coldest seeds into `notes/archive/ideas-cold-2026.md`. Don't delete — cold ideas warm up sometimes.

**Critical rule:** an idea sitting in this file for 2 years isn't a failure. An idea sitting in this file when you haven't thought about it in 2 years is. Length is a proxy signal; the real signal is whether you still care.

#### `quick.md` — monthly rotation, aggressive prune

This is a genuine junk drawer — phone numbers, code snippets to try, quotes, things to look up. It accumulates noise fastest.

**Monthly rotation pattern:**

1. Scan last month's `quick.md`
2. Anything still relevant → promote to the right home (todo → `todos.md`, idea → `ideas.md`, knowledge → `knowledge/`, project material → the project)
3. Everything else → delete
4. Start fresh

This file is supposed to be disposable. Treating it as permanent defeats its purpose. If you can't bring yourself to delete, append to `notes/archive/quick-2026.md` as a single giant archive file — but honestly, most of what's in `quick.md` is already dead by the time you review it.

#### `daily/` — no pruning needed

Already date-segmented. Natural archive boundary is the year.

**Archive rule:** at year-end, move `notes/daily/*.md` from 2025 into `archive/2025/daily/`. Start fresh.

#### `meetings/` — same as daily

**Archive rule:** at year-end, move `notes/meetings/*.md` from 2025 into `archive/2025/meetings/`. Start fresh.

### The graduation path

This is what keeps `notes/` from becoming a swamp — stuff escapes upward when it matures:

- **Ideas that have legs** → promoted to `knowledge/research/` (to develop) or become new project folders (to act on)
- **Todos that recur** → might reveal a missing how-to in `knowledge/how-tos/`
- **Daily notes with lasting insight** → distill the insight into `knowledge/research/`, leave the daily note as-is
- **Meeting decisions** → if cross-project, promote to `knowledge/` or the relevant project

Daily and meeting notes themselves are never promoted whole — they're a log. You mine them for the 5% that matters.

### The ritual is the system

The structure above only works if the review ritual actually happens. See [Review Rituals](#10-review-rituals) for the full schedule.

A warning worth giving straight: it's possible to spend more time designing the notes system than actually thinking in it. The structure serves the work. If you find yourself optimizing the system instead of writing notes, the system has become the problem. Better a slightly messy file you actually use than a perfect file you're afraid to add to.

---

## 4. Project Internal Structure

Inside `projects/`, every project gets its own folder. Standard subfolders:

```
projects/proj-acme-website/
├── wip/                        ← in-progress, multi-file drafts
├── docs/                       ← notes, meeting notes, project how-tos
├── diagrams/                   ← wireframes, architecture, drawings
├── refs/                       ← project-specific reference material
├── code/                       ← project-specific scripts, docker, source
└── deliverables/               ← final outputs sent externally
```

**Rules:**

- Create only the subfolders you need. A small project might just have `wip/` and `docs/`.
- Never pad with empty folders (same principle as the naming convention: never pad with empty segments).
- Project folder names use the `proj-` prefix per the naming convention: `proj-acme-website`, `proj-kitchen-reno`.

---

## 5. Top-Level vs Project-Level — The Rule

Some folders appear both at the top level (`work/knowledge/`, `work/code/`) and inside projects (`projects/proj-acme/docs/`, `projects/proj-acme/code/`). The rule for which goes where:

| Goes in top-level `knowledge/` or `code/` | Goes inside a project |
|---|---|
| Cross-project, reusable across contexts | Only meaningful for one project |
| You'd want it without remembering the project | You access it while working on that project |
| Standalone resource | Part of project context |

**Examples:**

- A general Git cheat sheet → `work/knowledge/cheat-sheets/git.md`
- Acme-specific Git workflow notes → `projects/proj-acme-website/docs/git-workflow.md`
- A script to back up your whole system → `work/code/`
- A script that only runs the Acme deployment → `projects/proj-acme-website/code/`
- Brand guidelines PDF used across projects → `work/knowledge/references/brand-guidelines.pdf`
- Acme's specific style guide → `projects/proj-acme-website/refs/acme-style-guide.pdf`

**Test:** if the project were archived tomorrow, would this file still be useful standalone?
- Useful standalone → top level (`knowledge/` or `code/`)
- Dies with the project → inside the project

**Promoting from project to knowledge:** when you finish a project and realize something you made is reusable, *copy* (don't move) it into the appropriate `knowledge/` subfolder. Distill or generalize as you copy. The project keeps its specific version in its history; `knowledge/` gets the reusable lesson.

---

## 6. In-Progress vs Done — The Promotion Model

Two mechanisms for tracking work status. Use the right one for the right scale.

### Mechanism A — Per-project `wip/` (multi-file work)

Work in progress lives in `projects/proj-x/wip/`. When done, files are promoted *up one level* to the appropriate sibling folder (`docs/`, `diagrams/`, `deliverables/`).

```
wip/proposal-draft-v2.docx
    ↓ (finished)
deliverables/proj-acme-proposal-v2.docx
```

On promotion: drop the `-draft` / `-wip` suffix (per naming convention, `final` is not used — absence of `-draft` means it's current).

### Mechanism B — Name suffix (single standalone files)

For one-off items where a whole `wip/` folder is overkill, use the filename:

```
receipt-acme-2026-04-draft.pdf      ← still verifying details
receipt-acme-2026-04.pdf            ← verified, file is canonical
```

### Which to use

| Use `wip/` folder | Use name suffix |
|---|---|
| 3+ related files in flight | 1-2 files |
| Multi-day work | Same-day work |
| Part of a project | Standalone item |

### What NOT to do

- **No global `staging/` folder.** It becomes a junk drawer. Promotion never happens because it's a separate chore.
- **No `final` or `complete` suffix.** Absence of `-draft`/`-wip` = current. Matches the naming convention doc.

---

## 7. Folder Definitions

| Folder | Purpose | Naming inside |
|---|---|---|
| `inbox/` | Unsorted items. Clean out weekly. Separate per side (work/personal). | Keep original names |
| `projects/` | Active work. One folder per project. | `proj-{name}` |
| `knowledge/` | Source of truth: cheat sheets, how-tos, guides, research, templates, references | See section 8 |
| `notes/` | Ephemeral thinking: todos, ideas, quick notes, daily logs, meetings | See section 3 |
| `code/` | Cross-project scripts, docker files, snippets, dotfiles | kebab-case, scoped by purpose |
| `receipts/` | Financial records. Time-indexed. | `yyyy-mm-dd_{vendor}-{descriptor}` |
| `admin/` | Contracts, HR, insurance, non-project operational docs | Descriptive kebab-case |
| `archive/` | Completed projects and time-expired materials | `{year}/proj-{name}` |

### Folder subfolder patterns

**`receipts/`** — organize by year for scannability:
```
receipts/
├── 2025/
└── 2026/
    ├── 2026-04-22_acme-hosting-annual.pdf
    └── 2026-04-15_office-supplies.pdf
```

**`archive/`** — organize by year of completion:
```
archive/
├── 2024/
│   └── proj-old-website/
└── 2025/
    ├── proj-rebrand/
    ├── daily/                  ← from notes/daily/
    └── meetings/               ← from notes/meetings/
```

---

## 8. Naming Inside Knowledge Subfolders

Because the subfolder already communicates the type, **don't repeat the type in the filename**:

```
✓ knowledge/cheat-sheets/git.md
✗ knowledge/cheat-sheets/git-cheat-sheet.md

✓ knowledge/how-tos/setup-new-mac.md
✗ knowledge/how-tos/how-to-setup-new-mac.md

✓ knowledge/templates/meeting-notes.md
✗ knowledge/templates/tmpl-meeting-notes.md
```

The file's location communicates type; the filename communicates topic. Clean for humans, clean for RAG — no redundant signal.

**Exception:** if a file might escape its folder (copied, emailed, shared), keep the type in the name. A `git.md` on someone's desktop is ambiguous; `git-cheat-sheet.md` isn't. Judgment call.

**Index files at scale:** once any subfolder hits ~15 files, drop in a `_index.md` listing contents with one-line descriptions. The underscore sorts it first. Useful for humans and for RAG retrieval.

---

## 9. Decision Rules

### Where does a new file go?

1. Is it work or personal? → pick the root
2. Is it tied to a specific project? → `projects/proj-x/{subfolder}/`
3. Is it fast-capture / ephemeral? → `notes/{file}` (see section 3)
4. Is it a receipt or financial record? → `receipts/{year}/`
5. Is it admin (contract, HR, insurance)? → `admin/`
6. Is it reusable knowledge? → `knowledge/{type}/`
   - Quick lookup → `cheat-sheets/`
   - Step-by-step → `how-tos/`
   - Explanatory → `guides/`
   - My notes/findings → `research/`
   - Reusable starter → `templates/`
   - External reference → `references/`
7. Is it reusable code / scripts / docker? → `code/`
8. I genuinely don't know → `inbox/` (on the current side)

### Work vs personal — which side?

| Goes in work/ | Goes in personal/ |
|---|---|
| Earning income (employment, clients, business) | Personal life, home, family |
| Work-issued devices, accounts, obligations | Your own devices, accounts, projects |
| Professional relationships | Friends, family, personal relationships |
| Work receipts, contracts, admin | Personal receipts, taxes, household admin |

**Ambiguous items:** don't split. Pick the side where the item *primarily* lives. A laptop that's 80% work goes in `work/receipts/`. Reference from the other side if needed.

### Knowledge vs notes — which one?

| Knowledge | Notes |
|---|---|
| Curated, cleaned up | Raw, half-formed |
| Written once, referenced many times | Often written once, never reread |
| Deliberate | Reactive / in-the-moment |
| "How do I deploy to AWS" | "buy milk", "what if we tried X" |

When in doubt, start in `notes/`. Promote to `knowledge/` once it's been cleaned up and proven reusable.

### When does a project move to archive?

Project is done, no follow-up expected in the next 30 days. Move the **whole project folder** (internal structure intact) to `archive/{year}/`. Don't cherry-pick files out of it.

### When does project-specific knowledge get promoted to `knowledge/`?

When you realize you want it without remembering which project it came from. *Copy* (don't move) into the appropriate `knowledge/` subfolder, generalize as you copy. The project keeps its specific version; `knowledge/` gets the reusable lesson.

### Cheat sheet vs how-to vs guide — which type?

- Will I **scan** this? → `cheat-sheets/`
- Will I **follow steps**? → `how-tos/`
- Will I **read to understand**? → `guides/`

When genuinely unsure, pick `how-tos/` as the safest default. It's the most common type and easy to move later.

---

## 10. Review Rituals

The structure above only works if review actually happens. The files bloat regardless of how clean the rules are.

Run these on both sides (`work/` and `personal/`). Work reviews typically happen during work hours; personal reviews on personal time.

| Cadence | Time | Tasks |
|---|---|---|
| **Weekly** | 5 min per side | Clear `inbox/`. Skim `todos.md` — strike completed, move "Done (recent)" items >30 days to archive. |
| **Monthly** | 15 min per side | Rotate `quick.md` (promote the 10% that matters, delete the rest). Scan `daily/` for anything worth promoting to `knowledge/`. |
| **Quarterly** | 30 min per side | Review `ideas.md` — move ideas between Live/Parked/Seeds zones based on current reality. Archive cold seeds if file is long. |
| **Yearly** | 1 hour per side | Move `notes/daily/` and `notes/meetings/` into `archive/{year}/`. Review `archive/` and delete truly dead content. Assess whether the folder structure still fits how you work. |

**If you can only do one:** the weekly 5-minute inbox-and-todos review is the highest-leverage ritual. Skip the others before you skip this one.

**If a ritual starts feeling like busywork:** drop it. The system should serve the work, not the other way around.

---

## 11. Worked Examples

### Example 1 — Writing a blog article

```
personal/projects/proj-article-folder-systems/
├── wip/
│   └── draft-v1.md
├── refs/
│   └── cal-newport-deep-work.pdf        ← source cited, project-specific
└── deliverables/
    └── proj-article-folder-systems-v1.md
```

When the article ships, the whole `proj-article-folder-systems/` folder moves to `personal/archive/2026/`.

### Example 2 — Client project with diagrams and code

```
work/projects/proj-acme-website/
├── wip/
│   ├── homepage-draft-v3.fig
│   └── proposal-draft-v2.docx
├── docs/
│   ├── 2026-04-15_kickoff-meeting.md
│   └── project-readme.md
├── diagrams/
│   ├── site-architecture-v1.png
│   └── user-flow-v2.png
├── refs/
│   └── acme-brand-guidelines.pdf
├── code/
│   ├── deploy.sh
│   └── docker-compose.yml
└── deliverables/
    └── proj-acme-proposal-v2.docx
```

### Example 3 — Standalone receipt

```
work/receipts/2026/2026-04-22_acme-hosting-annual.pdf
```

### Example 4 — Cross-project knowledge items

```
work/knowledge/
├── cheat-sheets/
│   └── git.md                             ← reusable across all projects
├── how-tos/
│   └── deploy-to-aws.md                   ← general procedure
├── templates/
│   ├── project-readme.md                  ← starter for new projects
│   └── meeting-notes.md
└── references/
    ├── aws-region-codes.md                ← lookup table you curated
    └── http-status-codes.pdf              ← external reference
```

### Example 5 — Project knowledge vs cross-project knowledge

Acme-specific (stays in project):
```
work/projects/proj-acme-website/docs/
└── how-to-deploy-acme.md
```

Later, distilled into reusable version (copied to knowledge):
```
work/knowledge/how-tos/
└── deploy-to-aws.md                       ← generalized from Acme learnings
```

### Example 6 — Research you're building up

```
personal/knowledge/research/
├── rag-architectures.md
├── folder-systems-comparison.md
└── ai-notetaking-apps-2026.md
```

### Example 7 — Notes in action (both sides)

```
work/notes/
├── todos.md                               ← work todos (client followups, etc.)
├── ideas.md                               ← work ideas (new services, process)
├── quick.md
├── daily/
│   └── 2026-04-22.md                      ← end-of-workday brain dump
└── meetings/
    └── 2026-04-22_team-standup.md

personal/notes/
├── todos.md                               ← personal todos (errands, household)
├── ideas.md                               ← personal ideas (side projects, articles)
├── quick.md
└── daily/
    └── 2026-04-22.md                      ← personal journal
```

### Example 8 — An idea graduating into knowledge

Day 1 — captured in notes:
```
personal/notes/ideas.md
# Seeds
- RAG system for personal knowledge base
```

Month 2 — promoted within notes as thinking develops:
```
personal/notes/ideas.md
# Live — actively thinking about
- RAG system for personal knowledge base
```

Month 3 — research notes emerge, moved to knowledge:
```
personal/knowledge/research/
└── rag-architectures.md                   ← distilled thinking
```

Month 4 — committed to building it, becomes a project:
```
personal/projects/proj-personal-rag/
├── wip/
├── docs/
└── code/
```

---

## 12. RAG Readiness Notes

This structure is designed to work cleanly with retrieval-augmented generation (RAG) systems — Claude Projects, LlamaIndex, LangChain, custom embeddings, etc.

### Why it's RAG-friendly

- **Folder paths become automatic metadata.** Most RAG pipelines extract paths as tags/filters. A file at `knowledge/cheat-sheets/git.md` gets auto-tagged with `type: cheat-sheet, topic: git` without any extra work.
- **Separate indices per side.** Point one RAG at `work/knowledge/`, another at `personal/knowledge/`. No accidental cross-contamination of work and personal context.
- **Notes are intentionally excluded.** By keeping `notes/` separate from `knowledge/`, your RAG doesn't retrieve "buy milk" when you ask about deployment strategies. Raw, half-formed thinking stays out of the index.
- **Predictable structure.** The model can learn what each subfolder contains once and apply it consistently.

### Optional: frontmatter for richer metadata

When you're ready to add more signal without restructuring, use YAML frontmatter:

```markdown
---
type: cheat-sheet
topic: git
tags: [version-control, dev-tools]
updated: 2026-04-22
---
```

This is a future enhancement, not required. Folder structure alone gets you ~80% of the value.

### Keeping knowledge RAG-ready as it grows

- Prefer markdown (`.md`) over binary formats where possible — text is universally retrievable
- For PDFs in `references/`, most RAG pipelines handle them, but markdown transcripts retrieve better
- `_index.md` files in large subfolders act as great retrieval targets that point to other docs
- Date-stamp major updates in research files so the RAG can prefer recent analysis

---

*Last updated: 2026-04-22 — v1.3*
*Companion: naming-convention-reference.md*
*Changelog:*
*v1.1 — consolidated templates and references under knowledge/*
*v1.2 — added notes/ structure, pruning rules, review rituals*
*v1.3 — work and personal fully separated; each has own inbox and notes*
