# Machine Learning & Deep Learning Projects

A collection of machine learning and deep learning projects, experiments, and implementations created for a machine learning classroom.

## Contents
- Jupyter notebooks: `*.ipynb` (project code, experiments, and lab exercises)
- Data: `datasets/` (CSV, images, or other raw data used by notebooks)
- Outputs: `outputs/` (trained models, exported figures, logs)
- Environment: `requirements.txt` (Python dependencies)

## Getting started

1. Create a Python virtual environment and activate it.

```bash
python -m venv .venv
# Windows
.venv\\Scripts\\activate
# macOS / Linux
source .venv/bin/activate
```

2. Install dependencies:

```bash
pip install -r requirements.txt
```

3. Launch JupyterLab or Jupyter Notebook and open `*.ipynb` files:

```bash
jupyter lab
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