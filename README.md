# AMCS - Automated Marks Collection System

## Overview
AMCS (Automated Marks Collection System) takes photo-scanned images of test paper mark sheets and automatically identifies all marks, inputting them digitally into an Excel sheet. This system offers an alternative to manual data entry for universities that do not have the resources to implement a full digital correction system.

The system comprises two machine learning models:
- **MSDM (MarkSheet Detection Model)** - Detects and locates mark regions on the sheet
- **HNGM (Handwritten Number Guessing Model)** - Recognizes handwritten numbers

<div align="center">
  <img src="https://github.com/user-attachments/assets/ed0add13-1820-46f9-b923-ea5c962f1a60" width="600" alt="AMCS System Overview"/>
  <br/><br/>
  <img src="https://github.com/user-attachments/assets/668edcf6-622d-48f4-becf-47293fbe769c" alt="Model Processing" style="margin-right: 20px;"/>
  <img src="https://github.com/user-attachments/assets/0cb2dd17-ac31-4855-aa23-ada5c86dfcb1" alt="Results Example"/>
</div>

## Setup Requirements
* Use Google Colab
* Under notebook settings, set to use T4 GPU

## Running AMCS

### Option 1: Running the Pre-trained System
To quickly run and test the system:
1. Download the 2 trained models from the models folder
2. Download or create a test image named "test.jpg"
3. Run the AMCS.ipynb notebook

#### Test Image Requirements
For optimal model performance:
* Use a marker/sketch pen to fill in the marksheet
* All digits entered for marks must be between 0-9 whole numbers (except USN)
* USN must be between 0-900 and evenly spaced

---

### Option 2: Training Models from Scratch

#### MSDM Dataset Setup
1. Create a Roboflow account
2. Go to https://universe.roboflow.com/ml-bpqjm/msdm/dataset/6
3. Click "Download Dataset"
4. Select download as code snippet or ZIP file
5. Select format as YOLOv8 and select "Show download code" in Download Options
6. Copy the code and paste it in the appropriate kernel

#### HNGM Dataset Setup
1. Navigate to https://drive.google.com/drive/folders/1f2o1kjXLvcxRgtmMMuDkA2PQ5Zato4Or
2. Download:
   * Images(28x28).npy
   * WriterInfo.py

**Citation**: Cédric Beaulac and Jeffrey S. Rosenthal, Analysis of a high-resolution hand-written digits data set with writer characteristics, preprint

#### Final Steps for Training
1. After downloading the datasets, run and save the models as per the requirements in the respective .ipynb files
2. After obtaining the trained models, run AMCS.ipynb following the instructions in Option 1
