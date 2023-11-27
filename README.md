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
