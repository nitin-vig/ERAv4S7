
# Cifar10 dataset Model Iterations – ERA v4 S7

This repository documents the iterative development of a CNN-based model for the CIFAR10 dataset.  
The goal was to acheive 85% test accuracy with less than 200k parameters.  

---

## Iteration 1
- **Target**:  
  - Start with a padding of 16 so that cutout of 16 X 16 can be applied
  - Build the initial model and applied transformations -CoarseDropout,HorizontalFlip,ShiftScaleRotate.  
  - Stay below **200k parameters**.  
  - Achieve ~**85% train/test accuracy** consistently within 50 epochs.  
  - No Fully Connected layers.
  - No Maxpooling- use stride instead to downsize the image.  

- **Results**:  
  - Parameters: **120,276**  
  - Train Accuracy: **62.1%**  
  - Test Accuracy: **85.1%**
  - High Receptive Field.

- **Analysis**:  
  - Train accuracy still has scope for improvement.  
  - Signs of **underfitting** (test > train accuracy) due to transformations.  

- **Notebook**: [Baseline Version](https://github.com/nitin-vig/ERAv4S7/blob/main/CIFAR10v1.ipynb)

---

## Iteration 2
- **Target**:  
  - Use **Depthwise Convolution** in atleast one layer and analyze the impact.  

- **Results**:  
  - Parameters: **116,308** (achieved mainly via **Global Average Pooling**)  
  - Accuracy: **>84.3%** after 10 epochs  

- **Analysis**:  
  - **Depthwise Convolution** reduced the number of parameters significantly and dropped the test accuracy slightly. 

- **Notebook**: [Impact of Depthwise Convolution ](https://github.com/nitin-vig/ERAv4S7/blob/main/CIFAR10v2.ipynb)

---
