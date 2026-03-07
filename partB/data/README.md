# Dataset Information

## Dataset Source

This project does not use an external dataset file.  
Instead, the dataset is generated programmatically using the `make_classification` function from the `scikit-learn` library.

## Dataset Generation

The dataset is created in the notebooks using the following parameters:

- Number of samples: 100  
- Number of features: 20  
- Informative features: 2  
- Redundant features: 2  
- Classes: 2 (binary classification)

Example code used in the notebooks:

```python
from sklearn.datasets import make_classification

X, y = make_classification(
    n_samples=100,
    n_features=20,
    n_informative=2,
    n_redundant=2,
    n_classes=2,
    random_state=42
)
```

A fixed random seed (`random_state=42`) is used to ensure that the dataset remains identical across runs and is fully reproducible.


## How the Dataset Is Used in the Notebooks

The same dataset generation process is used across multiple notebooks in this project.

### `task_2_1.ipynb`

- Generates the synthetic dataset.  
- Performs the train-test split.  
- Documents the dataset selection and preprocessing steps.  

### `task_2_2.ipynb`

- Uses the dataset to reproduce the ranked feature idea from the CW-SVM paper.  
- Trains two models:  
  - A baseline linear SVM.  
  - A modified model where selected features are scaled to simulate expert-ranked features.  

### `task_2_3.ipynb`

- Uses the dataset to evaluate model performance.  
- Computes classification accuracy.  
- Generates a confusion matrix visualization saved in the `partB/results/` folder.  

### `task_3_1.ipynb`

- Uses the same dataset for the ablation study.  
- Compares the full ranked-feature method against simplified versions where ranking information is removed or reduced.  

### `task_3_2.ipynb`

- Uses the dataset to demonstrate a failure scenario.  
- Introduces an incorrect feature ranking to show how the model may behave when expert knowledge is inaccurate.  



## Why This Dataset Was Used

The synthetic dataset allows controlled experimentation with feature importance. This makes it suitable for demonstrating the main idea of the CW-SVM method, where expert-ranked features influence the classifier.

Although the dataset is much smaller and simpler than the high-dimensional text datasets used in the original paper (such as biomedical document screening datasets), it is sufficient to demonstrate how feature-level constraints can influence model behaviour.



## Reproducibility

Because the dataset is generated programmatically and a fixed random seed is used, the dataset can be reproduced exactly by running the notebooks.

No manual download or preprocessing steps are required.
