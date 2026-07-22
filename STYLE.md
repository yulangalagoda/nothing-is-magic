# STYLE.md — design and voice decisions for *Nothing Is Magic*

The single source of truth for how the book looks and sounds. When a choice
recurs, it gets written here so it's decided once, not re-argued per chapter.

---

## Colour palette

From yulan.me, carried into the book.

| Role                | Hex       | Used for                                    |
|---------------------|-----------|---------------------------------------------|
| Ink (near-black)    | `#141414` | Body figure content: primary arrows, labels |
| Pine green          | `#1B5E43` | The one element a figure is *about* (accent) |
| Cream               | `#FBFAF7` | Page background (site/theme)                 |

Figure-specific greys:

| Role              | Hex       | Used for                                     |
|-------------------|-----------|----------------------------------------------|
| Grid              | `#dcdcdc` | Background grid on all figures               |
| Axes              | `#b0b0b0` | Coordinate axes (measured figures only)      |
| Structural / drop | `#8a8a8a` | Dashed drop-lines, secondary construction    |
| Muted arrow       | `#9a9a9a` | "Second-leg" or de-emphasised arrows         |
| Value labels      | `#4a4a4a` | Numbers on axes (128, 7, etc.)               |

Rule of thumb: grid at the back, structure in grey, the actual subject in ink,
and the one thing the figure is *about* in pine. The subject should always be
the darkest or most saturated thing on the page.

---

## Figures

### Three figure types

**Measured figures** — real axes, labelled with named quantities and values
(e.g. the 1.1 tempo/loudness arrow). These keep their axes, drawn in `#b0b0b0`.
Use when the figure's point depends on specific coordinates.

**Schematic figures** — direction and relationship only, no coordinate values
(e.g. 1.2 addition, scaling). No drawn axes. Use when specific numbers would be
noise.

**Region figures** — showing a set or area that a construction fills (e.g. the
1.2 span wash). No grid: a background grid implies discrete integer points and
fights the "continuous region" being depicted. Use a soft radial wash plus a
fine scatter for the filled area, subject vectors in ink on top.

All types use the `#dcdcdc` background grid.

### Format and construction

- Format: hand-authored **SVG** while figures are illustrative (non-technical).
  Move to **matplotlib in `{python}` blocks** once a figure shows a *computed
  result* — the reader must see the code produce it. (Decided ch 1.1 beat 4.)
- Files live in `images/`, named `CH-SEC-slug.svg` (e.g. `01-02-addition.svg`).
- Referenced from chapters with a relative path: `../images/...`.
- Font: `Georgia, serif` in-figure, to sit near the book's Playfair/serif feel.
- Arrowheads: filled triangle marker, colour-matched to its line.
- Grid: `<pattern>` at 30px, `stroke-width="1"`. Print eats light greys, so
  `#dcdcdc` is the floor; don't go lighter without checking a PDF render.

### Referencing in prose

- Every figure gets a `{#fig-slug}` label; refer to it in text as `@fig-slug`
  so numbering is automatic.
- Captions are full sentences describing what the figure *shows*, not just what
  it *is*.

---

## Voice

The register is "book," not "blog." Decided across ch 1.1 revisions.

Avoid (these read as AI-generated or as trying too hard):
- Frequent rhetorical questions
- Exclamations played for excitement ("That's it!", "Guess what!")
- Repeated callbacks to the same running example at every turn
- "This lives in section X" / "we'll meet this later" signposting used as filler

Keep:
- Fragments for emphasis, sparingly.
- One clear statement where a rhetorical question was tempting.
- Idiosyncratic asides — a specific observation only this author would make —
  as the main defence against sterile prose. (Preferred over deliberately
  roughening grammar, which just makes the book worse.)

Punctuation:
- **No em dashes.** Use full stops, colons, or parentheses instead.
  (Sweep still pending on ch 1.1 — see TODO.)

Register:
- First-person plural ("we"), consistently, within a chapter.
- Refer to chapters relatively ("the last chapter," "two chapters ago," "the
  first chapter"), never by absolute number. More conversational, and survives
  reordering.
- The "arithmetic goes where the picture can't" refrain is a deliberate motif,
  but vary its emphasis each time (1.1: length survives; 1.2: code survives;
  1.3: all three faces survive together). Don't photocopy the phrasing.

---

## The seven-beat chapter template

Every chapter, in order:

1. The itch — a concrete problem, felt, before any math.
2. The picture — geometric intuition in words + diagram, no formulas.
3. The math, built up — derive the formula from the picture.
4. Build it yourself — from-scratch NumPy the reader runs.
5. Where it lives in ML — the concrete payoff.
6. Common misunderstandings — the traps.
7. Check your intuition — questions with collapsible answers.

Beat headings carry `{.unnumbered}`.

- Forward references: prefer a self-standing statement of what's true now over
  an IOU ("we'll come back to this"). Keep the promise only when it genuinely
  defers *machinery* the reader can't yet have (e.g. gradient clipping needs
  training context). Cut promises that only defer a concept — state the concept
  plainly instead, and let the fuller treatment arrive unannounced.

  - Norm notation: bare ‖v‖ means the L2 norm (the default). Use a subscript
  (‖v‖₁, ‖v‖₂) only when disambiguating. Chapters 1.1–1.3 wrote all norms bare
  and all meant L2, so this is consistent retroactively — do not go back and
  subscript them.

- Matrix operations: always lead with the column / linear-combination view
  (Av = scale each column by the matching entry, add), which keeps the
  "matrix moves space" geometry alive. The row-by-row dot-product rule is
  introduced second, framed as the tool for computing by hand, never as the
  meaning.
- Matrix product order: AB means "apply B first, then A" (ABv = A(Bv),
  rightmost acts first). Standard convention, but counterintuitive — always
  state "B first" explicitly in prose when a product appears, never rely on
  the reader inferring order from left-to-right reading.

- The seven-beat template flexes when a chapter's nature demands it. 1.12
  (high dimensions) has no tool to build, so beat 4 becomes "Measure it
  yourself" — run code that demonstrates the phenomena rather than implementing
  a formula. Flex the template to serve the chapter; don't force a hollow beat
  to satisfy the shape.