# Writing Style Reference

> **Core principle:** Voice stays constant. Tone adapts to context. Every document — regardless of field or format — should feel like it came from the same author.

> **Audience principle:** Write for non-specialist readers who are familiar with the basics — an informed but non-technical audience with working knowledge but not domain expertise.

---

## Table of Contents

1. [Voice](#1-voice)
2. [Tone](#2-tone)
3. [Audience](#3-audience)
4. [Word choice](#4-word-choice)
5. [Headings and structure](#5-headings-and-structure)
6. [Lists](#6-lists)
7. [Tables](#7-tables)
8. [Conventions](#8-conventions)
9. [Text formatting](#9-text-formatting)
10. [Document types](#10-document-types)
11. [Quick reference checklist](#11-quick-reference-checklist)

---

## 1. Voice

Voice is who you are as a writer. It stays the same across every document, field, and format.

| Voice attribute | What it sounds like | What it doesn't sound like |
|---|---|---|
| Clear | Direct, specific, no filler | Vague, padded, over-qualified |
| Helpful | Anticipates questions, guides the reader | Assumes knowledge, skips steps |
| Human | Conversational, warm, real | Robotic, formal, stiff |
| Confident | States things directly | Hedges with "might," "could," "perhaps" |

**Rule:** Write like a knowledgeable colleague, not a manual. Inform without lecturing.

**Rule:** Be consistent. A reader encountering documents from the same source should feel the same authorial presence every time.

**Rule:** Use common contractions (it's, you'll, we're) — they keep writing human and readable.

---

## 2. Tone

Tone is how your voice sounds in a specific moment. It shifts based on the document type, the subject, and what the reader needs.

| Situation | Tone | Characteristics |
|---|---|---|
| Instructional (how-tos, procedures) | Direct, neutral | Step-by-step, no ambiguity, task-focused |
| Explanatory (guides, explainers) | Warm, patient | Context first, examples throughout, no assumptions |
| Reference (cheat sheets, tables) | Neutral, compact | Dense, scannable, minimal prose |
| Formal (reports, proposals) | Professional, measured | Structured, evidence-based, objective |
| Urgent (warnings, alerts) | Serious, concise | Lead with the issue, state the action, no filler |
| Conversational (emails, briefs) | Relaxed, direct | Short, natural, to the point |

**Rule:** Adjust tone to match what the reader needs — not what feels comfortable to write.

**Rule:** Tone changes; voice doesn't. A clear, human quality should be present even in the most formal document.

> **Test:** Read the document aloud. If it sounds like a legal contract or instruction manual, reduce the formality. If it sounds like a casual chat, add more structure.

---

## 3. Audience

The target reader is:

- a non-specialist who is familiar with the basics
- an informed but non-technical audience
- a reader with working knowledge but not domain expertise
- a broad audience with some background in the topic

**Rule:** Explain concepts in plain English before introducing technical terms.

**Rule:** Define every acronym and term on first use.

**Rule:** Prefer concrete examples over abstract descriptions. Show, don't just tell.

**Rule:** Avoid implementation-level details unless directly needed by the reader.

**Rule:** If something could go wrong, say so — and say what to do about it.

> **Test:** Would someone familiar with the topic but new to this context understand this? If not, simplify.

---

## 4. Word choice

**Rule:** Choose simple, precise words. When a simpler word exists, use it.

**Rule:** Use the same word for the same thing throughout — don't vary terms for style.

**Rule:** Avoid jargon, idioms, and modifier stacks — long chains of modifying words before a noun.

**Rule:** Define technical terms in context. Never attribute human characteristics to devices or products.

### Prefer → avoid

| Prefer | Avoid |
|---|---|
| `start` | `initialize`, `initiate` |
| `use` | `utilize`, `leverage` |
| `show` | `surface`, `expose` |
| `end` | `terminate`, `discontinue` |
| `get` | `obtain`, `retrieve` |
| `need` | `require`, `necessitate` |
| `help` | `facilitate`, `enable` |
| `change` | `modify`, `alter` |
| `check` | `verify`, `validate` |
| `set up` | `configure`, `instantiate` |

---

## 5. Headings and structure

**Rule:** Lead with what matters most. Put the key point at the top of every section.

**Rule:** Keep headings short. Sentence-style capitalization. No period at the end.

**Rule:** Use parallel structure at the same heading level — all noun phrases or all verb phrases.

**Rule:** Avoid two headings in a row without body text between them.

**Rule:** Include a table of contents with links in longer documents.

### Heading hierarchy

| Level | Purpose | Guidance |
|---|---|---|
| Top-level (`#`) | Document title | One per document |
| Second-level (`##`) | Major sections | As specific as possible |
| Third-level (`###`) | Sub-topics | Skip if fewer than two subtopics exist |

---

## 6. Lists

**Rule:** Use lists to present complex information in a scannable way. At least two items, no more than seven.

**Rule:** Make all items parallel in structure — all noun phrases or all verb phrases.

**Rule:** Introduce every list with a heading, sentence, or fragment ending in a colon.

### List types

**Bulleted lists** — for items with no required order.

**Numbered lists** — for sequential steps or prioritized items.

**Term lists** — for defining terms. Format the term in **bold**, follow with a period, then the definition starting with a capital letter.

### Example — numbered list

```markdown
To reset your password:

1. Open the sign-in page.        ← capital letter + period (complete sentence)
2. Select Forgot password.
3. Enter your email address.
4. Check your inbox for a reset link.
```

**Rule:** Begin each item with a capital letter. Use periods for complete sentences; skip them for short labels.

---

## 7. Tables

**Rule:** Use tables for structured data with two or more attributes. Use a list for similar items without attributes.

**Rule:** Every table needs a header row, two or more columns, and two or more data rows.

**Rule:** Place row-identifying information in the leftmost column. Never leave a cell blank — use "Not applicable" or "None."

**Rule:** Keep cell text brief and parallel. Use sentence-style capitalization throughout.

```
✓ | Environment | Purpose          |
✗ | Environment | Purpose...       |

✓ | Dev         | Local testing    |
✗ |             | Local testing    |   ← never leave a cell blank
```

---

## 8. Conventions

### Numbers

| Use spelled-out words for | Use numerals for |
|---|---|
| Zero through nine (general text) | 10 or greater |
| At the start of a sentence | Measurements, time, percentages, dimensions |
| Ordinals in text (first, second) | Ranges |

```
✓ Three failed attempts    ✗ 3 failed attempts
✓ 12 retries               ✗ Twelve retries
✓ 75%                      ✗ 75 percent
✓ 1,024 files              ✗ 1024 files
```

### Dates and times

**Rule:** Use Month Day, Year format. No ordinals.

```
✓ July 31, 2025      ✗ 31 July 2025      ✗ July 31st, 2025
```

**Rule:** Use AM and PM with a space before them. Use "noon" and "midnight" instead of 12:00 PM and 12:00 AM.

```
✓ 10:45 AM      ✗ 10:45am      ✗ 10:45 a.m.
```

### Acronyms and abbreviations

**Rule:** Spell out the term on first use; include the acronym in parentheses. Use the acronym after.

```
search engine optimization (SEO) → SEO from that point forward
```

**Rule:** Only use acronyms your audience already knows. Do not introduce an acronym used only once.

**Rule:** Form plurals like any noun (APIs, not API's).

---

## 9. Text formatting

| Element | Format |
|---|---|
| UI buttons, labels, menus, tab names | **Bold** |
| Key names and keyboard shortcuts | **Bold** |
| New terms being defined | *Italic* |
| Placeholders in syntax | *Italic* |
| Command-line commands and code | `Code style` |
| Error messages (in running text) | "Quotation marks" |
| File name extensions | Lowercase (`.docx`) |
| URLs | All lowercase |

> **Alignment:** Left alignment only. Never center text or justify both margins.

---

## 10. Document types

Voice stays the same across all of these. Structure and tone shift to fit the purpose.

### How-to / procedure

- Lead with the outcome: what the reader will be able to do.
- Use numbered steps with imperative verbs. One action per step.
- Include a prerequisites section if setup is required before starting.

### Guide / explainer

- Lead with context: why this matters before how it works.
- Build from simple to complex. Use examples and comparisons throughout.
- Aim for understanding, not just instruction.

### Reference / cheat sheet

- Dense and scannable. No prose introduction.
- Tables and lists only. Assume the reader knows what they're looking for.
- Alphabetical or logical order.

### Report / analysis

- Lead with the conclusion, not the methodology.
- Separate findings from recommendations.
- Use headings to signal structure. Keep any executive summary to one page.

### Proposal

- Lead with the problem, then the solution.
- Be specific about scope, timeline, and outcomes.
- Anticipate objections and address them directly.
- Avoid filler phrases ("As a leading provider of...").

### Email / brief communication

- Subject line = the point, in ten words or fewer.
- First sentence = what you need from the reader.
- One topic per message. End with a clear action or next step.

---

## 11. Quick reference checklist

- [ ] Voice is consistent — clear, helpful, human, confident
- [ ] Tone matches the document type and context
- [ ] Audience needs are addressed — no assumed expertise
- [ ] Sentence-style capitalization throughout (headings, lists, table headers)
- [ ] Short sentences; one idea per sentence
- [ ] Oxford comma used in all series
- [ ] No spaces around em dashes; en dashes for ranges
- [ ] Numbers zero–nine spelled out; 10+ as numerals
- [ ] Dates in "Month Day, Year" format; no ordinals
- [ ] Lists are parallel, introduced properly, and punctuated consistently
- [ ] Tables have header rows; no blank cells
- [ ] Acronyms spelled out on first use
- [ ] Bold for UI labels; italic for new terms and placeholders
- [ ] No jargon; plain language preferred
- [ ] People-first inclusive language

---

*Last updated: 2026-04-24 — v3.0*
*Approach: informed by the Mailchimp Content Style Guide*
