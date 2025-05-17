# Ultrasound Nerve Segmentation

This mini-project was developed as part of the **Machine Learning** course during our **Bachelor's in Computer Science and Engineering (Artificial Intelligence & Machine Learning)**. The goal of this project is to automate the process of nerve segmentation in ultrasound images using deep learning. The main focus was on identifying the **brachial plexus**, a network of nerves in the neck and shoulder region that is crucial for procedures like **Peripheral Nerve Blocks (PNB)**. By implementing a **U-Net architecture**, the aim was to enhance the accuracy and efficiency of ultrasound-based nerve detection, ultimately contributing to better clinical outcomes and safer medical procedures.

## 📝 Project Overview

* **Goal:** Automate nerve segmentation in ultrasound images for improved diagnosis and regional anesthesia.
* **Model Used:** U-Net (CNN-based encoder-decoder architecture)
* **Accuracy Achieved:** 98.5%
* **Loss Function:** Binary Crossentropy
* **Optimizer:** Adam

## 🧩 Problem Statement

Peripheral Nerve Blocks (PNB) are essential for pain management during surgeries. However, detecting nerve structures via ultrasound is challenging due to **speckle noise** and **echo distortions**. The model aims to solve this by segmenting nerves accurately from ultrasound images using deep learning.

## 🧪 Dataset

The dataset used in this project is sourced from the Kaggle competition: [Ultrasound Nerve Segmentation](https://www.kaggle.com/competitions/ultrasound-nerve-segmentation). It contains ultrasound images and their corresponding annotated masks for nerve segmentation tasks.

* **Train Images:** 5635
* **Test Images:** 5508
* **Structure:**
  * `train/` → Ultrasound images + annotated masks
  * `test/` → Ultrasound images (no masks)
  * `train_masks.csv` → RLE-encoded mask data
* **Annotation:** Expert-labeled mask regions identifying the brachial plexus.

## ⚙️ Methodology

### 🔧 Data Preprocessing

* Resized input images to a fixed shape.
* Normalized pixel values.
* Converted RLE-encoded masks to 2D binary masks.
* Split into training and validation sets.

### 🧠 Model Architecture – U-Net

* **Encoder:** Repeated Conv2D + MaxPooling + Dropout blocks.
* **Decoder:** Conv2DTranspose layers with skip connections.
* **Final Output:** Sigmoid activated 1-channel mask.

### 🏁 Training

* **Epochs:** 50 (early stopped at 22)
* **Callbacks:** EarlyStopping & ModelCheckpoint
* **Evaluation Metric:** Accuracy, Binary Crossentropy

## 📊 Results

* **Final Accuracy:** 98.5%
* **Best Validation Loss:** 0.02

Sample segmented outputs are visualized in the provided notebook.

## 🚀 Future Scope

* Improve robustness using attention mechanisms or pre-trained encoders.
* Integrate with clinical decision-making systems.
* Deploy in telemedicine environments for remote diagnosis.

## 🧑‍💻 Contributors

* Nikitha Matta 
* Venkata Rami Reddy 
* Boyi Gurunadh 
* Kodali Naga Vamsi 
