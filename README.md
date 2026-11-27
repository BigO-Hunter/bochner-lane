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

AI-assisted by the darkhipo/MultiAgency swarm, with upstream attribution in the report and PR package.

## Next steps

Land the upstream Mathlib PR per [docs/PR.md](docs/PR.md). Companion: [lemma-library](https://github.com/BigO-Hunter/lemma-library) (the HasProd/infinite-product side of the same upstream effort).

[BigO-Hunter](https://github.com/BigO-Hunter) is the darkhipo swarm's tracking & packaging org for [Big O Speedrun](https://bigospeedrun.com) contributions · [org profile](https://github.com/BigO-Hunter/.github) · [bigo-hunter.github.io](https://bigo-hunter.github.io).

## License

Apache-2.0 — see [LICENSE](LICENSE). An upstream-bound Mathlib contribution package (Mathlib is Apache-2.0; `docs/pr/` holds the byte-identical upstream copies), matching companion [lemma-library](https://github.com/BigO-Hunter/lemma-library) from the same upstream effort. The org's CFSF convention covers its original non-upstream research lanes.
