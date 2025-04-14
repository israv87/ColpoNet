# ColpoNet

**ColpoNet** is a deep learning framework that integrates **U-Net** and **Detectron2 (Mask R-CNN)** for multi-class semantic and instance segmentation of cervical lesions in colposcopic images. This project supports early diagnosis of cervical cancer through automated, AI-powered medical image analysis.

---

## 🎯 Objectives

- Segment regions of interest (ROIs) such as acetowhite areas, mosaic patterns, punctations, and atypical vessels using U-Net.
- Detect and classify individual lesions using Detectron2 for instance segmentation.
- Provide a reproducible, research-friendly pipeline for evaluating and visualizing medical image segmentation results.

---

## 🧱 Architecture

ColpoNet combines two complementary approaches:

- **U-Net**: Performs **pixel-wise semantic segmentation** for each lesion class. Output is a multi-class mask with one channel per lesion type.
- **Detectron2 (Mask R-CNN)**: Performs **instance segmentation and classification**, identifying and delineating individual lesion regions with bounding boxes and masks.

---

## 📁 Project Structure

```
ColpoNet/
├── notebooks/               # Jupyter Notebooks for training, testing, and visualization
├── data/
│   ├── raw/                 # Original images and masks
│   └── processed/           # Preprocessed images/masks for training
├── models/                  # Saved models and checkpoints
├── utils/                   # Utility scripts (metrics, visualization, preprocessing)
├── unet/                    # U-Net training and evaluation scripts
├── detectron/               # Detectron2 training setup
├── README.md
├── requirements.txt
└── .gitignore
```

---

## ⚙️ Setup Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/ColpoNet.git
cd ColpoNet
```

### 2. Create and Activate Virtual Environment

```bash
python -m venv colponet_env
source colponet_env/bin/activate  # Linux/Mac
colponet_env\Scripts\activate     # Windows
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

Make sure you have **CUDA/cuDNN** properly configured if using GPU.

---

## 🧪 How to Train

### U-Net

```bash
cd unet
python train_unet.py --config configs/unet_config.yaml
```

### Detectron2

```bash
cd detectron
python train_detectron.py --config configs/detectron_config.yaml
```

---

## 📊 Evaluation & Metrics

ColpoNet uses the following metrics for model evaluation:

- **IoU (Intersection over Union)** and **Dice Score** for U-Net
- **COCO metrics (AP, AP50, AP75, etc.)** for Detectron2
- Confusion matrix and class-wise analysis (optional)

---

## 🖼️ Visualization

ColpoNet includes tools to:

- Plot training/validation curves
- Display predicted vs ground truth masks
- Show instance-level predictions with bounding boxes and labels

---

## 🧾 Dataset Format

- Images must be in `.jpg` or `.png` format.
- Masks for U-Net must be in **multi-channel** or **indexed grayscale** format.
- Detectron2 annotations should follow **COCO format**.

---

## 📜 License

This project is licensed under the **MIT License** – see the [LICENSE](LICENSE) file for details.

---

## 🙌 Acknowledgements

This project builds on the foundations of:

- [Detectron2](https://github.com/facebookresearch/detectron2)
- [U-Net](https://arxiv.org/abs/1505.04597)
- TensorFlow, PyTorch, OpenCV, and Scikit-learn

---

## 🤝 Contributions

Feel free to fork this repo and submit pull requests. Contributions, suggestions, and issues are welcome!

---

## 📬 Contact

For research collaborations or questions, please contact:

**Ramiro Vivanco**  
GitHub: [@yourusername](https://github.com/yourusername)  
Email: [your.email@example.com](mailto:your.email@example.com)

