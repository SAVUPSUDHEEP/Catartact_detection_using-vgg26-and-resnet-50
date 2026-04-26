# Anterior Eye Models

This directory contains models trained on **anterior eye images** (front of the eye).

## Contents

### ResNet50 Models
- **Notebook:** `resnet/anterior_resnet_mlp.ipynb`
- **Model:** `../../models/anterior_eye/resnet_mlp_model.h5`
- **Features:** ResNet50 feature extraction + MLP classifier
- **Accuracy:** ~96%

### VGG16 Models
- **Notebooks:** 
  - `vgg16/anterior_vgg_mlp.ipynb`
  - `vgg16/anterior_vgg_final.ipynb`
- **Model:** `../../models/anterior_eye/vgg16_mlp_model.h5`
- **Features:** VGG16 feature extraction + MLP classifier
- **Accuracy:** ~95%

## How to Use

1. **Open the notebook** in Jupyter:
   ```bash
   jupyter notebook notebooks/anterior_eye_models/resnet/anterior_resnet_mlp.ipynb
   ```

2. **Load the pre-trained model:**
   ```python
   from tensorflow.keras.models import load_model
   model = load_model('../../models/anterior_eye/resnet_mlp_model.h5')
   ```

3. **Make predictions:**
   ```python
   predictions = model.predict(image_data)
   ```

## Data Format

- **Input:** RGB or grayscale anterior eye images
- **Size:** Typically 224x224 or 256x256 pixels
- **Format:** PNG or JPG
- **Classes:** Cataract (1) vs Normal (0)

## Model Architecture

```
Input Image
    ↓
[Pretrained CNN (ResNet50/VGG16)]
    ↓
Feature Vector (2048 or 512 dims)
    ↓
[MLP Classifier]
    ↓
Output Probability (0-1)
```

## Performance

| Model | Accuracy | Precision | Recall |
|-------|----------|-----------|--------|
| ResNet50 | 96% | 96% | 95% |
| VGG16 | 95% | 95% | 94% |

---

For more info, see the main [README.md](../../README.md)
