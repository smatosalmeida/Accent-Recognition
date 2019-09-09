# Capstone: Accent Recognition Portuguese - Portugal and Brasil

## Directory Structure

├── Capstone

├── NN_Clean_Train_Test.ipynb

├── README.md

└── Accent Recognition_Portuguese.pdf

## Executive Summary
The Portuguese language has spread worldwide and is spoken by about 290 million people on various continents. Portuguese is the official language of Angola, Brazil, Cape Verde, Guinea-Bissau, Mozambique, Portugal and Sao Tome and Principe, and is also spoken in other countries such as Equatorial Guinea, Timor-Leste and Macau.It is therefore very natural that many different accents have emerged in the various Portuguese-speaking countries.

Language has a social character: it belongs to a whole set of people who can converse. Each community member can choose this or that form of expression. On the other hand, it is not possible to create a particular language and require other speakers to understand it.

Language is an instrument of communication, consisting of grammatical rules that enable a certain group of speakers to produce statements that allow them to communicate and understand each other.

Our focus in this analysis was on accents from Brasil and Portugal.

For the accents in that we are trying to predict, the difference is most evident when comparing the two variants. Brazilians have a slower speech rhythm, in which both unstressed vowels and open vowels are clearly pronounced. In Portugal, on the other hand, speakers often "eliminate" the unstressed vowels, pronouncing only the stressed vowels.

In Portugal, people tend to talk with their mouths shut. However, in Brazil, it is the opposite. People talk with a much more open mouth.

As a proof of concept, we created a project that took a list of 1347 audio recording sentences from both portuguese and brazilian speakers, put the data through a NN model, and predicted whether a test sample of audio would belong to which accent. Since brazilian and portuguese accents for the project, we were able to generate very high accuracy scores for our dataset - 87.38% on the training data and 96.15% on the validation data. With this model, we are able to demonstrate the ability to clearly delineate one accent from the other. With the available data we also calculated the gender voice prediction model which also that also generated very high accuracy scores for our dataset.

Nowadays everyone has used an Ok Google or at least heard of some other personal assistant like: Siri from Apple, Cortana from Microsoft or Alexa from Amazon. There is no doubt of the growth of these personal assistants therefore we need to improve the hability that these machines can understand us!

## Description of Data

### Size
The data consist ofa file of 1,347 wav files (66% audio for Brasil , 33% audio for Portugal), plus a xlsx file with 6 columns of values of charaterizing each wav file.

### Source

1,197 of the speech files used for this project came from a sample of the ASR Speech Copora kindly provided by mail by Speechocean Company (http://en.speechocean.com).

Because the ceded data was unbalanced (no portuguese female speaker), I added 150 row observations of my own recording on audacity.com.

### Data Dictionary

|Feature|Type|Dataset|Description|
|---|---|---|---|---|
|sentence_n|integer|df|sentence id|
|sentence|object|df|sentence read by speaker|
|country|object|df|country of speaker|
|speaker|object|df|speaker id|
|gender|object|df|gender of speaker|
|transcript|object|df|Transcript of read sentences|
|fname|object|df|Name of audio file in folder pt_accents|

## Model Creation and Score

### Model Steps
Below is a summary of steps to create a model that categorizes a binary class voice recognition model:

Clean noise from the audio - FourierTransformation Preliminary EDA on xlsx data Random sample separated Choose transformers and models to use in a neural networks Check the scores of the models Explore the features, create a Confusion Matrix, calculate error metrics.

### Neural Networks:
num_labels = 2 
filter_size = 2 
loss=binary_crossentropy 
metrics=binary_accuracy 
optimizer=adam 
batch_size=32 
epochs=5

### Model Scores

Accent Recognition NN Model - 87.38% train and 96.15% val
Accent Recognition Confusion Matrix - TEST data
When using neural networks AND following good regularization practices (read: very liberal usage of Dropout), it’s basically assured that your test accuracy, at it’s best, will be better than your training accuracy.

Dropout, during training, slices off some random collection of these classifiers. Thus, training accuracy suffers.

Dropout, during testing, turns itself off and allows all of the ‘weak classifiers’ in the neural network to be used. Thus, testing accuracy improves.

## Data Visualization

## Next Steps

Gather more audio data

Clean silence from audio files

Investigate other models such as cnn, Xgboost

Perform the same analysis on word analysis and other portuguese accents.

## Outside References:
Yishan Jiao, Ming Tu, Visar Berisha, Julie Liss, "Accent Identification by Combining Deep Neural Networks and Recurrent Neural Networks Trained on Long and Short Term Features," in INTERSPEECH 2016, September 8-12 2016, San Francisco, USA.

https://github.com/mayur1711/Gender-Recognition-by-Voice

https://www.analyticsvidhya.com/blog/2017/08/audio-voice-processing-deep-learning/

https://en.wikipedia.org/

https://github.com/dwww2012/Accent-Classifier

https://www.kaggle.com/fizzbuzz/beginner-s-guide-to-audio-data/notebook

https://www.quora.com/Which-Portuguese-accent-sounds-better-the-one-in-Brazil-or-in-Portugal

