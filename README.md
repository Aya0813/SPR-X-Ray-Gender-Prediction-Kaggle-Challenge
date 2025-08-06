# SPR X-Ray Gender Prediction Challenge

This repository contains my work for the **SPR X-Ray Gender Prediction Kaggle Challenge**, completed during the [**2023 Bumblekite Machine Learning Summer School in Health, Care, and Biosciences**](https://www.bumblekite.co/summer-school-23) at **ETH Zurich**.

The challenge was presented by [**Dr. Judy Gichoya (Emory University)**](https://winshipcancer.emory.edu/profiles/gichoya-judy.php), keynote lecturer at the summer school, as part of her tutorial. She provided participants with three tasks based on their experience level: beginner, intermediate, and advanced. The **SPR X-Ray Gender Prediction Kaggle Challenge** was the **advanced task**, focused on predicting the gender of patients from chest X-ray images.

This repository contains two versions of the implementation:

- The original version was written in **July 2023**, when I was just getting started with Machine Learning. It represents my early attempt at working with medical imaging data and building CNN models using PyTorch on a Mac M1 GPU. Despite computational limitations, I successfully developed a Convolutional Neural Network (CNN) model and achieved an accuracy of **0.89**. This version can be found in the [`archive/`](archive/) folder.

- The updated version was completed nearly two years later (**August 2025**), after gaining significant experience in Machine Learning. I revisited and refined the original project, applying better training practices, architecture improvements, and evaluation techniques. The revised implementation and final report can be found in the **[main directory](./)** of this repository.


## 🗂️ Project Summary

- **Challenge**: [SPR X-Ray Gender Prediction](https://www.kaggle.com/competitions/spr-x-ray-gender)
- **Dataset**: 22,449 chest X-ray images (10,702 training, 11,747 testing)
- **Task**: Predict gender from medical images
- **Deep Learning Framework**: PyTorch
- **Development Environment**: Jupyter Notebook
- **Hardware**: MacBook Pro (13-inch, M1, 2020) using MPS (Apple's Metal Performance Shaders, being Apple GPU architecture)
- **Outcome**: Validation accuracy of 0.89
  
## 📁 Repository Contents

- `notebook_final.ipynb`: The final version of the notebook, containing the full implementation, updated training pipeline, evaluation metrics, and inference code.
- `report_final.pdf`: A report summarizing the model development process, tuning experiments, and final results.

- `archive/`: Contains the original version of this project from **July 2023**, including:
  - `notebook_archive.ipynb`: The initial notebook developed during the Bumblekite Summer School.
  - `report_archive.pdf`: The original project report documenting early challenges and learning outcomes.


- `results/`: Contains the final results:
  - `predictions.csv`: Soft probability scores for the test set, as required by the competition submission format. These scores represent the model's confidence that each image belongs to the male class (1), and are used by the Kaggle platform to compute the AUC metric.
  - `*.png`: Figures generated during training and evaluation (e.g., loss curves, confusion matrix).


## 🎓 Key Learnings

This project was a valuable introduction to Machine Learning for medical imaging and resource-aware deep learning workflows. I gained experience in:

- Preprocessing and normalizing imaging datasets  
- Building and debugging CNN architectures  
- Learning to leverage Apple's M1 GPU with PyTorch.
- Troubleshooting environment and compatibility issues  
- Tuning hyperparameters and interpreting performance metrics 

## 📊 Results Overview

The chosen final training configuration used a learning rate of `0.01` with `20` epochs and included dropout for regularization. It achieved the following metrics on the validation set:
- Accuracy: 89.3%
- Precision: 93.1%
- Recall: 80.6%
- F1-score: 86.4%

Below are the learning curve and the confusion matrix evaluation results from the final model:

### 📉 Learning Curve

The learning curve shows stable convergence:
![Final Loss Curve](results/final-lr-0.01-dropout-added-epoch-20.png)

### 💡 Confusion Matrix (Validation Set)

Since the challenge test labels are hidden, performance was assessed on the validation set. The confusion matrix below is based on predictions from the final epoch:

![Confusion Matrix](results/final-confusion-matrix.png)

Despite strong overall accuracy, the model shows slightly lower performance in identifying male images, indicating room for improvement in balancing feature representation across classes.
