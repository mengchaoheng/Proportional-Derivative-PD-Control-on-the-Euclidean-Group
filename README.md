# LaTeX Reconstruction of *Proportional Derivative (PD) Control on the Euclidean Group*

This repository provides an independent LaTeX reconstruction of the classic work by Francesco Bullo and Richard M. Murray on proportional-derivative control on the Euclidean group.

The reconstruction was created to improve readability, searchability, navigation, annotation, and reuse of mathematical formulas when studying the paper.

## Files

The repository contains several reconstructed versions:

- `Bullo_Murray_1995_PD_Control_full.tex`  
  Full reconstruction of the extended Caltech/CDS technical-report version.

- `Bullo_Murray_1995_PD_Control_simple.tex`  
  A reading-oriented version of the extended report with proofs omitted.

- `Bullo_Murray_1995_PD_Control_ECC95.tex`  
  Reconstruction of the shorter two-column ECC'95 conference version.

- `figures/`  
  Figure files prepared from the original paper and reused by the reconstructed LaTeX sources.

The LaTeX sources include internal hyperlinks for equations, figures, theorems, lemmas, sections, and references where appropriate.

## Compilation

The recommended compilation method is `latexmk`.

For the full version:

```bash
latexmk -pdf Bullo_Murray_1995_PD_Control_full.tex
```

For the simplified version:

```bash
latexmk -pdf Bullo_Murray_1995_PD_Control_simple.tex
```

For the ECC'95 version:

```bash
latexmk -pdf Bullo_Murray_1995_PD_Control_ECC95.tex
```

A standard `pdflatex` workflow also works:

```bash
pdflatex Bullo_Murray_1995_PD_Control_full.tex
pdflatex Bullo_Murray_1995_PD_Control_full.tex
```

Two passes resolve the table of contents and internal cross-references.

The bibliography is included directly in the LaTeX source through `thebibliography`, so the current reconstruction can be compiled without an external `.bib` file.

### VS Code / LaTeX Workshop

With LaTeX Workshop, the recommended recipe is:

```text
LaTeXmk
```

or equivalently:

```text
PDFLaTeX -> PDFLaTeX
```

## Citation

When using this repository for research or study, please cite the original work rather than this LaTeX reconstruction.

Two versions of the work are represented in this repository.

### Full technical-report version

F. Bullo and R. M. Murray,  
*Proportional Derivative (PD) Control on the Euclidean Group*,  
Technical Report Caltech/CDS 95-010,  
California Institute of Technology, 1995.

The 47-page source PDF used for the full reconstruction is dated August 11, 1995.

```bibtex
@techreport{BulloMurray1995PDTechReport,
  author      = {Francesco Bullo and Richard M. Murray},
  title       = {Proportional Derivative (PD) Control on the Euclidean Group},
  institution = {California Institute of Technology},
  type        = {Technical Report},
  number      = {Caltech/CDS 95-010},
  year        = {1995}
}
```

### ECC'95 conference version

F. Bullo and R. M. Murray,  
“Proportional derivative (PD) control on the Euclidean group,”  
in *European Control Conference*,  
Rome, Italy, pp. 1091–1097, 1995.

```bibtex
@inproceedings{BulloMurray1995PDECC,
  author    = {Francesco Bullo and Richard M. Murray},
  title     = {Proportional Derivative ({PD}) Control on the Euclidean Group},
  booktitle = {European Control Conference},
  address   = {Rome, Italy},
  pages     = {1091--1097},
  year      = {1995}
}
```

The ECC'95 paper is the shorter conference version, while the technical report contains the extended treatment.

## Reconstruction Notes

The LaTeX source was reconstructed from available PDF versions of the paper.

The reconstruction preserves the mathematical notation, terminology, section structure, equation numbering, and wording of the source as closely as practical, while allowing minor differences in typography and page layout.

A small number of clear typographical or mathematical issues identified during comparison of the available versions have been corrected in the reconstructed source. Such editorial changes are intended to improve mathematical consistency while keeping the reconstruction traceable to the original material.

## Disclaimer

This repository provides an independent LaTeX reconstruction of the original paper for scholarly reading, annotation, and study.

Copyright in the original text, figures, and underlying content remains with the original authors and/or respective rights holders. The reconstruction is shared for academic and educational purposes with full attribution to the original publication.

The authoritative source remains the original publication. Transcription, formatting, hyperlinking, and correction choices contained in this repository are the responsibility of the repository maintainer.

## Acknowledgment

All scientific content originates from the work of Francesco Bullo and Richard M. Murray. This repository contributes only the LaTeX reconstruction, formatting, cross-referencing, and related editorial work.
