# Changelog

All notable changes to Lecture 02 — *Point Sets in the Complex Plane* — are
documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).

## [Unreleased]

### Added

- Seven schematic figures under `figs/`, each as a vector PDF and a 300 dpi PNG:
  interior, exterior and boundary points; boundary, interior, open and closed
  sets; connected versus disconnected sets; simply versus multiply connected
  domains; positive orientation of the boundary; the boundary of a domain with
  `n` holes; and the Riemann sphere with its stereographic projection.
- `scripts/`: TikZ sources for those figures and `build-figs.ps1`, which
  compiles each of them to `figs/` as both PDF and PNG.
- Two worked examples, reduced to systems of inequalities between moduli and
  then classified as domains: the lune between the two internally tangent
  circles `|z - 1| = 1` and `|z - 1/2| = 1/2`, and the angular locus
  `0 < arg((z - i)/(z + i)) < pi/4`.
- A remark defining the complement of a set, placed before the interior,
  exterior and boundary definitions, since the boundary condition is stated in
  terms of it.
- Section on the extended complex plane: neighbourhoods of infinity,
  stereographic projection and the Riemann sphere.
- Figure captions, labels and `\ref` cross-references in the text.
- `CHANGELOG.md` to track changes to this lecture.
- `lec02.pdf`, the compiled version of `lec02.tex` (9 pages), now kept under
  version control alongside the source, as `lec01.pdf` already is.
- A definition of **closed domain**, `D` together with `\partial D`, which was
  missing even though the course later works with closed regions.

### Changed

- `lec02.md`: rewritten from a 15-line stub (sections 4.1 and 4.2 only, with
  equations numbered `(39)` and `(40)` in continuation of Lecture 1) into full
  lecture notes covering everything up to, but not including, complex
  functions. It now carries the same figures and the same numbering as
  `lec02.tex`.
- `lec02.tex`: the eight topics are now top-level sections numbered `1`-`8`,
  with the two worked examples as `8.1` and `8.2`. Equations are numbered
  `(1)`-`(37)`. Each lecture numbers independently; there is no shared
  chapter-level numbering.
- `lec02.tex`: the duplicated title `Point Sets in the Complex Plane` was
  removed from the body, since it already appears as the document subtitle.
- `.gitignore`: `ref/`, `scripts/` and `tmp/` are now excluded, listed after
  the allowlist so that `!*/` can no longer re-include them.

### Removed

- `lec02.tex`: the copy of the Lecture 1 material (fundamentals, operations and
  geometric applications) that had been carried over from the initial commit.
  This lecture now covers only point sets.

### Fixed

- `lec02.tex`: the interior point of a set now correctly requires `z_0` to
  belong to `E`, and the exterior and boundary conditions are stated with
  explicit quantifiers over `delta`.
- `lec02.tex`: a set that is neither open nor closed was previously illustrated
  by a circle, which is in fact closed; the example is now `|z| < 1` together
  with the single point `1`.
- `lec02.tex`: the positive orientation of the boundary of an annulus is stated
  as `C_0 + C_1^-`, and the boundary of a domain with `n` holes as
  `C_0 + C_1^- + ... + C_n^-`.
- `lec02.tex`: the angular locus `0 < arg((z - i)/(z + i)) < pi/4` is given its
  correct boundary, the two rays of the imaginary axis outside `[-i, i]`
  together with the major arc of `|z + 1| = sqrt(2)` in the closed left
  half-plane, traversed in the direction that keeps the domain on the left.
- `lec02.tex`: several passages used a notion before defining it. The closure
  was described as "the smallest closed set" before closed sets had been
  introduced; "compact" was used although it is never defined in this lecture;
  and differentiation and integration were referred to in sections that precede
  them. Each passage now uses only the notions already available.
- `lec02.tex`: the curve in the definition of simple connectedness was labelled
  `C \subset D \text{ closed}`, where "closed" collided with the term for a
  closed set; it now reads "a closed curve".
- `fig01-interior-exterior-boundary`: the boundary point `z_3` was placed at a
  hand-tuned coordinate and could drift off the outline. Its position is now
  computed with the `intersections` library, so it lies exactly on `\partial E`.
- `fig05-positive-boundary`: orientation arrows are marked twice per curve, and
  the clockwise sense uses reversed arrow heads, so the inner hole no longer
  needs a re-parameterised arc and the direction of travel is legible at a
  glance.

## [2026-10-11]

### Added

- `lec02.tex`, carrying a copy of the Lecture 1 material together with an
  introduction to point sets (neighbourhoods, point classification, domains).
- `lec02.md` stub and `README.md`.
