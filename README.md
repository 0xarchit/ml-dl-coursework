# Machine Learning & Deep Learning Projects

A collection of machine learning and deep learning projects, experiments, and implementations created for a machine learning classroom.

## Contents
- Jupyter notebooks: `*.ipynb` (project code, experiments, and lab exercises)
- Data: `datasets/` (CSV, images, or other raw data used by notebooks)
- Outputs: `outputs/` (trained models, exported figures, logs)
- Environment: `requirements.txt` (Python dependencies)

## Getting started

### Create a dual environment setup

- Use `.venv` for normal CPU workflows and lighter experiments such as `ann` and `pca`.
- Use `.ubuntu-venv` inside WSL2 Ubuntu for TensorFlow GPU work with CUDA support.

### Setup `.venv` for CPU-only work

```bash
python -m venv .venv
# Windows
.venv\\Scripts\\activate
# macOS / Linux
source .venv/bin/activate
pip install -r requirements.txt
```

### Setup `.ubuntu-venv` for WSL2 GPU work

```bash
python3 -m venv .ubuntu-venv
source .ubuntu-venv/bin/activate
pip install -r requirements.txt
pip install nvidia-cudnn-cu12 nvidia-cublas-cu12 nvidia-cuda-runtime-cu12
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:$(python -c "import nvidia.cudnn; print(nvidia.cudnn.__path__[0])")/lib
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:$(python -c "import nvidia.cublas; print(nvidia.cublas.__path__[0])")/lib
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:$(python -c "import nvidia.cuda_runtime; print(nvidia.cuda_runtime.__path__[0])")/lib
wget https://developer.download.nvidia.com/compute/cuda/repos/ubuntu2204/x86_64/cuda-keyring_1.1-1_all.deb
sudo dpkg -i cuda-keyring_1.1-1_all.deb
sudo apt update
sudo apt install -y cuda-toolkit-12-5
sudo apt install -y cuda-runtime-12-5
pip install tensorflow[and-cuda]
```

### Verify GPU access in Python
```python
import tensorflow as tf
print("Num GPUs Available: ", len(tf.config.list_physical_devices('GPU')))
```

## Structure & Conventions
- Keep each project or experiment as a self-contained notebook (`*.ipynb`).
- Use `datasets/` for raw and processed data. Do not commit large raw datasets to the repo — store links or use a data storage service when appropriate.
- Save results, trained models, and generated assets in `outputs/`.
- Use `requirements.txt` to pin Python package versions for reproducibility.

## Reproducibility
- Note random seeds and environment details inside notebooks when reporting experiments.
- Prefer deterministic training settings for reproducible comparison where possible.

## License
This repository is distributed under the MIT License. See the `LICENSE` file for details.