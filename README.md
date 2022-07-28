# Automatic-License-Plate-Recognition

## About Dataset
In this study, the <a href="https://www.kaggle.com/datasets/andrewmvd/car-plate-detection" target="_blank"> Car License Plate Detection</a> dataset was used in Kaggle. This dataset contains 433 images. It was concluded that there were unusable photographs while examining the dataset during the EDA (Exploratory Data Analysis) phase. With the deletion of these photos, 257 photos remained out of 433 photos. An additional dataset called <a href="http://www.zemris.fer.h" target="_blank">  Baza Slika</a> was used to increase the data in the dataset. There are 510 images in the data set, and 453 of these images were used in the project. After the images from the two datasets, the number of images processed in the project is 710 in jpg and png format. The first dataset includes license plates from different countries. The second dataset includes license plates predominantly from European countries.



## About Project
The project is an Image processing project using CNN (Convolutional Neural Network) technology. Some preprocessing techniques used on images:
* Convert an Image to Grayscale
* Histogram Equalization
* Normalization
* Standardization

Images undergoing preprocessing processes were trained using the InceptionResnetV2 Deep Learning Model (Transfer Learning) and Plate Detection was performed. Then, Character Recognition was performed using Tesseract. Flask was used to create the web application, and HTML and CSS were used for its design.

### Data Augmentation
Data augmentation method was applied in the project in order not to encounter the problem of overfitting in the model. For visual data; rotation (10 degrees), shear(0.01), HSV(1,1,1), scale(0.12) and translation (0.2) methods were used, but this time the success rate decreased as the plates were changed in the new images. These processes were applied to the plate coordinate information, so that even if the images were rotated 10 degrees or scaled by 0.12, the success rate was prevented from decreasing as the plate coordinates also went through the same process.


 ### Detection Success Rate
| Metric Type    |      Success Rate      |  
|----------|:----------|
| Accuracy  | 88.18% |  
| IoU  | 0.47 | 


### Hyperparameters
In this project, each hyperparameter optimization is a test. Various hyperparameter adjustments have been made to achieve a better percentage of success.
| Layers   |      Model (88.18%)      |  
|----------|:----------|
| InceptionResnetV2(weights=”imagenet”, include_top=False, input_tensor=Input(shape=(224,224,3)))  | Input shape dimension of 299x299 using 3 channels. include_top is a fully connected layer at the top of the network. |  
| Activation | relu, relu and linear | 
| Flatten | Model has 1 Flatten layer | 
| Dense | There are 3 Dense layers with units ; 128, 64 and 4. | 
| Batch Size | 10 | 
| Learning Rate | 0.0005 | 


### Conclusion
By using the deep learning model, license plate regions were found in the vehicle images, respectively, and the plate was converted to text. In addition, a database system was created and a web application was developed.


