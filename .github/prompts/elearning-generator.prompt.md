---
name: elearning-generator
description: Generate a fully self-contained, interactive e-learning environment as a single HTML file with embedded CSS and JS.
argument-hint: Describe the topic, target audience, learning objectives, and any specific interaction types (quiz, flashcards, drag-and-drop, etc.).
agent: agent
---

You are an expert instructional designer and front-end developer.

## Parameters

- `{TOPIC}` — The subject matter of the lesson (e.g., "JavaScript async/await", "The Water Cycle", "European History 1900–1950")
- `{AUDIENCE}` — Who the learner is (e.g., "beginner developers", "middle school students", "corporate onboarding")
- `{OBJECTIVES}` — 2–5 learning outcomes, each starting with an action verb (e.g., "Explain...", "Identify...", "Apply...")
- `{INTERACTION_TYPES}` — One or more of: `quiz`, `flashcards`, `drag-and-drop`, `fill-in-the-blank`, `timeline`, `matching`, `scenario`
- `{ESTIMATED_DURATION}` — Target time-on-task (e.g., "10 minutes", "30 minutes")
- `{COLOR_SCHEME}` — Visual tone: `professional`, `playful`, `dark`, or a hex pair (`#1a1a2e / #e94560`)
- `{CONSTRAINTS}` — Any hard limits (e.g., "no external libraries", "WCAG AA accessible", "mobile-first", "must work offline")

---

## Task

Build a **single, self-contained HTML file** that delivers an interactive e-learning lesson on `{TOPIC}` for `{AUDIENCE}`.

---

## Step-by-step procedure

### 1 — Lesson architecture

Design a linear lesson flow with these sections:

1. **Cover screen** — Title, estimated duration badge, and a "Start" button
2. **Learning objective screen** — Bulleted list of `{OBJECTIVES}` with a "Continue" button
3. **Content slides** — 3–6 instructional slides; each slide has a heading, concise body text (≤ 80 words), and at least one visual aid (SVG illustration, animated diagram, or styled code block)
4. **Interaction modules** — Implement each type listed in `{INTERACTION_TYPES}` (details below)
5. **Results screen** — Score/summary, per-objective mastery indicators, and a "Retry" + "Download Certificate" button

### 2 — Interaction module specs

#### Quiz

- 3–5 multiple-choice questions mapped to `{OBJECTIVES}`
- Immediate feedback per answer (correct/incorrect + short explanation)
- Progress bar and question counter

#### Flashcards

- 6–8 cards; click/tap to flip between front (term) and back (definition)
- Shuffle button
- "I knew this" / "Review again" self-assessment to track confidence

#### Drag-and-drop

- Drag labelled items into correct drop zones
- Visual snap feedback; incorrect placements animate back to origin
- Check button after all items are placed

#### Fill-in-the-blank

- Inline text inputs inside a passage; check against an answer list (case-insensitive, trim whitespace)
- Highlight correct in green, incorrect in red

#### Timeline

- Horizontal scrollable timeline; events placed chronologically
- Click each event node to expand a detail card

#### Matching

- Two columns; click an item in column A then an item in column B to draw a connecting line (SVG line)
- "Check" button validates all pairs

#### Scenario

- A short decision-tree scenario (2–3 branching points); each choice advances or reverts progress
- Each path ends with a consequence screen before rejoining the main flow

### 3 — Visual design

- Apply `{COLOR_SCHEME}` consistently; use CSS custom properties (`--color-primary`, `--color-surface`, `--color-text`, etc.)
- Smooth slide transitions (CSS `transform`/`opacity`, ≤ 300 ms)
- Responsive layout (works at 320 px–1440 px viewport width)
- Use system font stack unless a Google Font @import is explicitly allowed by `{CONSTRAINTS}`

### 4 — Accessibility & quality

- All interactive elements must be keyboard-focusable and have ARIA labels
- Colour contrast ≥ 4.5 : 1 for normal text
- `<title>` and `<meta>` tags set appropriately
- No external network requests if `{CONSTRAINTS}` includes "offline" or "no external libraries"

### 5 — State management

- Track: current slide index, interaction scores, confidence ratings
- Persist state in `sessionStorage` so a browser refresh does not lose progress
- Expose a `resetLesson()` function callable from the "Retry" button

### 6 — Certificate download

- On the results screen, "Download Certificate" generates a styled certificate via the Canvas API and triggers a PNG download
- Certificate includes: learner name (prompted via a single input on the cover screen), topic, completion date, and a score badge

---

## Output contract

Return **exactly one fenced code block** of type `html` containing the complete file. No prose before or after the block except the self-check results.

The file must:

- Be human-readable with consistent 2-space indentation
- Contain `<style>` block in `<head>` (all CSS)
- Contain one `<script>` block before `</body>` (all JS)
- Contain no `TODO` comments or placeholder text — every section must be fully implemented

---

## Self-check (run before outputting)

- [ ] All `{INTERACTION_TYPES}` are implemented and functional
- [ ] Lesson flows from Cover → Objectives → Slides → Interactions → Results without dead ends
- [ ] CSS custom properties define the entire colour palette
- [ ] Every interactive element has a keyboard handler and ARIA label
- [ ] Certificate download is wired to the Canvas API and triggers a real file save
- [ ] No external URLs are referenced unless `{CONSTRAINTS}` permits them
- [ ] The HTML passes a mental W3C validation pass (no unclosed tags, no duplicate IDs)

Report each check as ✅ or ❌ with a one-line note, then output the code block.
