# Wildfire Analysis Project
This repository contains the Python code for my talk proposal to SciPy's 2024 Conference.

## Overview
This repository contains a collection of Jupyter notebooks designed to collect, curate, and augment RGB GeoTIFF Sentinel-2 Satellite Imagery of wildfire-affected areas using Google Earth Engine (GEE) and analyze it using Deep Learning Convolutional Models. For demonstration purposes, this  project uses a pre-trained VGG16 model adapted for 3-channel RGB GeoTIFF files and a pre-trained EfficientNet adapted for multi-channel (6 bands) GeoTIFF files.  The models are used to detect and classify forested areas affected by wildfires. The VGG16 model trains on images taken after a wildfire and EfficientNet combines before and after wildfire imagery under one input. The aim is to provide insights into the impacts of wildfires and identify affected regions accurately to improve the effectiveness of disaster management.

## Installation
To get started, clone this repository to your local machine or Jupyter environment. Ensure you have Python installed, along with the following major dependencies:

TensorFlow (or Keras)
NumPy
rasterio
SciKit Learn
Matplotlib
pandas

## Usage
Each notebook in this repository is designed for a specific step in the wildfire analysis process, from data gathering and preparation to model training and deployment. Follow the instructions within each notebook to execute the code. Here's a brief overview of what each notebook accomplishes:

### Data Preparation and Preprocessing
wildfiresData.ipynb & wildfiresDataAfter.ipynb: Download Sentinel-2 satellite images of Forested Areas in California before and after wildfires.

CoordinateVerification.ipynb: Plot fire coordinates to verify the accuracy of the dataset.  

MaskingTests.ipynb & Masks.ipynb: Create two-dimensional labels using curated polygon data of historic wildfires to overlay on satellite images. These labels are for training Fully Convolutional Models.  

FilesBinary.ipynb: Organize and label the satellite image data for binary Convolutional Neural Network (CNN) models that only use 3-Channel RGB GeoTIFF input. 

6ChannelDataCreation.ipynb: Organize, pair and combine the before and after data under one 6-Channel input for CNN models that use 6-Channel RGB GeoTIFF.

### Data Augmentation and Segmentation
imageMaskPairingSegmenting.ipynb: Segment GeoTIFF images and their two-dimensional labels into smaller chunks (256*256 px) for analysis and model input.  

DamageTilesAugmentation.ipynb: Augment satellite images of fire-damaged areas to enhance the dataset and address the class imbalance.

### Data examples and visualization
DatasetExamples.ipynb: Visualize the dataset and its two-dimensional labels for demonstration purposes.

### Model Training and Evaluation
VGG16.ipynb: Run a simple VGG16 model on labeled post-wildfire GeoTIFF images.

ImprovedVGG16.ipynb: Enhancements to the VGG16 model, including addressing the class imbalance, implementing regularization, and adding Early Stopping.

EfficientNet.ipynb: Run an EfficientNet model for 6-channel satellite images to incorporate the Before RGB GeoTIFF Wildfire Images with the After RGB GeoTIFF Wildfire Images under one input.

### Contact Information

Valeria Martin Hernández: vm58@students.uwf.edu

### Acknowledgments

I want to extend my deepest gratitude to my PhD advisors, Dr. Kristen Venable and Dr. Derek Morgan, for their invaluable guidance, support, and mentorship throughout this project. Their expertise and insights have been instrumental in shaping both the direction and success of this work.

The VGG16 and EfficientNet model developers for their robust frameworks in image classification and segmentation tasks.
TensorFlow and Keras libraries for providing the essential tools to develop and train my AI models.
Jupyter Notebooks for offering a powerful and accessible platform for our data science experiments.

Additionally, I would like to acknowledge the assistance provided by OpenAI's ChatGPT, which offered valuable guidance and support for various aspects of this project, including code snippets, algorithm explanations, and documentation drafting. 

### License
This project is licensed - see the LICENSE file for details.


