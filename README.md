# Bochner lane

Lean 4 formalization of product-integral identities over an infinite product measure, past a finite prefix. The package proves the two valid monotone regimes and includes machine-checked counterexamples for the tempting but false unseparated form.

## Results

- **Every factor ≥ 1:** MeasureTheory.lintegral_iSup_finset_prod_eq exchanges the supremum of finite-prefix products with the lintegral.
- **Every factor ≤ 1:** MeasureTheory.lintegral_iInf_finset_prod_eq gives the corresponding infinite-product (ℝ≥0∞ infimum) identity.
- **Bochner integral:** finite-prefix product identities plus dominated and Vitali-style uniform-integrability forms for exchanging an infinite product and the integral.
- **Boundaries:** BochnerLane/Counterexample.lean proves why the independence-free, unseparated supremum, and undominated forms fail.

See [REPORT.md](REPORT.md) for the derivation, counterexamples and verification receipts. See [docs/PR.md](docs/PR.md) for the proposed upstream Mathlib package and exact source hashes; [docs/pr/](docs/pr/) contains the byte-identical upstream copies.

## Build

Pinned to Lean leanprover/lean4:v4.34.1 and Mathlib d13f23b723b8a846827a245b89c10fc7d3f11612.

~~~bash
lake exe cache get
lake build BochnerLane
~~~

The proof package is sorry-free and uses only the standard Mathlib axiom set (propext, Classical.choice, Quot.sound), as recorded in the report.

## Layout

- BochnerLane/Lintegral.lean — finite-prefix and monotone infinite-index lintegral identities.
- BochnerLane/Integral.lean — finite-prefix Bochner identity.
- BochnerLane/Infinite.lean — dominated and uniform-integrability infinite-index forms.
- BochnerLane/Counterexample.lean — machine-checked refutations of invalid strengthenings.
- BochnerLane/CheckAxioms.lean — axiom audit entry points.
- docs/pr/ — upstream-formatted copies of the compiled lane files.

AI-assisted by the darkhipo/MultiAgency swarm, with upstream attribution in the report and PR package. BigO-Hunter is a contributing and packaging org for [Big O Speedrun](https://github.com/bigospeedrun), not the project itself.

## Why this repo is up

Completed verified artifact + upstream Mathlib PR package: the two valid monotone product-integral regimes and dominated/Vitali Bochner exchange forms, with machine-checked counterexamples for the false strengthenings. Companion to [lemma-library](https://github.com/BigO-Hunter/lemma-library) (the HasProd/infinite-product side of the same upstream effort).

[BigO-Hunter](https://github.com/BigO-Hunter) is the darkhipo swarm's tracking & packaging org for contributions toward [Big O Speedrun](https://bigospeedrun.com) — a companion, never the project. Org story: [profile](https://github.com/BigO-Hunter/.github) · [bigo-hunter.github.io](https://bigo-hunter.github.io).

## What work can be done here

Land the upstream Mathlib PR per `docs/PR.md` (byte-identical upstream-formatted copies in `docs/pr/`). Reproduction: `lake exe cache get && lake build BochnerLane` at the campaign pins (v4.34.1 / d13f23b7); axiom audit via `BochnerLane/CheckAxioms.lean`.

## License

Licensed under the Copy-Free/Stays-Free (CFSF) License — see [LICENSE](LICENSE). CFSF: copy-free (use for any purpose) and stays-free (nobody may fence this work). The name is unclaimed in software licensing (checked 2026-11-09) and is deliberately not "Copyfree" — the Copyfree Initiative's certification mark — since CFSF's anti-enclosure condition is excluded by their standard.
