# Learn to See in the Rain (I): Image Raindrop Removal for UAV Aerial Imagery

## Overview
Raindrops on UAV camera lenses can severely degrade image quality, affecting tasks such as aerial surveillance, mapping, and object detection. This project introduces a novel deep learning-based approach for image raindrop removal in UAV aerial imagery. Our model adopts a **UNet-based architecture** inspired by the **MambaOut** variant from ["Mambaout paper"](https://arxiv.org/pdf/2405.07992), leveraging state-space models for improved feature representation and restoration.

The model is trained and evaluated using the **BasicSR** framework ([XPixelGroup/BasicSR](https://github.com/XPixelGroup/BasicSR)), enabling easy integration with existing image restoration pipelines.

## Features
- **UNet-inspired Mamba architecture** for efficient raindrop removal
- **Trained on real-world UAV imagery** with raindrop distortions
- **Compatible with BasicSR** for training and inference
- **Pretrained weights available** for quick deployment

## Model Architecture
Our approach integrates the strengths of UNet with the advanced sequence modeling capabilities of Mamba. The key components include:
- **Encoder-Decoder UNet** backbone for hierarchical feature learning
- **GatedCNN-based blocks** to enhance long-range dependencies and spatial coherence


## Installation
1. Clone this repository:
   ```bash
   git clone https://github.com/your-repo/image-raindrop-removal.git
   cd image-raindrop-removal
   ```
2. Install dependencies:
   ```bash
   conda create -n mambaair python=3.8
   conda activate mambaair
   pip install -r requirements.txt
   ```
3. Install BasicSR:
   ```bash
   git clone https://github.com/XPixelGroup/BasicSR.git
   cd BasicSR
   python setup.py develop
   ```

## Training & Evaluation
### Dataset
Ensure you have a dataset containing UAV images with and without raindrop distortions.

### Training
Run the following command to train the model using BasicSR:
```bash
python basicsr/train.py -opt options/train/train_raindrop_removal.yml
```

### Testing
Use the pretrained weights to test the model:
```bash
python basicsr/test.py -opt options/test/test_raindrop_removal.yml
```

## Pretrained Model
Download the pretrained model from [Google Drive / Hugging Face](#) and place it in the `models/` directory.

## Results
| Method | PSNR | SSIM |
|--------|------|------|
| Ours   | XX.X | X.XXX |
| Baseline | XX.X | X.XXX |

## Citation
If you use our model, please cite:
```

```

## Contact
<!-- For any inquiries, please open an issue or contact us at [your-email@example.com](mailto:your-email@example.com). -->

---
Let your UAV **see through the storm!** 🚁🌧️

