# Language Identification using CNN
Language is a system of conventional, spoken or written symbols by means of which human beings express themselves.This project focuses on classifying Language Identification using a Convolutional Neural Network (CNN), leveraging the unique properties of audio signals and transforming them into visual representations for effective Language Identification.

## Project Overview
Download the model and run a 3 seconds test audio using "interfacing.py". You will get a following output.
![Screenshot from 2024-03-10 16-14-36](https://github.com/Saif-000001/Language-Identification-using-CNN/assets/85629017/ad5668a3-ca9f-4238-9dcb-937b972a13c7)

The goal of this project is to accurately classify language tracks into their respective identity by analyzing short clips of audio. We use a CNN model for this task, as CNNs are highly effective in extracting patterns from visual data. The process involves converting audio files into mel spectrogram images, which capture the essential frequencies and textures of the language, serving as the input data for our CNN model.

## Audio Dataset Info
### Download Link
[Download the dataset here](https://drive.google.com/drive/folders/1s6N-sHHGvt4Hy8CNB4pZ0-cxSJKGAX4r?usp=drive_link)

### Contents
The dataset is organized into 2 subfolders, each representing a unique language identification. Each subfolder contains 20 audio files, with each file having a duration of 30 seconds. The total dataset comprises 40 audio files, providing a diverse collection of language samples for training and testing our model.

## Dataset Preprocessing
To prepare the dataset for training our CNN model, we perform several preprocessing steps:

1. **Audio Splitting**: Each 30-second audio file is split into 10 clips of 3 seconds each, resulting in 20 audio samples per identity. This increases the number of training samples and allows the model to learn from a broader range of language snippets.

2. **Mel Spectrogram Conversion**: For each audio clip, we generate a mel spectrogram image. Mel spectrograms provide a visual representation of the audio's frequency content over time, which is crucial for identity classification.

3. **Train-Test Split**: The spectrogram images are shuffled and divided into training and testing sets. This split is essential for evaluating the model's performance on unseen data.

### Running the Preprocessing Script

To start the preprocessing, run the `audio_2_image_dataset_generator.py` script:

```bash
python audio_2_image_dataset_generator.py
```

## Image Dataset Info
After proessing complete, go to your audio data directory. Inside that you will find a new dataset folder. It contains the audio3sec folder and spectogram folder. Inside spectorgram, there is train and test split. Cut thso and put it in to root directory. 

You can download the processed dataset directly from here and start the training immediately. Note that this model is undertrained due to time constrains. Its only trained on 20 epochs and achieve 56% accuracy. 
[Download the dataset here](https://drive.google.com/drive/folders/1uYVF9ziQeq1Dilv5u_IURjxHwYiezfBq?usp=drive_link)  


## Train 
Run the following, it will train the CNN model and saved the model in the directory. 
```bash
python train.py
```

## Inferencing   
Download the trained model from here: [Download the dataset here](https://drive.google.com/file/d/18TMVzfXwlmyfuSZOssqlx1-Jd8AsEH6n/view?usp=drive_link)  
Put it in the same directory. Now run: 
```
python inferencing.py 
```
It will open a plot showing the probability of the all class. 

