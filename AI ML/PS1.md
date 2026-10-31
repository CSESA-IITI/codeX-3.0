# Problem Statement 1: Supervised and Unsupervised Learning Algorithms

**Datasets:** Dogs vs. Cats (Supervised), MNIST Handwritten Digits (Unsupervised)

## 1. Problem Statement

In Machine Learning (ML), how an algorithm learns from data is fundamentally dictated by the nature of the dataset and the presence or absence of ground-truth labels. The primary objective of this PS is to establish a practical understanding of the two foundational pillars of machine learning: **Supervised Learning** and **Unsupervised Learning**.

In real-world applications, labeled data is often expensive, time-consuming, or impossible to acquire, whereas unlabeled data is abundant. Therefore, a machine learning practitioner must understand how to leverage explicit supervision to build high-accuracy predictive models, as well as how to extract meaningful hidden structures, patterns, and groupings from raw, unlabeled data.

This Problem Statement (PS1) requires the design, implementation, and evaluation of two distinct machine learning pipelines:

**Task A** (Supervised Learning): Build a model to classify images as either a cat or a dog using the **Cats and Dogs Dataset**, where every image already comes with the correct label.

**Task B** (Unsupervised Learning): Build a model to automatically group similar handwritten numbers using the **MNIST Digits Dataset** (with the labels removed), relying only on pixel brightness and shapes.

---

## 2. Algorithms to Study, Expected Outputs, and Evaluation Metrics

### Task A: Supervised Learning (Cats and Dogs Classification)

In supervised learning, the dataset consists of image-label pairs $D = \{(x_1, y_1), (x_2, y_2), \dots, (x_n, y_n)\}$, where $x_i$ is the input image and $y_i \in \{0, 1\}$ is the true label (e.g., $0$ for Cat, $1$ for Dog). The goal is to train a model $f(x; \theta) \to \hat{y}$ to predict the correct label by minimizing prediction errors (using a loss function like Binary Cross-Entropy) on the training data.

## 2. Algorithms to Study, Expected Outputs, and Evaluation Metrics

### Task A: Supervised Learning (Cats and Dogs Classification)

In supervised learning, the dataset consists of image-label pairs $D = \{(x_1, y_1), (x_2, y_2), \dots, (x_n, y_n)\}$, where $x_i$ is the input image and $y_i \in \{0, 1\}$ is the true label ($0$ for Cat, $1$ for Dog). The goal is to train a model $f(x; \theta) \to \hat{y}$ to predict the correct label by minimizing prediction errors (using Binary Cross-Entropy loss) on the training data.

#### 1. Algorithms to Study
* **Convolutional Neural Networks (CNNs):** Build a custom CNN from scratch. Learn how convolution layers, pooling layers, and activation functions (ReLU, Sigmoid) automatically extract visual features step-by-step (from simple edges to full object shapes).
* **Transfer Learning (e.g., ResNet, MobileNet, or VGG):** Fine-tune a pre-trained model (trained on ImageNet) to see how leveraging existing visual knowledge improves accuracy and speeds up training compared to a custom CNN.

#### 2. Expected Outputs & Deliverables
* **Model Predictions:** For each test image, output a probability score $P(y=1 \mid x_{\text{test}}) \in [0, 1]$ and a final class prediction $\hat{y} \in \{0, 1\}$.
* **Training & Validation Curves:** Plots of Training vs. Validation Loss and Accuracy over epochs for both the custom CNN and the Transfer Learning model.
* **Evaluation Metrics:** Confusion Matrix, Accuracy, Precision, Recall, and $F_1$-Score comparing both approaches.

---

### Task B: Unsupervised Learning (MNIST Handwritten Digits)

In unsupervised learning, the true labels are hidden during training. You are given an unlabeled dataset $D = \{x_1, x_2, \dots, x_n\}$, where each $x_i \in \mathbb{R}^{784}$ is a flattened $28 \times 28$ grayscale image. The goal is to find hidden patterns and group similar digit images into $K$ clusters without using any labels.

#### 1. Algorithms to Study
* **$K$-Means Clustering:** Group data points around $K$ cluster centers (centroids) by minimizing the distance between images and their assigned center:
  $$J = \sum_{j=1}^{K} \sum_{x_i \in C_j} \|x_i - \mu_j\|^2$$
* **Dimensionality Reduction (PCA & $t$-SNE):** Use Principal Component Analysis (PCA) or $t$-SNE to compress the $784\text{D}$ image vectors down to $2\text{D}$ so you can reduce noise and visually plot the clusters.

#### 2. Expected Outputs & Deliverables
* **Cluster Assignments & Center Images:** Group the images into $K=10$ clusters and plot the $28 \times 28$ grayscale images of the learned cluster centers ($\mu_1, \dots, \mu_{10}$) to see if the averages look like actual digits ($0\text{--}9$).
* **2D Cluster Visualization:** A $2\text{D}$ scatter plot (using PCA or $t$-SNE) colored by cluster ID to show how well the groups separate.
* **Evaluation Metrics:**
  * **Without Labels:** Elbow Method curve (Inertia) or Silhouette Score to evaluate cluster quality.
  * **With True Labels (for final testing only):** Compare your clusters against the actual MNIST labels using Adjusted Rand Index (ARI) or Normalized Mutual Information (NMI).

---

### Summary Comparison Matrix

| Dimension | Task A: Supervised (Cats vs. Dogs) | Task B: Unsupervised (MNIST Digits) |
| :--- | :--- | :--- |
| **Input Data** | Labeled Color Images $(x_i, y_i)$ | Unlabeled Grayscale Images $(x_i)$ |
| **Main Goal** | Predict the right class (Cat or Dog) | Group similar digits into clusters |
| **Algorithms** | Custom CNN, Transfer Learning (ResNet/VGG) | $K$-Means Clustering, PCA / $t$-SNE |
| **Direct Output** | Predicted Class $\hat{y} \in \{0, 1\}$ | Cluster ID $c_i \in \{1 \dots K\}$ & 2D Plot |
| **Evaluation Metrics** | Accuracy, $F_1$-Score, Confusion Matrix | Inertia (Elbow Curve), Silhouette Score, ARI / NMI |