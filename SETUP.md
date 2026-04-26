# Setup Guide

## Prerequisites

- Python 3.8 or higher
- pip or conda package manager
- Git

## Installation Steps

### 1. Clone the Repository
```bash
git clone https://github.com/yourusername/cataract-detection.git
cd cataract-detection
```

### 2. Create Virtual Environment

**Using venv:**
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

**Using conda:**
```bash
conda create -n cataract python=3.10
conda activate cataract
```

### 3. Install Dependencies
```bash
pip install -r requirements.txt
```

### 4. Download Pre-trained Models

Models are stored in the `models/` directory:
- `models/anterior_eye/resnet_mlp_model.h5`
- `models/anterior_eye/vgg16_mlp_model.h5`
- `models/fundus/resnet_mlp_model.h5`

If models are stored separately, download them and place in the appropriate directories.

### 5. Prepare Data

Place your datasets in:
```
data/
├── anterior_eye/
│   ├── train/
│   ├── val/
│   └── test/
└── fundus/
    ├── train/
    ├── val/
    └── test/
```

### 6. Run Jupyter Notebooks

```bash
jupyter notebook
```

Then navigate to:
- `notebooks/anterior_eye_models/` - for anterior eye models
- `notebooks/fundus_models/` - for fundus image models

## Troubleshooting

### CUDA/GPU Issues
If you have CUDA-capable GPU and want to use it:
```bash
pip install tensorflow-gpu
# or
conda install tensorflow-gpu
```

### Import Errors
Make sure all packages in `requirements.txt` are installed:
```bash
pip install --upgrade -r requirements.txt
```

### Notebook Issues
If notebooks don't load, reinstall Jupyter:
```bash
pip install --upgrade jupyter ipykernel
```

## Project Structure

```
├── notebooks/          # Jupyter notebooks for each model
├── models/            # Trained model files (.h5)
├── data/              # Dataset directory
├── results/           # Results and visualizations
├── src/               # Python utility scripts
├── requirements.txt   # Dependencies
└── README.md          # Project overview
```

## Next Steps

1. Read [README.md](README.md) for project overview
2. Explore notebooks in `notebooks/` directory
3. Load pre-trained models and make predictions
4. Experiment with your own eye images

---

Need help? Open an issue on GitHub!
