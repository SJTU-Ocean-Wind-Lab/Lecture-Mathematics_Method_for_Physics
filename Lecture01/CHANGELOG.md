# Changelog

All notable changes to Lecture 01 — *Complex Numbers and the Complex Plane* —
are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).

## [Unreleased]

### Added

- Nine schematic figures under `figs/`, each as a vector PDF and a 300 dpi PNG:
  the complex plane and its three equivalent descriptions, the modulus and
  argument, the principal argument in the four quadrants, the parallelogram
  rule for addition and subtraction, multiplication by `-i`, the `n`-th roots
  of unity, the circle and the line as point loci, directed and interior
  angles, and Thales's theorem.
- `scripts/`: TikZ sources and `build-figs.ps1`, which compiles every figure to
  `figs/` as both PDF and PNG.
- Figure cross-references (`\ref`) in the text, plus captions and labels.

### Changed

- `lec01.tex`: the three former top-level sections are now numbered `1`-`3`,
  with their subtopics as `1.1`, `1.1.1`, ... Deeper headings that had been
  flattened into bold lead-ins are standard `\subsection` and `\subsubsection`
  commands again; the custom `\leadin` macro was removed.
- `lec01.tex`: the polar section was reordered to `modulus`, `argument`,
  `polar form`, `exponential form`, so that no quantity is used before it is
  defined.
- `lec01.md`: same heading scheme, all nine figures embedded, and the
  placeholder screenshot replaced by the generated figure.
- `.gitignore`: `ref/`, `scripts/` and `tmp/` are now excluded, listed after the
  allowlist so that `!*/` can no longer re-include them.

### Removed

- `figs/tmp.jpg`: the handwritten placeholder photograph, 1.8 MB, superseded by
  the generated figures and no longer referenced anywhere.

### Fixed

- `fig01-complex-plane-polar`: the legend used the modulus and the argument,
  neither of which had been defined at that point in the text. Those two
  quantities were moved into a separate figure placed after their definitions.
- `lec01.tex`: the proof of Thales's theorem cited the theorem itself; the
  passage now states that the converse direction is part of the theorem.
- `lec01.tex`: the section openings announced concepts from later sections
  ("multiplication and powers", "Euler's formula") before they occur.

## [2026-10-14]

### Added

- `figs/tmp.jpg`: placeholder figure, reserved for future schematics.
- `CHANGELOG.md` to track changes to this lecture.

### Fixed

- `.gitignore`: the allowlist now re-includes the `figs/` directory and all of
  its nested files (`!figs/`, `!figs/**`), so figures are no longer excluded
  from version control.
- `README.md`: note formatting and added mention of the placeholder figure.

## [2026-10-11]

### Added

- Initial lecture notes: `lec01.tex`, `lec01.pdf`, and `lec01.md`.
- `README.md` and `.gitignore` for this lecture.
