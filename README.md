# 👁️ Cataract Detection Using Deep Learning

A robust AI-based system for detecting cataracts from eye images using transfer learning and feature-based deep learning approaches.

## 🔍 Problem

Cataract is a major cause of blindness, but:
- Diagnosis usually requires specialized equipment
- Not easily accessible in rural/low-resource areas

**Goal:** Build an AI system that can detect cataracts from eye images automatically.

## 🧠 Approach (Feature-Based Deep Learning)

Instead of training a random CNN from scratch, this project uses an intelligent feature extraction strategy:

### 1. Feature Extraction (Transfer Learning)
- **Pretrained Models:** VGG16 and ResNet50
- **Strategy:** Extract deep features from eye images instead of training from scratch
- **Benefit:** Leverages knowledge from models trained on ImageNet

### 2. Classification Layer
- **Architecture:** MLP (Multi-Layer Perceptron) on extracted features
- **Why MLP?**
  - Works well on smaller datasets
  - Faster training
  - Less overfitting compared to end-to-end training

### 3. Multi-Source Input Data
Dual-modality approach for robustness:
- **Fundus Images:** Retinal photographs (back of the eye)
- **Anterior Eye Images:** Front of the eye photographs
- **Benefit:** More robust predictions by considering multiple perspectives

### 4. Training Pipeline
```
Eye Image → Preprocessing → Feature Extraction (VGG16/ResNet50) → MLP Classifier → Prediction
```

## 📊 Results

- **Accuracy:** ~95-96% classification performance
- **Models:** Both VGG16 and ResNet50 architectures validated
- **Input Types:** Dual-modality (Fundus + Anterior) for comprehensive analysis

## 📁 Project Structure

```
cataract_detection/
├── notebooks/
│   ├── anterior_eye_models/
│   │   ├── resnet/
│   │   │   └── anterior_resnet_mlp.ipynb
│   │   └── vgg16/
│   │       ├── anterior_vgg_mlp.ipynb
│   │       └── anterior_vgg_final.ipynb
│   └── fundus_models/
│       ├── resnet/
│       │   └── fundus_resnet50_mlp.ipynb
│       └── vgg16/
│           └── fundus_vgg_mlp.ipynb
├── models/
│   ├── anterior_eye/
│   │   ├── resnet_mlp_model.h5
│   │   └── vgg16_mlp_model.h5
│   └── fundus/
│       ├── resnet_mlp_model.h5
│       └── vgg16_mlp_model.h5
├── results/
│   └── visualizations/
│       ├── performance_graphs/
│       ├── confusion_matrices/
│       └── sample_predictions/
├── data/
│   ├── anterior_eye/
│   │   ├── train/
│   │   ├── val/
│   │   └── test/
│   └── fundus/
│       ├── train/
│       ├── val/
│       └── test/
├── src/
│   ├── preprocess.py
│   ├── feature_extraction.py
│   ├── model_utils.py
│   └── predict.py
├── requirements.txt
├── .gitignore
└── README.md
```

## 🛠️ Installation

1. **Clone the repository**
```bash
git clone https://github.com/yourusername/cataract-detection.git
cd cataract-detection
```

2. **Install dependencies**
```bash
pip install -r requirements.txt
```

## 📓 Running Notebooks

Each notebook contains:
- Data loading and preprocessing
- Feature extraction using transfer learning
- MLP training and validation
- Performance evaluation

### Anterior Eye Models:
- `notebooks/anterior_eye_models/resnet/anterior_resnet_mlp.ipynb`
- `notebooks/anterior_eye_models/vgg16/anterior_vgg_mlp.ipynb`

### Fundus Models:
- `notebooks/fundus_models/resnet/fundus_resnet50_mlp.ipynb`
- `notebooks/fundus_models/vgg16/fundus_vgg_mlp.ipynb`

## 📊 Model Comparison

| Model | Input Type | Accuracy | Architecture |
|-------|-----------|----------|--------------|
| VGG16 | Anterior | ~95% | VGG16 → MLP |
| ResNet50 | Anterior | ~96% | ResNet50 → MLP |
| VGG16 | Fundus | ~95% | VGG16 → MLP |
| ResNet50 | Fundus | ~96% | ResNet50 → MLP |

## 🔑 Key Features

✅ **Transfer Learning:** Uses pretrained VGG16 and ResNet50
✅ **Lightweight:** MLP classifier for efficiency
✅ **Multi-Modal:** Uses both anterior and fundus images
✅ **High Performance:** 95-96% accuracy achieved
✅ **Reproducible:** Well-documented notebooks and code

## 📝 Citation

If you use this project, please cite:

```bibtex
@software{cataract_detection_2024,
  title={Cataract Detection Using Deep Learning},
  author={Your Name},
  year={2024},
  url={https://github.com/yourusername/cataract-detection}
}
```


## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📧 Contact

For questions or inquiries, please open an issue on the repository.

---

**Built with:** Python, TensorFlow/Keras, OpenCV, Scikit-learn.
##📄 Publication

This work has been published in the Springer proceedings of ICICCT 2025.

Title:
Cataract Detection Using Deep Learning Leveraging Fundus and Anterior Eye Images

DOI: https://doi.org/10.1007/978-3-032-08600-6_38
