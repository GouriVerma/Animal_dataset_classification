## Overview
This project aims to apply one vs rest classification on dataset of 90 categories of animals by using custom CNN model. The model is evaluated based on the 3 fold cross validation technique.

<br>

## Dataset Preparation
1. Initially, a dictionary is made by the help of pathlib library which contains each category as key and list of paths of images as value. files_dict looks like {category: list of paths of the images corresponding to that category}. Also, label_dict is made to store category as key and corresponding index as value.
2. The data is then restructured to form two arrays X and y, where X contains the correspoding tensor of each image and y contains the labels of each image.
3. For applying one vs rest, 60 images of a particular category is chosen along with 120 images of rest category and model is trained on this dataset.

<br>

## Model
The model here is a custom CNN model with total of 8 layers:

![image](https://github.com/GouriVerma/Animal_dataset_classification/assets/122892114/6fcdd180-8e39-434c-bb54-5ae55ed8a724)

<br>

## Model performance on normal train, test split
Model is evaluated on normal train test split by keeping test size to be equal to 0.3. The model was trained for 50 epochs with a batch size of 32 having a callback function related to maximum validation accuracy. The maximum accuracy obtained is close to 100% with validation accuracy as 77.78% The training and validation accuracies trend is as follows:

![image](https://github.com/GouriVerma/Animal_dataset_classification/assets/122892114/db3c6504-172e-4e8f-9c10-93ec64ba136f)

The evaluation of model on test dataset is

![image](https://github.com/GouriVerma/Animal_dataset_classification/assets/122892114/9134233e-87cb-4b03-a26c-cbdbe6f0b1a1)

The classification report is as follows with overall 78% precision and 68% recall.

![image](https://github.com/GouriVerma/Animal_dataset_classification/assets/122892114/a583c585-990c-4a1b-aca4-bc4a7d6853aa)

<br>


## 3 Fold cross validation
KFold is used from sklearn model_selection module to divide the test and train dataset thrice with different batches and model is trained on each of train dataset and saved as wg_index.keras. The performance of models is as follows

<br>

For first model: Training vs Validation accuracy
![image](https://github.com/GouriVerma/Animal_dataset_classification/assets/122892114/7ee4750a-8354-4939-88a1-f4619c410ca6)

<br>

Classification Report

![image](https://github.com/GouriVerma/Animal_dataset_classification/assets/122892114/d6eb341e-ad31-436b-a4be-31488e825c1b)

<br>

Confusion Matrix

![image](https://github.com/GouriVerma/Animal_dataset_classification/assets/122892114/89e4e389-6374-4cd0-87db-709bda2ef1e9)


For second model: Training vs Validation accuracy
![image](https://github.com/GouriVerma/Animal_dataset_classification/assets/122892114/0ca1cafb-21a0-4c2c-b3e9-19d61a07f140)

<br>

Classification Report

![image](https://github.com/GouriVerma/Animal_dataset_classification/assets/122892114/3dd6bd75-228b-4681-89b3-cf46672ffeb8)


<br>

Confusion Matrix

![image](https://github.com/GouriVerma/Animal_dataset_classification/assets/122892114/cd75bab0-5e76-42a9-9c2d-121ab8e09a89)

<br>

For third model: Training vs Validation accuracy
![image](https://github.com/GouriVerma/Animal_dataset_classification/assets/122892114/cad7be69-5147-40ca-a789-3eb786b38047)

<br>

Classification Report

![image](https://github.com/GouriVerma/Animal_dataset_classification/assets/122892114/ba3497da-c5f5-475b-9277-a2d8f326bd92)



<br>

Confusion Matrix

![image](https://github.com/GouriVerma/Animal_dataset_classification/assets/122892114/74d57828-fc3b-4317-8d41-2a19c328b288)








