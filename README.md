# Motor-Thermal-Anomaly-Detection
AI-based electric motor anomaly classification from thermal images using Simple CNN and fine-tuned MobileNetV2.

# Motor Thermal Anomaly Detection

AI-based electric motor anomaly classification from thermal images using
Simple CNN and fine-tuned MobileNetV2.

## Overview

This project presents an artificial intelligence approach for classifying
electric motor abnormalities from thermal images.

Two deep learning models are evaluated:

- Simple Convolutional Neural Network (Simple CNN)
- MobileNetV2 with transfer learning and fine-tuning

The task is formulated as binary classification:

- Normal
- Abnormal

## Dataset

The experiments use the following publicly available thermal image dataset:

Najafi, M., Baleghi, Y., and Mirimani, S. M.  
"Thermal image of equipment (Induction Motor) + 40 Ground Truths added."  
Mendeley Data, Version 3, 2023.

DOI: 10.17632/m4sbt8hbvk.3

The dataset is not included in this repository.

Users should download the dataset from Mendeley Data and configure
`DATASET_ROOT` in the notebook before running the experiments.

## Models

### Simple CNN

A Simple CNN is used as the baseline model.

### MobileNetV2

MobileNetV2 pretrained on ImageNet is used for transfer learning.
The final layers of the backbone are subsequently fine-tuned for
thermal image classification.

## Experimental Results

| Metric | Simple CNN | MobileNetV2 Fine-tuned |
|---|---:|---:|
| Accuracy | 0.6607 | **0.9821** |
| Macro Precision | 0.5870 | **0.9000** |
| Macro Recall | 0.8173 | **0.9904** |
| Macro F1 | 0.5364 | **0.9396** |
| Balanced Accuracy | 0.8173 | **0.9904** |
| MCC | 0.3322 | **0.8858** |
| ROC-AUC | 0.6346 | **1.0000** |
| PR-AUC | 0.9685 | **1.0000** |
| Abnormal Recall | 0.6346 | **0.9808** |
| Abnormal False Negatives | 19 | **1** |

The fine-tuned MobileNetV2 achieved an accuracy of 98.21%.
It correctly classified 51 of 52 abnormal test images.
Only one abnormal sample was misclassified as normal.

## Google Colab

The complete experiment is provided in:

`Motor_Thermal_Predictive_v2.ipynb`

Open the notebook directly from GitHub using the **Open in Colab** button.

## Running the Experiment

1. Download the dataset from Mendeley Data.
2. Upload or copy the dataset to Google Drive.
3. Open `Motor_Thermal_Predictive_v2.ipynb` in Google Colab.
4. Mount Google Drive.
5. Set `DATASET_ROOT` to the dataset location.
6. Run the notebook cells sequentially.

## Requirements

The main Python libraries used in this project include:

- TensorFlow
- NumPy
- Pandas
- Matplotlib
- scikit-learn

## Citation

If you use the dataset, please cite:

Najafi, M., Baleghi, Y., and Mirimani, S. M. (2023).
Thermal image of equipment (Induction Motor) + 40 Ground Truths added.
Mendeley Data, Version 3.
DOI: 10.17632/m4sbt8hbvk.3

Related publication:

M. Najafi, Y. Baleghi, S. A. Gholamian, and S. M. Mirimani,
"Fault Diagnosis of Electrical Equipment through Thermal Imaging and
Interpretable Machine Learning Applied on a Newly-Introduced Dataset,"
6th International Conference on Signal Processing and Intelligent Systems
(ICSPIS), 2020.
DOI: 10.1109/ICSPIS51611.2020.9349599

## License

This repository is distributed under the MIT License.

The dataset is subject to its original license and citation requirements.
