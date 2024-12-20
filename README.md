# scratch-detection-classification

**Scratch Detection and Classification using Mask R-CNN and ResNet50**

This project focuses on detecting scratches in images and classifying them as "Good" or "Bad" using deep learning techniques. The task involves:

    1.Classifying images based on the presence of scratches.
    2. Localizing the scratches using bounding boxes and masks.

We use ResNet50 for classification and Mask R-CNN for detecting and localizing scratches in the images.

**Project Overview**

The goal of this project is to classify images of text with or without scratches and detect the scratches in bad images. The project is split into two main tasks:

1. Image Classification: Using ResNet50, we classify images into "Good" (no scratches) and "Bad" (scratches present) categories.
2. Scratch Localization: Using Mask R-CNN, we localize scratches by drawing bounding boxes or creating masks over the scratched regions.

  **Model Selection and Training**
  
**ResNet50 for Image detection**

    ResNet50 was chosen for its ability to handle image classification tasks, especially for detecting patterns like scratches in images. The model is pretrained on ImageNet, which helps it generalize well even on smaller datasets.
    The model is fine-tuned on our dataset for the binary classification task: "Good" vs "Bad" images.

    *Scratch localization using Mask R-CNN*

    Mask R-CNN is used to localize and detect scratches in bad images by drawing bounding boxes or generating masks. This is chosen for its high precision in instance segmentation tasks.
    The model is configured to detect scratches and output bounding boxes for the regions containing scratches.

Step 1: Thresholding the Mask

-->We threshold the mask images to identify the scratched regions. By setting a threshold value, we classify images based on the scratch area. If the scratch area exceeds a certain threshold, the image is classified as a Bad Image.

Step 2: Contour Detection

-->We use contour detection to find the scratched areas. The contour areas are then summed up to calculate the total scratch area.

Step 3: Bounding Box Drawing

-->For each detected scratch region, we draw a bounding box on the original image to highlight the scratch.

**Evaluation and Metrics**

Classification Performance

The model's performance is evaluated using several metrics:

    Precision, Recall, and F1-Score for both classes ("Good" and "Bad").
    ROC Curve and AUC for overall model performance.

Macro and Weighted Averages

    Macro Average is calculated by averaging the performance across all classes.
    Weighted Average takes into account the number of samples in each class for performance evaluation.

**Results for detecting good & bad images:**

    Precision (Bad): 0.96
    Recall (Bad): 0.78
    F1-Score (Bad): 0.86
    Accuracy: 95%
