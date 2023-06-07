# VAE: Generating Fake Handwritten Digits

Hi, this demonstrates how to train a VAE model on the MNIST dataset. Unlike a traditional autoencoder, which converts the input image to a latent vector, a VAE model converts the input image into a mean and variance. 

By doing that, generating a continuous, structured latent space, which is useful for image generation.

This little unknown project references from a Tensorflow tutorial: https://www.tensorflow.org/tutorials/generative/cvae.

While studying it, I struggled with this little tricky thing called "Reparameterization trick". Wondering why I need it? While training a traditional AE model doesn't need one, though.

Even though I have studied both in a class and by myself on the theory, I still met this little obstacle.
