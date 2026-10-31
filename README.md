# Practical 5: Image Generation with Stable Diffusion

A Jupyter notebook practical that uses a pretrained Stable Diffusion model to generate images from text prompts and compare generation settings.

## Repository contents

- `notebooks/Practical_5_Image_Generation.ipynb` — the provided practical notebook.
- `requirements.txt` — Python libraries used by the notebook.

## Experiments

The notebook currently includes:

1. Basic text-to-image generation.
2. The effect of inference steps.
4. The effect of sampling method (scheduler).

There is no Experiment 3 section in the supplied notebook. The notebook also includes code comments describing guidance scale, but does not currently contain a separate guidance-scale comparison.

## Setup

Use Python 3.10 or 3.11 in a virtual environment. Install PyTorch for the compute environment you intend to use (CPU or CUDA) by following the official PyTorch installation selector, then install the remaining dependencies:

```bash
python -m venv .venv
# Windows PowerShell
.venv\Scripts\Activate.ps1
# macOS/Linux
source .venv/bin/activate
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
```

Open the notebook:

```bash
jupyter lab notebooks/Practical_5_Image_Generation.ipynb
```

The model is downloaded from Hugging Face on first use. You need an internet connection and enough disk space and memory. A CUDA-capable GPU is recommended; CPU execution can be slow. Check the model card and its terms before use.

## Running the notebook

Run cells from top to bottom. The notebook's first cell installs or updates packages in the active environment; after a package change, restart the Jupyter kernel if prompted. The model-loading cell selects CUDA when available and otherwise selects CPU.

The displayed observations are examples. Record your own image comparisons and timings for the hardware and package versions you use.

## Reproducibility notes

The helper uses a fixed random seed so settings can be compared under similar initial noise. Generation time varies with hardware, software versions, and runtime state. Some schedulers may introduce additional randomness, so outputs need not be identical across runs.
