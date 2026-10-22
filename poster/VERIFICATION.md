# Verification note: PC-RF poster for AIAS+ 2026

The poster is `pcrf_poster_aias2026.pdf`, 48 by 36 inches, landscape, built from `pcrf_poster.tex` with XeLaTeX on 2026-10-22. SHA-256 prefix of the PDF: `0226812a02b8b957`. `preview.png` is a 2400 px render of the same file.

## Build command

Run from this folder. The figures load from `figures/` and the university seal from `assets/`.

```sh
mkdir -p build
xelatex -interaction=nonstopmode -halt-on-error -file-line-error -output-directory=build pcrf_poster.tex
xelatex -interaction=nonstopmode -halt-on-error -file-line-error -output-directory=build pcrf_poster.tex
cp build/pcrf_poster.pdf pcrf_poster_aias2026.pdf
```

The fonts are EB Garamond and Fira Mono, as in the earlier posters.

## Checks

| Check | Result |
| --- | --- |
| Pages and size | 1 page, 3456 by 2592 pt (48 by 36 in) |
| Fonts | 11 embedded, none of Type 3 |
| Overfull and underfull boxes | 0 and 0 |
| Poster numbers | Every number appears in the 28 September 2026 paper draft or in the numbers ledger of the project |
| Layout | The three columns end 1.15, 1.01 and 0.37 in above the footer line |

## QR codes

Each symbol decodes to its URL from a render at 120, 150 and 200 dpi. The codes are 4.2 cm at error level Q on a white quiet zone. Each destination answered on 2026-10-22.

| Label | URL |
| --- | --- |
| Repo | https://github.com/arunshar/pcrf-aias2026-talk |
| Slides | https://github.com/arunshar/pcrf-aias2026-talk/blob/main/slides/PCRF_AIAS2026_slides.pdf |
| Video | https://youtu.be/xyiUB-ehX8g |
| Paper | https://github.com/arunshar/pcrf-aias2026-talk/blob/main/paper/PCRF_AIAS2026_paper.pdf |
| Header | https://arunshar.com/ |

The paper link serves the anonymized 22 September 2026 build of the manuscript. The video link serves the narrated recording of the talk.
