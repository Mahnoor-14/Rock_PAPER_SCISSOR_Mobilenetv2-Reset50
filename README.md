# Rock_PAPER_SCISSOR_Mobilenetv2-Reset50
This project compares two popular pretrained CNN architectures—MobileNetV2 and ResNet50—using transfer learning on the Rock-Paper-Scissors image classification dataset. The goal is to evaluate trade-offs in accuracy, training speed, model size, and inference efficiency when applying these models to a small-scale classification task.

# 🧠 Transfer Learning Showdown: MobileNetV2 vs ResNet50

## 🎯 Objective

A comparison was conducted between two pretrained CNN architectures—**MobileNetV2** and **ResNet50**—by applying transfer learning to the Rock-Paper-Scissors image classification dataset. The objective was to evaluate the models based on accuracy, training efficiency, model size, and practical deployment considerations.

## 📊 Model Comparison

| Feature | MobileNetV2 | ResNet50 |
|--------|-------------|----------|
| Input Size | 224×224 | 224×224 |
| Parameters | ~3.5M | ~25.6M |
| Depth | ~88 layers | ~50 layers |
| ImageNet Top-1 Acc | ~71.3% | ~75.2% |
| Model Size | ~14MB | ~98MB |
| Inference Speed | Fast | Slower |

## 🧪 Dataset

The [Rock-Paper-Scissors dataset](https://www.tensorflow.org/datasets/catalog/rock_paper_scissors) from `tensorflow_datasets` was used.
![image](https://github.com/user-attachments/assets/0439e360-b629-40f6-90c9-b76384bcf2a9)


- It was preprocessed by resizing all images to **224×224**.
- Model-specific normalization was applied using `preprocess_input()`.

## ⚙️ Workflow

The following steps were followed for both models:
1. Data preprocessing
2. Pretrained base model loading (without top)
3. Freezing of base layers
4. Addition of a custom classifier head
5. Initial training
6. Fine-tuning of top layers

EarlyStopping and ReduceLROnPlateau were employed to optimize training.

## 📈 Results

| Model        | Validation Accuracy | Parameters | Model Size | Notes                    |
|--------------|---------------------|------------|------------|--------------------------|
| MobileNetV2  | 1.00                | ~3.5M      | ~14MB      | Fast inference           |
| ResNet50     | 1.00                | ~25.6M     | ~98MB      | More accurate, heavier   |

Both models achieved perfect validation accuracy, though **ResNet50** may offer better generalization on more complex datasets.

#repository
├── mobilenetv2_rps_model.h5 # Saved MobileNetV2 model
├── resnet50_rps_model.h5 # Saved ResNet50 model
├── notebook.ipynb # Complete training notebook
├── README.md # Project overview
