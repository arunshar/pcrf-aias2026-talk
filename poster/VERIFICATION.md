# Verification note: PC-RF poster for AIAS+ 2026

The poster is `pcrf_poster_aias2026.pdf`, A0 portrait (33.1 by 46.8 inches), built from `pcrf_poster.tex` with XeLaTeX on 2026-10-22. SHA-256 prefix of the PDF: `dec954a04c431184`. `preview.png` is a 2400 px render of the same file.

The AIAS+ rule for posters is A0 portrait, 33.1 by 46.8 inches, printed and brought to the conference by the presenter. An earlier version of this poster was 48 by 36 inches in landscape. It is replaced by this one.

## Build command

Run from this folder. The figures load from `figures/` and the university seal from `assets/`. In the Desktop delivery folder, run the commands from its `source_copy` folder.

```sh
mkdir -p build
xelatex -interaction=nonstopmode -halt-on-error -file-line-error -output-directory=build pcrf_poster.tex
xelatex -interaction=nonstopmode -halt-on-error -file-line-error -output-directory=build pcrf_poster.tex
cp build/pcrf_poster.pdf pcrf_poster_aias2026.pdf
```

The fonts are EB Garamond and Fira Mono.

## Checks

| Check | Result |
| --- | --- |
| Pages and size | 1 page, 2383.2 by 3369.6 pt (33.1 by 46.8 in), portrait |
| Text sizes | Body and captions 24.9 pt, tables 20.7 pt, section headings 29.9 pt, footer 18 pt |
| Fonts | 11 embedded, none of Type 3 |
| Overfull and underfull boxes | 0 and 0 |
| Poster numbers | Every number appears in the 28 September 2026 paper draft or in the numbers ledger of the project |
| Layout | The two columns end 0.38 and 0.18 in above the Resources heading, and the Resources band ends 0.62 in above the footer text |
| Review | Three independent reviews (layout, claim fidelity against the paper, stale references) ran on 2026-10-22, and every confirmed finding was applied or recorded |

## QR codes

Each symbol decodes to its URL from a render at 150 dpi. The six codes in the Resources band are 5.0 cm at error level Q on a white quiet zone, and the header code for arunshar.com is 5.2 cm. Each destination answered on 2026-10-22, except LinkedIn, which blocks automated requests. The LinkedIn URL was decoded from the QR image of the author's own profile.

| Label | URL |
| --- | --- |
| Repo | https://github.com/arunshar/pcrf-aias2026-talk |
| Slides | https://github.com/arunshar/pcrf-aias2026-talk/blob/main/slides/PCRF_AIAS2026_slides.pdf |
| Paper | https://github.com/arunshar/pcrf-aias2026-talk/blob/main/paper/PCRF_AIAS2026_paper.pdf |
| AIAS+ video | https://youtu.be/xyiUB-ehX8g |
| PyTorch video | https://youtu.be/k1FH2Pu953w |
| LinkedIn | https://www.linkedin.com/in/arun08sharma?fromQR=1 |
| Header | https://arunshar.com/ |

The paper link serves the anonymized 22 September 2026 build of the manuscript. The AIAS+ video link serves the narrated recording of this talk. The PyTorch video link serves the PyTorch Conference talk, "From PyTorch to Production", which follows the same model from training to serving.

## Known limits

1. Figure 1 is a shared diagram. It prints "NVR = 0 and MCE = 0 for any model", and the surrounding text adds that the values are zero up to float32 rounding and that the rescale needs one positive cell.
2. The Recommendation box asks for DE beside NVR and MCE as a diagnostic. On ERA5, DE measures a deformation term because of a latitude sign error, which Section 5 states.
