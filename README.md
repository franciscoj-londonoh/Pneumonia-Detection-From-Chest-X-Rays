# Pneumonia detection from chest X-rays

## Project Overview
This project was part of the path to finish Udacity´s nanodegree: "AI for Healthcare", in which skills acquired in the 2D medical imaging course were applied to analyze data from the NIH Chest X-ray Dataset and to train a CNN for classifying a given chest x-ray for the presence or absence of pneumonia. The project produced a model that can predict the presence of pneumonia with human radiologist-level accuracy. 
The model was trained using a GPU for fast training of deep learning architecture, and access to a [dataset](https://www.kaggle.com/nih-chest-xrays/data) of 112,000 chest x-rays with disease labels acquired from 30,000 patients. 

## Background
Chest X-ray imaging is a frequent and cost-effective method to diagnose pneumonia, and an interesting technique to develop deep learning applications due to the high amount of available data to train deep learning models for image classification and the possibility to support better image reads in a challenging task even for expert radiologists, increasing accuracy and reducing clinical burnout. In fact, 


## Project Highlight
The development of this project involved:
* Recommend appropriate imaging modalities for common clinical applications of 2D medical imaging
* Perform exploratory data analysis (EDA) on medical imaging data to inform model training and explain model performance
* Establish the appropriate ‘ground truth’ methodologies for training algorithms to label medical images
* Extract images from a DICOM dataset
* Train common CNN architectures to classify 2D medical images
* Translate outputs of medical imaging models for use by a clinician
* Plan necessary validations to prepare a medical imaging model for regulatory approval

## The Project at a glance
This project contains the following parts:

* Part 1: Exploratory Data Analysis [(EDA)](https://github.com/franciscoj-londonoh/Pneumonia-Detection-From-Chest-X-Rays/blob/main/Part1_EDA.ipynb)

![EDA](https://github.com/franciscoj-londonoh/Pneumonia-Detection-From-Chest-X-Rays/blob/main/data/Distribution_EDA.png)

The first part of this project involves an exploratory data analysis (EDA) to understand and describe the content and nature of the data, including demographic data, such as gender, age, patient position, the x-ray views taken, the number of cases, comorbidities of pneumonia, histograms of intensity values, among others.

* Part 2: Building and Training a [Model](https://github.com/franciscoj-londonoh/Pneumonia-Detection-From-Chest-X-Rays/blob/main/Part2_BuildTrainModel.ipynb)

![Dataset](https://github.com/franciscoj-londonoh/Pneumonia-Detection-From-Chest-X-Rays/blob/main/data/Dataset_Model.png)

This part is divided is specific steps:
  - Selecting the train and validation Datasets based on EDA findings: distribution of pneumonia cases and comorbidities, demographic information, image view positions, and          number of images per patient in each set
  - The Model Architecture was set by fine-tuning the existing CNN VGG16 architecture with weights trained on the ImageNet dataset to classify x-rays images for the presence of      pneumonia
  - Image pre-processing and augmentation for increasing the model performance
  - Training the model
  - Monitoring performance assessment over subsequence training epochs. Pneumonia diagnosis is a challenging task even for expert radiologist, thus a F1 score than [0.35-0.4](https://arxiv.org/pdf/1711.05225.pdf) is a good reference point


* Part 3: Clinical Workflow Integration [(Inference)](https://github.com/franciscoj-londonoh/Pneumonia-Detection-From-Chest-X-Rays/blob/main/Part3_Inference.ipynb)

Since DICOM is the standard format in medicine imaging, this part of the project creates a DICOM wrapper that takes in a standard DICOM file and outputs data in the format accepted by the model.


* Part 4: FDA Submission
As part of the project, the following steps that are derived from the FDA's official guidance on both the algorithm description and the algorithm performance assessment. 

  - General information: intended use statement for the model, target population, limitations, among others
  - Algorithm design and function: description of the fully trained algorithm and the DICOM header checks implemented
  - Algorithm training: description of the model parameters and selection criteria. Additionally, description of the model performance by visualization of the training loss, 
    the validation loss and the precision-recall curve. Finally, report of the selected threshold for classification and the corresponded F1 score, recall, and precision
  - Databases: description about the selected training and validation datasets, such as size of the dataset, number of negative and positive cases, demographic data, radiologic      techniques used and views taken, and comorbidities
  - Ground truth description and its benefits and limitations
  - FDA validation plan 
  
Detailed description of the project proposal is provided in the [README](https://github.com/udacity/AIHCND_C2_Starter/blob/master/README.md) file of the Nanoprogram at Udacity's Github.
