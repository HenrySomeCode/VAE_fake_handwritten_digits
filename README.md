# VAE: Generating Fake Handwritten Digits

Hi, this demonstrates how to train a VAE model on the MNIST dataset. Unlike a traditional autoencoder, which converts the input image to a latent vector, a VAE model converts the input image into a mean and variance. 

By doing that, generating a continuous, structured latent space, which is useful for image generation.

This little unknown project references from a Tensorflow tutorial: https://www.tensorflow.org/tutorials/generative/cvae.

While studying it, I struggled with this little tricky thing called "Reparameterization trick". Wondering why I need it? While training a traditional AE model doesn't need one, though.

Even though I have studied both in a class and by myself on the theory, I still met this little obstacle.

So my assumption is that, different from AE, latent space is now no longer a vector. It's a distribution defined by the parameters outputted by the encoder. Or maybe it's a random vector from that distribution that cause a challenge for the backpropagation process of the encoder.

For that reason, "Reparameterization trick" came into the picture. Its formula is z = mean + std*e where mean and std is from a Gaussian distribution BUT derived from the decoder output. 

The 'e' in the formula represents a random noise used to maintain stochasticity of z. It's also from a normal distribution. Now the gradients of the encoder in backpropagation is achieved by mean and std derived from the decoder output.  

Also, I have learned that it's common practice to avoid using batch-norm when training the VAE model since the additional stochasticity when using mini-batches may make the model worse when we already add stochasticity from creating z.

But..well, until this time, I still get confused when it comes to the loss, optimizer, and training process of this model, so I hope that I can get it entirely in the future! 
