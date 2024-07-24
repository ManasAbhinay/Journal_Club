# Journal_Club

# CheXNet: Radiologist-Level Pneumonia Detection on Chest X-Rays with Deep Learning

## Introduction
Pneumonia is a major cause of morbidity and mortality worldwide. CheXNet aims to provide an automated, accurate, and efficient method for pneumonia detection using deep learning techniques on chest X-ray images.

## Motivation
Traditional diagnostic methods rely heavily on radiologist expertise, which can vary significantly. Access to skilled radiologists is limited in many regions, leading to missed or delayed diagnoses. The appearance of pneumonia in X-ray images is often vague, can overlap with other diagnoses, and can mimic many other benign abnormalities. These challenges highlight the need for an automated diagnostic tool like CheXNet.

## Problem Statement
The pneumonia detection task is a binary classification problem. The input is a frontal-view chest X-ray image, and the output is a binary label indicating the absence or presence of pneumonia.

## CheXNet Model
- **Architecture**: 121-layer Dense Convolutional Network (DenseNet)
- **Input**: Chest X-ray image
- **Output**: Probability of pneumonia along with a heatmap localizing the areas
- **Key Features**: Based on Dense Connections and Batch Normalization. The loss function is optimized for the sum of unweighted binary cross entropy losses.

## Training Data
The ChestX-ray14 dataset was used, containing 112,120 frontal-view X-ray images of 30,805 unique patients. The dataset was split into training, validation, and test sets, with no patient overlap between the sets. Images were downscaled to 224×224 and normalized before inputting into the network. Training data was augmented with random horizontal flipping.

## Achievements
CheXNet outperforms the best published results on all 14 pathologies in the ChestX-ray14 dataset. It localizes pathologies using Class Activation Maps, which highlight the areas of the X-ray that are most important for making a particular pathology classification.

## Limitations
1. Only frontal radiographs were used, while lateral views can be necessary for accurate diagnosis.
2. The model and radiologists did not have access to patient history, which can aid in diagnosis.
3. Diagnoses can be less accurate without considering the patient's clinical history and additional imaging views.

## Conclusion
CheXNet demonstrates significant potential in automating the detection of pneumonia from chest X-rays. While there are limitations, the model's performance highlights the importance and feasibility of using deep learning in medical imaging.

## References
- Wang, Xiaosong, et al. "ChestX-ray8: Hospital-scale chest X-ray database and benchmarks on weakly-supervised classification and localization of common thorax diseases." arXiv preprint arXiv:1705.02315 (2017).
- Huang, Gao, et al. "Densely connected convolutional networks." Proceedings of the IEEE conference on computer vision and pattern recognition. 2017.
- Kingma, Diederik P., and Jimmy Ba. "Adam: A method for stochastic optimization." arXiv preprint arXiv:1412.6980 (2014).
- Ioffe, Sergey, and Christian Szegedy. "Batch normalization: Accelerating deep network training by reducing internal covariate shift." International Conference on Machine Learning. PMLR, 2015.
