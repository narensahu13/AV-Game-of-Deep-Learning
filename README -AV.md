### AV-Game-of-Deep-Learning
AnalyticsVidhya- Game of Deep Learning: Computer Vision Hackathon

#### Modelling platform

I have used Kaggle platform (with GPU enabled and internet on) for the modelling purpose.
It already loaded with python 3.6 libaries and latest version of fastai, pytoch and torchvision.

#### Python 3.6 libraries
```
fastai==1.0.51
torch==1.0.1
torchvision==0.2.2
pretrainedmodels (resnet101, resnet152, densenet161, densenet169)
```

#### Approach

Details of the approach given in the attached pdf document.

#### Execution

To execute the model, run the attached ipynb notebook.
Remember to install fastai latest version (if not done already) using below codes
!pip install fastai==1.0.51 --no-deps
!pip install torch==1.0.1 torchvision==0.2.2

As mentioned in the approach, the final result is outcome of voting done on 22 different models.
These different models can are result of setting 3 differnt parameters mentioned below:
a) different pre-trained models (4 models as mentioned in libraries section)
b) different image sizes (3 image size were used 224X224, 484X484, 599X599). Also it is ver necessary to decrease the batch size 
as we increase the image resolution otherwise GPU memory error will occur.
c) with and without mixup technique (details in the approach document)

Finally, the predicted categories from all the models were taken into account and a voting was done to arrive at the final 
testset predictions.


Submitted By:
Narendra Sahu