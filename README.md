**Project Overview:**



This project builds a multimodal regression pipeline to predict residential property prices by combining:



Tabular property data (e.g., bedrooms, bathrooms, living area, location)



Satellite imagery capturing environmental and neighborhood context



The motivation is that property value depends not only on structural features but also on surroundings such as road connectivity, greenery, and urban density. Satellite images provide this additional context, which is integrated with tabular data to improve interpretability and modeling depth.





**Methodology:**



The project follows a structured pipeline:



1.Tabular Data Processing



&nbsp;     >Feature selection and scaling



&nbsp;     >Baseline regression model trained using numerical features only



2.Satellite Image Acquisition



&nbsp;     >Images fetched programmatically using latitude and longitude



&nbsp;     >A representative subset of 1,200 images was used due to API and computational constraints



3.CNN Feature Extraction



&nbsp;     >A pretrained ResNet18 model is used as a feature extractor



&nbsp;     >Each satellite image is converted into a 512-dimensional embedding



4.Multimodal Fusion



&nbsp;     >Tabular features and image embeddings are concatenated



&nbsp;     >A regression model is trained on the fused representation



5.Explainability



&nbsp;     >Grad-CAM is applied to visualize which regions of satellite images influence predictions





**Repository Structure:**

 

data\_fetcher.ipynb

preprocessing.ipynb

model\_training.ipynb

enrollno\_final.csv

README.md



**How to Run:**



Install dependencies:



pip install numpy pandas scikit-learn torch torchvision matplotlib pillow





Run preprocessing.ipynb for EDA and feature engineering.



Run model\_training.ipynb for baseline, multimodal training, and Grad-CAM.



Final predictions are saved as 23125012\_final.csv.





**Output:**



Prediction File: 23125012\_final.csv (format: id, predicted\_price)



Project Report: PDF containing EDA, results, Grad-CAM visualizations, and architecture diagram.









