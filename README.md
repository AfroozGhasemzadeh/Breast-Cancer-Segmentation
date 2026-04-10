# Breast-Cancer-Segmentation
This project explores how to segment tumor regions in histopathology images using a U‑Net architecture with a ResNet34 encoder. The goal was to build a clean, reproducible baseline model that can serve as a starting point for more advanced experiments.

The entire workflow, from dataset preparation to model training and evaluation, is implemented in a single, well‑structured notebook.
# Dataset
The dataset comes from Kaggle

    /kaggle/input/datasets/andrewmvd/breast-cancer-cell-segmentation
  
It contains:

+ H&E‑stained histopathology images

+ Corresponding segmentation masks

+ Masks are grayscale PNGs (converted to binary during preprocessing)

+ Because the dataset is relatively small, data augmentation plays an important role in improving generalization
 # Tools and Libraries
The project is built with:

+ Python

+ PyTorch

+ Torchvision

+ NumPy

+ Pillow

+ Matplotlib

+ scikit‑learn

Everything is lightweight and easy to reproduce. 
# Model
The model is a ResNet34‑UNet, which combines:

+ A ResNet34 encoder pretrained on ImageNet

+ A U‑Net style decoder with skip connections

+ A single‑channel sigmoid output for binary segmentation

For the loss function, I used a combination of:

+ Binary Cross‑Entropy (BCE)

+ Dice Loss

This helps balance pixel‑level accuracy with region‑level overlap.
# Training
The training pipeline includes:

1- Data augmentation (flips, rotations, color jitter)

2- Normalization

3- Adam optimizer with a learning rate of 1e‑4

4- 20 training epochs

5- A train/validation split for monitoring performance

The notebook also includes training curves and qualitative predictions.
# What’s Inside the Notebook
The notebook walks through the entire workflow:

+ Loading and pairing images with masks

+ Building a custom PyTorch dataset

+ Applying data augmentation

+ Implementing the ResNet34‑UNet model

+ Training and validation loops

+ Visualizing predictions

+ Final baseline model summary

Everything is written to be easy to follow and modify.
# Results
The model learns meaningful tumor structures and produces masks that visually align with the ground truth. Validation Dice scores typically fall around 0.55–0.60, which is reasonable for a small dataset and a baseline model.

A final train/validation/test split was explored, but due to the limited dataset size and differences between subsets, the model did not generalize well to the test portion. This is a common issue in medical imaging and will be addressed in future iterations.
# Future Improvements

There are several directions to build on this baseline:

+ Better dataset splitting (stratified or stain‑balanced)

+ Stain normalization

+ Higher‑resolution training

+ Stronger augmentation (elastic transforms, blur)

+ Trying deeper encoders (ResNet50, EfficientNet)

+ Early stopping and checkpointing
