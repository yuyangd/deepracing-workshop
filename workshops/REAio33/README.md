# REAio33 DeepRacing Workshop

## DeepRacer

AWS DeepRacer car is a 1:18-scale model car. It has a mounted camera (DeepLens) and an on-board compute module. The module can run inference against a deployed reinforcement learning model in order to drive itself along a track. The compute module and the vehicle chassis are powered by dedicated batteries known as the compute battery and the drive battery, respectively.

AWS DeepRacer Service use AWS SageMaker to build and train its reinforcement learning models and AWS RoboMaker to create the virtual simulator that serves as the environment the car interacts with.

## Reinforcement Learning

[DeepRacer RL](https://d2k9g1efyej86q.cloudfront.net/)

[Reward Function Parameters](parameter_illustration.md)

[Hyperparameters](algorithm_setting.md)

## Build, Train and Deploy

Demo

## Hands-on labs

Lab 1 should take about 25 to 35 minutes, Lab 2 should take about 5 minutes, and Lab 3 will take more time than you have in the workshop but is for use at home.
The lab will provide detail on the various components in the AWS DeepRacer service in the console and you will get the chance to try them all out. You should will start training your model at the end of lab 1.

[lab1 - Model Training](lab1/)

[lab2 - Advanced Model Training](lab2/)

## Hints

- Save your reward function locally, the REAio account will be wiped after.
- Take your time and familiarize yourself with the concepts first, before starting model training.
- when you do start a training job, run it for at least 90 minutes, but do not over train the model.
- If you want to continue learning after the lab, please check out the AWS training course.
- Apply incremental changes and train on existing model.
