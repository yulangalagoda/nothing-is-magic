# TODO

## Deferred fixes
- [x] Sweep em dashes from ch 1.1 (beats 1–5, both my text and drafts)
- [ ] Ch 1.4 (L1 vs L2): reconcile with ch 1.1 calling the L2 norm "the length"
      flatly — 1.4 must extend, not contradict. Add a one-line seam.
- [x] Ch 1.1 beat 6: bps conversion number — confirm 2.13 vs 2.1 rounding is
      deliberate and consistent.

## Decisions pending
- [x] Span figure (1.2 beat 3): resolved — no grid, wash + fine scatter.
- [ ] Ch 4.3 (linear regression): the "linear = lines stay lines" note in 1.2
      beat 5 defines linear geometrically (through origin). Affine / y=mx+c is
      deliberately deferred — 4.3 must introduce the shift, not contradict 1.2.
- [ ] Ch 1.3 (dot product): covers all three faces — projection, similarity,
      angle — since they're one formula. DEFER only advanced projection
      (onto subspaces, least-squares geometry) to Ch 4.3, where regression
      needs it. 1.3's projection stays at "shadow of one vector on another."
- [ ] Appendix (A1 or A2): prove v·w = ‖v‖‖w‖cosθ from the law of cosines.
      Promised in Ch 1.3 beat 3.
- [ ] Ch 1.3: decide whether projection length (v·w)/‖w‖ gets stated as an
      explicit formula (4th face) or stays implied. Currently implied.
- [ ] Ch 1.12 heading must carry {#sec-curse} — 1.1 cross-references it via
      @sec-curse. Until 1.12 exists the ref renders broken in preview
      (intentional reminder, do not "fix" by removing the ref).
- [ ] Ch 1.3 arccos block: when rendered, the nan cell emits a RuntimeWarning.
      Decision: show it (honest) rather than suppress. Confirm on first render.
- [ ] Ch 1.4 beat 5: sparsity explained via constraint-region ("leash")
      geometry, not penalty-gradient. Part 4 regularisation must reconcile the
      constraint view with the penalty-added-to-loss view (they're equivalent).
      Decide whether 1.4 needs a one-line aside noting the two views.
- [ ] Ch 1.7 (basis, rank): the word "basis" and the intuition (building blocks
      of the space) are introduced early in 1.5 beat 2. 1.7 must formalise
      (independence, what makes a valid basis) without re-introducing the word
      as if new.
- [ ] Ch 4.3 / affine: the "matrix fixes the origin, shifting isn't linear"
      point now appears in 1.2 (linear = through origin), 1.5 beat 2 (origin
      stays put), and 1.5 beat 6 (explicit: matrix can't move origin, promises
      "add something to the matrix"). 4.3 must deliver the bias/affine fix and
      resolve all three. The "add something" is the bias term.
- [ ] Part 4 (non-linearity / activation): the "bend between matrices" is now
      promised FOUR times — 1.2 b5 (stacking linear stays linear), 1.5 b5
      (matrices can't bend space), 1.6 b5 (composition collapses depth without
      it, stated as the precise mechanism). 1.6 b5 explicitly says "met three
      times as a promise, this is the collapse it exists to prevent." Part 4
      MUST deliver: (a) what the bend is, (b) that it breaks composability,
      (c) why that makes depth real. This is a headline payoff, not a footnote.
- [ ] Ch 1.11 (SVD): 1.6 beat 6 plants "you can't in general recover the two
      matrices from their product" (composition is one-way). SVD is the
      surprising exception — a canonical factorisation. Call back to this to
      make factorisation feel like the gift it is.
- [ ] Ch 1.9 (systems): "reach zero only trivially" (1.7 independence test) is
      the same question as "when does Ax=0 have non-trivial solutions." Weld
      these explicitly.
- [ ] Ch 1.9 / 4.3: "undoing a transformation needs independence" (1.7 beat 5)
      sets up matrix inversion (1.9) and regression solvability (4.3).
- [ ] Ch 1.11 (SVD): rank-as-true-reach (1.7) becomes visually obvious in SVD
      (how many stretch directions survive). Call back.
- [ ] "Dimension" formally defined in 1.7 beat 3 (size of any basis). Loose
      earlier use (1.1 "300 dimensions") is fine, not contradicted.
- [ ] Ch 1.7 beat 5: consider swapping Celsius/Fahrenheit for a security-domain
      redundant-feature example in author's voice.
- [ ] Ch 1.9 (systems): determinant-zero = "can't be undone" (1.8 beat 5) is
      the setup for matrix inversion and unique-solution conditions. Weld.
- [ ] Ch 1.11 (SVD): 1.8 beat 6 explicitly says determinant only gives the
      PRODUCT of stretches; singular values give per-direction stretch. SVD
      pays this off.
- [ ] Appendix: derive 2x2 determinant = parallelogram area from base×height.
      Promised 1.8 beat 3. (Now two appendix geometry proofs owed: this + law
      of cosines from 1.3.)
- [ ] Ch 4.3 (linear regression): least-squares is set up but not built in 1.9
      beat 5. Machinery assembled = reachable image (1.9) + closeness/L2 (1.4).
      4.3 must deliver the full construction and make it feel like the last
      piece clicking in. This is a major Part 1 → Part 4 payoff.
- [ ] "Singular" formally named 1.9 beat 4 = collapse = non-invertible = zero
      det = rank-deficient = dependent columns. Add to glossary if keeping one.
- [ ] Ch 1.9 beat 5 uses Celsius/Fahrenheit redundancy callback (from 1.7).
      If 1.7's example is swapped to a security-domain one, update here too for
      consistency.
- [ ] Ch 1.10 beat 4: rotation returns complex eigenvalues. Decide depth —
      keep as honest brief aside, or cut code block and keep prose-only point
      (rotations have no real survivor directions). Audience is near-zero-start;
      "complex numbers" may need a soft touch or a footnote.
- [ ] Render check: np.linalg.eig(R).eigenvalues (named attr) vs [0] indexing —
      confirm NumPy version. Same for .eigenvectors if used.
- [ ] Ch 1.11 (SVD): 1.10 beat 6 (third misunderstanding) explicitly sets up
      SVD as the "works for EVERY matrix" version — eigenvectors are picky
      (need square/symmetric, can be complex, don't rank importance in general).
      SVD MUST pay this off or the reader wonders why they need it. Load-bearing.
- [ ] Ch 1.10 beat 5: exploding/vanishing gradients = eigenvalues of repeated
      transformation. Dissertation-adjacent; forward-links to Part 2/4 training.
- [ ] Ch 1.11 is the Part 1 payoff chapter — edit LAST, read against all prior
      chapters to verify threads tightened. Threads landed: PCA (from 1.7),
      rank-as-nonzero-singular-values (1.7), collapse-as-zero-stretch
      (1.8/1.9/1.10), every-matrix decomposition (1.10's crack), factorisation
      exception (1.6 b6).
- [ ] Ch 1.11 beat 5: model compression paragraph is LoRA-adjacent. Decide
      whether to name LoRA/specific techniques (author's field) vs keep
      timeless. Currently unnamed for longevity.
- [ ] "Orthogonal" defined 1.11 beat 3. Add to glossary. Also "singular values."
- [ ] Judgement-over-mechanism motif now in 1.3 (cosine), 1.4 (norms), 1.11
      (truncation). Check tone consistency across all three in edit pass — this
      is a key throughline (knowing math vs doing ML).
- [x] @sec-curse cross-reference from 1.1 now resolves — 1.12 heading carries
      {#sec-curse}. Verify on render that 1.1's ref shows "Section 1.12" not broken.
- [ ] Ch 1.12 check 5 is written as the CLOSING STATEMENT of all of Part 1
      ("intuition has limited range, arithmetic outlives it"). Edit carefully —
      it's the part's last word. Make it land in author's voice.
- [ ] Ch 1.12 beat 4 is "Measure it yourself" not "Build it yourself" —
      sanctioned template flex (see STYLE.md). Confirm reads as intentional.

## Figure inventory (Part 1 run)
- [x] 01-07-independence.svg — built
- [x] 01-07-basis.svg — built
- [x] 01-08-area.svg — built
- [x] 01-08-collapse.svg — built
- [x] 01-09-three-fates.svg — built (3-panel, busiest so far; give room if cramped)
- [x] 01-10-eigen.svg — built
- [x] 01-11-rotate-stretch-rotate.svg — built. PRIORITY: canonical SVD picture,
      circle→ellipse. Give extra space at render; enlarge or two-row if cramped
      at chapter width.
- [x] 01-12-corners.svg — built