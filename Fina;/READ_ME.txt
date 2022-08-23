READ ME 



******

PLEASE READ NOTEBOOKS IN THIS ORDER : "DICOM Data Extraction - 2D and 3D.ipynb" ,"Neoadjuvant Treatment Clinical Data Analysis.ipynb",
		"Neoadjuvant_Late_Fusion_Model_2D_Images.ipynb"

******


-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

"DICOM Data Extraction - 2D and 3D.ipynb" Explains how DICOM data was extracted into a suitible numpy arrays ready for predictions


"Neoadjuvant Treatment Clinical Data Analysis.ipynb" Explains correlation between features and predicting response to neoadjuvant therapy, exaplains the research 
process taken to choose models and hyperparameters and feature selected data. At the end of the notebook cross-validation is used to verrify robustness of the chosen model.


"Neoadjuvant_Late_Fusion_Model_2D_Images.ipynb" THIS IS THE MAIN NOTEBOOK FOR LATE FUSION RESEARCH



NOTE: notebooks are included for Recurrence of cancer but are not vital to the research objective but rather suplementary evidence. 
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

File Directory 

B1414659_C_Vaughan-Jackson_Artefact
Fina;
|
|-----Clinical Data Analysis
|		|
|		|--Neoadjuvant Treatment Clinical Data Analysis.ipynb
|		|--Recurrence Clinical Data Analysis.ipynb
|
|-----Datasets
|		|
|		|--Annotaion_Boxes.xlsx
|		|--Breast_dataset_Neoadjuvant-2D-256-with identifier.npy
|		|--Clinical_and_Other_Features.csv
|		|--Neoadjuvant_clean_clinical.csv
|		|--Recurrence_clean_clinical.csv
|
|-----Late Fusion Model
|		|
|		|--Neoadjuvant_Late_Fusion_Model_2D_Images.ipynb
|		|--3D_Convolutional_Network_example.ipynb
|		|--Recurrence_Late_Fusion_Model_2D_Images.ipynb
|		|
|		|
|		|--Neoadjuvant Models and Weights
|				|
|				|--2D_clinical_Neoadjuvant.h5
|				|--2D_image_Neoadjuvant.h5
|
|----Preprocessing
|		|
|		|--Moving files.ipynb
|		|--DICOM Data Extraction -2D and 3D.ipynb
|
|_____



--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Understanding file directory

*note file directories might need to be altered for notebooks to be re-run
**it's advised not to re-run the models and notebooks as they take a lot of time and computational power

Preprocessing Folder:

Moving files.ipynb is code to reorganise and extract specific contrast images and rename into patient identified folders. 
DICOM Data Extraction - 2D and 3D.ipynb this is the code to convert all DICOM files for each patient into a numpy array, and where npy. files were made.
In addition the creation process of a correlating csv file with matching ID numbers.


Clinical Data Analysis Folder:

Both of these notebooks explain how features correlate to the respective target variable. These notebooks explain the experimention behind 
why certain features where selected and which model architecture were chosen.
The main body of work is found in Neoadjuvant Treatment Clinical Data Analysis.ipynb where cross validation can be seen for proof of model roustness


Neoadjuvant Models and Weights Folder:

h5 files have been saved from the results of running the models and saving best weights, these files can be loaded into Final_Neoadjuvant_Late_Fusion_Model_2D_images.ipynb
in the evaluate section at the end of the notebook to re-run results to save rerunning models. 


Datasets Folder:

contains data used in these notebooks. There are more npy. files for different dimension scans available on request.


Late Fusion Model Folder:

These is the most important notebooks in terms of model development and data integration processes, for reasoning for why certain features are selected and certain 
model arcitectures are chosen see Data analysis folder.

------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Techinical Requirements:

3D models and some 2D models require GPU configuration GPU used Tesla P100-PCIE-16GB
To configure GPU inside Juypter Notebook you will need: 

NVIDIA driver 
Visual Studio 2019, Microsoft visual C++
CUDA : 11.2
CuDNN : 8.1.0
Python : 3.8
Anaconda :4.13.0
Juypter Notebook :6.4.5

Module installation : 

Tensorflow : 2.80
pandas : 1.3.4 
numpy : 1.20.3
scipy :2.0
pydicom: 2.3.0

other modules (collections, random, os, matplotlib, seaborn, sklearn, keras_tuner)

-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

All data used is sourced from https://wiki.cancerimagingarchive.net/pages/viewpage.action?pageId=70226903 NBIA Data retriver is needed for download

Citation
Saha, A., Harowicz, M.R., Grimm, L.J., Kim, C.E., Ghate, S.V., Walsh, R. and Mazurowski, M.A., 2018. A machine learning approach to radiogenomics of
breast cancer: a study of 922 subjects and 529 DCE-MRI features. British journal of cancer, 119(4), pp.508-516
