# Facial Image Inpainting, Restoration and Super-Resolution Using ComfyUI

## Overview

This repository contains ComfyUI workflows developed for experimental facial image inpainting, restoration and super-resolution.

The work was carried out within the research project **SIP25-102** at SecurityIALab, Universidad Autónoma de Nayarit (UAN), Mexico.

The project investigates computer vision and generative artificial intelligence methods for improving degraded facial photographs in contexts related to missing-person searches.

The workflows are intended for research and experimental evaluation. Generated facial details must not be interpreted as verified characteristics of the individuals depicted.

## Experimental Scope

The study evaluates six image-processing configurations:

| ID | Method | Description |
|---|---|---|
| B1 | Bicubic Interpolation | Conventional image upscaling baseline |
| B2 | 4xUltraSharp | Learning-based image super-resolution |
| B3 | 4xUltraSharp + CodeFormer | Super-resolution followed by facial restoration |
| P1a | Stable Diffusion | Diffusion-based super-resolution without FaceDetailer |
| P1b | Stable Diffusion + FaceDetailer | Diffusion-based super-resolution with facial refinement |
| P2 | Qwen-Image-Edit | Multimodal generative image editing |

Facial inpainting is performed before applying the evaluated super-resolution configurations.

## Repository Contents

The `workflows/` directory contains the following ComfyUI workflow definitions:

- `Inpainting SD.json`: facial inpainting and occlusion removal.
- `baselineBicubica.json`: bicubic interpolation baseline.
- `baseline4xUltraSharp.json`: 4xUltraSharp super-resolution baseline.
- `baselineCodeFormer.json`: 4xUltraSharp followed by CodeFormer restoration.
- `SDUpscaleFaceDetailer.json`: Stable Diffusion super-resolution with FaceDetailer.
- `upscaleqwen.json`: Qwen-Image-Edit-based image enhancement.

The Stable Diffusion experiments with and without FaceDetailer were performed using the same processing pipeline, with the FaceDetailer component enabled or disabled.

## Evaluation Methodology

The experimental evaluation considers three complementary dimensions:

**Facial embedding consistency:** ArcFace embeddings are compared using cosine similarity.

**No-reference image quality:** BRISQUE is used to estimate image naturalness based on statistical image characteristics.

**Operational evaluability:** The proportion of images for which facial embeddings can be successfully extracted is recorded.

The ArcFace reference images were obtained after the inpainting stage. They are experimental references, not independently verified high-resolution ground-truth images.

Consequently, cosine similarity scores indicate consistency relative to the processed reference and do not establish definitive identity preservation.

## Reproducibility

The workflows are provided as ComfyUI JSON files.

Reproduction requires compatible model weights, custom nodes, software dependencies and runtime configurations.

The archived workflow definitions should be interpreted alongside the documented experimental parameters. Historical configurations and subsequent corrections must be distinguished.

Additional software and model metadata may be supplied through accompanying reproducibility documentation.

## Data Availability and Ethical Considerations

The experimental work used degraded facial photographs originating from publicly available missing-person notices in Nayarit, Mexico.

Original facial photographs and generated facial reconstructions are not distributed through this repository.

Public availability of the source notices does not imply unrestricted authorisation for redistributing or repurposing personal or biometric data.

Generated images are intended for exploratory research and visual support. They must not be used as autonomous forensic identifications or conclusive evidence of an individual's appearance.

## Research Context

**Institution:** Universidad Autónoma de Nayarit, Mexico

**Laboratory:** SecurityIALab

**Research project:** SIP25-102

**Project coordinator:** Pablo Velarde Alvarado

**Workflow development and experimental evaluation:** Gustavo de Jesús Aparicio Rojas

## Citation

The associated scientific manuscript is being prepared for journal submission. Bibliographic information will be added when a citable publication becomes available.