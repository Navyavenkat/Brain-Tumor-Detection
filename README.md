# Brain Tumor Detection
# Data Preprocessing
For every image, the following preprocessing steps were applied:

Crop the part of the image that contains only the brain (which is the most important part of the image).
Resize the image to have a shape of (240, 240, 3)=(image_width, image_height, number of channels): because images in the dataset come in different sizes. So, all images should have the same shape to feed it as an input to the neural network.
Apply normalization: to scale pixel values to the range 0-1.
# Data Split:
The data was split in the following way:

70% of the data for training.
15% of the data for validation.
15% of the data for testing.
# Neural Network Architecture
This is the architecture 

Neural Network Architecture

# Understanding the architecture:
Each input x (image) has a shape of (240, 240, 3) and is fed into the neural network. And, it goes through the following layers:

A Zero Padding layer with a pool size of (2, 2).
A convolutional layer with 32 filters, with a filter size of (7, 7) and a stride equal to 1.
A batch normalization layer to normalize pixel values to speed up computation.
A ReLU activation layer.
A Max Pooling layer with f=4 and s=4.
A Max Pooling layer with f=4 and s=4, same as before.
A flatten layer in order to flatten the 3-dimensional matrix into a one-dimensional vector.
A Dense (output unit) fully connected layer with one neuron with a sigmoid activation (since this is a binary classification task).
Why this architecture?

Firstly, I applied transfer learning using a ResNet50 and vgg-16, but these models were too complex to the data size and were overfitting. Of course, you may get good results applying transfer learning with these models using data augmentation. But, I'm using training on a computer with 6th generation Intel i7 CPU and 8 GB memory. So, I had to take into consideration computational complexity and memory limitations.

So why not try a simpler architecture and train it from scratch. And it worked :)

# Training the model
The model was trained for 24 epochs and these are the loss & accuracy plots:
# Performance Analytics
 ![a](https://github.com/Navyavenkat/Brain-Tumor-Detection/assets/94165327/d69e7992-0d6d-4f55-8ae7-c76f8800df2d)

![a1](https://github.com/Navyavenkat/Brain-Tumor-Detection/assets/94165327/c4f0cd62-c7aa-4fb5-b24a-1ed7104d76ce)

The best validation accuracy was achieved on the 23rd iteration.

# Results
Now, the best model (the one with the best validation accuracy) detects brain tumor with:

88.7% accuracy on the test set.
0.88 f1 score on the test set.
These resutls are very good considering that the data is balanced.

# Performance table of the best model:
