![TensorFlow](https://img.shields.io/badge/TensorFlow-%23FF6F00.svg?style=for-the-badge&logo=TensorFlow&logoColor=white) ![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54) ![Jupyter Notebook](https://img.shields.io/badge/jupyter-%23FA0F00.svg?style=for-the-badge&logo=jupyter&logoColor=white)
# Arabic-Speech-Recognition
### About the project
Create model with TensorFlow to classify spoken words by human. First thing to do in this project is preprocess the data by extract the information of it using MFCC. fter that, I store the extracted features in npy format (for later use). Then go to the main part modelling, I use 1 dimension CNN to construct the model followed by maxpooling layer, dropout, and dense layer on the output layer with softmax activation. After the training is complete, I saved the model with h5 extension and ready to be deployed. The saved model was served on [this repository](https://github.com/lutfi640/Speech-Recognition-Deployment) by the help on Heroku, go check it out.
### Dataset Information
The dataset that I used in this project was taken from website https://zenodo.org/record/4662481#.Yo7-16hBxEZ created by Abdulkader Ghandoura. This is the dataset characteristic :
* Spoken in Arabic
* Contains 40 classes, 30 different people, and each people do 10 utterances for every class. Therefore total dataset would be 40 x 30 x 10 = 12000 audio
* Audio extension is WAV
* 16000 Hz Sampling Rate
* Each audio is 1 seconds duration
* Modulation format is 16-bit little-endian
* 256kbps Bitrate
* Mono Channel

These is the detailed keyword (classes) :

![Keywords](https://github.com/abdulkaderghandoura/arabic-speech-commands-dataset/blob/v1.0/images/keywords.jpg)

### Feature Extraction
One of the best feature extracton for audio signal is MFCC (Mel Frequency Ceptral Coefficient) with 5 steps of calculations :

![MFCC Step](https://ars.els-cdn.com/content/image/1-s2.0-S2214317320302171-gr3.jpg)

To make it easier, I used library [Python Speech Features](https://python-speech-features.readthedocs.io/en/latest/) to get the feature just by typing its function and let library do the job.

### Training
I used machine learning framework [TensorFlow](https://www.tensorflow.org) to create the model. I used Convolutional Neural Network 1 dimension algorithm and other layer, this is the complete architecture of the model : 

![Architecture](https://github.com/lutfi640/Arabic-Speech-Recognition/blob/main/Other/model%20architecure.png)

### Result
The performance of the model with MFCC extraction and CNN algorithm dimension 1 is quite good with an accuracy of 95.52% and validation accuracy of 95.50%. And this is can be tested also using our own voice by running testing phase on the cell on the notebook. Below is the training curve and the confusion matrix :

![Training Curve](https://github.com/lutfi640/Arabic-Speech-Recognition/blob/main/Other/training.png)
![Confusion Matrix](https://github.com/lutfi640/Arabic-Speech-Recognition/blob/main/Other/output.png)
