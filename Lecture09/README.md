# Lecture 9: Laurent Series and Singularities

整理：杜润博（DRB）

Source notes: 1 and 3 November (11.1 and 11.3, through singularities).

| Document | Markdown | LaTeX | PDF |
| --- | --- | --- | --- |
| Main lecture | [Read](lec09.md) | [Source](lec09.tex) | [PDF](lec09.pdf) |
| Exercises | [Read](lec09_exercises.md) | [Source](lec09_exercises.tex) | [PDF](lec09_exercises.pdf) |

The main notes follow the repository's `Templates/template.tex`. Worked
practice and homework are collected in the exercise supplement. Figure
sources and their PDF/PNG versions are in [`figs/`](figs/).

Compile from this directory with pdfLaTeX (twice) or Tectonic:

```sh
pdflatex -interaction=nonstopmode -halt-on-error lec09.tex
pdflatex -interaction=nonstopmode -halt-on-error lec09.tex
pdflatex -interaction=nonstopmode -halt-on-error lec09_exercises.tex
pdflatex -interaction=nonstopmode -halt-on-error lec09_exercises.tex
```

For a figure, compile its standalone `.tex` source in `figs/` before
rebuilding the lecture. Equations and figures are numbered separately
in each document.

License: [CC BY-NC-SA 4.0](../LICENSE), as in the parent repository.
