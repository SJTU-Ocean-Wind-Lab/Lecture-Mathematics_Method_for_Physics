# Changelog

All notable changes to Lecture 13 — *Integral Transforms and Fourier
Analysis* — are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).

## [2026-11-19]

### Added

- Initial lecture notes: `lec13.tex`, `lec13.pdf` and `lec13.md`, covering
  integral transforms, Fourier series, the Fourier integral theorem, and the
  Fourier transform with five common transform pairs.
- Five schematic figures under `figs/`, each as a vector PDF and a 300 dpi PNG:
  the rectangular pulse and its sampling-function spectrum, the causal and
  anti-causal one-sided exponential decays, the two-sided exponential decay,
  the Gaussian pulse, and the sampling function with its ideal low-pass
  spectrum.
- Figure captions, labels and `\ref` cross-references in `lec13.tex`, and the
  corresponding figure links in `lec13.md`.
- `scripts/`: TikZ sources for the five figures and `build-figs.ps1`, which
  compiles each of them to `figs/` as both PDF and PNG.
- `README.md`, `CHANGELOG.md` and an allowlist `.gitignore` for this lecture.

### Fixed

- `lec13.tex`: corrected the dummy variable in the inner integral of the
  Fourier integral formula from `t` to `\tau`.
- `lec13.tex`: restored the absolute value in the two-sided exponential result
  `e^{-\beta|t|}`.
- `lec13.tex`: corrected the completed-square term in the Gaussian transform
  from `(t + i\omega/\beta)^2` to `(t + i\omega/(2\beta))^2`.
- `lec13.tex`: assigned the midpoint value `1/2` to the sampling-function
  spectrum at the jump points `|\omega| = \omega_0`.
