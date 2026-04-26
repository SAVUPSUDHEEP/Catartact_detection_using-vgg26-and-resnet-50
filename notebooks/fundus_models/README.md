# Fundus Models

This directory contains models trained on **fundus images** (retinal photographs - back of the eye).

## Contents

### ResNet50 Models
- **Notebook:** `resnet/fundus_resnet50_mlp.ipynb`
- **Model:** `../../models/fundus/resnet_mlp_model.h5`
- **Features:** ResNet50 feature extraction + MLP classifier
- **Accuracy:** ~96%

### VGG16 Models
- **Notebook:** `vgg16/fundus_vgg_mlp.ipynb`
- **Model:** `../../models/fundus/vgg16_mlp_model.h5`
- **Features:** VGG16 feature extraction + MLP classifier
- **Accuracy:** ~95%

## How to Use

1. **Open the notebook** in Jupyter:
   ```bash
   jupyter notebook notebooks/fundus_models/resnet/fundus_resnet50_mlp.ipynb
   ```

2. **Load the pre-trained model:**
   ```python
   from tensorflow.keras.models import load_model
   model = load_model('../../models/fundus/resnet_mlp_model.h5')
   ```

3. **Make predictions:**
   ```python
   predictions = model.predict(image_data)
   ```

## Data Format

- **Input:** RGB fundus photographs
- **Size:** Typically 224x224 or 256x256 pixels
- **Format:** PNG or JPG
- **Classes:** Cataract (1) vs Normal (0)

## Model Architecture

```
Input Fundus Image
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

## Dataset

Training uses fundus images from:
- Public eye disease datasets
- Medical imaging repositories

---

For more info, see the main [README.md](../../README.md)
