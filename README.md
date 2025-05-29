# Alzheimer’s MRI – CNN Benchmark & Explainable AI

## Project Overview
This notebook benchmarks several **state-of-the-art convolutional neural-network (CNN) architectures** on the public **Alzheimer’s MRI dataset** from Kaggle.  
The goals are:

1. **Model comparison** – measure validation accuracy / loss across popular backbones.  
2. **Deep-learning insight** – provide a clear, end-to-end walkthrough for anyone who wants to understand how modern CNNs behave on a real medical-imaging task.

---

## Models Evaluated

| Family    | Variants                                  |
|-----------|-------------------------------------------|
| **VGG**   | VGG-16, VGG-19                            |
| **ResNet**| ResNet-50, ResNet-101                     |
| **MobileNet** | MobileNet, MobileNet-V2              |
| **DenseNet**  | DenseNet-121, DenseNet-169           |
| **Xception**  | Xception                              |

All networks are initialized with ImageNet weights and fine-tuned on the Alzheimer’s dataset.

---

## Explainable AI (XAI)

Deep-learning models can act as black boxes—especially risky in healthcare.  
To **illuminate each network’s decision process**, the notebook integrates **Grad-CAM**:

* Generates heat-maps for every test image.  
* Highlights key anatomical regions (e.g., hippocampal atrophy) that influence predictions.  
* Saves overlay images to `outputs/grad_cam/` for quick, qualitative review.

> **Why it matters:** XAI lets clinicians verify that the model focuses on medically relevant brain areas instead of random noise or scanner artifacts.

---

## Results & Visualizations

* **Training / validation curves** for accuracy and loss are consolidated in `results_comparison.png`.  
* A bar chart ranks all architectures by best validation accuracy.  
* Example Grad-CAM overlays are stored in `README_images/` and referenced inside the notebook.

---

## Reproducibility

```bash
git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>
pip install -r requirements.txt
jupyter notebook Alzheimer_CNN_Benchmark.ipynb
