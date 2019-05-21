# CS498AML-HW9
### Homework 9: Variational Autoencoders

## About
### Goal
This homework focuses on evaluating variational autoencoders applied to the MNIST dataset.

### Submission
Submission will be through gradescope.

### Code and External Libraries
The assignment involves PyTorch, so it must be done using Python only.

You may use any third-party code for the variational autoencoder. But for the rest part of the assignment, you are expected to write your own code.

## Problems
#### Total points: 100
An autoencoder is a type of artificial neural network used to learn efficient data codings in an unsupervised manner. Variational autoencoder (VAE) models inherit the autoencoder architecture, but make strong assumptions concerning the distribution of latent variables. You can use this post as a reference.

You have two options for this assignment:

Implement your own VAE. Download the Python Notebook here. Alternatively, you can access a read-only version on colab here of which you will need to make a copy. There are cells for you to input code, as well as text. Make sure to fill in all such cells before submission. Important information and sections are in bold.
Obtain a PyTorch code for a VAE from any resource, like the example in this blog.
Train this autoencoder on the MNIST dataset. Use only the MNIST training set for training.

Now determine how well the codes produced by this autoencoder can be interpolated. Use only the MNIST test set for this.

For 10 pairs of MNIST test images of the same digit (1 pair for "0", 1 pair for "1", etc.), selected at random, compute the code for each image of the pair. Now compute 7 evenly spaced linear interpolates between these codes, and decode the result into images. Prepare a figure showing this interpolate. Lay out the figure so each interpolate is a row. On the left of the row is the first test image; then the interpolate closest to it; etc; to the last test image. You should have a 10 rows (1 row per digit) and 9 columns (7 interpolates + 2 selected test images) of images. You should give a figure like (make yours bigger):
For 10 pairs of MNIST test images of different digits selected at random, compute the code for each image of the pair. Now compute 7 evenly spaced linear interpolates between these codes, and decode the result into images. Prepare a figure showing this interpolate. Lay out the figure so each interpolate is a row. On the left of the row is the first test image; then the interpolate closest to it; etc; to the last test image. You should have a 10 rows and 9 columns of images.
## Submission
Submit to gradescope:

A PDF file (named "{yournetid}_HW9.pdf") containing the following:

(45 points) Page 1: Same digit interpolates (Make your figure large!)
(45 points) Page 2: Different digit interpolates (Make your figure large!)
(10 points) Page 3+: Your code.
