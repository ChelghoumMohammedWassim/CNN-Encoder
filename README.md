## Convolutional Neural Networks
A Convolutional Neural Network (CNN), a more capable and sophisticated variant of
traditional artificial neural networks, is designed to handle more complex data pre-
processing and computation tasks.

CNNs may be the most effective and adaptable model for image classification issues because
they were created for image data. CNNs can produce amazing results with non-image data
even though they weren't specifically designed to work with it.

There are 4 steps to building the CNN after importing your input data into the model:

1\. Convolution: a method for generating feature maps from our input data. Then, filters for
maps are applied using a function.

2\. Max-Pooling: This technique enables our CNN to recognize an image even when it has
been modified.

To make the data easier for CNN to read, flatten it into an array.

4\. Full Connection: The hidden layer that figures out our model's loss function.

## Autoencoders
The way autoencoders function is to automatically encode data based on input values, activate that data, and then decode the data for output. The input features were forcedtofitinto fewer categories by some kind of bottleneck. As a result, the autoencoder model will recognize any inherent structure in the data and use it to produce the output.

![image](https://github.com/ChelghoumMohammedWassim/CNN-Encoder/assets/101805975/00ac32cb-c34f-4c9a-a049-72f257b54974)

## Data Processing for Autoencoder Training Using Keras and TensorFlow
Let's prepare our input data. We only care about encoding and decoding the input images, sofor version 1, we use MNIST digits, and for version 2, we use alphabet images. we ignored the labels(y). We will simply normalize pixel values between 0 and 1 and use shape (samples, 28, 28,1).

## Use the Keras API of TensorFlow to create an autoencode
Let's start with one. The decoder will be made up of a stack of Conv2D and UpSampling2Dlayers, while the encoder will be made up of a stack of Conv2D and MaxPooling2D layers (max poolingwill be used for spatial down-sampling).we used the same model for the 2end version as well.

![image](https://github.com/ChelghoumMohammedWassim/CNN-Encoder/assets/101805975/0b5cf7ef-2bbe-425c-b138-00faf44b2ec5)

## Train The Model
First, we'll set up our model to use the Adam optimizer and a per-pixel binary crossentropy loss.Wewill now train our autoencoder for 20 epochs for aech dataset.
### MNIST
![image](https://github.com/ChelghoumMohammedWassim/CNN-Encoder/assets/101805975/2040d70c-9f7b-44e8-b34c-d4653f180b46)
After 20 epochs, the autoencoder appears to have stabilized at a validation loss value of about 0.0957.

### alphabet
![image](https://github.com/ChelghoumMohammedWassim/CNN-Encoder/assets/101805975/2b8d3200-981f-4bbb-abfa-0133188a5ed4)

After 20 epochs, the autoencoder appears to have stabilized at a validation loss value of about 0.1421.

## Autoencoder Predictions
Now let's look at the results. With simultaneous original and decoded images, we have the left
original image in the center encoded image and the left decoded image.
### MNIST :
![image](https://github.com/ChelghoumMohammedWassim/CNN-Encoder/assets/101805975/773f5e6d-1afc-4375-9197-1e63b594c965)
### alphabet:
![image](https://github.com/ChelghoumMohammedWassim/CNN-Encoder/assets/101805975/87507fb4-ecdf-485a-bd03-59d23e7324d3)
## Evaluation Model
To evaluate the model, we will compute the average uqi (universal image quality index) betweenoriginal images, decode the image, and consider the compression ratio.

![image](https://github.com/ChelghoumMohammedWassim/CNN-Encoder/assets/101805975/3ce5ab02-c58c-4ed4-bdeb-88385bf38f93)



