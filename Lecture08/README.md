# Lecture 8: Complex Series: Preliminaries

整理：杜润博（DRB）

Source notes: 25 October (10.25).

| Document | Markdown | LaTeX | PDF |
| --- | --- | --- | --- |
| Main lecture | [Read](lec08.md) | [Source](lec08.tex) | [PDF](lec08.pdf) |
| Exercises | [Read](lec08_exercises.md) | [Source](lec08_exercises.tex) | [PDF](lec08_exercises.pdf) |

The main notes follow the repository's `Templates/template.tex`. Worked
practice and homework are collected in the exercise supplement. Figure
sources and their PDF/PNG versions are in [`figs/`](figs/).

Compile from this directory with pdfLaTeX (twice) or Tectonic:

```sh
pdflatex -interaction=nonstopmode -halt-on-error lec08.tex
pdflatex -interaction=nonstopmode -halt-on-error lec08.tex
pdflatex -interaction=nonstopmode -halt-on-error lec08_exercises.tex
pdflatex -interaction=nonstopmode -halt-on-error lec08_exercises.tex
```

For a figure, compile its standalone `.tex` source in `figs/` before
rebuilding the lecture. Equations and figures are numbered separately
in each document.

License: [CC BY-NC-SA 4.0](../LICENSE), as in the parent repository.
