# Malaria Detection using CNNs

This project aims to develop a Convolutional Neural Network (CNN) to classify blood smear images as either "Malaria" or "Uninfected" to assist in the early detection of malaria. The dataset consists of around 27,500 annotated PNG images of blood smears, equally split between healthy and malaria-infected samples, taken at 100x zoom in RGB color space.

## Dataset

- **Source:** [Malaria Dataset (Thick Blood Smears 150)](https://data.lhncbc.nlm.nih.gov/public/Malaria/Thick_Smears_150/index.html)
- **Size:** ~27,500 images
- **Classes:** "Malaria" (Infected) and "Uninfected"
- **Resolution:** Images taken at 100x zoom, annotated by expert slide readers

## Problem Statement

Diagnosing malaria through traditional manual examination of blood smear slides is time-consuming and can lead to late detection, increasing mortality rates. Early detection is critical, and automated assistance through neural networks could enhance diagnostic accuracy, especially in areas with limited medical resources. This project explores using deep learning to assist in malaria diagnosis and potentially replace or supplement traditional methods.

## Model Architecture & Approach

1. **Preprocessing:**
   - Images are resized to various target sizes (64x64 and 128x128).
   - A subset of 1000 infected and 1000 uninfected images is randomly selected for testing.

2. **Training:**
   - **Training Split:** 70% of the dataset
   - **Validation Split:** 20% of the dataset
   - **Test Split:** 10% of the dataset

3. **Model Development:**
   - **Model 1:** 64x64 images, 2 convolutional layers, dropout, L2 regularization
   - **Model 2:** 128x128 images, 2 convolutional layers, dropout, L2 regularization
   - **Model 3:** 128x128 images, 3 convolutional layers, data augmentation, dropout
   - **Model 4:** 128x128 images, 3 convolutional layers, data augmentation, batch normalization, L2 regularization

4. **Regularization & Optimization:**
   - Dropout and L2 regularization were introduced to mitigate overfitting.
   - The model was evaluated for both accuracy and recall, with recall prioritized to minimize false negatives.

5. **Best Model:**
   - **Model 3** achieved the highest accuracy (96.55%) and recall (96.3%) on the test set. It uses 128x128 images, 3 convolutional layers, and data augmentation.
   - For applications where minimizing false negatives is crucial, the classification threshold can be adjusted, sacrificing precision for increased recall.

## Potential Use Case

The trained CNN can be deployed in regions with high malaria mortality rates and limited access to medical resources. In such areas, the model could help healthcare workers identify malaria-positive blood smear images, enabling quicker diagnosis and treatment. Positive diagnoses can be verified by doctors, especially if recall is maximized to avoid missing any malaria cases.

## Conclusion

The final model demonstrates the potential of deep learning for automated malaria detection, which could significantly improve diagnostic speed and accuracy, especially in resource-constrained environments.
