# 🫁 Lung Segmentation using U-Net
## 🧠 Model Architecture
The U-Net architecture is distinctive due to its symmetrical structure, consisting of a contracting path (encoder) and an expansive path (decoder).

## Contracting Path (Encoder):
The contracting path is responsible for capturing the contextual and abstract features of the input image. It consists of repeated application of convolutional layers followed by ReLU activation and max pooling operations. With each downsampling step:

The spatial dimensions (height and width) of the feature maps are reduced.

The depth (number of channels) is increased. This process enables the network to learn hierarchical representations, progressively capturing more complex and abstract features, similar to conventional convolutional neural networks (CNNs).

## Expansive Path (Decoder):
The expansive path focuses on precise localization and reconstruction of the input’s spatial details to generate an accurate segmentation map. It consists of:

Upsampling layers (e.g., transposed convolutions) to increase spatial resolution.

Convolutional layers to refine features.

Skip connections from the contracting path to concatenate high-resolution features from earlier layers with the upsampled outputs.

These skip connections play a crucial role in preserving fine-grained spatial information that might be lost during downsampling, thereby allowing the decoder to better localize structures within the image.

![Group14](https://github.com/user-attachments/assets/de4a46f7-043e-485f-9e47-61df61be6244)




This repository builds upon the work of **Kevin Mader** for lung segmentation in chest X-ray images. The primary goal is to automatically identify **lung opacities** in chest X-rays, contributing to the **RSNA Pneumonia Detection Challenge**.

## 📌 Project Motivation

**Medical Image Segmentation** is a critical step in medical imaging analysis, enabling automated identification of anatomical structures. In this project, we train a **U-Net based Convolutional Neural Network (CNN)** to segment lungs from chest X-rays.

To improve model performance given limited data, we heavily rely on **data augmentation techniques** during training.

---

## 🗃️ Datasets Used

- **Montgomery County Chest X-ray Set**
  - Includes manually segmented lung masks.
- **Shenzhen Hospital Chest X-ray Set**
  - Segmentation masks manually created by **Stirenko et al.**

> 📐 All images and masks were resized to **512×512 pixels**, and **masks were dilated** to include lung boundary information.


