# GAN-on-CIFAR-10
GANS - Generative Adversarial Networks on CIFAR-10
GANs are a class of Unsupervised Learning Algorithms that do much more than just recognizing image / voice , predicting or translating. They implement deep neural networks or CNN and are comprised of two parts, pitting one against the other (thus the “adversarial”). These two parts are called the Generator and the Discriminator.
Generator - The generator takes the role of a forger and tries to create music/image/speech from random noise. It learns to map from a latent space to a particular data distribution of interest. It generally implements a Deconvolutional Network to do so.
Discriminator- The Discriminator on the other hand takes the role of the evaluater and tries to distinguish the fake data (created by the Generator) from the real one. It is usually implemented as a Convolutional Network.
 
With that said what follows is a loop in which -
•	The generator tries to maximize the probability of fooling the Discriminator by making the images(for example) more close to real in each step thereby making the Discriminator classify them as real.
•	And the discriminator guides the generator to produce more realistic images , by classifying it's images as fake.

I will use CIFAR-10 which is a dataset that consists of 60000 32x32 colour images in 10 classes, with 6000 images per class. There are 50000 training images and 10000 test images.
These images along with the fake ones will be fed in batches to the Discriminator.Let's take a look at the steps our GAN will follow-
1.	The Generator takes in random numbers and returns an image.
2.	This generated image is fed into the Discriminator alongside a stream of images taken from the actual dataset.
3.	The Discriminator takes in both real and fake images and returns probabilities, a number between 0 and 1, with 1 representing a prediction of authenticity and 0 representing fake.


There are 2 feedback loops :-
1.	The Discriminator is in a feedback loop with the ground truth of the images (are they real or fake), which we know.
2.	The Generator is in a feedback loop with the Discriminator (did the Discriminator label it real or fake, regardless of the truth).

