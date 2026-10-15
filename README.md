# HairNET: Controllable Hairstyle Generation with Diffusion Models

HairNET is a deep learning research project exploring realistic, customizable hairstyle generation and transfer using pretrained diffusion models. The project investigates how mask-guided inpainting, DreamBooth personalization, and Low-Rank Adaptation (LoRA) can be used to generate hairstyles while preserving facial identity and controlling hair attributes.

Developed as a team research project at the University of Wisconsin–Madison.

## Overview

HairNET explores three approaches to hairstyle synthesis:

- **Mask-Guided Inpainting:** Uses hair segmentation masks to modify specific image regions while preserving surrounding facial features.
- **DreamBooth Personalization:** Investigates subject-specific generation using a limited number of reference images.
- **LoRA Fine-Tuning:** Adapts pretrained Stable Diffusion models using image-mask pairs to improve control over hairstyle characteristics.

The project compares these techniques in terms of image quality, mask fidelity, personalization, and generalization, with particular attention to resource-constrained environments.

## Tech Stack

- **Language:** Python
- **Frameworks:** PyTorch, Hugging Face Diffusers
- **Models:** Stable Diffusion, DreamBooth, LoRA
- **Techniques:** Image Inpainting, Semantic Segmentation, Diffusion Model Fine-Tuning
- **Dataset:** CelebA-HQ
- **Evaluation:** Fréchet Inception Distance (FID)

## Methodology

1. **Data Preparation:** Use CelebA-HQ facial images and segmentation masks to identify hair regions and construct training inputs.
2. **Baseline Generation:** Establish a zero-shot Stable Diffusion inpainting baseline using hair masks.
3. **Personalization:** Experiment with DreamBooth to adapt generation to individual subjects.
4. **Fine-Tuning:** Train LoRA adapters on curated image-mask pairs to improve hairstyle control.
5. **Evaluation:** Investigate generation quality and model trade-offs using visual comparisons and FID-based evaluation.

## Results

Experiments highlighted several trade-offs between the approaches:

- **Mask-guided inpainting** provided a practical baseline for localized hairstyle editing.
- **DreamBooth** demonstrated personalization potential but suffered from overfitting and prompt sensitivity.
- **LoRA fine-tuning** showed stronger adherence to hair masks and improved control over attributes such as color, texture, and volume.
- **Limitations** included inconsistent image precision, restricted stylistic diversity, and computational constraints.

### LoRA Fine-Tuning Results

**Input Image and Hair Segmentation Mask**

| Original Image | Hair Mask |
|---|---|
| ![Original portrait](https://github.com/user-attachments/assets/e8abaf06-9910-4f4f-a3f8-89023cb75a72) | ![Hair segmentation mask](https://github.com/user-attachments/assets/425c6ba2-f0b8-44c2-9a27-526c460c7b5d) |

**Generated Output**

![LoRA fine-tuned hairstyle generation](https://github.com/user-attachments/assets/233f646a-e52e-4c21-9890-cd44eb57d598)

## Repository Structure

```text
HairNET/
├── diffusers/
│   ├── Training_Lora_Inpainting.ipynb
│   ├── sd_dreambooth_training.ipynb
│   ├── segmentation.ipynb
│   └── stable_hair.ipynb
├── evalutions/
│   └── calculating_fid_for_generative_models.ipynb
├── investigations/
│   ├── BaseLineModel.ipynb
│   └── images/
├── HairNet Final Report.pdf
└── README.md
```

## Research Report

For additional details on experimental methodology, model comparisons, findings, and limitations, see the [HairNET Final Report](./HairNet%20Final%20Report.pdf).

## Future Improvements

- Improve identity preservation and hairstyle consistency.
- Expand hairstyle diversity and attribute-level control.
- Evaluate generation quality across a larger test set.
- Optimize inference and fine-tuning for resource-constrained hardware.

## Acknowledgments

Developed by Damion Huppert, Praneet Popuri, Yana Gupta, and Zachary Gunderson at the University of Wisconsin–Madison.
