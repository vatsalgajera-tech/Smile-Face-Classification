# 😊 Smile Face Classification

Python · TensorFlow · Keras · NumPy · Pandas · Scikit-learn · Jupyter Notebook · Deep Learning · Computer Vision

A deep learning project that classifies facial images into two categories: **Smile** and **Non-Smile** using a custom Convolutional Neural Network (CNN).

---

## 📌 Project Overview

Facial image classification is an application of computer vision. This project trains a model to distinguish images in the Smile category from images in the Non-Smile category.

The notebook builds a labeled image dataset from two class folders, preprocesses the images, trains a CNN, saves the trained model, and predicts labels for images in a test folder.

The system focuses on:

- 😊 **Smile Classification** — classify images labeled as Smile
- 😐 **Non-Smile Classification** — classify images labeled as Non-Smile
- 🖼️ **Image Preprocessing** — resize images and normalize pixel values
- 🧠 **CNN-Based Learning** — learn image features using convolutional neural network layers
- 💾 **Model Saving** — save and reload the trained model
- 🔍 **Test Image Prediction** — predict labels for images in the test directory

> **Model note:** This project uses a custom CNN trained from scratch. It does not currently use MobileNetV2 or another pretrained transfer-learning model.

---

## 🎯 Key Objectives

- 🗂️ Organize face images into Smile and Non-Smile categories
- 🧹 Load and preprocess facial image data
- 🏷️ Assign numeric labels to images and save their paths in a CSV file
- 🖼️ Resize images to `128 × 128` pixels
- 🔢 Normalize pixel values to the range `0–1`
- 🧠 Train a CNN for binary image classification
- 💾 Save the trained model for later inference
- 🔍 Predict categories for images in the test folder

---

## 🚀 Technologies Used

| Technology       | Purpose                                |
| ---------------- | -------------------------------------- |
| Python           | Core programming language              |
| TensorFlow       | Deep learning framework                |
| Keras            | CNN model construction and training    |
| NumPy            | Numerical computation and image arrays |
| Pandas           | Image paths and label management       |
| Scikit-learn     | Training-validation data split         |
| Jupyter Notebook | Development and experimentation        |

### Deep Learning Model

The notebook uses a **custom Convolutional Neural Network (CNN)**.

- **Conv2D** — learns visual features from images
- **MaxPooling2D** — reduces the spatial dimensions of feature maps
- **Flatten** — converts feature maps into a one-dimensional representation
- **Dense layers** — learn patterns for binary classification
- **Dropout (0.5)** — helps reduce overfitting
- **Sigmoid output** — produces a score used to choose between the two classes

The model is compiled with the Adam optimizer, binary cross-entropy loss, and accuracy as a training metric.

### Preprocessing

- Image loading from class folders
- Image resizing to `128 × 128`
- Pixel normalization by dividing values by `255.0`
- Numeric class labeling
- Train-validation split

---

## 📂 Dataset Details

### Smile Face Classification Dataset

The notebook expects facial images to be organized into two folders, along with a separate folder of test images.

### Dataset Categories

| Folder       | Numeric Label | Description                      |
| ------------ | ------------: | -------------------------------- |
| `smile/`     |           `0` | Images in the Smile category     |
| `non_smile/` |           `1` | Images in the Non-Smile category |

The labels follow the mapping used in the notebook. Consistent and accurate labeling is important for effective model training.

### Important Dataset Considerations

- Ensure both class folders contain correctly labeled images.
- The current notebook collects `.jpg` files from the class folders.
- Check for corrupted files and duplicates before training.
- Keep test images separate from training and validation images.
- Ideally, images of the same person should not appear in both training and validation sets.

---

## 🧠 Target Classes

### 😊 Smile Classification

**Folder:** `smile/`  
**Numeric label:** `0`

The model predicts this class for images it identifies as belonging to the Smile category.

### 😐 Non-Smile Classification

**Folder:** `non_smile/`  
**Numeric label:** `1`

The model predicts this class for images it identifies as belonging to the Non-Smile category.

The output represents a visual category prediction and should not be interpreted as a reliable measure of a person's actual emotions or intentions.

---

## 📊 Image Preprocessing

The notebook prepares images for CNN training through the following steps:

1. Load image paths from the `smile/` and `non_smile/` folders.
2. Assign a numeric label to each image.
3. Store image paths and labels in `labeled_faces.csv`.
4. Load the images and resize them to `128 × 128` pixels.
5. Convert images into numerical arrays.
6. Normalize pixel values to the range `0–1`.
7. Split the labeled data into training and validation sets using an 80:20 split and `random_state=42`.

### Training Configuration

| Parameter                 | Value                |
| ------------------------- | -------------------- |
| Image size                | `128 × 128` pixels   |
| Batch size                | `32`                 |
| Training epochs           | `10`                 |
| Training-validation split | `80:20`              |
| Random state              | `42`                 |
| Optimizer                 | Adam                 |
| Loss function             | Binary cross-entropy |
| Training metric           | Accuracy             |

---

## 🤖 CNN Architecture

The project uses a custom CNN to learn visual patterns from face images. Unlike transfer learning, this model learns its image features from the project dataset rather than reusing a pretrained ImageNet backbone.

### Model Workflow

```text
Smile / Non-Smile Images
          |
          v
     Image Labeling
          |
          v
    labeled_faces.csv
          |
          v
  Load and Resize Images
       (128 × 128)
          |
          v
   Normalize Pixel Values
          (0–1)
          |
          v
   Train / Validation Split
          |
          v
       Custom CNN
          |
          v
    Binary Classification
          |
          v
     Save Trained Model
          |
          v
     Predict Test Images
```

### CNN Components

- **Convolution layers:** learn visual patterns in image regions.
- **Max-pooling layers:** reduce feature-map dimensions.
- **Flatten layer:** converts extracted feature maps into a vector.
- **Dense layers:** combine learned features for classification.
- **Dropout:** randomly disables a proportion of units during training to help reduce overfitting.
- **Sigmoid output:** provides a single score for binary classification.

---

## 📈 Model Evaluation

The notebook tracks model accuracy during training and validation.

### Metrics Currently Used

- **Accuracy:** the proportion of correctly classified examples during the reported training or validation evaluation.

### Recommended Additional Metrics

The project can be extended to calculate:

- **Precision:** proportion of predicted positive cases that are correct.
- **Recall:** proportion of actual positive cases correctly identified.
- **F1 Score:** harmonic mean of precision and recall.
- **Confusion Matrix:** shows correct and incorrect predictions for both classes.
- **Classification Report:** summarizes class-wise precision, recall, and F1-score.

No fixed accuracy result is reported here because results depend on the dataset and the actual notebook execution.

---

## 📊 Analysis and Visualizations

Additional visualizations that can improve the analysis include:

- Number of images in each class
- Sample Smile images
- Sample Non-Smile images
- Training and validation accuracy curves
- Training and validation loss curves
- Confusion matrix
- Classification report
- Correct and incorrect sample predictions

These additions can help identify class imbalance, overfitting, and common classification errors.

---

## 📁 Project Structure

```text
Smile-Face-Classification/
│
├── smile/
│   └── Smile category images (.jpg)
│
├── non_smile/
│   └── Non-Smile category images (.jpg)
│
├── test/
│   ├── 1.jpg
│   ├── 2.jpg
│   └── ...
│
├── SmileDetectionTask.ipynb
├── labeled_faces.csv
├── FaceDetectorModel.h5
├── SmileFaceClassifier.h5
├── README.md
└── .gitignore
```

### Important Files

- **`smile/`** — images assigned to the Smile class.
- **`non_smile/`** — images assigned to the Non-Smile class.
- **`test/`** — test images used by the notebook's prediction code.
- **`SmileDetectionTask.ipynb`** — notebook containing data preparation, CNN training, model saving, and prediction.
- **`labeled_faces.csv`** — CSV file containing image paths and numeric labels.
- **`FaceDetectorModel.h5`** and **`SmileFaceClassifier.h5`** — model files present in the repository. Confirm their individual roles from the notebook's save/load cells.
- **`.gitignore`** — lists files and directories excluded from Git tracking.

---

## ⚙️ Installation & Setup

### 1. Clone the Repository

```bash
git clone https://github.com/vatsalgajera-tech/Smile-Face-Classification.git
cd Smile-Face-Classification
```

### 2. Install Required Libraries

```bash
pip install tensorflow numpy pandas scikit-learn jupyter
```

### 3. Launch Jupyter Notebook

```bash
jupyter notebook
```

### 4. Open the Notebook

Open:

```text
SmileDetectionTask.ipynb
```

Run the cells in order, starting with imports and dataset preparation. Ensure the class folders and test images are in the expected locations relative to the notebook's working directory.

### Important Implementation Note

The notebook resizes images to `128 × 128` and uses `IMG_SIZE` when defining the model input. Define the variable before model creation so both shapes agree:

```python
IMG_SIZE = (128, 128)
```

The prediction code expects test images named `1.jpg` through `50.jpg` in the `test/` folder. Adjust the file paths or loop if your test folder contains a different set of filenames.

---

## 🔄 Machine Learning Workflow

```text
Dataset
   |
   v
Load Image Paths
   |
   v
Assign Class Labels
   |
   v
Create labeled_faces.csv
   |
   v
Image Loading and Resizing
   |
   v
Pixel Normalization
   |
   v
Train-Validation Split
   |
   v
CNN Model Training
   |
   v
Save Model
   |
   v
Load Model and Predict
   |
   v
Review Predictions
```

---

## 🔮 Future Enhancements

- 📊 Add confusion matrix, precision, recall, and F1-score.
- 📈 Plot training and validation accuracy and loss.
- 🧪 Evaluate on a separate held-out test set.
- 🗂️ Add class-distribution analysis and handle class imbalance if present.
- 🧠 Compare the custom CNN with transfer-learning models such as MobileNetV2.
- 🔄 Fine-tune a pretrained model and compare it with the CNN baseline.
- 🖼️ Build a simple interface for image upload and prediction.
- 📷 Explore real-time webcam classification.
- 🌐 Deploy the model as a web application or API.

---

## ⚠️ Limitations

- The current notebook uses a custom CNN trained from scratch, not transfer learning.
- The notebook currently collects `.jpg` files from the two class directories.
- Prediction depends on the expected test-image filenames and file paths.
- Model performance depends on dataset size, image quality, class balance, and label accuracy.
- An image-level random split may not reliably measure performance on entirely unseen people if images of the same person appear in both splits.
- The predicted class describes the learned visual categories and does not reliably determine a person's emotional state.

---

## 👨‍💻 Contributor

<table>
  <tr>
    <td align="center">
      <a href="https://github.com/vatsalgajera-tech">
        <img src="https://github.com/vatsalgajera-tech.png" width="80" alt="Vatsal Gajera GitHub profile"/><br/>
        <b>Vatsal Gajera</b>
      </a><br/>
      <sub>Data Science · Deep Learning · Computer Vision</sub>
    </td>
  </tr>
</table>
