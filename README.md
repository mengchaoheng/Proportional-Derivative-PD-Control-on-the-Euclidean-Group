# LaTeX Reconstruction of *Proportional Derivative (PD) Control on the Euclidean Group*

This repository provides an independent LaTeX reconstruction of the classic work by Francesco Bullo and Richard M. Murray on proportional-derivative control on the Euclidean group.

The reconstruction was created to improve readability, searchability, navigation, annotation, and reuse of mathematical formulas when studying the paper.

## Files

The repository contains several reconstructed versions:

- `Bullo_Murray_1995_PD_Control_full.tex`  
  Full reconstruction of the extended Caltech/CDS technical-report version.

- `Bullo_Murray_1995_PD_Control_simple.tex`  
  A reading-oriented version of the extended Caltech/CDS technical-report with proofs omitted.

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

## Mathematical and Notational Corrections

The reconstruction is intended to remain close to the printed sources. The following changes are intentional corrections to formulas, symbols, or mathematically significant terminology that were explicitly checked during reconstruction. Algebraically equivalent rewrites, ordinary typesetting differences, and hyperlink/cross-reference changes are not listed here.

### Extended technical-report version (47-page source)

The full reconstruction makes one confirmed mathematical correction to the printed 47-page source. The simplified reading version inherits the same correction.

1. **Appendix A: missing factor in the final block expression for \(\mathcal{B}_X\).**

   The printed source gives the diagonal block at the end of Appendix A in the form

   $$
   I_3+\frac{1}{2}\widehat{\psi}
   +(1-\alpha(\|\psi\|))\widehat{\psi}^{\,2}.
   $$

   The reconstruction uses

   $$
   I_3+\frac{1}{2}\widehat{\psi}
   +\frac{1-\alpha(\|\psi\|)}{\|\psi\|^2}\widehat{\psi}^{\,2}.
   $$

   The denominator follows directly from the preceding derivation. With \(y=\|\psi\|\),

   $$
   A-y^2B=\frac{1-\alpha(y)}{y^2}.
   $$

   It also agrees with Lemma 3 and with the identity

   $$
   A(\psi)^{-T}
   =
   I_3+\frac{1}{2}\widehat{\psi}
   +\frac{1-\alpha(\|\psi\|)}{\|\psi\|^2}\widehat{\psi}^{\,2}.
   $$

### ECC'95 conference version (7-page source)

The short conference version contains several formula or notation inconsistencies that are corrected using the internally consistent formulas of the extended report.

1. **Order of the cross product in the \(\mathrm{SO}(3)\) exponential-coordinate derivative.**

   Printed short version:

   $$
   \dot{x}
   =
   \omega_{\parallel}
   +\beta(\|x\|)\omega_{\perp}
   +\frac{1}{2}(\omega\times x).
   $$

   Reconstruction:

   $$
   \dot{x}
   =
   \omega_{\parallel}
   +\beta(\|x\|)\omega_{\perp}
   +\frac{1}{2}(x\times\omega).
   $$

   For body angular velocity, the Bernoulli/Jacobian expansion begins with
   \(\dot X=V^b+\frac12\operatorname{ad}_X(V^b)+\cdots\), and under
   \(\mathfrak{so}(3)\simeq\mathbb{R}^3\) this gives
   \(\operatorname{ad}_x(\omega)=x\times\omega\).

2. **Missing proportional gain in the satellite Lyapunov function.**

   Printed short version:

   $$
   W
   =
   \frac{1}{2}\|g\|_{\mathrm{SO}(3)}^2
   +\frac{1}{2}\langle\omega^b,J\omega^b\rangle
   +\epsilon\langle\log(g),J\omega^b\rangle.
   $$

   Reconstruction:

   $$
   W
   =
   \frac{k_p}{2}\|g\|_{\mathrm{SO}(3)}^2
   +\frac{1}{2}\langle\omega^b,J\omega^b\rangle
   +\epsilon\langle\log(g),J\omega^b\rangle.
   $$

   The factor \(k_p\) is required for consistency with the feedback term
   \(-k_p\log(g)\) and with the Lyapunov derivative calculation.

3. **Body/spatial velocity argument in the right-invariant double-geodesic law.**

   Printed short version:

   $$
   U(g,V^b)
   =
   -f(g,V^s)
   -
   \begin{bmatrix}
   K_\omega\log_{\mathrm{SO}(3)}(R)\\
   K_vp
   \end{bmatrix}
   -K_dV^s.
   $$

   Reconstruction:

   $$
   U(g,V^s)
   =
   -f(g,V^s)
   -
   \begin{bmatrix}
   K_\omega\log_{\mathrm{SO}(3)}(R)\\
   K_vp
   \end{bmatrix}
   -K_dV^s.
   $$

   The equation is explicitly for the right-invariant system
   \(\dot g=V^s g\), and every term on the right-hand side already uses the spatial velocity \(V^s\).

4. **Sign of the velocity error in trajectory tracking.**

   Printed short version:

   $$
   V_e=\operatorname{Ad}_{g^{-1}}V_d+V.
   $$

   Reconstruction:

   $$
   V_e=V-\operatorname{Ad}_{g^{-1}}V_d.
   $$

   Differentiating \(e=g_d^{-1}g\) with
   \(\dot g=gV\) and \(\dot g_d=V_dg_d\) gives

   $$
   \dot e
   =
   e\left(V-\operatorname{Ad}_{g^{-1}}V_d\right),
   $$

   which fixes the sign.

5. **Rotational block of the hybrid error.**

   Printed short version:

   $$
   e_{\mathrm{hybrid}}
   =
   \begin{bmatrix}
   RR_d^T & p-p_d\\
   0 & 1
   \end{bmatrix}.
   $$

   Reconstruction:

   $$
   e_{\mathrm{hybrid}}
   =
   \begin{bmatrix}
   R_d^TR & p-p_d\\
   0 & 1
   \end{bmatrix}.
   $$

   The corresponding transformed hybrid error is corrected consistently as well. The rotational part is intended to retain the natural error \(R_d^TR\); under a common left rotation \(R_0\),

   $$
   (R_0R_d)^T(R_0R)=R_d^TR,
   $$

   while the translational part transforms as \(R_0(p-p_d)\).

6. **Control-theoretic terminology in the \(\mathrm{SO}(3)\) second-order discussion.**

   The short version says “controllability problem” at the point where the objective is convergence to the identity equilibrium. The reconstruction uses “stabilization problem,” consistent with the theorem statements and the closed-loop objective.

These corrections are editorial decisions in the reconstruction. The original publications remain the authoritative historical sources, and the changes above are documented so that readers can distinguish the reconstructed formulas from the printed versions.

## Disclaimer

This repository provides an independent LaTeX reconstruction of the original paper for scholarly reading, annotation, and study.

Copyright in the original text, figures, and underlying content remains with the original authors and/or respective rights holders. The reconstruction is shared for academic and educational purposes with full attribution to the original publication.

The authoritative source remains the original publication. Transcription, formatting, hyperlinking, and correction choices contained in this repository are the responsibility of the repository maintainer.

## Acknowledgment

All scientific content originates from the work of Francesco Bullo and Richard M. Murray. This repository contributes only the LaTeX reconstruction, formatting, cross-referencing, and related editorial work.
