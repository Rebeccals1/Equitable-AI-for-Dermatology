# Equitable-AI-for-Dermatology 
### Skin Lesion Classification with EfficientNetB4

## Overview
This project uses **EfficientNetB4** to classify 20 types of medically annotated skin lesions. The goal is to aid in early and accurate diagnosis using deep learning techniques and high-resolution dermatoscopic images.

---

## Technologies Used

This project was likely developed using the following tools and libraries:

* **Python:** The primary programming language for machine learning development.
* **Jupyter Notebook:** Used for interactive development, analysis, and generating the report.
* **EfficientNet:** The core neural network architecture utilized in the project.
* **TensorFlow / PyTorch:** (Likely one of these) Popular deep learning frameworks for building and training the model.

### Model Architecture

- **Base Model**: `EfficientNetB4` (pretrained on ImageNet)  
- **Custom Layers**: GlobalAveragePooling2D → Dense(Softmax)  
- **Loss Function**: Categorical Crossentropy  
- **Optimizer**: Adam  
- **Input Shape**: 380x380 RGB  
- **Class Weights**: Applied to handle class imbalance

---

## Model Performance: F1-Score Summary

The model demonstrates strong classification capabilities across a variety of skin conditions. Below is a breakdown of performance using F1-score, a balance between precision and recall.

---

### Overall Averages

- **Macro F1-Score**: `0.64`  
  (Treats all classes equally, useful for imbalanced datasets)

- **Micro F1-Score**: `0.62`  
  (Weighted by class frequency, reflects overall performance)

---

### Top 3 Performing Classes (by F1-Score)

| Class                 | F1-Score |
|-----------------------|----------|
| Folliculitis          | 0.87     |
| Dyshidrotic Eczema    | 0.86     |
| Kaposi Sarcoma        | 0.83     |

These classes showed high precision and recall, making them the most accurately predicted.

---

### Bottom 3 Performing Classes (by F1-Score)

| Class                   | F1-Score |
|-------------------------|----------|
| Actinic Keratosis       | 0.45     |
| Seborrheic Keratosis    | 0.52     |
| Acne                    | 0.64     |

Lower F1-scores suggest the model struggled with consistent prediction, possibly due to class imbalance or visual overlap with other conditions.

---

## Overall Result Summary

This project fine-tuned **EfficientNetB4** on a multi-class skin lesion dataset comprising 21 conditions. The model was trained on 4,000+ images and evaluated on 1,700 test images.

- 📊 **Final Test Accuracy**: **61.9%**
- 🎯 **Macro F1-Score**: **0.64**
- ⚖️ **Cohen’s Kappa Score**: **0.61** (moderate agreement beyond chance)
- 🧪 **Training Time**: ~30 epochs (~4 minutes per epoch)
- 📉 **Early stopping** and **class weights** were used to mitigate overfitting and class imbalance.

The model shows **strong performance** on several classes (e.g., folliculitis, dyshidrotic eczema), but **struggles with imbalanced or visually similar conditions** like acne and actinic keratosis. Grad-CAM visualizations and confusion matrix analysis are suggested for deeper insight.

This model forms a solid baseline for further improvements, clinical exploration, or deployment in dermatology-related tools.

---

## Running the Notebook with Jupyter

To explore or reproduce this project, use the provided notebook:

📄 `T11_EfficientNet_v10_60Percent.ipynb`


### 1. Install Jupyter (if not already installed)

```bash
pip install notebook
```
Or install all dependencies:
```bash
pip install -r requirements.txt
```
### 3. Run the Notebook Cells
- Run cells one by one using Shift + Enter
- Ensure dataset paths and environment variables are set properly
- The notebook handles preprocessing, model training, evaluation, and prediction steps

You can also open the notebook directly in VS Code with the Jupyter extension, or upload it to Google Colab for GPU access.

---

## License
This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.
