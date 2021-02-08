This is a Image Search powered by Tensorflow Deep Learning. Images will be recognized by Image
Captioning Neural Networks together with Semantic Segmentation Neural
Networks. Every Image uploaded to the S3E will be analyzed by Deep
Neural Networks to generate labels through Variational Auto Encoders
and then generate annotations and metadata about images through Image
Captioning Neural Networks via attention mechanism with tensorflow

The problem with normal method is that, when the model is trying to generate the next word of the caption, this word is usually describing only a part of the image. It is unable to capture the essence of the entire input image. Using the whole representation of the image h to condition the generation of each word cannot efficiently produce different words for different parts of the image.This is exactly where an Attention mechanism is helpful.

With an Attention mechanism, the image is first divided into n parts, and we compute with a Convolutional Neural Network (CNN) representations of each part h1,…, hn. When the RNN is generating a new word, the attention mechanism is focusing on the relevant part of the image, so the decoder only uses specific parts of the image.

Image Captioning using Attention Mechanism

We can recognize the figure of the “classic” model for image captioning, but with a new layer of attention model. What is happening when we want to predict the new word of the caption? If we have predicted i words, the hidden state of the LSTM is hi. We select the « relevant » part of the image by using hi as the context. Then, the output of the attention model zi, which is the representation of the image filtered such that only the relevant parts of the image remains, is used as an input for the LSTM. Then, the LSTM predicts a new word and returns a new hidden state hi+1.

Types of Attention Mechanism tested :

Attention could be broadly differentiated into 2 types:
Global Attention(Luong’s Attention): Attention is placed on all source positions.
Local Attention(Bahdanau Attention): Attention is placed only on a few source positions.


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
