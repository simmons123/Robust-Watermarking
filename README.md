# Embedding Guided End-to-End Framework for Robust Image Watermarking
## Overview
#### In this paper, an end-to-end framework based on embedding guidance is proposed for robust image watermarking. It contains four modules, i.e., prior knowledge extractor, encoder, attacking simulator, and decoder. To guide the watermark embedding, the prior knowledge extractor providing chrominance and edge information of cover images is used to modify cover images before inserting the watermark by the encoder. To enhance the robustness of watermark extraction, the attacking simulator applying various differentiable attacks on the encoded images is introduced before extracting the watermark by the decoder. Experimental results show that the proposed algorithm achieves a good balance between invisibility and robustness and is superior to state-of-the-art algorithms.

[Beibei Zhang,Yunqing Wu,1and Beijing Chen.Embedding Guided End-to-End Framework for Robust Image Watermarking.Security and Communication Networks/,2022;Article ID 7259469](https://www.hindawi.com/journals/scn/2022/7259469/)

## Prerequisites
#### Linux
#### NVIDIA GPU+CUDA CuDNN (CPU mode may also work, but untested)
#### Install Pytorch and dependencies


## Setup training 
#### 5,000 images randomly selected from the [COCO dataset](https://cocodataset.org/#download)  are used as cover images. Three types of images are taken as watermark images for experiments. They are 5,000 logo images randomly selected from logo-2k+ , 5,000 digital number images from MNIST, and 5,000 general images from ImageNet. These watermarks are converted into grayscale images before embedding. 5,000 cover images and each 5,000 watermark images are regarded as 5,000 pairs for the following experiments. Then, the cover images and watermark images are, respectively, divided into training/validation/testing sets according to the ratio of 8 : 1:1 and resized to 128 × 128.


#### The proposed watermarking model is trained iteratively using the ADAM optimizer with an initial learning rate of 1.0e-3. The batch size is set as 16. The weights in the loss function are set as α = 0.3, β = 0.7, and γ = 0.001. In addition, all simulated attacks have a hyperparameter governing the strengths: the kernel width ω of Gaussian blur is 3; quality factor QF of JPEG compression is 90; and ratios p of crop and dropout are 0.1 and 0.15, respectively.


## Realted Works

[[1] Zhu J, Kaplan R, Johnson J, et al. Hidden: Hiding data with deep networks. In Proceedings of the European Conference on Computer Vision (ECCV) 2018; 657-672.](https://openaccess.thecvf.com/content_ECCV_2018/html/Jiren_Zhu_HiDDeN_Hiding_Data_ECCV_2018_paper.html)

