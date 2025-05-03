# Pneumonia Detection Using Deep Learning 🫁

This project uses **transfer learning** with pre-trained CNN models (ResNet50, VGG16, and InceptionV3) to classify chest X-ray images as either **Pneumonia** or **Normal**.

## 🧠 Models & Techniques

This project leverages **transfer learning** using the following models pre-trained on ImageNet:

### 1. ResNet50
- **Used for:** Feature extraction
- **Layers:** Frozen
- **Classifier:** Custom head added on top for pneumonia classification

### 2. VGG16
- Same technique as ResNet50: freeze base layers and train a custom classifier

### 3. InceptionV3
- Again, ImageNet weights used; custom classification head trained for this specific task

Transfer learning allows the model to benefit from previously learned visual features, improving performance even with a smaller dataset.

## 🧪 Data Preprocessing

1. **Image Resizing:**
   - All chest X-ray images are resized to 256x256 pixels to match the input shape required by CNN models.

2. **Normalization:**
   - Pixel intensity values are scaled from the range [0, 255] to [0, 1] to ensure faster convergence during training.

3. **Data Augmentation:**
   - Applied random transformations such as horizontal flipping, zooming, and shearing using `ImageDataGenerator` to:
     - Reduce overfitting
     - Improve generalization

4. **Splitting:**
   - Used `validation_split` within the image generator or separate folders for training and validation data to monitor performance during training.

5. **Label Preparation:**
   - Images are categorized into two folders: `NORMAL` and `PNEUMONIA`, and labels are automatically inferred.

## 📊 Model Evaluation

Performance is evaluated using:
- Accuracy
- Precision, Recall, F1-Score
- Confusion Matrix
- Training/validation loss & accuracy plots

## 🛠️ Libraries Used

- TensorFlow
- Keras
- NumPy
- Pandas
- Matplotlib

## 🚀 How to Run

1. **Clone the repository:**
   ```bash
   git clone https://github.com/Srinidhi2274/pneumonia-detection.git
   cd pneumonia-detection
   ```

2. **(Optional) Create a virtual environment:**
   ```bash
   python -m venv venv
   source venv/bin/activate      # Windows: venv\Scripts\activate
   ```

3. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

4. **Run the notebook:**
   ```bash
   jupyter notebook pneumonia_predicton.ipynb
   ```

## 🔒 Permissions

This repository is **read-only** for the public. Only the owner can push changes. To suggest improvements, open an issue or submit a pull request.

## 📎 License

This project is released under the MIT License.
