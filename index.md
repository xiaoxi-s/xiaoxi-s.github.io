# Overview

Illumination prediction is a crutial component for augmented reality (AR) and mixed reality (MR) to produce expected virtual objects and scenes. 

 - importance, application
 - complexity

# State of Art
 

# Our Approach

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



### Labeler


### Accuracy

In general, accuracy for lighting evaluation can be tricky to evaluate. We use L2 distances with a predefined threshold to evaluate our model quantitatively. In particular, the location and the RGB value of a given light source are evaluated separately with their corresponding thresholds. However, as threshold based methods are susceptible to the limitations, we provide sensitivity analysis for our EXR model. 

 - JPG Model: Our JPG model achieves 18% accuracy when predicting the location of the light source given a threshold of 100 pixel distance. For predicting the RGB value, our JPG model achieves 89% accuracy given that the l2 norm of the predicted RGB value must be less than 100. The figure below shows the peformance on the test set. 

  ![JPG Color Accuracy](https://github.com/xiaoxi-s/Illumination-Prediction/blob/main/figures/03-12-2020_07-07-37_epoch-color-acc_no_fine_tune_warped.png)

  ![JPG Location Accuracy](https://github.com/xiaoxi-s/Illumination-Prediction/blob/main/figures/03-12-2020_07-07-37_epoch-loc-acc_no_fine_tune_warped.png)

 - EXR Model: For

#### Sensitivity Analysis for EXR model



### Rendering Examples


## Discussion

### Accuracy Measure



### Feature Extractor

Although this project is not aimmed at testing different feature extractors, we also tried another feature extractor, [wide residual network 50-2 (WRN)](https://arxiv.org/pdf/1605.07146.pdf). However, WRN is more computationally expensive (takes much longer to train) and yields much worse result than dense net. Therefore, we eventually stick to our initial choice. 

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
