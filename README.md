# tf_cnn_gan
First attempt for Building CNN and vanilla GAN using TensorFlow (success!)


Repo Content:
1. cnn_gan.ipynb - main code

Data:
1. for CNN I used CIFAR-10 dataset
2. for GAN I used Fashion-MNIST dataset


CNN architecture:   
  
1. Convolutional layer with 64 filters of size 11x11 followed by ReLu activation function. Input: of original pictures from CIFAR10 dataset. 
2. Pooling layer of size 2x2 with stride = 2. Pools highest number from subregions filter convolves around. Thus, reduces number of parameters to estimate and controls for NN overfitting.  
3. Convolutional layer with 128 filters of size 3x3 followed by ReLu activation function.  
4. Convolutional layer with 128 filters of size 3x3 followed by ReLu activation function.  
5. Average pooling layer which pools across last conv layer output (feature map). Used to add translation invariance.  
6. End of network: Flattern, ReLu, Softmax - convert output features into interpretable format. Note, we use SoftMax because we have more than 2 label categories.  


IMPORTANT! Weights: HeNormal initializer which performs good with ReLu according to https://arxiv.org/pdf/1502.01852.pdf  


Hyperparameters:  

Number and size of filters are quite arbitrarily chosen, but I made some prior testing. 11x11 filter used for high level perspective and computational cost reduction.   Other conv layers have 3x3 filters, which is a common choice - small and odd.  
Stride = 2 meaning that filter shifts by 2 units (pixels) instead of 1. Decreases filters overlapping and results in smaller output dimension.   


![repo_pic](https://github.com/BananZza1998/Snaps_1/blob/main/CNN.png)
