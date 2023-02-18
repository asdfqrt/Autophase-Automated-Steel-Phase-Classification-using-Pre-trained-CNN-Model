# Fe phase classification

Pytorch implementation of Phase classification of high carbon steel using pre-trained CNN model.
This project is still in progress, but still shows decent classification capabilites.

## Environmnet
- Python3
- Pytorch

## Getting stared
### Dataset
Place your Micrograph dataset in proper path

    Fe phase classification
    ├── data
    │    └── For Training
    │         ├── train
    │         │    ├── xxx.png
    │         │    ├── yyy.png
    │         │    └── ...
    │         ├── val
    │         │    ├── aaa.png
    │         │    ├── bbb.png
    │         │    └── ...
    │         ├── test
    │         │    ├── 111.png
    │         │    ├── 222.png
    │         │    └── ...
    │         └── metadata.csv
    └── Resnet_classification.py

metadata.csv must contain "path" and "primary_microconstituent" values of dataset

Or, you can just use sameple files in this repository for quick testing

### Hyperparameters
In `Resnet_calssification.py`, you can change
* File path
* Imbalance_correction, Overwrite
* batch_size
* learning_rate
* resize_level
* epochs
* model

It's okay to use the default

## Data Augmentation
If your dataset is biased, model's predictive performance may suffer. To correct the imbalance, this program has a data augmentation feature. This is a feature that transforms and copies images from classes with a small amount of images and trains it as much as a major class.
The Data Augmentation data will be saved as `dataaug.pt`.
If your training dataset is already balanced, 
change `Imbalance_correction, Overwrite = False,False`
If this is not your first time using this program and the dataaug.pt file already exists
change `Imbalance_correction, Overwrite = True,False`

## Run
Run `Resnet_classification.py`
It will automatecally train & test images in the directory folders.

1. Print out the distribution of your training set
2. Accuracy before training
3. Train images
4. Accuracy after training
5. predict Visualization(default set to 100 images)

## Result
![image (2)](https://user-images.githubusercontent.com/79451613/219881948-f062f3ab-4b01-42e8-a794-cd4cc251b267.png)

* The classification result will be recored in data/results.csv

## References
- Dataset: [UHCSDB: UltraHigh Carbon Steel Micrograph DataBase](https://www.kaggle.com/datasets/safi842/highcarbon-micrographs)

## Autor
[asdfqrt](https://github.com/asdfqrt)
