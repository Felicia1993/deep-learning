# GAN
A [**Generative Adversarial Network (GAN)**](https://en.wikipedia.org/wiki/Generative_adversarial_network) has two parts:

The **Generator** learns to generate plausible data. The generated instances become negative training examples for the discriminator.    

The **Discriminator** learns to distinguish the Generator's fake data from real data. The Discriminator penalizes the generator for producing implausible results.    

When training begins, the generator produces obviously fake data, and the discriminator quickly learns to tell that it's fake. As training progresses, the Generator gets closer to producing output that can fool the discriminator.     

For the Generator, it takes a batch of random noises as inputs and generates an image for each noise vector.
The random noises have a shape (B, 100). Here B is the batch size, and 100 is the dimension of each noise vector. We then convert the shape to (B, 100, 1, 1), i.e., (batch_size, channels, height, width), to make it suitable for convolutional operations.
As shown in the figure below, our Generator consists of four convolutional layers, it enlarges the resolution of feature maps and obtains the generated images as outputs with a shape (B, 3, 32, 32).     

<img src="http://yty.kapsi.fi/DLcourse/ass4/Generator.png" width="600" style="float: left;">     

For the Discriminator, it takes a batch of images as inputs and make their classification outputs of real or fake.
- The image inputs have a shape `(B, 3, 32, 32)`, i.e., `(batch_size, channels, height, width)`.
- The classification outpus are with a shape `(B, 1, 1, 1)`, we then flatten it to a vector with a shape `(B, )` to make the loss computation friendly.

The detailed structure of Discriminator is shown as follows:   
<img src="http://yty.kapsi.fi/DLcourse/ass4/Discriminator.png" width="600" style="float: left;">
