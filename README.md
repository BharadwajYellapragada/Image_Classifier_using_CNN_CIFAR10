# Image Classifier Using CNN and CIFAR10
The CIFAR-10 dataset consists of 60000x32 x 32 colour images divided in 10 classes, with 6000 images in each class. There are 50000 training images and 10000 test images. Generally, the dataset is divided into five training batches and one test batch, each with 10000 images. The test batch contains exactly 1000 randomly-selected images from each class. The training batches contain the remaining images in random order, but some training batches may contain more images from one class than another. Between them, the training batches contain exactly 5000 images from each class. For a better understanding i have divided my implementation into 7 phases
1. Data Loading
2. Data Visualizing
3. Data Transformation
4. Model Loading (model creation/specification/construction)
5. Model Compiling
6. Model training (fitting)
7. Ploting the results
## Data loading
We are using keras with tensorflow as background, keras.dataset have CIFAR-10 dataset, so we need to import that to work with the CIFAR10 dataset or you can also download it from [here](https://www.cs.toronto.edu/~kriz/cifar-10-python.tar.gz), we will use the dataset from keras and divide them into training set and testing set
## Data Visualizing
The label data is just a list of 10,000 numbers ranging from 0 to 9, which corresponds to each of the 10 classes in CIFAR-10.
* airplane : 0
* automobile : 1
* bird : 2
* cat : 3
* deer : 4
* dog : 5
* frog : 6
* horse : 7
* ship : 8
* truck : 9
## Data Transformation
In this phase, labels are one hot encoded and pixel values are normalized between 0 and 1.
## Model loading
A Sequencial CNN model is implemented with 4 convolution layers out of which 2 will reduce the image size followed by fully connected layers ending with a 10 neuron softmax layer.
## Model compiling
Adam optimizer, categorical crossentropy are considered to compile this model
## Model training
Normaized training image data and encoded labels are given to the model to train for 200 epochs ar a 128 batch size validating with test dataset.
## Ploting the results
There are 2 functions i have implemented for this phase.
1. A function that takes the model history and summarized it
2. A function that calculates accuracy

This model took 777.10 seconds to train in COLAB GPU and reached a accuracy of 74.22%