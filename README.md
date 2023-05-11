# PaKoML IDOLGAN Project

<div align = "center"> 
<img src="https://github.com/PaKoML/IDOLGAN/assets/19871043/f388c23a-0ff9-433b-9343-16e9df915cb2"></img>

![license](https://img.shields.io/github/license/PaKoML/IDOLGAN.svg)
![repo size in bytes](https://img.shields.io/github/repo-size/PaKoML/IDOLGAN.svg)
![GitHub contributors](https://img.shields.io/github/contributors/PaKoML/IDOLGAN.svg)
![GitHub commit](https://img.shields.io/github/last-commit/PaKoML/IDOLGAN.svg)
![GitHub commit interval](https://img.shields.io/github/commit-activity/w/PaKoML/IDOLGAN.svg)
</div>

<div align = "center">

</div>

## Introduction 
<p>
Welcome to this Github repository, which presents a generative AI project utilizing a modified DCGAN model and minibatch discrimination technique to produce random Kpop idol portraits. The project has been trained on a dataset of Kpop female idols' images, and through deep learning algorithms, it has acquired the ability to generate realistic and unique images of Kpop idols. The modified DCGAN model and minibatch discrimination techniques have been incorporated into the project to enhance its ability to create high-quality and diverse images. With this project, users can effortlessly generate random Kpop idol faces and explore the extensive creative possibilities offered by generative AI. We invite you to join us on an exciting journey to explore the infinite potential of AI-generated art.</p>

## Architecture 
### Generator
<p>
The generator consists of a series of transposed convolutional layers. The initial layer takes the input noise vector $z\sim \mathcal{N}(\boldsymbol{0}, 0.02^2 \boldsymbol{I}_{512})$ and applies transposed convolution with a kernel size of 4, stride of 1, and padding of 0. Subsequent layers increase the spatial resolution by a factor of 2 while reducing the depth. The final layer generates a 64x64 RGB image using transposed convolution with a kernel size of 4, stride of 2, and padding of 1. Batch normalization and ReLU activation are applied throughout the model. The minibatch discrimination technique is used to enhance image diversity. The output image is resized to 64x64 using bilinear interpolation.
</p>

### Discriminator
<p>
The discriminator is consists of convolutional layers, each followed by batch normalization and LeakyReLU activation. These layers progressively reduce the spatial dimensions while increasing the number of channels in the tensor. The resulting tensor is flattened and passed through a fully connected layer, which maps it to a lower-dimensional feature space. A minibatch discrimination module is added in the middle of the discriminator architecture to enhance diversity among generated samples by comparing features within a minibatch.
</p>

## Datasets
The model is trained on about 5000 images of kpop idol's face image. The figures in the images is not evenly distributed, so the output result may be similar to some specific celebrity. 

## References
[1] Radford, A., Metz, L., & Chintala, S. (2015). Unsupervised representation learning with deep convolutional generative adversarial networks. arXiv preprint arXiv:1511.06434.
[2] Salimans, T., Goodfellow, I., Zaremba, W., Cheung, V., Radford, A., & Chen, X. (2016). Improved techniques for training gans. Advances in neural information processing systems, 29.
[3] Minibatch discrimination module in PyTorch. (n.d.). Gist. https://gist.github.com/t-ae/732f78671643de97bbe2c46519972491


## Developers
* [Minjun Kim](https://github.com/kmj0825) 
* [Hanbin Park](https://github.com/kimchyoungman)
* [Jihwan Hong](https://github.com/Jordano-Jackson)



