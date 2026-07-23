# Nothing Is Magic

*Machine learning mathematics.*

A free, open book on the mathematics behind machine learning, built around
intuition rather than memorisation. Every formula arrives only after the
picture that makes it feel inevitable, every major idea is implemented from
scratch in plain NumPy, and every concept is tied back to where it actually
lives in machine learning.

**Read it online: **

## Status

**Part 1 — Linear Algebra: complete.** Twelve chapters, from what a vector is
through to the singular value decomposition, ending with where geometric
intuition stops being reliable in high dimensions.

Parts 2 (calculus), 3 (probability and statistics), and 4 (the mathematics of
learning itself) are in progress. The book is written in the open and updated
continuously.

## Who it's for

Anyone who wants to understand *why* the mathematics of machine learning works,
not just how to apply it. School algebra and the memory of having once seen a
derivative is enough to begin. Readers who already know a section can skip
ahead from its opening.

## Structure

Every chapter follows the same seven beats: the itch (a problem you can feel),
the picture (geometric intuition, no formulas), the math built up from that
picture, code you run yourself, where the idea lives in machine learning, the
misunderstandings that catch people, and questions to check your intuition
against.

## Building it

The book is written in [Quarto](https://quarto.org).

```bash
python3 -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
quarto preview
```

Rendering the PDF additionally requires `librsvg2-bin` and a TeX distribution
(`quarto install tinytex`).

## Licence

The text and figures are licensed under
[CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/): free to share
and adapt with credit, and derivatives stay open.

The code examples are released under the MIT licence, so they can be reused
freely without restriction.

The online version will always be free.

## Contributing

Corrections, unclear explanations, and places where the intuition doesn't land
are all genuinely useful. Open an issue.
