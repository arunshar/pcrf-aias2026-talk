# Physics-Constrained Rectified Flow for Climate Downscaling

Arun Sharma, University of Minnesota, Twin Cities

This repository holds the talk that Arun Sharma prepared for
[AIAS+ 2026](https://www.aiasplus.org/), the Chen Institute Symposium for AI Advancing Science and
Society, in San Francisco on 5 to 7 November 2026.

| Item | Link |
|---|---|
| Video (13:13) | The YouTube link will be added here after the upload. |
| Slides (22 pages, PDF) | [slides/PCRF_AIAS2026_slides.pdf](slides/PCRF_AIAS2026_slides.pdf) |
| Paper (13 pages, PDF) | [paper/PCRF_AIAS2026_paper.pdf](paper/PCRF_AIAS2026_paper.pdf) |

## The talk in brief

Generative downscalers can produce sharp precipitation fields that rain below zero. PC-RF is a
physics-constrained rectified-flow downscaler for precipitation and wind. It shapes the field in
training with three differentiable penalties, and it applies a projection after sampling. The
projection clamps rain at zero and then rescales the field once so that its domain mean matches
the coarse mean. After the projection, rain is non-negative and the mean matches for any model.

The talk asks which of the two steps carries the guarantee. At a matched three-year budget, the
model trained without penalties (RF-base) and PC-RF tie, so the guarantee belongs to the
projection.

## Main numbers

Every number below comes from one training seed per arm.

| Result | Value |
|---|---|
| CorrDiff (our reimplementation, scored without the projection), share of ensemble-mean rain cells below zero, ERA5 2020 | 45% (NVR 0.451) |
| Bicubic interpolation, NVR, ERA5 2020 | 0.101 |
| PC-RF and RF-base after the projection, NVR and MCE | 0 and 0, up to float32 rounding |
| Synthetic check with no trained network, NVR before and after | 0.236 to 0 |
| Three years (2019 to 2021), matched budget, SSIM of RF-base and PC-RF | 0.942 and 0.939 |

## Caveats the talk states

- The fine reference is ERA5-Land precipitation, which is interpolated from ERA5 forcing over a
  different accumulation window. The perceptual scores (SSIM, PSNR, CRPS) therefore measure
  agreement with an interpolant, and they cannot show downscaling skill.
- SRCNN, SRGAN, DDPM and CorrDiff are our reimplementations. We scored them without the
  projection, which any of them could apply.
- On ERA5, a latitude sign error makes the divergence penalty and the divergence error (DE) act
  on a deformation term, not on the divergence. The synthetic check uses grid coordinates and is
  not affected.
- NVR and MCE certify the serving step. They cannot rank two projected models.

## Chapters

| Time | Chapter |
|---|---|
| 0:00 | Physics-Constrained Rectified Flow for Climate Downscaling |
| 0:32 | The talk in one slide |
| 1:21 | Sharp fields can rain below zero |
| 2:06 | Two kinds of evidence |
| 2:44 | Guarantees go in the inference path |
| 3:13 | Data and setup |
| 4:08 | A 7.6M-parameter conditional U-Net |
| 4:41 | Three penalties shape the field in training |
| 5:19 | The projection, stage one: a synthetic raw field |
| 5:46 | The projection, stage two: clamp at zero |
| 6:02 | The projection, stage three: rescale the mean |
| 6:38 | Synthetic check: the mechanism works |
| 7:15 | ERA5 2020: only projected models are exactly valid |
| 7:59 | Matched one-year budget: tied on SSIM |
| 8:34 | Three years, matched budget: still a tie |
| 9:26 | What the checks certify |
| 10:14 | A protocol for scoring downscalers |
| 10:45 | Export the network, not the sampler |
| 11:36 | Limitations we raise ourselves |
| 12:13 | Next steps |
| 12:48 | Takeaways |

## About the files

- The slides are the talk deck as it will be presented, including three backup slides on metric
  definitions, training configuration and serving details.
- The paper is the revised manuscript prepared for the conference's second review round. It is
  anonymized for that review, so its author block reads "Anonymous".

Contact: arunshar@umn.edu
