#
# Image Captioning using InceptionV3 and Beam

## Image Captioning is the process of **generating textual description of an image**. It uses both Natural Language Processing and Computer Vision to generate the captions. The dataset will be in the form [image → captions].

## Dataset

## Image feature extraction

![0](https://user-images.githubusercontent.com/44580998/80075155-e2b72300-8567-11ea-8e73-dd5e092cd040.jpg)

This image is taken from the slides Recurrent Neural Networks, Image Captioning and LSTM taught by Andrej Karpathy.

I have done image captioning on it.  In this i used a CNN to extract the features from an image which is then along with the captions is fed into an LSTM. To extract the features, I used a model trained on Imagenet.

## Training and Hyperparameters

For creating the model, the captions has to be put in an embedding. I used Word2Vec to get the pre-trained embedding weights of vocabulary,. So, I took some ideas from it by setting the embedding size to 300. The image below is the model that I used.

I explored VGG-16, Resnet-50 also . Vgg16 has almost 134 million parameters and its top-5 error on Imagenet is 7.3%. InceptionV3 has 21 million parameters and its top-5 error on Imagenet is 3.46%.  So i decided to continue with it.


![0 1](https://user-images.githubusercontent.com/44580998/80075152-e0ed5f80-8567-11ea-96ca-2204b800804f.PNG)


I have used beam seach Beam Search is where we take top k predictions, feed them again in the model and then sort them using the probabilities returned by the model.

So, the list will always contain the top k predictions. In the end, we take the one with the highest probability .But we can aslo go with Argmax search.

# **Results**
Pneumonia Results via sementic search using attention mechanism

![2](https://user-images.githubusercontent.com/44580998/107186170-c5c1e280-6a09-11eb-83f7-8de40b7df2a5.JPG)
![3](https://user-images.githubusercontent.com/44580998/107186172-c6f30f80-6a09-11eb-8fe8-3ef22f96d4bf.JPG)
![4](https://user-images.githubusercontent.com/44580998/107186176-c78ba600-6a09-11eb-8aa6-b1bc0b6857eb.JPG)
![Capture](https://user-images.githubusercontent.com/44580998/107186177-c8243c80-6a09-11eb-8128-c1136203dc48.JPG)







Normal testing Images
![1](https://user-images.githubusercontent.com/44580998/80075158-e34fb980-8567-11ea-8cb8-30629f4263d4.PNG)
![2](https://user-images.githubusercontent.com/44580998/80075165-e77bd700-8567-11ea-98d5-3fb52e9fd3f5.PNG)
![4](https://user-images.githubusercontent.com/44580998/80075130-d6cb6100-8567-11ea-8efc-e6ef755341c3.PNG)
![5](https://user-images.githubusercontent.com/44580998/80075141-da5ee800-8567-11ea-8d66-7988b4e26ba8.PNG)
