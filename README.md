
## Dataset Preparation
1. Initially, the dataset of images of 5 categories are chosen: antelope, badger, bat, beer, bee and a dictionary is by the help of pathlib library which contains each category as key and list of paths of images as value. files_dict looks like {category: list of paths of the images corresponding to that category}. Also, label_dict is made to store category as key and corresponding index as value.
2. The data is then restructured to form two arrays X and y, where X contains the correspoding tensor of each image and y contains the labels of each image.
