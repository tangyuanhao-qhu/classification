# Hierarchical Fusion of Local and Global Visual Features with Mixture-of-Experts for Remote Sensing Image Scene Classification
<p align="center">
  <img src="docs/logo1.png" alt="AFM-Net Logo" width="600"/>
</p>


<p align="center">

  <img src="https://img.shields.io/badge/License-MIT-blue" alt="License">
  <img src="https://img.shields.io/badge/Python-3.8%2B-green" alt="Python Version">
  <img src="https://img.shields.io/badge/PyTorch-1.12%2B-orange" alt="PyTorch Version">
  <a href="https://doi.org/10.48550/arXiv.2510.27155">
    <img src="https://img.shields.io/badge/arXiv-2510.27155-b31b1b.svg" alt="arXiv">
  </a>
  <a href="https://huggingface.co/Yuannnn-tyh/AFM-Net/">
    <img src="https://img.shields.io/badge/🤗%20Hugging%20Face-yellow" alt="Hugging Face">
  </a>

</p>

##  🔍 Introduction 

Remote sensing scene classification of high-resolution images remains a challenging task due to complex spatial structures and high intra-class variance. We propose a parallel heterogeneous framework that:
- ✅ **Synergizes Local and Global Visual Encoder**: Coupling CNN-based local texture extraction with Mamba-based global sequence modeling to ensure robust co-representation.
- ✅ **Hierarchical Fusion Strategy**: Employs a hierarchical fusion module to densely integrate heterogeneous features across different semantic levels.
- ✅ **Adaptive MoE Classifier**: Uses a Mixture-of-Experts (MoE) head to dynamically select optimal features, balancing performance with efficiency.

Extensive experiments show our model achieves state-of-the-art performance on AID, NWPU-RESISC45, and UC Merced datasets.

---

##  📐 Model Architecture

<p align="center">
  <!-- 点击图片会跳转/下载 fig1.pdf -->
  <a href="docs/fig1.pdf">
    <img src="docs/fig1.png" alt="AFM-Net Architecture" width="700"/>
  </a>
</p>

## ⚙️Installation 
### 1.Clone this repository:
```bash
git clone https://github.com/tangyuanhao-qhu/classification.git
cd classification
```
### 2.Create a Python virtual environment and install dependencies:
```bash
conda create -n class python=3.8 -y
conda activate class
pip install -r requirements.txt
```
### 3.Prepare datasets
The expected folder structure for AID dataset is as follows:
```
AID/
├── Airport/
│   ├── img1.jpg
│   ├── img2.jpg
│   └── ...
├── Beach/
│   ├── img1.jpg
│   └── ...
├── ...
```
Other datasets (NWPU-RESISC45, UC Merced) should follow a similar class-wise folder organization.

## 🚀Usage 
🔹 Training 
 ```bash
python train.py --dataset AID --batch_size 32 --epochs 500
 ```
## 🔥 Performance Comparison 
| Model                      | UC Merced (F1) | AID (F1) | NWPU (F1) |
| :-------------------------- | :-------------: | :------: | :-------: |
| **CNN-based Models**        |                 |          |           |
| ResNet18                    | 90.22           | 92.22    | 93.75     |
| ResNet50                    | 90.85           | 92.22    | 94.40     |
| ResNet101                   | 93.74           | 91.77    | 94.75     |
| **Transformer-based Models**|                 |          |           |
| DeiT-T                      | 84.42           | 80.63    | 83.45     |
| DeiT-S                      | 91.61           | 80.92    | 82.98     |
| DeiT-B                      | 92.34           | 82.05    | 79.98     |
| ViT-B                       | 90.18           | 82.54    | 80.16     |
| ViT-L                       | 92.42           | 81.84    | 79.46     |
| Swin-T                      | 88.88           | 87.35    | 89.72     |
| Swin-S                      | 89.72           | 87.03    | 89.28     |
| Swin-B                      | 91.66           | 86.37    | 89.41     |
| CMTFNet                     | 94.64           | 93.01    | 94.31     |
| **Mamba-based Models**      |                 |          |           |
| ViMamba-T                   | 92.81           | 91.10    | 93.94     |
| VisionMamba-T               | 83.06           | 78.68    | 88.97     |
| VisionMamba-S               | 89.32           | 87.54    | 95.21     |
| VisionMamba-B               | 88.82           | 90.72    | 95.06     |
| RSMamba-B                   | 93.88           | 91.66    | 94.84     |
| RSMamba-L                   | 94.74           | 91.90    | 95.02     |
| RSMamba-H                   | 95.25           | 92.63    | 95.18     |
| HC-Mamba-T                  | 94.76           | 91.42    | 94.87     |
| HC-Mamba-S                  | 95.08           | 91.95    | 95.08     |
| HC-Mamba-B                  | 95.34           | 92.86    | 95.25     |
| **Ours**                    | **96.81**       | **93.71**| **95.52** |

















