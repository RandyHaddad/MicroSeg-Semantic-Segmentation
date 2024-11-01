# MicroSegQ+ Semantic Segmentation Tool

For detailed methodology and technical details, please refer to the full paper: [Accelerated Semantic Segmentation of Additively Manufactured Metal Matrix Composites](https://github.com/RandyHaddad/MicroSeg-Semantic-Segmentation/blob/main/MicroSegQ%2B.pdf) (*Expert Systems With Applications*, 251, 2024). This work is a collaborative effort by Mutahar Safdar, Yi Fan Li, and Randy El Haddad, with equal contributions listed by seniority.

### Primary Contributions: Randy El Haddad

Randy's work was foundational in multiple facets of this project, spanning data preprocessing, deep learning model adaptation, and novel augmentation techniques for enhanced performance in class-imbalanced datasets. His contributions include:

1. **Dataset Preparation and Preprocessing**:
   - Randy led the preprocessing pipeline, transforming raw metallographic images into high-quality, standardized inputs for model training.
   - Applied advanced filtering techniques to ensure optimal contrast and sharpness in images, improving feature distinguishability and model learning outcomes.
   - Developed a consistent labeling and annotation workflow to create reliable ground truths, particularly for challenging MMC features like porosities and reinforcement particles.
   - Implemented methods for artifact reduction, including adaptive background removal and noise reduction, to prevent misclassification in the segmentation model.

2. **Transfer Learning and Deep Learning Model Optimization**:
   - Randy fine-tuned both convolutional neural networks (CNNs) and Vision Transformers (ViTs) specifically for MMC data, optimizing architectures like U-Net++ and Segformer.
   - Utilized transfer learning by adapting models pretrained on large datasets to MMC microstructure segmentation, carefully tuning model layers to capture the specific texture and structure of metallographic images.
   - His work on model selection and hyperparameter tuning significantly improved convergence rates and segmentation accuracy, allowing the models to generalize effectively across variations in MMC microstructures.

3. **Zoom-in Augmentation**:
   - Randy pioneered the *Zoom-in Augmentation* technique, which selectively amplifies underrepresented classes, particularly rare defects and intricate structural features. This targeted augmentation is essential for addressing class imbalances typical in MMC datasets.
   - By selectively zooming in on minority classes, this technique provided the model with a balanced training distribution, enhancing robustness and accuracy on challenging segmentation tasks where defects and irregularities are sparse.

4. **Model Fusion Strategy**:
   - Designed and implemented a model fusion strategy that paired CNN and ViT model predictions, allowing each model to contribute its strengths. This approach provided superior performance in detecting both large-scale background elements and smaller, minority classes, achieving a balanced and accurate segmentation output.
   - Established a weighted voting system for model fusion, leveraging each model's strengths to achieve reliable predictions on class imbalances, thereby refining segmentation quality across diverse classes.

5. **Quantification and Analysis in MicroSegQ+**:
   - Randy contributed significantly to integrating quantification metrics in MicroSegQ+, allowing real-time feedback on class distribution and feature size in segmented images.
   - Developed the system for exporting segmentation masks and quantification reports, enabling seamless data interpretation and further analysis within industry-standard software.


---

## Overview

**MicroSegQ+** is a tool designed to expedite the segmentation and quantification of microstructures in additively manufactured metal matrix composites (MMCs). Leveraging both convolutional and transformer-based models, it delivers high accuracy in segmenting complex microstructures with imbalanced classes, providing a user-friendly interface for industrial deployment.

### Key Contributions

1. **Dataset Preparation**: 
   - Two custom-annotated datasets for Direct Energy Deposition (DED) based MMCs.
   - *Zoom-in Augmentation* to improve segmentation accuracy for minority classes (e.g., porosities).

2. **Deep Learning Models**:
   - **U-Net++** and **DeepLabv3+** convolutional models for large-scale features.
   - **Segformer** (transformer-based model) for minority class segmentation in class-imbalanced datasets.
   
3. **Fusion Strategy**:
   - Fusion of convolutional and transformer-based model predictions, balancing strengths to enhance accuracy, particularly for minority classes.
   
4. **MicroSegQ+ Tool**:
   - GUI interface for model selection, image segmentation, quantification, and prediction fusion.
   - Lightweight, standalone executable for industrial use, capable of handling large metallographic images.

---

## Key Features

1. **Data Processing and Augmentation**
   - Custom dataset annotations and preparation techniques.
   - Innovative *Zoom-in Augmentation* for improved class balance in imbalanced datasets.

2. **Modeling and Fusion Strategy**
   - Integration of multiple deep learning architectures to handle unique MMC microstructure segmentation challenges.
   - Fusion method allows enhanced prediction performance for complex, industrial metallographs.

3. **MicroSegQ+ Tool**
   - **Modular GUI** with options for model loading, image segmentation, quantification, and fusion.
   - Real-time quantification and visualization of segmentation results.

---

## Usage

### Installation

MicroSegQ+ requires Python 3.8 or higher and the following libraries:
- `PyTorch`
- `Transformers` (from Hugging Face)
- `Tkinter` (for GUI)
- `PyInstaller` (for packaging the executable)

### Running the Tool

1. **Load Models**: Select the pre-trained models you wish to use.
2. **Segment Images**: Load your image, segment with the selected model(s), and visualize results.
3. **Quantify Segmentation**: Obtain quantitative data (e.g., pixel counts) for each segmented class.
4. **Fuse Predictions** (optional): Combine predictions from two different models for optimal performance on complex images.

---

## Model Architectures

The models utilized include:
- **Convolutional Models**: U-Net++ and DeepLabv3+ for large-scale feature segmentation.
- **Transformer Model**: Segformer for improved performance on minority classes, especially in class-imbalanced datasets.

Each model has been optimized and validated on custom MMC datasets, demonstrating high accuracy across multiple class distributions.

---

## Results

MicroSegQ+ has been evaluated on industrial datasets and benchmarked against state-of-the-art methods, achieving notable performance improvements, particularly on imbalanced classes. Key metrics (IoU, F1 score) are provided in the full paper.

---

## Future Directions

- Expand MicroSegQ+ to support additional model architectures and industry-specific datasets.
- Incorporate fine-tuning and model retraining capabilities within the GUI.
- Develop a no-code ML pipeline to streamline the integration of custom datasets.

## License and Acknowledgements

MicroSegQ+ is released under the [MIT License](LICENSE). We acknowledge the support from Digital Research Alliance of Canada and the AI-SLAM consortium for their valuable resources and funding support.

---
