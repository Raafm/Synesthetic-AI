# Synesthetic-AI
![image](https://user-images.githubusercontent.com/72469894/222024195-7a226596-71be-4fee-9648-aa1cbd47be7a.png)

![image](https://user-images.githubusercontent.com/72469894/222034715-2e93b105-e54c-4175-8653-9cc610f0a7c0.png)
(Image from the article: https://www.frontiersin.org/articles/10.3389/fnins.2018.00777/full, to represent a 2D-CNN)

The aim of this project is to apply 2D convolution neural networks (CNNs) to visually perform speaker recognition.
The CNNs are applied to "see" audios representations generated from the original audios by an algorithm. 

## requirements
The following libs were used:

* pandas
* numpy 
* torch
* matplotlib
* librosa
* sklearn

The versions are the default used on google colab in the ned of 2022, as the project was done using it. 
I hope the most recent versions installed with pip (whenever you are reading this) might work as well.

## Original Dataset
This project uses the dataset: https://www.kaggle.com/datasets/vjcalling/speaker-recognition-audio-dataset, which has 50 different speakers. 
Only 10 of them were used due to lack of memory resources.
All this audios were converted to a single vector with each position being a value related to the volume at some moment of time.

The following image shows an example:
![image](https://user-images.githubusercontent.com/72469894/222025818-7eec43f3-dba1-452b-be55-a773ff53efb1.png)

## Audio's Images dataset
There are 1D convolution neural nets, which might work for this problem.
But this project uses 2D CNNs that works on images. To adapt the representation it is necessary to transform the input into a series of images.
The algorithm used was a composition of the results of many Fast Fourier Transforms stacked applied to sections of the original audio.
Besides this main part of the algorithm, several approchas to split the audios were tried to increase the number of samples of each speaker and decrease the size of the images without compromising their quality. 

The following image is an example of the transformation:
![image](https://user-images.githubusercontent.com/72469894/222028466-842ba372-0fa1-4e11-a6be-a3ffd3b976a6.png)

## Models
3 types of sizes of CNNs were used (gradually increasing the number of parameters), 
with 3 types of challenges: binary classification, classification of 5 speakers, classification of 10 speakers.
