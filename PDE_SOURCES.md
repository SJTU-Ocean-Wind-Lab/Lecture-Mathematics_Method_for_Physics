# PDE Source and Validation Notes

The PDE material is arranged as Lectures 18-20, following the overall task numbers in the supplied course allocation table. These are English teaching notes based on the supplied handwritten PDFs, with intermediate derivations and the final worked example completed where needed. They are not a page-by-page transcription.

## Source mapping

Page numbers below are one-based PDF page positions, not the textbook page numbers written in the notes.

| Lecture | Source pages | Included material |
| --- | --- | --- |
| 18 | `12.13.pdf`, pp. 7-13 | Three model PDEs; string-force balance; Fourier heat-flux law and energy balance |
| 18 | `12.15.pdf`, p. 4 bottom to p. 13 top | Initial data; three boundary types; characteristic coordinates; travelling waves; d'Alembert formula; whole-line wave examples |
| 18 | `12.20.pdf`, p. 1 | Hyperbolic, elliptic, and parabolic classification |
| 19 | `12.20.pdf`, pp. 2-11 | Fixed-end separation; eigenvalue cases; orthogonality; polynomial and finite-mode examples; free and mixed endpoints |
| 19 | `12.27.pdf`, pp. 1-6 | Continuation of mixed-end example; Neumann zero modes; insulated heat conduction; rectangular Laplace problem |
| 20 | `12.15.pdf`, pp. 13-17 | Fourier transform of the whole-line heat equation; Gaussian inversion; heat kernel and source convolution |
| 20 | `12.27.pdf`, pp. 7-12 | Boundary homogenization; forced modal equations; Laplace transform; time convolution; nonzero-boundary worked example |

The opening inverse-Laplace exercises in `12.13.pdf` and `12.15.pdf` belong to the preceding integral-transform unit and are not duplicated. Homework lists, timetable notes, and repeated material across the PDFs are omitted. The original source PDFs are kept separately and are not included in this repository package.

## Notation and mathematical corrections

- Wave speed is denoted by `a`. Heat diffusivity is denoted by `kappa`, corresponding to `a^2` in the handwritten heat-equation sections; the distinction prevents a diffusion coefficient from being interpreted as a wave speed.
- Heat-flux and Robin formulas use an explicit outward-normal convention. String spring conditions are written with the appropriate opposite signs at the left and right endpoints.
- For `xi=x+at` and `eta=x-at`, the correct transformed wave operator is `-4 a^2 U_{xi eta}`. The coefficient in one handwritten intermediate line is corrected.
- The two-fixed-end eigenproblem uses `X(0)=X(ell)=0`. A derivative at the right endpoint instead corresponds to a mixed fixed/free problem. Integer and half-integer spectra are kept separate.
- Every velocity projection includes the inverse modal frequency. The Neumann constant mode has norm squared `ell`, whereas the positive cosine modes have norm squared `ell/2`.
- Zero modes are written separately: linear in time for a free-end wave, constant in time for insulated heat flow, and linear in the remaining coordinate for the rectangular Laplace problem.
- The Fourier convention is fixed as forward kernel `exp(-i xi x)` and inverse factor `1/(2 pi)`. Spatial whole-line convolution and causal time convolution are defined separately.
- Subtracting a boundary lift changes both the source term and the initial data. Those changes are shown explicitly, including when the lift depends on time.
- The polynomial displacement example is written as `C x(ell-x)` to absorb the source's constant amplitude divisor into one coefficient, without changing the spatial profile.
- The general forced-wave integral is expanded from the extension referenced in `12.15.pdf`. The rectangular Laplace coefficients and the final forced-string example are carried through to explicit solutions.
- Formal eigenfunction and transform manipulations are accompanied by their smoothness, decay, or convergence requirements. They are not presented as unconditional pointwise identities for arbitrary data.

## File consistency and validation

Each lecture has matching Markdown, LaTeX, and PDF versions with the same equation order and numbering. The LaTeX uses the existing article template, instructor header, A4 page size, 11-point type, one-inch margins, and theorem-environment declarations. Existing Lecture01, Lecture02, and Templates files are unchanged.

Validation includes LaTeX compilation, inspection of all rendered PDF pages, comparison of displayed equations between Markdown and LaTeX, and symbolic substitution into the PDE and initial/boundary conditions for the worked examples. The heat-kernel normalization, modal forcing response, and polynomial Fourier coefficients are also checked.

All material remains under the repository's existing CC BY-NC-SA 4.0 license. The task-list numbers identify the supplied allocation and do not imply that Lectures 03-17 are present in the repository.
