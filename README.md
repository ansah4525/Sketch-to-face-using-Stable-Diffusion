

# 🎨 Sketch2Face: Forensic Face Synthesis from Sketches and Text Prompts

**Sketch2Face** is a multimodal generative AI framework that transforms rough forensic sketches and textual descriptions into realistic human face images using a fine-tuned [InstructPix2Pix](https://huggingface.co/docs/diffusers/api/pipelines/pix2pix) model. Designed for forensic applications, the system bridges the gap between coarse suspect sketches and photo-quality reconstructions to support law enforcement and investigative workflows.

---

## 🔍 Project Highlights

* **Model**: Fine-tuned InstructPix2Pix (based on Stable Diffusion) for sketch + text-to-face synthesis
* **Inputs**: Hand-drawn or synthetic sketches + descriptive text prompts
* **Outputs**: Realistic facial images aligned with input sketches and attributes
* **Dataset**: Subset of [Multi-Modal-CelebA-HQ](https://github.com/IIGROUP/MM-CelebA-HQ-Dataset), enhanced with custom high-quality sketches
* **Evaluation**: Quantitative (FID, SSIM, LPIPS, CLIP, PSNR) and qualitative (user survey, GPT-4 feedback)

---

## 📁 Repository Structure

```
├── best_generated_images/         # Final curated outputs
├── generated_images_baseline/     # Baseline model outputs
├── images_200/                    # Ground truth or original images
├── sketches_200/                  # Input sketches (synthetic or hand-drawn)
├── Code_Final.ipynb               # Final training script for fine-tuning
├── train_instruct_pix2pix.py      # Training script (Python version)
├── Generate200.ipynb              # Runs inference on all test sketches
├── Evaluation_Metrics.ipynb       # Computes FID, SSIM, PSNR, LPIPS, CLIP
├── CreatingDataset2.0.ipynb       # Converts raw data to training-ready format
├── test_prompts.csv               # Text prompts for sketch-image pairs
├── README.md                      # You're here!
```

---

## 🚀 Getting Started

### 1. Environment Setup

Install dependencies:

```bash
pip install -r requirements.txt
```

Recommended: Use a machine with an A100 GPU or similar.

### 2. Prepare Dataset

Ensure `images_200/`, `sketches_200/`, and `test_prompts.csv` are properly populated. To generate custom sketches:

```python
# See CreatingDataset2.0.ipynb
```

### 3. Fine-Tune Model

```bash
python train_instruct_pix2pix.py
```

Or use the `Code_Final.ipynb` notebook to interactively run the training process.

### 4. Generate Images

```bash
# Batch inference on 200 test cases
Run Generate200.ipynb
```

### 5. Evaluate Performance

```bash
# Compute FID, SSIM, LPIPS, PSNR, CLIP
Run Evaluation_Metrics.ipynb


## 👥 Authors

* Muhammad Hannan Akhtar
* Ansah Siddiqui
* Muhammed Noshin

---

## 📄 Citation

If you use this work in your research, please cite:

```bibtex
@article{sketch2face2024,
  title={Sketch2Face: Leveraging Text and Sketch Prompts for Suspect Identification},
  author={Akhtar, Muhammad Hannan and Siddiqui, Ansah and Noshin, Muhammed},
  year={2024},
  journal={Unpublished Manuscript}
}
