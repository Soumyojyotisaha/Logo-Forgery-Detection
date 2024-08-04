# Fake-Logo-Detection

This Fake Logo Detection model helps in detecting the fake and original logos of 15 different brands like Puma, Nike, Starbucks, Adidias, HP, Apple etc. This model is built using CNN architecture and deployed in the web using Flask Framework.

# Fake-Logo-Detection-VIT

![Project Image](https://github.com/Soumyojyotisaha/Logo-Forgery-Detection/blob/main/project.jpg)

# Project Overview

The project comprises three main scripts: `checkfakelogo.py`, `fake_logo_gen.py`, and `trainedmodel.py`. These scripts collectively offer functionalities for logo authenticity detection, fake logo generation, and training a machine learning model for logo classification.

## 1. Logo Authenticity Detection (`checkfakelogo.py`)

### Purpose
This script determines the authenticity of a given logo image using a pre-trained machine learning model.

### Key Steps
1. **Load Trained Model:**
   - Loads a pre-trained machine learning model from the file `trained_model.joblib` using the `joblib` library.

2. **Image Preprocessing:**
   - Defines a function (`preprocess_image`) to load, resize, and normalize pixel values of an image.

3. **Prediction:**
   - Applies the pre-trained model to predict whether the provided logo image is genuine or fake.
   - Prints the raw prediction and a corresponding message.

### Example Usage
Demonstrates the use of the script with an example of a genuine logo image.

## 2. Fake Logo Generation (`fake_logo_gen.py`)

### Purpose
This script generates fake logos by applying rotation and scaling transformations to existing logo images.

### Key Steps
1. **Image Transformation:**
   - Iterates through logo images in a specified folder (`output`) and applies rotation and scaling transformations.
   - Saves the transformed images to a new folder (`genLogoOutput`).

2. **Data Collection:**
   - Collects metadata about the transformed images (filename, brand name, label) and updates a CSV file (`file_mapping.csv`).

### Notes
- The script uses OpenCV (`cv2`) for image processing.

## 3. Model Training (`trainedmodel.py`)

### Purpose
This script trains a Random Forest classifier to classify logos as genuine or fake.

### Key Steps
1. **Load Data:**
   - Reads image data and labels from a CSV file (`file_mapping.csv`) containing information about images and their labels.

2. **Preprocessing:**
   - Defines a function (`preprocess_image`) to read, rotate, and scale images.
   - Creates a feature matrix (`X`) and labels (`y`) by applying preprocessing to each image.

3. **Train-Test Split:**
   - Splits the data into training and testing sets using `train_test_split` from scikit-learn.

4. **Random Forest Classifier:**
   - Creates a Random Forest classifier using a pipeline with a `StandardScaler` for feature scaling.

5. **Model Training:**
   - Trains the classifier using the training data.

6. **Model Evaluation:**
   - Makes predictions on the test set and evaluates the model's accuracy.

7. **Model Persistence:**
   - Saves the trained model to a file (`trained_model.joblib`).

### Example Usage
Demonstrates how to use the trained model for predictions on new data.

## Conclusion

In summary, the project provides tools for logo analysis, including authenticity detection, fake logo generation, and training a machine learning model. The scripts can be used individually or collectively, depending on the user's needs. The README provides clear instructions on how to install, use, and contribute to the project.


