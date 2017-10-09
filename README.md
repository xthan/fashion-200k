## Fashion200K dataset

Fashion200K dataset used in ICCV'17 paper "Automatic Spatially-aware Fashion Concept Discovery." [[paper]](https://arxiv.org/pdf/1708.01311.pdf)

### Contact

Author: Xintong Han

Contact: xintong@umd.edu

### Dataset

This dataset is crawled from [Lyst.com](http://lyst.com) in September 2016. 

You can download the dataset via [Google Drive](https://drive.google.com/open?id=0B4Eo9mft9jwoamlYWFZBSHFzV3c):

image_urls.txt: Image urls. Format: ImageName ImageURL.

detection: Detection results. Format: ImageName Category_DetectionScore_xMin_xMax_yMin_yMax. We trained a [MultiBox](https://arxiv.org/pdf/1412.1441.pdf) detector for 9 classes (dress, skirt, top, bag, shorts, sunglasses, shoe, outwear, pants).

women.tar.gz: Cropped detected images. If you want the original images, they can be downloaded using their urls in image_urls.txt.

labels: train/test labels. Format: ImageName DetectionScore ProductDescription.

Note that there is information of more than 300k images in image_urls.txt and detection folder, but we remove around 100k images (see labels folder) because they have low detection scores.


### Code
You can refer to Tensorflow's [im2txt](https://github.com/tensorflow/models/blob/master/research/im2txt) for how to train the model. By setting f_rnn_loss_factor and g_rnn_loss_factor to 0 in the model configuration in this [repo](https://github.com/xthan/polyvore) can also train a visual-semantic embedding for the same purpose.

You can look at the original [CAM code](https://github.com/metalbubble/CAM/blob/master/pytorch_CAM.py#L41) to figure out how to extract activation maps in a joint embedding setting.

### Citation
    @inproceedings{han2017automatic,
      title = {Automatic Spatially-aware Fashion Concept Discovery},
      author = {Han, Xintong and Wu, Zuxuan and Huang, Phoenix X. and Zhang, Xiao and Zhu, Menglong and Li, Yuan and Zhao, Yang  and Davis, Larry S.},
      booktitle = {ICCV},
      year  = {2017},
    }
