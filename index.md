## Overview
======

Illumination prediction is a crutial component for augmented reality (AR) and mixed reality (MR) to produce expected virtual objects and scenes. 

 - importance, application
 - complexity

## State-of-Art

## Our Approach

 - Deep learning based
 - Simplified parametric estimation


### Network Architecture

The feature extractor is [dense121](https://arxiv.org/abs/1608.06993). The classification layer is replaced with two linear layers with a Relu activation between them. The output of the naive JPG model is different from that of the EXR model. The JPG model assumes there are three light sources in the environment map of an input image. 

### Data and Preprocess

 - Dataset
 - Labeling process

### Training

  - choice of weights
  - ...

## Result

In this section, we would provide the results of the pre-processing (labeling), evaluation of both the JPG and EXR model, and rendering exmaples. 

### Labeler


### Accuracy

In general, accuracy for lighting evaluation can be tricky to evaluate. We use L2 distances with a predefined threshold to evaluate our model quantitatively. In particular, the location and the RGB value of a given light source are evaluated separately with their corresponding thresholds. However, as threshold based methods are limited to the choice of thresholds, we provide sensitivity analysis for our EXR model to determine the effects of different thresholds. 

#### JPG Model
----

Our JPG model achieves around 18% accuracy when predicting the location of the light source given a threshold of 100 pixel distance. For predicting the RGB value, our JPG model achieves 85% accuracy given that the l2 norm of the predicted RGB value must be less than 100. The figure below shows the performance on the test set. 

  <p align="center">
  <img src="figures/accuracy/03-12-2020_07-07-37_epoch-color-acc_no_fine_tune_warped.png" alt="JPG Color Accuracy" width="400" height="" style="border:0px;margin:10px;float:center">
  
  <img src="figures/accuracy/03-12-2020_07-07-37_epoch-loc-acc_no_fine_tune_warped.png" alt="JPG Location Accuracy" width="400" height="" style="border:0px;margin:10px;float:center">
  </p>
  <br>

#### EXR Model


#### Sensitivity Analysis for EXR model
----

For the EXR model, we provide sensitivity analysis for its performance. 

Specifically, sensitivity analysis includes the following steps:

  - Determine a step size and a "reasonable" range of the parameter, in this case, the threshold for counting accuracy. 
  - Quantize the range with the step size to generate a sequence of thresholds. 
  - Evaluate the performance given each threshold in the sequence.
  - Normalize two sequences of thresholds (one for location accuracy, the other for color accuracy) to the range (0, 1] by dividing the maximum of the parameter. 
  - Plot the figure of normalized thresholds vs. accuracy.

As the label of location for EXR samples are angles, we choose the range to be \[pi/18, 3.20\]. For RGB values of EXR files, as the range is between [0, 1], we set the threshold to be within \[0.001, 1.2\]. The choice of the largest thresholds can be justified as follows. The key idea is to choose them to be the worst case. Notice that we did not use cosine loss function to train the network for location (coordinate) prediction. Therefore, the range for coordinates is fixed. In particular, the horizontal angle is in the range \[0, 2pi\]. and the vertical angle is in the range \[0, pi\]. For location prediction, as the system is spherical, the worst average difference between prediction and the ground truth is pi, which means the predicted coordinate is at the opposite direction to the ground truth. Thus, we choose the threshold to be slightly higher than pi. For RGB value prediction, EXR files have RGB values between \[0, 1\]. Then, the worst average difference is 1. Again, we choose a slightly higher value 1.2. 

### Rendering Examples



## Discussion



### Accuracy Measure



#### Sensitivity Analysis



### Feature Extractor

Although this project is not aimmed at testing different feature extractors, we tried another feature extractor, [wide residual network 50-2 (WRN)](https://arxiv.org/pdf/1605.07146.pdf). However, WRN is more computationally expensive (takes much longer to train) and yields much worse result than dense net. Therefore, we eventually stick to our initial choice. 

## Material

### Project Proposal

### Mid-term Report

## Reference



## Training Details

### Environment Specification
 - Dependencies: 

### Parameter Setting

 - Optimizer: [SGD](https://pytorch.org/docs/stable/optim.html?highlight=sgd#torch.optim.SGD)
 - Learning rate: 0.001
 - Momentum: 0.9
 - Batch size: 16 
 - Model type: float

### Network reference

 - Time for training with fine tune: 6.4 min/epoch
 - Time for training without fine tune: 2.7 min/epoch
 - network [reference](https://github.com/xiaoxi-s/Illumination-Prediction/blob/main/checkpoint/model_epoch_20_res_360x240)


# Welcome to GitHub Pages

You can use the [editor on GitHub](https://github.com/xiaoxi-s/xiaoxi-s.github.io/edit/main/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/xiaoxi-s/xiaoxi-s.github.io/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
