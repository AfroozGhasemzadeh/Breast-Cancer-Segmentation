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

  Python

  PyTorch

  Torchvision

  NumPy

  Pillow

  Matplotlib

  scikit‑learn

Everything is lightweight and easy to reproduce. 
