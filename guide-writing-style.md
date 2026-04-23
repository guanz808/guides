# Document style guide

> Condensed from the Microsoft Writing Style Guide for AI document generation

This is the writing and formatting standard for all PKA library documents. It covers voice and tone, audience, capitalization, headings, sentence structure, word choice, punctuation, lists, tables, numbers, and inclusive language. The agent reads this before drafting every document to ensure consistency across the library.

---

## 0. Audience — write for non-technical readers

**Every document in this library must be written for readers who are not deeply technical.** Assume the reader understands the subject matter but may not know the technical tools, acronyms, or implementation details behind it.

**Rules:**
- Explain concepts in plain English before introducing technical terms.
- Define every acronym and technical term on first use — do not assume the reader knows it.
- Use analogies and real-world comparisons to explain abstract concepts.
- Break complex steps into smaller, numbered sub-steps rather than combining them.
- Prefer concrete examples over abstract descriptions. Show, don't just tell.
- Avoid implementation-level details unless they are directly needed by the reader.
- When a simpler word exists, use it. "Start" not "initialize." "Use" not "utilize." "Show" not "surface."
- If a step could go wrong in a common way, say so — and say what to do about it.
- Lead every section with a plain-English summary before going into detail.

**Test:** After drafting, ask — "Would someone who has never used this tool before understand this?" If not, simplify.

---

## 1. Voice and tone

- **Warm and relaxed** — conversational, grounded, occasionally fun
- **Crisp and clear** — write for scanning first, reading second; simple above all
- **Ready to help** — anticipate reader needs; offer the right info at the right time

**Core principles:**
- Get to the point fast. Lead with the key takeaway.
- Talk like a person. Use short, everyday words and contractions (it's, you'll, we're).
- Simpler is better. Short sentences and fragments are easier to scan.
- Prune every excess word. Omit unnecessary adverbs; use precise one-word verbs.

---

## 2. Capitalization

- Use **sentence-style capitalization** everywhere: capitalize only the first word and proper nouns.
- Never use title case (Like This) for headings, phrases, or UI labels.
- Never use ALL CAPS for emphasis.
- Never use all lowercase as a design choice.
- Capitalize proper nouns: unique people, places, product names, trademarks, book titles.
- Do not capitalize common technology terms (cloud computing, smartphone, open source).

**Examples:**
- Correct: `Find a Microsoft partner`
- Incorrect: `Find a Microsoft Partner`
- Correct: `Limited-time offer`
- Incorrect: `Limited-Time Offer`

---

## 3. Headings

- Keep headings **short**; put the most important idea first.
- Use sentence-style capitalization (no periods at the end).
- A question mark or exclamation point may be used if needed for meaning.
- Use headings to outline the document — make them specific and interesting.
- Use **parallel structure** for all headings at the same level (e.g., all noun phrases or all verb phrases).
- Avoid two headings in a row without body text between them.
- Don't use ampersands (&) or plus signs (+) in headings unless referencing UI.
- Avoid hyphens in headings when possible (can cause awkward line breaks on mobile).
- Use `vs.` (not `v.` or `versus`) in headings.

**Heading hierarchy:**
- Top-level: major subjects, as specific as possible
- Second-level: distinct subtopics only (skip if fewer than two subtopics exist)
- Lower levels: increasingly specific details

---

## 4. Sentences and paragraphs

- Write **short, simple sentences** using standard word order: subject → verb → object.
- Use **present tense** whenever possible (easier to read than past or future).
- Use **active voice** most of the time (subject performs the action).
- Use passive voice only to avoid blaming the reader or when the receiver of the action is the focus.
- Use **second person** (you/your) to address the reader directly.
- Avoid first-person plural (we/us) unless needed for clarity.
- Keep paragraphs **3–7 lines** long; single-line paragraphs are acceptable.
- Avoid chains of more than two prepositional phrases in a row.
- Start most statements with a **verb**; edit out "you can" and "there is/are/were."
- Include "that" and "who" for clarity (they help readers and translation tools).

---

## 5. Word choice

- Choose **simple, precise, conversational words**.
- Use common contractions (that's, don't, you'll) — they're friendly and readable.
- Avoid words with multiple meanings; if you mean the same thing, use the same word.
- Avoid jargon; use plain language whenever possible.
- Avoid idioms, colloquial expressions, and culture-specific references.
- Do not invent new words if one already exists.
- Define technical terms in context if the audience may not know them.
- Do not attribute human characteristics to devices or products.
- Avoid modifier stacks (long chains of modifying words before a noun).

---

## 6. Punctuation

- End every sentence with a period, even two-word sentences.
- Use **one space** after periods, question marks, exclamation marks, and colons.
- Use the **Oxford (serial) comma** in lists of three or more: Android, iOS, and Windows.
- Use a comma after introductory phrases and to join independent clauses with a conjunction.
- Use **em dashes** (—) with no spaces around them to set off phrases.
- Use **en dashes** (–) for ranges (pages, dates, times) with no spaces.
- Use **hyphens** for compound modifiers before nouns; avoid them in headings.
- Do not use a slash (/) as a substitute for "or."
- Use exclamation points sparingly. Use question marks sparingly.
- Place closing quotation marks outside commas and periods; inside other punctuation.
- Do not use apostrophes for possessives of "it" (use "its" not "it's" for possession).

**Headings and list items:** Skip end punctuation unless items are complete sentences.

---

## 7. Lists

- Use lists to present complex information in a scannable way.
- Lists should have **at least two items** and ideally no more than **seven items**.
- Each item should be short enough that a reader can see 2–3 items at a glance.
- Make all items in a list **parallel in structure** (e.g., all noun phrases or all verb phrases).
- Introduce every list with a heading, complete sentence, or fragment ending in a colon.

**Bulleted lists** — for items that share something in common but have no required order.

**Numbered lists** — for sequential steps or prioritized items.

**Term lists** — for defining a set of terms:
- Use a bulleted list.
- Format the term in **bold**, sentence case.
- Follow with a period, then the definition starting with a capital letter and ending with a period.

**Capitalization:** Begin each list item with a capital letter.

**Punctuation:**
- Use a period after items that are complete sentences or complete an introductory phrase.
- Skip periods if all items are three words or fewer, or are labels, headings, or strings.
- Do not use semicolons, commas, or conjunctions at the end of list items.

---

## 8. Tables

- Use tables for **structured data**: values, simple instructions, categories with examples, or items with two or more attributes.
- Do not use a table just to list similar items — use a list instead.
- Tables must have **two or more rows** (plus a header row) and **two or more columns**.
- Place the row-identifying information in the **leftmost column**.
- Make cell entries **parallel** (all noun phrases or all verb phrases within a column).
- Never leave a cell blank — use "Not applicable" or "None."
- Keep cell text brief, ideally one line. Limit the number of columns.
- Do not use a colon after introductory text — use a complete sentence ending in a period.
- Use **sentence-style capitalization** for table titles, column headers, and cell text.
- Do not use ellipses at the end of column headers.

**Header rows:**
- Make header text visually distinct (bold in Markdown: `| **Column** |`).
- Use specific column names (e.g., "Employee" not "Name").
- In long tables, keep the header row visible (repeat or freeze it).

---

## 9. Numbers

| Use spelled-out words for | Use numerals for |
|---|---|
| Zero through nine (general text) | 10 or greater |
| At the start of a sentence | Measurements (distance, weight, pixels, etc.) |
| Ordinals in text (first, second) | Time of day |
| | Percentages (use %, not "percent") |
| | Dimensions and ranges |

- Use commas in numbers with **4 or more digits** (e.g., 1,024).
- Do not use ordinal numbers for dates (write "June 5," not "June 5th").
- Always spell out the name of the month.
- Use a minus sign (not an en dash) for negative numbers.
- Hyphenate compound numbers when spelled out (twenty-one).
- Spell out fractions; hyphenate them (one-third, three-fourths).

---

## 10. Dates and times

- Date format: **Month Day, Year** — e.g., July 31, 2025 (not 31 July 2025).
- Do not use ordinal numbers in dates (not "July 31st").
- Capitalize days of the week and months; avoid abbreviations unless space is limited.
- Use **AM** and **PM** (with a space before them): 10:45 AM, 6:30 PM.
- Use numerals for times: 2:00, 4:15, 7:30. Always include AM or PM.
- Use "noon" and "midnight" instead of 12:00 PM/12:00 AM.
- Include the time zone when discussing events beyond a local audience.
- Use "to" in time ranges in text; use an en dash (–) in schedules or tables.
- Do not refer to seasons if months or calendar quarters will do.

---

## 11. Acronyms and abbreviations

- Spell out the term on first use; include the acronym in parentheses. Use the acronym after.
- Only use acronyms your audience is familiar with.
- Do not introduce an acronym used only once.
- Lowercase all words in the spelled-out form unless they are proper nouns.
- Form plurals like any noun (APIs, not API's).
- Use "a" or "an" based on how the acronym is pronounced (an ISP, a SQL database).
- Always spell out Microsoft product and feature names.

---

## 12. Text formatting

| Element | Format |
|---|---|
| UI buttons, labels, menus, tab names | **Bold** |
| Key names and keyboard shortcuts | **Bold** |
| New terms being defined | *Italic* |
| Placeholders in syntax | *Italic* |
| Mathematical variables | *Italic* |
| Command-line commands and code | `Code style` |
| Error messages (when referenced in text) | "Quotation marks" |
| File name extensions | Lowercase (`.docx`) |
| URLs | All lowercase |

- Use **left alignment** only. Never center text or justify both margins.
- Do not compress line spacing.
- Avoid widows, orphans, and lines ending in hyphens.

---

## 13. Structure and scannability

- **Lead with what matters most** — put key information at the top.
- Write short headings, short sentences, and short paragraphs.
- Use consistent formatting patterns so readers develop familiarity.
- Place important keywords **near the beginning** of headings and paragraphs.
- Include a table of contents with links in longer documents.
- Use parallel sentence structures when comparing things or writing list items.
- For procedures, always use numbered steps with imperative verbs and sentence-style capitalization.

---

## 14. Inclusive language

- Use **people-first language** by default: "person who is blind," "person with a disability."
- Never use language with offensive connotations.
- Do not use gendered pronouns (he/she) in generic references. Use "you," a role name, or "they."
- Use "they" as a singular non-binary pronoun when appropriate.
- Do not attribute gender to roles unless referring to a specific real person.

---

## Quick reference checklist

- [ ] Sentence-style capitalization throughout (headings, lists, table headers)
- [ ] Active voice, present tense
- [ ] Short sentences; one idea per sentence
- [ ] Oxford comma used in all series
- [ ] No spaces around em dashes; en dashes for ranges
- [ ] One space after all end punctuation
- [ ] Numbers zero–nine spelled out; 10+ as numerals
- [ ] Dates in "Month Day, Year" format; no ordinals
- [ ] Lists are parallel, introduced properly, and punctuated consistently
- [ ] Tables have header rows; no blank cells; sentence-style capitalization
- [ ] Acronyms spelled out on first use
- [ ] Bold used for UI labels; italic for new terms and placeholders
- [ ] No jargon; plain language preferred
- [ ] People-first inclusive language

---

## References

- [Microsoft Writing Style Guide](https://learn.microsoft.com/en-us/style-guide/welcome/)
