# Image-Captioning-Bot
* Created a tool which able generate captions for an image
* Dataset was taken from kaggle. (Flick8k)
* Link for dataset: https://www.kaggle.com/shadabhussain/flickr8k
* Built an API on Flask and deployed it on a local server 

# Code and Resources Used 
**Python Version:** 3.7  
**Packages:** pandas, numpy, sklearn, matplotlib, seaborn, selenium, flask, json, pickle , tensorflow, keras

# Overview Of The Dataset

* The dataset contains of 8000 images
* Each image has 5 captions with it

# Steps Performed

**Data Collection**
* In this step, I read the captions text file and stored it in a variable called 'captions'
* Next, I split each caption, to separate the image-id and the caption.
* Finally I created a dictionary to map each Image with the list of captions it has

**Text Data Cleaning**
* In this step, I created a function clean_text which removes all words which are not a between a-z and have a length <=1.
* Next, I applied this function on each caption.
* I created a set called 'vocab' which has all the unique words in the dataset. There are 8424 unique words.
* Then, I created a list called 'total_words' which contains all the words in the dataset.
* I removed the words which had a frequency <=10
* Then I splitted the dataset into train and text captions based on the image-ids given in the trainimages.txt and testimages.txt
* Finally I added a "startseq" and "endseq" token in each sentence. 

**Image Data Encoding**
* In this step I encoded each image using the ResNet-50 model.

**Model**
* Here, I created the model architecture.
* I used pre-trained glove embeddings in the embeddings layer.

**Flask**
* Finally the model was deployed on a local server using flask
![image](https://user-images.githubusercontent.com/56645508/122637442-4a391600-d10c-11eb-928a-7fdd0069db83.png)

![image](https://user-images.githubusercontent.com/56645508/122638014-3216c600-d10f-11eb-85b0-98ce8fa968a2.png)
