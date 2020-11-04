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
For this project, you will complete the following steps that are derived from the FDA's official guidance on both the algorithm description and the algorithm performance assessment. Much of this portion of the project relies on what you did during your EDA, model building, and model training. Use figures and statistics from those earlier parts in completing the following documentation.

1. General Information:

First, provide an Intended Use statement for your model
Then, provide some indications for use that should include:
Target population
When your device could be utilized within a clinical workflow
Device limitations, including diseases/conditions/abnormalities for which the device has been found ineffective and should not be used
Explain how a false positive or false negative might impact a patient
2. Algorithm Design and Function

In this section, describe your fully trained algorithm and the DICOM header checks that you have built around it. Include a flowchart that describes the following:

Any pre-algorithm checks you perform on your DICOM
Any preprocessing steps performed by your algorithm on the original images (e.g. normalization)
Note that this section should not include augmentation
The architecture of the classifier
For each stage of your algorithm, briefly describe the design and function.

3. Algorithm Training

Describe the following parameters of your algorithm and how they were chosen:

Types of augmentation used during training
Batch size
Optimizer learning rate
Layers of pre-existing architecture that were frozen
Layers of pre-existing architecture that were fine-tuned
Layers added to pre-existing architecture
Also describe the behavior of the following throughout training (use visuals to show):

Training loss
Validation loss
Describe the algorithm's final performance after training was complete by showing a precision-recall curve on your validation set.

Finally, report the threshold for classification that you chose and the corresponded F1 score, recall, and precision. Give one or two sentences of explanation for why you chose this threshold value.

4. Databases

For the database of patient data used, provide specific information about the training and validation datasets that you curated separately, including:

Size of the dataset
The number of positive cases and the its radio to the number of negative cases
The patient demographic data (as it is available)
The radiologic techniques used and views taken
The co-occurrence frequencies of pneumonia with other diseases and findings
5. Ground Truth

The methodology used to establish the ground truth can impact reported performance. Describe how the NIH created the ground truth for the data that was provided to you for this project. Describe the benefits and limitations of this type of ground truth.

6. FDA Validation Plan

You will simply describe how a FDA Validation Plan would be conducted for your algorithm, rather than actually performing the assessment. Describe the following:

The patient population that you would request imaging data from from your clinical partner. Make sure to include:

Age ranges
Sex
Type of imaging modality
Body part imaged
Prevalence of disease of interest
Any other diseases that should be included or excluded as comorbidities in the population
Provide a short explanation of how you would obtain an optimal ground truth

Provide a performance standard that you choose based on this paper.

Detailed description of the project proposal is provided in the [README](https://github.com/udacity/AIHCND_C2_Starter/blob/master/README.md) file of the Nanoprogram at Udacity's Github.-
