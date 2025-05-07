# Visual Sentiment Analysis with CNNs: Struggles in Capturing Emotional Cues in Disaster Images

This repository accompanies the study **"Visual Sentiment Analysis with CNNs: Struggles in Capturing Emotional Cues in Disaster Images"**, which investigates the limitations of current deep learning approaches in extracting emotions from disaster-related imagery.

📄 **[Read the Paper](https://github.com/XaviRS95/Visual-Sentiment-Analysis-with-CNNs-Struggles-in-Capturing-Emotional-Cues-in-Disaster-Images)**

## 🚨 Problem Statement

While text-based sentiment analysis is well-established, visual sentiment analysis (VSA), especially in disaster contexts, remains a challenge due to:
- Subjectivity in emotional interpretation
- Lack of clear visual symmetry
- Complexity of emotional cues in disaster imagery

## 🎯 Objective

To evaluate the performance and limitations of state-of-the-art CNN architectures in classifying emotions from disaster images, using both **binary** and **multi-label** classification, and to analyze feature importance through **Grad-CAM**.

## 🧠 Key Contributions

1. **Model Benchmarking**  
   Evaluated CNNs: ResNet50, VGG19, InceptionV3, EfficientNetV2S on binary and multi-label tasks using disaster images.

2. **Early Fusion Architecture**  
   Combined object-level (ImageNet) and scene-level (Places365) features to improve emotional representation.

3. **Preprocessing and Regularization**  
   Applied oversampling, undersampling, data augmentation, L1/L2 regularization, dropout, and label powerset transformation.

4. **Grad-CAM Visualization**  
   Revealed that CNNs often focus on irrelevant regions (e.g., backgrounds), ignoring emotionally salient cues.

5. **Roadmap for Future Work**  
   Suggested exploring transformers, synthetic data generation (GANs), and advanced multi-label classification methods.

## 📊 Dataset

- **Source**: MediaEval Visual Sentiment Dataset
- **Size**: 3,631 disaster-related images
- **Labels**: Single-label (positive, negative, neutral) and multi-label (joy, sadness, fear, etc.)
- **Preprocessing**: Images resized to 224x224, normalized, and augmented

## 🔍 Models & Training

- **Pretrained CNNs**:
  - VGG19
  - ResNet50
  - InceptionV3
  - EfficientNetV2S
- **Fusion Strategy**: Early fusion of ImageNet + Places365 features
- **Optimizers Tested**: SGD, Adam, AdamW
- **Best Results**: Achieved through early fusion + Adam optimizer + class balancing

## 📈 Results Summary

| Model           | Binary F1 (Fusion) | Multi-label F1 (Fusion)  |
|-----------------|--------------------|--------------------------|
| ResNet50        | 0.51               | 0.63                     |
| EfficientNetV2S | 0.53               | 0.59                     |
| InceptionV3     | 0.52               | 0.64                     |
| VGG19           | 0.30               | 0.59                     |

> Note: Performance was generally modest, highlighting the difficulty of the task.

| Model            |  Binary F1 (Unimodal) | Multi-Label F1 (Unimodal) |
|------------------|-----------------------|---------------------------|
| ResNet50         | 0.52                  | 0.62                      |
| EfficientNetV2S  | 0.40                  | 0.53                      |
| InceptionV3      | 0.49                  | 0.62                      |
| VGG19            | 0.32                  | 0.56                      |

> 🔍 **Observation**: ResNet50 and InceptionV3 showed more balanced performance across both tasks. EfficientNetV2S excelled in precision but lagged in recall, leading to a lower F1 in binary classification. VGG19 performed poorly in binary tasks.

## 📌 Key Challenges Identified

- Ambiguity and subjectivity of emotion in images
- Lack of specialized, balanced datasets
- Models fail to focus on emotionally relevant regions
- Scene and object-level features both necessary but not sufficient

## 🧭 Future Directions

- Adopt transformer-based architectures (e.g., ViT, Swin)
- Improve dataset quality and size
- Explore GANs for synthetic data generation
- Leverage multi-label classifiers like PrunedSet, Calibrated Label Ranking

## 📎 Citation

```bibtex
@article{romero2025visual,
  title={Visual Sentiment Analysis with CNNs: Struggles in Capturing Emotional Cues in Disaster Images},
  author={Romero, Javier and Ahmad, Kashif},
  journal={Journal Not Specified},
  year={2025},
  note={Submitted for publication},
  url={https://github.com/XaviRS95/Visual-Sentiment-Analysis-with-CNNs-Struggles-in-Capturing-Emotional-Cues-in-Disaster-Images}
}

