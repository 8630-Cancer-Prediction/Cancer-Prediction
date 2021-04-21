There are two forms of autoencoders here.  They can be thought of as self-supervised neural networks. 
The SAE is the normal stacked autoencoder and the SDAE is the stacked denoising autoencoder. 
The denoising AE adds Gaussian noise to the dataset (0.1 st. dev.). 

Both are comprised of 7 layers of nodes. 
They follow a bottle neck architecture as follows: 20533 (# of features in input) >15000 > 8000 > 4000 (bottleneck, 5:1 compression). 
This is known as the encoder piece which is used to compress the data. 

The decoder piece returns the original input (4000 > 8000 > 15000 > 20533). 
This is a method of feature extraction not feature selection, therefore the purpose is not to know which genes are important, only to improve accuracy. 

The validation statistics, with 500 epochs and 250 batch size, for both models are as follows:
SAE = 0.0641 loss, 79.45% accuracy
SDAE = 0.0592 loss, 80.82% accuracy
