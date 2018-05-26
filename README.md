# NERmultimodal
## 1.Introduction
Keras Implementation of "Adaptive Co-attention Network for Named Entity Recognition in Tweets". 
This project is re-developed from https://github.com/jlfu/NERmultimodal, which is developed with Python2.7 and Keras 1.2.

## 2. Environment
1) Anaconca 5.1.0
2) Python 3.5 (Conda environment)
3) ~~Theano 1.0.1~~ Tensorflow 1.8.0 with gpu
4) keras 2.1.5 with [keras-contrib](https://github.com/keras-team/keras-contrib)(CRF support)
5) The image features were extracted from 16-layer VGGNet. Before extracting the features, you need to download a pretrained model: [vgg16_weights_th_dim_ordering_th_kernels_notop.h5](https://code.vi-seem.eu/Risojevic/hrrs_image_classification/blob/a8906ce4745b8809d49a927cc96002437e63575a/Models/vgg16_weights_th_dim_ordering_th_kernels_notop.h5).
4) Word embedding trained by tweets from ~~http://pan.baidu.com/s/1boSlljL~~ --> [glove-twitter-200](https://github.com/RaRe-Technologies/gensim-data)

## 3. Data(Offered by [jlfu](https://github.com/jlfu))
> Our datasets include 8,257 tweet and image pairs. We split the dataset into three parts: the training set, development set, and testing set, which contain 4,000, 1,000, and 3,257 tweets, respectively.  
>
> We set an image id for each picture, and we put this image id in the begging of a tweet. We use a blank line to split a sample. Here's an example of such a file:
>
> IMGID:50447     
> RT	O        
> @washingtonpost	O        
> :	O        
> Two	O        
> maps	O        
> that	O        
> show	O        
> the	O        
> shocking	O        
> inequality	O        
> in	O        
> Baltimore	B-LOC        
> http://t.co/FssPdKxglv	        
> http://t.co/JZiqXSTNec        
>
> IMGID:418340        
> Rep	O        
> .	O        
> Howard	B-PER        
> Coble	I-PER        

## 4. Some "Gotcha"
1. keras.json
``` 
{
    "floatx": "float32",
    "epsilon": 1e-08,
    "image_data_format": "channels_first",
    "image_dim_ordering": "th",
    "backend": "tensorflow"
}

``` 
2. [glove-twitter-200](https://github.com/RaRe-Technologies/gensim-data) need to be converted to word2vec format

3. …………………………