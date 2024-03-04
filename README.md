
## Dataset Preparation
1. Initially, the dataset of images of 5 categories are chosen: "antelope, badger, bat, beer, bee" and a dictionary is by the help of pathlib library which contains each category as key and list of paths of images as value. files_dict looks like {category: list of paths of the images corresponding to that category}. Also, label_dict is made to store category as key and corresponding index as value.
2. The data is then restructured to form two arrays X and y, where X contains the correspoding tensor of each image and y contains the labels of each image.

<br>


## Model
The model here is a custom CNN model with total of 8 layers:
![image](https://github.com/GouriVerma/Animal_dataset_classification/assets/122892114/712f13e1-b821-4f95-b87d-f34bb1af01da)

<br>

## Model performance on normal train, test split
Model is evaluated on normal train test split by keeping test size to be equal to 0.33. The model was trained for 50 epochs with a batch size of 32 having a callback function related to maximum validation accuracy. The maximum accuracy obtained is 97.62% with validation accuracy as 67.78%
The training and validation accuracies trend is as follows:

![image](https://github.com/GouriVerma/Animal_dataset_classification/assets/122892114/eeaf86b7-1942-4f74-9975-2dab7a12a3f7)

<br>

The evaluation of model on test dataset is

![image](https://github.com/GouriVerma/Animal_dataset_classification/assets/122892114/5e5fc5d2-446d-4d72-8a71-c206b670949d)

<br>

The classification report is as follows with overall 68% precision and 68% recall.

![image](https://github.com/GouriVerma/Animal_dataset_classification/assets/122892114/ae1a7d38-75f2-476d-b21c-dba02a3706ff)


<br>

## 3 Fold cross validation
KFold is used from sklearn model_selection module to divide the test and train dataset thrice with different batches and model is trained on each of train dataset and saved as wg_index.keras.
The performance of models is as follows

<br>

For first model:
Training vs Validation accuracy
![image](https://github.com/GouriVerma/Animal_dataset_classification/assets/122892114/48d717ad-3861-47cd-ad96-92ee034a3e98)

Classification Report

![image](https://github.com/GouriVerma/Animal_dataset_classification/assets/122892114/2902d7fd-57f7-4b25-afef-6e5dc19d9bc4)

Confusion Matrix

![image](https://github.com/GouriVerma/Animal_dataset_classification/assets/122892114/fcbaa85e-141e-47f7-b5bc-6f347393d311)

<br>

For second model:

Training vs Validation accuracy

![image](https://github.com/GouriVerma/Animal_dataset_classification/assets/122892114/7f0148b5-42c8-4079-ace2-543581dce8d1)

Classification Report

![image](https://github.com/GouriVerma/Animal_dataset_classification/assets/122892114/97918a0f-aa6f-4ccd-bd2e-74be4415ee15)


Confusion Matrix

![image](https://github.com/GouriVerma/Animal_dataset_classification/assets/122892114/d82fda1c-17fa-4084-ab93-01ffa2e054b1)


<br>

For third model:

Training vs Validation accuracy

![image](https://github.com/GouriVerma/Animal_dataset_classification/assets/122892114/c66bf6ab-673c-4b22-bfc9-a2635159b242)


Classification Report

![image](https://github.com/GouriVerma/Animal_dataset_classification/assets/122892114/018a438f-ff75-471a-b108-596d86cc00a6)


Confusion Matrix

![image](https://github.com/GouriVerma/Animal_dataset_classification/assets/122892114/39eda24f-1c95-4974-bc9a-0c2f9f82712c)


<br>

## Feature Maps of Convolutional layers
The output of each convolutional layer can be accessed by tf.keras.models.Model. There are 4 CNN layers having 2 layers of Conv2D and 2 of MaxPooling2D. The number of filters in the layers are 32, 32, 64 and 64 respectively. The output of each layer's filter are displayed 

![image](https://github.com/GouriVerma/Animal_dataset_classification/assets/122892114/ba6f9577-0e86-4f76-95fa-edda4d7ad3de)

<br>

For first layer, output of first 6 filters is as shown

![image](https://github.com/GouriVerma/Animal_dataset_classification/assets/122892114/8f9892ca-5031-4024-bf2d-e252edb5962b)
![image](https://github.com/GouriVerma/Animal_dataset_classification/assets/122892114/98fa9601-2898-4ccf-a614-f1a1e8984898)
![image](https://github.com/GouriVerma/Animal_dataset_classification/assets/122892114/09f47348-1fb2-47ad-81d8-94179ab02412)

![image](https://github.com/GouriVerma/Animal_dataset_classification/assets/122892114/c5126bbb-0b64-4f79-9c76-ac086c1e898d)
![image](https://github.com/GouriVerma/Animal_dataset_classification/assets/122892114/53e8f90a-2db5-44ec-9b8a-8b85c91bd4c0)
![image](https://github.com/GouriVerma/Animal_dataset_classification/assets/122892114/65e1e583-aba3-4d28-9cc1-bb91713a8fb7)

The very first filter appears to get rough edges of the image, followed by 3 filters extracting some of the other features like facial characteristics. The last 2nd feature gets very fine outline of the animal and the 6th feature separates the black and white color in the image and also focuses on eyes and nose.





