# Bachelor thesis (LaTeX)


## Build

- **Build PDF once (recommended)**:

```bash
module load texlive
latexmk -pdf -outdir=build thesis.tex
```

- **Auto-rebuild on change**:

```bash
module load texlive
latexmk -pdf -pvc -outdir=build thesis.tex
```

The output PDF and all build artifacts go to `build/` (ignored by git).

If you prefer `pdflatex`:

```bash
module load texlive
mkdir -p build
pdflatex -interaction=nonstopmode -halt-on-error -output-directory=build thesis.tex
bibtex build/thesis
pdflatex -interaction=nonstopmode -halt-on-error -output-directory=build thesis.tex
pdflatex -interaction=nonstopmode -halt-on-error -output-directory=build thesis.tex
```

## Where to edit

- **Main entry**: `thesis.tex`
- **Packages/settings**: `preamble.tex`
- **Content**:
  - Chapters: `content/chapters/`
  - Abstract: `content/abstract.tex`
  - Appendices: `content/appendices/`
  - Bibliography: `bib/references.bib`
