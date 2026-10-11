# 😊 Smile Face Classification Using Transfer Learning

Python · TensorFlow · Keras · MobileNetV2 · NumPy · Matplotlib · Scikit-learn · Jupyter Notebook · Deep Learning

A deep learning project that classifies facial images into two categories: **Smile** and **Non-Smile** using transfer learning and computer vision techniques.

---

## 📌 Project Overview

Facial expression classification is an important application of computer vision. This project develops an image classification model to identify faces showing a wide, open-mouth smile and distinguish them from faces displaying a normal expression.

The project uses labeled facial images to train a deep learning model that learns visual patterns associated with the two categories.

The system focuses on:

- 😊 **Smile Classification** — identify faces showing a wide or open-mouth smile
- 😐 **Non-Smile Classification** — identify faces showing a normal expression without a wide smile
- 🧠 **Transfer Learning** — leverage pretrained deep learning models for feature extraction
- 📊 **Model Evaluation** — evaluate classification performance using appropriate metrics
- 🔍 **Image Prediction** — predict the category of a new facial image

The project includes dataset organization, image preprocessing, model training, evaluation, and prediction.

---

## 🎯 Key Objectives

- 🗂️ Organize facial images into Smile and Non-Smile categories
- 🧹 Load and preprocess facial image data
- 🖼️ Resize images to the required input dimensions
- 🔄 Apply data augmentation to improve model generalization
- 🧠 Use transfer learning with a pretrained convolutional neural network
- 😊 Train a binary image classification model
- 📈 Evaluate the model using classification metrics
- 📊 Visualize training and validation performance
- 🔍 Predict facial expression categories for new images
- 💾 Save the trained model for future use

---

## 🚀 Technologies Used

| Technology | Purpose |
|---|---|
| Python | Core programming language |
| TensorFlow | Deep learning and model training |
| Keras | Neural network development |
| MobileNetV2 | Pretrained feature extraction and transfer learning |
| NumPy | Numerical computation |
| Pandas | Dataset and label management |
| Matplotlib | Data visualization |
| Scikit-learn | Classification metrics and evaluation |
| Jupyter Notebook | Development and experimentation |

### Deep Learning Model

- **MobileNetV2** — pretrained convolutional neural network used for transfer learning
- **Global Average Pooling** — converts feature maps into compact feature representations
- **Dense Layer** — learns patterns useful for distinguishing the two classes
- **Dropout** — helps reduce overfitting
- **Sigmoid Activation** — produces an output score for binary classification

### Preprocessing

- Image resizing
- MobileNetV2-specific image preprocessing
- Data augmentation
- Binary class labeling
- Training and validation split

---

## 📂 Dataset Details

### Smile Face Classification Dataset

The project uses a labeled facial image dataset organized into two categories.

### Dataset Categories

| Category | Description |
|---|---|
| `smile` | Facial images showing a wide or open-mouth smile |
| `non_smile` | Facial images showing a normal expression without a wide smile |

### Important Dataset Considerations

- Images should have correct category labels.
- Both classes should contain a sufficient number of representative images.
- Images should be checked for corrupted files and duplicates.
- Training, validation, and test images should be separated appropriately.
- Images from the same person should ideally not appear across different splits when evaluating generalization to unseen people.

The quality and diversity of the dataset directly affect model performance.

---

## 🧠 Target Classes

### 😊 Smile Classification

**Target:** `smile`

The model identifies facial images containing a wide or open-mouth smile.

### 😐 Non-Smile Classification

**Target:** `non_smile`

The model identifies facial images showing a normal expression without a wide smile.

The classification depends on the examples provided in the dataset. The model predicts visual categories rather than determining a person's actual emotions or intentions.

---

## 📊 Image Preprocessing

Before training, images are prepared for the pretrained model.

The preprocessing workflow includes:

- Loading images from their respective class directories
- Resizing images to `224 × 224` pixels
- Converting images into numerical tensors
- Applying MobileNetV2 preprocessing
- Applying suitable augmentation to training images
- Splitting data into training and validation sets

### Data Augmentation

The following techniques may be used during training:

- Horizontal flipping
- Random rotation
- Random zoom
- Random contrast adjustment

Data augmentation helps the model learn from variations in image appearance. Validation and test images should not receive random training augmentation.

---

## 🤖 Transfer Learning Architecture

The project uses **MobileNetV2**, a convolutional neural network pretrained on ImageNet, as the feature extraction backbone.

Instead of training an entire deep neural network from scratch, transfer learning reuses previously learned visual features and adds classification layers for the target categories.

### Model Architecture

```text
Input Facial Image
        |
        v
Resize to 224 × 224
        |
        v
Data Augmentation
        |
        v
MobileNetV2 Preprocessing
        |
        v
Pretrained MobileNetV2
        |
        v
Global Average Pooling
        |
        v
Dense Layer (128 Neurons)
        |
        v
Dropout
        |
        v
Sigmoid Output
        |
        v
Smile / Non-Smile
```

### Training Strategy

1. Load MobileNetV2 with pretrained ImageNet weights.
2. Remove its original classification head.
3. Freeze the pretrained backbone initially.
4. Add custom classification layers.
5. Train the new classification layers on the facial image dataset.
6. Optionally fine-tune selected deeper layers using a smaller learning rate.

Fine-tuning can help the model adapt pretrained visual features to the specific classification task.

---

## 📈 Model Evaluation

The model can be evaluated using the following metrics.

### Classification Metrics

- **Accuracy:** Percentage of correctly classified images
- **Precision:** Proportion of predicted positive cases that are correct
- **Recall:** Proportion of actual positive cases correctly identified
- **F1 Score:** Harmonic mean of precision and recall
- **Confusion Matrix:** Displays correct and incorrect predictions for both categories

### Training Performance

The training notebook can visualize:

- Training Accuracy
- Validation Accuracy
- Training Loss
- Validation Loss
- Confusion Matrix
- Classification Report
- Sample Image Predictions

Actual performance results should be recorded after running the notebook on the dataset.

---

## 📊 Analysis and Visualizations

The project can include the following visualizations:

- Sample Smile Images
- Sample Non-Smile Images
- Dataset Class Distribution
- Training and Validation Accuracy
- Training and Validation Loss
- Confusion Matrix
- Classification Report
- Predictions on Test Images
- Predicted Class and Confidence Score

These visualizations help analyze model learning, classification errors, and potential overfitting.

---

## 📁 Project Structure

```text
Smile-Face-Classification/
│
├── smile/
│   └── Smile category images
│
├── non_smile/
│   └── Non-Smile category images
│
├── test/
│   └── Test images
│
├── SmileDetectionTask.ipynb
├── FaceDetectorModel.h5
├── SmileFaceClassifier.h5
├── labeled_faces.csv
├── README.md
└── .gitignore
```

### Important Files

- **`smile/`** — images belonging to the Smile category.
- **`non_smile/`** — images belonging to the Non-Smile category.
- **`test/`** — images used for testing or individual predictions, depending on the notebook implementation.
- **`SmileDetectionTask.ipynb`** — notebook containing the model implementation, training, and evaluation.
- **`FaceDetectorModel.h5`** — saved model artifact; its exact function depends on the implementation.
- **`SmileFaceClassifier.h5`** — saved model artifact intended for smile classification, subject to verification against the notebook.
- **`labeled_faces.csv`** — CSV file containing image labels or associated dataset information.
- **`.gitignore`** — specifies files and folders excluded from Git tracking.

---

## ⚙️ Installation & Setup

### 1. Clone the repository

```bash
git clone https://github.com/vatsalgajera-tech/Smile-Face-Classification.git
cd Smile-Face-Classification
```

### 2. Install required libraries

```bash
pip install tensorflow numpy pandas matplotlib scikit-learn jupyter
```

### 3. Launch Jupyter Notebook

```bash
jupyter notebook
```

### 4. Open the notebook

Open:

```text
SmileDetectionTask.ipynb
```

Run the cells sequentially, starting from imports and dataset loading.

**Note:** If you are loading a previously saved model, use a compatible TensorFlow/Keras version and the same preprocessing steps used during training.

---

## 🔄 Deep Learning Workflow

```text
Facial Image Dataset
         |
         v
Dataset Loading
         |
         v
Image Inspection & Labeling
         |
         v
Image Preprocessing
         |
         v
Training / Validation Split
         |
         v
Data Augmentation
         |
         v
MobileNetV2 Transfer Learning
         |
         v
Model Training
         |
         v
Image Classification
         |
         v
Model Evaluation
         |
         v
Visualization & Prediction
         |
         v
Save Trained Model
```

---

## 🔮 Future Enhancements

- 📈 Improve performance using additional high-quality labeled images
- 🧠 Compare MobileNetV2 with EfficientNetB0 and ResNet50
- 🔄 Apply fine-tuning to improve domain-specific feature learning
- 📊 Add detailed class-wise performance analysis
- 🖼️ Build an interface for uploading and classifying facial images
- 📷 Extend the project to real-time webcam classification
- 🌐 Deploy the model through a web application or API
- 📱 Explore lightweight deployment for mobile or edge devices

---

## ⚠️ Limitations

- Model performance depends on dataset quality, class balance, and labeling consistency.
- Lighting, image resolution, face orientation, and occlusion may affect predictions.
- Performance on unseen people may differ from performance on the training dataset.
- A predicted smile category should not be interpreted as a reliable assessment of a person's emotional state.
- Confidence scores are not necessarily calibrated probabilities.

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

---

⭐ If you find this project useful for learning deep learning and computer vision, consider giving the repository a star.

**Project Focus:** Smile vs Non-Smile Facial Image Classification Using Transfer Learning.