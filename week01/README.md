MNIST Digit Classification with PCA and Random Forest
This project demonstrates how to classify handwritten digits from the MNIST dataset using a Random Forest classifier, incorporating Principal Component Analysis (PCA) for dimensionality reduction to optimize training time and potentially improve model performance.

Project Description
The MNIST dataset is a classic benchmark in machine learning, consisting of 70,000 grayscale images of handwritten digits (0-9). Each image is 28x28 pixels, resulting in 784 features. Training a classification model on this high-dimensional data can be computationally intensive.

This notebook addresses this challenge by:

Loading and Preprocessing the MNIST dataset.
Applying Principal Component Analysis (PCA) to reduce the dimensionality of the data while retaining a significant portion of its variance.
Training a Random Forest Classifier on the PCA-reduced data.
Evaluating the model's performance.
Setup and Dependencies
To run this notebook, you need to have Python and the following libraries installed. You can install them using pip:

pip install numpy pandas scikit-learn matplotlib seaborn
Code Explanation
The notebook follows these main steps:

Load Data: Fetches the MNIST dataset using fetch_openml from sklearn.datasets.
Data Scaling: Standardizes the pixel values (features) using StandardScaler to ensure PCA performs optimally.
Dimensionality Reduction (PCA): Applies PCA to reduce the 784 features. We configure PCA to retain components that explain 95% of the total variance. This significantly reduces the number of features (e.g., from 784 to around 332 components, as observed).
Train-Test Split: Divides the dataset into training and testing sets (80% train, 20% test).
Model Training: Initializes and trains a RandomForestClassifier with 100 estimators on the PCA-reduced training data.
Prediction and Evaluation: Makes predictions on the test set and evaluates the model's accuracy, precision, recall, and F1-score using accuracy_score and classification_report.
Visualization: Plots the cumulative explained variance by principal components to visually confirm the effect of PCA.
Expected Output
Upon running the notebook, you will see:

The original number of features and the reduced number of features after PCA.
A plot showing the cumulative explained variance, indicating how many principal components are needed to capture 95% of the data's variance.
The model's accuracy on the test set.
A detailed classification report, including precision, recall, and F1-score for each digit class.
