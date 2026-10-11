# 😊 Smile Face Classification Using Transfer Learning

**Python · TensorFlow · Keras · MobileNetV2 · Deep Learning · Computer Vision**

A deep learning project that classifies facial images into two categories: **Smile** and **Non-Smile**. The project uses image preprocessing and transfer learning to train a model that recognizes wide, open-mouth smiles and distinguishes them from normal facial expressions.

## 📌 Project Overview

Facial expression classification is an important application of computer vision. This project focuses on identifying whether a face image represents a wide smile or a normal, non-smiling expression.

The model learns visual features from labeled face images and uses them to predict the appropriate category for an input image.

### 🎯 Key Objectives

- Classify facial images into Smile and Non-Smile categories.
- Organize and prepare labeled face image data.
- Apply image preprocessing and resizing.
- Use transfer learning to leverage pretrained visual features.
- Train and evaluate a binary image-classification model.
- Generate predictions for previously unseen face images.
- Visualize training performance and classification results.

## 🧠 Classification Categories

| Class | Description |
|---|---|
| Smile | Face images showing a wide or open-mouth smile |
| Non-Smile | Face images showing a normal expression without a wide smile |

The model is designed for these two dataset-specific categories. Its predictions depend on the quality, diversity, and labeling of the training images.

## 🚀 Technologies Used

| Technology | Purpose |
|---|---|
| Python | Core programming language |
| TensorFlow | Deep learning framework |
| Keras | Model development and training |
| MobileNetV2 | Pretrained feature extraction and transfer learning |
| NumPy | Numerical operations |
| Matplotlib | Visualization of images and training results |
| Scikit-learn | Classification metrics and evaluation |
| Jupyter Notebook | Development and experimentation |

## 🤖 Model Architecture

The project uses a transfer learning approach with MobileNetV2, a convolutional neural network pretrained on ImageNet.

### Workflow

1. Load labeled face images.
2. Resize images to the required input dimensions.
3. Normalize image values using MobileNetV2 preprocessing.
4. Apply data augmentation to improve generalization.
5. Extract image features using the pretrained MobileNetV2 base.
6. Add classification layers for the two target categories.
7. Train the classification head on the face image dataset.
8. Generate predictions and evaluate model performance.

### Architecture

```text
Input Face Image
       |
       v
Image Resizing
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
Dense + Dropout Layers
       |
       v
Sigmoid Output
       |
       v
Smile / Non-Smile
```

**Transfer learning:** The pretrained model provides useful visual feature representations, reducing the need to train a large convolutional network entirely from scratch.

## 📂 Repository Structure

```text
Smile-Face-Classification/
│
├── smile/
│   └── Smile class images
│
├── non_smile/
│   └── Non-Smile class images
│
├── test/
│   └── Test images
│
├── SmileDetectionTask.ipynb
├── FaceDetectorModel.h5
├── SmileFaceClassifier.h5
├── labeled_faces.csv
└── .gitignore
```

**File descriptions:**

- `smile/` — images belonging to the Smile category.
- `non_smile/` — images belonging to the Non-Smile category.
- `test/` — images intended for testing or prediction.
- `SmileDetectionTask.ipynb` — notebook containing the project implementation and experiments.
- `FaceDetectorModel.h5` — saved model file; its exact role depends on how it was trained and used in the notebook.
- `SmileFaceClassifier.h5` — saved smile-classification model.
- `labeled_faces.csv` — CSV file containing face-image labels or related dataset information.

*Note: The actual directory contents, model architecture, and notebook implementation determine the exact behavior of each saved artifact.*

## ⚙️ Installation and Setup

### 1. Clone the repository

```bash
git clone https://github.com/vatsalgajera-tech/Smile-Face-Classification.git
cd Smile-Face-Classification
```

### 2. Create a virtual environment (optional)

```bash
python -m venv venv
```

Activate it on Windows:

```bash
venv\Scripts\activate
```

### 3. Install dependencies

```bash
pip install tensorflow numpy pandas matplotlib scikit-learn jupyter
```

### 4. Launch Jupyter Notebook

```bash
jupyter notebook
```

Open `SmileDetectionTask.ipynb` and execute the cells in order.

**Important:** Use the same model architecture and preprocessing configuration used to save the trained model when loading it for prediction. If a notebook uses a specific TensorFlow/Keras version, install a compatible version.

## 📊 Model Evaluation

The model can be evaluated using appropriate binary classification metrics:

- **Accuracy:** Overall proportion of correct predictions.
- **Precision:** Proportion of predicted positive cases that are correct.
- **Recall:** Proportion of actual positive cases correctly identified.
- **F1-score:** Harmonic mean of precision and recall.
- **Confusion Matrix:** Shows correct and incorrect predictions for both classes.

Training and validation accuracy/loss plots can also help identify overfitting and assess model generalization.

Actual performance values should be reported after running the notebook on the dataset.

## 🔍 Applications

- Facial expression classification
- Computer vision learning projects
- Image classification demonstrations
- Deep learning and transfer learning experiments
- Educational AI and machine learning applications

## ⚠️ Limitations

- Performance depends on dataset size, image quality, and label accuracy.
- Lighting, face orientation, occlusion, and image resolution may affect predictions.
- A model trained on a limited dataset may not generalize to unfamiliar faces or environments.
- Smile classification does not reliably measure a person's emotions or intentions.

## 🔮 Future Enhancements

- Compare MobileNetV2 with other pretrained architectures.
- Apply fine-tuning to selected pretrained layers.
- Add a separate test-set evaluation.
- Improve dataset balance and diversity.
- Build an interface for uploading an image and viewing predictions.
- Develop a real-time webcam demonstration.
- Deploy the classifier as a web application or API.

## 👨‍💻 Author

**Vatsal Gajera**

GitHub: [@vatsalgajera-tech](https://github.com/vatsalgajera-tech)

---

⭐ If you find this project useful for learning deep learning and computer vision, consider giving the repository a star.

**Project Focus:** Binary Facial Image Classification using Transfer Learning.
