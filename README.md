# VGG16 Implementation on CIFAR100 Dataset

## Introduction
This is my personal attempt at training a model that is based on the VGG16 architecture. Please take this implementation with a grain of salt; I neither had the time to properly train the model for sufficient iterations, nor to experiment with different hyperparameters that much (batch size, nodes, etc).

## Dataset
The model was trained on the CIFAR100 dataset which contains 60,000, 32x32, RGB images with 100 different classes. This dataset is widely used to train various CNN models.

## Architecture
In its name, VGG16 consists of 16 layers. The architecture that I implemented had 5 main blocks:

Note: each block is ended by a max-pooling layer.
1- A 64 channel block, with a batchnorm layer and a ReLU after each layer.
2- A 128 channel block, with a batchnorm layer and a ReLU after each layer.
3- A 256 channel block, with a batchnorm layer and a ReLU after each layer.
4- A 512 channel block, with a batchnorm layer and a ReLU after each layer.

The blocks are concluded with an avg-pooling layer of (1,1).

For more details please refer to the notebook file.

![Architecture](/images/Architecture.png)
![Visualization](/images/Visualization.png)


## Training
To train the VGG16 model on the CIFAR100 dataset, I used a combination of data augmentation techniques such as random cropping, horizontal flipping, and normalization. I also used weight decay, although I could have skipped it since I'm not overfitting with "12" epochs anyway. Nonetheless, to alleviate overfitting on higher number of epochs or smaller batch sizes, weight decay as well as the commented out dropout layers could be used. This is obviously going to improve validation accuracy on the expense of training time.

## Evaluation
I did a simple evaluation; A simple train / test loss plot as well as direct evaluation was implemented as seen in the notebook. Feel free to assess your models with different metrics.
(Confusion matricies, recall scores, etc.)

## Conclusion
Implementing VGG16 on the CIFAR100 dataset can provide valuable insights into deep learning and image classification. By following this guide, you will be able to build and train a powerful model that can accurately classify images into 100 different classes.

