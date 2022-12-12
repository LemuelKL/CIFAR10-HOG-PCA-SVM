# CIFAR10-HOG-SVM
Classifier for CIFAR-10. Grayscaling, HOG, PCA, and RBF SVM. 62% test accuracy.

# Dimensionality Reduction

1. Input `32x32x3 => 3072`
2. Grayscale `32x32x1 => 1024`
3. HOG `pixels_per_cell=(8, 8), cells_per_block=(2, 2) => 324`
4. PCA `80% explained variance => 66`

# Configuration and Hyperparameters

- Input -> Grayscaling -> HOG -> PCA -> Stardardization + normalization -> SVM
- Support Vector Machine (SVM) with the radial basis function (KBF) kernel
- `C = 10`
- Scikit-learn modules are used

# Time Complexity

- This training time of this non-linear SVM grows faster than linear time against the number of samples
- Training takes 5 minutes on Google Colab Free
- Scoring against the test dataset takes 1 minuite

# Accuracy

- 62% against the test dataset
- Confusion matrix also available ![download](https://user-images.githubusercontent.com/20835180/207023895-8bb3cf04-bb49-4e0e-afb9-d023409b3f39.png)
  - Good separation between animals and machineries
  - Rather confused between different types of animals (cats vs deer), and different types of machineries (airplanes vs ships)
  - Confused between cats and dogs
