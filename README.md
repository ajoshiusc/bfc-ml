# Bias Field correction in 3D-MRIs using Convolutional Autoencoders

Author: Shashank Nelamangala Sridhara.
University of Southern California.  
e-mail: nelamang@usc.edu 

## Problem Statement
 Bias Field correction is a crucial step in MRI preprocessing. The bias field affects the intensity uniformity in MRI images. This effect is mostly due to the in-homogeneity in the magnetic fields or variation in magnetic susceptibility during acquisition. The presence of bias field affects the tissue classification stage, as most of the common methods assume uniform intensities across  same tissue. We present a deep learning approach that uses an autoencoding architecture to predict the bias field. The performance of the method is evaluated based on tissue classification accuracy compared to the ground truth result. The proposed method outperforms a traditional histogram based method and results in a more accurate tissue classification.

## Network Architecture
For  the  neural  network  architecture,  we  used  a  convolutional  autoencoder.   Autoencoder learns to efficiently encode the data in compressed latent space and reconstruct the data back from the reducedencoded representation.  Instead of training the autoencoder to reconstruct the corrected MRI (bias-free MRI),it is trained to output the estimated bias field to preserve image details since pooling layers typically degradesimage details and generates over smooth restoration.Our deep convolutional autoencoder network is built with 16 hidden layers.  There are 8 layers on the encoder and 8 layers on the decoder side.  We used mean-squarederror for the loss function and Adam Optimizer for updating the weights.  The model was trained for 30 epochsof the training data using NVIDIA Tesla V100 GPU on Google cloud platform.

![Autoencoder Architecture](/Figures/autoencoder_architecture_1.png)

## Results
The estimated bias field from the autoencoder model is shown along with the ground truth bias field in below figure.  The bias field corrected MRIs, and tissue classification using histogram based and the proposed methods are shown in below figure.  We showed that the proposed method outperforms the histogram-based method in removingbias fields and achieves more accurate tissue classification.


![Result-1](/Figures/bias_field_comparison_poster.png)
![Result-2](/Figures/corrected-tissue-poster.png)
