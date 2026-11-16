# Changelog

All notable changes to Lecture 01 — *Complex Numbers and the Complex Plane* —
are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).

## [Unreleased]

### Added

- Eight schematic figures under `figs/`, each as a vector PDF and a 300 dpi
  PNG: the complex plane and polar coordinates, the principal argument in the
  four quadrants, the parallelogram rule for addition and subtraction,
  multiplication by `-i`, the circle and the line as point loci, directed and
  interior angles, Thales's theorem, and the `n`-th roots of unity.
- `scripts/`: TikZ sources and `build-figs.ps1`, which compiles every figure to
  `figs/` as both PDF and PNG.
- Figure cross-references (`\ref`) in the text, plus captions and labels.

### Changed

- `lec01.tex`: inserted the eight figures and switched the numbering to the
  chapter scheme `1.1` / `1.1.1` / equations `(1.1.n)`, matching Chapter 1.2.
  The three former `\section`s are now subsections `1.1.1`-`1.1.3`; deeper
  headings became unnumbered bold lead-ins.
- `lec01.md`: same heading scheme, all eight figures embedded, and the
  placeholder screenshot replaced by the generated figure.
- `.gitignore`: `ref/`, `scripts/` and `tmp/` are now excluded, listed after the
  allowlist so that `!*/` can no longer re-include them.

### Removed

- `figs/tmp.jpg`: the handwritten placeholder photograph, 1.8 MB, superseded by
  the generated figures and no longer referenced anywhere.

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
