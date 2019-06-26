# AV-Game-of-Deep-Learning
AnalyticsVidhya- Game of Deep Learning: Computer Vision Hackathon

![Competition banner](images/banner.jpg)

[Competition Link](https://datahack.analyticsvidhya.com/contest/game-of-deep-learning/)

#### Problem Statement

Ship or vessel detection has a wide range of applications, in the areas of maritime safety,  fisheries management, marine pollution, 
defence and maritime security, protection from piracy, illegal migration, etc.

Keeping this in mind, a Governmental Maritime and Coastguard Agency is planning to deploy a computer vision based automated system to
identify ship type only from the images taken by the survey boats. You have been hired as a consultant to build an efficient 
model for this project.

There are 5 classes of ships to be detected which are as follows: 

![Category](images/category.png)

#### Dataset Description

There are 6252 images in train and 2680 images in test data. The categories of ships and their corresponding codes in the dataset are as follows -
```
'Cargo' -> 1
'Military' -> 2
'Carrier' -> 3
'Cruise' -> 4
'Tankers' -> 5
```
- There are three files provided to you, viz train.zip, test.csv and sample_submission.csv which have the following structure.

| Variable	| Definition |
| ------------- | ----------------- |
| image	| Name of the image in the dataset (ID column) |
| category | Ship category code (target column) |
 

- train.zip contains the images corresponding to both train and test set along with the true labels for train set images in train.csv

#### Evaluation Metric
The Evaluation metric for this competition is weighted F1 Score.

#### Public and Private Split
Public leaderboard is based on randomly selected 30% of the test images, while private leaderboard will be evaluated on remaining 
70% of the test images.

#### Python 3.6 libraries
```
fastai==1.0.51
torch==1.0.1
torchvision==0.2.2
pretrainedmodels
```

#### Approach

I have used [fastai](https://fast.ai) cnn learner datablock api. The final submission is a result of votings based on 
22 submissions which were created from 22 different models based on different techniques such as: 
 - different image size (299/484/599)
 - different pre-trained architectures (resnet101/resnet152/densenet161/densenet169)
 - different augmentation techniques
 - mixup models (see the code for details) 

#### Score

- public LB score - 0.9906 (Rank - 2/2083)
- private LB Score - 0.9875 (Rank - 1/2083)

#### Final Thoughts

Although training 22 models seems very time consuming as well as computationally intensive, but for small dataset like this,
it would be a great idea. I was able to acheive private LB score similar upto 4 decimal places as the score from 22 models using
only 9 models (including 4 mixup models, image size was fixed at 499X499, 4 pre-trained architectures stated above were used and 
lastly voting method was applied), however the public score was not that great (0.9855).
This suggests that we still can achieve state of the art results by training fewer models and applying right ensemble method for 
aggregating.
