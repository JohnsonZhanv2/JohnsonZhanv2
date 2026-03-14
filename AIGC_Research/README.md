# 🔬 AIGC & Diffusion Model Research Lab

[![Student](https://img.shields.io/badge/Student-HKU-blue)](https://www.hku.hk/)
[![Python](https://img.shields.io/badge/Python-3.10+-yellow)](https://www.python.org/)
[![Framework](https://img.shields.io/badge/Framework-Stable%20Diffusion-orange)](https://github.com/AUTOMATIC1111/stable-diffusion-webui)

This repository serves as a technical log for my experiments with generative AI, specifically focusing on **Prompt Engineering** and **Latent Diffusion Models**. As an Electronic Engineering student at HKU, I approach image generation as a signal-to-noise optimization problem.

## 🛠️ Technical Implementation

### 1. Sampling & Convergence Optimization
In this lab, I prioritized the **DPM++ 2M SDE Karras** solver. 
- **Reasoning**: Unlike ancestral samplers (like Euler a), DPM++ 2M SDE offers superior convergence. By utilizing the Karras noise schedule, I achieved higher structural integrity and refined texture details in fewer steps (28-35 steps).
- **CFG Scale Tuning**: Balanced at 7.0 - 8.0 to maintain prompt adherence without introducing over-saturation or "burnt" artifacts.

### 2. High-Resolution Reconstruction (Hires. fix)
To overcome the limitations of the base 512px latent space:
- **Upscaler**: Employed **R-ESRGAN 4x+ Anime6B** for sharp edge detection and line-art preservation.
- **Denoising Logic**: Controlled at **0.45**, allowing the model to hallucinate micro-details (like skin texture and fabric folds) without altering the primary composition.

### 3. Precision Inpainting
Implemented regional regeneration for structural correction.
- **Workflow**: Utilizing masked latent noise to reconstruct cloth physics and anatomical accuracy.
- **Denoising Strength**: Specifically tuned to **0.55** for seamless edge blending between the original image and the generated patch.

---

## 🖼️ Showcase (Samples)

| Theme | Key Techniques | Preview |
| :--- | :--- | :--- |
| **Cyberpunk Aesthetic** | Cinematic Lighting, Rim Lighting, Neon Refraction | 
| **Material Physics** | Stretching Fabric, Detailed Embroidery, Depth of Field | 
| **Atmospheric Lighting** | God Rays, Tyndall Effect, Soft Focus | 
---

## 📂 Repository Structure
- `AIGC_Research/`: Core Jupyter Notebooks used for environment deployment on Google Colab (Tesla T4).
- `showcase/`: High-quality rendered outputs (PNG/JPG).
- `prompts/`: Structured prompt templates for reproducible AI art.

---

## 📫 Contact
**Johnson Zhan (战泓旭)**
- 🎓 **University**: The University of Hong Kong (HKU)
- 📧 **Email**: u3629190@connect.hku.hk
- 💻 **Major**: Electronic Engineering
