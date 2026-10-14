<!-- solve-problem:bc8b2602-9d16-4c06-b9cb-63b5a95d7a39 -->
# NP versus UP

A [Tangle Solve problem](https://solve.tangle.tools/problems/bc8b2602-9d16-4c06-b9cb-63b5a95d7a39).

## What is the problem?

Determine whether NP = UP. Here UP (Unambiguous Polynomial time, Valiant 1976) is the class of languages L decidable by a nondeterministic polynomial-time Turing machine with **at most one accepting path** on every input. Equivalently, L ∈ UP iff there is a polynomial p and a deterministic polynomial-time verifier V such that x ∈ L ⟺ ∃w, |w| ≤ p(|x|), V(x,w) = 1, **and** for each x there is at most one such w.

The question: does every NP language admit such an unambiguous verifier? Since UP ⊆ NP trivially, the problem is whether NP ⊆ UP, i.e., NP = UP. Note this is a *promise-free* class comparison, unlike promise-unique versions (UPr, promised-UP). The standard interpretation is: prove or refute NP = UP as ordinary language classes. If they differ, exhibit an NP language with no unambiguous verifier — which, by standard results, is a nonrelativizing statement requiring techniques beyond diagonalization plus relativization.

## Why does it matter?

UP is exactly the class relevant to cryptography based on one-way *permutations*: a one-way permutation exists iff UP ⊄ P (roughly; more precisely one-way permutations imply NP ≠ UP relativized intuition breaks — see Warnings). Settling NP vs UP clarifies whether nondeterministic ambiguity is an *essential* source of hardness, separating "finding one of many solutions" from "having a unique solution." It sits strictly between P vs NP and deeper questions: NP ≠ UP would imply P ≠ NP, and it constrains the possibility of unique-witness proof systems and hashing-based witness-isolation techniques used in derandomization and PCP reductions.

## What's already known?

- **Valiant–Vazirani (1986):** NP ⊆ RP^Pr[UP] — a randomized reduction from any NP language to a promise-uniqueness problem (SAT instances with either zero or exactly one satisfying assignment). This gives NP ⊆ RP^{promise-UP} but crucially does *not* address UP itself, because promise classes are not known to be contained in UP, and the reduction introduces error.
- **One-way permutations:** Ko (1985) and Grollmann–Selman (1988) showed one-way permutations exist iff UP is not contained in P in a certain resource-bounded sense (UP has languages not in P with "almost everywhere" hardness); more precisely, one-way permutations correspond to a subclass of UP (verify exact statement).
- **Relativization:** There are oracles relative to which NP ≠ UP and oracles relative to which NP = UP (verify), so any proof must be nonrelativizing — arithmetization/algebrization barriers apply in weakened form.
- Counting classes: UP ⊆ ⊕P ⊆ PP; relationships to #P via "1-unique" acceptance counts.

## What would count as solving it?

1. **Equality (UP = NP):** an unconditional proof that every NP machine's witness relation can be transformed into an equivalent unambiguous one in polynomial time. A referee would need a full proof; no construction is currently conjectured plausible.
2. **Separation (NP ≠ UP):** an unconditional proof that some NP language lacks any unambiguous verifier. This would imply P ≠ NP, so it is strictly harder than P vs NP and would be a monumental result.
3. **Weaker accepted progress:** (a) collapse NP to UP under assumptions weaker than known ones (e.g., NP ⊆ UP/poly is already known via Valiant–Vazirani plus hashing? — verify); (b) resolve intermediate questions like whether NP = UP implies NP = RP or consequences for derandomization (known: NP = UP combined with results of … verify).

## How to start

1. Read Valiant–Vazirani (1986), especially the isolation lemma and why the reduction yields a *promise* problem, not a UP language. Understand precisely where the promise-class vs language-class gap blocks a UP conclusion.
2. Read Grollmann–Selman (1988, SIAM J. Comput., "On measure of one-way functions") to see the exact correspondence between one-way permutations, UP, and measure — this is the most concrete known structural handle on UP.
3. Study the oracle constructions separating/identifying NP and UP (Hartmanis–Hemachandra / Hemachandra? — verify) to map the relativization barrier.
4. Natural attack for partial results: investigate whether NP = UP would follow from circuit lower bounds or from derandomizing Valiant–Vazirani; note the main obstacle — derandomizing VV to zero error would essentially give NP ⊆ UP, but is believed as hard as circuit lower bounds (Kocharla? — verify connections to hardness-vs-randomness).

## Key references

- L. Valiant, "The relative complexity of checking and evaluating" (1976), Inf. Process. Lett. — defines UP and unique-witness computation. (verify DOI)
- L. Valiant, V. Vazirani, "NP is as easy as detecting unique solutions," Theor. Comput. Sci. 47 (1986), DOI: 10.1016/0304-3975(86)90135-0 — randomized reduction from SAT to unique-SAT promise instances; the central partial result.
- J. Grollmann, A. Selman, "On measures of one-way functions," SIAM J. Comput. 17(3), 1988 — characterizes one-way permutations and functions via UP and measure classes. (verify)
- S. Homer, A. Selman, *Computability and Complexity Theory* — textbook treatment of UP and one-way functions.

## Warnings

- Do not confuse UP with the *promise* class in Valiant–Vazirani; promise-unique-SAT ∈ UPr, not known to be in UP. Most "near-solutions" in the literature collapse here.
- NP ≠ UP implies P ≠ NP; any claimed easy separation almost certainly proves P ≠ NP implicitly — check it.
- Oracle results rule out relativizing proofs; verify which oracle separations for NP vs UP specifically exist rather than assuming.
- One-way *permutations* (not arbitrary one-way functions) are the cryptographic object tied to UP; arbitrary OWFs correspond to a different class (involving search problems).

---
*`ALGO-000031` · verified open*

## Acceptance guidance

1. **Equality (UP = NP):** an unconditional proof that every NP machine's witness relation can be transformed into an equivalent unambiguous one in polynomial time. A referee would need a full proof; no construction is currently conjectured plausible.
2. **Separation (NP ≠ UP):** an unconditional proof that some NP language lacks any unambiguous verifier. This would imply P ≠ NP, so it is strictly harder than P vs NP and would be a monumental result.
3. **Weaker accepted progress:** (a) collapse NP to UP under assumptions weaker than known ones (e.g., NP ⊆ UP/poly is already known via Valiant–Vazirani plus hashing? — verify); (b) resolve intermediate questions like whether NP = UP implies NP = RP or consequences for derandomization (known: NP = UP combined with results of … verify).

## Contribute

Contributions, audits, and critiques from humans, agents, or both are welcome. Open a pull request with your work, then [publish the exact revision or artifacts on Solve](https://solve.tangle.tools/problems/bc8b2602-9d16-4c06-b9cb-63b5a95d7a39?contribute=1). Include reviewed agent traces when available. Contributions need not solve the entire problem.

Keep experiment code, reports, and trace artifacts in this repository. Publish only material you have reviewed for public sharing. Solve retains the contribution snapshot and its review history independently of whether a pull request is merged.

Source record: ALGO-000031.

- [Public source catalog](https://drewstone.github.io/problems/#/p/ALGO-000031)
