<<<<<<< HEAD
# 😊 Smile Face Classification

Python · TensorFlow · Keras · NumPy · Pandas · Scikit-learn · Jupyter Notebook · Deep Learning · Computer Vision

A deep learning project that classifies facial images into two categories: **Smile** and **Non-Smile** using a custom Convolutional Neural Network (CNN).
=======
# 😊 Smile Face Classification Using Transfer Learning

Python · TensorFlow · Keras · MobileNetV2 · NumPy · Matplotlib · Scikit-learn · Jupyter Notebook · Deep Learning

A deep learning project that classifies facial images into two categories: **Smile** and **Non-Smile** using transfer learning and computer vision techniques.
>>>>>>> 7f678e804186bbdcd877a879ac01dde729919a73

---

## 📌 Project Overview

<<<<<<< HEAD
Facial image classification is an application of computer vision. This project trains a model to distinguish images in the Smile category from images in the Non-Smile category.

The notebook builds a labeled image dataset from two class folders, preprocesses the images, trains a CNN, saves the trained model, and predicts labels for images in a test folder.

The system focuses on:

- 😊 **Smile Classification** — classify images labeled as Smile
- 😐 **Non-Smile Classification** — classify images labeled as Non-Smile
- 🖼️ **Image Preprocessing** — resize images and normalize pixel values
- 🧠 **CNN-Based Learning** — learn image features using convolutional neural network layers
- 💾 **Model Saving** — save and reload the trained model
- 🔍 **Test Image Prediction** — predict labels for images in the test directory

> **Model note:** The uploaded notebook uses a custom CNN trained from scratch. It does not currently use MobileNetV2 or another pretrained transfer-learning model.
=======
Facial expression classification is an important application of computer vision. This project develops an image classification model to identify faces showing a wide, open-mouth smile and distinguish them from faces displaying a normal expression.

The project uses labeled facial images to train a deep learning model that learns visual patterns associated with the two categories.

The system focuses on:

- 😊 **Smile Classification** — identify faces showing a wide or open-mouth smile
- 😐 **Non-Smile Classification** — identify faces showing a normal expression without a wide smile
- 🧠 **Transfer Learning** — leverage pretrained deep learning models for feature extraction
- 📊 **Model Evaluation** — evaluate classification performance using appropriate metrics
- 🔍 **Image Prediction** — predict the category of a new facial image

The project includes dataset organization, image preprocessing, model training, evaluation, and prediction.
>>>>>>> 7f678e804186bbdcd877a879ac01dde729919a73

---

## 🎯 Key Objectives

<<<<<<< HEAD
- 🗂️ Organize face images into Smile and Non-Smile categories
- 🧹 Load and preprocess facial image data
- 🏷️ Assign numeric labels to images and save their paths in a CSV file
- 🖼️ Resize images to `128 × 128` pixels
- 🔢 Normalize pixel values to the range `0–1`
- 🧠 Train a CNN for binary image classification
- 💾 Save the trained model for later inference
- 🔍 Predict categories for images in the test folder
=======
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
>>>>>>> 7f678e804186bbdcd877a879ac01dde729919a73

---

## 🚀 Technologies Used

| Technology | Purpose |
|---|---|
| Python | Core programming language |
<<<<<<< HEAD
| TensorFlow | Deep learning framework |
| Keras | CNN model construction and training |
| NumPy | Numerical computation and image arrays |
| Pandas | Image paths and label management |
| Scikit-learn | Training-validation data split |
=======
| TensorFlow | Deep learning and model training |
| Keras | Neural network development |
| MobileNetV2 | Pretrained feature extraction and transfer learning |
| NumPy | Numerical computation |
| Pandas | Dataset and label management |
| Matplotlib | Data visualization |
| Scikit-learn | Classification metrics and evaluation |
>>>>>>> 7f678e804186bbdcd877a879ac01dde729919a73
| Jupyter Notebook | Development and experimentation |

### Deep Learning Model

<<<<<<< HEAD
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
=======
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
>>>>>>> 7f678e804186bbdcd877a879ac01dde729919a73

---

## 📂 Dataset Details

### Smile Face Classification Dataset

<<<<<<< HEAD
The notebook expects facial images to be organized into two folders, along with a separate folder of test images.

### Dataset Categories

| Folder | Numeric label | Description |
|---|---:|---|
| `smile/` | `0` | Images in the Smile category |
| `non_smile/` | `1` | Images in the Non-Smile category |

The labels above follow the mapping used in the notebook. The model learns the definitions represented by the supplied labels, so consistent and accurate labeling is important.

### Important Dataset Considerations

- Ensure both class folders contain correctly labeled images.
- The current notebook collects `.jpg` files from the class folders.
- Check for corrupted files and duplicates before training.
- Keep the test images separate from the images used for training and validation.
- If several images come from the same person, ideally keep that person’s images in only one split to better evaluate generalization to unseen people.
=======
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
>>>>>>> 7f678e804186bbdcd877a879ac01dde729919a73

---

## 🧠 Target Classes

### 😊 Smile Classification

<<<<<<< HEAD
**Folder:** `smile/`  
**Numeric label:** `0`

The model predicts this class for images it identifies as belonging to the Smile category.

### 😐 Non-Smile Classification

**Folder:** `non_smile/`  
**Numeric label:** `1`

The model predicts this class for images it identifies as belonging to the Non-Smile category.

The output is a visual category prediction. It should not be interpreted as a reliable measure of a person's actual emotions or intentions.
=======
**Target:** `smile`

The model identifies facial images containing a wide or open-mouth smile.

### 😐 Non-Smile Classification

**Target:** `non_smile`

The model identifies facial images showing a normal expression without a wide smile.

The classification depends on the examples provided in the dataset. The model predicts visual categories rather than determining a person's actual emotions or intentions.
>>>>>>> 7f678e804186bbdcd877a879ac01dde729919a73

---

## 📊 Image Preprocessing

<<<<<<< HEAD
The notebook prepares images for CNN training through the following steps:

1. Load image paths from the `smile/` and `non_smile/` folders.
2. Assign a numeric label to each image.
3. Store image paths and labels in `labeled_faces.csv`.
4. Load the images and resize them to `128 × 128` pixels.
5. Convert images into numerical arrays.
6. Normalize pixel values to the range `0–1`.
7. Split the labeled data into training and validation sets using an 80:20 split and `random_state=42`.

### Training Configuration

| Parameter | Value |
|---|---|
| Image size | `128 × 128` pixels |
| Batch size | `32` |
| Training epochs | `10` |
| Training-validation split | `80:20` |
| Random state | `42` |
| Optimizer | Adam |
| Loss function | Binary cross-entropy |
| Training metric | Accuracy |

---

## 🤖 CNN Architecture

The project uses a custom CNN to learn visual patterns from the face images. Unlike transfer learning, this model learns its image features from the project dataset rather than reusing a pretrained ImageNet backbone.

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
=======
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
>>>>>>> 7f678e804186bbdcd877a879ac01dde729919a73

---

## 📈 Model Evaluation

<<<<<<< HEAD
The notebook tracks model accuracy during training and validation.

### Metrics Currently Used

- **Accuracy:** the proportion of correctly classified examples during the reported training or validation evaluation.

### Recommended Additional Metrics

For a more complete assessment, the project can be extended to calculate:

- **Precision:** proportion of predicted positive cases that are correct
- **Recall:** proportion of actual positive cases correctly identified
- **F1 Score:** harmonic mean of precision and recall
- **Confusion Matrix:** shows correct and incorrect predictions for both classes
- **Classification Report:** summarizes class-wise precision, recall, and F1-score

No fixed accuracy result is reported here because results depend on the dataset and the actual notebook execution.
=======
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
>>>>>>> 7f678e804186bbdcd877a879ac01dde729919a73

---

## 📊 Analysis and Visualizations

<<<<<<< HEAD
The current notebook's core workflow focuses on image preparation, CNN training, model saving, and test-image prediction. Additional visualizations that can improve the analysis include:

- Number of images in each class
- Sample Smile images
- Sample Non-Smile images
- Training and validation accuracy curves
- Training and validation loss curves
- Confusion matrix
- Classification report
- Correct and incorrect sample predictions

These additions can help identify class imbalance, overfitting, and common classification errors.
=======
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
>>>>>>> 7f678e804186bbdcd877a879ac01dde729919a73

---

## 📁 Project Structure

```text
Smile-Face-Classification/
│
├── smile/
<<<<<<< HEAD
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
=======
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
>>>>>>> 7f678e804186bbdcd877a879ac01dde729919a73
├── README.md
└── .gitignore
```

### Important Files

<<<<<<< HEAD
- **`smile/`** — images assigned to the Smile class.
- **`non_smile/`** — images assigned to the Non-Smile class.
- **`test/`** — test images used by the notebook's prediction code.
- **`SmileDetectionTask.ipynb`** — notebook containing the data preparation, CNN training, saving, and prediction workflow.
- **`labeled_faces.csv`** — CSV file containing image paths and numeric labels, generated by the notebook.
- **`FaceDetectorModel.h5`** and **`SmileFaceClassifier.h5`** — model files present in the repository. Confirm their individual roles from the cells that save or load them; their filenames alone do not establish their architectures or functions.
- **`.gitignore`** — lists files and directories excluded from Git tracking.
=======
- **`smile/`** — images belonging to the Smile category.
- **`non_smile/`** — images belonging to the Non-Smile category.
- **`test/`** — images used for testing or individual predictions, depending on the notebook implementation.
- **`SmileDetectionTask.ipynb`** — notebook containing the model implementation, training, and evaluation.
- **`FaceDetectorModel.h5`** — saved model artifact; its exact function depends on the implementation.
- **`SmileFaceClassifier.h5`** — saved model artifact intended for smile classification, subject to verification against the notebook.
- **`labeled_faces.csv`** — CSV file containing image labels or associated dataset information.
- **`.gitignore`** — specifies files and folders excluded from Git tracking.
>>>>>>> 7f678e804186bbdcd877a879ac01dde729919a73

---

## ⚙️ Installation & Setup

### 1. Clone the repository

```bash
git clone https://github.com/vatsalgajera-tech/Smile-Face-Classification.git
cd Smile-Face-Classification
```

### 2. Install required libraries

```bash
<<<<<<< HEAD
pip install tensorflow numpy pandas scikit-learn jupyter
=======
pip install tensorflow numpy pandas matplotlib scikit-learn jupyter
>>>>>>> 7f678e804186bbdcd877a879ac01dde729919a73
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

<<<<<<< HEAD
Run the cells in order, starting with imports and dataset preparation. Ensure the class folders and test images are in the expected locations relative to the notebook's working directory.

### Important Implementation Note

The uploaded notebook resizes images to `128 × 128` and uses `IMG_SIZE` when defining the model input. Define the variable before model creation so both shapes agree:

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
=======
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
>>>>>>> 7f678e804186bbdcd877a879ac01dde729919a73
```

---

## 🔮 Future Enhancements

<<<<<<< HEAD
- 📊 Add confusion matrix, precision, recall, and F1-score
- 📈 Plot training and validation accuracy and loss
- 🧪 Evaluate on a separate held-out test set
- 🗂️ Add class-distribution analysis and handle class imbalance if present
- 🧠 Compare the custom CNN with transfer-learning models such as MobileNetV2
- 🔄 Fine-tune a pretrained model and compare it with the CNN baseline
- 🖼️ Build a simple interface for image upload and prediction
- 📷 Explore real-time webcam classification
- 🌐 Deploy the model as a web application or API
=======
- 📈 Improve performance using additional high-quality labeled images
- 🧠 Compare MobileNetV2 with EfficientNetB0 and ResNet50
- 🔄 Apply fine-tuning to improve domain-specific feature learning
- 📊 Add detailed class-wise performance analysis
- 🖼️ Build an interface for uploading and classifying facial images
- 📷 Extend the project to real-time webcam classification
- 🌐 Deploy the model through a web application or API
- 📱 Explore lightweight deployment for mobile or edge devices
>>>>>>> 7f678e804186bbdcd877a879ac01dde729919a73

---

## ⚠️ Limitations

<<<<<<< HEAD
- The current notebook uses a custom CNN trained from scratch, not transfer learning.
- The notebook currently collects `.jpg` files from the two class directories.
- Prediction depends on the expected test-image filenames and file paths.
- Model performance depends on dataset size, image quality, class balance, and label accuracy.
- An image-level random split may not reliably measure performance on entirely unseen people if images of the same person appear in both splits.
- The predicted class describes the learned visual categories and does not reliably determine a person's emotional state.
=======
- Model performance depends on dataset quality, class balance, and labeling consistency.
- Lighting, image resolution, face orientation, and occlusion may affect predictions.
- Performance on unseen people may differ from performance on the training dataset.
- A predicted smile category should not be interpreted as a reliable assessment of a person's emotional state.
- Confidence scores are not necessarily calibrated probabilities.
>>>>>>> 7f678e804186bbdcd877a879ac01dde729919a73

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

<<<<<<< HEAD
**Project Focus:** Smile vs Non-Smile Facial Image Classification using a Custom CNN.
=======
**Project Focus:** Smile vs Non-Smile Facial Image Classification Using Transfer Learning.
>>>>>>> 7f678e804186bbdcd877a879ac01dde729919a73
