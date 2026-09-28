# Handwritten Digit Classification using ANN | MNIST Dataset

A Deep Learning project to classify handwritten digits (0–9) using an Artificial Neural Network (ANN) on the MNIST dataset.

The main purpose of this project is to understand how a basic Neural Network works, how image data is prepared for an ANN, how an ANN is implemented using TensorFlow/Keras, and how the trained model makes predictions.

---

## 📌 Dataset

The **MNIST (Modified National Institute of Standards and Technology)** dataset contains handwritten digit images from **0 to 9**.

Each image is:

- Grayscale
- 28 × 28 pixels
- Represented by pixel intensity values from 0 to 255
- Associated with a label from 0 to 9

The dataset contains:

- 60,000 training images
- 10,000 test images

This is a **multiclass classification problem with 10 classes**.

---

## 📂 Dataset Loading

The MNIST dataset is loaded directly using TensorFlow/Keras:

```python
(X_train, y_train), (X_test, y_test) = keras.datasets.mnist.load_data()

Dataset Shapes
X_train → (60000, 28, 28)
y_train → (60000,)

X_test  → (10000, 28, 28)
y_test  → (10000,)

🧠 ANN Architecture

The neural network follows this architecture:
              28 × 28 Image
                    ↓
                 Flatten
                    ↓
               784 Features
                    ↓
             Dense Layer
              128 Neurons
                    ↓
                  ReLU
                    ↓
             Dense Layer
              10 Neurons
                    ↓
                 Softmax
                    ↓
          Predicted Digit (0–9)
Model
model = Sequential([
    Input(shape=(28, 28)),
    Flatten(),
    Dense(128, activation='relu'),
    Dense(10, activation='softmax')
])


🏋️ Model Compilation

The model is compiled using:

Optimizer: Adam
Loss: Sparse Categorical Cross-Entropy
Metric: Accuracy

The loss function is suitable because the MNIST labels are integer class labels rather than one-hot encoded vectors.

🚀 Model Training

The model is trained for:
10 epochs
Input
  ↓
Forward Propagation
  ↓
Prediction
  ↓
Loss Calculation
  ↓
Backpropagation
  ↓
Weight Updates
  ↓
Next Batch
  ↓
Repeat

🔮 Prediction

After training, the model produces probabilities for each of the 10 classes.

The predicted class is obtained using:
y_pred = y_prob.argmax(axis=1)
argmax() returns the index corresponding to the highest probability.

Therefore:
10 probabilities
      ↓
Highest probability
      ↓
Predicted digit

📊 Model Evaluation

The trained model is evaluated on the MNIST test dataset.

The model achieved approximately:
97.85% Test Accuracy
This means the model correctly classified approximately 97.85% of the unseen test images.

📈 Training and Validation Visualization

The notebook visualizes the model's training progress using the training history.

The curves can be used to observe:

Training accuracy
Validation accuracy
Training loss
Validation loss

These plots help understand how the model behaves during training and whether there are signs of overfitting.

🧪 Key Learnings

This project helped understand the complete basic workflow of an ANN:
Dataset
   ↓
Explore Images
   ↓
Normalize Data
   ↓
Flatten Images
   ↓
Build ANN
   ↓
Compile Model
   ↓
Train Model
   ↓
Generate Predictions
   ↓
Evaluate Accuracy
   ↓
Visualize Training

Important concepts covered
Image data representation
Pixel values
Data normalization
Flattening images
Dense layers
Neurons
ReLU activation
Softmax activation
Multiclass classification
Sparse categorical cross-entropy
Adam optimizer
Model training
Prediction using argmax
Training/validation curves
Test-set evaluation


🧩 Complete Project Workflow
                 MNIST DATASET
                       ↓
          ┌────────────────────────┐
          │ 60,000 Training Images │
          │ 10,000 Test Images     │
          └────────────────────────┘
                       ↓
                28 × 28 Images
                       ↓
              Normalize / 255
                       ↓
                  Flatten
                       ↓
                784 Features
                       ↓
              Dense Layer (128)
                       ↓
                    ReLU
                       ↓
               Dense Layer (10)
                       ↓
                   Softmax
                       ↓
              Class Probabilities
                       ↓
                   argmax()
                       ↓
              Predicted Digit
                       ↓
                Model Evaluation
                       ↓
              ~97.85% Accuracy

📁 Project Structure
handwritten-digit-classification-ann/
│
├── digit-image-classification-praveer-singh.ipynb
├── README.md
└── requirements.txt

👨‍💻 Author

Praveer Singh

B.Tech CSE
MNNIT Allahabad



